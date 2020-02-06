---
title: Elenco delle tabelle CDR in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 031843fd-c7ff-4534-9b02-8847aad70807
description: Lo schema di database di registrazione dei dettagli delle chiamate (CDR) è costituito dalle tabelle seguenti.
ms.openlocfilehash: a35636333366bbfd55d4337fadfec68af681db6f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815134"
---
# <a name="list-of-cdr-tables-in-skype-for-business-server-2015"></a>Elenco delle tabelle CDR in Skype for Business Server 2015
 
Lo schema di database di registrazione dei dettagli delle chiamate (CDR) è costituito dalle tabelle seguenti. 
  
## <a name="static-tables"></a>Tabelle statiche

|**Tabella**|**Descrizione**|
|:-----|:-----|
|[Tabella CallPriorities in Skype for Business Server 2015](callpriorities.md) <br/> |Archivia l'elenco delle possibili priorità di chiamata, ad esempio emergenza, urgente, normale, non urgente e altro ancora.  <br/> |
|[Tabella ConferenceJoinTimeThresholds in Skype for Business Server 2015](conferencejointimethresholds.md) <br/> |Archivia i limiti di classificazione usati dal report di riepilogo dell'ora di partecipazione alla conferenza.  <br/> |
|[Tabella DeRegisterType in Skype for Business Server 2015](deregistertype.md) <br/> |Archivia l'elenco dei possibili motivi di annullamento della registrazione degli utenti, ad esempio "client avviato", "Registrazione scaduta", "arresto anomalo del client" e altro ancora.  <br/> |
|[Tabella MediaList](medialist.md) <br/> |Archivia l'elenco dei tipi di elementi multimediali che possono generare voci nel database, ad esempio messaggistica istantanea, audio, video e trasferimento di file.  <br/> |
|[Tabella PurgeSettings](purgesettings.md) <br/> |Archivia le informazioni che specificano se (e quando) i record dettagli chiamata non aggiornati verranno eliminati automaticamente dal database CDR.  <br/> |
|[Tabella Roles](roles.md) <br/> |Archivia l'elenco dei ruoli di conferenza possibili, ad esempio partecipante e relatore.  <br/> |
|[Tabella SIPResponseMetaData](sipresponsemetadata.md) <br/> |Archivia un elenco di codici di risposta SIP e la classificazione e la definizione di ognuno di questi codici.  <br/> |
   
## <a name="supporting-tables"></a>Tabelle di supporto

|**Tabella**|**Descrizione**|
|:-----|:-----|
|[Tabella ClientVersions in Skype for Business Server 2015](clientversions.md) <br/> |Archivia i client (sia il tipo di client che il numero di versione) di ogni client coinvolto in una chiamata con le informazioni acquisite in questo database.  <br/> |
|[Tabella ConferenceUris in Skype for Business Server 2015](conferenceuris.md) <br/> |Archivia un elenco di ConferenceURIs usati nelle chiamate correlate alla conferenza.  <br/> |
|[Tabella ContentTypes in Skype for Business Server 2015](contenttypes.md) <br/> |Archivia un elenco di tipi di contenuto SIP (Session Initiation Protocol) usati sia in chiamate peer-to-peer che in conferenze telefoniche.  <br/> |
|[Tabella dispositivi in Skype for Business Server 2015](devices.md) <br/> |Archivia un elenco di dispositivi, inclusi il produttore, la versione hardware e l'indirizzo MAC.  <br/> |
|[Tabella finestre di dialogo in Skype for Business Server 2015](dialogs.md) <br/> |Archivia le informazioni sull'ID della finestra di dialogo per ogni sessione nel database.  <br/> |
|[Tabella EdgeServers in Skype for Business Server 2015](edgeservers.md) <br/> |Archivia un elenco di Edge Server usati per le chiamate esterne.  <br/> |
|[Tabella gateway in Skype for Business Server 2015](gateways.md) <br/> |Archivia un elenco di gateway usati per le chiamate VoIP (Voice over Internet Protocol).  <br/> |
|[Tabella HardwareVersions in Skype for Business Server 2015](hardwareversions.md) <br/> |Archivia un elenco di versioni hardware dei dispositivi (telefono da tavolo).  <br/> |
|[Tabella produttori in Skype for Business Server 2015](manufacturers.md) <br/> |Archivia un elenco di produttori di dispositivi (telefono da tavolo).  <br/> |
|[Tabella MCU in Skype for Business Server 2015](mcus.md) <br/> |Archivia le informazioni sui vari server di conferenza A/V e sui relativi URI.  <br/> |
|[Tabella MediationServers](mediationservers.md) <br/> |Archivia un elenco di server di mediazione usati per le chiamate VoIP.  <br/> |
|[Tabella Phones](phones.md) <br/> |Archivia tutti i numeri di telefono usati nelle chiamate VoIP archiviate o i cui dettagli delle chiamate sono stati registrati.  <br/> |
|[Tabella Pools](pools.md) <br/> |Archivia i nomi del pool in cui vengono acquisiti i messaggi di messaggistica istantanea.  <br/> |
|[Tabella Servers](servers.md) <br/> |Archivia il nome dei server coinvolti nelle chiamate.  <br/> |
|[Tabella Tenants](tenants.md) <br/> |Archivia i tenant supportati dalla distribuzione corrente. Sono presenti alcuni tenant per l'utente aziendale, un utente federato, un utente di connettività per messaggistica istantanea pubblica e utenti anonimi.  <br/> |
|[Tabella UserAgentDef](useragentdef.md) <br/> |Associa gli identificatori dell'agente utente ai nomi descrittivi dell'agente.  <br/> |
|[Tabella Users](users.md) <br/> |Archivia gli URI utente degli utenti che hanno partecipato a sessioni registrate o archiviate in questo database.  <br/> |
|[Tabella UserStatistics](userstatistics.md) <br/> |Archivia le informazioni sull'uso di un singolo utente del sistema.  <br/> |
   
