---
title: Elenco delle tabelle cdR in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: Lo schema del database di registrazione dettagli chiamata (CDR) è costituito dalle tabelle riportate di seguito.
ms.openlocfilehash: 27381a95a5de2613845fa831e8730a1bc06d374ae7936eaedb31d239b3dbb0cf
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54343250"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>Elenco delle tabelle cdR in Skype for Business Server 2015
 
Lo schema del database di registrazione dettagli chiamata (CDR) è costituito dalle tabelle riportate di seguito. 
  
## <a name="static-tables"></a>Tabelle statiche

|**tavolo**|**Descrizione**|
|:-----|:-----|
|[Tabella CallPriorities in Skype for Business Server 2015](callpriorities.md) <br/> |In questa tabella è archiviato l'elenco delle possibili priorità delle chiamate, ad esempio "emergency" (di emergenza), "urgent" (urgente), "normal" (normale), "non-urgent" (non urgente) e così via.  <br/> |
|[Tabella ConferenceJoinTimeThresholds Skype for Business Server 2015](conferencejointimethresholds.md) <br/> |In questa tabella sono archiviati i limiti di classificazione utilizzati dal rapporto riepilogativo Tempo di partecipazione alla conferenza.  <br/> |
|[Tabella DeRegisterType Skype for Business Server 2015](deregistertype.md) <br/> |In questa tabella è archiviato l'elenco dei possibili motivi di annullamento della registrazione utente, ad esempio "client initiated" (avviato dall'utente), "registration expired" (registrazione scaduta), "client crash" (arresto anomalo del client) e così via.  <br/> |
|[Tabella MediaList](medialist.md) <br/> |,  <br/> |
|[Tabella PurgeSettings](purgesettings.md) <br/> |In questa tabella sono archiviate informazioni che specificano se le registrazioni dettagli chiamata obsolete verranno eliminate automaticamente dal database CDR.  <br/> |
|[Tabella Ruoli](roles.md) <br/> |In questa tabella è archiviato l'elenco dei possibili ruoli per le conferenze, ad esempio partecipante e relatore.  <br/> |
|[Tabella SIPResponseMetaData](sipresponsemetadata.md) <br/> |In questa tabella è archiviato un elenco di codici di risposta SIP con la classificazione e la definizione di ogni codice.  <br/> |
   
## <a name="supporting-tables"></a>Tabelle di supporto

|**tavolo**|**Descrizione**|
|:-----|:-----|
|[Tabella ClientVersions in Skype for Business Server 2015](clientversions.md) <br/> |In questa tabella sono archiviati il tipo e il numero di versione dei singoli client coinvolti in una chiamata con le informazioni acquisite nel database.  <br/> |
|[Tabella ConferenceUris in Skype for Business Server 2015](conferenceuris.md) <br/> |In questa tabella è archiviato l'elenco degli URI conferenza utilizzati nelle chiamate relative alle conferenze.  <br/> |
|[Tabella ContentTypes in Skype for Business Server 2015](contenttypes.md) <br/> |In questa tabella è archiviato l'elenco dei tipi di contenuto SIP (Session Initiation Protocol) utilizzati sia nelle chiamate peer-to-peer che nelle conferenze telefoniche.  <br/> |
|[Tabella Devices in Skype for Business Server 2015](devices.md) <br/> |In questa tabella è archiviato l'elenco dei dispositivi con il relativo produttore, la versione hardware e l'indirizzo MAC.  <br/> |
|[Tabella Dialogs in Skype for Business Server 2015](dialogs.md) <br/> |In questa tabella sono archiviate le informazioni relative all'ID dialogo per ogni sessione nel database.  <br/> |
|[Tabella EdgeServers in Skype for Business Server 2015](edgeservers.md) <br/> |In questa tabella è archiviato l'elenco dei server perimetrali utilizzati per le chiamate esterne.  <br/> |
|[Tabella Gateways in Skype for Business Server 2015](gateways.md) <br/> |In questa tabella è archiviato l'elenco dei gateway utilizzati per le chiamate VoIP (Voice over Internet Protocol).  <br/> |
|[Tabella HardwareVersions Skype for Business Server 2015](hardwareversions.md) <br/> |In questa tabella è archiviato l'elenco delle versioni hardware dei dispositivi (telefoni da tavolo).  <br/> |
|[Tabella Manufacturers Skype for Business Server 2015](manufacturers.md) <br/> |In questa tabella è archiviato l'elenco dei produttori dei dispositivi (telefoni da tavolo).  <br/> |
|[Tabella Mcus in Skype for Business Server 2015](mcus.md) <br/> |In questa tabella sono archiviate le informazioni relative ai diversi A/V Conferencing Server con i relativi URI.  <br/> |
|[Tabella MediationServers](mediationservers.md) <br/> |In questa tabella è archiviato l'elenco dei Mediation Server utilizzati per le chiamate VoIP.  <br/> |
|[Tabella Telefoni](phones.md) <br/> |In questa tabella sono archiviati tutti i numeri di telefono utilizzati nelle chiamate VoIP che sono state archiviate o di cui sono stati registrati i dettagli.  <br/> |
|[Tabella Pools](pools.md) <br/> |In questa tabella sono archiviati i nomi del pool in cui vengono acquisiti i messaggi istantanei.  <br/> |
|[Tabella Server](servers.md) <br/> |In questa tabella è archiviato il nome dei server coinvolti nelle chiamate.  <br/> |
|[Tabella Tenant](tenants.md) <br/> |In questa tabella sono archiviati i tenant supportati dalla distribuzione corrente. Vi sono alcuni tenant predefiniti per l'utente Enterprise, l'utente federato, l'utente di connettività di messaggistica istantanea pubblica e gli utenti anonimi.  <br/> |
|[Tabella UserAgentDef](useragentdef.md) <br/> |Mappe degli agenti utente ai nomi descrittivi dell'agente.  <br/> |
|[Tabella Utenti](users.md) <br/> |In questa tabella sono archiviati gli URI degli utenti che hanno partecipato alle sessioni registrate o archiviate nel database.  <br/> |
|[Tabella UserStatistics](userstatistics.md) <br/> |Archivia le informazioni sull'utilizzo del sistema da parte di un singolo utente.  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>Tabelle specifiche dei record CDR per le conferenze

