---
title: Visualizzazione VideoStreamDetail
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: Nella visualizzazione VideoStreamDetail vengono archiviate informazioni su ogni flusso video nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 0e34791bd3081497c4c8501dbd01d2e9d39503f1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393538"
---
# <a name="videostreamdetail-view"></a>Visualizzazione VideoStreamDetail
 
Nella visualizzazione VideoStreamDetail vengono archiviate informazioni su ogni flusso video nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Descrizione**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Riferimento dalla [tabella MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |ID univoco in una linea multimediale.  <br/> |
|StartTime  <br/> |datetime  <br/> |Data e ora di inizio della sessione.  <br/> |
|EndTime  <br/> |datetime  <br/> |Ora di fine della sessione.  <br/> |
|CallPriority  <br/> |int  <br/> |Priorità della chiamata.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN del pool del chiamante.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN del pool del destinatario della chiamata.  <br/> |
|Chiamante  <br/> |nvarchar(450)  <br/> |URI del chiamante.  <br/> |
|Chiamato  <br/> |nvarchar(450)  <br/> |URI del chiamato.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Stringa agente utente del chiamante.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo di agente utente del chiamante. Per informazioni [dettagliate, vedere la tabella UserAgent](useragent.md) . <br/> |
|CallerUserAgentCategory  <br/> |nvarchar(64)  <br/> |Categoria dell'agente utente del chiamante. Per informazioni [dettagliate, vedere la tabella UserAgentDef (QoE](useragentdef-qoe.md) ). <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Stringa agente utente del chiamato.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo di agente utente del chiamato. Per informazioni [, vedere la tabella UserAgent](useragent.md) . <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar(64)  <br/> |Categoria dell'agente utente del chiamato. Per informazioni [, vedere la tabella UserAgentDef (QoE](useragentdef-qoe.md) ). <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nome dell'endpoint del chiamante.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nome dell'endpoint del chiamato.  <br/> |
|CallerOS  <br/> |nvarchar(128)  <br/> |Sistema operativo dell'endpoint del chiamante.  <br/> |
|CalleeOS  <br/> |nvarchar(128)  <br/> |Sistema operativo dell'endpoint del chiamato.  <br/> |
|CallerCPUName  <br/> |nvarchar(128)  <br/> |Nome CPU dell'endpoint del chiamante.  <br/> |
|CalleeCPUName  <br/> |nvarchar(128)  <br/> |Nome CPU dell'endpoint del chiamato.  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Numero di core di CPU dell'endpoint del chiamante.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Numero di core della CPU dell'endpoint del chiamato.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Velocità del processore della CPU dell'endpoint del chiamante.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Velocità del processore della CPU dell'endpoint del chiamato.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indica se il sistema del chiamante è in esecuzione in un ambiente virtualizzato. Per ulteriori [informazioni, vedere](endpoint.md) la tabella Endpoint. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indica se il sistema del chiamato è in esecuzione in un ambiente virtualizzato. Per ulteriori [informazioni, vedere](endpoint.md) la tabella Endpoint. <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informazioni sul percorso multimediale, ad esempio diretto o inoltrato. Per ulteriori [informazioni, vedi la tabella MediaLine](medialine-0.md) . <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il chiamante. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il destinatario della chiamata. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.  <br/> |
|Trasporto  <br/> |int  <br/> |Tipo di trasporto: 0 per UDP, 1 per TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Indirizzo IP del chiamante. Può essere un indirizzo IPv4 o IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Porta utilizzata dal chiamante.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica se il chiamante è all'interno della rete dell'organizzazione. 1 indica che il chiamante è all'interno della rete aziendale, 0 invece indica che è all'esterno della rete.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Indirizzo IP del destinatario della chiamata. Può essere un indirizzo IPv4 o IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Porta utilizzata dal destinatario della chiamata.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica se il chiamante è all'interno della rete dell'organizzazione. 1 indica che il destinatario chiamata è all'interno della rete aziendale, 0 invece indica che è all'esterno della rete.  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |Nome del sito del chiamante.  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |Nome del paese/area geografica del sito del chiamante.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |Nome del sito del chiamato.  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |Nome del paese/area geografica del sito del chiamato.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Indirizzo IP del servizio A/V Edge utilizzato dal chiamante. Per ulteriori [informazioni, vedere la tabella IPAddress](ipaddress.md) . <br/> |
|CallerRelayPort  <br/> |int  <br/> |Porta del servizio A/V Edge utilizzata dal chiamante.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Codice indirizzo IP del servizio A/V Edge utilizzato dal destinatario della chiamata. Per ulteriori [informazioni, vedere la tabella IPAddress](ipaddress.md) . <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta del servizio A/V Edge utilizzato dal destinatario chiamata.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nome del dispositivo di acquisizione del chiamante.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nome del dispositivo di rendering del chiamante.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nome del driver del dispositivo di acquisizione del chiamante.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |Nome del driver del dispositivo di rendering del chiamante.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |Nome del dispositivo di acquisizione del chiamato.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nome del dispositivo di rendering del chiamato.  <br/> |
|CalleCaptureDevDriver  <br/> |varchar(256)  <br/> |Nome del driver del dispositivo di acquisizione del chiamato.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nome del driver del dispositivo di rendering del chiamato.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Tipo di connessione di rete del chiamante: 0 è cablato, 1 è wireless.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica se il chiamante si è connesso tramite una rete privata virtuale. 1 indica una rete privata virtuale (VPN), 0 indica una rete non VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,)  <br/> |Velocità del collegamento di rete per l'endpoint del chiamante (in bps).  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Tipo di connessione di rete del chiamato: 0 è cablato, 1 è wireless.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica se il destinatario chiamata si è connesso tramite una rete privata virtuale. 1 indica una rete privata virtuale (VPN), 0 indica una rete non VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |Velocità del collegamento di rete per l'endpoint del chiamato (in bps).  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |Conversational MOS a banda stretta delle sessioni audio (basato su entrambi i flussi audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Larghezza di banda effettivamente applicata al flusso sul lato dell'invio secondo diverse impostazioni di criteri (TURN, API, SDP, server dei criteri e così via). Da non confondere con la larghezza di banda effettiva, perché può esistere una larghezza di banda effettiva inferiore basata sulla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che può essere utilizzata dal flusso di invio escludendo i limiti imposti dalla stima della larghezza di banda.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Instabilità di rete massima durante la chiamata.  <br/> |
|RoundTrip  <br/> |int  <br/> |Tempo di round trip dalle statistiche RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Tempo di round trip massimo per il flusso audio.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |Frequenza media di perdita di pacchetti durante la chiamata.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |Perdita di pacchetti massima rilevata durante la chiamata.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Numero di pacchetti per il flusso video (Real Time Transport Protocol, RTP).  <br/> |
|BandwidthEst  <br/> |int  <br/> |Stime di larghezza di banda per il flusso audio.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Codec audio usato per la chiamata, a cui viene fatto riferimento dalla [tabella PayloadDescription](payloaddescription.md).  <br/> |
|VideoResolution  <br/> |char(9)  <br/> |Risoluzione del video in larghezza pixel moltiplicata per altezza pixel. Riportata come stringa.  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |Velocità in bit media del flusso video.  <br/> |
|InboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |Frequenza dei fotogrammi del video ricevuto.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |Frequenza dei fotogrammi del video inviato.  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |Velocità in bit video massima durante la sessione video.  <br/> |
|VideoPacketLossRate  <br/> |decimal(9,4)  <br/> |Frequenza di perdita dei pacchetti video.  <br/> |
|VideoFrameLossRate  <br/> |decimal(9,4)  <br/> |Percentuale di frame video totali perduti.  <br/> |
|VideoFEC  <br/> |bit  <br/> |Non utilizzata.  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |Quantità media di larghezza di banda allocata per il video.  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |decimal(9,4)  <br/> |Percentuale di frame video totali perduti.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Direzione del flusso per le informazioni PAI (P-Asserted Identity). 1 indica che la direzione del flusso procede dal chiamante verso il destinatario della chiamata, 0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.  <br/> |
   

