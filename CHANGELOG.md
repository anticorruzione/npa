<details>
<summary><h1>Note di rilascio del 22/09/2023</h1></summary>

## Modello Dati
* modello-dati-tipologiche.yaml:
  * creato un nuovo oggetto TipologicaSchemaErroriType
  * modificato l'attributo $ref dell'oggetto ErroriEnum per estendere il nuovo schema dati ($ref: '#/components/schemas/TipologicaSchemaErroriType')
* modello-dati-npa.yaml:
  * aggiunta nuova scheda SQ1
  * aggiunti gli attributi idNuovaScheda e idNuovoAvviso in EsitoOperazioneType
      
### Regole
* A1_29.dmn, A1_30.dmn, A1_31.dmn, A1_32.dmn, A1_33.dmn, A1_34.dmn, A1_35.dmn, A1_36.dmn, A1_37.dmn, A2_29.dmn, A2_30.dmn, A2_31.dmn, A2_32.dmn, A2_33.dmn, A2_34.dmn, A2_35.dmn, A2_36.dmn, A2_37.dmn, A3_1.dmn, A3_2.dmn, A3_3.dmn, A3_4.dmn, A3_5.dmn, A3_6.dmn,M1_38.dmn, M1_39.dmn, M1_40.dmn, M2_38.dmn, M2_39.dmn, M2_40.dmn:
  * aggiunte nuove regole
* AD1_25.dmn, AD1_26.dmn, AD1_27.dmn, AD1_28.dmn, AD2_25.dmn, AD2_26.dmn, AD2_27.dmn, AD2_28.dmn, AD3.dmn, P1_10.dmn, P1_11.dmn, P1_12.dmn, P1_13.dmn, P1_16.dmn, P1_17.dmn, P1_20.dmn, P1_21.dmn, P2_10.dmn, P2_11.dmn, P2_12.dmn, P2_13.dmn, P2_16.dmn, P2_17.dmn, P2_20.dmn, P2_21.dmn, P3_4.dmn:
  * regola REG7 corretto il messaggio con art. 140 co. 10 D. Lgs. 36/2023
    
### Schede
* modello-dati-schede-dati-comuni.yaml:
  * modificato l'oggetto StazioneAppaltanteType rendendo tutti i campi obbligatori tranne funzioniSvolte
  * modificato l'oggetto AggiudicazioneA1_31Type rendendo il cig obbligatorio
  * modificato l'oggetto ModificaContrattualeType togliendo lotIdentifier
  * modificato l'oggetto ModificaContrattuale_40Type togliendo lotIdentifier
  * modificato l'oggetto AggiudicazioneA7Type togliendo il lotIdentifier e inserendo il cig obbligatorio
  * modificato l'oggetto AppaltoA7Type togliendo l'idAppalto
  * aggiunto all'oggetto AppaltoP4BaseType il campo boolean costituzioneSocietaDiScopo obbligatorio
  * modificato il format datetime in date-time su tutti gli oggetti
  * modificato l'oggetto DatiTerminiInvioType: oraScadenzaPresentazioneOfferte diventa date-time
  * modificato l'oggetto DatiBaseTerminiInvioSoloOraType: oraScadenzaPresentazioneOfferte diventa date-time
  * eliminati gli oggetti MisurePremialiType, MotivoDerogaType, LingueType, TipologiaLavoroType, CondizioniNegoziataType
  * modificato l'oggetto ParitaDiGenereGenerazionaleType: l'attributo misurePremiali diventa array di MisurePremialiEnum e motivoDeroga diventa array di MotivoDerogaEnum
  * modificato l'oggetto DatiBaseDocumentiType: l'attributo lingue diventa array di LingueEnum
  * modificati gli oggetti LottoP_10Type, LottoP_11Type, LottoP_15Type,	LottoP_16Type, LottoP_17Type, LottoP_19Type,  LottoP3BaseType, LottoP6BaseType, LottoP4BaseType,LottoP7BaseType: l'attributo tipologiaLavoro diventa array di TipologiaLavoroEnum
  * modificati gli oggetti LottoBaseType, LottoP4BaseType, LottoP7BaseType: l'attributo condizioniNegoziata diventa array di CondizioniNegoziataEnum
  * modificato l'oggetto DatiBaseAccessibilitaType: il campo accessibilita non è più array, secondo quanto indicato nel ted con la sdk 1.8.0
  * modificati gli oggetti PrestazioniEnum, TipoRealizzazioneContrattoEnum, FunzioniDelegateEnum, GiustificazioneAggiudicazioneDirettaEnum, EsitoProceduraEnum, GiustificazioneEsitoProceduraEnum, MotiviModificaContrattualeEnum, MotiviVariazioneAnagraficaEnum, MotiviInterruzioneEnum, TipologiaComunicazioneEnum: rinominato il riferimento al json
  * modificati gli oggetti InvitatoType, DatiPersonaGiuridicaType, AggiudicatarioType, AggiudicatarioA1_35Type, PartecipanteType, PartecipanteADType, SoggettoType: rinominato l'attributo tipo in tipoOE
  * modificato l'oggetto PrestazioneType: rinominato l'attributo tipo in tipoSoggetto
  * modificato l'oggetto FinanziamentoType: rinominato l'attributo tipo in tipoFinanziamento	 
* modello-dati-schede-P3.5.yaml:
  * l'attributo condizioniNegoziata diventa array di CondizioniNegoziataEnum
* modello-dati-schede-A2.31.yaml, modello-dati-schede-A3.5.yaml, modello-dati-schede-A3.6.yaml:
  * reso il cig obbligatorio
* modello-dati-schede-A3.3.yaml:
  * modificato il format datetime in date-time
* modello-dati-schede-AD3.yaml:
  * reso il lotidentifier obbligatorio
* modello-dati-schede-AD4.yaml:
  * reso il lotidentifier obbligatorio
  * modificato il format datetime in date-time
* modello-dati-schede-CL1.yaml:
  * tolto l'idcontratto dall'oggetto CollaudoType e inserito nell'anacForm
  * modificato il format datetime in date-time
* modello-dati-schede-CO1.yaml, modello-dati-schede-CO2.yaml:
  * tolto l'idcontratto dall'oggetto ConclusioneType e inserito nell'anacForm
  * modificato il format datetime in date-time
* modello-dati-schede-I1.yaml:
  * tolto l'idcontratto dall'oggetto DatiInizioType e inserito nell'anacForm
  * modificato il format datetime in date-time
* modello-dati-schede-NAG.yaml:
  * reso obbligatorio il cig e i lotti
* modello-dati-schede-SC1.yaml:
  * tolto l'idcontratto dall'oggetto DatiContrattoType
  * modificato il format datetime in date-time
* modello-dati-schede-RI1.yaml:
  * aggiunto l'attributo incidenzaCronoprogramma
  * eliminato l'array sospensioni e inserito l'elemento sospensione.
  * tolto l'idcontratto dall'oggetto sospensioneType. inserito l'idscheda nell'anacForm
  * modificato il format datetime in date-time
* modello-dati-schede-SQ1.yaml:
  * aggiunta nuova scheda di superamento del quarto del tempo contrattuale
* modello-dati-schede-AC1.yaml:
  * eliminato l'array accordiBonari e inserito l'elemento accordoBonario.
  * tolto l'idcontratto dall'oggetto AccordoBonarioType e inserito nell'anacForm
  * modificato il format datetime in date-time
* modello-dati-schede-IR1.yaml:
  * eliminato l'array ritardi e inserito l'elemento ritardo.
  * tolto l'idcontratto dall'oggetto RitardoType e inserito nell'anacForm
  * modificato il format datetime in date-time
* modello-dati-schede-S2.yaml:
  * modificato il format datetime in date-time
* modello-dati-schede-RSU1.yaml:
  * eliminato l'array subappalti e inserito l'elemento subappalto.
  * tolto l'idcontratto dall'oggetto subappaltotype e inserito nell'anacForm
* modello-dati-schede-CS1.yaml:
  * eliminato l'array subappalti e inserito l'elemento subappalto.
  * tolto l'idcontratto dall'oggetto subappaltotype e inserito nell'anacForm
  * modificato il format datetime in date-time
* modello-dati-schede-ES1.yaml:
  * eliminato l'array subappalti e inserito l'elemento subappalto.
  * tolto l'idcontratto dall'oggetto subappaltotype. aggiunto l'idScheda nell'anacForm
  * modificato il format datetime in date-time
* modello-dati-schede-S3.yaml, modello-dati-schede-S4.yaml:
  * tolto lotidentifier. reso il cig obbligatorio
* modello-dati-schede-SA1.yaml:
  * eliminato l'array avanzamenti e inserito l'elemento avanzamento.
  * tolto l'idcontratto dall'oggetto avanzamentotype e inserito nell'anacForm
  * modificato il format datetime in date-time
* modello-dati-schede-SO1.yaml:
  * eliminato l'array sospensioni e inserito l'elemento sospensione.
  * tolto l'idcontratto dall'oggetto sospensioneType e inserito nell'anacForm
  * modificato il format datetime in date-time
* modello-dati-schede-SU1.yaml:
  * eliminato l'array sospensioni e inserito l'elemento sospensione.
  * tolto l'idcontratto dall'oggetto sospensioneType e inserito nell'anacForm 
* modello-dati-schede-P3.3.yaml:	
  * modificata label cigAccordoQuadro in cigAccordoQuadroConvenzione
* modello-dati-schede-P6.3.yaml, modello-dati-schede-P6.4.yaml, modello-dati-schede-P6.5.yaml, modello-dati-schede-P6.6.yaml:
  * file eliminati
  
### Tipologiche
* errori.json:
  * corretto con art. 140 co. 10 D. Lgs. 36/2023
  * inserito nuovo messaggio di errore REG77
  * inserito nuovo messaggio di errore ERR63
  * inserito nuovo messaggio di errore ERR64
  * modificato messaggio dell'errore ERR46
  * inserito nuovo messaggio di errore FVX30 
* codiceScheda.json: 
  * aggiunta la nuova scheda SQ1.
  * modificato codice C01 e C02 in CO1 e CO2
* lingue.json, statoScheda.json, statoAvviso.json, esitoOperazione.json, codNUTS.json, codIstat.json:
  * aggiornati i valori delle tipologiche  
* prestazioni.json:
  * rinominata in prestazioniComprese.json
* tipoRealizzazioneContratto.json:
  * rinominata in tipoRealizzazione.json
* funzioniDelegate.json:
  * rinominata in funzioniSvolte.json
* giustificazioneAggiudicazioneDiretta.json:
  * rinominata in giustificazioniAggiudicazioneDiretta.json
* esitoProcedura.json:
  * rinominata in esito.json
* giustificazioneEsitoProcedura.json:
  * rinominata in giustificazione.json
* motiviModificaContrattuale.json:
  * rinominata in motiviModifica.json
* motiviVariazioneAnagrafica.json:
  * rinominata in motivoVariazione.json
* motiviInterruzione.json:
  * rinominata in causaInterruzioneAnticipata.json
* tipologiaComunicazione.json:
  * rinominata in tipoComunicazione.json      
* cancellate le seguenti tipologiche perché rinominate o non utilizzate:
  * prestazioni.json
  * tipoRealizzazioneContratto.json
  * funzioniDelegate.json
  * giustificazioneAggiudicazioneDiretta.json
  * esitoProcedura.json
  * giustificazioneEsitoProcedura.json
  * motiviModificaContrattuale.json
  * motiviVariazioneAnagrafica.json
  * motiviInterruzione.json
  * erroriEform.json
  * tipologiaComunicazione.json
