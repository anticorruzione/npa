# AVVISI:
## 1
E' stata pubblicata sulla PDND di attestazione e di esercizio la nuova versione dei servizi FVC che include il richiedi-documenti in POST

## 2
Come da [roadmap](/docs/specifiche-jws/roadmap.md), si ricorda a tutti i soggetti che sono stati autorizzati all’accesso temporaneo agli eService della Piattaforma Contratti Pubblici, che a partire dal 9 ottobre 2023, per poter accedere agli eService attualmente disponibili che implementano il contesto di sicurezza, dovranno effettuare l’onboarding su PDND attraverso la richiesta di iscrizione tra le piattaforme certificate come indicato nelle [regole tecniche](https://www.agid.gov.it/it/piattaforme/procurement/certificazione-componenti-piattaforme) emanate da AgID 

## 3
Attivato il nuovo ambiente di ATTESTAZIONE per le piattaforme.
L'ambiente è destinato all'esecuzione di test funzionali per la verifica delle attività di MAC, è esposto su PDND e disponibile alle sole piattaforme certificate.
ANAC non garantisce livelli di servizio sulla disponibilità dell'ambiente ed è ammesso un disallineamento temporaneo di versione tra tale ambiente e quello di esercizio in coincidenza con le operazioni di rilascio di MAC, MAD o MEV.
Di tale attività viene data informazione sul presente canale, il disallineamento può avere una durata fino a 3 giorni lavorativi.
Nella sezione Ambienti di interoperabilità i dettagli per la connessione

# Descrizione
Il repository contiene la documentazione tecnica dei servizi di cooperazione applicativa che **le stazioni appaltanti** possono utilizzare per integrarsi con la Nuova Piattaforma Appalti (NPA) e con il Fascicolo Virtuale dell'Operatore Economico (FVOE) messi a disposizione dall'Autorità Nazionale Anticorruzione (ANAC), per governare l'ecosistema nazionale di approvvigionamento digitale per la gestione degli appalti pubblici.

# Ambienti di interoperabilità
La piattaforma PCP è disponibile esclusivamente attraverso l'infrastruttura PDND. Per le modalità di accesso a PDND e le indicazioni operative per la fruizione degli e-services si faccia riferimento alla documentazione presente sul portale PDND
Sono previsti tre distinti ambienti disponibili alle Piattaforme Digitali di Approvvigionamento (PDA). Gli end point dei servizi sono pubblicati su PDND, per ogni ambiente è necessario attivare una fruizione.

## Ambiente di QUALIFICAZIONE
L'ambiente di qualificazione è destinato alle PDA durante la fase di certificazione dei propri componenti.
L'accesso all'ambiente è garantito ai soggetti iscritti nel Registro delle Piattaforme Certificate, pubblicato da ANAC e gestito da AgID, che sono in fase di certificazione.
Per le modalità di presentazione della domanda di certificazione si faccia riferimento alle norme tecniche ed alle istruzioni operative pubblicate da AgID sul proprio portale.
Gli utenti e le stazioni appaltanti di test sono generati da ANAC e comunicati al gestore della piattaforma in fase di cerificazione.
La richiesta di generazione di utenti di test può essere fatta invianfo un'email a ufficio.uscp@anticorruzione.it

## Ambiente di ATTESTAZIONE
L'ambiente di ATTESTAZIONE è destinato alle PDA durante la fase di esercizio dei propri componenti.
L'accesso all'ambiente è garantito ai soggetti iscritti nel Registro delle Piattaforme Certificate che hanno già conseguito la certificazione.
Gli utenti e le stazioni appaltanti di test sono i medesimi generati da ANAC per l'ambiente di QUALIFICAZIONE.
La richiesta di generazione di ulteriori utenti di test può essere fatta inviando un'email a ufficio.uscp@anticorruzione.it

## Ambiente di ESERCIZIO
L'ambiente di ESERCIZIO è destinato alle PDA durante la fase di esercizio dei propri componenti.
L'accesso all'ambiente è garantito ai soggetti iscritti nel Registro delle Piattaforme Certificate che hanno già conseguito la certificazione.
E' richiesta l'iscrizione degli utenti sul sistema di gestione utenti di ANAC e per le stazioni appaltanti la corretta iscrizione in AUSA.

# Documentazione
## Specifiche delle interfacce
 - Il [file YAML](/docs/specifiche-interfacce/specifiche-servizi-appalto.yaml) relativo alle specifiche dei servizi esposti dalla NPA per la gestione del Ciclo di vita dell'Appalto
 - Il [file YAML](/docs/specifiche-interfacce/specifiche-servizi-fvoe-fva.yaml) relativo alle specifiche dei servizi esposti dalla NPA per la gestione del Fascicolo Virtuale dell'Operatore Economico e del Fascicolo Virtuale dell'Appalto
 - Il [documento](/docs/specifiche-interfacce/documento-specifiche-servizi-npa.md) di sintesi di Specifica delle Interfacce redatto utilizzando il linguaggio di markup Markdown
 - Il [documento](/docs/specifiche-jws/specificheJWS.json) riporta la struttura del token JWS che deve essere generato dal fruitore per l'interazione con gli eService esposti da ANAC. Qui è consultabile [roadmap](/docs/specifiche-jws/roadmap.md) con la previsione dell'attivazione delle restrizioni all'accesso in seguito all'adozione del JWS.

## Modello dati
Il modello dati di NPA rappresenta l'insieme di informazioni oggetto del monitoraggio dell'appalto. I dati che riguardano l'appalto sono organizzati in oggetti autoconsistenti denominati "Schede". Ogni evento significativo ai fini del monitoraggio di un appalto o ogni richiesta di azione (ad es la pubblicazione di un avviso) vengono notificati alla NPA tramite l'invio di una opportuna scheda.
La superclasse dalla quale derivano tutte le schede è riportata di seguito: 

```shell
AvvisoRequest{
  idAvviso* [...],
  idAppalto* [...],
    scheda SchedaGroupType{
      oneOf ->	
        SchedaPianificazioneType{
          _idScheda {...},
          codice* {...},
          versione* [...],
          _stato {...},
          _dataCreazione {...},
          body	{
            oneOf ->	
              SchedaPIN_1Type {...}
              SchedaPIN_2Type {...}
              ...
            }
        }
        SchedaComunicaAppaltoType{
          _idScheda {...},
          codice* {...},
          versione* [...],
          _stato {...},
          _dataCreazione {...},
          body	{
            oneOf ->	
              SchedaP1_10Type {...}
              SchedaP1_11Type {...}
              SchedaP1_12Type {...}
              SchedaP1_13Type {...}
              ...
          }
       }
       SchedaPostPubblicazioneType{
         _idScheda {...},
         codice* {...},
         versione* [...],
         _stato {...},
         _dataCreazione {...},
         body	{
           oneOf ->	
              SchedaA1_29Type {...}
              SchedaA1_30Type {...}
              ...
         }
      }
   }
 }
 ```
Durante l'esercizio della piattaforma NPA il processo di aggiornamento del modello dati sarà continuo, gli aggiornamenti verranno riportati nel presente repository e la loro efficacia è regolata secondo le specifiche del paragrafo [Termini del servizio](#termini-del-servizio). Le piattaforme interoperabili con NPA sono tenute all'aggiornamento del payload inviato entro i tempi previsti.

La cartella [modello-dati](/docs/modello-dati/) contenente la definizione dinamica del modello dati referenziato nelle specifiche dei servizi esposti dalla NPA. *Esempio*:
 ```shell
 StatoAppaltoEnum:
   $ref: 'https://raw.githubusercontent.com/anticorruzione/npa/main/docs/modello-dati/modello-dati-npa.yaml#/components/schemas/StatoAppaltoEnum'
 ```
## Gestione del processo
La gestione del processo di appalto è demandata al componente NPA di orchestrazione che, tramite il suo motore di regole, ha il compito di gestire il flusso di informazioni (schede) che caratterizzano il singolo appalto. 
Il modulo di ochestrazione è un componente di backend che non espone servizi in interoporabilità ma ha il compito di:
 - effettuare la validazione sintattica e semantica dei dati di input
 - verificare se la scheda dati passata in input è coerente con lo stato dell’Appalto. 
 - attivare uno o più servizi di backend per soddisfare le richieste avanzate dal fruitore (ad es. pubblicazione di un avviso, richiesta di documenti ad altri Enti)
 - In caso non siano rilevate anomalie, far avanzare il processo allo stato successivo.

Lo schema delle regole di orchestrazione è consultabile nella cartella [orchestratore](/docs/orchestratore/). Le piattaforme fruitrici dei servizi di NPA sono tenute ad adeguare la sequenza di invio delle informazioni al flusso descritto.

Le regole di validazione sintattica (tipo e obbligatorietà del campo) sono definite nelle specifiche dei servizi dettagliate al paragrafo [Specifiche delle interfacce](#specifiche-delle-interfacce). 
La validazione sintattico/semantica è completata tramite regole espresse con annotazione DMN, definite nella cartella [regole](/docs/modello-dati/regole/), leggibili attraverso un qualunque interprete DMN come ad esempio [demo.bpmn.io](https://demo.bpmn.io/)

Al pari del modello dati le regole che gestiscono il flusso delle informazioni sono soggette a variazioni continue in adeguamento alla normativa di settore, gli aggiornamenti verranno riportati nel presente repository e la loro efficacia è regolata secondo le specifiche del paragrafo [Termini del servizio](#termini-del-servizio). Le piattaforme interoperabili con NPA sono tenute all'aggiornamento del flusso di lavoro entro i tempi previsti.

## Modello statico e dinamico
I diagrammmi di contesto, di sequenza e di transizione di stato per l'intero Ciclo di Vita dell'Appalto sono consultabili nella cartella [diagrammi-drawio](/docs/diagrammi-drawio/) e, sono stati disegnati mediante l'utilizzo di [Draw.io](https://www.draw.io/).
Gli stessi sono anche disponibili in formato immagine nella nella cartella [immagini](/docs/immagini/).

# Termini del servizio
Le specifiche di interoperabilità per NPA sono presenti esclusivamente su questo repository. 
L'aggiornamento della documentazione può avvenire in qualsiasi momento e non verrà pubblicizzata in altro modo, gli utenti fruitori sono tenuti a consultare periodicamente il repository per ottenere le nuove specifiche.

## Tempi di adozione delle nuove specifiche
Nella tabella seguente sono disciplinati i tempi massimi e minimi per l'adozione da parte di NPA delle nuove specifiche e la conseguente eventuale deprecazione delle precedenti. In casi specifici, di particolare urgenza o in adempimento a normative di settore, ANAC può indicare tempi più ristretti ripetto a quelli standard.
 - Nuovi servizi o operazioni: non prima di 90 giorni dal rilascio della specifica;
 - Aggiornamento di servizi esistenti con deprecazione e mantenimento della versione precedente: non prima di 90 giorni dal rilascio della specifica;
 - Mantenimento della versione deprecata di un servizio: non meno di 180 giorni dal rilascio della specifica della nuova versione;
 - Aggiornamento di servizi esistenti con radiazione della versione precedente: non prima di 180 giorni dal rilascio della specifica;
 - Aggiornamento modello dati: non meno di 30 giorni e non più di 90 giorni dal rilascio della specifica
 - Aggiornamento del flusso di monitoraggio*: non meno di 30 giorni e non più di 90 giorni dal rilascio della specifica

**NB**: l'aggiornamento del flusso di monitoraggio può includere l'aggiornamento o l'estensione del modello dati anche mediante l'introduzione di nuove schede.

## Standard adottati
 - eForms sdk versione 1.9.0;
 - ESPD versione 2.1.1;

**NB**: nel momento in cui il sistema sarà in esercizio, l'upgrade delle versioni utilizzate sarà pubblicato con almeno 90 giorni di anticipo.

## Domande, chiarimenti e ulteriori infomazioni
Il canale di comunicazione con ANAC è rappresentato dall'apposita sezione [Issues](https://github.com/anticorruzione/npa/issues) nella quale sarà possibile inserire una richiesta.

## Scenari di esempio
La cartella [scenari-di-esempio](docs/scenari-di-esempio) contiene una sequenza di operazioni da eseguire per ottenere l'aggiudicazione di un appalto

## Disclaimer
L’Autorità Nazionale Anticorruzione si riserva la facoltà di non fornire risposta puntuale a tutte le issues ricevute ed è sollevata da eventuali responsabilità dovuta:
- alla mancanza di risposta per richieste pervenute al di fuori dell'unico canale di comunicazione con ANAC rappresentato dalla sezione [Issues](https://github.com/anticorruzione/npa/issues)
- alla possibile mancanza di risposta per tutte le richieste pervenute nell'apposita sezione Issues o che potrebbero essere di competenza di organizzazioni esterne.

# Roadmap del progetto
Le scadenze principali del progetto (milestones) sono consultabili nella [Roadmap](./roadmap.md). Fermo restando le scadenze principali la roadmap può essere aggiornata in qualunque momento
