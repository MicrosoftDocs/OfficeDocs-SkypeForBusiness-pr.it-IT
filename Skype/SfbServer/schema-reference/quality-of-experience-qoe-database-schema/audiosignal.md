---
title: Tabella AudioSignal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: Ogni record rappresenta le metriche del segnale audio per un endpoint. In genere, ogni chiamata ha due record, uno è per il chiamante e uno per il chiamato.
ms.openlocfilehash: f8d617e96fe3427493bcb9e4cc70008fedae72e7
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194636"
---
# <a name="audiosignal-table"></a>Tabella AudioSignal
 
Ogni record rappresenta le metriche del segnale audio per un endpoint. In genere, ogni chiamata ha due record, uno è per il chiamante e uno per il chiamato. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |DateTime  <br/> |Principale  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principale  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |po'  <br/> |Principale  <br/> |0: dati del destinatario  <br/> 1: dati del chiamante  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |Rappresenta il livello di segnale audio per il controllo del guadagno post-analogico. L'unità per questa metrica è dBmo. Per una qualità accettabile, dovrebbe essere di almeno 30 dBmo. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |Vedere SendSignalLevel.  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |Rappresenta il livello di rumore audio del controllo di guadagno post-analogico. L'unità per questa metrica è dBmo. Per una qualità accettabile, dovrebbe essere inferiore a 35 dBmo. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |Vedere SendNoiseLevel.  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |Metrica di miglioramento della perdita di echo return. L'unità per questa metrica è dB. I valori più bassi rappresentano meno eco. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |Inconvenienti medi per cinque minuti per il rendering del diffusore. Per una buona qualità, questa operazione deve essere inferiore a uno per cinque minuti. Non segnalato da un/V Conferencing Server, Mediation Server o telefoni IP.  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |Glitch media per cinque minuti per l'acquisizione del microfono. Per una qualità ottimale, questa operazione deve essere inferiore a uno per cinque minuti. Non segnalato da un/V Conferencing Server, Mediation Server o telefoni IP.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimale (9; 2)  <br/> | <br/> |Velocità di spostamento del dispositivo microfonico, relativo all'orologio della CPU.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimale (9; 2)  <br/> | <br/> |Frequenza della velocità di spostamento del dispositivo del relatore, rispetto all'orologio della CPU.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimale (9; 2)  <br/> | <br/> |Frequenza della velocità di spostamento del dispositivo del relatore, rispetto all'orologio della CPU.  <br/> Messaggio di errore medio per l'acquisizione di un indicatore di data e ora in millisecondi negli ultimi 20 secondi della chiamata.  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimale (9; 2)  <br/> | <br/> |Messaggio di errore medio del flusso di rendering del relatore, in millisecondi, negli ultimi 20 secondi della chiamata.  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |L'opzione Voice Switch è una modalità half-duplex con un'abilità di interruzione ridotta. Cause della voce di interruttore vocale:  <br/> ENTER_VS_BADTS 0X01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0X04  <br/> ENTER_VS_DNLP 0x08  <br/> La causa può essere una combinazione di queste singole cause. ENTER_VS_FORCEORCONVERGENCE può essere abilitato solo da RegKey per scopi di test.  <br/> Il tipo di dati per questa colonna è stato modificato in Microsoft Lync Server 2013.  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |Cause di un evento Echo:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0X02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0X10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> La causa può essere una combinazione di queste singole cause.  <br/> |
|**EchoPercentMicIn** <br/> |decimale (5; 2)  <br/> | <br/> |Percentuale di tempo in cui Echo è stato rilevato nel flusso di acquisizione del microfono. In genere, i valori sono bassi per gli auricolari o i dispositivi portatili e più in alto per i telefoni con altoparlante o per gli altoparlanti autonomi. Per i dispositivi che supportano l'annullamento dell'eco acustica a bordo, i valori elevati indicano la perdita di eco. Per altri dispositivi, questa metrica non deve essere usata per valutare la qualità del dispositivo.  <br/> |
|**EchoPercentSend** <br/> |decimale (5; 2)  <br/> ||Percentuale di tempo in cui Echo viene rilevato in Stream inviato. Percentuale di eco elevata nei flussi di trasmissione un'indicazione della perdita di eco.  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |Livello di segnale ricevuto sul server Mediation dal gateway; Questo si applica solo al Mediation Server. L'unità di questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere [-30 a-18] dBoV.  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |Livello di segnale ricevuto nel server Mediation dal gateway. Questo si applica solo al Mediation Server. L'unità di questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere inferiore a-50 dBoV.  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |Controllo automatico del guadagno (AGC) sul lato Mediation Server.  <br/> |
|**InitialSignalLevelRMS** <br/> |galleggiante  <br/> | <br/> |Il quadrato medio radice (RMS) del segnale in arrivo fino ai primi 30 secondi della chiamata.  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||Livello di segnale ricevuto sul canale 1.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||Livello di segnale ricevuto sul canale 2.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||Livello di rumorosità ricevuto sul canale 1.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||Livello di rumorosità ricevuto sul canale 2.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||Livello di segnale inviato sul canale 1.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||Livello di segnale inviato sul canale 2.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||Livello di rumorosità inviato sul canale 1.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||Livello di rumorosità inviato sul canale 2.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||Livello in dBFS del segnale inviato all'altoparlante per la riproduzione. Account per eventuali rettifiche di guadagno apportate al segnale ricevuto. <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||Livello in dBFS del contenuto di rumore nel segnale inviato all'altoparlante per la riproduzione <br/> |