* tipoContenuto.json: 
  * nuova tipologica ad uso interno

## Orchestratore

## Specifiche Interfacce

## Documentazione
* Nella sezione Standard adottati del file README.md è stata aggiornata la versione sdk dell'eForms da adottare (1.8.0).
</details>

<details>
<summary><h1>Note di rilascio del 25/09/2023</h1></summary>

## JWS token 
ref. /docs/specifiche-jws/

* jws.yaml:
  * creato un nuovo file con le specifiche openAPI 3 del modello dati dell'oggetto body del token
* roadmap.md:
  * creato un nuovo file con la roadmap prevista per l'attivazione dei controlli di correttezza formale e sostanziale del JWS token 
</details>

<details>
<summary><h1>Note di rilascio del 09/10/2023</h1></summary>

## Modello Dati 

### Regole
* A3_1.dmn, A2_30.dmn, A2_33.dmn, A2_34.dmn,A3_2.dmn,A3_3.dmn,A3_4.dmn,A3_5.dmn,A3_6.dmn,A1_34.dmn,A1_33.dmn,A1_30.dmn,A1_32.dmn, A2_32.dmn,A1_35.dmn,A2_35.dmn, A2_29.dmn, A1_29.dmn: aggiornate regole

### Schede
* modello-dati-schede-P*.yaml, modello-dati-schede-PL*.yaml, modello-dati-schede-AD*.yaml, modello-dati-schede-A*.yaml, modello-dati-schede-M*.yaml, modello-dati-schede-SA1.yaml, modello-dati-schede-RSU1.yaml, modello-dati-schede-ES1.yaml, modello-dati-schede-CS1.yaml, modello-dati-schede-SO1.yaml, modello-dati-schede-SQ1.yaml, modello-dati-schede-RI1.yaml, modello-dati-schede-AC1.yaml, modello-dati-schede-CL1.yaml:
  * modificata la descrizione della scheda

* modello-dati-schede-dati-comuni.yaml:
  * eliminato l'oggetto DatiBaseAggiudicazioneSubappaltoType
  * modificato l'oggetto AggiudicazioneA4Type: rinominata la property datibaseSubappalti in datiBaseSubappalti
  * modificato l'oggetto AppaltoBaseType rendendo obbligatorio il campo categorieMerceologiche.
  * Rimosso il required del campo categorieMerceologiche dagli oggetti AppaltoP_10Type, AppaltoP_11Type, AppaltoP_12Type, AppaltoP_13Type, AppaltoP_14Type, AppaltoP_16Type, AppaltoP_17Type, AppaltoP_19Type, AppaltoP_20Type, AppaltoP_21Type. 
  * modificato l'oggetto LottoBaseType:
  	* resi obbligatori i campi categorieMerceologiche, afferenteInvestimentiPNRR, contrattiDisposizioniParticolari.
  	* eliminato il campo modalitaAcquisizione.
  * modificati gli oggetti LottoP_10Type, LottoP_11Type, LottoP_12Type, LottoP_13Type, LottoP_14Type, LottoP_16Type, LottoP_17Type, LottoP_19Type, LottoP_20Type, LottoP_21Type:
  	* rimosso il required dei campi categorieMerceologiche, afferenteInvestimentiPNRR, contrattiDisposizioniParticolari
  	* aggiunto il campo modalitaAcquisizione
  * modificato l'oggetto DatiBaseProceduraType rendendo obbligatorio il campo tipoProcedura
  * aggiunto l'oggetto DatiBaseProceduraOptionalType che non prevede il campo tipoProcedura obbligatorio
  * modificato l'oggetto AppaltoPLCompletoType cambiando la reference da DatiBaseProceduraType a DatiBaseProceduraOptionalType
  * modificato l'oggetto AppaltoP4BaseType: modificata la property datiBaseProcedura togliendo il required perché inserito nell'oggetto DatiBaseProceduraType referenziato 
  * modificato l'oggetto AppaltoP7BaseType: modificata la property datiBaseProcedura togliendo il required perché inserito nell'oggetto DatiBaseProceduraType referenziato 
  * modificato l'oggetto DatiBaseDocumentiType rendendo required la url
  * modificati gli oggetti LottoP6BaseType e LottoP7BaseType: cambiata la reference del campo datiBaseDocumenti da DatiBaseDocumentiType a DatiBaseDocumentiOptionalType
  * modificati gli oggetti LottoPLBase,LottoPLCompletoType,LottoP4BaseType: aggiunto il campo datiBaseDocumenti
  * modificati gli oggetti DatiBaseAppaltoType,DatiBaseLottoType: aggiunto il required sull'importo
  * aggiunti gli oggetti DatiBaseDocumentiOptionalType, DatiBaseAppaltoOptionalType,DatiBaseLottoOptionalType,DatiBaseAggiudicazioneOptionalType,LottoP7_2BaseType,DatiBaseLottoP7_3Type,DatiBaseCPVP7Type,DatiBaseCPVPLType,DatiBaseContrattoP7Type,DatiBaseProceduraADType, DatiBaseStrumentiProceduraAType, DatiBaseSubappaltiRequiredType
  * modificati gli oggetti AppaltoP6BaseType,LottoP6BaseType: tolta la property datibase    
  * LottoP3BaseType eliminati i campi afferenteInvestimentiPNRR, categoria.
  * DatiBaseAggiudicazioneType: aggiunto il required
  * modificato l'oggetto AppaltoAType: eliminato il campo relazioneUnicaSulleProcedure
  * modificati gli oggetti AppaltoA1_29Type, AppaltoA1_30Type, AppaltoA1_33Type, AppaltoA1_34Type : aggiunto il campo relazioneUnicaSulleProcedure
  * modificati gli oggetti AggiudicazioneCompletaType e AggiudicazioneBaseType: eliminato il campo numeroOfferteAmmesse
  * modificati gli oggetti AggiudicazioneA1_29Type, AggiudicazioneA1_30Type, AggiudicazioneA1_32Type, AggiudicazioneA1_33Type, AggiudicazioneA1_34Type, AggiudicazioneA1_35Type, AggiudicazioneA1_36Type, AggiudicazioneA1_37Type, AggiudicazioneA4Type: aggiunto il campo numeroOfferteAmmesse
  * modificati gli oggetti ModificaContrattualeType,ModificaContrattuale_40Type: tolta la property idcontratto

* modello-dati-schede-A2.32.yaml, modello-dati-schede-A2.33.yaml, modello-dati-schede-A2.34.yaml, modello-dati-schede-A2.35.yaml:
  * modificata la property datiBaseAggiudicazioneSubappalto: sostituito il puntamento all'oggetto DatiBaseAggiudicazioneSubappaltoType con DatiBaseSubappaltiType
  * rinominata la property datibaseSubappalti in datiBaseSubappalti

* modello-dati-schede-A2.29.yaml, modello-dati-schede-A2.30.yaml, modello-dati-schede-A2.31.yaml, modello-dati-schede-A7.1.2.yaml, modello-dati-schede-A3.1.yaml, modello-dati-schede-A3.2.yaml, modello-dati-schede-A3.3.yaml, modello-dati-schede-A3.4.yaml, modello-dati-schede-A3.5.yaml:
	* rinominata la property datiBaseAggiudicazioneSubappalto in datiBaseSubappalti

* modello-dati-schede-PL2.7.yaml,modello-dati-schede-PL2.8.yaml,modello-dati-schede-PL2.9.yaml:
	* eliminati i required dei campi accordoQuadro, sistemaDinamicoAcquisizione dalla property datiBaseStrumentiProcedura

* modello-dati-schede-A2.37.yaml,modello-dati-schede-A2.36.yaml:
	* modificata la property datiBaseProcedura tolto il required perché inserito nell'oggetto DatiBaseProceduraType referenziato

* modello-dati-schede-P3.5.yaml,modello-dati-schede-P3.4.yaml,modello-dati-schede-P3.3.yaml,modello-dati-schede-P3.2.yaml,modello-dati-schede-P3.1.yaml: 
	* modificato l'oggetto lotti: 
	 * cambiata la reference di datiBaseDocumenti da DatiBaseDocumentiType a DatiBaseDocumentiOptionalType
	 * aggiunti i campi afferenteInvestimentiPNRR, categoria
	 * aggiornata la reference di datiBase
	 * eliminati i required da datiBase e DatiBaseAggiudicazioneType perché già presenti nell'oggetto referenziato

* modello-dati-schede-P2.24.yaml,modello-dati-schede-P2.23.yaml,modello-dati-schede-P2.21.yaml,modello-dati-schede-P2.20.yaml,modello-dati-schede-P2.19.yaml,modello-dati-schede-P2.14.yaml,modello-dati-schede-P2.13.yaml,modello-dati-schede-P2.12.yaml,modello-dati-schede-P2.11.yaml,modello-dati-schede-P2.10.yaml:
	* modificato l'oggetto appalto: modificate le property datiBaseProcedura e datiBase: tolto il required perché inserito inserito negli oggetti referenziati
	* modificato l'oggetto lotti eliminando il required perché già presente nell'oggetto DatiBaseDocumentiType referenziato 

* modello-dati-schede-P2.12.yaml:
	* resa array la property lotti 

* modello-dati-schede-P2.18.yaml,modello-dati-schede-P2.17.yaml,modello-dati-schede-P2.16.yaml:
	* aggiunto l'oggetto DatiBaseStrumentiProceduraType con i required richiesti
	* modificato l'oggetto appalto:		
		modificata la property datiBaseStrumentiProcedura referenziando il nuovo oggetto DatiBaseStrumentiProceduraType
		modificata la property datiBase aggiornando la reference all'oggetto DatiBaseAppaltoOptionalType
	* modificato l'oggetto lotti:
		modificato l'oggetto lotto eliminando il required perché già presente nell'oggetto DatiBaseDocumentiType referenziato
		modificata la property datiBase aggiornando la reference all'oggetto DatiBaseLottoOptionalType

* modello-dati-schede-P6.1.yaml:
	* inseriti gli oggetti AppaltoP6_1Type, LottoP6_1Type 
	* modello-dati-schede-P6.2.yaml:
	* inserita la property datiBase negli oggetti AppaltoP6_2Type eLottoP6_2Type con i required opportuni

* modello-dati-schede-P7.2.yaml:
	* modificata la reference dell'oggetto LottoP7_2Type
	* aggiunto l'oggetto QuadroEconomicoType

* modello-dati-schede-P7.3.yaml: 
	* modificata la reference all'oggetto datiBase e datiBaseDocumenti

* modello-dati-schede-AD2_25.yaml, modello-dati-schede-AD2_26.yaml, modello-dati-schede-AD2_27.yaml, modello-dati-schede-AD2_28.yaml:
	* modificata la reference dell'oggetto datiBaseProcedura

* modello-dati-schede-A2_29.yaml,modello-dati-schede-A2_30.yaml,modello-dati-schede-A2_31.yaml,modello-dati-schede-A3_4.yaml:
	* cambiata la reference degli oggetti datiBaseStrumentiProcedura e datiBaseSubappalti

* modello-dati-schede-A7_1_2.yaml:
	* cambiata la reference della property datibaseprocedura

* modello-dati-schede-NAG.yaml:
	* tolto il required dalla property datiBaseRisultatoProcedura

