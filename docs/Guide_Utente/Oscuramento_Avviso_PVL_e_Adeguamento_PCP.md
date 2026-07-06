# Oscuramento Avviso, Allineamento e Rettifica

## 1 Obiettivo del documento

Il presente documento descrive il processo di gestione degli avvisi oscurati nell’ambito dell’integrazione tra la Piattaforma Contratti Pubblici (PCP) e la Piattaforma di Pubblicità a Valore Legale (PVL).

Sono illustrati:

- il comportamento del sistema in caso di oscuramento di un avviso;
- le modalità di allineamento delle informazioni tra PVL e PCP;
- i servizi disponibili per la consultazione del dettaglio dell'oscuramento;
- il processo di rettifica finalizzato alla ripubblicazione dell'avviso.

Il documento è rivolto alle Piattaforme di Approvvigionamento Digitale (PAD) che utilizzano i servizi di pubblicazione e consultazione degli avvisi.

---

## 2 Descrizione del contesto

Nel contesto **pubblicaAvviso**, PCP consente la pubblicazione, la rettifica e l'annullamento degli avvisi associati ad un appalto.

A seguito della ricezione di una richiesta di pubblicazione o rettifica, PVL esegue i controlli previsti dalle proprie regole di validazione e pubblicazione.

Qualora siano rilevate anomalie o informazioni che impediscono la pubblicazione dell'avviso, PVL può procedere al relativo oscuramento e notificarne l'esito a PCP.

L'allineamento tra i due sistemi avviene mediante flussi asincroni che consentono a PCP di mantenere aggiornato lo stato dell'avviso e le relative informazioni di dettaglio.

---

## 3 Descrizione del processo

Il processo di gestione dell'oscuramento prevede i seguenti passaggi:

1. La PAD invoca il servizio **pubblica-avviso** oppure **rettifica-avviso**.
2. PCP trasmette la richiesta a PVL.
3. PVL esegue i controlli di competenza sull'avviso.
4. Qualora l'avviso non possa essere pubblicato o debba essere oscurato, PVL genera un evento contenente il dettaglio delle verifiche effettuate.
5. L'evento viene trasmesso a PCP mediante un canale asincrono.
6. PCP aggiorna lo stato dell'avviso e memorizza il dettaglio dell'oscuramento.
7. Le informazioni risultano successivamente disponibili tramite i servizi di consultazione.

---

## 4 Allineamento asincrono

L'aggiornamento delle informazioni tra PVL e PCP avviene in modalità asincrona.

Di conseguenza, l'esito di un oscuramento potrebbe non risultare immediatamente visibile al termine della richiesta di pubblicazione o rettifica.

L'allineamento si considera completato quando PCP acquisisce ed elabora la notifica proveniente da PVL, aggiornando le informazioni di stato e rendendo disponibili le evidenze dell'oscuramento tramite i servizi di consultazione.

---

## 5 Effetti dell'oscuramento

A seguito della ricezione di una notifica di oscuramento, PCP provvede a:

- aggiornare lo stato dell'avviso, facendolo transitare in "NON PUBBLICATO";
- registrare il dettaglio delle informazioni associate all'oscuramento;
- rendere disponibile il dettaglio tramite il servizio **consulta-avviso-oscurato**;
- aggiornare i servizi di consultazione che espongono informazioni relative a pianificazioni, appalti, schede e avvisi;
- applicare, ove previsto, le regole di esclusione degli avvisi oscurati dai risultati di ricerca;
- registrare l'esito dell'avvenuta operazione di oscuramento.

---

## 6 Consultazione dell'avviso oscurato

Per verificare le motivazioni che hanno determinato l'oscuramento di un avviso, la PAD può utilizzare i servizi di consultazione dedicati.

### Descrizione dei servizi

- **consulta-avviso**: consente di recuperare le informazioni di dettaglio dell'avviso e il relativo stato.
- **consulta-avviso-oscurato**: consente di consultare le informazioni che hanno determinato l'oscuramento dell'avviso.
- **esito-operazione**: permette di monitorare lo stato delle operazioni di pubblicazione e rettifica.

Attraverso tali servizi è possibile identificare con precisione i dati che necessitano di correzione prima di procedere con una nuova richiesta di pubblicazione.

---

## 7 Rettifica dell'avviso

