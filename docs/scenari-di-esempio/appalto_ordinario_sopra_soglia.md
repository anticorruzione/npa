# Premessa

Di seguito la sequenza di operazioni da eseguire per ottenere l'aggiudicazione di un appalto nel settore ordinario sopra soglia scheda P1_16

## Pubblicazione procedura sopra soglia
Creazione e pubblicazione di una procedura sopra soglia con invio dell'avvisio di indizione al TED. <br>
Schede utilizzate: P1_16  

### 1 Preparazione dati 

| Sezione | Modifica |
| ---------- | ---------- |
| anacForm | <ul><li> modificare o aggiungere le informazioni identificative della Stazione appaltante in $.scheda.body.anacForm.stazioniAppaltanti <br> si può scegliere di modificare la SA presente (cf 11111111115) o aggiungere una nuova SA. Quella presente è la SA di test in uso presso ANAC </li> <li> modificare $.scheda.body.anacForm.appalto.codiceAppalto inserendo un valore univoco </li> </ul>|
|	eForm |<ul><li>	modifica notice-id inserendo un valore univoco </li> <li> modifica issueDate inserendo la data corrente </li> </ul> <br> per l'aggiornamento della eForm estrarre il campo eForm, effettuare la decodifica e modificare il documento XML. Il documento modificato deve essere codificato Base64 e inserito nel campo scheda.eForm della scheda |

### 2 Sequenza operazioni
#### 2.1 Creazione di un avviso di indizione
#### Servizio:
../ComunicaAppalto/v2/crea-appalto/
#### Payload:
[P1_16.json](./files/P1_16.json)
#### Response:
```yaml
{
    "status": 200,
    "title": "Operazione Effettuata",
    "detail": "Creazione eseguita con successo",
    "type": "about:blank",
    "idAppalto": "4f8f5660-87e8-4dbb-b325-17e216f4a519"
}
```
#### 2.2 Conferma di un avviso di indizione
 Ad esito positivo dell'operazione il sistema assegna i CIG ai lotti. 
#### Servizio:
../ComunicaAppalto/v2/conferma-appalto
#### Payload:
```yaml
{
    "idAppalto": "4f8f5660-87e8-4dbb-b325-17e216f4a519"
}
```
#### Response:
```yaml
{
    "status": 200,
    "title": "OK",
    "detail": "Richiesta acquisita",
    "type": "about:blank"
}
```
#### 2.3 Esito Operazione
 L'operazione di conferma è asincona e richiede un secondo accesso per ottere l'esito.
 Se la conferma va a buon fine esito-operazione consente di acquisire gli identificativi dell'avviso e della scheda per loro suo successivo uso nel payload dati 
#### Servizio:
../ServiziComuni/v2/esito-operazione?idAppalto=4f8f5660-87e8-4dbb-b325-17e216f4a519&tipoRicerca=ULTIMO_ESITO&tipoOperazione=AP_CONF
#### Payload:
non richiesto
#### Response:
```yaml
{
    "status": 200,
    "title": "OK",
    "detail": "Esecuzione avvenuta con successo",
    "type": "about:blank",
    "listaEsiti": [
        {
            "idAppalto": "4f8f5660-87e8-4dbb-b325-17e216f4a519",
            "idScheda": "989d89c5-29f1-4ce0-98e6-5171ace7e1a2",
            "idAvviso": "b4a5f333-64e6-4fba-8c48-eb3cf88e3cdd",
            "esito": {
                "idTipologica": "esito",
                "codice": "OK"
            },
            "tipoOperazione": {
                "idTipologica": "tipoOperazione",
                "codice": "AP_CONF"
            },
            "dataControllo": "2023-11-30T09:15:54.152+00:00",
            "dettaglio": {
                "idTipologica": "esitoOperazione",
                "codice": "AP_CONF"
            }
        }
    ]
}
```
#### 2.4 Recupero CIG assegnati ai lotti
 L'operazione consente di acquisire i codici CIG per il loro futuro uso nel payload dati 