* modello-dati-schede-M1.yaml,modello-dati-schede-M1.40.yaml,modello-dati-schede-M2.yaml,modello-dati-schede-M2.40.yaml:
	* modificato l'array delle modifiche contrattuali in property singola.
	* spostato l'idcontratto dalla property modifica all'anac form.
   
### Tipologiche
* subappalto.json:
  * modificati i valori secondo la codelist Applicability del TED
* errori.json
  * aggiornate descrizioni
  * inserito nuovo messaggio di errore ERR65
  * inserito nuovo messaggio di errore ERR66
    
</details>

<details>
<summary><h1> Note di rilascio del 13/11/2023</h1></summary>

## Modello Dati 
* modello-dati-fvoe-fva.yaml:
  * modificato tipoDato idRichiesta di RichiediDocumentoResponse
  * aggiunto attributo personaGiuridica in AnagraficaOEType utilizzato dall'operazione /recupera-anagrafica-oe
* modello-dati-npa.yaml:
  * aggiunto il type string per l'attributo lotIdentifier in LottoType
  * aggiunto ProfiloSAType utilizzato dall'operazione /recupera-profilo
  * aggiungo l'attributo idPianificazione all'oggetto EsitoOperazioneType
  * aggiunto l'attributo tipo all'oggetto DatiPianoBaseType
  * aggiunto l'attributo idPianificazione all'oggetto StatoAvvisoType
  * AvvisoBaseType estende il nuovo oggetto AvvisoCommonType e aggiunge gli attributi idAppalto e idPianificazione
  * AvvisoType estende il nuovo oggetto AvvisoCommonType e aggiunge l'attributo piano
  * spostata la scheda P7_3 nelle schede di pianificazione
* modello-dati-persona-giuridica.yaml:
  * nuovo file che riporta il modello dati della persona giuridica restituita dall'operazione /recupera-anagrafica-oe    
    
### Regole
* P*.dmn, A*.dmn:
	* revisionate le regole 

### Schede
* modello-dati-schede-AC1.yaml:
	* modificata descrizione scheda
* modello-dati-schede-CS1.yaml:
	* cambiato idcontratto con idscheda di esito subappalto
 	* aggiunto nuovo campo motivoMancataEsecuzioneSubappalto
* modello-dati-schede-CO1.yaml:
	* modificato l'oggetto ConclusioneType aggiungendo i campi motiviRisoluzione, dataStipula, dataEsecutivita.
* modello-dati-schede-dati-comuni.yaml:
	* modificato l'oggetto AggiudicazioneA4Type: corretta la label datiBaseAggiudicazioneAppalto
 	* ove presente sia idGruppo sia idPartecipante eliminato idGruppo in quanto sarà usato solo l’idPartecipante
  	* aggiornato il riferimento alla tipologica motivazioneCIG.json
  	* reso obbligatorio partecipanti negli oggetti usati dalle schede di affidamento diretto
  	* aggiornato l'oggetto DefinizioneType utilizzato nella scheda di collaudo CL1
  	* aggiunto l'enum MotivoMancataEsecuzioneSubappaltoEnum utilizzato nella scheda di conclusione subappalto CS1
  	* riscritti gli enum in upper case
* modello-dati-schede-S1.yaml:
	* aggiunto l'oggetto anacForm.elencoSoggettiRichiedenti[] che ingloba l’attuale modello dati definito
 	* rinominato idGruppo dentro soggettiInteressati in idPartecipante
* modello-dati-schede-S2.yaml:
	* idPartecipante: da tipo string diventa tipo uuid
 	* aggiunto l'oggetto anacForm.elencoSoggetti[] che ingloba l’attuale modello dati definito
 * modello-dati-schede-S3.yaml:
	* aggiunto l'oggetto anacForm.elencoIncarichi[] che ingloba l’attuale modello dati definito
	* modificato l’oggetto datiPersonaGiuridica dentro incarichi[] in un array datiPersonaGiuridica[]
 	* modificato l’oggetto datiPersonaGiuridica dentro prestazioni[] in un array datiPersonaGiuridica[]
 * modello-dati-schede-A3_6.yaml, modello-dati-schede-AD*.yaml:
 	* aggiunto l'oggetto stazioniAppaltanti
  	* modificato l'oggetto offertePresentate in partecipanti
   	* modificato l'oggetto aggiudicatario in partecipanti
* modello-dati-schede-P2*.yaml:
	* eliminata la doppia reference agli oggetti AppaltoBaseType e LottoBaseType
* modello-dati-schede-A*.yaml:
	*  reso idPartecipante obbligatorio
 	*  reso offertePresentate obbligatorio
* modello-dati-schede-P*.yaml:
	* modificato il nome dell'attributo idSchedaPreinformazione in idPianificazione
* modello-dati-schede-RSU1.yaml:
	* aggiunto il campo codiceFiscaleDittaACascata
 	* reso il campo cpv array
* modello-dati-schede-SC1.yaml:
	* modificato il tipo del campo importoCauzione in number, double.
* modello-dati-schede-CL1.yaml:
	* riscritto enum in upper case.
* modello-dati-schede-AD4.yaml:
	* aggiornata reference verso PartecipanteADType 
### Tipologiche
* errori.json
  * aggiunti i seguenti messaggi di errore: ERR67, ERR68, ERR69, ERR70, ERR71, ERR72, ERR73, ERR74, ERR75, ERR76, ERR77, ERR78, ERR79, ERR80, ERR81, ERR82, ERR83, ERR84, ERR85, ERR86, ERR87, ERR88, ERR89, ERR90, ERR91, ERR92, SEC14, SEC15, FVX31, FVX32, FVX33, FVX34, REG78
* tipoRuolo.json
  * aggiunti i nuovi valori DRP1, DRP2, DRP3 ed eliminato DRP
* statoContratto.json
  * aggiornati i valori della tipologica
* tipoPiano.json
  * aggiornati i valori della tipologica
* tipoIncarico.json:
  * eliminati i codici 9,11, 12, 14, 15, 16, 17 e 19
* statoComprova.json
  * nuova tipologica ad uso interno
* statoUtilizzo.json
  * nuova tipologica ad uso interno
* motivazioneCig.json: rinominata in motivazioneCIG.json
* motivoMancataEsecuzioneSubappalto.json
	* nuova tipologica utilizzata nella scheda di conclusione di una richiesta di subappalto   

## Orchestratore
* Aggiornato il file schema-cronologia-schede.xlsx
  
## Specifiche Interfacce
* specifiche-servizi-appalto.yaml:
  * inserita operazione /recupera-profilo
  * per l'operation /esito-operazione aggiunto in input idPianificazione
  * per le operation /modifica-avviso, /rettifica-avviso, /cancella-avviso, /ricerca-avviso aggiunto in input idPianificazione
* documento-specifiche-servizi-npa.md
  * aggiornamento dei ruoli nei paragrafi 4.4 Utenti e ruoli e 4.5 Servizi e ruoli
  * aggiornamento conferma-piano nel paragrafo 6 Contesto pianificazioneAppalto
* specifiche-servizi-fvoe-fva.yaml
  * modificata la descrizione per l'operation /recupero-anagrafica-oe
    
## Documentazione
* Nella sezione Standard adottati del file README.md è stata aggiornata la versione sdk dell'eForms da adottare (1.9.0).
</details>

<details>
<summary><h1> Note di rilascio del 24/11/2023</h1></summary>

## Modello Dati 
* modello-dati-npa.yaml:
  * eliminato attributo oggettoPrincipaleContratto in LottoType per adeguamento eform 1.9
    
### Regole
* inserite le regole di esecuzione
* AD*.dmn, P1*.dmn, P2*.dmn, P3_4.dmn, A1*.dmn, A2*.dmn:
	* modificata la REG8

### Schede
* modello-dati-schede-AD*.yaml, modello-dati-schede-A3_6.yaml, modello-dati-schede-P7_1_1.yaml, modello-dati-schede-P7_1_2.yaml, modello-dati-schede-P7_1_3.yaml,modello-dati-schede-P7_2.yaml:
	* inseriti gli attributi: importo, oggetto, oggetto contratto, codNuts, codIstat, categoria, ccnl
* modello-dati-schede-AD*.yaml e modello-dati-schede-P7*.yaml:
	* resa la cpv secondaria opzionale
* modello-dati-schede-dati-comuni.yaml:
	*  aggiunto l'oggetto MultilinguaType per l'invio dei dati in multilingua
 	* modificati gli oggetti DatiBaseAppaltoType,DatiBaseAppaltoOptionalType,DatiBaseAppaltoPLType,DatiBaseAppaltoADType,DatiBaseLottoType,DatiBaseLottoOptionalType,DatiBaseLottoPLType,DatiBaseLottoP7_3Type,DatiBaseLottoADType: aggiunto l'attributo oggettoMl per il multilingua
  	* modificato l'oggetto DatiBaseAccessibilitaType: aggiunto l'attributo giustificazioneMl per il multilingua
  	* modificato l'oggetto DatiBaseModificaContrattualeType: aggiunto l'attributo causaModificaMl per il multilingua
  	* modificati gli oggetti PartecipanteType, PartecipanteADType: aggiunto l'attributo paeseOperatoreEconomicoMl per il multilingua
  	* modificato l'oggetto DatiBaseProceduraCompletoType:
  		* aggiunto l'attributo giustificazioneProceduraAccelerataMl per il multilingua
  	 	* modificato il type dell'attributo giustificazioneProceduraAccelerata
  	* aggiunto il campo array categoriaScorporabile per tutti gli oggetti lotto.
  	* modificati gli oggetti DatiBaseRisultatoProceduraType e DatiBaseEsitoRisultatoProceduraType: cambiato il nome del campo esito in esitoProcedura
  	* modificato l'oggetto PartecipanteType: eliminate le imprese ausiliarie
  	* modificato l'oggetto PartecipanteADType:
  		* eliminate le imprese ausiliarie.
  	 	* aggiunte le obbligatorietà sui campi
	* reso opzionale il campo tipologiaLavoro
* modello-dati-schede-IR1.yaml:
	* modificato l'oggetto RitardoType: aggiunto l'attributo motivoSospensioneMl per il multilingua
* modello-dati-schede-P5.yaml:
	* modificato l'oggetto LottoP5Type: aggiunto l'attributo oggettoMl per il multilingua
 	* aggiunto l'array delle stazioni appaltanti
* modello-dati-schede-P7.3.yaml:
	* aggiunto l'array delle stazioni appaltanti
 	* tolti gli attributi idSchedaPreinformazione e termineRidottoAvvisoPreinformazione
* modello-dati-schede-RSU1.yaml:
	* modificato l'oggetto SubappaltoType: aggiunto l'attributo oggettoMl per il multilingua
* modello-dati-schede-SA1.yaml: 
	* modificato l'oggetto AvanzamentoType: aggiunto l'attributo denominazioneAvanzamentoMl per il multilingua
* modello-dati-schede-SC1.yaml:
	* idPartecipante: da tipo string diventa tipo uuid
* modello-dati-schede-I1.yaml:
	* resi opzionali i campi consegnaFrazionata e avvioPerFasi
* modello-dati-schede-AD5.yaml:
	* tolti i campi codiceFiscaleSA e denominazioneSA dall'oggetto appalto.
 	* reso opzionale il campo cup
* modello-dati-schede-P3*.yaml, modello-dati-schede-P6*.yaml, modello-dati-schede-P7_2.yaml, modello-dati-schede-AD*.yaml, modello-dati-schede-RSU1.yaml:
	* reso obbligatorio il campo espd
