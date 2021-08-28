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
ms.localizationpriority: medium
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: Lo schema del database è costituito dalle tabelle seguenti.
ms.openlocfilehash: 1d6d60d06dcb6cbfdde6a4fdbbd2746d00aa8531
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58601271"
---
# <a name="list-of-qoe-tables"></a>Elenco di tabelle QoE
 
Lo schema del database è costituito dalle tabelle seguenti. 
  
**Tabelle di supporto**

|**Tavolo**|**Descrizione**|
|:-----|:-----|
|[Tabella AppSharingMetricsThreshold](appsharingmetricsthreshold.md) <br/> |Archivia valori ottimali e accettabili per le metriche di qualità dell'esperienza usate con la condivisione delle applicazioni.  <br/> |
|[Tabella CodecDescription](codecdescription.md) <br/> |Mappe identificatori codec univoci al codec corrispondente.  <br/> |
|[Tabella IPAddress](ipaddress.md) <br/> |Mappe Indirizzi IP agli identificatori di indirizzi IP univoci utilizzati altrove nel database qualità dell'esperienza.  <br/> |
|[Tabella NetworkConnectionDetail](networkconnectiondetail.md) <br/> |Mappe tipi di connessione di rete agli identificatori di connessione di rete utilizzati altrove nel database qualità dell'esperienza.  <br/> |
|[Tabella PurgeSettings (QoE)](purgesettings-qoe.md) <br/> |Archivia le informazioni che specificano se e quando i record di qualità dell'esperienza non aggiornati verranno eliminati automaticamente dal database QoE.  <br/> |
|[Tabella TraceRoute](traceroute.md) <br/> |Archivia le informazioni di routing per le chiamate.  <br/> |
|[Tabella UserAgentDef (QoE)](useragentdef-qoe.md) <br/> |Mappe degli agenti utente ai nomi descrittivi dell'agente.  <br/> |
|[Tabella VideoMetricsThreshold](videometricsthreshold.md) <br/> |Archivia valori ottimali e accettabili per le metriche di qualità dell'esperienza usate con le videochiamate.  <br/> |
|[Tabella UserAgent](useragent.md) <br/> |Archivia le stringhe dell'agente utente SIP (Session Initiation Protocol) e i tipi UA utilizzati nelle sessioni audio e video.  <br/> |
|[Tabella utente](user-0.md) <br/> |Archivia gli URI di utenti, conferenze e telefonici utilizzati nelle sessioni audio e video.  <br/> |
|[Tabella endpoint](endpoint.md) <br/> |Archivia i nomi di computer FQDN degli endpoint che partecipano a sessioni audio e video.  <br/> |
|[Tabella Pool](pool.md) <br/> |Archivia i nomi dei pool a cui appartengono i dati delle metriche.  <br/> |
|[Tabella dei dispositivi](device.md) <br/> |Archivia i dispositivi di acquisizione e i dispositivi di rendering usati in chiamate audio/video.  <br/> |
|[Tabella DeviceDriver](devicedriver.md) <br/> |Archivia il driver per il dispositivo di acquisizione e il dispositivo di rendering usati nelle chiamate audio/video.  <br/> |
|[Tabella Conferenze](conference.md) <br/> |Archivia gli URI conferenza per gli scenari di conferenza o DialogID per altri scenari.  <br/> |
|[Tabella SessionCorrelation](sessioncorrelation.md) <br/> |Archivia CorrelationID per le chiamate PSTN.  <br/> |
|[Tabella PayloadDescription](payloaddescription.md) <br/> |Archivia il codec utilizzato nelle chiamate audio/video.  <br/> |
|[Tabella AppliedBandwidthSource](appliedbandwidthsource.md) <br/> |Archivia l'origine della larghezza di banda utilizzata nelle chiamate audio/video.  <br/> |
|[Tabella MacAddress](macaddress.md) <br/> |Archivia l'indirizzo MAC degli endpoint che partecipano a sessioni audio e video.  <br/> |
|[Tabella Dialog](dialog.md) <br/> |Archivia l'ID finestra di dialogo delle sessioni audio e video.  <br/> |
|[Tabella Region](region.md) <br/> |Archivia l'area di rete definita nell'impostazione NCS.  <br/> |
|[Tabella UserSite](usersite.md) <br/> |Archivia il sito di rete definito nell'impostazione NCS.  <br/> |
|[Tabella Subnet](subnet.md) <br/> |Archivia la subnet definita nell'impostazione NCS.  <br/> |
|[Tabella MonitoredRegionLink](monitoredregionlink.md) <br/> |Archivia il collegamento area definito nell'impostazione NCS.  <br/> |
|[Tabella MonitoredUserSiteLink](monitoredusersitelink.md) <br/> |Archivia i collegamenti di sito di rete definiti nell'impostazione NCS.  <br/> |
|[Tabella EndpointSubnet](endpointsubnet.md) <br/> |Archivia la subnet dell'endpoint che partecipa a una sessione audio e video.  <br/> |
|[Tabella Server](server.md) <br/> |Archivia il nome di dominio completo o l'indirizzo IP del server attraverso il supporto.  <br/> |
   
