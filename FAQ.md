# FAQ per il progetto della Piattaforma Contratti Pubblici

## PDND Interoperabilità

### PDND Interoperabilità - Errore nel caricamento dell'Accordo di adesione

Nel caso di errore nel caricamento dell'accordo di adesione a completamento dell'iter di onboarding i motivi possono essere:
errore generico: errore non ben individuato ma che non ha permesso di completare la registrazione;
errore per allegato non conforme: l’accordo di adesione non ha il formato aspettato oppure non coincide con quello inviato dalla piattaforma, ad esempio quando è stato firmato ed è stato anche protocollato e il sistema non lo riconosce più;
errore per firma digitale non riconducibile al Legale Rappresentante indicato in fase di adesione al prodotto: il firmatario non coincide con quanto dichiarato nel documento;
errore per invalidità dell’operazione, ossia tutti i casi in cui la richiesta sia già stata completata, cancellata o scaduta (passati i 30 giorni dall’invio della richiesta).
Qualora il link presente nella PEC non fosse più valido bisognerà inserire una nuova richiesta di fruizione.
Se l'errore è del terzo tipo, si può far fare firmare di nuovo il documento e usare lo stesso link per caricare l'Accordo con la sua nuova firma.

### PDND Interoperabilità - Finalità con stato "In aggiornamento"

Una finalità che è stata attivata può presentare come nuovo stato "In aggiornamento" quando il fruitore decide di aggiornare la stima di carico. Se la nuova stima rispetta tutte le soglie impostate dall’erogatore, la finalità vecchia con la nuova soglia sarà attivata automaticamente. In caso contrario, l’erogatore la individuerà tra quelle “In attesa di approvazione” e dovrà ripetere il processo di attivazione. Fino a che la nuova soglia non viene attivata, il fruitore può continuare ad utilizzare la finalità attiva con la soglia precedente.
L’attivazione di una finalità che supera una o più soglie è sempre e solo manuale ad opera dell’erogatore. L’azione di attivazione è irreversibile.
Se una finalità rimane per lungo tempo nello stato "In aggiornamento" bisogna contattare direttamente l'erogatore in modo da farla attivare.

### PDND Interoperabilità - Ruoli e permessi

Su PDND Interoperabilità ci sono tre diversi tipi di utenza, ognuna con i suoi permessi specifici per operare sulla piattaforma:

**Amministratore (operatore amministrativo)**
Questi sono di fatto delegati dal legale rappresentante ad operare con pieni poteri su PDND Interoperabilità. Utenti con questi permessi possono ad esempio inoltrare, sospendere e riattivare richieste di fruizione agli e-service, creare client e finalità, aggiungere, rimuovere o sospendere figure operative, compilare analisi del rischio e fare tutte le operazioni che competono a livelli di permesso inferiori.
Nell'ambiente di produzione si possono nominare massimo 3 amministratori, a differenza dell'ambiente di collaudo dove se ne possono nominare infiniti.

**Operatore API**
Un operatore API è un'utenza tecnica dedicata a un aderente che opera in modalità erogazione. Può gestire il ciclo di vita degli e-service per conto di utenze con permessi di amministrazione.

**Operatore di sicurezza**
Un operatore di sicurezza è un'utenza tecnica dedicata a un aderente che opera in modalità fruizione. Può vedere solo i client ai quali è associato. Per questi client, può caricare ed eliminare chiavi pubbliche. Con le chiavi caricate, può portare a compimento la procedura per ottenere un voucher valido per tutte le finalità associate ai client sopra citati.
Per maggiori informazioni: https://docs.pagopa.it/interoperabilita-1/