## <a name="tables-specific-to-conference-cdr-records"></a>Tabelle specifiche dei record CDR per conferenze

|**Tabella**|**Descrizione**|
|:-----|:-----|
|[Tabella conferenze in Skype for Business Server 2015](conferences.md) <br/> |Archivia informazioni su tutte le conferenze archiviate o i cui dettagli sono stati registrati, inclusi ConferenceURI, e l'ora di inizio e di fine.  <br/> |
|[Tabella ConferenceSessionDetails in Skype for Business Server 2015](conferencesessiondetails-0.md) <br/> |Archivia informazioni su ogni sessione di conferenza basata su SIP, inclusi l'ora di inizio e di fine, l'ID utente, il codice di risposta e l'ID di diagnostica per ogni sessione.  <br/> |
|[Tabella FocusJoinsAndLeaves in Skype for Business Server 2015](focusjoinsandleaves.md) <br/> |Archivia le informazioni relative a riunioni e fogli di conferenza, inclusi il ruolo degli utenti e la versione client.  <br/> |
|[Tabella McuJoinsAndLeaves in Skype for Business Server 2015](mcujoinsandleaves.md) <br/> |Archivia le informazioni sui server di conferenza A/V coinvolti in una conferenza e l'utente partecipa e lascia gli orari.  <br/> |
   
## <a name="tables-for-messages-in-im-conferences"></a>Tabelle per i messaggi nelle conferenze di messaggistica istantanea

|**Tabella**|**Descrizione**|
|:-----|:-----|
|[Tabella ConferenceMessageCount in Skype for Business Server 2015](conferencemessagecount.md) <br/> |Per ogni conferenza di messaggistica istantanea, archivia il numero di messaggi inviati da ogni utente.  <br/> |
|[Tabella IMReportSummary in Skype for Business Server 2015](imreportsummary.md) <br/> |Fornisce un report globale sulle sessioni di messaggistica istantanea svolte in un'organizzazione.  <br/> |
   
## <a name="tables-for-peer-to-peer-sessions"></a>Tabelle per le sessioni peer-to-peer

|**Tabella**|**Descrizione**|
|:-----|:-----|
|[Tabella SessionDetails](sessiondetails.md) <br/> |Archivia informazioni su ogni sessione peer-to-peer, inclusi l'ora di inizio e di fine, l'ID utente, il codice di risposta e il numero di messaggi per ogni utente.  <br/> |
|[Tabella FileTransfers in Skype for Business Server 2015](filetransfers-0.md) <br/> |Archivia informazioni sulle sessioni di trasferimento di file, inclusi il nome e il risultato del file (accettato, rifiutato o annullato).  <br/> |
|[Tabella Media](media.md) <br/> |Archivia le informazioni sui diversi tipi di elementi multimediali coinvolti nelle sessioni peer-to-peer.  <br/> |
   
## <a name="table-for-voip-call-details"></a>Tabella per i dettagli delle chiamate VoIP

|**Tabella**|**Descrizione**|
|:-----|:-----|
|[Tabella VoipDetails](voipdetails-0.md) <br/> |Per ogni chiamata VoIP/PSTN a due parti, archivia le informazioni sulla chiamata, ad esempio l'ID telefono del telefono VoIP, il gateway usato e il partito disconnesso. Fa riferimento alla [tabella SessionDetails](sessiondetails.md) per gli orari di inizio/fine e il codice di risposta delle chiamate. <br/> |
   
