---
title: Visualizzazione AudioStreamDetail
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: La visualizzazione AudioStreamDetail archivia le informazioni su ogni flusso audio nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 14815a107654fc83fc2b71c5070b82617154677c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810874"
---
# <a name="audiostreamdetail-view"></a>Visualizzazione AudioStreamDetail
 
La visualizzazione AudioStreamDetail archivia le informazioni su ogni flusso audio nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Dettagli**|
|:-----|:-----|:-----|
|SessionTime  <br/> |DateTime  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |ID univoco all'interno di una linea media.  <br/> |
|StartTime  <br/> |DateTime  <br/> |Ora di inizio della sessione.  <br/> |
|EndTime  <br/> |DateTime  <br/> |Ora di fine della sessione.  <br/> |
|DialogCategory  <br/> |po'  <br/> |Categoria di finestra di dialogo: 0 è il server Skype for business per Mediation Server; 1 è il Mediation Server per la gamba del gateway PSTN.  <br/> |
|MediationServerBypassFlag  <br/> |po'  <br/> |Contrassegno che indica se la chiamata è stata ignorata o meno.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Se presente, indica perché una chiamata non è stata ignorata anche se gli ID di bypass corrispondono. Viene definito un solo valore:  <br/> 0x0001-ID di bypass sconosciuto per la scheda di rete predefinita.  <br/> |
|CallPriority  <br/> |int  <br/> |Priorità della chiamata.  <br/> |
|CallerPool  <br/> |nvarchar (256)  <br/> |FQDN del pool chiamante.  <br/> |
|CalleePool  <br/> |nvarchar (256)  <br/> |Nome di dominio completo del pool di chiamate.  <br/> |
|Chiamante  <br/> |nvarchar (450)  <br/> |URI del chiamante.  <br/> |
|Chiamato  <br/> |nvarchar (450)  <br/> |URI del chiamato.  <br/> |
|CallerUserAgent  <br/> |nvarchar (256)  <br/> |Stringa agente utente del chiamante.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo di agente utente del chiamante. Per informazioni dettagliate, vedere la [tabella UserAgent](useragent.md) . <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoria dell'agente utente del chiamante. Per informazioni dettagliate, vedere la [Tabella UserAgentDef (QoE)](useragentdef-qoe.md) . <br/> |
|CalleeUserAgent  <br/> |nvarchar (256)  <br/> |Stringa agente utente del chiamato.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo di agente utente del destinatario. Per informazioni, vedere la [tabella UserAgent](useragent.md) . <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoria dell'agente utente del destinatario. Per informazioni, vedere la [Tabella UserAgentDef (QoE)](useragentdef-qoe.md) . <br/> |
|CallerEndpoint  <br/> |nvarchar (256)  <br/> |Nome dell'endpoint del chiamante.  <br/> |
|CalleeEndpoint  <br/> |nvarchar (256)  <br/> |Nome dell'endpoint del chiamato.  <br/> |
|CallerOS  <br/> |nvarchar (128)  <br/> |Sistema operativo (OS) dell'endpoint del chiamante.  <br/> |
|CalleeOS  <br/> |nvarchar (128)  <br/> |Sistema operativo (OS) dell'endpoint del destinatario.  <br/> |
|CallerCPUName  <br/> |nvarchar (128)  <br/> |Nome della CPU dell'endpoint del chiamante.  <br/> |
|CalleeCPUName  <br/> |nvarchar (128)  <br/> |Nome della CPU dell'endpoint del chiamato.  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Numero di core della CPU nell'endpoint del chiamante.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Numero di core della CPU nell'endpoint del chiamato.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Velocità del processore della CPU dell'endpoint del chiamante.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Velocità del processore della CPU dell'endpoint del chiamato.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indica se il sistema del chiamante è in uso in un ambiente virtualizzato. Per altre informazioni, vedere la [tabella endpoint](endpoint.md) . <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indica se il sistema del destinatario viene eseguito in un ambiente virtualizzato. Per altre informazioni, vedere la [tabella endpoint](endpoint.md) . <br/> |
|CorrelationKey  <br/> ||Chiave di correlazione. A cui si fa riferimento dalla [tabella SessionCorrelation](sessioncorrelation.md).  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informazioni sul percorso multimediale, ad esempio Direct o inoltrata. Per altre informazioni, vedere la [Tabella MediaLine](medialine-0.md) . <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in contrassegni bits per il chiamante. Per informazioni dettagliate, vedere la specifica relativa alla qualità delle specifiche di protocollo di monitoraggio delle esperienze.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in contrassegni bits per il chiamato. Per informazioni dettagliate, vedere la specifica relativa alla qualità delle specifiche di protocollo di monitoraggio delle esperienze.  <br/> |
|Transport  <br/> |tinyint  <br/> |Tipo di trasporto: 0 è UDP, 1 è TCP.  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |Indirizzo IP del chiamante. Può trattarsi di un indirizzo IPv4 o IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Porta utilizzata dal chiamante.  <br/> |
|CallerInside  <br/> |po'  <br/> |Indica se il chiamante si trova all'interno della rete di intervalli: 1 indica che il chiamante si trova all'interno della rete aziendale, 0 indica che il chiamante si trova all'esterno della rete.  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |Indirizzo IP del destinatario. Può trattarsi di un indirizzo IPv4 o IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Porta utilizzata dal chiamato.  <br/> |
|CalleeInside  <br/> |po'  <br/> |Indica se il chiamato si trova all'interno della rete a intervalli: 1 significa che il chiamato si trova all'interno della rete aziendale, 0 indica che il chiamato è all'esterno della rete.  <br/> |
|CallerUserSite  <br/> |nvarchar (128)  <br/> |Nome del sito del chiamante.  <br/> |
|CallerRegion  <br/> |nvarchar (128)  <br/> |Nome del paese/area geografica del sito del chiamante.  <br/> |
|CalleeUserSite  <br/> |nvarchar (128)  <br/> |Nome del sito del destinatario.  <br/> |
|CalleeRegion  <br/> |nvarchar (128)  <br/> |Nome del paese/area geografica del sito del destinatario.  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |Indirizzo IP del servizio A/V Edge usato dal chiamante. Per altre informazioni, vedere la [tabella IPAddress](ipaddress.md) . <br/> |
|CallerRelayPort  <br/> |int  <br/> |Porta usata nel servizio A/V Edge usato dal chiamante.  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |Chiave indirizzo IP del servizio A/V Edge usato dal destinatario. Per altre informazioni, vedere la [tabella IPAddress](ipaddress.md) . <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta usata nel servizio A/V Edge usato dal chiamato.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |Nome del dispositivo di acquisizione del chiamante.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |Nome del dispositivo di rendering del chiamante.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |Nome del driver del dispositivo di acquisizione del chiamante.  <br/> |
|CallerRenderDriver  <br/> |varchar (256)  <br/> |Nome del driver del dispositivo di rendering del chiamante.  <br/> |
|CalleeCaptureDev  <br/> |varchar (256)  <br/> |Nome del dispositivo di acquisizione del chiamato.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |Nome del dispositivo di rendering del destinatario.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar (256)  <br/> |Nome del driver del dispositivo di acquisizione del destinatario.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |Nome del driver del dispositivo di rendering del destinatario.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Tipo di connessione di rete del chiamante: 0 è cablato, 1 è wireless.  <br/> |
|CallerVPN  <br/> |po'  <br/> |Indica se il chiamante è connesso tramite una rete privata virtuale: 1 è una rete privata virtuale (VPN), 0 non è VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimale (18; 0)  <br/> |Velocità di collegamento di rete per l'endpoint del chiamante in bps.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Tipo di connessione di rete del chiamante: 0 è cablato, 1 è wireless.  <br/> |
|CalleeVPN  <br/> |po'  <br/> |Indica se il chiamante è connesso tramite una rete privata virtuale: 1 è una rete privata virtuale (VPN), 0 non è VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimale (18; 0)  <br/> |Velocità di collegamento di rete per l'endpoint del destinatario in bps.  <br/> |
|ConversationalMOS  <br/> |decimale (3; 2)  <br/> |Stretta MOS colloquiale delle sessioni audio (in base a entrambi i flussi audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Larghezza di banda effettiva applicata al flusso del lato di invio assegnato in base alle varie impostazioni dei criteri (TURN, API, SDP, Policy Server e così via). Questa operazione non deve essere confusa con la larghezza di banda effettiva, perché la larghezza di banda effettiva può essere inferiore in base alla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che il flusso di invio può bloccare i limiti imposti dalla stima della larghezza di banda  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Jitter medio della rete dalle statistiche RTCP (Real Time Control Protocol).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Variazione massima della rete durante la chiamata.  <br/> |
|PacketLossRate  <br/> |decimale (5; 4)  <br/> |Tasso medio di perdita di pacchetti durante la chiamata.  <br/> |
|PacketLossRateMax  <br/> |decimale (5; 4)  <br/> |Perdita massima del pacchetto osservata durante la chiamata.  <br/> |
|BurstDensity  <br/> |decimale (9; 4)  <br/> |Densità media della perdita di pacchetti durante le esplosioni di perdite durante la chiamata.  <br/> |
|BurstDuration  <br/> |int  <br/> |Durata media della perdita di pacchetti durante le esplosioni di perdite durante la chiamata.  <br/> |
|BurstGapDensity  <br/> |decimale (9; 4)  <br/> |Densità media della perdita di pacchetti durante gli intervalli tra i burst di perdita di pacchetti.  <br/> |
|BurstGapDuration  <br/> |int  <br/> |Durata media degli intervalli tra i burst di perdita di pacchetti.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Conteggio dei pacchetti per il flusso audio.  <br/> |
|Larghezza di banda più ampia  <br/> |int  <br/> |Stime della larghezza di banda per il flusso audio.  <br/> |
|DegradationAvg  <br/> |decimale (3; 2)  <br/> |Degradazione MOS Network per l'intera chiamata. L'intervallo è compreso tra 0,0 e 5,0. Questa metrica Mostra l'importo che il MOS della rete è stato ridotto a causa di jitter e perdita di pacchetti. Per una qualità accettabile dovrebbe essere inferiore a 0,5.  <br/> |
|DegradationMax  <br/> |decimale (3; 2)  <br/> |Massimo degrado dei MOS di rete durante la chiamata.  <br/> |
|DegradationJitterAvg  <br/> |decimale (3; 2)  <br/> |Degradazione dei MOS di rete causata da jitter.  <br/> |
|DegradationPacketLossAvg  <br/> |decimale (3; 2)  <br/> |Degradazione dei MOS di rete causata da perdita di pacchetti.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Codec audio usato per la chiamata, a cui viene fatto riferimento dalla [Tabella PayloadDescription](payloaddescription.md).  <br/> |
|AudioSampleRate  <br/> |int  <br/> |Frequenza di campionamento per il flusso audio.  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |Livello di segnale audio di controllo del guadagno post-analogico per l'audio inviato dal chiamante. L'unità per questa metrica è dBmo. Per una qualità accettabile, dovrebbe essere di almeno 30 dBmo. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |Livello di segnale audio per l'audio ricevuto dal chiamante. L'unità per questa metrica è dBmo. Per una qualità accettabile, dovrebbe essere di almeno 30 dBmo. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |Livello di rumore audio del controllo di guadagno post-analogico per l'audio inviato dal chiamante. L'unità per questa metrica è dBmo. Per una qualità accettabile, dovrebbe essere inferiore a 35 dBmo. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |Livello di rumore audio del controllo di guadagno post-analogico per l'audio ricevuto dal chiamante. L'unità per questa metrica è dBmo. Per una qualità accettabile, dovrebbe essere inferiore a 35 dBmo. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |Miglioramento della perdita di ritorno Echo per il chiamante. L'unità per questa metrica è dB. I valori più bassi rappresentano meno eco. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |Glitch media per cinque minuti per il rendering dell'altoparlante del chiamante. Per una buona qualità, questa operazione deve essere inferiore a uno per cinque minuti. Non segnalato da un/V Conferencing Server, Mediation Server o telefoni IP.  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |Glitch media per cinque minuti per l'acquisizione del microfono del chiamante. Per una qualità ottimale, questa operazione deve essere inferiore a uno per cinque minuti. Non segnalato da un/V Conferencing Server, Mediation Server o telefoni IP.  <br/> |
|CallerTimestampDriftRateMic  <br/> |decimale (9; 2)  <br/> |Tasso di velocità di clock del dispositivo microfono del chiamante, relativo all'orologio della CPU.  <br/> |
|CallerTimestampDriftRateSpk  <br/> |decimale (9; 2)  <br/> |Tasso di deriva dell'orologio del dispositivo di altoparlante del chiamante, relativo all'orologio della CPU.  <br/> |
|CallerTimestampErrorMicMs  <br/> |decimale (9; 2)  <br/> |Messaggio di errore medio per l'acquisizione di un indicatore di data e ora in millisecondi negli ultimi 20 secondi della chiamata.  <br/> |
|CallerTimestampErrorSpkMs  <br/> |decimale (9; 2)  <br/> |Media dell'errore del timestamp del chiamante del flusso di rendering del relatore, in millisecondi, negli ultimi 20 secondi della chiamata.  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |L'opzione Voice Switch è una modalità half-duplex con un'abilità di interruzione ridotta. Per altre informazioni, vedere la [Tabella MediaLine](medialine-0.md) . <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |Cause di un evento Echo per il chiamante. Per altre informazioni, vedere la [Tabella MediaLine](medialine-0.md) . <br/> |
|CallerEchoPercentMicIn  <br/> |decimale (5; 2)  <br/> |Percentuale di tempo in cui Echo viene rilevato nel flusso di acquisizione del microfono del chiamante. Se si usa l'auricolare, il valore dovrebbe essere basso.  <br/> |
|CallerEchoPercentSend  <br/> |decimale (5; 2)  <br/> |Percentuale di tempo in cui Echo viene rilevato nel flusso inviato del chiamante. Percentuale di eco elevata nei flussi di trasmissione un'indicazione della perdita di eco.  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |Livello di segnale ricevuto sul Mediation Server dal gateway per l'audio del chiamante; Questo si applica solo al Mediation Server. L'unità di questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere compreso tra-30 e-18 dBoV.  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |Livello di segnale ricevuto sul Mediation Server dal gateway per l'audio del chiamante. Questo si applica solo al Mediation Server. L'unità di questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere inferiore a-50 dBoV.  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |Controllo di guadagno automatico (AGC) sul lato Mediation Server applicato all'audio del chiamante.  <br/> |
|CallerInitialSignalLevelRMS  <br/> |galleggiante  <br/> |Radice media quadrata (RMS) del segnale in arrivo al chiamante per un massimo di 30 secondi della chiamata.  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |Rappresenta il livello di segnale audio del controllo di guadagno post-analogico per l'audio inviato dal chiamato. L'unità per questa metrica è dBmo. Per una qualità accettabile, dovrebbe essere di almeno 30 dBmo. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |Livello di segnale audio per l'audio ricevuto dal chiamato. L'unità per questa metrica è dBmo. Per una qualità accettabile, dovrebbe essere di almeno 30 dBmo. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |Livello di rumore audio del controllo di guadagno post-analogico per l'audio inviato dal chiamato. L'unità per questa metrica è dBmo. Per una qualità accettabile, dovrebbe essere inferiore a 35 dBmo. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |Livello di rumore audio del controllo di guadagno post-analogico per l'audio ricevuto dal chiamato. L'unità per questa metrica è dBmo. Per una qualità accettabile, dovrebbe essere inferiore a 35 dBmo. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |Miglioramento della perdita di ritorno Echo per il destinatario. L'unità per questa metrica è dB. I valori più bassi rappresentano meno eco. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |Inconvenienti medi per cinque minuti per il rendering dell'altoparlante del destinatario. Per una buona qualità, questa operazione deve essere inferiore a uno per cinque minuti. Non segnalato da un/V Conferencing Server, Mediation Server o telefoni IP.  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |Glitch media per cinque minuti per l'acquisizione del microfono del destinatario. Per una qualità ottimale, questa operazione deve essere inferiore a uno per cinque minuti. Non segnalato da un/V Conferencing Server, Mediation Server o telefoni IP.  <br/> |
|CalleeTimestampDriftRateMic  <br/> |decimale (9; 2)  <br/> |Tasso di velocità di clock del dispositivo microfono del destinatario, relativo all'orologio della CPU.  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |decimale (9; 2)  <br/> |Tasso di deriva dell'orologio del dispositivo altoparlante del destinatario, relativo all'orologio della CPU.  <br/> |
|CalleeTimestampErrorMicMs  <br/> |decimale (9; 2)  <br/> |Messaggio di errore medio per l'acquisizione di un indicatore di data e ora in millisecondi negli ultimi 20 secondi della chiamata.  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |decimale (9; 2)  <br/> |Media dell'errore di timestamp del flusso di rendering del relatore del destinatario, in millisecondi, negli ultimi 20 secondi della chiamata.  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |L'opzione Voice Switch è una modalità half-duplex con un'abilità di interruzione ridotta. Per altre informazioni, vedere la [Tabella MediaLine](medialine-0.md) . <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |Cause di un evento Echo per il chiamato. Per altre informazioni, vedere la [Tabella MediaLine](medialine-0.md) . <br/> |
|CalleeEchoPercentMicIn  <br/> |decimale (5; 2)  <br/> |Percentuale di tempo in cui Echo viene rilevato nel flusso di acquisizione del microfono del destinatario. Se si usa l'auricolare, il valore dovrebbe essere basso.  <br/> |
|CalleeEchoPercentSend  <br/> |decimale (5; 2)  <br/> |Percentuale di tempo in cui Echo viene rilevato nel flusso inviato del destinatario. Percentuale di eco elevata nei flussi di trasmissione un'indicazione della perdita di eco.  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |Livello di segnale ricevuto nel server Mediation dal gateway per l'audio del destinatario; Questo si applica solo al Mediation Server. L'unità di questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere [-30 a-18] dBoV.  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |Livello di segnale ricevuto nel server Mediation dal gateway per l'audio del destinatario. Questo si applica solo al Mediation Server. L'unità di questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere inferiore a-50 dBoV.  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |Controllo di guadagno automatico (AGC) sul lato Mediation Server applicato all'audio del destinatario.  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |galleggiante  <br/> |Radice media quadrata (RMS) del segnale in arrivo al chiamato per un massimo di 30 secondi della chiamata.  <br/> |
|RatioConcealedSamplesAvg  <br/> |decimale (5; 2)  <br/> |Rapporto medio tra campioni nascosti generati dalla guarigione audio in campioni tipici.  <br/> |
|RatioStretchedSamplesAvg  <br/> |decimale (5; 2)  <br/> |Rapporto medio tra campioni allungati generati da una guarigione audio a campioni tipici.  <br/> |
|RatioCompressedSamplesAvg  <br/> |decimale (5; 2)  <br/> |Rapporto medio tra campioni compressi generati dalla guarigione audio in esempi tipici.  <br/> |
|RoundTrip  <br/> |int  <br/> |Tempo di andata e ritorno dalle statistiche di RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Tempo massimo di andata e ritorno per il flusso audio.  <br/> |
|OverallAvgNetworkMOS  <br/> |decimale (3; 2)  <br/> |MOS di rete a banda larga media per la chiamata. Questa metrica dipende dalla perdita di pacchetti, dal jitter e dal codec usati. L'intervallo è compreso tra 1,0 e 5,0.  <br/> |
|OverallMinNetworkMOS  <br/> |decimale (3; 2)  <br/> |MOS della rete a banda larga minima per la chiamata.  <br/> |
|SendListenMOS  <br/> |decimale (3; 2)  <br/> |Valore medio previsto per l'ascolto della banda larga stimata per l'invio di audio, tra cui livello vocale, livello di rumore e caratteristiche del dispositivo di acquisizione.  <br/> |
|SendListenMOSMin  <br/> |decimale (3; 2)  <br/> |SendListenMOS minima per la chiamata.  <br/> |
|RecvListenMOS  <br/> |decimale (3; 2)  <br/> |Valore medio previsto per l'ascolto della banda larga stimata per l'audio ricevuto dalla rete, inclusi livello vocale, livello di rumore, codec, condizioni di rete e caratteristiche del dispositivo di acquisizione.  <br/> |
|RecvListenMOSMin  <br/> |decimale (3; 2)  <br/> |RecvListenMOS minima per la chiamata.  <br/> |
|AudioFECUsed  <br/> |po'  <br/> |Indica se per la chiamata è stato usato l'audio FEC.  <br/> |
|SenderIsCallerPAI  <br/> |po'  <br/> |Indica la direzione delle informazioni identificative p-asserite; 1 indica che la direzione del flusso è dal chiamante al chiamato; 0 indica che la direzione del flusso è dal chiamato al chiamante.  <br/> |
   

