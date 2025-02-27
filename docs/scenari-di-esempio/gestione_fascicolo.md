# Premessa

Di seguito la sequenza di operazioni da eseguire per accedere al FV dell'OE per la successiva verifica dei requisiti. <br>
Per il formato e l'obbligatorietà di tutti i campi dei servizi si rimanda al [file YAML](../specifiche-interfacce/specifiche-servizi-fvoe-fva.yaml)

## Richiesta di Accesso al Fascicolo dell'OE

La SA può richiedere l'accesso al fascicolo se non ha mai eseguito la richiesta o se questa é stata NEGATA o REVOCATA dall'OE o se é in stato SCADUTA.
Non vengono accettate più richieste di autorizzazione per uno stesso fascicolo già autorizzato o su cui é in attesa di risposta da parte dell'OE 

La richiesta di accesso se validata genera una notifica verso il FE dell'OE. 

### 1 Preparazione dati 
| ModelloDati | Modifica |
| ---------- | ---------- |
| RichiestaAccessoRequest | <ul><li> $RichiestaAccessoRequest.dataInizioAutorizzazione inserire obbligatoriamente la data inizio di validita dell'autorizzazione. il Valore deve essere maggiore o uguale alla data odierna</li> <li>$RichiestaAccessoRequest.dataFineAutorizzazione. Inserire facoltativamente la data fine di validità. In caso di mancata valorizzazione si assume una data fittizia 2099/12/31 indicante che la richiesta di accesso non ha scadenza</li> <li> $RichiestaAccessoRequest.operatoriEconomici.$AnagraficaOEType.codiceFiscale. Inserire obbligatoriamente almeno un CF dell'OE di cui si richiede l'accesso al Fascicolo. <br> Nella stessa richiesta é possibile richiedere l'accesso verso più OE per lo stesso appalto.<br> Il CF dell'OE inserito DEVE essere precedentemente inviato come Partecipante/Aggiudicatario in una delle seguenti schede: S1, S2, S2R, S4, RSU1, AD1_25, AD1_26, AD1_27, AD1_28, AD2_25, AD2_26, AD2_27, AD2_28, AD2_29, AD3, AD4 e AD5. Per i test possono essere utilizzati i codici fiscali 11111111113 e 11111111114.</li><li> $RichiestaAccessoRequest.idAppalto inserire obbligatoriamente l'idAppalto su cui si vuole eseguire la verifica della documentazione dell'OE</li></ul>|

### 2 Invocazione servizio 
#### Servizio:
../FVC/v2/richiesta-accesso-fvoe/
#### Payload:
```yaml
{
  "dataInizioAutorizzazione": "2024-06-05T12:02:05Z",
  "dataFineAutorizzazione": "2025-06-05T12:02:05Z",
  "operatoriEconomici": [
    {
      "codiceFiscale": "1111111113"
    },
    {
      "codiceFiscale": "80140110588"
    }
  ],
  "appalto": {
    "idAppalto": "4f8f5660-87e8-4dbb-b325-17e216f4a519"
  }
}
```
#### Response:
```yaml
{
  "status": 200,
  "title": "Operazione Effettuata",
  "detail": "Richiesta acquisita",
  "idRichiesta": "f81d4fae-7dec-11d0-a765-00a0c91e6bf6"
}
```
## Verifica Stato Richiesta di Accesso al Fascicolo dell'OE
L'autorizzazione può richiedere diversi giorni. Se entro un mese la richiesta non viene autorizzata/negata dall OE questa passa in stato 05 - SCADUTA. 
### 1 Preparazione dati 
| ModelloDati | Modifica |
| ---------- | ---------- |
| Parameters | <ul><li> $codiceFiscale  Inserire obbligatoriamente il CF dell'OE di cui si é richiesto l'accesso al Fascicolo</li> <li>$idAppalto.inserire obbligatoriamente l'idAppalto di cui si é eseguita la richiesta di accesso al fascicolo </li> </ul>|

### 2 Invocazione servizio 
#### Servizio:
../FVC/v2/verifica-richiesta-accesso-fvoe/
#### Payload:
```yaml
codiceFiscale : "1111111113"
idAppalto : "f81d4fae-7dec-11d0-a765-00a0c91e6bf6"
```
#### Response: Richiesta in Attesa di essere autorizzata
```yaml
{
  "status": 200,
  "title": "Operazione Effettuata",
  "autorizzazione": {
    "idAutorizzazione": "1789c793-bdbe-4e8c-aa7e-4117145c739b",
    "dataInizio": "2022-01-23T12:02:05Z",
    "dataFine": "2023-01-23T12:02:05Z",
    "operatoreEconomico": {
      "codiceFiscale": "1111111113"
    },
    "appalto": {
      "idAppalto": "4f8f5660-87e8-4dbb-b325-17e216f4a519"
    },
    "stato": {
      "codice": "01",
      "descrizione": {
        "it": "Richiesta"
      }
    },
    "richiestaAccesso": {
      "idRichiesta": "f81d4fae-7dec-11d0-a765-00a0c91e6bf6"
    },
  }
}
}
```