* adeguamento eform 1.9: eliminato l'attributo oggettoPrincipaleContratto in tutte le schede. Il campo per indicare l'oggetto del contratto è oggettoContratto e la tipologica di riferimento è la oggettoContratto.json con i valori previsti dal TED.
* modello-dati-schede-P4_2.yaml,modello-dati-schede-P4_3.yaml,modello-dati-schede-P4_4.yaml,modello-dati-schede-P4_5.yaml,modello-dati-schede-P4_6.yaml, modello-dati-schede-M1.yaml, modello-dati-schede-M1.40.yaml:
	* reso obbligatorio il campo eform
* modello-dati-schede-P3*.yaml, modello-dati-schede-P2_18.yaml:
	* reso obbligatorio il campo stazioniAppaltanti
   
### Tipologiche
* statoPiano.json
  * aggiunti i nuovi valori IN_ATT_PUBB, IN_STOP_PUBB e PUBB
* errori.json
  * aggiunti i seguenti messaggi di errore: ERR93, FVX36, FVX37, FVX38
  * aggiunti i messaggi delle regole di esecuzione
* esito.json: rinominata in esitoProcedura.json
* accessibilita.json, accordoQuadro.json, affidamentiRiservati.json, criteriAggiudicazione.json, durata.json, esitoProcedura.json, giustificazione.json, giustificazioniAggiudicazioneDiretta.json, lingue.json, motiviModifica.json, oggettoContratto.json, sistemaDinamicoAcquisizione.json, subappalto.json, tipoClassificazione.json, tipoProcedura.json:
	* inserite le descrizioni in tedesco
* motiviRevisionePrezzi.json: rinominata in motivoRevisionePrezzi.json

## Orchestratore
* Aggiornato il file schema-cronologia-schede.xlsx
</details>

<details>
<summary><h1> Note di rilascio del 27/11/2023</h1></summary>

## Modello Dati 

    
### Regole
* AD5.dmn:
	* eliminata la regola REG53 perché il modello dati non richiede il ruoloOE.
* AD4.dmn:
	* eliminate le regole REG34, REG35, REG36 perché non valide per questa scheda.

### Schede
* modello-dati-schede-A2_29.yaml, modello-dati-schede-A2_30.yaml, modello-dati-schede-A2_31.yaml:
	* modificata la reference dell'oggetto datiBaseProcedura
* modello-dati-schede-P1.10.yaml,modello-dati-schede-P1.11.yaml,modello-dati-schede-P1.12.yaml,modello-dati-schede-P1.13.yaml,modello-dati-schede-P1.16.yaml,modello-dati-schede-P1.17.yaml,modello-dati-schede-P1.20.yaml,modello-dati-schede-P1.21.yaml,modello-dati-schede-P2.10.yaml,modello-dati-schede-P2.11.yaml,modello-dati-schede-P2.12.yaml,modello-dati-schede-P2.13.yaml,modello-dati-schede-P2.16.yaml,modello-dati-schede-P2.17.yaml,modello-dati-schede-P2.20.yaml,modello-dati-schede-P2.21.yaml,modello-dati-schede-P3.1.yaml,modello-dati-schede-P3.3.yaml,modello-dati-schede-P3.4.yaml,modello-dati-schede-AD3.yaml,modello-dati-schede-AD1.25.yaml,modello-dati-schede-AD1.26.yaml,modello-dati-schede-AD1.28.yaml,modello-dati-schede-AD2.25.yaml,modello-dati-schede-AD2.26.yaml,modello-dati-schede-AD2.28.yaml
	* reso obbligatorio l'attributo quadroEconomicoStandard
</details>

<details>
<summary><h1> Note di rilascio del 30/11/2023</h1></summary>

## Scenari di esempio 
* Aggiunta la cartella [scenari-di-esempio](docs/scenari-di-esempio) che riporta la sequenza di operazioni da eseguire per ottenere l'aggiudicazione di un appalto nel settore ordinario sopra soglia
  
## Documentazione
* Nel file README.md è stato aggiunto il riferimento alla nuova sezione Scenari di esempio
</details>

<details>
<summary><h1> Note di rilascio del 04/12/2023</h1></summary>
	
## Modello Dati 

### Regole
* S3.dmn
	* riviste le regole
### Schede
* modello-dati-schede-I1.yaml:
	* modificato l'oggetto DatiInizioType: corretto il nome dell'attributo dataDisposizioneInizio (ISSUE 748)
### Tipologiche
* errori.json
  * aggiunti i seguenti messaggi di errore: ERR94
* tipoSoggettoANAG.json
  * nuova tipologica ad uso interno
* naturaGiuridicaANAG.json
  * nuova tipologica ad uso interno
  
## Orchestratore  
* Aggiornato il file schema-cronologia-schede.xlsx
</details>

<details>
<summary><h1> Note di rilascio del 18/12/2023</h1></summary>

## Modello Dati 
* modello-dati-npa.yaml:
  * aggiunto idAvvisoPVL in DatiPubblicazioneITType
  * aggiunti publicationId e publicationUrl in DatiPubblicazioneEUType
  * aggiunti codiceScheda e codiceNuovaScheda in EsitoOperazioneType
       
### Regole

### Schede
* modello-dati-schede-CSU1.yaml:
  * eliminata perché non utlizzata
* modello-dati-schede-AD3.yaml, modello-dati-schede-AD4.yaml, modello-dati-schede-AD5.yaml, modello-dati-schede-P6.1.yaml, modello-dati-schede-P6.2.yaml, modello-dati-schede-P7.2.yaml:
  * reso opzionale il campo espd
* modello-dati-schede-AD2*.yaml,modello-dati-schede-AD3.yaml,modello-dati-schede-AD4.yaml,modello-dati-schede-AD5.yaml:
	* inserito l'oggetto datiBaseDocumenti
    
### Tipologiche
* errori.json
  * aggiunti i seguenti messaggi di errore: ERR95
* CPV.json:
  * eliminati i codici duplicati 

## Orchestratore  
* Aggiornato il file schema-cronologia-schede.xlsx
</details>

<details>
<summary><h1>Note di rilascio del 31/01/2024 (esercizio 01/03/2024 ore 13:00)</h1></summary>

## Pianificazione orario
Il rilascio in esercizio è pianificato per le ore 13:00 e avra' una durata di circa un'ora, durante la quale i servizi PCP non saranno raggiungibili.

## Modello Dati 
* modello-dati-npa.yaml:
  * modificato l'attributo $ref dell'oggetto scheda in AvvisoType
    
### Regole (IN ESERCIZIO IL 09/02/2024)
* P1_16.dmn, P1_17.dmn, P1_18.dmn, P1_19.dmn, P1_20.dmn, P1_21.dmn, P1_23.dmn, P1_24.dmn,P2_16.dmn, P2_17.dmn, P2_18.dmn, P2_19.dmn, P2_20.dmn, P2_21.dmn, P2_23.dmn, P2_24.dmn, P3*.dmn, P4*.dmn:
  * aggiunte le regole REG95, REG96, REG97 sulla data di scadenza presentazione offerte e data scadenza presentazione invito

### Schede
* issue 712:
  * modello-dati-schede-dati-comuni.yaml: oggetto DatiPersonaGiuridicaType: sostituito idgruppo con idPartecipante. 
* issue 694, 799:
  * modello-dati-schede-dati-comuni.yaml: oggetto OfferteType: reso obbligatorio il campo aggiudicatario.
* issue 448,548,567,875:	
  * modello-dati-schede-CO2.yaml: oggetto AnacFormCO2Type: inserito cig allo stesso livello dell’oggetto conclusione.
  * modello-dati-schede-CO1.yaml: oggetto AnacFormCO1Type: inserita la doppia chiave: idContratto e cig
* issue 796:
  * modello-dati-schede-A3_6.yaml: eliminato l'oggetto datiBaseRisultatoProcedura da AggiudicazioneA3_6Type
* issue 599:
  * modello-dati-schede-dati-comuni.yaml, modello-dati-schede-A3.6.yaml, modello-dati-schede-PL2.7.yaml, modello-dati-schede-PL2.8.yaml, modello-dati-schede-PL2.9.yaml, modello-dati-schede-P3.4.yaml, modello-dati-schede-P2.10.yaml, modello-dati-schede-P2.11.yaml, modello-dati-schede-P2.16.yaml, modello-dati-schede-P2.17.yaml, modello-dati-schede-P2.18.yaml, modello-dati-schede-AD3.yaml, modello-dati-schede-AD4.yaml, modello-dati-schede-AD5.yaml: modificata la descrizione dei dati comuni con il ted
* issue 308:
  * modello-dati-schede-RSU1.yaml: modificata la cardinalità dell'oggetto codiceFiscaleDitta. Diventato array codiciFiscaliOE
* issue 850, 855, 912:
  * reso offertePresentate obbligatorio nelle schede A1_31, A2_31, A3_5
* issue 854:
  * reso offertePresentate obbligatorio nella scheda A3_3 
* tolto il campo idAppalto da tutte le schede.
* PL,P*,AD*: reso obbligatorio l'oggetto datiBaseDocumenti con il link SA su tutte le schede in cui il campo url è obbligatorio.
* modello-dati-schede-P5.yaml:
  * eliminati i campi oggetto, oggettoMl, oggettoContratto, importo da LottoP5Type e aggiunto il campo datiBase, contenenti i campi oggetto, oggettoMl, oggettoContratto, importo.
 * modello-dati-schede-dati-comuni.yaml:
   * aggiunta obbligatorietà del campo datiBase.importo.
  * eliminato il pattern nei campi percentuale e inseriti gli attributi minimum =0 e maximum=100
 * P2*,P3_4,P3_5,P4*,P6*,P7*,PL2_8:
  * reso obbligatorio l'oggetto datiBaseTerminiInvio
       
### Tipologiche
* aggiornata tipoDocumento.json
* aggiornata ruoloOE.json
* aggiornata categoria.json: eliminate le voci non più valide
* aggiornata codIstat.json: eliminate le voci non più valide, eliminata la voce "non classificato", corretti i codici inserendo la codifica a 9 cifre
* aggiornata codNuts.json: eliminate le voci non più valide, eliminata la voce "non classificato"
* tipoCatastoStato.json
  * nuova tipologica utilizzabile per la compilazione della richiesta di documentazione 
* tipoFormaGiuridica.json
  * nuova tipologica utilizzabile per la compilazione della richiesta di documentazione
* aggiornata errori.json
  
## Orchestratore  
* Modificata la colonna N "pubblicazioneNazionale": 
  * scheda AD3: impostato pubblicazioneNazionale a SI
  * schede A3_1, A3_2, A3_3: impostato pubblicazioneNazionale a NO (modifica già pubblicata)
* Modificata la colonna R "schedaSuccessiva": 
  * scheda CO1: inclusa se stessa come scheda successiva
  * scheda CO2: inclusa se stessa come scheda successiva
  * per le schede di indizione sottosoglia:
  	* dove prevista come scheda successiva S1,S2 diventa S1,S2,NAG
  	* dove prevista come scheda successiva S2 diventa S2,NAG
  	* dove prevista come scheda successiva S1 diventa S1,NAG
  * per la scheda S1 diventa S2,NAG
</details>

<details>
<summary><h1>Note di rilascio del 09/02/2024 (Segnalazioni chiuse in Esercizio)</h1></summary>

### Regole
* Ticket#2024012460000868:
  * AD4.dmn: eliminate le regole REG69, REG70, REG71