#### Servizio:
../ComunicaAppalto/v2/recupera-cig?idAppalto=4f8f5660-87e8-4dbb-b325-17e216f4a519
#### Payload:
non richiesto
#### Response:
```yaml
{
    "status": 200,
    "title": "OK",
    "detail": "Operazione eseguita con successo",
    "type": "about:blank",
    "totRows": 2,
    "totPages": 1,
    "currentPage": 1,
    "elementPage": 20,
    "result": [
        {
            "cig": "K00003EC3A",
            "lotIdentifier": "LOT-0001"
        },
        {
            "cig": "L00003DC3A",
            "lotIdentifier": "LOT-0002"
        }
    ]
}
```
#### 2.5 Pubblica avviso
 Per richiedere la pubblicazione di una scheda di indizione è necessaria una chiamata esplicita al servizio pubblica avviso (in tutti gli altri casi il sistema pubblica automaticamente gli avvisi di pre e post informazione)
#### Servizio:
../PubblicaAvviso/v2/pubblica-avviso
#### Payload:
```yaml
{
    "idAppalto": "4f8f5660-87e8-4dbb-b325-17e216f4a519",
    "idAvviso": "b4a5f333-64e6-4fba-8c48-eb3cf88e3cdd"
}
```
#### Response:
```yaml
{
    "status": 200,
    "title": "OK",
    "detail": "Richiesta acquisita",
    "type": "about:blank"
}
```
#### 2.6 Stato avviso
 La pubblicazione dell'avviso può richiedere uno o più giorni e il processo attraversa diversi stati.
 La condizione attuale può essere consultata con il servizio stato avviso
#### Servizio:
../PubblicaAvviso/v2/stato-avviso?idAvviso=b4a5f333-64e6-4fba-8c48-eb3cf88e3cdd
#### Payload:
non richiesto
#### Response:
```yaml
{
    "status": 200,
    "title": "OK",
    "detail": "Operazione Effettuata",
    "type": "about:blank",
    "statoAvviso": {
        "idAvviso": "b4a5f333-64e6-4fba-8c48-eb3cf88e3cdd",
        "idAppalto": "4f8f5660-87e8-4dbb-b325-17e216f4a519",
        "idPianificazione": null,
        "dataControllo": "2023-11-30T09:20:22.830+00:00",
        "stato": {
            "idTipologica": "statoAvviso",
            "codice": "IN_ATT_PUBB"
        }
    }
}
```

#### 2.7 Consulta avviso
 Il servizio restituisce maggiori dettagli sull'avviso e le informazioni relative alla pubblicazione dal parte del sistema TED e del servizio Pubblicita a Valore Legale (PVL) di ANAC
#### Servizio:
../PubblicaAvviso/v2/consulta-avviso?idAvviso=b4a5f333-64e6-4fba-8c48-eb3cf88e3cdd
#### Payload:
non richiesto
#### Response:
```yaml
{
    "instance": null,
    "status": 200,
    "title": "OK",
    "detail": "Operazione Effettuata",
    "type": "about:blank",
    "avviso": {
        "idAvviso": "b4a5f333-64e6-4fba-8c48-eb3cf88e3cdd",
        "idAppalto": "4f8f5660-87e8-4dbb-b325-17e216f4a519",
        "idPianificazione": null,
        "dataCreazione": "2023-11-30T09:15:50.204+00:00",
        "dataPubblicazione": null,
        "stato": {
            "idTipologica": "statoAvviso",
            "codice": "IN_ATT_PUBB"
        },
        "dataControllo": "2023-11-30T09:20:22.830+00:00",
        "azione": {
            "idTipologica": "tipoAzioneAvviso",
            "codice": "AZ_PUBB"
        },
        "datiPubblicazioneEU": {
            "noticeId": "048e8090-e8f5-4f71-a282-76fc4236c98a",
            "versionId": "01",
            "tipo": {
                "idTipologica": "tipoAvviso",
                "codice": "EU"
            },
            "stato": {
                "idTipologica": "statoAvviso",
                "codice": "IN_ATT_PUBB"
            },
            "dataControllo": "2023-11-30T09:20:22.830+00:00",
            "dataInoltroPubblicazione": "2023-11-30T09:20:24.619+00:00",
            "dataRicezionePubblicazione": null,
            "dataPubblicazione": null
        },
        "datiPubblicazioneIT": {
            "tipo": {
                "idTipologica": "tipoAvviso",
                "codice": "IT"
            },
            "stato": null,
            "dataControllo": null,
            "dataInoltroPubblicazione": null,
            "dataPubblicazione": null
        },
        "scheda": {...omessa...},
        "appalto": {
            "idAppalto": "4f8f5660-87e8-4dbb-b325-17e216f4a519",
            "codiceAppalto": "TEST_P1_16.0",
            "oggetto": "Provision of IT services related to the information systems of the publications office (namely EUR-Lex, N-Lex, and Search Layer),\n\t\t\twith the possibility to extend the provision to other information systems.",
            "dataCreazione": "2023-11-30T09:14:31.209+00:00",
            "dataModifica": "2023-11-30T09:20:22.831+00:00",
            "stato": {
                "idTipologica": "statoAppalto",
                "codice": "IN_ATT_PUBB"
            }
        },
        "piano": null
    }
}
```

