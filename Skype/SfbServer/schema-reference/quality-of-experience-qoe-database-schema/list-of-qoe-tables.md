---
title: Elenco di tabelle QoE
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: Lo schema del database è costituito dalle tabelle seguenti.
ms.openlocfilehash: 291d2ddefefc264aa283480362a6f57cda9161cd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834486"
---
# <a name="list-of-qoe-tables"></a>Elenco di tabelle QoE
 
Lo schema del database è costituito dalle tabelle seguenti. 
  
**Tabelle di supporto**

|**tavolo**|**Descrizione**|
|:-----|:-----|
|[Tabella AppSharingMetricsThreshold](appsharingmetricsthreshold.md) <br/> |Archivia i valori ottimali e accettabili per le metriche di qualità dell'esperienza usate con la condivisione delle applicazioni.  <br/> |
|[Tabella CodecDescription](codecdescription.md) <br/> |Mappa gli identificatori di codec univoci al codec corrispondente.  <br/> |
|[Tabella IPAddress](ipaddress.md) <br/> |Mappa gli indirizzi IP agli identificatori di indirizzo IP univoci utilizzati altrove nel database della qualità dell'esperienza.  <br/> |
|[Tabella NetworkConnectionDetail](networkconnectiondetail.md) <br/> |Mappa i tipi di connessione di rete agli identificatori di connessione di rete utilizzati altrove nel database della qualità dell'esperienza.  <br/> |
|[Tabella PurgeSettings (QoE)](purgesettings-qoe.md) <br/> |Archivia le informazioni che specificano se e quando i record QoE non aggiornati verranno eliminati automaticamente dal database QoE.  <br/> |
|[Tabella TraceRoute](traceroute.md) <br/> |In questa tabella sono archiviate le informazioni di routing per le chiamate.  <br/> |
|[Tabella UserAgentDef (QoE)](useragentdef-qoe.md) <br/> |Mappa gli identificatori degli agenti utente ai nomi descrittivi dell'agente.  <br/> |
|[Tabella VideoMetricsThreshold](videometricsthreshold.md) <br/> |Archivia i valori ottimali e accettabili per le metriche di qualità dell'esperienza usate con le videochiamate.  <br/> |
|[Tabella UserAgent](useragent.md) <br/> |In questo database sono archiviati i tipi di agente utente SIP (Session Initiation Protocol) e i tipi di agente utente utilizzati nelle sessioni audio e video.  <br/> |
|[Tabella User](user-0.md) <br/> |In questo database sono archiviati gli URI di utenti, conferenze e telefonici utilizzati nelle sessioni audio e video.  <br/> |
|[Tabella Endpoint](endpoint.md) <br/> |In questo database vengono archiviati i nomi di computer FQDN degli endpoint che partecipano alle sessioni audio e video.  <br/> |
|[Tabella Pool](pool.md) <br/> |Archivia i nomi dei pool a cui appartengono i dati della metrica.  <br/> |
|[Tabella Device](device.md) <br/> |In questo database vengono archiviati i dispositivi di acquisizione e di rendering usati nelle chiamate audio/video.  <br/> |
|[Tabella DeviceDriver](devicedriver.md) <br/> |Archivia il driver per il dispositivo di acquisizione e il dispositivo di rendering usati nelle chiamate audio/video.  <br/> |
|[Tabella Conference](conference.md) <br/> |In questo database sono archiviati gli URI conferenza per gli scenari di conferenza o DialogID per altri scenari.  <br/> |
|[Tabella SessionCorrelation](sessioncorrelation.md) <br/> |Archivia CorrelationID per le chiamate PSTN.  <br/> |
|[Tabella PayloadDescription](payloaddescription.md) <br/> |Archivia il codec utilizzato nelle chiamate audio/video.  <br/> |
|[Tabella AppliedBandwidthSource](appliedbandwidthsource.md) <br/> |Archivia l'origine della larghezza di banda utilizzata nelle chiamate audio/video.  <br/> |
|[Tabella MacAddress](macaddress.md) <br/> |Archivia l'indirizzo MAC degli endpoint che partecipano alle sessioni audio e video.  <br/> |
|[Tabella Dialog](dialog.md) <br/> |Memorizza l'ID della finestra di dialogo delle sessioni audio e video.  <br/> |
|[Tabella Region](region.md) <br/> |Archivia l'area di rete definita nell'impostazione NCS.  <br/> |
|[Tabella UserSite](usersite.md) <br/> |Archivia il sito di rete definito nell'impostazione NCS.  <br/> |
|[Tabella Subnet](subnet.md) <br/> |Archivia la subnet definita nell'impostazione NCS.  <br/> |
|[Tabella MonitoredRegionLink](monitoredregionlink.md) <br/> |Archivia il collegamento area definito nell'impostazione NCS.  <br/> |
|[Tabella MonitoredUserSiteLink](monitoredusersitelink.md) <br/> |In questa tabella sono archiviati i collegamenti di sito di rete definiti nell'impostazione NCS.  <br/> |
|[Tabella EndpointSubnet](endpointsubnet.md) <br/> |Archivia la subnet dell'endpoint che partecipa a una sessione audio e video.  <br/> |
|[Tabella Server](server.md) <br/> |Archivia l'FQDN o l'indirizzo IP del server attraverso il supporto.  <br/> |
   
