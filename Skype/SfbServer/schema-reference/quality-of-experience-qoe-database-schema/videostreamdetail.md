---
title: Visualizzazione VideoStreamDetail
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: La visualizzazione VideoStreamDetail archivia le informazioni su ogni flusso video nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: ee342de919ffca8b62c60f8c7b724f3dc7be0205
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194554"
---
# <a name="videostreamdetail-view"></a>Visualizzazione VideoStreamDetail
 
La visualizzazione VideoStreamDetail archivia le informazioni su ogni flusso video nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
  
|**Colonna**|**Tipo di dati**|**Descrizione**|
|:-----|:-----|:-----|
|SessionTime  <br/> |DateTime  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |A cui si fa riferimento dalla [Tabella MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |ID univoco all'interno di una linea media.  <br/> |
|StartTime  <br/> |DateTime  <br/> |Ora di inizio della sessione.  <br/> |
|EndTime  <br/> |DateTime  <br/> |Ora di fine della sessione.  <br/> |
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
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Numero di core della CPU dell'endpoint del chiamante.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Numero di core della CPU dell'endpoint del chiamato.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Velocità del processore della CPU dell'endpoint del chiamante.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Velocità del processore della CPU dell'endpoint del chiamato.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indica se il sistema del chiamante è in uso in un ambiente virtualizzato. Per altre informazioni, vedere la [tabella endpoint](endpoint.md) . <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indica se il sistema del destinatario viene eseguito in un ambiente virtualizzato. Per altre informazioni, vedere la [tabella endpoint](endpoint.md) . <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informazioni sul percorso multimediale, ad esempio Direct o inoltrata. Per altre informazioni, vedere la [Tabella MediaLine](medialine-0.md) . <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in contrassegni bits per il chiamante. Per informazioni dettagliate, vedere la specifica relativa alla qualità delle specifiche di protocollo di monitoraggio delle esperienze.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in contrassegni bits per il chiamato. Per informazioni dettagliate, vedere la specifica relativa alla qualità delle specifiche di protocollo di monitoraggio delle esperienze.  <br/> |
|Transport  <br/> |int  <br/> |Tipo di trasporto: 0 è UDP, 1 è TCP.  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |Indirizzo IP del chiamante. Può trattarsi di un indirizzo IPv4 o IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Porta utilizzata dal chiamante.  <br/> |
|CallerInside  <br/> |po'  <br/> |Indica se il chiamante si trova all'interno della rete dell'organizzazione. 1 indica che il chiamante si trova all'interno della rete aziendale, 0 indica che il chiamante si trova all'esterno della rete.  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |Indirizzo IP del destinatario. Può trattarsi di un indirizzo IPv4 o IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Porta utilizzata dal chiamato.  <br/> |
|CalleeInside  <br/> |po'  <br/> |Indica se il chiamante si trova all'interno della rete dell'organizzazione. 1 significa che il chiamato si trova all'interno della rete aziendale, 0 indica che il visitatore si trova all'esterno della rete.  <br/> |
|CallerUserSite  <br/> |nvarchar (128)  <br/> |Nome del sito del chiamante.  <br/> |
|CallerRegion  <br/> |nvarchar (128)  <br/> |Nome del paese/area geografica del sito del chiamante.  <br/> |
|CalleeUserSite  <br/> |nvarchar (128)  <br/> |Nome del sito del destinatario.  <br/> |
|CalleeRegion  <br/> |nvarchar (128)  <br/> |Nome del paese/area geografica del sito del destinatario.  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |Indirizzo IP del servizio A/V Edge usato dal chiamante. Per altre informazioni, vedere la [tabella IPAddress](ipaddress.md) . <br/> |
|CallerRelayPort  <br/> |int  <br/> |Porta nel servizio A/V Edge usato dal chiamante.  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |Chiave indirizzo IP del servizio A/V Edge usato dal destinatario. Per altre informazioni, vedere la [tabella IPAddress](ipaddress.md) . <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta nel servizio A/V Edge usato dal chiamato.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |Nome del dispositivo di acquisizione del chiamante.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |Nome del dispositivo di rendering del chiamante.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |Nome del driver del dispositivo di acquisizione del chiamante.  <br/> |
|CallerRenderDevDriver  <br/> |varchar (256)  <br/> |Nome del driver del dispositivo di rendering del chiamante.  <br/> |
|CalleeCaptureDev  <br/> |varchar (256)  <br/> |Nome del dispositivo di acquisizione del chiamato.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |Nome del dispositivo di rendering del destinatario.  <br/> |
|CalleCaptureDevDriver  <br/> |varchar (256)  <br/> |Nome del driver del dispositivo di acquisizione del destinatario.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |Nome del driver del dispositivo di rendering del destinatario.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Tipo di connessione di rete del chiamante: 0 è cablato, 1 è wireless.  <br/> |
|CallerVPN  <br/> |po'  <br/> |Indica se il chiamante è connesso o meno tramite una rete privata virtuale. 1 è una rete privata virtuale (VPN), 0 non è VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimale (18)  <br/> |Velocità di collegamento di rete per l'endpoint del chiamante in bps.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Tipo di connessione di rete del chiamante: 0 è cablato, 1 è wireless.  <br/> |
|CalleeVPN  <br/> |po'  <br/> |Indica se il chiamato è connesso o meno tramite una rete privata virtuale. 1 è una rete privata virtuale (VPN), 0 non è VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimale (18; 0)  <br/> |Velocità di collegamento di rete per l'endpoint del destinatario della chiamata (in bps).  <br/> |
|ConversationalMOS  <br/> |decimale (3; 2)  <br/> |Stretta MOS colloquiale delle sessioni audio (in base a entrambi i flussi audio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Larghezza di banda effettiva applicata al flusso del lato di invio assegnato in base alle varie impostazioni dei criteri (TURN, API, SDP, Policy Server e così via). Questa operazione non deve essere confusa con la larghezza di banda effettiva, perché la larghezza di banda effettiva può essere inferiore in base alla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che il flusso di invio può bloccare i limiti imposti dalla stima della larghezza di banda.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Jitter medio della rete dalle statistiche RTCP (Real Time Control Protocol).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Variazione massima della rete durante la chiamata.  <br/> |
|RoundTrip  <br/> |int  <br/> |Tempo di andata e ritorno dalle statistiche di RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Tempo massimo di andata e ritorno per il flusso audio.  <br/> |
|PacketLossRate  <br/> |decimale (5; 4)  <br/> |Tasso medio di perdita di pacchetti durante la chiamata.  <br/> |
|PacketLossRateMax  <br/> |decimale (5; 4)  <br/> |Perdita massima del pacchetto osservata durante la chiamata.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Numero di pacchetti per il flusso video (protocollo di trasporto in tempo reale, RTP).  <br/> |
|Larghezza di banda più ampia  <br/> |int  <br/> |Stime della larghezza di banda per il flusso audio.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Codec audio usato per la chiamata, a cui fa riferimento la [Tabella PayloadDescription](payloaddescription.md).  <br/> |
|VideoResolution  <br/> |codice.caratt(9  <br/> |Risoluzione del video in larghezza in pixel moltiplicata per l'altezza dei pixel. Segnalato come stringa.  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |Velocità in bit media del flusso video.  <br/> |
|InboundVideoFrameRateAvg  <br/> |decimale (9; 4)  <br/> |Frequenza fotogrammi del video ricevuto.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |decimale (9; 4)  <br/> |Frequenza fotogrammi del video inviato.  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |Velocità in bit massima video durante la sessione video.  <br/> |
|Flussi  <br/> |decimale (9; 4)  <br/> |Frequenza con cui sono stati persi i pacchetti video.  <br/> |
|VideoFrameLossRate  <br/> |decimale (9.4)  <br/> |Percentuale di fotogrammi video totali persi.  <br/> |
|VideoFEC  <br/> |po'  <br/> |Non usato.  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |Quantità media di larghezza di banda allocata per il video.  <br/> |
|Flussi  <br/> |decimale (9.4)  <br/> |Percentuale di fotogrammi video totali persi.  <br/> |
|SenderIsCallerPAI  <br/> |po'  <br/> |Direzione del flusso per le informazioni sull'identità asserite da p. 1 indica che la direzione del flusso è dal chiamante al chiamato; 0 indica che la direzione del flusso è dal chiamato al chiamante.  <br/> |
   