* Issue 1010:
  * AC1.dmn: corretto il messaggio di errore e modificata la REG74 perché accetti anche lo 0 nel campo oneriDerivanti. 
* Issue 1076:
  * P*.dmn: corretta la REG15
* P1_18.dmn, P2_18.dmn, P5.dmn, A3_6.dmn: corretta la sintassi
* AD5.dmn: aggiundo controllo su importo dati base

### Tipologiche
* aggiornata errori.json
</details>

<details>
<summary><h1>Note di rilascio del 12/03/2024 (Segnalazioni chiuse in Esercizio)</h1></summary>

### Segnalazioni
* Issue 996, 1046, 1052, 1130, 1249:
  * fix messaggio di errore troncato proveniente dal TED
* Issue 1174, 1156, 1134:
  * fix errore partecipante ERR77
    
### Tipologiche
* aggiornata errori.json
* strumentiSvolgimentoProcedure.json: riattivata la voce con codice 5
</details>

<details>
<summary><h1>Note di rilascio del 15/03/2024 (in Esercizio)</h1></summary>
 
### Tipologiche
* misurePremiali.json: inserita la voce con codice 13
* fattispecieTracciabilita.json: inserita la voce con codice 11
</details>

<details>
<summary><h1>Note di rilascio del 26/03/2024 (in Esercizio)</h1></summary>
 
### Tipologiche
* errori.json: aggiunti i valori REG105, REG106
* codNUTS.json: aggiunti i valori per allineare la tipologica al TED

### Regole
* P1*,P2*,P3*,P4*, P6*, P7*, PL*: inserito controllo REG105 e REG106 sulla validità dei datiBaseTerminiInvio

### Orchestratore  
* Scheda S3: aggiornati i valori per la colonna "schedaSuccessiva"

</details>

<details>
<summary><h1>Note di rilascio del 05/04/2024</h1></summary>

**NOTA: La nuova operazione /richiedi-documenti è utilizzabile in ambiente di qualificazione a partire dal 6 giugno**

## Modello Dati
* modello-dati-fvoe-fva.yaml:
  * creato un nuovo oggetto DatiSA_00004. Oggetto che riporta i dati per richiedere il documento CERTIFICATO DEL CASELLARIO GIUDIZIARIO (INTEGRALE).
  * creato un nuovo oggetto DatiSA_00020. Oggetto che riporta i dati per richiedere il documento CERTIFICATO DELL'ANAGRAFE DELLE SANZIONI AMMINISTRATIVE DIPENDENTI DA REATO
  * creato un nuovo oggetto DatiSA_00036. Oggetto che riporta i dati per richiedere il documento DATI REDDITUALI SOCIETA DI PERSONE e per il documento DATI REDDITUALI IMPRESA INDIVIDUALE
  * creato un nuovo oggetto DatiSA_00047. Oggetto che riporta i dati per richiedere il documento CONSISTENZA MEDIA PERSONALE
  * creato un nuovo oggetto DatiSA_00048. Oggetto che riporta i dati per richiedere il documento COSTO COMPLESSIVO PERSONALE
  * creato un nuovo oggetto DatiSA_00050. Oggetto che riporta i dati per richiedere il documento COMUNICAZIONE ANTIMAFIA
  * creato un nuovo oggetto DatiSA_00899. Oggetto che riporta i dati generici per richiedere il documento all' Operatore Economico
  * creato un nuovo oggetto DocumentoRichiediType Oggetto che riporta i dati della Richiesta di Documentazione verso gli enti certificanti
 
## Specifiche Interfacce
* specifiche-servizi-fvoe-fva.yaml:
  * inserita operazione richiedi-documenti
</details>

<details>
<summary><h1>Aggiornamento documentazione del 24/04/2024</h1></summary>
	
## read.me
* Pubblicazione ambiente ATTESTAZIONE
  
## documento-specifiche-servizi-npa.md 
* Aggiornamento descrizione servizio modifica-avviso
</details>

<details>
<summary><h1>Note di rilascio del 15/05/2024 (in Esercizio)</h1></summary>

### Tipologiche
* errori.json: aggiunti gli errori ERR110, ERR111
* motivoEsclusioneOrdinarioSpeciale: riattivato codice 24
</details>

<details>
<summary><h1> Note di rilascio del 21/05/2024 (in Esercizio)</h1></summary>

### Schede 
* modello-dati-schede-P2*.yaml, modello-dati-schede-P3*.yaml, modello-dati-schede-P7_3.yaml, modello-dati-schede-AD2*.yaml,modello-dati-schede-AD3.yaml, modello-dati-schede-AD4.yaml, modello-dati-schede-AD5.yaml, modello-dati-schede-A3_6.yaml, modello-dati-schede-dati-comuni.yaml:
	* reso obbligatorio l'oggetto datiBaseCPV e il campo cpvPrevalente
 * **[PROCESSO DI ANNULLAMENTO PROCEDURA O COMUNICAZIONE NUOVO IMPORTO/CUP]** modello-dati-schede-CM1.yaml, modello-dati-schede-CM2.yaml, modello-dati-schede-ANN.yaml:
 	* Nuove schede CM1, CM2 e ANN per annullamento procedura (ANN) o comunicazione nuovo importo per appalti sopra (CM1) e sotto (CM2) i 5K euro.
* modello-dati-schede-P7_1_1.yaml, modello-dati-schede-P7_1_2.yaml, modello-dati-schede-P7_1_3.yaml, modello-dati-schede-P7_2.yaml:
	* eliminata l'obbligatorietà del campo motivazioneCIG
* modello-dati-schede-P3_4.yaml, modello-dati-schede-P3_5.yaml, modello-dati-schede-P7_3.yaml:
	* resi obbligatori l'oggetto datiBaseDocumenti e il campo url
* modello-dati-schede-NAG.yaml: reso obbligatorio l'oggetto datiBaseRisultatoProcedura
* modello-dati-schede-M2.yaml,modello-dati-schede-M2_40.yaml: reso obbligatorio l'oggetto datiBaseModificaContrattuale
* modello-dati-schede-dati-comuni.yaml, modello-dati-schede-A3_6.yaml, modello-dati-schede-AD3.yaml, modello-dati-schede-AD4.yaml, modello-dati-schede-AD5.yaml, modello-dati-schede-P5.yaml:
	*  Impostata la minLength a 8 sul codiceAppalto (si raccomanda l'adozione immediata per consentire l'enforcement rinviato a settembre)
  
## Modello Dati
 * **[PROCESSO DI ANNULLAMENTO PROCEDURA O COMUNICAZIONE NUOVO IMPORTO/CUP]** modello-dati-npa.yaml:
	*  aggiunti i riferimenti alle nuove schede (CM1,CM2,ANN) nell'oggetto SchedaPostPubblicazioneType

## Orchestratore
* righe relative alle schede P3_1, P3_2, P3_3, P6_1, P6_2, P5, AD4: aggiornata la colonna scheda successiva per includere le nuove schede CM1, ANN
* riga relativa alla scheda AD5: aggiornata la colonna scheda successiva per includere le nuove schede CM2, ANN
* inserite nuove schede CM1, CM2, ANN

### Regole
* **[PROCESSO DI ANNULLAMENTO PROCEDURA O COMUNICAZIONE NUOVO IMPORTO/CUP]** CM1.dmn, CM2.dmn, ANN.dmn:
  * regole relative alle nuove schede CM1, CM2 e ANN per annullamento procedura (ANN) o comunicazione nuovo importo o cup per appalti sopra (CM1) e sotto (CM2) i 5K euro.
* AD*.dmn, A3_6.dmn:
  * inserito controllo che ci sia un solo idPartecipante
* **IN ESERCIZIO DAL 15/03/2024** P7_1*.dmn,P7_2.dmn,P6*.dmn,P1_10.dmn,P2_10.dmn,P1_11.dmn,P2_11.dmn,P1_12.dmn,P2_12.dmn,P1_13.dmn,P2_13.dmn,P1_14.dmn,P2_14.dmn,PL1_7.dmn,PL2_7.dmn,PL1_8.dmn,PL2_8.dmn,PL1_9.dmn,PL_2_9.dmn,P4*.dmn,P3*.dmn,P1_16.dmn,P2_16.dmn,P1_17.dmn,P2_17.dmn,P1_18.dmn,P2_18.dmn,P1_19.dmn,P2_19.dmn,P1_20.dmn,P2_20.dmn,P1_21.dmn,P2_21.dmn,P1_23.dmn,P2_23.dmn,P1_24.dmn,P2_24.dmn:
  * inserite le regole di validazione REG105.dmn, REG106 per i campi scadenzaPresentazioneInvito e oraScadenzaPresentazioneOfferte
* P1*.dmn, P2*.dmn, P3*.dmn, P4*.dmn,P5.dmn, P6*.dmn, P7_1*.dmn,P7_2.dmn;
  * inserita la regola di validazione 110: somma dell'importo dei lotti compresa tra 80% e 100% dell'importo gara
* **IN ESERCIZIO DAL 30/04/2024**
  P1_23.dmn, P1_24.dmn;
  * eliminate REG98 e REG99    

### Tipologiche
* aggiornata errori.json
* aggiornata contrattiDisposizioniParticolari.json
* aggiornata fattispecieTracciabilita.json
* aggiornata motivoEsclusioneConcessione.json
* aggiornata motivoEsclusioneOrdinarioSpeciale.json
* aggiornata tipoFascicolo.json
* aggiornata tipoDocumento.json
* **[PROCESSO DI ANNULLAMENTO PROCEDURA O COMUNICAZIONE NUOVO IMPORTO/CUP]** motivoAnnullamento.json:
  * nuova tipologica per annullamento procedura.
* **[PROCESSO DI ANNULLAMENTO PROCEDURA O COMUNICAZIONE NUOVO IMPORTO/CUP]** motivoRichiestaModifica.json:
  * nuova tipologica per comunicazione nuovo importo o cup per appalti sopra (CM1) e sotto (CM2) i 5K euro.
* enteCertificante.json:
  * nuova tipologica usata internamente dal FE della SA per la trascodfica.
* aggiornata codiceScheda.json
</details>

# Note di rilascio del 02/08/2024 (Changelog-01 In esercizio)
**NOTA**
* Pubblicazione contenuti su GitHub: già pubblicati
* Rilascio in Qualificazione: 07/08/2024
* Rilascio in Esercizio: 08/08/2024
  
### Tipologiche
* motivoEsclusioneOrdinarioSpeciale.json, fattispecieTracciabilità.json, motivoEsclusioneConcessione.json:
	* aggiunta la voce "Appalti Difesa e Sicurezza soggetti al D. Lgs 208/2011"
* tipoSoggetto.json:
	* eliminata la voce "RTI"
### Schede
* modello-dati-schede-P3.1.yaml:
	* rimossa la richiesta di ESPD
### Orchestratore
* modificata la colonna includeESPD a "NO" per la scheda P3_1

# Note di rilascio del 06/08/2024 (Changelog-02 - In esercizio)
**NOTA**
* Pubblicazione contenuti su GitHub: 12/09/2024
* Rilascio in Qualificazione: 24/09/2024 (rilasciata il 27/09/2024)
* Rilascio in Esercizio: 14/11/2024 (eseguito come da pianificazione)
  
**Disponibile in tutti gli ambienti**
    
## documento-specifiche-servizi-npa.md 
* Inserito paragrafo 11.3 Lista tipi documento richiedibili agli enti certificanti
  
