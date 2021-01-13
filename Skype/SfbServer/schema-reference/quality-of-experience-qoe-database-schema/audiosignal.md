---
title: Tabella AudioSignal
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
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: Ogni record rappresenta la metrica del segnale audio per un endpoint. In genere, ogni chiamata ha due record, uno è per il chiamante e uno è per il destinatario della chiamata.
ms.openlocfilehash: ab918941357b85c6bcb25dcbaeb93a7be9c55f2d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809656"
---
# <a name="audiosignal-table"></a>Tabella AudioSignal
 
Ogni record rappresenta la metrica del segnale audio per un endpoint. In genere, ogni chiamata ha due record, uno è per il chiamante e uno è per il destinatario della chiamata. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principale  <br/> |Riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |Riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principale  <br/> |Riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |po'  <br/> |Principale  <br/> |0: dati del destinatario della chiamata  <br/> 1: dati del chiamante  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |Rappresenta il livello di segnale audio post-analogico di controllo del guadagno. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |Vedere SendSignalLevel.  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |Rappresenta il livello di rumore del controllo di guadagno post-analogico. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |Vedere SendNoiseLevel.  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |Metrica di miglioramento della perdita di rendimento eco. L'unità di misura per questa metrica è dB. I valori più bassi rappresentano un'eco minore. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |Glitch medi per cinque minuti per il rendering degli altoparlanti. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |Glitch media per cinque minuti per l'acquisizione del microfono. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimale (9, 2)  <br/> | <br/> |Velocità della deriva del clock del dispositivo microfono rispetto al clock della CPU.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimale (9, 2)  <br/> | <br/> |Velocità della deriva del dispositivo di altoparlanti, rispetto al clock della CPU.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimale (9, 2)  <br/> | <br/> |Velocità della deriva del dispositivo di altoparlanti, rispetto al clock della CPU.  <br/> Media di errore del timestamp, in millisecondi, del flusso di acquisizione del microfono negli ultimi 20 secondi della chiamata.  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimale (9, 2)  <br/> | <br/> |Errore medio del timestamp del flusso di rendering dell'altoparlante, in millisecondi, negli ultimi 20 secondi della chiamata.  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |La commutazione vocale è una modalità half-duplex con possibilità di interruzione ridotta. Cause della voce del commutatore vocale:  <br/> ENTER_VS_BADTS 0X01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0X04  <br/> ENTER_VS_DNLP 0x08  <br/> La causa può essere una combinazione di queste singole cause. ENTER_VS_FORCEORCONVERGENCE può essere abilitato solo da RegKey a scopo di test.  <br/> Il tipo di dati per questa colonna è stato modificato in Microsoft Lync Server 2013.  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |Cause di un evento Echo:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0X02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0X10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> La causa può essere una combinazione di queste singole cause.  <br/> |
|**EchoPercentMicIn** <br/> |Decimal (5, 2)  <br/> | <br/> |Percentuale del tempo in cui è stata rilevata eco nel flusso di acquisizione del microfono. In genere, i valori sono bassi per gli auricolari o i telefoni e sono più alti per i telefoni speaker o per gli altoparlanti autonomi. Per i dispositivi che supportano l'annullamento dell'eco acustica di bordo, i valori elevati indicano una perdita di eco. Per gli altri dispositivi, questa metrica non deve essere utilizzata per valutare la qualità del dispositivo.  <br/> |
|**EchoPercentSend** <br/> |Decimal (5, 2)  <br/> ||Percentuale di tempo in cui l'eco viene rilevata nel flusso inviato. Un'elevata percentuale di eco nei flussi di invio è un'indicazione della perdita di eco.  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |Livello di segnale ricevuto sul Mediation Server dal gateway. Questo è valido solo per il Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile dovrebbe essere [-30 a-18] dBoV.  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |Livello di segnale ricevuto sul Mediation Server dal gateway. Si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, il valore accettabile deve essere inferiore a -50 dBoV.  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |Controllo di guadagno automatico (AGC) sul server di Mediation Side.  <br/> |
|**InitialSignalLevelRMS** <br/> |galleggiante  <br/> | <br/> |Il quadrato medio radice (RMS) del segnale in ingresso fino ai primi 30 secondi della chiamata.  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||Livello di segnale ricevuto sul canale 1.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||Livello di segnale ricevuto sul canale 2.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||Livello di rumore ricevuto sul canale 1.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||Livello di rumore ricevuto sul canale 2.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||Livello di segnale inviato sul canale 1.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||Livello di segnale inviato sul canale 2.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||Livello di rumore inviato sul canale 1.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||Livello di rumore inviato sul canale 2.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||Livello in dBFS del segnale inviato all'altoparlante per la riproduzione. Gli account per eventuali rettifiche di guadagno apportate al segnale ricevuto. <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||Livello in dBFS del contenuto del rumore nel segnale inviato all'altoparlante per la riproduzione <br/> |

