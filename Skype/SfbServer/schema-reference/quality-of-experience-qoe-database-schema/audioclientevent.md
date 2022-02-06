---
title: Tabella AudioClientEvent
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: 'Ogni record contiene un evento client per un endpoint in una chiamata audio. In genere, una chiamata ha due record, uno per il chiamante e uno per il chiamato.'
---

# <a name="audioclientevent-table"></a>Tabella AudioClientEvent
 
Ogni record contiene un evento client per un endpoint in una chiamata audio. In genere, una chiamata ha due record, uno per il chiamante e uno per il chiamato.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principale  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principale  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principale  <br/> |0: dati del chiamato  <br/> 1: Dati del chiamante  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Percentuale della sessione in cui è stato generato l'evento NetworkSendQuality per lo stato "Bad".  <br/> La qualità della rete in termini di instabilità o perdita di pacchetti è grave e influisce sulla qualità dell'audio inviato.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Percentuale della sessione in cui è stato generato l'evento ReceiveSendQuality per lo stato "Bad".  <br/> La qualità della rete in termini di instabilità o perdita di pacchetti è grave e influisce sulla qualità dell'audio ricevuto.  <br/> |
|**NetworkDelayEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Percentuale della sessione in cui è stato generato l'evento Delay per lo stato "Bad". La latenza di rete è grave e influisce sull'esperienza impedendo la comunicazione interattiva  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Percentuale della sessione in cui è stato generato l'evento LowBandwidth per lo stato "Bad". La larghezza di banda disponibile non è sufficiente per un'esperienza vocale accettabile.  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Percentuale della sessione in cui è stato generato l'evento CPU insufficiente per lo stato "Non valido". I cicli di CPU non sono sufficienti per l'elaborazione con le modalità e le applicazioni correnti in uso. Ciò causa distorsioni con il canale audio.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Percentuale della sessione in cui è stato generato l'evento DeviceHalfDuplexAEC per lo stato "Bad". Per evitare l'eco, il sistema ha inserito half duplex.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Percentuale della sessione in cui è stato generato l'evento DeviceRenderNotFunctioning per lo stato "Bad". Il dispositivo di rendering attualmente utilizzato per la sessione non funziona correttamente. Ciò può causare problemi audio unidireli.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Percentuale della sessione in cui è stato generato l'evento DeviceCaptureNotFunctioning per lo stato "Bad". Il dispositivo di acquisizione attualmente in uso per la sessione non funziona correttamente. Ciò può causare problemi audio unidireli.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Percentuale della sessione in cui è stato generato l'evento DeviceGlitches per lo stato "Bad". Il rendering dell'audio causa gravi problemi che causano distorsioni. Questi problemi possono essere causati da problemi del driver, chiamate di procedura differita (DPC) storm (driver) e utilizzo elevato della CPU.  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Percentuale della sessione in cui è stato generato l'evento DeviceLowSNR per lo stato "Bad". La qualità di acquisizione è molto scarsa, molto rumorosa o l'utente sta parlando troppo lontano dal microfono. Ciò causerà distorsioni.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Percentuale della sessione in cui è stato generato l'evento DeviceLowSpeechLevel per lo stato "Bad". Il livello di sintesi vocale dell'utente è troppo basso e il sistema non può aumentarlo ulteriormente. Ciò può causare distorsioni o essere percepito come audio unidirevi.  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal(5,2)  <br/> | <br/> |Percentuale della sessione in cui è stato generato l'evento DeviceClipping per lo stato "Bad".  <br/> Quando il riconoscimento vocale near-end ritaglia il microfono, l'estremità finale sente la distorsione dovuta al ritaglio. È importante evitare il ritaglio del microfono near-end.  <br/> |
|**DeviceEchoEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Percentuale della sessione in cui è stato generato l'evento DeviceEchoEvent per lo stato "Bad". Il dispositivo o la configurazione causa eco oltre la capacità del sistema di compensare.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimal(5,2)  <br/> | <br/> |Percentuale della sessione in cui è stato generato l'evento DeviceNearEndToEchoRatio per lo stato "Bad". La voce dell'utente è troppo bassa rispetto all'eco acquisita che influisce sull'esperienza degli utenti perché limita la facilità di interruzione di un utente. Ridurre il volume degli altoparlanti, avvicinare il microfono al relatore.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||Numero di volte in cui durante la sessione è stato generato l'evento DeviceMultipleEndpoints per lo stato "Bad". Sono stati rilevati più endpoint audio nella stessa sessione e il sistema ha compensato riducendo il volume di rendering.  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |Numero di volte in cui durante la sessione è stato generato l'evento DeviceHowlingEvent per lo stato "Bad". Rilevato loop di feedback audio (causato da più endpoint che condividono il percorso audio).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimal(5,2)  <br/> ||Percentuale della sessione in cui è stato generato l'evento DeviceRenderZeroVolume per lo stato "Bad". Il dispositivo di rendering è stato impostato su volume zero.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimal(5,2)  <br/> ||Percentuale della sessione in cui è stato generato l'evento DeviceRenderMute per lo stato "Bad". Il dispositivo di rendering è stato disattivato.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
   