**Tabelle per i dati delle metriche**

|**Tavolo**|**Descrizione**|
|:-----|:-----|
|[Tabella AppSharingStream](appsharingstream.md) <br/> |Archivia le metriche di qualità dell'esperienza per i flussi di rete usati per la condivisione delle applicazioni. Metriche di qualità dell'esperienza per i flussi di rete usati per la condivisione delle applicazioni.  <br/> |
|[Tabella session](session.md) <br/> |Archivia le informazioni generali su una sessione audio o audio/video. Una sessione è definita come una finestra di dialogo SIP audio o video tra due endpoint.  <br/> |
|[Tabella MediaLine](medialine-0.md) <br/> |Archivia le informazioni su ogni linea multimediale in una sessione. Una linea multimediale è una raccolta di uno o più flussi audio e video. In genere, una singola linea multimediale avrà due flussi, audio o video.  <br/> |
|[Tabella AudioStream](audiostream.md) <br/> |Archivia le metriche di qualità multimediale audio per ogni flusso audio nella linea multimediale.  <br/> |
|[Tabella AudioSignal](audiosignal.md) <br/> |Archivia le metriche di qualità multimediale audio nella linea multimediale. Sono incluse le metriche di annullamento dell'eco acustico (AEC) e di controllo automatico del guadagno (AGC).  <br/> |
|[Tabella VideoStream](videostream.md) <br/> |Archivia le metriche di qualità multimediale video per ogni flusso audio nella linea multimediale.  <br/> |
|[Tabella AudioClientEvent](audioclientevent.md) <br/> |Archivia le metriche di qualità multimediale audio raccolte dall'evento client.  <br/> |
|[Tabella VideoClientEvent](videoclientevent.md) <br/> |Archivia le metriche di qualità multimediale video raccolte dall'evento client.  <br/> |
|**Tabella DiagnosticData** <br/> |Archivia i dati di diagnostica solo per uso interno.  <br/> |
   
**Tabelle per i dati di riepilogo**

|**Tavolo**|**Descrizione**|
|:-----|:-----|
|**Tabella ServerSummary** <br/> |Archivia i dati di riepilogo per i server, questi dati vengono utilizzati solo per la creazione di report QoE( Quality of Experience).  <br/> |
|**Tabella UserSummary** <br/> |Archivia i dati di riepilogo per gli utenti, questi dati vengono utilizzati solo per i report QoE.  <br/> |
|**Tabella CallTypeSummary** <br/> |Archiviare i dati di riepilogo per i tipi di chiamata, questi dati vengono utilizzati solo per i report QoE.  <br/> |
   
**Tabelle per l'utilizzo interno da parte di Monitoring Server**

|**Tavolo**|**Descrizione**|
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
   