|**tavolo**|**Descrizione**|
|:-----|:-----|
|[Tabella Conferenze in Skype for Business Server 2015](conferences.md) <br/> |In questa tabella sono archiviate le informazioni relative a tutte le conferenze che sono state archiviate o di cui sono stati registrati i dettagli, inclusi l'URI conferenza e la data/ora di inizio e fine.  <br/> |
|[Tabella ConferenceSessionDetails in Skype for Business Server 2015](conferencesessiondetails-0.md) <br/> |In questa tabella sono archiviate le informazioni relative a tutte le sessioni di conferenza basate su SIP, inclusi la data/ora di inizio e fine, l'ID utente, il codice di risposta e l'ID diagnostica di ogni sessione.  <br/> |
|[Tabella FocusJoinsAndLeaves Skype for Business Server 2015](focusjoinsandleaves.md) <br/> |In questa pagina sono archiviate le informazioni sulle partecipazioni e le abbandonazioni alle conferenze, tra cui il ruolo e la versione client degli utenti.  <br/> |
|[Tabella McuJoinsAndLeaves Skype for Business Server 2015](mcujoinsandleaves.md) <br/> |In questa tabella sono archiviate le informazioni relative agli A/V Conferencing Server coinvolti in una conferenza e la data/ora di partecipazione e abbandono degli utenti.  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>Tabelle per i messaggi nelle conferenze di messaggistica istantanea

|**tavolo**|**Descrizione**|
|:-----|:-----|
|[Tabella ConferenceMessageCount in Skype for Business Server 2015](conferencemessagecount.md) <br/> |In questa tabella è archiviato, per ogni conferenza di messaggistica istantanea, il numero dei messaggi inviati da ogni utente.  <br/> |
|[Tabella IMReportSummary Skype for Business Server 2015](imreportsummary.md) <br/> |Questa tabella fornisce un rapporto complessivo sulle sessioni di messaggistica istantanea tenute in un'organizzazione.  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>Tabelle per le sessioni peer-to-peer

|**tavolo**|**Descrizione**|
|:-----|:-----|
|[Tabella SessionDetails](sessiondetails.md) <br/> |In questa tabella sono archiviate le informazioni relative a tutte le sessioni peer-to-peer, inclusi la data/ora di inizio e fine, l'ID utente, il codice di risposta e il numero dei messaggi per ogni utente.  <br/> |
|[Tabella FileTransfers in Skype for Business Server 2015](filetransfers-0.md) <br/> |In questa tabella sono archiviate le informazioni relative alle sessioni di trasferimento file, inclusi il nome di file e il risultato (accettazione, rifiuto o annullamento).  <br/> |
|[Media table](media.md) <br/> |In questa tabella sono archiviate le informazioni relative ai diversi tipi di contenuto multimediale coinvolti nelle sessioni peer-to-peer.  <br/> |
   
## <a name="table-for-voip-call-details"></a>Tabella per i dettagli delle chiamate VoIP

|**tavolo**|**Descrizione**|
|:-----|:-----|
|[Tabella VoipDetails](voipdetails-0.md) <br/> |In questa tabella sono archiviate, per ogni chiamata VoIP/PSTN tra due parti, le informazioni relative alla chiamata, ad esempio l'ID del telefono VoIP, il gateway utilizzato e la parte che si è disconnessa. Fa riferimento alla [tabella SessionDetails per l'ora](sessiondetails.md) di inizio/fine delle chiamate e il codice di risposta. <br/> |
   
