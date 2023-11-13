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

# Note di rilascio del 13/11/2023

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