---
title: 'Lync Server 2013: Tabella AppSharingStream'
description: 'Lync Server 2013: Tabella AppSharingStream.'
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
ms.openlocfilehash: b530af5b489e090e5d0d00fbb01b2b950bafbe5a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48574722"
---
# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="66742-103">Tabella AppSharingStream in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="66742-103">AppSharingStream table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="66742-104">_**Ultimo argomento modificato:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="66742-104">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="66742-105">La tabella AppSharingStream include la metrica QoE (Quality of Experience) per i flussi di rete utilizzati per la condivisione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="66742-105">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="66742-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="66742-106">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="66742-107"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="66742-107"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="66742-108"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="66742-108"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="66742-109"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="66742-109"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="66742-110"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="66742-110"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="66742-111"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="66742-111"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-112">dateTime</span><span class="sxs-lookup"><span data-stu-id="66742-112">dateTime</span></span></p></td>
<td><p><span data-ttu-id="66742-113">Primaria/o, esterna/o</span><span class="sxs-lookup"><span data-stu-id="66742-113">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="66742-114">Data e ora di avvio della sessione.</span><span class="sxs-lookup"><span data-stu-id="66742-114">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-115"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="66742-115"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-116">int</span><span class="sxs-lookup"><span data-stu-id="66742-116">int</span></span></p></td>
<td><p><span data-ttu-id="66742-117">Primaria/o, esterna/o</span><span class="sxs-lookup"><span data-stu-id="66742-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="66742-118">Identificatore sequenziale utilizzato per distinguere tra loro sessioni avviate nella stessa data alla stessa ora.</span><span class="sxs-lookup"><span data-stu-id="66742-118">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-119"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="66742-119"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="66742-120">tinyint</span></span></p></td>
<td><p><span data-ttu-id="66742-121">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="66742-121">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="66742-p102">Rappresenta il tipo di linea video utilizzato nella chiamata. I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="66742-p102">Represents the type of video line used in the call. Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="66742-124">0 – audio</span><span class="sxs-lookup"><span data-stu-id="66742-124">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="66742-125">1-video</span><span class="sxs-lookup"><span data-stu-id="66742-125">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="66742-126">2 - Panoramica</span><span class="sxs-lookup"><span data-stu-id="66742-126">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="66742-127">3 – condivisione di applicazioni/desktop</span><span class="sxs-lookup"><span data-stu-id="66742-127">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-128"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="66742-128"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-129">int</span><span class="sxs-lookup"><span data-stu-id="66742-129">int</span></span></p></td>
<td><p><span data-ttu-id="66742-130">Principale</span><span class="sxs-lookup"><span data-stu-id="66742-130">Primary</span></span></p></td>
<td><p><span data-ttu-id="66742-131">Identificatore univoco del flusso di condivisione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="66742-131">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-132"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="66742-132"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-133">int</span><span class="sxs-lookup"><span data-stu-id="66742-133">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-134">Instabilità media rilevata tra gli arrivi dei pacchetti RTP (Real-Time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="66742-134">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="66742-135">(Jitter è una misura del &quot; shakiness &quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</span><span class="sxs-lookup"><span data-stu-id="66742-135">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-136"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="66742-136"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-137">int</span><span class="sxs-lookup"><span data-stu-id="66742-137">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-138">Instabilità massima rilevata tra gli arrivi di pacchetti RTP.</span><span class="sxs-lookup"><span data-stu-id="66742-138">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="66742-139">(Jitter è una misura del &quot; shakiness &quot; di una chiamata). I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o persi.</span><span class="sxs-lookup"><span data-stu-id="66742-139">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-140"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="66742-140"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-141">int</span><span class="sxs-lookup"><span data-stu-id="66742-141">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p105">Quantità media di tempo (in millisecondi) necessaria per il trasferimento di andata e ritorno di un pacchetto RTP da un endpoint all'altro. Un tempo di roundtrip di 200 millisecondi o inferiore viene considerato di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="66742-p105">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="66742-p106">Valori di tempo di roundtrip elevati possono essere dovuti a routing delle chiamate internazionali, errata configurazione del routing o overload di un server di contenuti multimediali e comportano difficoltà nelle conversazioni audio bidirezionali in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="66742-p106">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-146"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="66742-146"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-147">int</span><span class="sxs-lookup"><span data-stu-id="66742-147">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p107">Quantità massima di tempo (in millisecondi) necessaria per il trasferimento di andata e ritorno di un pacchetto RTP da un endpoint all'altro. Un tempo di roundtrip di 200 millisecondi o inferiore viene considerato di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="66742-p107">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back. Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="66742-p108">Valori di tempo di roundtrip elevati possono essere dovuti a routing delle chiamate internazionali, errata configurazione del routing o overload di un server di contenuti multimediali e comportano difficoltà nelle conversazioni audio bidirezionali in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="66742-p108">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server. High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-152"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="66742-152"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-153">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-153">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p109">Frequenza media di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, ovvero un protocollo utilizzato per la trasmissione di audio e video su Internet, non raggiungono la destinazione. Valori di perdita elevati sono generalmente dovuti a congestione, larghezza di banda insufficiente, congestione/interferenze wireless o overload di un server di contenuti multimediali e comportano distorsione o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="66742-p109">Average rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-157"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="66742-157"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-158">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-158">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p110">Frequenza massima di perdita di pacchetti RTP. La perdita di pacchetti si verifica quando i pacchetti RTP, ovvero un protocollo utilizzato per la trasmissione audio e video su Internet, non riescono a raggiungere la destinazione. Frequenze di perdita elevate sono generalmente dovute a congestione, larghezza di banda insufficiente, interferenze o congestione della rete wireless o overload di un server di contenuti multimediali e comportano distorsione o perdita di audio.</span><span class="sxs-lookup"><span data-stu-id="66742-p110">Maximum rate of Real-Time Transport Protocol (RTP) packet loss. (Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server. Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-162"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="66742-162"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-163">int</span><span class="sxs-lookup"><span data-stu-id="66742-163">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-164">Numero di pacchetti inviati.</span><span class="sxs-lookup"><span data-stu-id="66742-164">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-165"><strong>Larghezza di banda</strong></span><span class="sxs-lookup"><span data-stu-id="66742-165"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-166">int</span><span class="sxs-lookup"><span data-stu-id="66742-166">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p111">Larghezza di banda unidirezionale stimata disponibile alla fine della sessione. Indicata in bit al secondo.</span><span class="sxs-lookup"><span data-stu-id="66742-p111">Estimated one-way bandwidth available at the end of the session. Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-169"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="66742-169"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-170">int</span><span class="sxs-lookup"><span data-stu-id="66742-170">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-171">Descrizione del payload di condivisione di applicazioni.</span><span class="sxs-lookup"><span data-stu-id="66742-171">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-172"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="66742-172"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-173">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-173">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p112">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="66742-p112">Total amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-176"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="66742-176"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-177">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-177">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p113">Quantità complessiva di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="66742-p113">Average amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-180"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="66742-180"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-181">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-181">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p114">Quantità massima di latenza unidirezionale. La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="66742-p114">Maximum amount of one-way latency. Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-184"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66742-184"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-185">int</span><span class="sxs-lookup"><span data-stu-id="66742-185">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p115">Occorrenze burst unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="66742-p115">Total one-way burst occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-189"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66742-189"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-190">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-190">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p116">Densità burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="66742-p116">Total one-way burst density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-194"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66742-194"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-195">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-195">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p117">Durata burst unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="66742-p117">Total one-way burst duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-199"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66742-199"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-200">int</span><span class="sxs-lookup"><span data-stu-id="66742-200">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p118">Occorrenze gap unidirezionali totali. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="66742-p118">Total one-way gap occurrences. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-204"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66742-204"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-205">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-205">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p119">Densità gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="66742-p119">Total one-way gap density. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-209"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66742-209"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-210">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-210">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p120">Durata gap unidirezionale totale. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile. I gap indicano i ritardi tra questi burst. Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="66742-p120">Total one-way gap duration. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts. This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-214"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="66742-214"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-215">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="66742-215">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-216">Ruolo applicazione (condivisore o visualizzatore) e tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="66742-216">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-217"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="66742-217"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-218">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-218">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p121">Tempo totale di elaborazione per le sezioni RDP (Remote Desktop Protocol). Un valore superiore corrisponde a un ritardo maggiore nell'esperienza di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="66742-p121">Total processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-221"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="66742-221"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-222">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-222">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p122">Tempo medio di elaborazione per le sezioni RDP. Un valore superiore corrisponde a un ritardo maggiore nell'esperienza di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="66742-p122">Average processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-225"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="66742-225"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-226">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-226">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p123">Tempo massimo di elaborazione per le sezioni RDP. Un valore superiore corrisponde a un ritardo maggiore nell'esperienza di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="66742-p123">Maximum processing time for remote desktop protocol (RDP) tiles. A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-229"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66742-229"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-230">int</span><span class="sxs-lookup"><span data-stu-id="66742-230">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p124">Occorrenze burst nel tempo di elaborazione per le sezioni RDP. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile.</span><span class="sxs-lookup"><span data-stu-id="66742-p124">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-233"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66742-233"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-234">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-234">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p125">Densità burst nel tempo di elaborazione per le sezioni RDP. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile.</span><span class="sxs-lookup"><span data-stu-id="66742-p125">Burst density in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-237"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66742-237"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-238">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-238">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p126">Durata burst nel tempo di elaborazione per le sezioni RDP. In una trasmissione di tipo burst il flusso di dati non è prevedibile, diversamente dal flusso stabile.</span><span class="sxs-lookup"><span data-stu-id="66742-p126">Burst duration in the processing time for remote desktop protocol (RDP) tiles. A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-241"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66742-241"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-242">int</span><span class="sxs-lookup"><span data-stu-id="66742-242">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-243">Occorrenze gap nel tempo di elaborazione per le sezioni RDP.</span><span class="sxs-lookup"><span data-stu-id="66742-243">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-244"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66742-244"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-245">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-245">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p127">Densità gap nel tempo di elaborazione per le sezioni RDP. Una densità gap bassa corrisponde a un'esperienza di visualizzazione migliore.</span><span class="sxs-lookup"><span data-stu-id="66742-p127">Gap density in the processing time for remote desktop protocol (RDP) tiles. Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-248"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66742-248"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-249">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-249">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-p128">Durata gap nel tempo di elaborazione per le sezioni RDP. Durate gap basse corrispondono a un'esperienza di visualizzazione migliore.</span><span class="sxs-lookup"><span data-stu-id="66742-p128">Gap duration in the processing time for remote desktop protocol (RDP) tiles. Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-252"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="66742-252"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-253">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-253">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-254">Frequenza totale di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="66742-254">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-255"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="66742-255"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-256">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-256">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-257">Frequenza media di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="66742-257">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-258"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="66742-258"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-259">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-259">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-260">Frequenza massima di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="66742-260">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-261"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66742-261"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-262">in t</span><span class="sxs-lookup"><span data-stu-id="66742-262">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-263">Occorrenze burst nella frequenza di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="66742-263">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-264"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66742-264"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-265">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-265">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-266">Densità burst nella frequenza di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="66742-266">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-267"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66742-267"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-268">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-268">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-269">Durata burst nella frequenza di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="66742-269">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-270"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66742-270"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-271">int</span><span class="sxs-lookup"><span data-stu-id="66742-271">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-272">Occorrenze gap nella frequenza di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="66742-272">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-273"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66742-273"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-274">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-274">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-275">Densità gap nella frequenza di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="66742-275">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-276"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66742-276"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-277">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-277">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-278">Durata gap nella frequenza di sezioni acquisite (sezioni al secondo).</span><span class="sxs-lookup"><span data-stu-id="66742-278">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-279"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="66742-279"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-280">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-280">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-281">Percentuale totale di contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="66742-281">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-282"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="66742-282"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-283">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-283">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-284">Percentuale media di contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="66742-284">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-285"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="66742-285"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-286">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-286">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-287">Percentuale massima di contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="66742-287">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-288"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66742-288"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-289">int</span><span class="sxs-lookup"><span data-stu-id="66742-289">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-290">Occorrenze burst per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="66742-290">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-291"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66742-291"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-292">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-292">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-293">Densità burst per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="66742-293">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-294"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66742-294"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-295">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-295">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-296">Durata burst per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="66742-296">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-297"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66742-297"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-298">int</span><span class="sxs-lookup"><span data-stu-id="66742-298">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-299">Occorrenze gap per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="66742-299">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-300"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66742-300"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-301">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-301">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-302">Densità gap per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="66742-302">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-303"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66742-303"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-304">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-304">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-305">Durata gap per il contenuto che non ha raggiunto il visualizzatore ma è stato ignorato e sovrascritto da nuovo contenuto.</span><span class="sxs-lookup"><span data-stu-id="66742-305">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-306"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="66742-306"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-307">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-307">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-308">Numero totale di fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="66742-308">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-309"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="66742-309"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-310">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-310">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-311">Numero medio di fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="66742-311">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-312"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="66742-312"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-313">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-313">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-314">Numero massimo di fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="66742-314">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-315"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66742-315"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-316">int</span><span class="sxs-lookup"><span data-stu-id="66742-316">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-317">Occorrenze burst nei fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="66742-317">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-318"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66742-318"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-319">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-319">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-320">Densità burst nei fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="66742-320">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-321"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66742-321"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-322">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-322">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-323">Durata burst nei fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="66742-323">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-324"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66742-324"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-325">int</span><span class="sxs-lookup"><span data-stu-id="66742-325">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-326">Occorrenze gap nei fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="66742-326">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-327"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66742-327"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-328">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-328">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-329">Densità gap nei fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="66742-329">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-330"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66742-330"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-331">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-331">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-332">Durata gap nei fotogrammi acquisiti mediante scraping dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="66742-332">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-333"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="66742-333"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-334">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-334">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-335">Frequenza totale fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="66742-335">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-336"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="66742-336"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-337">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-337">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-338">Frequenza media fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="66742-338">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-339"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="66742-339"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-340">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-340">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-341">Frequenza massima sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="66742-341">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-342"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66742-342"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-343">int</span><span class="sxs-lookup"><span data-stu-id="66742-343">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-344">Occorrenze burst nella frequenza sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="66742-344">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-345"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66742-345"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-346">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-346">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-347">Densità burst nella frequenza sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="66742-347">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-348"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66742-348"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-349">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-349">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-350">Durata burst nella frequenza sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="66742-350">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-351"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66742-351"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-352">int</span><span class="sxs-lookup"><span data-stu-id="66742-352">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-353">Occorrenze gap nella frequenza sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="66742-353">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-354"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66742-354"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-355">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-355">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-356">Densità gap nella frequenza sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="66742-356">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-357"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66742-357"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-358">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-358">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-359">Durata gap nella frequenza sezioni in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="66742-359">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-360"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="66742-360"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-361">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-361">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-362">Frequenza totale fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="66742-362">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-363"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="66742-363"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-364">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-364">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-365">Frequenza media fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="66742-365">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-366"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="66742-366"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-367">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-367">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-368">Frequenza massima fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="66742-368">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-369"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66742-369"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-370">int</span><span class="sxs-lookup"><span data-stu-id="66742-370">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-371">Occorrenze burst nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="66742-371">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-372"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66742-372"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-373">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-373">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-374">Densità burst nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="66742-374">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-375"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66742-375"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-376">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-376">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-377">Durata burst nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="66742-377">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-378"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66742-378"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-379">int</span><span class="sxs-lookup"><span data-stu-id="66742-379">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-380">Occorrenze gap nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="66742-380">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-381"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66742-381"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-382">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-382">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-383">Densità gap nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="66742-383">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-384"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66742-384"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-385">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-385">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-386">Durata gap nella frequenza fotogrammi in arrivo ricevuti dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="66742-386">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-387"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="66742-387"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-388">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-388">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-389">Frequenza totale sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="66742-389">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-390"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="66742-390"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-391">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-391">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-392">Frequenza media sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="66742-392">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-393"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="66742-393"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-394">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-394">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-395">Frequenza massima sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="66742-395">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-396"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66742-396"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-397">int</span><span class="sxs-lookup"><span data-stu-id="66742-397">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-398">Occorrenze burst nella frequenza sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="66742-398">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-399"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66742-399"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-400">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-400">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-401">Densità burst nella frequenza sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="66742-401">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-402"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66742-402"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-403">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-403">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-404">Durata burst nella frequenza sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="66742-404">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-405"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66742-405"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-406">int</span><span class="sxs-lookup"><span data-stu-id="66742-406">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-407">Occorrenze gap nella frequenza sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="66742-407">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-408"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66742-408"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-409">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-409">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-410">Densità gap nella frequenza sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="66742-410">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-411"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66742-411"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-412">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-412">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-413">Durata gap nella frequenza sezioni in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="66742-413">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-414"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="66742-414"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-415">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-415">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-416">Frequenza totale fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="66742-416">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-417"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="66742-417"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-418">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-418">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-419">Frequenza media fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="66742-419">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-420"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="66742-420"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-421">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-421">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-422">Frequenza massima fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="66742-422">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-423"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66742-423"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-424">int</span><span class="sxs-lookup"><span data-stu-id="66742-424">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-425">Occorrenze burst nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="66742-425">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-426"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66742-426"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-427">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-427">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-428">Densità burst nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="66742-428">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-429"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66742-429"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-430">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-430">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-431">Durata burst nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="66742-431">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-432"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="66742-432"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-433">int</span><span class="sxs-lookup"><span data-stu-id="66742-433">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-434">Occorrenze gap nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="66742-434">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-435"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="66742-435"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-436">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-436">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-437">Densità gap nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="66742-437">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-438"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="66742-438"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-439">galleggiante</span><span class="sxs-lookup"><span data-stu-id="66742-439">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-440">Durata gap nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="66742-440">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-441"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="66742-441"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-442">int</span><span class="sxs-lookup"><span data-stu-id="66742-442">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-443">Altezza media risoluzione video, in pixel.</span><span class="sxs-lookup"><span data-stu-id="66742-443">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-444"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="66742-444"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-445">int</span><span class="sxs-lookup"><span data-stu-id="66742-445">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-446">Larghezza media risoluzione video, in pixel.</span><span class="sxs-lookup"><span data-stu-id="66742-446">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-447"><strong>Inbound</strong></span><span class="sxs-lookup"><span data-stu-id="66742-447"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-448">po'</span><span class="sxs-lookup"><span data-stu-id="66742-448">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-449">Frequenza media dei fotogrammi (frame al secondo) per le trasmissioni in entrata.</span><span class="sxs-lookup"><span data-stu-id="66742-449">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="66742-450"><strong>In uscita</strong></span><span class="sxs-lookup"><span data-stu-id="66742-450"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-451">po'</span><span class="sxs-lookup"><span data-stu-id="66742-451">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-452">Frequenza media dei fotogrammi (frame al secondo) per le trasmissioni in uscita.</span><span class="sxs-lookup"><span data-stu-id="66742-452">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="66742-453"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="66742-453"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="66742-454">po'</span><span class="sxs-lookup"><span data-stu-id="66742-454">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="66742-455">1 indica che la direzione del flusso va dal chiamante al destinatario della chiamata.</span><span class="sxs-lookup"><span data-stu-id="66742-455">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="66742-456">0 indica che la direzione del flusso va dal destinatario della chiamata al chiamante.</span><span class="sxs-lookup"><span data-stu-id="66742-456">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

