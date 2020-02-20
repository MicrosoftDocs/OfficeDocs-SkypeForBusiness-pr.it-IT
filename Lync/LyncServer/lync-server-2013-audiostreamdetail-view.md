---
title: 'Lync Server 2013: visualizzazione AudioStreamDetail'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AudioStreamDetail view
ms:assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721859(v=OCS.15)
ms:contentKeyID: 49733792
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b69cdbbe7a4635e60e5912e6f41d2f089612b30a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145485"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a>Visualizzazione AudioStreamDetail in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-03_

Nella visualizzazione AudioStreamDetail vengono archiviate le informazioni relative a ogni flusso audio nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.


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
<th>Dettagli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SessionTime</p></td>
<td><p>datetime</p></td>
<td><p>A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>A cui viene fatto riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>ID univoco in una linea multimediale.</p></td>
</tr>
<tr class="even">
<td><p>StartTime</p></td>
<td><p>datetime</p></td>
<td><p>Data e ora di inizio della sessione.</p></td>
</tr>
<tr class="odd">
<td><p>EndTime</p></td>
<td><p>datetime</p></td>
<td><p>Data e ora di fine della sessione.</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>po'</p></td>
<td><p>Categoria della finestra di dialogo: 0 è il Lync Server a Mediation Server Leg; 1 è il Mediation Server per la gamba del gateway PSTN.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>po'</p></td>
<td><p>Flag che indica se la chiamata è stata o meno ignorata.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>Se presente, indica il motivo per cui una chiamata non è stata ignorata anche in caso di corrispondenza degli ID bypass. Viene definito un solo valore:</p>
<p>0x0001 - ID bypass sconosciuto per la scheda di rete predefinita.</p></td>
</tr>
<tr class="odd">
<td><p>CallPriority</p></td>
<td><p>int</p></td>
<td><p>Priorità della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CallerPool</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>FQDN del pool del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePool</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>FQDN del pool del destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>Chiamante</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>Destinatario chiamata</p></td>
<td><p>nvarchar (450)</p></td>
<td><p>URI del destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Stringa dell'agente utente del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo dell'agente utente del chiamante. Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoria dell'agente utente del chiamante. Per informazioni dettagliate, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgent</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Stringa dell'agente utente del destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CalleeUserAgentType</p></td>
<td><p>smallint</p></td>
<td><p>Tipo dell'agente utente del destinatario della chiamata. Per informazioni, vedere la <a href="lync-server-2013-useragent-table.md">tabella UserAgent in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserAgentCategory</p></td>
<td><p>nvarchar (64)</p></td>
<td><p>Categoria dell'agente utente del destinatario della chiamata. Per informazioni, vedere la <a href="lync-server-2013-useragentdef-table-qoe.md">Tabella UserAgentDef (QoE) in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerEndpoint</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nome dell'endpoint del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEndpoint</p></td>
<td><p>nvarchar (256)</p></td>
<td><p>Nome dell'endpoint del destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CallerOS</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Sistema operativo dell'endpoint del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeOS</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Sistema operativo dell'endpoint del destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUName</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Nome della CPU dell'endpoint del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUName</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Nome della CPU dell'endpoint del destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>Numero di core della CPU nell'endpoint del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>Numero di core della CPU nell'endpoint del destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CallerCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>Velocità del processore della CPU dell'endpoint del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUProcessorSpeed</p></td>
<td><p>int</p></td>
<td><p>Velocità del processore della CPU dell'endpoint del destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CallerVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Indica se il sistema del chiamante è in esecuzione in un ambiente virtualizzato. Per ulteriori informazioni, vedere la <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVirtualizationFlag</p></td>
<td><p>tinyint</p></td>
<td><p>Indica se il sistema del destinatario della chiamata è in esecuzione in un ambiente virtualizzato. Per ulteriori informazioni, vedere la <a href="lync-server-2013-endpoint-table.md">tabella endpoint in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CorrelationKey</p></td>
<td></td>
<td><p>Chiave di correlazione. A cui viene fatto riferimento dalla <a href="lync-server-2013-sessioncorrelation-table.md">tabella SessionCorrelation in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>Informazioni sul percorso multimediale, ad esempio diretto o inoltrato. Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il chiamante. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto nei flag di bit per il destinatario della chiamata. Per informazioni dettagliate, vedere la specifica del protocollo del Monitoring Server per QoE.</p></td>
</tr>
<tr class="even">
<td><p>Trasporto</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo di trasporto: 0 è UDP e 1 è TCP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Indirizzo IP del chiamante. Può essere un indirizzo IPv4 o IPv6.</p></td>
</tr>
<tr class="even">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>Porta utilizzata dal chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInside</p></td>
<td><p>po'</p></td>
<td><p>Indica se il chiamante è nella rete interna: 1 indica che il chiamante è all'interno della rete aziendale e 0 indica che il chiamante è all'esterno della rete.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Indirizzo IP del destinatario della chiamata. Può essere un indirizzo IPv4 o IPv6.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Porta utilizzata dal destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>po'</p></td>
<td><p>Indica se il destinatario della chiamata è nella rete interna: 1 indica che il destinatario della chiamata è all'interno della rete aziendale e 0 indica che il destinatario della chiamata è all'esterno della rete.</p></td>
</tr>
<tr class="odd">
<td><p>CallerUserSite</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Nome del sito del chiamante.</p></td>
</tr>
<tr class="even">
<td><p>CallerRegion</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Nome del paese/area geografica del sito del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeUserSite</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Nome del sito del destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Nome del paese/area geografica del sito del destinatario della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Indirizzo IP del servizio A/V Edge utilizzato dal chiamante. Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>Porta utilizzata nel servizio A/V Edge utilizzato dal chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Codice indirizzo IP del servizio A/V Edge utilizzato dal destinatario della chiamata. Per ulteriori informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IndirizzoIP in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Porta utilizzata nel servizio A/V Edge utilizzato dal destinatario della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del dispositivo di acquisizione del chiamante.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del dispositivo di rendering del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CallerCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del driver del dispositivo di acquisizione del chiamante.</p></td>
</tr>
<tr class="even">
<td><p>CallerRenderDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del driver del dispositivo di rendering del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del dispositivo di acquisizione del destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del dispositivo di rendering del destinatario della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del driver del dispositivo di acquisizione del destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del driver del dispositivo di rendering del destinatario della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo di connessione di rete del chiamante: 0 indica una connessione cablata e 1 indica una connessione wireless.</p></td>
</tr>
<tr class="even">
<td><p>CallerVPN</p></td>
<td><p>po'</p></td>
<td><p>Indica se il chiamante si è connesso tramite una rete VPN: 1 indica una rete VPN e 0 indica una rete non VPN.</p></td>
</tr>
<tr class="odd">
<td><p>CallerLinkSpeed</p></td>
<td><p>decimale (18,0)</p></td>
<td><p>Velocità del collegamento di rete, in bps, per l'endpoint del chiamante.</p></td>
</tr>
<tr class="even">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo di connessione di rete del destinatario della chiamata: 0 indica una connessione cablata e 1 indica una connessione wireless.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>po'</p></td>
<td><p>Indica se il chiamante si è connesso tramite una rete VPN: 1 indica una rete VPN e 0 indica una rete non VPN.</p></td>
</tr>
<tr class="even">
<td><p>CalleeLinkSpeed</p></td>
<td><p>decimale (18,0)</p></td>
<td><p>Velocità del collegamento di rete, in bps, per l'endpoint del destinatario della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>ConversationalMOS</p></td>
<td><p>decimale (3, 2)</p></td>
<td><p>Conversational MOS a banda stretta delle sessioni audio (basato su entrambi i flussi audio).</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>Larghezza di banda effettivamente applicata al flusso sul lato dell'invio secondo diverse impostazioni di criteri (TURN, API, SDP, server dei criteri e così via). Da non confondere con la larghezza di banda effettiva, perché può esistere una larghezza di banda effettiva inferiore basata sulla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che può essere utilizzata dal flusso di invio escludendo i limiti imposti dalla stima della larghezza di banda.</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>Instabilità di rete media dalle statistiche RTCP (Real Time Control Protocol).</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>Instabilità di rete massima durante la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRate</p></td>
<td><p>decimale (5, 4)</p></td>
<td><p>Frequenza media di perdita di pacchetti durante la chiamata.</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRateMax</p></td>
<td><p>decimale (5, 4)</p></td>
<td><p>Perdita di pacchetti massima rilevata durante la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>DensitàBurst</p></td>
<td><p>decimale (9, 4)</p></td>
<td><p>Densità media della perdita di pacchetti durante burst di perdite durante la chiamata.</p></td>
</tr>
<tr class="even">
<td><p>BurstDuration</p></td>
<td><p>int</p></td>
<td><p>Durata media della perdita di pacchetti durante burst di perdite durante la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>BurstGapDensity</p></td>
<td><p>decimale (9, 4)</p></td>
<td><p>Densità media della perdita di pacchetti durante le pause tra burst della perdita di pacchetti.</p></td>
</tr>
<tr class="even">
<td><p>BurstGapDuration</p></td>
<td><p>int</p></td>
<td><p>Durata media delle pause tra burst della perdita di pacchetti.</p></td>
</tr>
<tr class="odd">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>Numero di pacchetti per il flusso audio.</p></td>
</tr>
<tr class="even">
<td><p>Larghezza di banda</p></td>
<td><p>int</p></td>
<td><p>Stime della larghezza di banda per il flusso audio.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationAvg</p></td>
<td><p>decimale (3, 2)</p></td>
<td><p>Degradazione MOS di rete per l'intera chiamata. L'intervallo è compreso tra 0,0 e 5,0. Questa metrica indica la quantità di MOS di rete ridotta a causa della dispersione e della perdita di pacchetti. Per un livello di qualità accettabile, questo valore deve essere minore di 0,5.</p></td>
</tr>
<tr class="even">
<td><p>DegradationMax</p></td>
<td><p>decimale (3, 2)</p></td>
<td><p>Degradazione MOS di rete massima durante la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationJitterAvg</p></td>
<td><p>decimale (3, 2)</p></td>
<td><p>Degradazione MOS di rete causata dall'instabilità.</p></td>
</tr>
<tr class="even">
<td><p>DegradationPacketLossAvg</p></td>
<td><p>decimale (3, 2)</p></td>
<td><p>Degradazione MOS di rete causata dalla perdita di pacchetti.</p></td>
</tr>
<tr class="odd">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>Codec audio utilizzato per la chiamata, a cui viene fatto riferimento dalla <a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>AudioSampleRate</p></td>
<td><p>int</p></td>
<td><p>Frequenza di campionamento per il flusso audio.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di segnale audio dopo il controllo guadagno analogico per l'audio inviato dal chiamante. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di segnale audio per l'audio ricevuto dal chiamante. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di disturbo audio dopo il controllo guadagno analogico per l'audio inviato dal chiamante. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di disturbo audio dopo il controllo guadagno analogico per l'audio ricevuto dal chiamante. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoReturn</p></td>
<td><p>int</p></td>
<td><p>ERLE (Echo Return Loss Enhancement) per il chiamante. L'unità di misura per questa metrica è dB. I valori più bassi rappresentano un'eco minore. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</p></td>
</tr>
<tr class="even">
<td><p>CallerSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Media dei problemi di rendering dell'altoparlante del chiamante ogni 5 minuti. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Media dei problemi di acquisizione del microfono del chiamante ogni 5 minuti. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampDriftRateMic</p></td>
<td><p>decimale (9, 2)</p></td>
<td><p>Deviazione del clock del dispositivo microfono del chiamante rispetto al clock della CPU.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampDriftRateSpk</p></td>
<td><p>decimale (9, 2)</p></td>
<td><p>Deviazione del clock del dispositivo altoparlante del chiamante rispetto al clock della CPU.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampErrorMicMs</p></td>
<td><p>decimale (9, 2)</p></td>
<td><p>Media di errore del timestamp, in millisecondi, del flusso di acquisizione del microfono negli ultimi 20 secondi della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampErrorSpkMs</p></td>
<td><p>decimale (9, 2)</p></td>
<td><p>Media di errore del timestamp, in millisecondi, del flusso di rendering dell'altoparlante del chiamante negli ultimi 20 secondi della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CallerVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>La commutazione vocale è una modalità half-duplex con possibilità di interruzione ridotta. Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>Cause di un evento di eco per il chiamante. Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerEchoPercentMicIn</p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p>Percentuale di tempo in cui viene rilevata l'eco nel flusso di acquisizione del microfono del chiamante. Se viene utilizzato un auricolare, il valore deve essere basso.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoPercentSend</p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p>Percentuale di tempo in cui viene rilevata l'eco nel flusso inviato del chiamante. Un'elevata percentuale di eco nei flussi di invio è un'indicazione della perdita di eco.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di segnale ricevuto nel Mediation Server dal gateway per l'audio del chiamante. Si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere compreso tra -30 e -18 dBoV.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di disturbo ricevuto nel Mediation Server dal gateway per l'audio del chiamante. Si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, il valore accettabile deve essere inferiore a -50 dBoV.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>Controllo guadagno automatico (AGC) sul lato Mediation Server applicato all'audio del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInitialSignalLevelRMS</p></td>
<td><p>galleggiante</p></td>
<td><p>Radice della media dei quadrati del segnale in ingresso per il chiamante fino ai primi 30 secondi della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Rappresenta il livello di segnale audio dopo il controllo guadagno analogico per l'audio inviato dal destinatario della chiamata. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di segnale audio per l'audio ricevuto dal destinatario della chiamata. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere almeno pari a 30 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di disturbo audio dopo il controllo guadagno analogico per l'audio inviato dal destinatario della chiamata. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di disturbo audio dopo il controllo guadagno analogico per l'audio ricevuto dal destinatario della chiamata. L'unità di misura per questa metrica è dBmo. Per una qualità accettabile, il valore deve essere inferiore a 35 dBmo. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoReturn</p></td>
<td><p>int</p></td>
<td><p>ERLE (Echo Return Loss Enhancement) per il destinatario della chiamata. L'unità di misura per questa metrica è dB. I valori più bassi rappresentano un'eco minore. Questa metrica non è riportata da telefoni IP o A/V Conferencing Server.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Media dei problemi di rendering dell'altoparlante del destinatario della chiamata ogni 5 minuti. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.</p></td>
</tr>
<tr class="even">
<td><p>CalleeMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Media dei problemi di acquisizione del microfono del destinatario della chiamata ogni 5 minuti. Per una buona qualità, il valore deve essere inferiore a 1 ogni 5 minuti. Questa metrica non è riportata da A/V Conferencing Server, Mediation Server o telefoni IP.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampDriftRateMic</p></td>
<td><p>decimale (9, 2)</p></td>
<td><p>Deviazione del clock del dispositivo microfono del destinatario della chiamata rispetto al clock della CPU.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampDriftRateSpk</p></td>
<td><p>decimale (9, 2)</p></td>
<td><p>Deviazione del clock del dispositivo altoparlante del destinatario della chiamata rispetto al clock della CPU.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampErrorMicMs</p></td>
<td><p>decimale (9, 2)</p></td>
<td><p>Media di errore del timestamp, in millisecondi, del flusso di acquisizione del microfono negli ultimi 20 secondi della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampErrorSpkMs</p></td>
<td><p>decimale (9, 2)</p></td>
<td><p>Media di errore del timestamp, in millisecondi, del flusso di rendering dell'altoparlante del destinatario della chiamata negli ultimi 20 secondi della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>La commutazione vocale è una modalità half-duplex con possibilità di interruzione ridotta. Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>Cause di un evento di eco per il destinatario della chiamata. Per ulteriori informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEchoPercentMicIn</p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p>Percentuale di tempo in cui viene rilevata l'eco nel flusso di acquisizione del microfono del destinatario della chiamata. Se viene utilizzato un auricolare, il valore deve essere basso.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoPercentSend</p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p>Percentuale di tempo in cui viene rilevata l'eco nel flusso inviato del destinatario della chiamata. Un'elevata percentuale di eco nei flussi di invio è un'indicazione della perdita di eco.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di segnale ricevuto nel Mediation Server dal gateway per l'audio del destinatario della chiamata. Si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere compreso tra [-30 e -18] dBoV.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di disturbo ricevuto nel Mediation Server dal gateway per l'audio del destinatario della chiamata. Si applica solo al Mediation Server. L'unità di misura per questa metrica è dBoV. Per una buona qualità, il valore accettabile deve essere inferiore a -50 dBoV.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>Controllo guadagno automatico (AGC) sul lato Mediation Server applicato all'audio del destinatario della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInitialSignalLevelRMS</p></td>
<td><p>galleggiante</p></td>
<td><p>Radice della media dei quadrati del segnale in ingresso per il destinatario della chiamata fino ai primi 30 secondi della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>RatioConcealedSamplesAvg</p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p>Rapporto medio tra i campioni nascosti risultanti dalla correzione audio e i campioni tipici.</p></td>
</tr>
<tr class="even">
<td><p>RatioStretchedSamplesAvg</p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p>Rapporto medio tra i campioni estesi risultanti dalla correzione audio e i campioni tipici.</p></td>
</tr>
<tr class="odd">
<td><p>RatioCompressedSamplesAvg</p></td>
<td><p>Decimal (5, 2)</p></td>
<td><p>Rapporto medio tra i campioni compressi risultanti dalla correzione audio e i campioni tipici.</p></td>
</tr>
<tr class="even">
<td><p>RoundTrip</p></td>
<td><p>int</p></td>
<td><p>Tempo di round trip dalle statistiche RTCP.</p></td>
</tr>
<tr class="odd">
<td><p>RoundTripMax</p></td>
<td><p>int</p></td>
<td><p>Tempo di round trip massimo per il flusso audio.</p></td>
</tr>
<tr class="even">
<td><p>OverallAvgNetworkMOS</p></td>
<td><p>decimale (3, 2)</p></td>
<td><p>MOS di rete a banda larga medio per la chiamata. Questa metrica dipende dalla perdita di pacchetti, dall'instabilità e dal codec utilizzato. L'intervallo valido è compreso tra 1,0 e 5,0.</p></td>
</tr>
<tr class="odd">
<td><p>OverallMinNetworkMOS</p></td>
<td><p>decimale (3, 2)</p></td>
<td><p>MOS di rete a banda larga minimo per la chiamata.</p></td>
</tr>
<tr class="even">
<td><p>Valore SendListenMOS</p></td>
<td><p>decimale (3, 2)</p></td>
<td><p>Punteggio Listening MOS a banda larga previsto medio per l'audio inviato, inclusi il livello di parlato, il livello di disturbo e le caratteristiche del dispositivo di acquisizione.</p></td>
</tr>
<tr class="odd">
<td><p>SendListenMOSMin</p></td>
<td><p>decimale (3, 2)</p></td>
<td><p>Valore SendListenMOS minimo per la chiamata.</p></td>
</tr>
<tr class="even">
<td><p>RecvListenMOS</p></td>
<td><p>decimale (3, 2)</p></td>
<td><p>Punteggio Listening MOS a banda larga previsto medio per l'audio ricevuto dalla rete, inclusi il livello di parlato, il livello di disturbo, il codec, le condizioni della rete e le caratteristiche del dispositivo di acquisizione.</p></td>
</tr>
<tr class="odd">
<td><p>RecvListenMOSMin</p></td>
<td><p>decimale (3, 2)</p></td>
<td><p>Valore RecvListenMOS minimo per la chiamata.</p></td>
</tr>
<tr class="even">
<td><p>AudioFECUsed</p></td>
<td><p>po'</p></td>
<td><p>Indica se per la chiamata è stata utilizzata la correzione FEC audio.</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>po'</p></td>
<td><p>Indica la direzione delle informazioni P-Asserted-Identity: 1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata e 0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