## Specifiche Interfacce
* specifiche-servizi-fvoe-fva.yaml:
  * modificato esempio operazione richiedi-documenti
    
### Tipologiche
* statoAutorizzazione.json
  * aggiunto il valore: 05
* tipoDocumento.json:
  * aggiunti i seguenti valori: 00008 00042 00010 e 00011
* errori.json
  * aggiunto il valore : FVX58, REG111, REG113, FVC01, FVC02 FVX53, FVX54, FVX55, FVX56, FVX57, ERR114, ERR115, ERR116, ERR117, ERR118, ERR119, ERR120, ERR121, ERR122, ERR123
* tipoPrefettura.json
  * nuova tipologica utilizzata per la scelta della prefettura nella compilazione della richiesta del 00001-Comunicazione Antimafia
* enteCertificante.json
  * aggiunti i seguenti valori : MINLAV ISPLAV
* erroriEC.json
  * nuova tipologica utilizzata per la trascodifica degli errori provenienti dagli enti certificanti.
* aggiunta la tipologica operazioneSDA.json
* aggiunta la tipologica statoSDA.json Tipologica ad uso intern utilizzata dalla gestione dei partecipanti della scheda S0 dal FVOE2.0
* aggiunta la tipologica tipoNotifica.json Tipologica ad uso interno per la gestione delle notifiche inviate verso il RP e l'OE all'interno delle funzionalità del FVOE2.0
* codiceScheda.json: aggiunte le nuove schede per lo SDA: CSDA1, CSDA2, S0, ISDA1, ISDA2
    
### Modello Dati 
* modello-dati-fvoe-fva.yaml:
  * modificato Soggetto_00050 - nel "luogo di nascita" inserita una regex per controllare i comuni italiani e gli stati esteri
  * modificato DatiSA_00050 - Inserito il codice prefettura e altriSoggetti . Modifica RegExp per codice comune di nascita
  * modificato DatiNominativo_00004DatiNascita - nel "codice catasto comune italiano" modificata la regex per controllare i comuni italiani.
  * modificato il nome dei modelli dati utlizzato per richiedere i documenti agli enti certificanti. Rimosso il carattere "_"
* modello-dati-npa.yaml: aggiunti i riferimenti alle nuove schede ISDA1,ISDA2 nell'oggetto SchedaComunicaAppaltoType e S0,CSDA1,CSDA2 nell'oggetto SchedaPostPubblicazioneType
* rimosso il campo idSDA dall'oggetto AppaltoISDABaseType
  
### Schede 
* issue 853: 
	* modello-dati-schede-P6.2.yaml: reso obbligatorio il quadroEconomicoStandard
* issue 1151:
	* modello-dati-schede-dati-comuni.yaml: per le schede P1_23 e P2_23 spostato il campo contrattiDisposizioniParticolari dall'oggetto appalto all'oggetto lotti, come per tutte le altre schede
* modello-dati-schede-S4.yaml:
	* modificata la descrizione della scheda
* modello-dati-schede-PL1_*.yaml:
	* aggiunta l'anacForm con l'oggetto stazioniAppaltanti.
* modello-dati-schede-PL2_7.yaml, modello-dati-schede-PL2_8.yaml, modello-dati-schede-PL2_9.yaml, modello-dati-schede-dati-comuni.yaml:
	* aggiunto l'oggetto stazioniAppaltanti in anacForm.
* modello-dati-schede-AD5.yaml:
	* eliminata l'obbligatorietà dell'oggetto datiBaseDocumenti e del campo url
* modello-dati-schede-P2_19.yaml, modello-dati-schede-S2.yaml:
	* aggiornata la descrizione della Scheda in coerenza con il file orchestratore.
*  modello-dati-schede-dati-comuni.yaml:
	* eliminati i campi saNonSoggettaObblighi24Dicembre2015 e iniziativeNonSoddisfacenti dall'oggetto lotto in tutte le schede
 	* Reso obbligatorio l'oggetto finanziamenti
  	* Reso obbligatorio oggetto ipotesiCollegamento
   	* Reso obbligatorio l'oggetto quadroEconomicoConcorsiProgettazione
  	* Motivo deroga: corretta la descrizione del campo
	* modalita acquisizione: resa facolativa nelle schede P_20 e P_21
  	* aggiunto il campo costituzionesocietascopo nelle schede P1_14, P2_14 ,P1_19, P2_19
   	* oggetto parita di genere: aggiunto il flag ulterioriMisurePremiali
   	* Reso obbligatorio il campo quadroEconomicoStandardRideterminato dell'oggetto ModificaContrattualeType
   	* Resi obbligatori gli importi del quadroEconomicoStandardRideterminato
    * Reso obbligatorio il campo offertaAnomala in offerteType
  * aggiunto l'enum OperazioneSDAEnum utilizzato nella scheda S0
  * In ComunicazioneType modificata la cardinalità del campo cup
  * aggiunto l'oggetto AppaltoISDABaseType utilizzato nelle schede ISDA1 e ISDA2
  * aggiunto l'oggetto LottoISDABaseType utilizzato nelle schede ISDA1 e ISDA2
  * aggiunto l'oggetto DatiBaseStrumentiProceduraSDAType utilizzato nella scheda ISDA2
  * aggiunto l'oggetto DatiBaseStrumentiProceduraCSDAType utilizzato nella scheda CSDA2
  * aggiunto l'oggetto DatiBaseDurataCSDAType utilizzato nella scheda CSDA2
  * modificato l'oggetto AppaltoP7_2Type: aggiunta la proprietà idSDA
* modello-dati-schede-A3_6.yaml, modello-dati-schede-AD3.yaml:
	* inserito il quadro economico delle concessioni
* modello-dati-schede-AD1_28.yaml, modello-dati-schede-AD2_28.yaml:
	* eliminato il quadro economico standard
* modello-dati-schede-AD1_25.yaml, modello-dati-schede-AD2_25.yaml, modello-dati-schede-AD1_26.yaml, modello-dati-schede-AD2_26.yaml:
	* eliminato il quadro economico delle concessioni
* modello-dati-schede-AD1_27.yaml, modello-dati-schede-AD2_27.yaml:
	* eliminati i quadri economici
* modello-dati-schede-PL2_1.yaml,modello-dati-schede-PL2_2.yaml,modello-dati-schede-PL2_3.yaml:
	* revisione schede: aggiunti nell'oggetto appalto i campi: importo, accordoQuadro, 	sistemaDinamicoAcquisizione,astaElettronica, fineSistemaDinamicoAcquisizione. Aggiunti nell'oggetto lotto i campi: lotidentifier, importo, cpv secondaria, criteriAggiudicazione, affidamentiRiservati, accessibilita, contrattiSuccessivi, dataInvioInviti. Eliminato il campo codNUTS.
* modello-dati-schede-PL2_7.yaml,modello-dati-schede-PL2_8.yaml,modello-dati-schede-PL2_9.yaml:
	* revisione schede: aggiunti nell'oggetto appalto i campi: proceduraAccelerata, giustificazioneProceduraAccelerata, giustificazioneProceduraAccelerataMl,fineSistemaDinamicoAcquisizione. Aggiunto nell'oggetto lotto il campo: contrattiSuccessivi
* modello-dati-schede-P7_3.yaml:
	* revisione schede: reso obbligatorio l'oggetto datiBaseDurata
* modello-dati-schede-P2_10.yaml,modello-dati-schede-P2_11.yaml,modello-dati-schede-P2_16.yaml,modello-dati-schede-P2_17.yaml, modello-dati-schede-P2_18.yaml:
	* revisione schede: resi obbligatori gli oggetti datiBaseAggiuntivi, datiBaseStrumentiProcedura
* modello-dati-schede-P2_12.yaml,modello-dati-schede-P2_13.yaml,modello-dati-schede-P2_14.yaml,modello-dati-schede-P2_19.yaml,modello-dati-schede-P2_20.yaml,modello-dati-schede-P2_21.yaml:
	* revisione schede: reso obbligatorio l'oggetto datiBaseAggiuntivi
* modello-dati-schede-P2_23.yaml,modello-dati-schede-P2_24.yaml:
	* revisione schede: reso obbligatorio l'oggetto datiBaseImporto
* modello-dati-schede-P3_1.yaml,modello-dati-schede-P3_2.yaml,modello-dati-schede-P3_3.yaml:
	* revisione schede: resi obbligatori gli oggetti datiBaseAggiuntivi,datiBaseAggiudicazione. Aggiunto nell'oggetto lotto il campo: ccnl
* modello-dati-schede-P3_4.yaml:
	* revisione schede: reso obbligatorio l'oggetto datiBaseAggiudicazione.
* modello-dati-schede-P3_5.yaml:
	* revisione schede: resi obbligatori gli oggetti: datiBaseAggiudicazione,tipoRealizzazione,ipotesiCollegamento
* modello-dati-schede-P4*.yaml:
	* revisione schede: resi obbligatori gli oggetti: ccnl,ipotesiCollegamento,datiBaseAggiuntivi
* modello-dati-schede-P6*.yaml:
	* revisione schede: resi obbligatori gli oggetti: datiBaseStrumentiProcedura,ipotesiCollegamento,datiBaseAggiudicazione
* modello-dati-schede-P7_1_1.yaml, modello-dati-schede-P7_1_2.yaml, modello-dati-schede-P7_1_3.yaml, modello-dati-schede-P7_2.yaml:
	* revisione schede:
 		* resi obbligatori gli oggetti: datiBaseContratto,datiBaseAggiudicazione,datiBaseAggiuntivi,contrattiDisposizioniParticolari.
 		* aggiunto l'oggetto datiBaseStrumentiProcedura
* modello-dati-schede-AD2_25.yaml,modello-dati-schede-AD2_26.yaml,modello-dati-schede-AD2_27.yaml,modello-dati-schede-AD2_28.yaml, modello-dati-schede-AD4.yaml:
	* revisione schede: reso obbligatorio l'oggetto datiBaseContratto
* modello-dati-schede-AD3.yaml:
	* revisione schede: resi obbligatori gli oggetti afferenteInvestimentiPNRR, datiBaseContratto.
* modello-dati-schede-AD5.yaml:
	* eliminati i campi ccnl, categoria e categoria scorporabile. Nell'oggetto datibasecontratto tolta l'obbligatorietà del campo codNuts.
* modello-dati-schede-A3_6.yaml:
	* revisione schede: resi obbligatori gli oggetti datiBaseContratto,datiBaseAggiudicazioneAppalto.
* modello-dati-schede-A2_29.yaml,modello-dati-schede-A2_30.yaml,modello-dati-schede-A2_31.yaml:
	* revisione schede: resi obbligatori gli oggetti datiBaseAggiudicazioneAppalto,datiBaseSubappalti, datiBaseRisultatoProcedura. aggiunti i campi offertaMinimoRibasso, proceduraAccelerata