Nel caso di oscuramento, la PAD può procedere mediante il servizio **rettifica-avviso**.

### Descrizione del servizio

Il servizio consente di trasmettere una nuova versione dell'avviso corretta con le modifiche necessarie alla risoluzione delle anomalie evidenziate da PVL.

L'operazione di rettifica deve essere effettuata mantenendo invariato, ove presente, l'eForm TED dell'avviso originario, al fine di preservare la continuità del processo di pubblicazione.

### Flusso operativo

1. Consultare il dettaglio dell'oscuramento tramite il servizio **consulta-avviso-oscurato**.
2. Correggere o integrare le informazioni che hanno determinato il blocco della pubblicazione.
3. Predisporre l'avviso di rettifica mantenendo il medesimo eForm TED dell'avviso originario.
4. Invocare il servizio **rettifica-avviso**.
5. Monitorare l'avanzamento dell'operazione mediante il servizio **esito-operazione**.
6. Verificare il nuovo stato attraverso il servizio **consulta-avviso**.

L'obiettivo della rettifica è consentire una nuova valutazione da parte di PVL senza generare una nuova pubblicazione TED non necessaria.

---

## 8 Casi d'uso principali

### 8.1 Avviso non ancora pubblicato

In questo scenario l'avviso si trova in fase di pubblicazione e PVL rileva condizioni che ne impediscono la diffusione.

Il sistema:

- procede con l'oscuramento dell'avviso;
- notifica l'evento a PCP;
- aggiorna lo stato dell'avviso dopo l'elaborazione della notifica.

### 8.2 Avviso già pubblicato

In questo scenario PVL rileva successivamente elementi che richiedono un intervento sull'avviso già pubblicato.

Il sistema:

- registra l'evento di oscuramento o l'aggiornamento dei metadati dell'avviso;
- notifica l'evento a PCP;
- rende disponibili le informazioni aggiornate tramite i servizi di consultazione.

In entrambi i casi, le informazioni restituite dal servizio **consulta-avviso-oscurato** costituiscono il riferimento per individuare le correzioni necessarie e procedere con una eventuale rettifica.

## 9. I controlli di PVL: cosa blocca la pubblicazione

### 9.1 Come funziona
Prima di pubblicare un avviso, PVL verifica che tutti i campi obbligatori siano presenti, valorizzati e coerenti. I controlli sono definiti da regole configurate per tipologia di avviso e vengono eseguiti automaticamente a ogni invio.

L'esito di ogni controllo ricade in una di tre categorie:

| Esito | Significato pratico                                                                                                                             |
|---|-------------------------------------------------------------------------------------------------------------------------------------------------|
| **KO** | Campo mancante o non valido che blocca la pubblicazione e causa l'oscuramento dell'avviso                                                       |
| **Non conforme** | Anomalia segnalata nel dettaglio, ma non bloccante                                                                                              |
| **Warning** | Segnalazione informativa, impedisce la pubblicazione e causa l'oscuramento dell'avviso (al momento non sono presenti campi con questa severity) |

Quando un avviso viene oscurato, il dettaglio riportato in PCP distingue i campi `invalidFields` (KO, da correggere obbligatoriamente) da `nonConformeFields` e `warningFields`.

### 9.2 Cosa controlla PVL su ogni campo
Per ciò che riguarda i campi soggetti a controlli, questi sono attualmente disattivati e saranno progressivamente introdotti, riportandone il dettaglio in questo paragrafo stesso man mano che verranno rilasciati.

## 10. Buone pratiche operative
- Verificare sempre il dettaglio di oscuramento prima di rettificare.
- Limitare la rettifica ai dati strettamente necessari allo sblocco.
- Mantenere eForm TED identico quando il caso richiede sola rettifica per nuova pubblicazione PVL.
- Dopo l'invio, verificare nuovamente i servizi di consultazione PCP per conferma dello stato aggiornato.

## 11. Messaggio chiave per gli utenti
L'oscuramento non e' una semplice anomalia tecnica: e' un esito funzionale gestito in modo orchestrato tra PVL e PCP.

PVL determina e notifica l'oscuramento, PCP recepisce in asincrono, traccia il dettaglio e lo espone ai servizi di consultazione, permettendo all'utente di eseguire una rettifica mirata e riprendere correttamente il ciclo di pubblicazione.