**Tabelle per i dati della metrica**

|**tavolo**|**Descrizione**|
|:-----|:-----|
|[Tabella AppSharingStream](appsharingstream.md) <br/> |Archivia le metriche di qualità dell'esperienza per i flussi di rete usati per la condivisione delle applicazioni. Metriche di qualità dell'esperienza per i flussi di rete usati per la condivisione delle applicazioni.  <br/> |
|[Tabella Session](session.md) <br/> |Archivia informazioni generali su una sessione audio o audio/video. Una sessione è definita come una finestra di dialogo SIP audio o video tra due endpoint.  <br/> |
|[Tabella MediaLine](medialine-0.md) <br/> |Archivia informazioni su ogni linea multimediale in una sessione. Una linea multimediale è una raccolta di uno o più flussi audio e video. In genere, una singola linea multimediale avrà due flussi, audio o video.  <br/> |
|[Tabella AudioStream](audiostream.md) <br/> |Archivia le metriche di qualità multimediale audio per ogni flusso audio nella linea multimediale.  <br/> |
|[Tabella AudioSignal](audiosignal.md) <br/> |Archivia le metriche di qualità multimediale audio nella linea multimediale. Sono incluse le metriche di annullamento dell'eco acustica (AEC) e del controllo automatico del guadagno (AGC).  <br/> |
|[Tabella VideoStream](videostream.md) <br/> |Archivia le metriche di qualità multimediale video per ogni flusso audio nella linea multimediale.  <br/> |
|[Tabella AudioClientEvent](audioclientevent.md) <br/> |Archivia le metriche di qualità multimediale audio raccolte dall'evento client.  <br/> |
|[Tabella VideoClientEvent](videoclientevent.md) <br/> |Archivia le metriche di qualità multimediale video raccolte dall'evento client.  <br/> |
|**Tabella DiagnosticData** <br/> |Archivia i dati di diagnostica solo per uso interno.  <br/> |
   
**Tabelle per i dati di riepilogo**

|**tavolo**|**Descrizione**|
|:-----|:-----|
|**Tabella ServerSummary** <br/> |Archivia i dati di riepilogo per i server, questi dati vengono utilizzati solo per i report QoE (Quality of Experience).  <br/> |
|**Tabella UserSummary** <br/> |Archivia i dati di riepilogo per gli utenti, questi dati vengono utilizzati solo per i report QoE.  <br/> |
|**Tabella CallTypeSummary** <br/> |Archiviare i dati di riepilogo per i tipi di chiamata, questi dati vengono utilizzati solo per i report QoE.  <br/> |
   
**Tabelle per l'utilizzo interno da parte di Monitoring Server**

|**tavolo**|**Descrizione**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Solo per utilizzo interno.  <br/> |
|**DbConfigInt** <br/> |Solo per utilizzo interno.  <br/> |
|**Tabella FrontEnd** <br/> |Solo per utilizzo interno.  <br/> |
|**Tabella Task** <br/> |Solo per utilizzo interno.  <br/> |
|**SummaryTableConfiguration** <br/> |Solo per utilizzo interno.  <br/> |
|**DbErrorMessage** <br/> |Solo per utilizzo interno.  <br/> |
|**MetricsThreshold** <br/> |Solo per utilizzo interno.  <br/> |
|**DaylightSavingYears** <br/> |Solo per utilizzo interno.  <br/> |
|**TimeZoneConfiguration** <br/> |Solo per utilizzo interno.  <br/> |
|**TimeZones** <br/> |Solo per utilizzo interno.  <br/> |
|**Tabella CallSummary** <br/> |Solo per uso interno.  <br/> |
|**Tabella DeviceCallSumary** <br/> |Solo per uso interno.  <br/> |
|**Tabella Tenant** <br/> |Solo per uso interno.  <br/> |
|**VideoCallSummaryTable** <br/> |Solo per uso interno.  <br/> |
|**ASCallSummaryTable** <br/> |Solo per uso interno.  <br/> |
   

