---
title: Elenco delle tabelle QoE
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/13/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 176194d7-d184-4e23-94bb-cb62b4db47f5
description: Lo schema del database è costituito dalle tabelle seguenti.
ms.openlocfilehash: ba6f439d97692a40fd485a2c550da079092d7365
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194614"
---
# <a name="list-of-qoe-tables"></a>Elenco delle tabelle QoE
 
Lo schema del database è costituito dalle tabelle seguenti. 
  
**Tabelle di supporto**

|**Tabella**|**Descrizione**|
|:-----|:-----|
|[Tabella AppSharingMetricsThreshold](appsharingmetricsthreshold.md) <br/> |Consente di archiviare valori ottimali e accettabili per la qualità delle metriche di esperienza usate con la condivisione delle applicazioni.  <br/> |
|[Tabella CodecDescription](codecdescription.md) <br/> |Associa gli identificatori di codec univoci al relativo codec.  <br/> |
|[Tabella IPAddress](ipaddress.md) <br/> |Esegue il mapping degli indirizzi IP agli identificatori di indirizzi IP univoci usati altrove nel database qualità di esperienza.  <br/> |
|[Tabella NetworkConnectionDetail](networkconnectiondetail.md) <br/> |Associa i tipi di connessione di rete agli identificatori di connessione di rete usati in un altro punto del database qualità dell'esperienza.  <br/> |
|[Tabella PurgeSettings (QoE)](purgesettings-qoe.md) <br/> |Archivia le informazioni che specificano se (e quando) la qualità obsoleta dei record dell'esperienza verrà eliminata automaticamente dal database QoE.  <br/> |
|[Tabella TraceRoute](traceroute.md) <br/> |Archivia le informazioni di routing per le chiamate.  <br/> |
|[Tabella UserAgentDef (QoE)](useragentdef-qoe.md) <br/> |Associa gli identificatori dell'agente utente ai nomi descrittivi dell'agente.  <br/> |
|[Tabella VideoMetricsThreshold](videometricsthreshold.md) <br/> |Consente di archiviare valori ottimali e accettabili per la qualità delle metriche delle esperienze usate con videochiamate.  <br/> |
|[Tabella UserAgent](useragent.md) <br/> |Archivia le stringhe degli agenti utente SIP (Session Initiation Protocol) e i tipi UA usati nelle sessioni audio e video.  <br/> |
|[Tabella User](user-0.md) <br/> |Archivia gli URI dell'utente, della conferenza e del telefono usati nelle sessioni audio e video.  <br/> |
|[Tabella Endpoint](endpoint.md) <br/> |Archivia i nomi di computer FQDN degli endpoint che partecipano a sessioni audio e video.  <br/> |
|[Tabella Pool](pool.md) <br/> |Archivia i nomi dei pool a cui appartengono i dati della metrica.  <br/> |
|[Tabella Device](device.md) <br/> |Archivia i dispositivi di acquisizione e i dispositivi di rendering usati in una chiamata audio/video.  <br/> |
|[Tabella DeviceDriver](devicedriver.md) <br/> |Archivia il driver per il dispositivo di acquisizione e il dispositivo di rendering usato nelle chiamate audio/video.  <br/> |
|[Tabella Conference](conference.md) <br/> |Archivia gli URI della conferenza per gli scenari di conferenza o DialogID per altri scenari.  <br/> |
|[Tabella SessionCorrelation](sessioncorrelation.md) <br/> |Memorizza CorrelationID per le chiamate PSTN.  <br/> |
|[Tabella PayloadDescription](payloaddescription.md) <br/> |Archivia il codec usato nelle chiamate audio/video.  <br/> |
|[Tabella AppliedBandwidthSource](appliedbandwidthsource.md) <br/> |Archivia l'origine della larghezza di banda usata nelle chiamate audio/video.  <br/> |
|[Tabella MacAddress](macaddress.md) <br/> |Archivia l'indirizzo MAC degli endpoint che partecipano a sessioni audio e video.  <br/> |
|[Tabella Dialog](dialog.md) <br/> |Archivia l'ID della finestra di dialogo delle sessioni audio e video.  <br/> |
|[Tabella Region](region.md) <br/> |Archivia l'area di rete definita in impostazione NCS.  <br/> |
|[Tabella UserSite](usersite.md) <br/> |Archivia il sito di rete definito nell'impostazione NCS.  <br/> |
|[Tabella Subnet](subnet.md) <br/> |Archivia la subnet definita nell'impostazione NCS.  <br/> |
|[Tabella MonitoredRegionLink](monitoredregionlink.md) <br/> |Archivia il collegamento all'area geografica definito nell'impostazione NCS.  <br/> |
|[Tabella MonitoredUserSiteLink](monitoredusersitelink.md) <br/> |Archivia i collegamenti ai siti di rete definiti nell'impostazione NCS.  <br/> |
|[Tabella EndpointSubnet](endpointsubnet.md) <br/> |Archivia la subnet dell'endpoint che partecipa a una sessione audio e video.  <br/> |
|[Tabella Server](server.md) <br/> |Archivia il nome di dominio completo o l'indirizzo IP del server in cui passa il contenuto multimediale.  <br/> |
   
