---
title: Tabella AudioClientEvent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fef73d8f-7261-4e5b-9769-82435b007979
description: Ogni record contiene un evento client per un endpoint in una chiamata audio. In genere, una chiamata ha due record, uno per il chiamante e uno per il chiamato.
ms.openlocfilehash: 1f754f9b7ef19919503988d40347fdeb218830d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194639"
---
# <a name="audioclientevent-table"></a>Tabella AudioClientEvent
 
Ogni record contiene un evento client per un endpoint in una chiamata audio. In genere, una chiamata ha due record, uno per il chiamante e uno per il chiamato.
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateTime  <br/> |Principale  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principale  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |po'  <br/> |Principale  <br/> |0: dati del destinatario  <br/> 1: dati del chiamante  <br/> |
|**NetworkSendQualityEventRatio** <br/> |decimale (5; 2)  <br/> | <br/> |Percentuale della sessione l'evento NetworkSendQuality è stato generato per lo stato "Bad".  <br/> La qualità della rete in termini di jitter o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio inviato.  <br/> |
|**NetworkReceiveQualityEventRatio** <br/> |decimale (5; 2)  <br/> | <br/> |Percentuale della sessione l'evento ReceiveSendQuality è stato generato per lo stato "Bad".  <br/> La qualità della rete in termini di jitter o perdita di pacchetti è grave e ha un impatto sulla qualità dell'audio ricevuto.  <br/> |
|**NetworkDelayEventRatio** <br/> |decimale (5; 2)  <br/> | <br/> |Percentuale della sessione che l'evento Delay è stato generato per lo stato "Bad". La latenza della rete è grave e ha un impatto sull'esperienza impedendo comunicazioni interattive  <br/> |
|**NetworkBandwidthLowEventRatio** <br/> |decimale (5; 2)  <br/> | <br/> |Percentuale della sessione l'evento LowBandwidth è stato generato per lo stato "Bad". La larghezza di banda disponibile è insufficiente per un'esperienza vocale accettabile.  <br/> |
|**CPUInsufficientEventRatio** <br/> |decimale (5; 2)  <br/> | <br/> |Percentuale della sessione l'evento CPU insufficiente è stato generato per lo stato "non valido". Sono disponibili cicli di CPU insufficienti per l'elaborazione con le modalità e le applicazioni correnti in uso. Ciò causa distorsioni con il canale audio.  <br/> |
|**DeviceHalfDuplexAECEventRatio** <br/> |decimale (5; 2)  <br/> | <br/> |Percentuale della sessione l'evento DeviceHalfDuplexAEC è stato generato per lo stato "Bad". Per evitare l'eco, il sistema ha immesso half duplex.  <br/> |
|**DeviceRenderNotFunctioningEventRatio** <br/> |decimale (5; 2)  <br/> | <br/> |Percentuale della sessione l'evento DeviceRenderNotFunctioning è stato generato per lo stato "Bad". Il dispositivo di rendering attualmente in uso per la sessione non funziona correttamente. Ciò può causare problemi audio unidirezionali.  <br/> |
|**DeviceCaptureNotFunctioningEventRatio** <br/> |decimale (5; 2)  <br/> | <br/> |Percentuale della sessione l'evento DeviceCaptureNotFunctioning è stato generato per lo stato "Bad". Il dispositivo di acquisizione attualmente in uso per la sessione non funziona correttamente. Ciò può causare problemi audio unidirezionali.  <br/> |
|**DeviceGlitchesEventRatio** <br/> |decimale (5; 2)  <br/> | <br/> |Percentuale della sessione l'evento DeviceGlitches è stato generato per lo stato "Bad". Il rendering dell'audio causa distorsioni è grave. Queste anomalie possono essere causate da problemi di driver, rimandi temporali (DPC), e uso elevato della CPU.  <br/> |
|**DeviceLowSNREventRatio** <br/> |decimale (5; 2)  <br/> | <br/> |Percentuale della sessione l'evento DeviceLowSNR è stato generato per lo stato "Bad". La qualità di acquisizione è molto povera, molto rumorosa o l'utente sta discutendo troppo lontano dal microfono. Questo causerà distorsioni.  <br/> |
|**DeviceLowSpeechLevelEventRatio** <br/> |decimale (5; 2)  <br/> | <br/> |Percentuale della sessione l'evento DeviceLowSpeechLevel è stato generato per lo stato "Bad". Il livello del discorso dell'utente è troppo basso e il sistema non può aumentarlo ulteriormente. Ciò può causare distorsioni o percepire l'audio unidirezionale.  <br/> |
|**DeviceClippingEventRatio** <br/> |Decimale (5; 2)  <br/> | <br/> |Percentuale della sessione l'evento DeviceClipping è stato generato per lo stato "Bad".  <br/> Quando il microfono termina con la fine del discorso, la distorsione viene pronunciata a causa del ritaglio. È importante evitare il ritaglio del microfono vicino alla fine.  <br/> |
|**DeviceEchoEventRatio** <br/> |decimale (5; 2)  <br/> | <br/> |Percentuale della sessione l'evento DeviceEchoEvent è stato generato per lo stato "Bad". Il dispositivo o la configurazione sta causando l'eco oltre la capacità del sistema di compensare.  <br/> |
|**DeviceNearEndToEchoRatioEventRatio** <br/> |decimale (5; 2)  <br/> | <br/> |Percentuale della sessione l'evento DeviceNearEndToEchoRatio è stato generato per lo stato "Bad". Il discorso dell'utente è troppo basso rispetto all'eco che viene acquisito, che ha un impatto sull'esperienza degli utenti, perché limita la facilità di interruzione di un utente. Ridurre il volume dell'altoparlante, posizionare il microfono più vicino all'oratore.  <br/> |
|**DeviceMultipleEndpointsEventCount** <br/> |int  <br/> ||Numero di volte durante la sessione l'evento DeviceMultipleEndpoints è stato generato per lo stato "Bad". Più endpoint audio nella stessa sessione rilevati e il sistema ha compensato riducendo il volume di rendering.  <br/> |
|**DeviceHowlingEventCount** <br/> |int  <br/> | <br/> |Numero di volte durante la sessione l'evento DeviceHowlingEvent è stato generato per lo stato "Bad". Loop di feedback audio rilevato (causato da più endpoint che condividono il percorso audio).  <br/> |
|**DeviceRenderZeroVolumeEventRatio** <br/> |decimale (5; 2)  <br/> ||Percentuale della sessione l'evento DeviceRenderZeroVolume è stato generato per essere nello stato "Bad". Il dispositivo di rendering è stato impostato su zero volume.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**DeviceRenderMuteEventRatio** <br/> |decimale (5; 2)  <br/> ||Percentuale della sessione l'evento DeviceRenderMute è stato generato per essere nello stato "Bad". Il dispositivo di rendering è stato disattivato.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
   

