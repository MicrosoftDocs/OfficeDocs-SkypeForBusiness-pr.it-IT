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
ms.openlocfilehash: 31a75ddd223816c57a69bd0c9e88b48845d4374e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029307"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="f55c6-102">Tabella AppSharingStream in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f55c6-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f55c6-103">_**Ultimo argomento modificato:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="f55c6-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="f55c6-104">La tabella AppSharingStream include la metrica QoE (Quality of Experience) per i flussi di rete utilizzati per la condivisione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="f55c6-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="f55c6-105">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f55c6-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f55c6-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="f55c6-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="f55c6-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="f55c6-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="f55c6-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="f55c6-112">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="f55c6-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f55c6-113">Data e ora di avvio della sessione.</span><span class="sxs-lookup"><span data-stu-id="f55c6-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-115">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-115">int</span></span></p></td>
<td><p><span data-ttu-id="f55c6-116">Primario, esterno</span><span class="sxs-lookup"><span data-stu-id="f55c6-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f55c6-117">Identificatore sequenziale utilizzato per distinguere tra loro sessioni avviate nella stessa data alla stessa ora.</span><span class="sxs-lookup"><span data-stu-id="f55c6-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="f55c6-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="f55c6-120">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="f55c6-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="f55c6-p102">Rappresenta il tipo di linea video utilizzato nella chiamata. I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="f55c6-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="f55c6-123">0 – audio</span><span class="sxs-lookup"><span data-stu-id="f55c6-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="f55c6-124">1-video</span><span class="sxs-lookup"><span data-stu-id="f55c6-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="f55c6-125">2 - Panoramica</span><span class="sxs-lookup"><span data-stu-id="f55c6-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="f55c6-126">3 – condivisione di applicazioni/desktop</span><span class="sxs-lookup"><span data-stu-id="f55c6-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-128">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-128">int</span></span></p></td>
<td><p><span data-ttu-id="f55c6-129">Principale</span><span class="sxs-lookup"><span data-stu-id="f55c6-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="f55c6-130">Identificatore univoco del flusso di condivisione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="f55c6-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-132">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-133">Instabilità media rilevata tra gli arrivi dei pacchetti RTP (Real-Time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="f55c6-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="f55c6-134">(Jitter è una misura del &quot;shakiness&quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</span><span class="sxs-lookup"><span data-stu-id="f55c6-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-136">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-137">Instabilità massima rilevata tra gli arrivi di pacchetti RTP.</span><span class="sxs-lookup"><span data-stu-id="f55c6-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="f55c6-138">(Jitter è una misura del &quot;shakiness&quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</span><span class="sxs-lookup"><span data-stu-id="f55c6-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-139"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-140">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p105">Quantità media di tempo (in millisecondi) necessaria per il trasferimento di andata e ritorno di un pacchetto RTP da un endpoint all'altro. Un tempo di roundtrip di 200 millisecondi o inferiore viene considerato di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="f55c6-p106">Valori alti di tempo di roundtrip possono essere dovuti a routing delle chiamate internazionali, errata configurazione del routing o sovraccarico del server dei contenuti multimediali con conseguenti difficoltà nelle conversazioni audio bidirezionali in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-146">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p107">Quantità massima di tempo (in millisecondi) necessaria per il trasferimento di andata e ritorno di un pacchetto RTP da un endpoint all'altro. Un tempo di roundtrip di 200 millisecondi o inferiore viene considerato di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="f55c6-p108">Valori di tempo di roundtrip elevati possono essere dovuti a routing delle chiamate internazionali, errata configurazione del routing o overload di un server di contenuti multimediali e comportano difficoltà nelle conversazioni audio bidirezionali in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-152">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p109">Frequenza media di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, ovvero un protocollo utilizzato per la trasmissione di audio e video su Internet, non raggiungono la destinazione. Valori di perdita elevati sono generalmente dovuti a congestione, larghezza di banda insufficiente, congestione/interferenze wireless o overload di un server di contenuti multimediali e comportano distorsione o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-157">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p110">Frequenza massima di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, ovvero un protocollo utilizzato per la trasmissione audio e video su Internet, non riescono a raggiungere la destinazione. Frequenze di perdita elevate sono generalmente dovute a congestione, larghezza di banda insufficiente, interferenze o congestione della rete wireless o overload di un server di contenuti multimediali e comportano distorsione o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-162">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-163">Numero di pacchetti inviati.</span><span class="sxs-lookup"><span data-stu-id="f55c6-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-164"><strong>Larghezza di banda</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-165">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p111">Larghezza di banda unidirezionale stimata disponibile alla fine della sessione. Indicata in bit al secondo.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-169">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-170">Descrizione del payload di condivisione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="f55c6-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-172">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p112">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-176">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p113">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-180">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p114">Quantità massima di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-184">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p115">Occorrenze burst unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-189">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p116">Densità burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-194">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p117">Durata burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-199">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p118">Occorrenze gap unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-204">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p119">Densità gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-209">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p120">Durata gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="f55c6-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-215">Ruolo applicazione (condivisore o visualizzatore) e tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="f55c6-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-217">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p121">Tempo totale di elaborazione per le sezioni RDP (Remote Desktop Protocol). Un valore superiore corrisponde a un ritardo maggiore nell'esperienza di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-221">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p122">Tempo medio di elaborazione per le sezioni RDP. Un valore superiore corrisponde a un ritardo maggiore nell'esperienza di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-225">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p123">Tempo massimo di elaborazione per le sezioni RDP. Un valore superiore corrisponde a un ritardo maggiore nell'esperienza di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-229">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p124">Occorrenze burst nel tempo di elaborazione per le sezioni RDP. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-233">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p125">Densità burst nel tempo di elaborazione per le sezioni RDP. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-237">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p126">Durata burst nel tempo di elaborazione per le sezioni RDP. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-241">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-242">Occorrenze gap nel tempo di elaborazione per le sezioni RDP.</span><span class="sxs-lookup"><span data-stu-id="f55c6-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-244">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p127">Densità gap nel tempo di elaborazione per le sezioni RDP. Una densità gap bassa corrisponde a un'esperienza di visualizzazione migliore.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-248">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-p128">Durata gap nel tempo di elaborazione per le sezioni RDP. Durate gap basse corrispondono a un'esperienza di visualizzazione migliore.</span><span class="sxs-lookup"><span data-stu-id="f55c6-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-252">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-253">Frequenza totale di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="f55c6-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-255">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-256">Frequenza media di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="f55c6-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-258">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-259">Frequenza massima di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="f55c6-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-261">in t</span><span class="sxs-lookup"><span data-stu-id="f55c6-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-262">Occorrenze burst nella frequenza di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="f55c6-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-264">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-265">Densità burst nella frequenza di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="f55c6-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-267">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-268">Durata burst nella frequenza di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="f55c6-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-270">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-271">Occorrenze gap nella frequenza di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="f55c6-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-273">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-274">Densità gap nella frequenza di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="f55c6-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-276">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-277">Durata gap nella frequenza di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="f55c6-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-279">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-280">Percentuale totale di contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="f55c6-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-282">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-283">Percentuale media di contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="f55c6-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-285">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-286">Percentuale massima di contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="f55c6-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-288">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-289">Occorrenze burst per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="f55c6-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-291">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-292">Densità burst per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="f55c6-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-294">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-295">Durata burst per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="f55c6-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-297">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-298">Occorrenze gap per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="f55c6-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-300">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-301">Densità gap per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="f55c6-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-303">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-304">Durata gap per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="f55c6-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-306">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-307">Numero totale di fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="f55c6-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-309">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-310">Numero medio di fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="f55c6-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-312">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-313">Numero massimo di fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="f55c6-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-315">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-316">Occorrenze burst nei fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="f55c6-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-318">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-319">Densità burst nei fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="f55c6-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-321">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-322">Durata burst nei fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="f55c6-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-324">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-325">Occorrenze gap nei fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="f55c6-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-327">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-328">Densità gap nei fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="f55c6-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-330">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-331">Durata gap nei fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="f55c6-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-333">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-334">Frequenza totale fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f55c6-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-336">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-337">Frequenza media fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f55c6-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-339">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-340">Frequenza massima sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f55c6-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-342">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-343">Occorrenze burst nella frequenza sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f55c6-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-345">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-346">Densità burst nella frequenza sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f55c6-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-348">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-349">Durata burst nella frequenza sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f55c6-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-351">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-352">Occorrenze gap nella frequenza sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f55c6-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-354">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-355">Densità gap nella frequenza sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f55c6-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-357">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-358">Durata gap nella frequenza sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f55c6-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-360">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-361">Frequenza totale fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f55c6-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-363">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-364">Frequenza media fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f55c6-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-366">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-367">Frequenza massima fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f55c6-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-369">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-370">Occorrenze burst nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f55c6-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-372">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-373">Densità burst nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f55c6-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-375">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-376">Durata burst nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f55c6-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-378">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-379">Occorrenze gap nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f55c6-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-381">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-382">Densità gap nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f55c6-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-384">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-385">Durata gap nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="f55c6-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-387">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-388">Frequenza totale sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="f55c6-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-390">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-391">Frequenza media sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="f55c6-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-393">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-394">Frequenza massima sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="f55c6-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-396">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-397">Occorrenze burst nella frequenza sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="f55c6-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-399">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-400">Densità burst nella frequenza sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="f55c6-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-402">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-403">Durata burst nella frequenza sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="f55c6-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-405">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-406">Occorrenze gap nella frequenza sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="f55c6-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-408">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-409">Densità gap nella frequenza sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="f55c6-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-411">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-412">Durata gap nella frequenza sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="f55c6-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-414">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-415">Frequenza totale fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="f55c6-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-417">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-418">Frequenza media fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="f55c6-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-420">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-421">Frequenza massima fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="f55c6-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-423">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-424">Occorrenze burst nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="f55c6-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-426">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-427">Densità burst nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="f55c6-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-429">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-430">Durata burst nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="f55c6-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-432">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-433">Occorrenze gap nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="f55c6-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-435">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-436">Densità gap nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="f55c6-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-438">galleggiante</span><span class="sxs-lookup"><span data-stu-id="f55c6-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-439">Durata gap nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="f55c6-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-441">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-442">Altezza media risoluzione video, in pixel.</span><span class="sxs-lookup"><span data-stu-id="f55c6-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-444">int</span><span class="sxs-lookup"><span data-stu-id="f55c6-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-445">Larghezza media risoluzione video, in pixel.</span><span class="sxs-lookup"><span data-stu-id="f55c6-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-446"><strong>Inbound</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-447">po'</span><span class="sxs-lookup"><span data-stu-id="f55c6-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-448">Frequenza media dei fotogrammi (frame al secondo) per le trasmissioni in entrata.</span><span class="sxs-lookup"><span data-stu-id="f55c6-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f55c6-449"><strong>In uscita</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-450">po'</span><span class="sxs-lookup"><span data-stu-id="f55c6-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-451">Frequenza media dei fotogrammi (frame al secondo) per le trasmissioni in uscita.</span><span class="sxs-lookup"><span data-stu-id="f55c6-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f55c6-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="f55c6-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="f55c6-453">po'</span><span class="sxs-lookup"><span data-stu-id="f55c6-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="f55c6-454">1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="f55c6-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="f55c6-455">0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.</span><span class="sxs-lookup"><span data-stu-id="f55c6-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