> [!NOTE]
> Se una delle parti di una chiamata è un utente VoIP o se è stato coinvolto un Mediation Server nella chiamata, verrà creato un record in questa tabella. Le informazioni sulle chiamate VoIP/VoIP che non coinvolgono un telefono PSTN (Public Switched Telephone Network) vengono acquisite nella [tabella SessionDetails](sessiondetails.md). 
  
## <a name="table-for-e9-1-1-call-auditing"></a>Tabella per il controllo delle chiamate E9-1-1

|**Tabella**|**Descrizione**|
|:-----|:-----|
|[Tabella Locations in Skype for Business Server 2015](locations.md) <br/> |Per ogni chiamata di emergenza, ad esempio una chiamata avanzata di 9-1-1 (E9-1-1), memorizza le informazioni sulla posizione sulla chiamata. Fa riferimento alla [tabella SessionDetails](sessiondetails.md) per gli orari di inizio/fine e il codice di risposta delle chiamate. <br/> |
   
> [!NOTE]
> Questa tabella contiene solo il BLOB della posizione per la chiamata E9-1-1. Fa riferimento alla tabella SessionDetails per altre informazioni dettagliate sulla chiamata. 
  
## <a name="tables-for-troubleshooting"></a>Tabelle per la risoluzione dei problemi

|**Tabella**|**Descrizione**|
|:-----|:-----|
|[Tabella delle applicazioni in Skype for Business Server 2015](application.md) <br/> |Archivia le informazioni sui vari processi in Skype for Business Server 2015 coinvolti nel routing e nelle connessioni.  <br/> |
|[Tabella CallType in Skype for Business Server 2015](calltype.md) <br/> |Archivia informazioni sui tipi di chiamata, ad esempio "audio", "messaggistica istantanea", "audio e video" e "condivisione applicazioni".  <br/> |
|[Tabella ErrorCategory in Skype for Business Server 2015](errorcategory.md) <br/> |Archivia il nome descrittivo per ogni classificazione diagnostica di Skype for Business Server 2015.  <br/> |
|[Tabella ErrorDef in Skype for Business Server 2015](errordef.md) <br/> |Archivia informazioni sui tipi di errori e sulle relative definizioni.  <br/> |
|[Tabella ErrorReport in Skype for Business Server 2015](errorreport.md) <br/> |Archivia le informazioni sugli errori che si sono verificati.  <br/> |
|[Tabella ProgressReport](progressreport.md) <br/> |Archivia le informazioni sui rapporti sullo stato di avanzamento di vari passaggi coinvolti nei processi di Skype for Business Server 2015.  <br/> |
   
Le tabelle nell'elenco seguente vengono usate internamente da Skype for Business Server 2015. I relativi dettagli non sono descritti in questo documento.
  
## <a name="tables-for-internal-use-by-lync-server"></a>Tabelle per l'uso interno da Lync Server

|**Tabella**|**Descrizione**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Solo per uso interno.  <br/> |
|**DbConfigInt** <br/> |Solo per uso interno.  <br/> |
|**DbErrorMessage** <br/> |Solo per uso interno.  <br/> |
|**Tabella FrontEnd** <br/> |Solo per uso interno.  <br/> |
|**Tabella MSMQProcessing** <br/> |Solo per uso interno.  <br/> |
|**SummaryTableConfiguration** <br/> |Solo per uso interno.  <br/> |
|**Tabella Syndicate** <br/> |Solo per uso interno.  <br/> |
|**Tabella SyndicatorsTenantMap** <br/> |Solo per uso interno.  <br/> |
|**Tabella delle attività** <br/> |Solo per uso interno.  <br/> |
|**UserStatistics** <br/> |Solo per uso interno.  <br/> |
|**UsageSummary_UQ** <br/> |Solo per uso interno.  <br/> |
|**UsageSummary** <br/> |Solo per uso interno.  <br/> |
|**DaylightSavingYears** <br/> |Solo per uso interno.  <br/> |
|**TimeZoneConfiguration** <br/> |Solo per uso interno.  <br/> |
|**TimeZones** <br/> |Solo per uso interno.  <br/> |
|**FailureSummary_UQ** <br/> |Solo per uso interno.  <br/> |
|**FailureSummary** <br/> |Solo per uso interno.  <br/> |
|**ServerSummary** <br/> |Solo per uso interno.  <br/> |
|**MsDiagMetaData** <br/> |Solo per uso interno.  <br/> |
   

