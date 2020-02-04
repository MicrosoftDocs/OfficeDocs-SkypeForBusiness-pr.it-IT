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
ms.openlocfilehash: 77cebcd47d735f1779396c0272877c0ec64a6189
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="audiostreamdetail-view-in-lync-server-2013"></a>Visualizzazione AudioStreamDetail in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-03_

La visualizzazione AudioStreamDetail archivia le informazioni su ogni flusso audio nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.


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
<td><p>DateTime</p></td>
<td><p>A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>SessionSeq</p></td>
<td><p>int</p></td>
<td><p>A cui si fa riferimento dalla <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>StreamId</p></td>
<td><p>int</p></td>
<td><p>ID univoco all'interno di una linea media.</p></td>
</tr>
<tr class="even">
<td><p>StartTime</p></td>
<td><p>DateTime</p></td>
<td><p>Ora di inizio della sessione.</p></td>
</tr>
<tr class="odd">
<td><p>EndTime</p></td>
<td><p>DateTime</p></td>
<td><p>Ora di fine della sessione.</p></td>
</tr>
<tr class="even">
<td><p>DialogCategory</p></td>
<td><p>po'</p></td>
<td><p>Categoria di finestra di dialogo: 0 è il server Lync a Leg Mediation Server; 1 è il Mediation Server per la gamba del gateway PSTN.</p></td>
</tr>
<tr class="odd">
<td><p>MediationServerBypassFlag</p></td>
<td><p>po'</p></td>
<td><p>Contrassegno che indica se la chiamata è stata ignorata o meno.</p></td>
</tr>
<tr class="even">
<td><p>MediaBypassWarningFlag</p></td>
<td><p>int</p></td>
<td><p>Se presente, indica perché una chiamata non è stata ignorata anche se gli ID di bypass corrispondono. Viene definito un solo valore:</p>
<p>0x0001-ID di bypass sconosciuto per la scheda di rete predefinita.</p></td>
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
<td><p>Numero di core della CPU nell'endpoint del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCPUNumberOfCores</p></td>
<td><p>smallint</p></td>
<td><p>Numero di core della CPU nell'endpoint del chiamato.</p></td>
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
<td><p>CorrelationKey</p></td>
<td></td>
<td><p>Chiave di correlazione. A cui si fa riferimento dalla <a href="lync-server-2013-sessioncorrelation-table.md">tabella SessionCorrelation in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>ConnectivityIce</p></td>
<td><p>tinyint</p></td>
<td><p>Informazioni sul percorso multimediale, ad esempio Direct o inoltrata. Per altre informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in contrassegni bits per il chiamante. Per informazioni dettagliate, vedere la specifica relativa alla qualità delle specifiche di protocollo di monitoraggio delle esperienze.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeIceWarningFlags</p></td>
<td><p>int</p></td>
<td><p>Informazioni sul processo ICE (Interactive Connectivity Establishment) descritto in contrassegni bits per il chiamato. Per informazioni dettagliate, vedere la specifica relativa alla qualità delle specifiche di protocollo di monitoraggio delle esperienze.</p></td>
</tr>
<tr class="even">
<td><p>Transport</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo di trasporto: 0 è UDP, 1 è TCP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Indirizzo IP del chiamante. Può trattarsi di un indirizzo IPv4 o IPv6.</p></td>
</tr>
<tr class="even">
<td><p>CallerPort</p></td>
<td><p>int</p></td>
<td><p>Porta utilizzata dal chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInside</p></td>
<td><p>po'</p></td>
<td><p>Indica se il chiamante si trova all'interno della rete di intervalli: 1 indica che il chiamante si trova all'interno della rete aziendale, 0 indica che il chiamante si trova all'esterno della rete.</p></td>
</tr>
<tr class="even">
<td><p>CalleeIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Indirizzo IP del destinatario. Può trattarsi di un indirizzo IPv4 o IPv6.</p></td>
</tr>
<tr class="odd">
<td><p>CalleePort</p></td>
<td><p>int</p></td>
<td><p>Porta utilizzata dal chiamato.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInside</p></td>
<td><p>po'</p></td>
<td><p>Indica se il chiamato si trova all'interno della rete a intervalli: 1 significa che il chiamato si trova all'interno della rete aziendale, 0 indica che il chiamato è all'esterno della rete.</p></td>
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
<td><p>Nome del sito del destinatario.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRegion</p></td>
<td><p>nvarchar (128)</p></td>
<td><p>Nome del paese/area geografica del sito del destinatario.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Indirizzo IP del servizio A/V Edge usato dal chiamante. Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerRelayPort</p></td>
<td><p>int</p></td>
<td><p>Porta usata nel servizio A/V Edge usato dal chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRelayIPAddr</p></td>
<td><p>var (50)</p></td>
<td><p>Chiave indirizzo IP del servizio A/V Edge usato dal destinatario. Per altre informazioni, vedere la <a href="lync-server-2013-ipaddress-table.md">tabella IPAddress in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeRelayPort</p></td>
<td><p>int</p></td>
<td><p>Porta usata nel servizio A/V Edge usato dal chiamato.</p></td>
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
<td><p>Nome del dispositivo di acquisizione del chiamato.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDev</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del dispositivo di rendering del destinatario.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeCaptureDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del driver del dispositivo di acquisizione del destinatario.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRenderDevDriver</p></td>
<td><p>varchar (256)</p></td>
<td><p>Nome del driver del dispositivo di rendering del destinatario.</p></td>
</tr>
<tr class="odd">
<td><p>CallerNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo di connessione di rete del chiamante: 0 è cablato, 1 è wireless.</p></td>
</tr>
<tr class="even">
<td><p>CallerVPN</p></td>
<td><p>po'</p></td>
<td><p>Indica se il chiamante è connesso tramite una rete privata virtuale: 1 è una rete privata virtuale (VPN), 0 non è VPN.</p></td>
</tr>
<tr class="odd">
<td><p>CallerLinkSpeed</p></td>
<td><p>decimale (18; 0)</p></td>
<td><p>Velocità di collegamento di rete per l'endpoint del chiamante in bps.</p></td>
</tr>
<tr class="even">
<td><p>CalleeNetworkConnectionType</p></td>
<td><p>tinyint</p></td>
<td><p>Tipo di connessione di rete del chiamante: 0 è cablato, 1 è wireless.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVPN</p></td>
<td><p>po'</p></td>
<td><p>Indica se il chiamante è connesso tramite una rete privata virtuale: 1 è una rete privata virtuale (VPN), 0 non è VPN.</p></td>
</tr>
<tr class="even">
<td><p>CalleeLinkSpeed</p></td>
<td><p>decimale (18; 0)</p></td>
<td><p>Velocità di collegamento di rete per l'endpoint del destinatario in bps.</p></td>
</tr>
<tr class="odd">
<td><p>ConversationalMOS</p></td>
<td><p>decimale (3; 2)</p></td>
<td><p>Stretta MOS colloquiale delle sessioni audio (in base a entrambi i flussi audio).</p></td>
</tr>
<tr class="even">
<td><p>AppliedBandwidthLimit</p></td>
<td><p>int</p></td>
<td><p>Larghezza di banda effettiva applicata al flusso del lato di invio assegnato in base alle varie impostazioni dei criteri (TURN, API, SDP, Policy Server e così via). Questa operazione non deve essere confusa con la larghezza di banda effettiva, perché la larghezza di banda effettiva può essere inferiore in base alla stima della larghezza di banda. Si tratta in pratica della larghezza di banda massima che il flusso di invio può bloccare i limiti imposti dalla stima della larghezza di banda</p></td>
</tr>
<tr class="odd">
<td><p>JitterInterArrival</p></td>
<td><p>int</p></td>
<td><p>Jitter medio della rete dalle statistiche RTCP (Real Time Control Protocol).</p></td>
</tr>
<tr class="even">
<td><p>JitterInterArrivalMax</p></td>
<td><p>int</p></td>
<td><p>Variazione massima della rete durante la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>PacketLossRate</p></td>
<td><p>decimale (5; 4)</p></td>
<td><p>Tasso medio di perdita di pacchetti durante la chiamata.</p></td>
</tr>
<tr class="even">
<td><p>PacketLossRateMax</p></td>
<td><p>decimale (5; 4)</p></td>
<td><p>Perdita massima del pacchetto osservata durante la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>BurstDensity</p></td>
<td><p>decimale (9; 4)</p></td>
<td><p>Densità media della perdita di pacchetti durante le esplosioni di perdite durante la chiamata.</p></td>
</tr>
<tr class="even">
<td><p>BurstDuration</p></td>
<td><p>int</p></td>
<td><p>Durata media della perdita di pacchetti durante le esplosioni di perdite durante la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>BurstGapDensity</p></td>
<td><p>decimale (9; 4)</p></td>
<td><p>Densità media della perdita di pacchetti durante gli intervalli tra i burst di perdita di pacchetti.</p></td>
</tr>
<tr class="even">
<td><p>BurstGapDuration</p></td>
<td><p>int</p></td>
<td><p>Durata media degli intervalli tra i burst di perdita di pacchetti.</p></td>
</tr>
<tr class="odd">
<td><p>PacketUtilization</p></td>
<td><p>int</p></td>
<td><p>Conteggio dei pacchetti per il flusso audio.</p></td>
</tr>
<tr class="even">
<td><p>Larghezza di banda più ampia</p></td>
<td><p>int</p></td>
<td><p>Stime della larghezza di banda per il flusso audio.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationAvg</p></td>
<td><p>decimale (3; 2)</p></td>
<td><p>Degradazione MOS Network per l'intera chiamata. L'intervallo è compreso tra 0,0 e 5,0. Questa metrica Mostra l'importo che il MOS della rete è stato ridotto a causa di jitter e perdita di pacchetti. Per una qualità accettabile dovrebbe essere inferiore a 0,5.</p></td>
</tr>
<tr class="even">
<td><p>DegradationMax</p></td>
<td><p>decimale (3; 2)</p></td>
<td><p>Massimo degrado dei MOS di rete durante la chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>DegradationJitterAvg</p></td>
<td><p>decimale (3; 2)</p></td>
<td><p>Degradazione dei MOS di rete causata da jitter.</p></td>
</tr>
<tr class="even">
<td><p>DegradationPacketLossAvg</p></td>
<td><p>decimale (3; 2)</p></td>
<td><p>Degradazione dei MOS di rete causata da perdita di pacchetti.</p></td>
</tr>
<tr class="odd">
<td><p>PayloadDescription</p></td>
<td><p>int</p></td>
<td><p>Codec audio usato per la chiamata, a cui viene fatto riferimento dalla <a href="lync-server-2013-payloaddescription-table.md">Tabella PayloadDescription in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>AudioSampleRate</p></td>
<td><p>int</p></td>
<td><p>Frequenza di campionamento per il flusso audio.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di segnale audio di controllo del guadagno post-analogico per l'audio inviato dal chiamante. L'unità per questa metrica è dBmo. Per una qualità accettabile, dovrebbe essere di almeno 30 dBmo. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di segnale audio per l'audio ricevuto dal chiamante. L'unità per questa metrica è dBmo. Per una qualità accettabile, dovrebbe essere di almeno 30 dBmo. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di rumore audio del controllo di guadagno post-analogico per l'audio inviato dal chiamante. L'unità per questa metrica è dBmo. Per una qualità accettabile, dovrebbe essere inferiore a 35 dBmo. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</p></td>
</tr>
<tr class="even">
<td><p>CallerRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di rumore audio del controllo di guadagno post-analogico per l'audio ricevuto dal chiamante. L'unità per questa metrica è dBmo. Per una qualità accettabile, dovrebbe essere inferiore a 35 dBmo. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoReturn</p></td>
<td><p>int</p></td>
<td><p>Miglioramento della perdita di ritorno Echo per il chiamante. L'unità per questa metrica è dB. I valori più bassi rappresentano meno eco. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</p></td>
</tr>
<tr class="even">
<td><p>CallerSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Glitch media per cinque minuti per il rendering dell'altoparlante del chiamante. Per una buona qualità, questa operazione deve essere inferiore a uno per cinque minuti. Non segnalato da un/V Conferencing Server, Mediation Server o telefoni IP.</p></td>
</tr>
<tr class="odd">
<td><p>CallerMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Glitch media per cinque minuti per l'acquisizione del microfono del chiamante. Per una qualità ottimale, questa operazione deve essere inferiore a uno per cinque minuti. Non segnalato da un/V Conferencing Server, Mediation Server o telefoni IP.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampDriftRateMic</p></td>
<td><p>decimale (9; 2)</p></td>
<td><p>Tasso di velocità di clock del dispositivo microfono del chiamante, relativo all'orologio della CPU.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampDriftRateSpk</p></td>
<td><p>decimale (9; 2)</p></td>
<td><p>Tasso di deriva dell'orologio del dispositivo di altoparlante del chiamante, relativo all'orologio della CPU.</p></td>
</tr>
<tr class="even">
<td><p>CallerTimestampErrorMicMs</p></td>
<td><p>decimale (9; 2)</p></td>
<td><p>Messaggio di errore medio per l'acquisizione di un indicatore di data e ora in millisecondi negli ultimi 20 secondi della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>CallerTimestampErrorSpkMs</p></td>
<td><p>decimale (9; 2)</p></td>
<td><p>Media dell'errore del timestamp del chiamante del flusso di rendering del relatore, in millisecondi, negli ultimi 20 secondi della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CallerVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>L'opzione Voice Switch è una modalità half-duplex con un'abilità di interruzione ridotta. Per altre informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>Cause di un evento Echo per il chiamante. Per altre informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CallerEchoPercentMicIn</p></td>
<td><p>decimale (5; 2)</p></td>
<td><p>Percentuale di tempo in cui Echo viene rilevato nel flusso di acquisizione del microfono del chiamante. Se si usa l'auricolare, il valore dovrebbe essere basso.</p></td>
</tr>
<tr class="odd">
<td><p>CallerEchoPercentSend</p></td>
<td><p>decimale (5; 2)</p></td>
<td><p>Percentuale di tempo in cui Echo viene rilevato nel flusso inviato del chiamante. Percentuale di eco elevata nei flussi di trasmissione un'indicazione della perdita di eco.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di segnale ricevuto sul Mediation Server dal gateway per l'audio del chiamante; Questo si applica solo al Mediation Server. L'unità di questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere compreso tra-30 e-18 dBoV.</p></td>
</tr>
<tr class="odd">
<td><p>CallerRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di segnale ricevuto sul Mediation Server dal gateway per l'audio del chiamante. Questo si applica solo al Mediation Server. L'unità di questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere inferiore a-50 dBoV.</p></td>
</tr>
<tr class="even">
<td><p>CallerRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>Controllo di guadagno automatico (AGC) sul lato Mediation Server applicato all'audio del chiamante.</p></td>
</tr>
<tr class="odd">
<td><p>CallerInitialSignalLevelRMS</p></td>
<td><p>galleggiante</p></td>
<td><p>Radice media quadrata (RMS) del segnale in arrivo al chiamante per un massimo di 30 secondi della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Rappresenta il livello di segnale audio del controllo di guadagno post-analogico per l'audio inviato dal chiamato. L'unità per questa metrica è dBmo. Per una qualità accettabile, dovrebbe essere di almeno 30 dBmo. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di segnale audio per l'audio ricevuto dal chiamato. L'unità per questa metrica è dBmo. Per una qualità accettabile, dovrebbe essere di almeno 30 dBmo. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</p></td>
</tr>
<tr class="even">
<td><p>CalleeSendNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di rumore audio del controllo di guadagno post-analogico per l'audio inviato dal chiamato. L'unità per questa metrica è dBmo. Per una qualità accettabile, dovrebbe essere inferiore a 35 dBmo. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRecvNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di rumore audio del controllo di guadagno post-analogico per l'audio ricevuto dal chiamato. L'unità per questa metrica è dBmo. Per una qualità accettabile, dovrebbe essere inferiore a 35 dBmo. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoReturn</p></td>
<td><p>int</p></td>
<td><p>Miglioramento della perdita di ritorno Echo per il destinatario. L'unità per questa metrica è dB. I valori più bassi rappresentano meno eco. Questa metrica non viene segnalata da un/V Conferencing Server o telefoni IP.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeSpeakerGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Inconvenienti medi per cinque minuti per il rendering dell'altoparlante del destinatario. Per una buona qualità, questa operazione deve essere inferiore a uno per cinque minuti. Non segnalato da un/V Conferencing Server, Mediation Server o telefoni IP.</p></td>
</tr>
<tr class="even">
<td><p>CalleeMicGlitchRate</p></td>
<td><p>int</p></td>
<td><p>Glitch media per cinque minuti per l'acquisizione del microfono del destinatario. Per una qualità ottimale, questa operazione deve essere inferiore a uno per cinque minuti. Non segnalato da un/V Conferencing Server, Mediation Server o telefoni IP.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampDriftRateMic</p></td>
<td><p>decimale (9; 2)</p></td>
<td><p>Tasso di velocità di clock del dispositivo microfono del destinatario, relativo all'orologio della CPU.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampDriftRateSpk</p></td>
<td><p>decimale (9; 2)</p></td>
<td><p>Tasso di deriva dell'orologio del dispositivo altoparlante del destinatario, relativo all'orologio della CPU.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeTimestampErrorMicMs</p></td>
<td><p>decimale (9; 2)</p></td>
<td><p>Messaggio di errore medio per l'acquisizione di un indicatore di data e ora in millisecondi negli ultimi 20 secondi della chiamata.</p></td>
</tr>
<tr class="even">
<td><p>CalleeTimestampErrorSpkMs</p></td>
<td><p>decimale (9; 2)</p></td>
<td><p>Media dell'errore di timestamp del flusso di rendering del relatore del destinatario, in millisecondi, negli ultimi 20 secondi della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeVsEntryCauses</p></td>
<td><p>smallint</p></td>
<td><p>L'opzione Voice Switch è una modalità half-duplex con un'abilità di interruzione ridotta. Per altre informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoEventCauses</p></td>
<td><p>tinyint</p></td>
<td><p>Cause di un evento Echo per il chiamato. Per altre informazioni, vedere la <a href="lync-server-2013-medialine-table.md">Tabella MediaLine in Lync Server 2013</a> .</p></td>
</tr>
<tr class="odd">
<td><p>CalleeEchoPercentMicIn</p></td>
<td><p>decimale (5; 2)</p></td>
<td><p>Percentuale di tempo in cui Echo viene rilevato nel flusso di acquisizione del microfono del destinatario. Se si usa l'auricolare, il valore dovrebbe essere basso.</p></td>
</tr>
<tr class="even">
<td><p>CalleeEchoPercentSend</p></td>
<td><p>decimale (5; 2)</p></td>
<td><p>Percentuale di tempo in cui Echo viene rilevato nel flusso inviato del destinatario. Percentuale di eco elevata nei flussi di trasmissione un'indicazione della perdita di eco.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCSignalLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di segnale ricevuto nel server Mediation dal gateway per l'audio del destinatario; Questo si applica solo al Mediation Server. L'unità di questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere [-30 a-18] dBoV.</p></td>
</tr>
<tr class="even">
<td><p>CalleeRxAGCNoiseLevel</p></td>
<td><p>int</p></td>
<td><p>Livello di segnale ricevuto nel server Mediation dal gateway per l'audio del destinatario. Questo si applica solo al Mediation Server. L'unità di questa metrica è dBoV. Per una buona qualità, l'intervallo accettabile deve essere inferiore a-50 dBoV.</p></td>
</tr>
<tr class="odd">
<td><p>CalleeRxAGCGain</p></td>
<td><p>int</p></td>
<td><p>Controllo di guadagno automatico (AGC) sul lato Mediation Server applicato all'audio del destinatario.</p></td>
</tr>
<tr class="even">
<td><p>CalleeInitialSignalLevelRMS</p></td>
<td><p>galleggiante</p></td>
<td><p>Radice media quadrata (RMS) del segnale in arrivo al chiamato per un massimo di 30 secondi della chiamata.</p></td>
</tr>
<tr class="odd">
<td><p>RatioConcealedSamplesAvg</p></td>
<td><p>decimale (5; 2)</p></td>
<td><p>Rapporto medio tra campioni nascosti generati dalla guarigione audio in campioni tipici.</p></td>
</tr>
<tr class="even">
<td><p>RatioStretchedSamplesAvg</p></td>
<td><p>decimale (5; 2)</p></td>
<td><p>Rapporto medio tra campioni allungati generati da una guarigione audio a campioni tipici.</p></td>
</tr>
<tr class="odd">
<td><p>RatioCompressedSamplesAvg</p></td>
<td><p>decimale (5; 2)</p></td>
<td><p>Rapporto medio tra campioni compressi generati dalla guarigione audio in esempi tipici.</p></td>
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
<td><p>OverallAvgNetworkMOS</p></td>
<td><p>decimale (3; 2)</p></td>
<td><p>MOS di rete a banda larga media per la chiamata. Questa metrica dipende dalla perdita di pacchetti, dal jitter e dal codec usati. L'intervallo è compreso tra 1,0 e 5,0.</p></td>
</tr>
<tr class="odd">
<td><p>OverallMinNetworkMOS</p></td>
<td><p>decimale (3; 2)</p></td>
<td><p>MOS della rete a banda larga minima per la chiamata.</p></td>
</tr>
<tr class="even">
<td><p>SendListenMOS</p></td>
<td><p>decimale (3; 2)</p></td>
<td><p>Valore medio previsto per l'ascolto della banda larga stimata per l'invio di audio, tra cui livello vocale, livello di rumore e caratteristiche del dispositivo di acquisizione.</p></td>
</tr>
<tr class="odd">
<td><p>SendListenMOSMin</p></td>
<td><p>decimale (3; 2)</p></td>
<td><p>SendListenMOS minima per la chiamata.</p></td>
</tr>
<tr class="even">
<td><p>RecvListenMOS</p></td>
<td><p>decimale (3; 2)</p></td>
<td><p>Valore medio previsto per l'ascolto della banda larga stimata per l'audio ricevuto dalla rete, inclusi livello vocale, livello di rumore, codec, condizioni di rete e caratteristiche del dispositivo di acquisizione.</p></td>
</tr>
<tr class="odd">
<td><p>RecvListenMOSMin</p></td>
<td><p>decimale (3; 2)</p></td>
<td><p>RecvListenMOS minima per la chiamata.</p></td>
</tr>
<tr class="even">
<td><p>AudioFECUsed</p></td>
<td><p>po'</p></td>
<td><p>Indica se per la chiamata è stato usato l'audio FEC.</p></td>
</tr>
<tr class="odd">
<td><p>SenderIsCallerPAI</p></td>
<td><p>po'</p></td>
<td><p>Indica la direzione delle informazioni identificative p-asserite; 1 indica che la direzione del flusso è dal chiamante al chiamato; 0 indica che la direzione del flusso è dal chiamato al chiamante.</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

