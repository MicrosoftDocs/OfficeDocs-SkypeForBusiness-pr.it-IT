---
title: 'Lync Server 2013: visualizzazione VideoStreamDetail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: VideoStreamDetail view
ms:assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721928(v=OCS.15)
ms:contentKeyID: 49733863
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 95cc003a0e136a4a4c123355548b95c9566b4b31
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974529"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="videostreamdetail-view-in-lync-server-2013"></a>Visualizzazione VideoStreamDetail in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-03_

La visualizzazione VideoStreamDetail archivia le informazioni su ogni flusso video nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Colonna</th>
<th>Tipo di dati</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SessionTime</p></td>
<td><p>DateTime</p></td>
<td><p>A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>MediaLineLabel</p></td>
<td><p>tinyint</p></td>
<td><p>A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>ID univoco all'interno di una linea media.</p></td>
</tr>
<tr class="odd">
<td><p>StartTime</p></td>
<td><p>DateTime</p></td>
<td><p>Ora di inizio della sessione.</p></td>
</tr>
<tr class="even">
<td><p>EndTime</p></td>
<td><p>DateTime</p></td>
<td><p>Ora di fine della sessione.</p></td>
</tr>
<tr class="odd">
<td><p>CallPriority</p></td>
<td><p>int</p></td>
<td><p>Priorità della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>FQDN del pool chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nome di dominio completo del pool di chiamate.</p></td>
</tr>
<tr class="even">
<td><p>Chiamante</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>Chiamato</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del chiamato.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Stringa agente utente del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo di agente utente del chiamante. Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoria dell'agente utente del chiamante. Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Stringa agente utente del chiamato.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo di agente utente del destinatario. Per informazioni, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoria dell'agente utente del destinatario. Per informazioni, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nome dell'endpoint del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nome dell'endpoint del chiamato.</p></td>
</tr>
<tr class="even">
<td><p>CallerOS</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Sistema operativo (OS) dell'endpoint del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Sistema operativo (OS) dell'endpoint del destinatario.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUName</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Nome della CPU dell'endpoint del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUName</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Nome della CPU dell'endpoint del chiamato.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>Numero di core della CPU dell'endpoint del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>Numero di core della CPU dell'endpoint del chiamato.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>Velocità del processore della CPU dell'endpoint del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>Velocità del processore della CPU dell'endpoint del chiamato.</p></td>
</tr>
<tr class="even">
<td><p>CallerVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Indica se il sistema del chiamante è in uso in un ambiente virtualizzato. Per altre informazioni, vedere la <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Indica se il sistema del destinatario viene eseguito in un ambiente virtualizzato. Per altre informazioni, vedere la <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>Informazioni sul percorso multimediale, ad esempio Direct o inoltrata. Per altre informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in contrassegni bits per il chiamante. Per informazioni dettagliate, vedere la specifica relativa alla qualità delle specifiche di protocollo di monitoraggio delle esperienze.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in contrassegni bits per il chiamato. Per informazioni dettagliate, vedere la specifica relativa alla qualità delle specifiche di protocollo di monitoraggio delle esperienze.</p></td>
</tr>
<tr class="odd">
<td><p>Transport</p></td>
<td><p>int</p></td>
<td><p>Tipo di trasporto: 0 è UDP, 1 è TCP.</p></td>
</tr>
<tr class="even">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Indirizzo IP del chiamante. Può trattarsi di un indirizzo IPv4 o IPv6.</p></td>
</tr>
<tr class="odd">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>Porta utilizzata dal chiamante.</p></td>
</tr>
<tr class="even">
<td><p>CallerInside</p></td>
<td><p>po'</p></td>
<td><p>Indica se il chiamante si trova all'interno della rete dell'organizzazione. 1 indica che il chiamante si trova all'interno della rete aziendale, 0 indica che il chiamante si trova all'esterno della rete.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Indirizzo IP del destinatario. Può trattarsi di un indirizzo IPv4 o IPv6.</p></td>
</tr>
<tr class="even">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Porta utilizzata dal chiamato.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeInside</p></td>
<td><p>po'</p></td>
<td><p>Indica se il chiamante si trova all'interno della rete dell'organizzazione. 1 significa che il chiamato si trova all'interno della rete aziendale, 0 indica che il visitatore si trova all'esterno della rete.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Nome del sito del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRegion</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Nome del paese/area geografica del sito del chiamante.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Nome del sito del destinatario.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Nome del paese/area geografica del sito del destinatario.</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Indirizzo IP del servizio A/V Edge usato dal chiamante. Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>Porta nel servizio A/V Edge usato dal chiamante.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Chiave indirizzo IP del servizio A/V Edge usato dal destinatario. Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Porta nel servizio A/V Edge usato dal chiamato.</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del dispositivo di acquisizione del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del dispositivo di rendering del chiamante.</p></td>
</tr>
<tr class="even">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del driver del dispositivo di acquisizione del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del driver del dispositivo di rendering del chiamante.</p></td>
</tr>
<tr class="even">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del dispositivo di acquisizione del chiamato.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del dispositivo di rendering del destinatario.</p></td>
</tr>
<tr class="even">
<td><p>CalleCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del driver del dispositivo di acquisizione del destinatario.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del driver del dispositivo di rendering del destinatario.</p></td>
</tr>
<tr class="even">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo di connessione di rete del chiamante: 0 è cablato, 1 è wireless.</p></td>
</tr>
<tr class="odd">
<td><p>CallerVPN</p></td>
<td><p>po'</p></td>
<td><p>Indica se il chiamante è connesso o meno tramite una rete privata virtuale. 1 è una rete privata virtuale (VPN), 0 non è VPN.</p></td>
</tr>
<tr class="even">
<td><p>CallerLinkSpeed</p></td>
<td><p>decimale (18)</p></td>
<td><p>Velocità di collegamento di rete per l'endpoint del chiamante in bps.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo di connessione di rete del chiamante: 0 è cablato, 1 è wireless.</p></td>
</tr>
<tr class="even">
<td><p>CalleeVPN</p></td>
<td><p>po'</p></td>
<td><p>Indica se il chiamato è connesso o meno tramite una rete privata virtuale. 1 è una rete privata virtuale (VPN), 0 non è VPN.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeLinkSpeed</p></td>
<td><p>decimale (18; 0)</p></td>
<td><p>Velocità di collegamento di rete per l'endpoint del destinatario della chiamata (in bps).</p></td>
</tr>
<tr class="even">
<td><p>ConversationalMOS</p></td>
<td><p>decimale (3; 2)</p></td>
<td><p>Stretta MOS colloquiale delle sessioni audio (in base a entrambi i flussi audio).</p></td>
</tr>
<tr class="odd">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>Larghezza di banda effettiva applicata al flusso del lato di invio assegnato in base alle varie impostazioni dei criteri (TURN, API, SDP, Policy Server e così via). Questa operazione non deve essere confusa con la larghezza di banda effettiva, perché la larghezza di banda effettiva può essere inferiore in base alla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che il flusso di invio può bloccare i limiti imposti dalla stima della larghezza di banda.</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>Jitter medio della rete dalle statistiche RTCP (Real Time Control Protocol).</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>Variazione massima della rete durante la chiamata.</p></td>
</tr>
<tr class="even">
<td><p>RoundTrip</p></td>
<td><p>int</p></td>
<td><p>Tempo di andata e ritorno dalle statistiche di RTCP.</p></td>
</tr>
<tr class="odd">
<td><p>RoundTripMax</p></td>
<td><p>int</p></td>
<td><p>Tempo massimo di andata e ritorno per il flusso audio.</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRate</p></td>
<td><p>decimale (5; 4)</p></td>
<td><p>Tasso medio di perdita di pacchetti durante la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRateMax</p></td>
<td><p>decimale (5; 4)</p></td>
<td><p>Perdita massima del pacchetto osservata durante la chiamata.</p></td>
</tr>
<tr class="even">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>Numero di pacchetti per il flusso video (protocollo di trasporto in tempo reale, RTP).</p></td>
</tr>
<tr class="odd">
<td><p>Larghezza di banda più ampia</p></td>
<td><p>int</p></td>
<td><p>Stime della larghezza di banda per il flusso audio.</p></td>
</tr>
<tr class="even">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>Codec audio usato per la chiamata, a cui viene fatto riferimento dalla <a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>VideoResolution</p></td>
<td><p>codice.caratt(9</p></td>
<td><p>Risoluzione del video in larghezza in pixel moltiplicata per l'altezza dei pixel. Segnalato come stringa.</p></td>
</tr>
<tr class="even">
<td><p>VideoBitRateAvg</p></td>
<td><p>int</p></td>
<td><p>Velocità in bit media del flusso video.</p></td>
</tr>
<tr class="odd">
<td><p>InboundVideoFrameRateAvg</p></td>
<td><p>decimale (9; 4)</p></td>
<td><p>Frequenza fotogrammi del video ricevuto.</p></td>
</tr>
<tr class="even">
<td><p>OutboundVideoFrameRateAvg</p></td>
<td><p>decimale (9; 4)</p></td>
<td><p>Frequenza fotogrammi del video inviato.</p></td>
</tr>
<tr class="odd">
<td><p>ViideoBitRateMax</p></td>
<td><p>int</p></td>
<td><p>Velocità in bit massima video durante la sessione video.</p></td>
</tr>
<tr class="even">
<td><p>Flussi</p></td>
<td><p>decimale (9; 4)</p></td>
<td><p>Frequenza con cui sono stati persi i pacchetti video.</p></td>
</tr>
<tr class="odd">
<td><p>VideoFrameLossRate</p></td>
<td><p>decimale (9.4)</p></td>
<td><p>Percentuale di fotogrammi video totali persi.</p></td>
</tr>
<tr class="even">
<td><p>VideoFEC</p></td>
<td><p>po'</p></td>
<td><p>Non usato.</p></td>
</tr>
<tr class="odd">
<td><p>VideoAllocateBWAvg</p></td>
<td><p>int</p></td>
<td><p>Quantità media di larghezza di banda allocata per il video.</p></td>
</tr>
<tr class="even">
<td><p>Flussi</p></td>
<td><p>decimale (9.4)</p></td>
<td><p>Percentuale di fotogrammi video totali persi.</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>po'</p></td>
<td><p>Direzione del flusso per le informazioni sull'identità asserite da p. 1 indica che la direzione del flusso è dal chiamante al chiamato; 0 indica che la direzione del flusso è dal chiamato al chiamante.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