#### Response: Richiesta Autorizzata
```yaml
{
  "status": 200,
  "title": "Operazione Effettuata",
  "autorizzazione": {
    "idAutorizzazione": "1789c793-bdbe-4e8c-aa7e-4117145c739b",
    "dataInizio": "2022-01-23T12:02:05Z",
    "dataFine": "2023-01-23T12:02:05Z",
    "operatoreEconomico": {
      "codiceFiscale": "1111111113"
    },
    "appalto": {
      "idAppalto": "4f8f5660-87e8-4dbb-b325-17e216f4a519"
    },
    "stato": {
      "codice": "02",
      "descrizione": {
        "it": "Autorizzato"
      }
    },
    "motivo": "",
    "autorizzante": {
      "codiceFiscale": "4f8f5660-87e8-4dbb-b325-17e216f4a519"
    },
    "richiestaAccesso": {
      "idRichiesta": "f81d4fae-7dec-11d0-a765-00a0c91e6bf6"
    },
    "chiaveAccesso": "dafc5f6f-227c-4788-a523-72aa5244f649"
  }
}
}
```
## Recupero della lista dei documenti associati al FV dell'OE
Dopo aver ottenuto il codiceAccesso é possibile recuperare la lista con i dati di sintesi dei documenti presenti nel Fascicolo in modo ordinato e paginato. 

### 1 Preparazione dati 
| ModelloDati | Modifica |
| ---------- | ---------- |
| Parameters | <ul><li> $chiaveAccesso  Inserire obbligatoriamente la chiaveAccesso recuperata mediante il servizio di <b>verifica-accesso-richiesta-fvoe</b></li> </ul>|

### 2 Invocazione servizio 
#### Servizio:
../FVC/v2/ricerca-documenti-fvoe
#### Payload:
```yaml
chiaveAccesso : "dafc5f6f-227c-4788-a523-72aa5244f649"
```
#### Response: 
```yaml
{
  "status": 200,
  "title": "Operazione terminata correttamente",
  "totRows": 2,
  "totPages": 1,
  "currentPage": 1,
  "elementPage": 2,
  "result": [
    {
      "idDocumento": "a8add5d8-42f5-4c9c-9ca0-d0580a582e8b",
      "tipo": {
        "codice": "00001",
        "id": "tipoDocumento"
      },
      "stato": {
        "codice": "1",
        "id": "statoDocumento"
      },
      "oggetto": "Test",
      "dataInserimento": "2014-02-28T18:07:17Z",
      "fascicoli": [
                {
                    "tipoFascicolo": {
                        "codice": "FVC",
                        "id": "tipoFascicolo"
                    },
                    "idFascicolo": "dafc5f6f-227c-4788-a523-72aa5244f649",
                    "codiceFascicolo": "1111111113|4f8f5660-87e8-4dbb-b325-17e216f4a519"
                }
      ]
    },
    {
      "idDocumento": "b75b41c2-f7e3-4c2a-9309-4f8dd85ed6d1",
      "tipo": {
        "codice": "01",
        "id": "tipoDocumento"
      },
      "stato": {
        "codice": "1",
        "id": "statoDocumento"
      },
      "oggetto": "",
      "dataInserimento": "2014-02-28T18:07:17Z",
      "fascicoli": [
                {
                    "tipoFascicolo": {
                        "codice": "FVC",
                        "id": "tipoFascicolo"
                    },
                    "idFascicolo": "dafc5f6f-227c-4788-a523-72aa5244f649",
                    "codiceFascicolo": "1111111113|4f8f5660-87e8-4dbb-b325-17e216f4a519"
                }
      ]
    }
  ]
}
```
## Recupero del dettaglio documento associato al FV dell'OE
Mediante l'idDocumento recuperato dall'operazione precedente é possibile recuperate il documento nella sua interezza. Sia la parte dati e sia la parte binaria (facoltativa) .

### 1 Preparazione dati 
| ModelloDati | Modifica |
| ---------- | ---------- |
| Parameters | <ul><li> $idDocumento  Inserire obbligatoriamente l'idDocumento recuperato mediante il servizio di <b>ricerca-documenti-fvoe</b></li> </ul>|

### 2 Invocazione servizio 
#### Servizio:
../FVC/v2/recupera-documento-fvoe
#### Payload:
```yaml
idDocumento : "a8add5d8-42f5-4c9c-9ca0-d0580a582e8b"
```
#### Response: 
```yaml
{
  "status": 200,
  "title": "Operazione terminata correttamente",
  "documento": {
      "idDocumento": "a8add5d8-42f5-4c9c-9ca0-d0580a582e8b",
      "tipo": {
        "codice": "00001",
        "id": "tipoDocumento"
      },
      "stato": {
        "codice": "1",
        "id": "statoDocumento"
      },
      "oggetto": "Test",
      "dataInserimento": "2014-02-28T18:07:17Z",
      "dataEmissione": "2023-05-01T07:28:00Z",
      "dataFineValidita": "2024-02-29T08:28:00Z",
      "dataProtocollo": "2023-05-01T07:28:00Z",
      "numeroProtocollo": "3011202356",
      "dataCreazione": "2023-12-20T09:29:03.724Z",
      "utenteCreazione": "11111111114",
      "fascicoli": [
                {
                    "tipoFascicolo": {
                        "codice": "FVC",
                        "id": "tipoFascicolo"
                    },
                    "idFascicolo": "dafc5f6f-227c-4788-a523-72aa5244f649",
                    "codiceFascicolo": "1111111113|4f8f5660-87e8-4dbb-b325-17e216f4a519"
                }
      ]
  },
  "contenutoDocumento": {
      "nomefile": "esDoc00001.pdf",
      "estensione": "PDF",
      "contenuto": "JVBERi0xLjQKJcOkw7zDtsOfCjIgM3RhcnR4cmVmCjkxMzkxCiUlRU9GCg==",
      "dimensione": 93355
  }
}


```