**Tabelle per i dati delle metriche**

|**Tabella**|**Descrizione**|
|:-----|:-----|
|[Tabella AppSharingStream](appsharingstream.md) <br/> |Archivia la qualità delle metriche dell'esperienza per i flussi di rete usati per la condivisione delle applicazioni. Qualità delle metriche dell'esperienza per i flussi di rete usati per la condivisione delle applicazioni.  <br/> |
|[Tabella Session](session.md) <br/> |Archivia informazioni generali su una sessione audio o audio/video. Una sessione viene definita come una finestra di dialogo SIP audio o video tra due endpoint.  <br/> |
|[Tabella MediaLine](medialine-0.md) <br/> |Archivia informazioni su ogni riga multimediale di una sessione. Una linea media è una raccolta di uno o più flussi audio e video. In genere, una singola linea multimediale avrà due flussi, audio o video.  <br/> |
|[Tabella AudioStream](audiostream.md) <br/> |Memorizza le metriche per la qualità del supporto audio per ogni flusso audio nella linea media.  <br/> |
|[Tabella AudioSignal](audiosignal.md) <br/> |Memorizza le metriche di qualità per i supporti audio nella linea media. Sono incluse le metriche per l'annullamento dell'eco acustica (AEC) e il controllo automatico del guadagno (AGC).  <br/> |
|[Tabella VideoStream](videostream.md) <br/> |Archivia le metriche di qualità multimediali video per ogni flusso audio nella linea media.  <br/> |
|[Tabella AudioClientEvent](audioclientevent.md) <br/> |Archivia le metriche di qualità del supporto audio raccolte dall'evento client.  <br/> |
|[Tabella VideoClientEvent](videoclientevent.md) <br/> |Archivia le metriche di qualità multimediali video raccolte dall'evento client.  <br/> |
|**Tabella DiagnosticData** <br/> |Archivia i dati di diagnostica solo per uso interno.  <br/> |
   
**Tabelle per i dati di riepilogo**

|**Tabella**|**Descrizione**|
|:-----|:-----|
|**Tabella ServerSummary** <br/> |Archivia i dati di riepilogo per i server, questi dati vengono usati solo per i report di qualità dell'esperienza (QoE).  <br/> |
|**Tabella UserSummary** <br/> |Archivia i dati di riepilogo per gli utenti, questi dati vengono usati solo per i report QoE.  <br/> |
|**Tabella CallTypeSummary** <br/> |Archiviare i dati di riepilogo per i tipi di chiamata, questi dati vengono usati solo per i report QoE.  <br/> |
   
**Tabelle per l'uso interno tramite Monitoring Server**

|**Tabella**|**Descrizione**|
|:-----|:-----|
|**DbConfigDateTime** <br/> |Solo per uso interno.  <br/> |
|**DbConfigInt** <br/> |Solo per uso interno.  <br/> |
|**Tabella FrontEnd** <br/> |Solo per uso interno.  <br/> |
|**Tabella delle attività** <br/> |Solo per uso interno.  <br/> |
|**SummaryTableConfiguration** <br/> |Solo per uso interno.  <br/> |
|**DbErrorMessage** <br/> |Solo per uso interno.  <br/> |
|**MetricsThreshold** <br/> |Solo per uso interno.  <br/> |
|**DaylightSavingYears** <br/> |Solo per uso interno.  <br/> |
|**TimeZoneConfiguration** <br/> |Solo per uso interno.  <br/> |
|**TimeZones** <br/> |Solo per uso interno.  <br/> |
|**Tabella CallSummary** <br/> |Solo per uso interno.  <br/> |
|**Tabella DeviceCallSumary** <br/> |Solo per uso interno.  <br/> |
|**Tabella tenant** <br/> |Solo per uso interno.  <br/> |
|**VideoCallSummaryTable** <br/> |Solo per uso interno.  <br/> |
|**ASCallSummaryTable** <br/> |Solo per uso interno.  <br/> |
   

