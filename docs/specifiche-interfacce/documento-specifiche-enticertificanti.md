
## Introduzione

Con la nuova operazione esposta /richiedi-documenti la SA potrà richiedere la documentazione verso gli enti certificanti.
In base alla tipologia del documento l'ente certificante potrebbe richiedere delle informazioni aggiuntive non presenti nell'anagrafica di ANAC.
Nel presente documento vengono riportati i tipi documento e il rispettivo modello dati che riporta tali informazioni aggiuntive che la SA deve popolare per una corretta elaborazione della richiesta.

## Tipi Documenti Richiedibili

Vengono riportati per ogni tipologia di documento richiedibile all'ente certificante il modello dati che arricchisce le informazioni, dove non presente, le informazioni implicitamente passate nella richiesta (Esempio Denominazione OE, Sede Legale, ecc) sono esaustive per l'eleborazione della richiesta per l'ente cerificante.

Tutti i modelli dati sono presenti nel file [modello-dati-fvoe-fva.yaml](https://github.com/anticorruzione/npa/tree/main/docs/modello-dati/modello-dati-fvoe-fva.yaml)


°Note: La lista verrà aggiornata in base alle nuove integrazioni 

| `Data Esercizio`  | `Codice Documento`  | `Descrizione Documento` | `Modello Dati` | `Ente Certificante` |
| :-------------: | :---------------: | :-------------------- | ----------------- | ----------------- | 
| `23/01/2024`    | `00033` | `Estratto del casellario informatico ANAC`  | `-` | `Anac` |
| `23/01/2024`    | `00004` | `Certificato integrale del casellario giudiziario`  | `DatiSA_00004` | `Min.Giustizia` |
| `23/01/2024`    | `00021` | `Comunicazione regolarità fiscale` | `-` | `Agenzia delle Entrate` |
| `23/01/2024`    | `00034` | `Visura al registo delle imprese`   | `-` | `Unioncamere` |
| `23/01/2024`    | `00005` | `Anagrafe delle sanzioni amministrative dipendenti da reato`  | `DatiSA_00020` | `Min. Giustizia` |
| `23/01/2024`    | `00038` | `DURC inarcassa professionista`  | `-` | `Inarcassa` |
| `23/01/2024`    | `00039` | `DURC inarcassa impresa`  | `-` | `Inarcassa` |
| `23/01/2024`    | `00035` | `Dati reddituali impresa individuale`  | `DatiSA_00036` | `Agenzia delle Entrate` |
| `23/01/2024`    | `00036` | `Consistenza media personale`  | `DatiSA_00047` | `Inps` |
| `23/01/2024`    | `00037` | `Consistenza complessivo personale`  | `DatiSA_00048` | `Inps` |
| `23/01/2024`    | `00001` | `Comunicazione antimafia`  | `DatiSA_00050` | `Min. Interno` |
| `23/01/2024`    | `00041` | `Dati reddituali società di persone` | `DatiSA_00036`| `Agenzia delle Entrate` |
| `23/01/2024`    | `00899` | `Documento Generico OE`  | `DatiSA_00899` | `Operatore Econimico` |
| `16/09/2024`    | `00006` | `Carichi Fiscali Pendenti` | `-` | `Agenzia delle Entrate` |
| `In Progress`   | `00007` | `Attestato WhiteList` | `-` | `Min. Interno` |
| `02/08/2024`    | `00008` | `DURC emesso in corso di validità` | `-` | `Inps` |
| `25/09/2024`    | `00010` | `Verifica esistenza prospetto informativo disabili` | `-` | `Ministero del Lavoro` |
| `25/09/2024`    | `00011` | `Verifica esistenza prospetto Rapporto situazione personale` | `-` | `Ministero del Lavoro` |
