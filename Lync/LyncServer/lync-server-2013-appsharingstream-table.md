---
title: 'Lync Server 2013: Tabella AppSharingStream'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: AppSharingStream table
ms:assetid: 391490cb-d7b8-44ca-b4d1-429600da909c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204808(v=OCS.15)
ms:contentKeyID: 48183852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4454b7fbcaffc1fc302d5c434666cfdfa93ada36
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42134502"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="904fe-102">Tabella AppSharingStream in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="904fe-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="904fe-103">_**Ultimo argomento modificato:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="904fe-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="904fe-104">La tabella AppSharingStream include la metrica QoE (Quality of Experience) per i flussi di rete utilizzati per la condivisione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="904fe-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="904fe-105">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="904fe-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="904fe-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="904fe-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="904fe-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="904fe-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="904fe-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="904fe-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="904fe-112">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="904fe-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="904fe-113">Data e ora di avvio della sessione.</span><span class="sxs-lookup"><span data-stu-id="904fe-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-115">int</span><span class="sxs-lookup"><span data-stu-id="904fe-115">int</span></span></p></td>
<td><p><span data-ttu-id="904fe-116">Primario, esterno</span><span class="sxs-lookup"><span data-stu-id="904fe-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="904fe-117">Identificatore sequenziale utilizzato per distinguere tra loro sessioni avviate nella stessa data alla stessa ora.</span><span class="sxs-lookup"><span data-stu-id="904fe-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="904fe-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="904fe-120">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="904fe-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="904fe-p102">Rappresenta il tipo di linea video utilizzato nella chiamata. I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="904fe-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="904fe-123">0 – audio</span><span class="sxs-lookup"><span data-stu-id="904fe-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="904fe-124">1-video</span><span class="sxs-lookup"><span data-stu-id="904fe-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="904fe-125">2 - Panoramica</span><span class="sxs-lookup"><span data-stu-id="904fe-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="904fe-126">3 – condivisione di applicazioni/desktop</span><span class="sxs-lookup"><span data-stu-id="904fe-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-128">int</span><span class="sxs-lookup"><span data-stu-id="904fe-128">int</span></span></p></td>
<td><p><span data-ttu-id="904fe-129">Principale</span><span class="sxs-lookup"><span data-stu-id="904fe-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="904fe-130">Identificatore univoco del flusso di condivisione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="904fe-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-132">int</span><span class="sxs-lookup"><span data-stu-id="904fe-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-133">Instabilità media rilevata tra gli arrivi dei pacchetti RTP (Real-Time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="904fe-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="904fe-134">(Jitter è una misura del &quot;shakiness&quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</span><span class="sxs-lookup"><span data-stu-id="904fe-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-136">int</span><span class="sxs-lookup"><span data-stu-id="904fe-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-137">Instabilità massima rilevata tra gli arrivi di pacchetti RTP.</span><span class="sxs-lookup"><span data-stu-id="904fe-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="904fe-138">(Jitter è una misura del &quot;shakiness&quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</span><span class="sxs-lookup"><span data-stu-id="904fe-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-139"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-140">int</span><span class="sxs-lookup"><span data-stu-id="904fe-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p105">Quantità media di tempo (in millisecondi) necessaria per il trasferimento di andata e ritorno di un pacchetto RTP da un endpoint all'altro. Un tempo di roundtrip di 200 millisecondi o inferiore viene considerato di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="904fe-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="904fe-p106">Valori alti di tempo di roundtrip possono essere dovuti a routing delle chiamate internazionali, errata configurazione del routing o sovraccarico del server dei contenuti multimediali con conseguenti difficoltà nelle conversazioni audio bidirezionali in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="904fe-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-146">int</span><span class="sxs-lookup"><span data-stu-id="904fe-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p107">Quantità massima di tempo (in millisecondi) necessaria per il trasferimento di andata e ritorno di un pacchetto RTP da un endpoint all'altro. Un tempo di roundtrip di 200 millisecondi o inferiore viene considerato di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="904fe-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="904fe-p108">Valori di tempo di roundtrip elevati possono essere dovuti a routing delle chiamate internazionali, errata configurazione del routing o overload di un server di contenuti multimediali e comportano difficoltà nelle conversazioni audio bidirezionali in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="904fe-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-152">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p109">Frequenza media di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, ovvero un protocollo utilizzato per la trasmissione di audio e video su Internet, non raggiungono la destinazione. Valori di perdita elevati sono generalmente dovuti a congestione, larghezza di banda insufficiente, congestione/interferenze wireless o overload di un server di contenuti multimediali e comportano distorsione o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="904fe-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-157">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p110">Frequenza massima di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, ovvero un protocollo utilizzato per la trasmissione audio e video su Internet, non riescono a raggiungere la destinazione. Frequenze di perdita elevate sono generalmente dovute a congestione, larghezza di banda insufficiente, interferenze o congestione della rete wireless o overload di un server di contenuti multimediali e comportano distorsione o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="904fe-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-162">int</span><span class="sxs-lookup"><span data-stu-id="904fe-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-163">Numero di pacchetti inviati.</span><span class="sxs-lookup"><span data-stu-id="904fe-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-164"><strong>Larghezza di banda</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-165">int</span><span class="sxs-lookup"><span data-stu-id="904fe-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p111">Larghezza di banda unidirezionale stimata disponibile alla fine della sessione. Indicata in bit al secondo.</span><span class="sxs-lookup"><span data-stu-id="904fe-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-169">int</span><span class="sxs-lookup"><span data-stu-id="904fe-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-170">Descrizione del payload di condivisione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="904fe-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-172">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p112">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="904fe-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-176">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p113">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="904fe-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-180">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p114">Quantità massima di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="904fe-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-184">int</span><span class="sxs-lookup"><span data-stu-id="904fe-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p115">Occorrenze burst unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="904fe-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-189">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p116">Densità burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="904fe-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-194">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p117">Durata burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="904fe-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-199">int</span><span class="sxs-lookup"><span data-stu-id="904fe-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p118">Occorrenze gap unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="904fe-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-204">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p119">Densità gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="904fe-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-209">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p120">Durata gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="904fe-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="904fe-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-215">Ruolo applicazione (condivisore o visualizzatore) e tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="904fe-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-217">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p121">Tempo totale di elaborazione per le sezioni RDP (Remote Desktop Protocol). Un valore superiore corrisponde a un ritardo maggiore nell'esperienza di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="904fe-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-221">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p122">Tempo medio di elaborazione per le sezioni RDP. Un valore superiore corrisponde a un ritardo maggiore nell'esperienza di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="904fe-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-225">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p123">Tempo massimo di elaborazione per le sezioni RDP. Un valore superiore corrisponde a un ritardo maggiore nell'esperienza di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="904fe-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-229">int</span><span class="sxs-lookup"><span data-stu-id="904fe-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p124">Occorrenze burst nel tempo di elaborazione per le sezioni RDP. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile.</span><span class="sxs-lookup"><span data-stu-id="904fe-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-233">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p125">Densità burst nel tempo di elaborazione per le sezioni RDP. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile.</span><span class="sxs-lookup"><span data-stu-id="904fe-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-237">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p126">Durata burst nel tempo di elaborazione per le sezioni RDP. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile.</span><span class="sxs-lookup"><span data-stu-id="904fe-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-241">int</span><span class="sxs-lookup"><span data-stu-id="904fe-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-242">Occorrenze gap nel tempo di elaborazione per le sezioni RDP.</span><span class="sxs-lookup"><span data-stu-id="904fe-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-244">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p127">Densità gap nel tempo di elaborazione per le sezioni RDP. Una densità gap bassa corrisponde a un'esperienza di visualizzazione migliore.</span><span class="sxs-lookup"><span data-stu-id="904fe-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-248">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-p128">Durata gap nel tempo di elaborazione per le sezioni RDP. Durate gap basse corrispondono a un'esperienza di visualizzazione migliore.</span><span class="sxs-lookup"><span data-stu-id="904fe-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-252">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-253">Frequenza totale di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="904fe-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-255">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-256">Frequenza media di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="904fe-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-258">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-259">Frequenza massima di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="904fe-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-261">in t</span><span class="sxs-lookup"><span data-stu-id="904fe-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-262">Occorrenze burst nella frequenza di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="904fe-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-264">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-265">Densità burst nella frequenza di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="904fe-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-267">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-268">Durata burst nella frequenza di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="904fe-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-270">int</span><span class="sxs-lookup"><span data-stu-id="904fe-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-271">Occorrenze gap nella frequenza di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="904fe-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-273">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-274">Densità gap nella frequenza di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="904fe-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-276">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-277">Durata gap nella frequenza di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="904fe-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-279">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-280">Percentuale totale di contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="904fe-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-282">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-283">Percentuale media di contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="904fe-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-285">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-286">Percentuale massima di contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="904fe-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-288">int</span><span class="sxs-lookup"><span data-stu-id="904fe-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-289">Occorrenze burst per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="904fe-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-291">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-292">Densità burst per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="904fe-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-294">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-295">Durata burst per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="904fe-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-297">int</span><span class="sxs-lookup"><span data-stu-id="904fe-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-298">Occorrenze gap per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="904fe-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-300">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-301">Densità gap per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="904fe-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-303">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-304">Durata gap per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="904fe-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-306">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-307">Numero totale di fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="904fe-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-309">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-310">Numero medio di fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="904fe-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-312">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-313">Numero massimo di fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="904fe-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-315">int</span><span class="sxs-lookup"><span data-stu-id="904fe-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-316">Occorrenze burst nei fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="904fe-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-318">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-319">Densità burst nei fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="904fe-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-321">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-322">Durata burst nei fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="904fe-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-324">int</span><span class="sxs-lookup"><span data-stu-id="904fe-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-325">Occorrenze gap nei fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="904fe-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-327">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-328">Densità gap nei fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="904fe-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-330">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-331">Durata gap nei fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="904fe-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-333">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-334">Frequenza totale fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="904fe-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-336">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-337">Frequenza media fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="904fe-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-339">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-340">Frequenza massima sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="904fe-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-342">int</span><span class="sxs-lookup"><span data-stu-id="904fe-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-343">Occorrenze burst nella frequenza sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="904fe-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-345">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-346">Densità burst nella frequenza sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="904fe-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-348">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-349">Durata burst nella frequenza sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="904fe-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-351">int</span><span class="sxs-lookup"><span data-stu-id="904fe-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-352">Occorrenze gap nella frequenza sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="904fe-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-354">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-355">Densità gap nella frequenza sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="904fe-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-357">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-358">Durata gap nella frequenza sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="904fe-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-360">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-361">Frequenza totale fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="904fe-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-363">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-364">Frequenza media fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="904fe-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-366">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-367">Frequenza massima fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="904fe-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-369">int</span><span class="sxs-lookup"><span data-stu-id="904fe-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-370">Occorrenze burst nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="904fe-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-372">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-373">Densità burst nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="904fe-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-375">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-376">Durata burst nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="904fe-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-378">int</span><span class="sxs-lookup"><span data-stu-id="904fe-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-379">Occorrenze gap nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="904fe-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-381">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-382">Densità gap nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="904fe-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-384">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-385">Durata gap nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="904fe-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-387">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-388">Frequenza totale sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="904fe-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-390">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-391">Frequenza media sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="904fe-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-393">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-394">Frequenza massima sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="904fe-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-396">int</span><span class="sxs-lookup"><span data-stu-id="904fe-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-397">Occorrenze burst nella frequenza sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="904fe-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-399">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-400">Densità burst nella frequenza sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="904fe-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-402">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-403">Durata burst nella frequenza sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="904fe-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-405">int</span><span class="sxs-lookup"><span data-stu-id="904fe-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-406">Occorrenze gap nella frequenza sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="904fe-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-408">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-409">Densità gap nella frequenza sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="904fe-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-411">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-412">Durata gap nella frequenza sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="904fe-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-414">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-415">Frequenza totale fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="904fe-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-417">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-418">Frequenza media fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="904fe-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-420">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-421">Frequenza massima fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="904fe-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-423">int</span><span class="sxs-lookup"><span data-stu-id="904fe-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-424">Occorrenze burst nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="904fe-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-426">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-427">Densità burst nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="904fe-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-429">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-430">Durata burst nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="904fe-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-432">int</span><span class="sxs-lookup"><span data-stu-id="904fe-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-433">Occorrenze gap nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="904fe-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-435">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-436">Densità gap nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="904fe-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-438">galleggiante</span><span class="sxs-lookup"><span data-stu-id="904fe-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-439">Durata gap nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="904fe-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-441">int</span><span class="sxs-lookup"><span data-stu-id="904fe-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-442">Altezza media risoluzione video, in pixel.</span><span class="sxs-lookup"><span data-stu-id="904fe-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-444">int</span><span class="sxs-lookup"><span data-stu-id="904fe-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-445">Larghezza media risoluzione video, in pixel.</span><span class="sxs-lookup"><span data-stu-id="904fe-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-446"><strong>Inbound</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-447">po'</span><span class="sxs-lookup"><span data-stu-id="904fe-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-448">Frequenza media dei fotogrammi (frame al secondo) per le trasmissioni in entrata.</span><span class="sxs-lookup"><span data-stu-id="904fe-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="904fe-449"><strong>In uscita</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-450">po'</span><span class="sxs-lookup"><span data-stu-id="904fe-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-451">Frequenza media dei fotogrammi (frame al secondo) per le trasmissioni in uscita.</span><span class="sxs-lookup"><span data-stu-id="904fe-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="904fe-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="904fe-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="904fe-453">po'</span><span class="sxs-lookup"><span data-stu-id="904fe-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="904fe-454">1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="904fe-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="904fe-455">0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.</span><span class="sxs-lookup"><span data-stu-id="904fe-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