> [!NOTE]
> Se una parte coinvolta in una chiamata è un utente VoIP o se nella chiamata è coinvolto un Mediation Server, verrà creato un record in questa tabella. Le informazioni sulle chiamate VoIP/VoIP che non coinvolgono un telefono PSTN (Public Switched Telephone Network) vengono acquisite nella [tabella SessionDetails.](sessiondetails.md) 
  
## <a name="table-for-e9-1-1-call-auditing"></a>Tabella per il controllo delle chiamate di emergenza

|**tavolo**|**Descrizione**|
|:-----|:-----|
|[Tabella Locations in Skype for Business Server 2015](locations.md) <br/> |In questa tabella sono archiviate, per ogni chiamata di emergenza, le informazioni relative alla località della chiamata. Fa riferimento alla [tabella SessionDetails per l'ora](sessiondetails.md) di inizio/fine delle chiamate e il codice di risposta. <br/> |
   
> [!NOTE]
> In questa tabella è contenuto solo il BLOB della località per la chiamata di emergenza. Fa riferimento alla tabella SessionDetails per altre informazioni dettagliate relative alla chiamata. 
  
## <a name="tables-for-troubleshooting"></a>Tabella per la risoluzione dei problemi

|**tavolo**|**Descrizione**|
|:-----|:-----|
|[Tabella delle applicazioni in Skype for Business Server 2015](application.md) <br/> |Archivia le informazioni sui vari processi Skype for Business Server 2015 coinvolti nel routing e nelle connessioni.  <br/> |
|[Tabella CallType Skype for Business Server 2015](calltype.md) <br/> |Archivia informazioni sui tipi di chiamata, ad esempio "audio", "messaggistica istantanea", "audio e video" e "condivisione applicazioni".  <br/> |
|[Tabella ErrorCategory in Skype for Business Server 2015](errorcategory.md) <br/> |Archivia il nome descrittivo per ogni Skype for Business Server di diagnostica 2015.  <br/> |
|[Tabella ErrorDef in Skype for Business Server 2015](errordef.md) <br/> |In questa tabella sono archiviate le informazioni relative ai tipi di errori con le relative definizioni.  <br/> |
|[Tabella ErrorReport in Skype for Business Server 2015](errorreport.md) <br/> |In questa tabella sono archiviate le informazioni relative agli errori che si sono verificati.  <br/> |
|[Tabella ProgressReport](progressreport.md) <br/> |In questa tabella sono archiviate le informazioni sui rapporti sullo stato dei vari passaggi Skype for Business Server 2015.  <br/> |
   
Le tabelle nell'elenco seguente vengono utilizzate internamente da Skype for Business Server 2015. I relativi dettagli non vengono illustrati in questo documento.
  
## <a name="tables-for-internal-use-by-lync-server"></a>Tabelle utilizzate internamente da Lync Server

|**tavolo**|**Descrizione**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Solo per utilizzo interno.  <br/> |
|**DbConfigInt** <br/> |Solo per utilizzo interno.  <br/> |
|**DbErrorMessage** <br/> |Solo per utilizzo interno.  <br/> |
|**Tabella FrontEnd** <br/> |Solo per utilizzo interno.  <br/> |
|**Tabella MSMQProcessing** <br/> |Solo per utilizzo interno.  <br/> |
|**SummaryTableConfiguration** <br/> |Solo per utilizzo interno.  <br/> |
|**Tabella Syndicators** <br/> |Solo per utilizzo interno.  <br/> |
|**Tabella SyndicatorsTenantMap** <br/> |Solo per utilizzo interno.  <br/> |
|**Tabella Task** <br/> |Solo per utilizzo interno.  <br/> |
|**UserStatistics** <br/> |Solo per utilizzo interno.  <br/> |
|**UsageSummary_UQ** <br/> |Solo per utilizzo interno.  <br/> |
|**UsageSummary** <br/> |Solo per utilizzo interno.  <br/> |
|**DaylightSavingYears** <br/> |Solo per utilizzo interno.  <br/> |
|**TimeZoneConfiguration** <br/> |Solo per utilizzo interno.  <br/> |
|**TimeZones** <br/> |Solo per utilizzo interno.  <br/> |
|**FailureSummary_UQ** <br/> |Solo per utilizzo interno.  <br/> |
|**FailureSummary** <br/> |Solo per utilizzo interno.  <br/> |
|**ServerSummary** <br/> |Solo per utilizzo interno.  <br/> |
|**MsDiagMetaData** <br/> |Solo per utilizzo interno.  <br/> |
   