* modello-dati-schede-A2_32,modello-dati-schede-A2_35: resi obbligatori gli oggetti: datiBaseRisultatoProcedura,datiBaseAggiudicazioneAppalto,quadroEconomicoConcessioni. Eliminato il campo nImpreseEscluseInsufficientiGiustificazioni. Aggiunto datiBaseProcedura
* modello-dati-schede-A2_33.yaml,modello-dati-schede-A2_34.yaml,modello-dati-schede-A2_36.yaml,modello-dati-schede-A2_37.yaml,modello-dati-schede-A3_1.yaml,modello-dati-schede-A3_2.yaml,modello-dati-schede-A3_3.yaml,modello-dati-schede-A3_5.yaml: resi obbligatori gli oggetti: datiBaseRisultatoProcedura,datiBaseAggiudicazioneAppalto
* modello-dati-schede-A3_4.yaml: resi obbligatori gli oggetti: datiBaseRisultatoProcedura,datiBaseAggiudicazioneAppalto,datiBaseStrumentiProcedura,datiBaseSubappalti
* modello-dati-schede-A4.yaml: resi obbligatori gli oggetti: numeroOfferteAmmesse,datiBaseRisultatoProcedura,datiBaseAggiudicazioneAppalto
* modello-dati-schede-A7_1_2.yaml: reso obbligatorio l'oggetto: datiBaseAggiudicazioneAppalto
* modello-dati-schede-ISDA1.yaml,modello-dati-schede-ISDA2.yaml,modello-dati-schede-S0.yaml,modello-dati-schede-CSDA1.yaml,modello-dati-schede-CSDA2.yaml: nuove schede per la gestione dello SDA
* modello-dati-schede-P7_2.yaml: 
  * inserito identificativo per lo SDA
  * all'interno della property "appalto" di AnacFormP7_2Type, è stato cambiato il riferimento adottato da AppaltoP7BaseType a AppaltoP7_2Type e perciò rimosso il campo "StrumentiSvolgimentoProcedure" dalla scheda P7_2 e sostituito con l'oggetto "datiBaseStrumentiProcedura"
* #48952 modello-dati-schede-CM1.yaml,modello-dati-schede-CM2.yaml,modello-dati-schede-AD5.yaml,modello-dati-schede-P5.yaml: modificata la cardinalità del campo cupLotto e del campo cup
* modello-dati-schede-P2_19,S2 modificata la descrizione delle schede
* modello-dati-schede-S0 Aggiunto il campo lotIdentier 
* modello-dati-schede-ISDA2 rimosso il campo lotIdentifier dall'oggetto LottoSDAType

  
## Orchestratore
* modificata a sì la colonna includeAnacForm per le schede PL1_*.
* inserite le informazioni per gestire il processo delle nuove schede SDA (ISDA1, ISDA2, S0, CSDA1, CSDA2)
* aggiunte schede ISDA1, ISDA2, S0, CSDA1, CSDA2

### Regole
* issue 1145: eliminata la REG13 da tutte le schede
* issue 1016, 1144, 1194, 1310: eliminata la REG67 dalle schede dove non è presente il campo giustificazioneProceduraAccelerata
* P7_1_1.dmn, P7_1_2.dmn, P7_1_3.dmn, P7_2.dmn:
	* inserito controllo sul campo motivazioneCIG
* ISDA1.dmn, ISDA2.dmn, S0.dmn, CSDA1.dmn, CSDA2.dmn: nuove regole per la gestione dello SDA
* CM1.dmn,CM2.dmn,AD5.dmn,P5.dmn: aggiornate le regole in coerenza con la nuova cardinalità del cupLotto
* ISDA1.dmn: aggiunte le regole REG98 e REG99
* ISDA2.dmn: aggiunte le regole REG98 e REG99

# Note di rilascio del 06/08/2024 (Changelog-03)
**NOTA**
* Pubblicazione contenuti su GitHub: 15/10/2024 (eseguita come da pianificazione)
* Rilascio in Qualificazione: 15/11/2024 (eseguito come da pianificazione)
* Rilascio in Esercizio: 16/12/2024 (ripianificata)
  
**la nota di rilascio potrà essere integrata successivamente**
    
### Modello Dati 
* modello-dati-npa.yaml: aggiunti i riferimenti alle nuove schede AOC nell'oggetto SchedaComunicaAppaltoType e SOC, COC nell'oggetto SchedaPostPubblicazioneType
  
### Schede 
* modello-dati-schede-ANN.yaml, modello-dati-schede-CM1.yaml: modificata la descrizione in coerenza con l'orchestratore
* modello-dati-schede-dati-comuni.yaml: 
	* reso facoltativo il campo dataSottoscrizione dell'oggetto DatiBaseModificaContrattualeType utilizzato nelle schede M2 e M2_40
	* aggiunti gli oggetti AggiudicazioneBaseSopraSogliaType e AggiudicazioneCompletaSopraSogliaType: reso offertePresentate facoltativo
	* modificati gli oggetti AggiudicazioneA1_29Type, AggiudicazioneA1_30Type, AggiudicazioneA1_32Type, AggiudicazioneA1_33Type, AggiudicazioneA1_34Type, AggiudicazioneA1_35Type, AggiudicazioneA1_36Type, AggiudicazioneA1_37Type: aggiornate le reference ai nuovi oggetti creati
	* modificato l'oggetto AggiudicazioneA1_31Type: reso offertePresentate facoltativo
	* aggiunto l'oggetto SettoreEnum 
	* aggiunto il campo obbligatorio contrattoDifesa agli oggetti AppaltoP7BaseType, AppaltoP7_2Type.
	* aggiunto il campo obbligatorio settore agli oggetti AppaltoP3BaseType, AppaltoP4BaseType, AppaltoP7BaseType, AppaltoP7_2Type, AppaltoISDABaseType, AppaltoP_14Type, AppaltoP_19Type, AppaltoAD1_28Type
	* aggiunto l'oggetto MotivoDerogaQlfEnum
	* aggiunto il campo facoltativo derogaQualificazione agli oggetti LottoBaseType, LottoP4BaseType, LottoP6BaseType, LottoP7BaseType, LottoP7_2BaseType, AggiudicazioneAD1_25Type, AggiudicazioneAD1_26Type, AggiudicazioneAD1_28Type
	* deprecato il campo strumentiSvolgimentoProcedura
	* rimosso il maximum sul campo offertaInAumento dell'oggetto OfferteType 
* modello-dati-schede-P7.3.yaml: aggiunti i campi obbligatori contrattoDifesa, settore all'oggetto AppaltoP7_3Type
* modello-dati-schede-AD3.yaml: 
	* aggiunti i campi obbligatori contrattoDifesa, settore all'oggetto AppaltoAD3Type
	* aggiunto il flag accordoQuadro nell'oggetto AppaltoAD3Type
* modello-dati-schede-P5.yaml: aggiunto il campo obbligatorio settore all'oggetto AppaltoP5Type
* modello-dati-schede-A3_6.yaml: 
	* aggiunto il campo obbligatorio settore all'oggetto AppaltoA3_6Type
	* aggiunto il flag accordoQuadro nell'oggetto AppaltoA3_6Type
* modello-dati-schede-AD5.yaml: aggiunto il campo obbligatorio settore all'oggetto AppaltoAD5Type
* modello-dati-schede-P3_4.yaml: 
	* aggiunto il campo facoltativo derogaQualificazione all'oggetto LottoP3_4Type
	* aggiunto il campo accordoQuadro nell'oggetto appalto.datiBaseStrumentiProcedura
* modello-dati-schede-P3_5.yaml: 
	* aggiunto il campo facoltativo derogaQualificazione all'oggetto LottoP3_5Type
	* aggiunto il campo accordoQuadro nell'oggetto appalto.datiBaseStrumentiProcedura
* modello-dati-schede-AOC.yaml, modello-dati-schede-SOC.yaml, modello-dati-schede-COC.yaml: aggiunte le nuove schede per il flusso degli Organi Costituzionali
* modello-dati-schede-ISDA2.yaml: 
	* modificata la reference della properties AppaltoSDAType.datiBase verso DatiBaseAppaltoType
	* modificata la reference della properties LottoSDAType.datiBase verso DatiBaseLottoType

### Tipologiche
* errori.json: aggiunti gli errori REG117, REG118, REG119, REG120, REG121, REG122, REG123, REG124, REG125, REG126, ERR113
* codiceScheda.json: 
	* aggiornate le descrizioni delle schede CM1, ANN
	* aggiunte le nuove schede per gli Organi Costituzionali AOC, SOC, COC
* settore.json: aggiunta per indicare il settore: ordinario/speciale
* motivoDerogaQlf.json: aggiunta per indicare il motivo della deroga al servizio di qualificazioneSA
  
## Orchestratore
* scheda M2: modificata la colonna flussoAppartenenza: aggiunti 30,61,62
* scheda NAG: Rimozione flussi 71 e 73, Inserimento dei flussi 711, 712, 713, 61, 62
* scheda CM1: 
	* modificata la colonna settore-regime con appalti>= 5k, modificata la colonna schedaDescrizione con "Scheda di comunicazione modifica dati della procedura per appalti sopra o pari a 5K euro"
	* modificata la colonna fase in "affidamento"
* scheda CM2: modificata la colonna fase in "affidamento"
* scheda ANN:
	* modificata la colonna fase in "affidamento"
	* modificata la colonna schedaDescrizione con "Annullamento affidamento"
* scheda M1: modificata la colonna schedaDescrizione con "Modifica contrattuale, direttiva generale e direttiva settoriale"
* scheda M2: modificata la colonna schedaDescrizione con "Modifica contrattuale sottosoglia, generale e settoriale"
* scheda A2_29: inserito nella colonna ‘flussoAppartenenza’ il flusso 72
* schede P1*: modificata la colonna schedaSuccessiva: aggiunte le A1.
* aggiunte le tre nuove schede per gli Organi Costituzionali e aggiunta la scheda SOC come scheda successiva alla S2.

### Regole
* SC1.dmn: aggiunta la regola REG117
* P1_10.dmn, P1_11.dmn, P1_12.dmn, P1_13.dmn, P1_14.dmn,P1_16.dmn,P1_17.dmn,P1_19.dmn,P1_20.dmn,P1_21.dmn,P2_10.dmn, P2_11.dmn, P2_12.dmn, P2_13.dmn, P2_14.dmn,P2_16.dmn,P2_17.dmn,P2_19.dmn,P2_20.dmn,P2_21.dmn,P3_4.dmn,P3_5.dmn,P4*.dmn,P6*.dmn,P7_1_1.dmn,P7_1_2.dmn,P7_1_3.dmn,P7_2.dmn,AD1_25.dmn,AD2_25.dmn,AD1_26.dmn,AD2_26.dmn,AD1_28.dmn,AD2_28.dmn: aggiunte le regole REG118, REG119, REG120, REG121, REG122
* AOC.dmn, SOC.dmn, COC.dmn: aggiunte le regole relative alle nuove schede per il flusso degli Organi Costituzionali

<details>
<summary><h1>Note di rilascio del 09/09/2024  (In Esercizio)</h1></summary>

## Modello Dati

### Tipologiche
* errori.json: Aggiunto errore REG112