## Acquisizione partecipanti e aggiudicazione
Creazione e pubblicazione di una procedura sopra soglia con invio dell'avvisio di indizione al TED.
Schede utilizzate: S2, A1_29 

### 1 Preparazione dati 
#### 1.1 Scheda S2 elenco partecipanti
| Sezione | Modifica |
| ---------- | ---------- |
| anacForm | <ul><li> modificare i codici CIG inserendo quelli ottenuti per la procedura corrente con il servizio recupera CIG </li> <li> modificare idAppalto inserendo quello della procedura in corso </li></ul>|
|	eForm | non prevista |

#### 1.2 Scheda A1_29 elenco partecipanti
| Sezione | Modifica |
| ---------- | ---------- |
| anacForm | <ul><li> modificare i codici CIG inserendo quelli ottenuti per la procedura corrente con il servizio recupera CIG </li> </ul>|
|	eForm |<ul><li>	modifica notice-id inserendo un valore univoco </li> <li> modifica issueDate inserendo la data corrente </li> </ul> <br> per l'aggiornamento della eForm vedi file eForm29.xml. Il file modificato deve essere codificato Base64 e inserito nel campo scheda.eForm della scheda |

### 2 Sequenza operazioni
#### 2.1 Creazione di una scheda S2
#### Servizio:
../ComunicaPostPubblicazione/v2/crea-scheda
#### Payload:
[S2.json](./files/S2.json)
#### Response:
```yaml
{
    "status": 200,
    "title": "Operazione Effettuata",
    "detail": "Creazione eseguita con successo",
    "type": "about:blank",
    "idScheda": "7f234d6b-6fba-4384-9c06-3a22e643ca8c"
}
```

#### 2.2 Conferma della scheda S2
 
#### Servizio:
../ComunicaPostPubblicazione/v2/conferma-scheda
#### Payload:
```yaml
{
 "idScheda": "7f234d6b-6fba-4384-9c06-3a22e643ca8c",
  "idAppalto": "4f8f5660-87e8-4dbb-b325-17e216f4a519"
}
```
#### Response:
```yaml
{
    "status": 200,
    "title": "OK",
    "detail": "Richiesta acquisita",
    "type": "about:blank"
}
```
#### 2.3 Creazione di una scheda A1_29
#### Servizio:
../ComunicaPostPubblicazione/v2/crea-scheda
#### Payload:
[A1_29.json](./files/A1_29.json)
#### Response:
```yaml
{
    "status": 200,
    "title": "Operazione Effettuata",
    "detail": "Creazione eseguita con successo",
    "type": "about:blank",
    "idScheda": "90c54b91-1306-46c6-a96b-3c282195736c"
}
```

#### 2.4 Conferma della scheda A1_29
 
#### Servizio:
../ComunicaPostPubblicazione/v2/conferma-scheda
#### Payload:
```yaml
{
 "idScheda": "90c54b91-1306-46c6-a96b-3c282195736c",
  "idAppalto": "4f8f5660-87e8-4dbb-b325-17e216f4a519"
}
```
#### Response:
```yaml
{
    "status": 200,
    "title": "OK",
    "detail": "Richiesta acquisita",
    "type": "about:blank"
}
```
