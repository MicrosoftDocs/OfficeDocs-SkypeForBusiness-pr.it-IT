---
title: Tabella AudioClientEvent
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
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: Ogni record contiene un evento client per un endpoint in una chiamata audio. In genere, una chiamata ha due record, uno per il chiamante e uno per il destinatario della chiamata.
ms.openlocfilehash: f5211d7f4ec3bc1d366d97def06edd325c448def
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809686"
---
# <a name="audioclientevent-table"></a>Tabella AudioClientEvent
 
Ogni record contiene un evento client per un endpoint in una chiamata audio. In genere, una chiamata ha due record, uno per il chiamante e uno per il destinatario della chiamata.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principale  <br/> |Riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |Riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principale  <br/> |Riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |po'  <br/> |Principale  <br/> |0: dati del destinatario della chiamata  <br/> 1: dati del chiamante  <br/> |
|**NetworkSendQualityEventRatio** <br/> |Decimal (5, 2)  <br/> | <br/> |Percentuale di sessione l'evento NetworkSendQuality è stato generato per lo stato ' Bad '.  <br/> La qualità della rete in termini di instabilità o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio inviato.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |Decimal (5, 2)  <br/> | <br/> |Percentuale di sessione l'evento l'ReceiveSendQuality è stato generato per lo stato ' Bad '.  <br/> La qualità della rete in termini di instabilità o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio ricevuto.  <br/> |
|**NetworkDelayEventRatio** <br/> |Decimal (5, 2)  <br/> | <br/> |Percentuale di sessione l'evento Delay è stato generato per lo stato ' Bad '. La latenza della rete è grave e influisce sull'esperienza impedendo le comunicazioni interattive  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |Decimal (5, 2)  <br/> | <br/> |Percentuale di sessione l'evento LowBandwidth è stato generato per lo stato ' Bad '. La larghezza di banda disponibile non è sufficiente per un'esperienza vocale accettabile.  <br/> |
|**CPUInsufficientEventRatio** <br/> |Decimal (5, 2)  <br/> | <br/> |Percentuale di sessione l'evento CPU insufficiente è stato generato per lo stato ' Bad '. Non sono disponibili cicli di CPU insufficienti per l'elaborazione con le modalità correnti e le applicazioni in uso. In questo modo le distorsioni vengono causate dal canale audio.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |Decimal (5, 2)  <br/> | <br/> |Percentuale di sessione l'evento DeviceHalfDuplexAEC è stato generato per lo stato ' Bad '. Al fine di prevenire l'eco, il sistema ha immesso half duplex.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |Decimal (5, 2)  <br/> | <br/> |Percentuale di sessione l'evento DeviceRenderNotFunctioning è stato generato per lo stato ' Bad '. Il dispositivo di rendering attualmente utilizzato per la sessione non funziona correttamente. Ciò può causare problemi di tipo audio unidirezionale.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |Decimal (5, 2)  <br/> | <br/> |Percentuale di sessione l'evento DeviceCaptureNotFunctioning è stato generato per lo stato ' Bad '. Il dispositivo di acquisizione attualmente utilizzato per la sessione non funziona correttamente. Ciò può causare problemi di tipo audio unidirezionale.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |Decimal (5, 2)  <br/> | <br/> |Percentuale di sessione l'evento DeviceGlitches è stato generato per lo stato ' Bad '. Vi sono gravi problemi di rendering dell'audio che causano distorsioni. Questi difetti possono essere causati da problemi relativi ai driver, dalla tempesta di chiamate di routine posticipate (DPC) e dall'elevato utilizzo della CPU.  <br/> |
|**DeviceLowSNREventRatio** <br/> |Decimal (5, 2)  <br/> | <br/> |Percentuale di sessione l'evento DeviceLowSNR è stato generato per lo stato ' Bad '. La qualità di acquisizione è molto scarsa, sia molto rumoroso o l'utente sta parlando troppo lontano dal microfono. Ciò provocherà distorsioni.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |Decimal (5, 2)  <br/> | <br/> |Percentuale di sessione l'evento DeviceLowSpeechLevel è stato generato per lo stato ' Bad '. Il livello di sintesi vocale dell'utente è troppo basso e il sistema non può aumentare ulteriormente. Questo può causare distorsioni o percepito come un audio unidirezionale.  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimal (5, 2)  <br/> | <br/> |Percentuale di sessione l'evento DeviceClipping è stato generato per lo stato ' Bad '.  <br/> Quando il microfono viene ritagliato da un punto di vista intermedio, la distorsione di fine-estremità si sente a causa del clipping. È importante evitare il clipping del microfono near-end.  <br/> |
|**DeviceEchoEventRatio** <br/> |Decimal (5, 2)  <br/> | <br/> |Percentuale di sessione l'evento cui è stato generato per lo stato ' Bad '. Il dispositivo o il programma di installazione stanno causando l'eco oltre la capacità del sistema di compensare.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |Decimal (5, 2)  <br/> | <br/> |Percentuale di sessione l'evento DeviceNearEndToEchoRatio è stato generato per lo stato ' Bad '. La voce dell'utente è troppo bassa rispetto all'acquisizione dell'eco che influisce sull'esperienza degli utenti, in quanto limita la facilità di interruzione di un utente. Ridurre il volume degli altoparlanti, spostare il microfono più vicino all'oratore.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||Numero di volte durante la sessione in cui è stato generato l'evento DeviceMultipleEndpoints per lo stato ' Bad '. Sono stati rilevati più endpoint audio nella stessa sessione e il sistema ha compensato la riduzione del volume di rendering.  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |Numero di volte durante la sessione in cui è stato generato l'evento DeviceHowlingEvent per lo stato ' Bad '. Ciclo di commenti e suggerimenti audio rilevato (causato da più endpoint che condividono il percorso audio).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |Decimal (5, 2)  <br/> ||Percentuale di sessione l'evento DeviceRenderZeroVolume è stato generato per essere nello stato "Bad". Il dispositivo di rendering è stato impostato su zero volume.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |Decimal (5, 2)  <br/> ||Percentuale di sessione l'evento DeviceRenderMute è stato generato per essere nello stato "Bad". La periferica di rendering è stata disattivata.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
   

