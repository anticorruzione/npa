| Data | Attività |
| ---- | ---- |
| 25/10/2023 | Pubblicazione specifiche JWS |
| 09/10/2023 | Attivazione verifiche di base JWS sui servizi PDND <br> <ul><li>Verifica presenza e validità formale del token JWS</li> <li>Verifica valore dei claim standard: exp, iat, aud, nbf</li> <li>Verifica della durata massima del token fissata a 3600 secondi, claim: iat </li></ul> |
| 16/10/2023 | Attivazione verifiche avanzate JWS sui servizi PDND <br> <ul> <li>Verifica della durata massima del token fissata a 10 secondi, claim: iat </li>Verifica univocità del token, claim jti </li> <li>Verifica dei private claim <ul> <li> Iscrizione sul registro del modulo/piattaforma, verifica valore dei claim: regCodicePiattaforma, regCodiceComponente</li> <li> Esistenza profilo Utente, verifica valore dei claim: userCF, userRole, userLoa</li><li>Esistenza stazione appaltante, verifica valore dei claim: SAcodiceAUSA </li><li>Associazione dell’utente alla stazione appaltante </li> </ul> </li> </ul> |
