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
description: Ogni record rappresenta le metriche del segnale audio per un endpoint. In genere, ogni chiamata ha due record, uno per il chiamante e uno per il chiamato.
ms.openlocfilehash: 36ece4a9481400c3fae9e248d00cc59f3ec161b21aa03d8e824fc4d21931d04f
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54309205"
---
# <a name="audiosignal-table"></a>Tabella AudioSignal
 
Ogni record rappresenta le metriche del segnale audio per un endpoint. In genere, ogni chiamata ha due record, uno per il chiamante e uno per il chiamato. 
  
|**Colonna**|**Tipo di dati**|**Chiave/indice**|**Dettagli**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Principale  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Principale  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Principale  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Principale  <br/> |0: dati del chiamato  <br/> 1: Dati del chiamante  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |Rappresenta il livello del segnale audio Post-Analog Gain Control. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |Vedere SendSignalLevel.  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |Rappresenta il livello di rumore audio Post-Analog Gain Control. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |Vedere SendNoiseLevel.  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |Metrica Echo Return Loss Enhancement. L'unità di misura per questa metrica è dB. I valori più bassi rappresentano un'eco minore. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |Numero medio di problemi per cinque minuti per il rendering dell'altoparlante. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |Numero medio di problemi per cinque minuti per l'acquisizione del microfono. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal(9,2)  <br/> | <br/> |Frequenza di deriva del clock del dispositivo microfono, rispetto al clock della CPU.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal(9,2)  <br/> | <br/> |Frequenza di deriva del clock del dispositivo altoparlante, rispetto al clock della CPU.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal(9,2)  <br/> | <br/> |Frequenza di deriva del clock del dispositivo altoparlante, rispetto al clock della CPU.  <br/> Media di errore del timestamp, in millisecondi, del flusso di acquisizione del microfono negli ultimi 20 secondi della chiamata.  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal(9,2)  <br/> | <br/> |Errore di timestamp medio del flusso di rendering dell'altoparlante, in millisecondi, negli ultimi 20 secondi della chiamata.  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |La commutazione vocale è una modalità half-duplex con possibilità di interruzione ridotta. Cause della voce del commutatore vocale:  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> La causa può essere una combinazione di queste singole cause. ENTER_VS_FORCEORCONVERGENCE può essere abilitato solo da regkey a scopo di test.  <br/> Il tipo di dati per questa colonna è stato modificato in Microsoft Lync Server 2013.  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |Cause di un evento eco:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> La causa può essere una combinazione di queste singole cause.  <br/> |
|**EchoPercentMicIn** <br/> |decimal(5,2)  <br/> | <br/> |Percentuale di tempo in cui è stata rilevata l'eco nel flusso di acquisizione del microfono. In genere, i valori sono bassi per cuffie o ricevitori e superiori per i telefoni degli altoparlanti o gli altoparlanti autonomi. Per i dispositivi che supportano l'annullamento dell'eco acustico a bordo, valori elevati indicano una perdita di eco. Per altri dispositivi, questa metrica non deve essere usata per valutare la qualità del dispositivo.  <br/> |
|**EchoPercentSend** <br/> |decimal(5,2)  <br/> ||Percentuale di tempo in cui viene rilevato l'eco nel flusso inviato. Un'elevata percentuale di eco nei flussi di invio è un'indicazione della perdita di eco.  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |Livello del segnale ricevuto nel Mediation Server dal gateway. ciò si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere [-30 a -18] dBoV.  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |Livello di segnale ricevuto nel Mediation Server dal gateway. Si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, il valore accettabile deve essere inferiore a -50 dBoV.  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |Controllo automatico del guadagno (AGC) sul lato Mediation Server.  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |Il quadrato della media radice (RMS) del segnale in arrivo fino ai primi 30 secondi della chiamata.  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||Livello del segnale ricevuto sul canale 1.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||Livello del segnale ricevuto sul canale 2.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||Livello di rumore ricevuto sul canale 1.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||Livello di rumore ricevuto sul canale 2.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||Livello del segnale inviato sul canale 1.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||Livello del segnale inviato sul canale 2.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||Livello di rumore inviato sul canale 1.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||Livello di rumore inviato sul canale 2.  <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||Livello in dBFS del segnale inviato all'altoparlante per la riproduzione. Rappresenta le eventuali rettifiche di guadagno apportate al segnale ricevuto. <br/> Questa colonna è stata introdotta in Microsoft Lync Server 2013.  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||Livello in dBFS del contenuto di rumore nel segnale inviato all'altoparlante per la riproduzione <br/> |

