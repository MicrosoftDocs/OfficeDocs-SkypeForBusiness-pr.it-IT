---
title: Visualizzazione VideoStreamDetail
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: Nella visualizzazione VideoStreamDetail vengono archiviate informazioni su ogni flusso video nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 6341febeb8d43e36975c5b4cc446ac24ff1287c2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834346"
---
# <a name="videostreamdetail-view"></a>Visualizzazione VideoStreamDetail
 
Nella visualizzazione VideoStreamDetail vengono archiviate informazioni su ogni flusso video nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Descrizione**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |Riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |ID univoco in una linea multimediale.  <br/> |
|StartTime  <br/> |datetime  <br/> |Data e ora di inizio della sessione.  <br/> |
|EndTime  <br/> |datetime  <br/> |Ora di fine della sessione.  <br/> |
|CallPriority  <br/> |int  <br/> |Priorità della chiamata.  <br/> |
|CallerPool  <br/> |nvarchar (256)  <br/> |FQDN del pool del chiamante.  <br/> |
|CalleePool  <br/> |nvarchar (256)  <br/> |FQDN del pool del destinatario della chiamata.  <br/> |
|Chiamante  <br/> |nvarchar (450)  <br/> |URI del chiamante.  <br/> |
|Destinatario chiamata  <br/> |nvarchar (450)  <br/> |URI del destinatario della chiamata.  <br/> |
|CallerUserAgent  <br/> |nvarchar (256)  <br/> |Stringa dell'agente utente del chiamante.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo di agente utente del chiamante. Per ulteriori informazioni, vedere la [tabella UserAgent](useragent.md) . <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoria dell'agente utente del chiamante. Per informazioni dettagliate, vedere la [Tabella UserAgentDef (QoE)](useragentdef-qoe.md) . <br/> |
|CalleeUserAgent  <br/> |nvarchar (256)  <br/> |Stringa dell'agente utente del destinatario della chiamata.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo di agente utente del destinatario della chiamata. Per informazioni, vedere la [tabella UserAgent](useragent.md) . <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoria dell'agente utente del destinatario della chiamata. Per informazioni, vedere la [Tabella UserAgentDef (QoE)](useragentdef-qoe.md) . <br/> |
|CallerEndpoint  <br/> |nvarchar (256)  <br/> |Nome dell'endpoint del chiamante.  <br/> |
|CalleeEndpoint  <br/> |nvarchar (256)  <br/> |Nome dell'endpoint del destinatario chiamata.  <br/> |
|CallerOS  <br/> |nvarchar (128)  <br/> |Sistema operativo dell'endpoint del chiamante.  <br/> |
|CalleeOS  <br/> |nvarchar (128)  <br/> |Sistema operativo dell'endpoint del destinatario della chiamata.  <br/> |
|CallerCPUName  <br/> |nvarchar (128)  <br/> |Nome della CPU dell'endpoint del chiamante.  <br/> |
|CalleeCPUName  <br/> |nvarchar (128)  <br/> |Nome della CPU dell'endpoint del destinatario della chiamata.  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Numero di core della CPU dell'endpoint del chiamante.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Numero di core della CPU dell'endpoint del destinatario della chiamata.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Velocità del processore della CPU dell'endpoint del chiamante.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Velocità del processore della CPU dell'endpoint del destinatario della chiamata.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indica se il sistema del chiamante è in esecuzione in un ambiente virtualizzato. Per ulteriori informazioni, vedere la [tabella endpoint](endpoint.md) . <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indica se il sistema del destinatario della chiamata è in esecuzione in un ambiente virtualizzato. Per ulteriori informazioni, vedere la [tabella endpoint](endpoint.md) . <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informazioni sul percorso multimediale, ad esempio diretto o inoltrato. Per ulteriori informazioni, vedere la [Tabella MediaLine](medialine-0.md) . <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il chiamante. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il destinatario della chiamata. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.  <br/> |
|Trasporto  <br/> |int  <br/> |Tipo di trasporto: 0 per UDP, 1 per TCP.  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |Indirizzo IP del chiamante. Può essere un indirizzo IPv4 o IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Porta utilizzata dal chiamante.  <br/> |
|CallerInside  <br/> |po'  <br/> |Indica se il chiamante è all'interno della rete dell'organizzazione. 1 indica che il chiamante è all'interno della rete aziendale, 0 invece indica che è all'esterno della rete.  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |Indirizzo IP del destinatario della chiamata. Può essere un indirizzo IPv4 o IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Porta utilizzata dal destinatario della chiamata.  <br/> |
|CalleeInside  <br/> |po'  <br/> |Indica se il chiamante è all'interno della rete dell'organizzazione. 1 indica che il destinatario chiamata è all'interno della rete aziendale, 0 invece indica che è all'esterno della rete.  <br/> |
|CallerUserSite  <br/> |nvarchar (128)  <br/> |Nome del sito del chiamante.  <br/> |
|CallerRegion  <br/> |nvarchar (128)  <br/> |Nome del paese/area geografica del sito del chiamante.  <br/> |
|CalleeUserSite  <br/> |nvarchar (128)  <br/> |Nome del sito del destinatario della chiamata.  <br/> |
|CalleeRegion  <br/> |nvarchar (128)  <br/> |Nome del paese/area geografica del sito del destinatario della chiamata.  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |Indirizzo IP del servizio A/V Edge utilizzato dal chiamante. Per ulteriori informazioni, vedere la [tabella IPAddress](ipaddress.md) . <br/> |
|CallerRelayPort  <br/> |int  <br/> |Porta del servizio A/V Edge utilizzata dal chiamante.  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |Codice indirizzo IP del servizio A/V Edge utilizzato dal destinatario della chiamata. Per ulteriori informazioni, vedere la [tabella IPAddress](ipaddress.md) . <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta del servizio A/V Edge utilizzato dal destinatario chiamata.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |Nome del dispositivo di acquisizione del chiamante.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |Nome del dispositivo di rendering del chiamante.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |Nome del driver del dispositivo di acquisizione del chiamante.  <br/> |
|CallerRenderDevDriver  <br/> |varchar (256)  <br/> |Nome del driver del dispositivo di rendering del chiamante.  <br/> |
|CalleeCaptureDev  <br/> |varchar (256)  <br/> |Nome del dispositivo di acquisizione del destinatario della chiamata.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |Nome del dispositivo di rendering del destinatario chiamata.  <br/> |
|CalleCaptureDevDriver  <br/> |varchar (256)  <br/> |Nome del driver del dispositivo di acquisizione del destinatario chiamata.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |Nome del driver del dispositivo di rendering del destinatario chiamata.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Tipo di connessione di rete del chiamante: 0 è cablato, 1 è wireless.  <br/> |
|CallerVPN  <br/> |po'  <br/> |Indica se il chiamante si è connesso tramite una rete privata virtuale. 1 indica una rete privata virtuale (VPN), 0 indica una rete non VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimale (18,)  <br/> |Velocità del collegamento di rete per l'endpoint del chiamante (in bps).  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Tipo di connessione di rete del destinatario della chiamata: 0 è cablato, 1 è wireless.  <br/> |
|CalleeVPN  <br/> |po'  <br/> |Indica se il destinatario chiamata si è connesso tramite una rete privata virtuale. 1 indica una rete privata virtuale (VPN), 0 indica una rete non VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimale (18,0)  <br/> |Velocità del collegamento di rete per l'endpoint del destinatario della chiamata (in bps).  <br/> |
|ConversationalMOS  <br/> |decimale (3, 2)  <br/> |Conversational MOS a banda stretta delle sessioni audio (basato su entrambi i flussi audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Larghezza di banda effettivamente applicata al flusso sul lato dell'invio secondo diverse impostazioni di criteri (TURN, API, SDP, server dei criteri e così via). Da non confondere con la larghezza di banda effettiva, perché può esistere una larghezza di banda effettiva inferiore basata sulla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che può essere utilizzata dal flusso di invio escludendo i limiti imposti dalla stima della larghezza di banda.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Instabilità di rete massima durante la chiamata.  <br/> |
|RoundTrip  <br/> |int  <br/> |Tempo di round trip dalle statistiche RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Tempo di round trip massimo per il flusso audio.  <br/> |
|PacketLossRate  <br/> |decimale (5, 4)  <br/> |Frequenza media di perdita di pacchetti durante la chiamata.  <br/> |
|PacketLossRateMax  <br/> |decimale (5, 4)  <br/> |Perdita di pacchetti massima rilevata durante la chiamata.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Numero di pacchetti per il flusso video (Real Time Transport Protocol, RTP).  <br/> |
|Larghezza di banda  <br/> |int  <br/> |Stime di larghezza di banda per il flusso audio.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Codec audio utilizzato per la chiamata, a cui viene fatto riferimento dalla [Tabella PayloadDescription](payloaddescription.md).  <br/> |
|VideoResolution  <br/> |char (9)  <br/> |Risoluzione del video in larghezza pixel moltiplicata per altezza pixel. Riportata come stringa.  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |Velocità in bit media del flusso video.  <br/> |
|InboundVideoFrameRateAvg  <br/> |decimale (9, 4)  <br/> |Frequenza dei fotogrammi del video ricevuto.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |decimale (9, 4)  <br/> |Frequenza dei fotogrammi del video inviato.  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |Velocità in bit video massima durante la sessione video.  <br/> |
|VideoPacketLossRate  <br/> |decimale (9, 4)  <br/> |Frequenza di perdita dei pacchetti video.  <br/> |
|VideoFrameLossRate  <br/> |decimale (9.4)  <br/> |Percentuale di frame video totali perduti.  <br/> |
|VideoFEC  <br/> |po'  <br/> |Non utilizzata.  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |Quantità media di larghezza di banda allocata per il video.  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |decimale (9.4)  <br/> |Percentuale di frame video totali perduti.  <br/> |
|SenderIsCallerPAI  <br/> |po'  <br/> |Direzione del flusso per le informazioni PAI (P-Asserted Identity). 1 indica che la direzione del flusso procede dal chiamante verso il destinatario della chiamata, 0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.  <br/> |
   