### Regole
* ticket 55540: A1_32.dmn, A2_32.dmn, A1_35.dmn, A2_35.dmn: corretto errore di sintassi nella regola REG47
* ticket 56076: P3_3.dmn, P3_4.dmn: eliminate le REG37 e REG38 perché i campi non sono presenti nel modello dati
* ticket 56077: P6_2.dmn: eliminata la REG11 perché il campo non è presente nel modello dati
* ticket 55503: P1_10.dmn,P1_11.dmn,P1_12.dmn,P1_13.dmn,P1_14.dmn,P1_16.dmn,P1_17.dmn,P1_19.dmn,P1_20.dmn,P1_21.dmn,P1_23.dmn,P1_24.dmn,P2_10.dmn,P2_11.dmn,P2_12.dmn,P2_13.dmn,P2_14.dmn,P2_16.dmn,P2_17.dmn,P2_19.dmn,P2_20.dmn,P2_21.dmn,P2_23.dmn,P2_24.dmn,P3_1.dmn,P3_2.dmn,P3_3.dmn,P3_4.dmn,P3_5.dmn,P4_1.dmn,P4_2.dmn,P4_3.dmn,P4_4.dmn,P4_5.dmn,P4_6.dmn,P6_1.dmn,P6_2.dmn: corretto un errore di sintassi nella regola REG20
* ticket 54713: 
A1_29.dmn,A1_30.dmn,A1_31.dmn,A1_32.dmn,A1_33.dmn,A1_34.dmn,A1_35.dmn,A1_36.dmn,A1_37.dmn,A2_29.dmn,A2_30.dmn,A2_31.dmn,A2_32.dmn,A2_33.dmn,A2_34.dmn,A2_35.dmn,A2_36.dmn,A2_37.dmn,A3_1.dmn,A3_2.dmn,A3_3.dmn,A3_4.dmn,A3_5.dmn,A3_6.dmn,A4_1.dmn,A4_2.dmn,A4_3.dmn,A4_4.dmn,A4_5.dmn,A4_6.dmn,A7_1_1.dmn,A7_1_2.dmn,AD1_25.dmn,AD1_26.dmn,AD1_27.dmn,AD1_28.dmn,AD2_25.dmn,AD2_26.dmn,AD2_27.dmn,AD2_28.dmn,AD3.dmn, AD4.dmn, AD5.dmn: aggiunta la REG112 per verificare che le aggiudicazioni non siano vuote

### Orchestratore
* aggiunto il valore 713 nella colonna flussoAppartenenza
</details>

# Note di rilascio del 01/10/2024 (In Esercizio)

## Modello Dati

### Tipologiche
* ticket 56624:
errori.json: Aggiunto errore REG68_1

### Regole
* ticket 56624:
  * AD1*.dmn, AD2*.dmn,A1_29.dmn,A1_30.dmn,A1_31.dmn,A1_32.dmn,A1_33.dmn,A1_34.dmn,A1_35.dmn,A2_29.dmn,A2_30.dmn,A2_31.dmn,A2_32.dmn,A2_33.dmn,A2_34.dmn,A2_35.dmn: corretta la sintassi della regola 68 e aggiunta la REG68_1
* ticket 55651:
  * P1_10.dmn,P1_11.dmn,P1_12.dmn,P1_13.dmn,P1_14.dmn,P2_10.dmn,P2_11.dmn,P2_12.dmn,P2_13.dmn,P2_14.dmn: corretta la sintassi della regola REG106 per considerare anche l'orario
  * P1_16.dmn,P1_17.dmn,P1_19.dmn,P1_20.dmn,P1_21.dmn,P1_23.dmn,P1_24.dmn,P2_16.dmn,P2_17.dmn,P2_19.dmn,P2_20.dmn,P2_21.dmn,P2_23.dmn,P2_24.dmn,P3_1.dmn,P3_2.dmn,P3_3.dmn,P3_4.dmn,P3_5.dmn,P4_1.dmn,P4_2.dmn,P4_3.dmn,P4_4.dmn,P4_5.dmn,P4_6.dmn: corretta la sintassi delle regole REG105 e REG106 per considerare anche l'orario
  * P6_1.dmn,P6_2.dmn: corretta la sintassi della regola REG105 per considerare anche l'orario
 
# Note di rilascio del 03/10/2024 (In Esercizio)

## Modello Dati

### Regole
* ticket 55650, 59540, 59541, 59556:
  * P1_10.dmn,P1_11.dmn,P1_12.dmn,P1_13.dmn,P1_14.dmn,P1_16.dmn,P1_17.dmn,P1_19.dmn,P1_20.dmn,P1_21.dmn,P2_10.dmn,P2_11.dmn,P2_12.dmn,P2_13.dmn,P2_14.dmn,P2_16.dmn,P2_17.dmn,P2_19.dmn,P2_20.dmn,P2_21.dmn: corretta la sintassi della regola REG1

* ticket 59350:
  * P1_23.dmn,P1_24.dmn: eliminate le REG98 e REG99 inserite per errore nell'ultimo rilascio

# Note di rilascio del 13/11/2024 (In Esercizio)

## Modello Dati
### Schede
* ticket 59340:
	* modello-dati-schede-dati-comuni.yaml: rimosso il maximum sul campo offertaInAumento dell'oggetto OfferteType

### Regole
* ticket 55651:
	* P7_1_1.dmn,P7_1_2.dmn,P7_1_3.dmn: corretta la sintassi della regola REG106 per considerare anche l'orario
	* P7_2.dmn,PL1_8.dmn,PL2_8.dmn: corretta la sintassi della regola REG105 per considerare anche l'orario
	* P1_18.dmn, P2_18.dmn, PL1_7.dmn, PL1_9.dmn, PL2_7.dmn, PL2_9.dmn: corretta la sintassi delle regole REG105 e REG106 per considerare anche l'orario
* ticket 60341:
 	* P7_1_1.dmn,P7_1_2.dmn,P7_1_3.dmn,P7_2.dmn: inserito Output name "Errore"
* ticket 55775:
  * M1.dmn, M2.dmn: corretta la sintassi delle regole REG54, REG55, REG56, REG61, REG62, REG63
  * M1_40.dmn, M2_40.dmn: corretta la sintassi delle regole REG54, REG55, REG56, REG61, REG62
* ticket 60869:
	* AD4.dmn: corretta la sintassi della regola REG53 per uniformarla alle altre AD*
* ticket 59340:
	* A1_29.dmn,A1_30.dmn,A1_33.dmn,A1_34.dmn, A2_29.dmn, A2_30.dmn,A2_33.dmn,A2_34.dmn, A3*.dmn, A4*.dmn: modificata la REG51 perché sia accettato solo un valore non nullo tra offertePresentate.offertaEconomica e offertePresentate.offertaInAumento 

### Orchestratore
* ticket 59196:
	* corretto il riferimento alla scheda RSU1 per la scheda IR1

### Tipologiche
* ticket 57847:
	* errori.json: modificato l'errore REG61
* tipoPrefettura.json:
  * corretta la sintassi del file
  
### Segnalazioni
* ticket 61371:
  * fix estrazione dati REG68_1
  
  
# Note di rilascio del 22/11/2024 (In Esercizio)

## Modello Dati
  
### Segnalazioni
  * AD1*.dmn, AD2*.dmn,A1_29.dmn,A1_30.dmn,A1_31.dmn,A1_32.dmn,A1_33.dmn,A1_34.dmn,A1_35.dmn,A2_29.dmn,A2_30.dmn,A2_31.dmn,A2_32.dmn,A2_33.dmn,A2_34.dmn,A2_35.dmn: eliminata la REG68_1

# Note di rilascio del 09/12/2024 (In Esercizio)
### Tipologiche
* ticket 57597:
	* errori.json: inserito nuovo messaggio di errore ERR124
* ticket 60734:
	* errori.json: inseriti nuovi messaggi di errore ERR125, ERR126


<summary><h1>Note di rilascio del 10/12/2024 (Changelog-04)</h1></summary>

**NOTA**
* Pubblicazione contenuti su GitHub: 10/12/2024
* Rilascio in Qualificazione: 17/01/2025
* Rilascio in Esercizio: 17/02/2025
  
**la nota di rilascio potrà essere integrata successivamente**
    
### Modello Dati 
* modello-dati-npa.yaml:
  * aggiunta nuova scheda S2R
  
### Schede 
* modello-dati-schede-A7.1.2.yaml:
	* oggetto AggiudicazioneA7Type: deprecati i campi: acquisizioneCup, afferenteInvestimentiPNRR, cupLotto, paritaDiGenereGenerazionale, partecipanti, finanziamenti, datiBaseAccessibilita
	* oggetto AggiudicazioneA7Type: aggiunti i campi: valore soglia anomalia, offerte Presentate, numero offerte ammesse, esitoProceduraAnnullata, datiBaseRisultatoProcedura, datiBaseSottomissioniRicevute
* modello-dati-schede-dati-comuni.yaml: 
	* oggetto AggiudicazioneA7Type: deprecati i campi: acquisizioneCup, afferenteInvestimentiPNRR, cupLotto, paritaDiGenereGenerazionale, partecipanti, finanziamenti, datiBaseAccessibilita
	* oggetto AggiudicazioneA7Type: aggiunti i campi: valore soglia anomalia, offerte Presentate, numero offerte ammesse, esitoProceduraAnnullata, datiBaseRisultatoProcedura, datiBaseSottomissioniRicevute
 	* aggiunto l'oggetto MotivoRichiestaRettificaEnum
* modello-dati-schede-S2R.yaml:
	* nuova scheda di rettifica della scheda S2

### Tipologiche
* errori.json:
	* aggiornata la descrizione della REG100 e della REG18
 	* aggiunti gli errori REG19 e REG20_1
* motivoRichiestaRettifica.json: nuova tipologica per la scheda S2R
* giustificazioniAggiudicazioneDiretta.json: aggiornata alla versione ted sdk 1.12
	* modificate le label su below-thres-sme, int-oper, tra-ser
 	* aggiunte occorrenze char-imp, exc-circ-rail, sim-infra
  	* rimossa occorrenza rail
* tipoProcedura.json: aggiornata alla versione ted sdk 1.12
	* modificate le label su comp-tend
 	* aggiunta occorrenzea exp-int-rail
* codiceScheda.json: 
  * aggiunta la nuova scheda S2R.

## Orchestratore
* Nella riga relativa alla scheda SC1, nella colonna ‘scheda successiva’, eliminata la scheda SA1.
* Modificata la riga della scheda S2: aggiunta la S2R come possibile scheda successiva
* Aggiunte le informazioni sulla nuova scheda S2R
  
### Regole
* AD3.dmn, AD*_25.dmn, AD*_26.dmn, AD*_27.dmn: 
	* aggiornata la REG100 per consentire più partecipanti in caso di accordo quadro.
* A7.1.1.dmn, A7.1.2.dmn: 
	* aggiunte le regole REG47, REG50, REG51, REG52
* S2R.dmn: aggiunte regole per la nuova scheda S2R
* P1_10.dmn,P1_11.dmn,P1_12.dmn,P1_13.dmn,P1_14.dmn,P1_16.dmn,P1_17.dmn,P1_19.dmn,P1_20.dmn,P1_21.dmn,P1_23.dmn,P1_24.dmn,P2_10.dmn,P2_11.dmn,P2_12.dmn,P2_13.dmn,P2_14.dmn,P2_16.dmn,P2_17.dmn,P2_19.dmn,P2_20.dmn,P2_21.dmn,P2_23.dmn,P2_24.dmn,P3_1.dmn,P3_2.dmn,P3_3.dmn,P3_4.dmn,P3_5.dmn,P4_1.dmn,P4_2.dmn,P4_3.dmn,P4_4.dmn,P4_5.dmn,P4_6.dmn,P6_1.dmn,P6_2.dmn:
	* aggiornata la REG18
 	* aggiunte le REG19 e REG20_1



<summary><h1>Scadenza certificato digitale *.anticorruzione.it</h1></summary>
* Il certificato digitale SSL utilizzato per i servizi di ANAC è in scadenza il prossimo 24 luglio. La nuova catena di certificazione pubblica è disponibile per il download nella cartella docs/certificato SSL.
Il certificato sarà installato alle 17.00 di oggi (18 luglio) negli ambienti di qualificazione e attestazione e il 22 luglio alle ore 13.00 in ambiente di esercizio.

