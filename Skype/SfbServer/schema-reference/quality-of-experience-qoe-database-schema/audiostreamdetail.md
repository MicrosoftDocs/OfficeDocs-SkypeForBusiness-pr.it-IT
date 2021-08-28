---
title: Visualizzazione AudioStreamDetail
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: Nella visualizzazione AudioStreamDetail vengono archiviate le informazioni relative a ogni flusso audio nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: fa3d65c5c4f42bb0ecfe32447b9d8dcab5a10c55
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58583750"
---
# <a name="audiostreamdetail-view"></a>Visualizzazione AudioStreamDetail
 
Nella visualizzazione AudioStreamDetail vengono archiviate le informazioni relative a ogni flusso audio nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |ID univoco in una linea multimediale.  <br/> |
|StartTime  <br/> |datetime  <br/> |Data e ora di inizio della sessione.  <br/> |
|EndTime  <br/> |datetime  <br/> |Data e ora di fine della sessione.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Categoria finestra di dialogo: 0 è il Skype for Business Server a Mediation Server. 1 è il passaggio da Mediation Server a gateway PSTN.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Flag che indica se la chiamata è stata o meno ignorata.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Se presente, indica il motivo per cui una chiamata non è stata ignorata anche in caso di corrispondenza degli ID bypass. Viene definito un solo valore:  <br/> 0x0001 - ID bypass sconosciuto per la scheda di rete predefinita.  <br/> |
|CallPriority  <br/> |int  <br/> |Priorità della chiamata.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN del pool del chiamante.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN del pool del destinatario della chiamata.  <br/> |
|Chiamante  <br/> |nvarchar(450)  <br/> |URI del chiamante.  <br/> |
|Chiamato  <br/> |nvarchar(450)  <br/> |URI del chiamato.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Stringa agente utente del chiamante.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo dell'agente utente del chiamante. Per informazioni [dettagliate, vedere](useragent.md) la tabella UserAgent. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar(64)  <br/> |Categoria dell'agente utente del chiamante. Per informazioni [dettagliate, vedere la tabella UserAgentDef (QoE).](useragentdef-qoe.md) <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Stringa agente utente del chiamato.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo di agente utente del chiamato. Per [informazioni, vedere la tabella UserAgent.](useragent.md) <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar(64)  <br/> |Categoria dell'agente utente del chiamato. Per [informazioni, vedere la tabella UserAgentDef (QoE).](useragentdef-qoe.md) <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nome dell'endpoint del chiamante.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nome dell'endpoint del chiamato.  <br/> |
|CallerOS  <br/> |nvarchar(128)  <br/> |Sistema operativo dell'endpoint del chiamante.  <br/> |
|CalleeOS  <br/> |nvarchar(128)  <br/> |Sistema operativo dell'endpoint del chiamato.  <br/> |
|CallerCPUName  <br/> |nvarchar(128)  <br/> |Nome CPU dell'endpoint del chiamante.  <br/> |
|CalleeCPUName  <br/> |nvarchar(128)  <br/> |Nome CPU dell'endpoint del chiamato.  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Numero di core della CPU nell'endpoint del chiamante.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Numero di core della CPU nell'endpoint del chiamato.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Velocità del processore della CPU dell'endpoint del chiamante.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Velocità del processore della CPU dell'endpoint del chiamato.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indica se il sistema del chiamante è in esecuzione in un ambiente virtualizzato. Per ulteriori [informazioni, vedere](endpoint.md) la tabella Endpoint. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indica se il sistema del chiamato è in esecuzione in un ambiente virtualizzato. Per ulteriori [informazioni, vedere](endpoint.md) la tabella Endpoint. <br/> |
|CorrelationKey  <br/> ||Chiave di correlazione. Riferimento dalla [tabella SessionCorrelation](sessioncorrelation.md).  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informazioni sul percorso multimediale, ad esempio diretto o inoltrato. Per ulteriori informazioni, vedi la tabella [MediaLine.](medialine-0.md) <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il chiamante. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il destinatario della chiamata. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.  <br/> |
|Trasporto  <br/> |tinyint  <br/> |Tipo di trasporto: 0 è UDP e 1 è TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Indirizzo IP del chiamante. Può essere un indirizzo IPv4 o IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Porta utilizzata dal chiamante.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica se il chiamante è nella rete interna: 1 indica che il chiamante è all'interno della rete aziendale e 0 indica che il chiamante è all'esterno della rete.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Indirizzo IP del destinatario della chiamata. Può essere un indirizzo IPv4 o IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Porta utilizzata dal destinatario della chiamata.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica se il destinatario della chiamata è nella rete interna: 1 indica che il destinatario della chiamata è all'interno della rete aziendale e 0 indica che il destinatario della chiamata è all'esterno della rete.  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |Nome del sito del chiamante.  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |Nome del paese/area geografica del sito del chiamante.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |Nome del sito del chiamato.  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |Nome del paese/area geografica del sito del chiamato.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Indirizzo IP del servizio A/V Edge utilizzato dal chiamante. Per ulteriori informazioni, vedere la tabella [IPAddress.](ipaddress.md) <br/> |
|CallerRelayPort  <br/> |int  <br/> |Porta utilizzata nel servizio A/V Edge utilizzato dal chiamante.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Codice indirizzo IP del servizio A/V Edge utilizzato dal destinatario della chiamata. Per ulteriori informazioni, vedere la tabella [IPAddress.](ipaddress.md) <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta utilizzata nel servizio A/V Edge utilizzato dal destinatario della chiamata.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nome del dispositivo di acquisizione del chiamante.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nome del dispositivo di rendering del chiamante.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nome del driver del dispositivo di acquisizione del chiamante.  <br/> |
|CallerRenderDriver  <br/> |varchar(256)  <br/> |Nome del driver del dispositivo di rendering del chiamante.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |Nome del dispositivo di acquisizione del chiamato.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nome del dispositivo di rendering del chiamato.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |Nome del driver del dispositivo di acquisizione del chiamato.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nome del driver del dispositivo di rendering del chiamato.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Tipo di connessione di rete del chiamante: 0 è cablato, 1 è wireless.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica se il chiamante si è connesso tramite una rete VPN: 1 indica una rete VPN e 0 indica una rete non VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,0)  <br/> |Velocità del collegamento di rete, in bps, per l'endpoint del chiamante.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Tipo di connessione di rete del chiamato: 0 è cablato, 1 è wireless.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica se il chiamante si è connesso tramite una rete VPN: 1 indica una rete VPN e 0 indica una rete non VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |Velocità del collegamento di rete, in bps, per l'endpoint del destinatario della chiamata.  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |Conversational MOS a banda stretta delle sessioni audio (basato su entrambi i flussi audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Larghezza di banda effettivamente applicata al flusso sul lato dell'invio secondo diverse impostazioni di criteri (TURN, API, SDP, server dei criteri e così via). Da non confondere con la larghezza di banda effettiva, perché può esistere una larghezza di banda effettiva inferiore basata sulla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che può essere utilizzata dal flusso di invio escludendo i limiti imposti dalla stima della larghezza di banda.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Instabilità di rete massima durante la chiamata.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |Frequenza media di perdita di pacchetti durante la chiamata.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |Perdita di pacchetti massima rilevata durante la chiamata.  <br/> |
|BurstDensity  <br/> |decimal(9,4)  <br/> |Densità media della perdita di pacchetti durante burst di perdite durante la chiamata.  <br/> |
|BurstDuration  <br/> |int  <br/> |Durata media della perdita di pacchetti durante burst di perdite durante la chiamata.  <br/> |
|BurstGapDensity  <br/> |decimal(9,4)  <br/> |Densità media della perdita di pacchetti durante le pause tra burst della perdita di pacchetti.  <br/> |
|BurstGapDuration  <br/> |int  <br/> |Durata media delle pause tra burst della perdita di pacchetti.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Numero di pacchetti per il flusso audio.  <br/> |
|BandwidthEst  <br/> |int  <br/> |Stime della larghezza di banda per il flusso audio.  <br/> |
|DegradationAvg  <br/> |decimal(3,2)  <br/> |Degradazione MOS di rete per l'intera chiamata. L'intervallo è compreso tra 0,0 e 5,0. Questa metrica indica la quantità di MOS di rete ridotta a causa della dispersione e della perdita di pacchetti. Per un livello di qualità accettabile, questo valore deve essere minore di 0,5.  <br/> |
|DegradationMax  <br/> |decimal(3,2)  <br/> |Degradazione MOS di rete massima durante la chiamata.  <br/> |
|DegradationJitterAvg  <br/> |decimal(3,2)  <br/> |Degradazione MOS di rete causata dall'instabilità.  <br/> |
|DegradationPacketLossAvg  <br/> |decimal(3,2)  <br/> |Degradazione MOS di rete causata dalla perdita di pacchetti.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Codec audio utilizzato per la chiamata, a cui viene fatto riferimento dalla [tabella PayloadDescription.](payloaddescription.md)  <br/> |
|AudioSampleRate  <br/> |int  <br/> |Frequenza di campionamento per il flusso audio.  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |Livello di segnale audio dopo il controllo guadagno analogico per l'audio inviato dal chiamante. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |Livello di segnale audio per l'audio ricevuto dal chiamante. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |Livello di disturbo audio dopo il controllo guadagno analogico per l'audio inviato dal chiamante. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |Livello di disturbo audio dopo il controllo guadagno analogico per l'audio ricevuto dal chiamante. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |ERLE (Echo Return Loss Enhancement) per il chiamante. L'unità di misura per questa metrica è dB. I valori più bassi rappresentano un'eco minore. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |Media di problemi ogni cinque minuti per il rendering dell'altoparlante del chiamante. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |Numero medio di problemi per cinque minuti per l'acquisizione del microfono del chiamante. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.  <br/> |
|CallerTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |Frequenza di deriva del clock del dispositivo microfono del chiamante, rispetto al clock della CPU.  <br/> |
|CallerTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |Frequenza di deriva del clock del dispositivo altoparlante del chiamante, rispetto al clock della CPU.  <br/> |
|CallerTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |Media di errore del timestamp, in millisecondi, del flusso di acquisizione del microfono negli ultimi 20 secondi della chiamata.  <br/> |
|CallerTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |Media dell'errore di timestamp del flusso di rendering dell'altoparlante del chiamante, in millisecondi, negli ultimi 20 secondi della chiamata.  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |La commutazione vocale è una modalità half-duplex con possibilità di interruzione ridotta. Per ulteriori informazioni, vedi la tabella [MediaLine.](medialine-0.md) <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |Cause di un evento di eco per il chiamante. Per ulteriori informazioni, vedi la tabella [MediaLine.](medialine-0.md) <br/> |
|CallerEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |Percentuale di tempo in cui viene rilevata l'eco nel flusso di acquisizione del microfono del chiamante. Se viene utilizzato un auricolare, il valore deve essere basso.  <br/> |
|CallerEchoPercentSend  <br/> |decimal(5,2)  <br/> |Percentuale di tempo in cui viene rilevato l'eco nel flusso inviato del chiamante. Un'elevata percentuale di eco nei flussi di invio è un'indicazione della perdita di eco.  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |Livello del segnale ricevuto nel Mediation Server dal gateway per l'audio del chiamante; ciò si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere compreso tra -30 e -18 dBoV.  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |Livello di segnale ricevuto nel Mediation Server dal gateway per l'audio del chiamante. Si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, il valore accettabile deve essere inferiore a -50 dBoV.  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |Controllo automatico dei guadagni (AGC) sul lato Mediation Server applicato all'audio del chiamante.  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |Radice della media dei quadrati del segnale in ingresso per il chiamante fino ai primi 30 secondi della chiamata.  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |Rappresenta il livello di segnale audio dopo il controllo guadagno analogico per l'audio inviato dal destinatario della chiamata. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |Livello di segnale audio per l'audio ricevuto dal destinatario della chiamata. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |Livello di disturbo audio dopo il controllo guadagno analogico per l'audio inviato dal destinatario della chiamata. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |Livello di disturbo audio dopo il controllo guadagno analogico per l'audio ricevuto dal destinatario della chiamata. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |ERLE (Echo Return Loss Enhancement) per il destinatario della chiamata. L'unità di misura per questa metrica è dB. I valori più bassi rappresentano un'eco minore. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |Numero medio di problemi ogni cinque minuti per il rendering dell'altoparlante del chiamato. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |Numero medio di problemi ogni cinque minuti per l'acquisizione del microfono del chiamato. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.  <br/> |
|CalleeTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |Frequenza di deriva del clock del dispositivo microfono del chiamato, rispetto al clock della CPU.  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |Frequenza di deriva del clock del dispositivo altoparlante del chiamato, rispetto al clock della CPU.  <br/> |
|CalleeTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |Media di errore del timestamp, in millisecondi, del flusso di acquisizione del microfono negli ultimi 20 secondi della chiamata.  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |Media dell'errore di timestamp del flusso di rendering dell'altoparlante del chiamato, in millisecondi, negli ultimi 20 secondi della chiamata.  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |La commutazione vocale è una modalità half-duplex con possibilità di interruzione ridotta. Per ulteriori informazioni, vedi la tabella [MediaLine.](medialine-0.md) <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |Cause di un evento di eco per il destinatario della chiamata. Per ulteriori informazioni, vedi la tabella [MediaLine.](medialine-0.md) <br/> |
|CalleeEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |Percentuale di tempo in cui viene rilevata l'eco nel flusso di acquisizione del microfono del chiamato. Se viene utilizzato un auricolare, il valore deve essere basso.  <br/> |
|CalleeEchoPercentSend  <br/> |decimal(5,2)  <br/> |Percentuale di tempo in cui viene rilevato l'eco nel flusso inviato del chiamato. Un'elevata percentuale di eco nei flussi di invio è un'indicazione della perdita di eco.  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |Livello del segnale ricevuto nel Mediation Server dal gateway per l'audio del chiamato; ciò si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere compreso tra [-30 e -18] dBoV.  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |Livello di segnale ricevuto nel Mediation Server dal gateway per l'audio del chiamato. Si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, il valore accettabile deve essere inferiore a -50 dBoV.  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |Controllo automatico del guadagno (AGC) sul lato Mediation Server applicato all'audio del chiamato.  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |Radice della media dei quadrati del segnale in ingresso per il destinatario della chiamata fino ai primi 30 secondi della chiamata.  <br/> |
|RatioConcealedSamplesAvg  <br/> |decimal(5,2)  <br/> |Rapporto medio tra i campioni nascosti risultanti dalla correzione audio e i campioni tipici.  <br/> |
|RatioStretchedSamplesAvg  <br/> |decimal(5,2)  <br/> |Rapporto medio tra i campioni estesi risultanti dalla correzione audio e i campioni tipici.  <br/> |
|RatioCompressedSamplesAvg  <br/> |decimal(5,2)  <br/> |Rapporto medio tra i campioni compressi risultanti dalla correzione audio e i campioni tipici.  <br/> |
|RoundTrip  <br/> |int  <br/> |Tempo di round trip dalle statistiche RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Tempo di round trip massimo per il flusso audio.  <br/> |
|OverallAvgNetworkMOS  <br/> |decimal(3,2)  <br/> |MOS di rete a banda larga medio per la chiamata. Questa metrica dipende dalla perdita di pacchetti, dall'instabilità e dal codec utilizzato. L'intervallo valido è compreso tra 1,0 e 5,0.  <br/> |
|OverallMinNetworkMOS  <br/> |decimal(3,2)  <br/> |MOS di rete a banda larga minimo per la chiamata.  <br/> |
|SendListenMOS  <br/> |decimal(3,2)  <br/> |Punteggio Listening MOS a banda larga previsto medio per l'audio inviato, inclusi il livello di parlato, il livello di disturbo e le caratteristiche del dispositivo di acquisizione.  <br/> |
|SendListenMOSMin  <br/> |decimal(3,2)  <br/> |Valore SendListenMOS minimo per la chiamata.  <br/> |
|RecvListenMOS  <br/> |decimal(3,2)  <br/> |Punteggio Listening MOS a banda larga previsto medio per l'audio ricevuto dalla rete, inclusi il livello di parlato, il livello di disturbo, il codec, le condizioni della rete e le caratteristiche del dispositivo di acquisizione.  <br/> |
|RecvListenMOSMin  <br/> |decimal(3,2)  <br/> |Valore RecvListenMOS minimo per la chiamata.  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |Indica se per la chiamata è stata utilizzata la correzione FEC audio.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Indica la direzione delle informazioni P-Asserted-Identity: 1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata e 0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.  <br/> |
   

