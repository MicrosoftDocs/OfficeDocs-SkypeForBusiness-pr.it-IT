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
ms.openlocfilehash: c00a606981ab09d370d5aac390aa244a31063f24
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="appsharingstream-table-in-lync-server-2013"></a><span data-ttu-id="41c84-102">Tabella AppSharingStream in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="41c84-102">AppSharingStream table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="41c84-103">_**Argomento Ultima modifica:** 2014-02-21_</span><span class="sxs-lookup"><span data-stu-id="41c84-103">_**Topic Last Modified:** 2014-02-21_</span></span>

<span data-ttu-id="41c84-104">La Tabella AppSharingStream contiene la qualità delle metriche dell'esperienza per i flussi di rete usati per la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="41c84-104">The AppSharingStream table contains Quality of Experience metrics for the network streams used for application sharing.</span></span> <span data-ttu-id="41c84-105">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="41c84-105">This table was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="41c84-106"><strong>Colonna</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-106"><strong>Column</strong></span></span></th>
<th><span data-ttu-id="41c84-107"><strong>Tipo di dati</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-107"><strong>Data Type</strong></span></span></th>
<th><span data-ttu-id="41c84-108"><strong>Chiave/indice</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-108"><strong>Key/Index</strong></span></span></th>
<th><span data-ttu-id="41c84-109"><strong>Dettagli</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-109"><strong>Details</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="41c84-110"><strong>ConferenceDateTime</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-110"><strong>ConferenceDateTime</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-111">dateTime</span><span class="sxs-lookup"><span data-stu-id="41c84-111">dateTime</span></span></p></td>
<td><p><span data-ttu-id="41c84-112">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="41c84-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="41c84-113">Data e ora di inizio della sessione.</span><span class="sxs-lookup"><span data-stu-id="41c84-113">Date and time that the session started.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-114"><strong>SessionSeq</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-114"><strong>SessionSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-115">int</span><span class="sxs-lookup"><span data-stu-id="41c84-115">int</span></span></p></td>
<td><p><span data-ttu-id="41c84-116">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="41c84-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="41c84-117">Identificatore sequenziale usato per distinguere tra le sessioni avviate nella stessa data e contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="41c84-117">Sequential identifier used to distinguish between sessions that started on the same date and at the same time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-118"><strong>MediaLineLabel</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-118"><strong>MediaLineLabel</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-119">tinyint</span><span class="sxs-lookup"><span data-stu-id="41c84-119">tinyint</span></span></p></td>
<td><p><span data-ttu-id="41c84-120">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="41c84-120">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="41c84-121">Rappresenta il tipo di linea video usato nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="41c84-121">Represents the type of video line used in the call.</span></span> <span data-ttu-id="41c84-122">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="41c84-122">Allowed values are:</span></span></p>
<ul>
<li><p><span data-ttu-id="41c84-123">0-audio</span><span class="sxs-lookup"><span data-stu-id="41c84-123">0 – Audio</span></span></p></li>
<li><p><span data-ttu-id="41c84-124">1-video</span><span class="sxs-lookup"><span data-stu-id="41c84-124">1 – Video</span></span></p></li>
<li><p><span data-ttu-id="41c84-125">2-video panoramico</span><span class="sxs-lookup"><span data-stu-id="41c84-125">2 – Panoramic video</span></span></p></li>
<li><p><span data-ttu-id="41c84-126">3-condivisione di applicazioni/desktop</span><span class="sxs-lookup"><span data-stu-id="41c84-126">3 –Application/Desktop Sharing</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-127"><strong>StreamID</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-127"><strong>StreamID</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-128">int</span><span class="sxs-lookup"><span data-stu-id="41c84-128">int</span></span></p></td>
<td><p><span data-ttu-id="41c84-129">Principale</span><span class="sxs-lookup"><span data-stu-id="41c84-129">Primary</span></span></p></td>
<td><p><span data-ttu-id="41c84-130">Identificatore univoco del flusso di condivisione dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="41c84-130">Unique identifier of the application sharing stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-131"><strong>JitterInterArrival</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-131"><strong>JitterInterArrival</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-132">int</span><span class="sxs-lookup"><span data-stu-id="41c84-132">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-133">Jitter medio rilevato tra gli arrivi del pacchetto RTP.</span><span class="sxs-lookup"><span data-stu-id="41c84-133">Average jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="41c84-134">(Jitter è una misura della &quot;shakiness&quot; di una chiamata.) I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.</span><span class="sxs-lookup"><span data-stu-id="41c84-134">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-135"><strong>JitterInterArrivalMax</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-135"><strong>JitterInterArrivalMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-136">int</span><span class="sxs-lookup"><span data-stu-id="41c84-136">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-137">Jitter massimo rilevato tra gli arrivi del pacchetto RTP.</span><span class="sxs-lookup"><span data-stu-id="41c84-137">Maximum jitter detected between RTP packet arrivals.</span></span> <span data-ttu-id="41c84-138">(Jitter è una misura della &quot;shakiness&quot; di una chiamata.) I valori di jitter elevato sono in genere causati dalla congestione o da un server multimediale di overload e generano audio distorte o perse.</span><span class="sxs-lookup"><span data-stu-id="41c84-138">(Jitter is a measure of the &quot;shakiness&quot; of a call.) High jitter values are typically caused by congestion or an overloaded media server, and result in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-139"><strong>RoundTrip</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-139"><strong>RoundTrip</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-140">int</span><span class="sxs-lookup"><span data-stu-id="41c84-140">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-141">Importo medio (in millisecondi) richiesto per un pacchetto di protocollo di trasporto in tempo reale per spostarsi in un altro endpoint e quindi viceversa.</span><span class="sxs-lookup"><span data-stu-id="41c84-141">Average amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="41c84-142">I tempi di andata e ritorno di 200 millisecondi sono considerati di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="41c84-142">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="41c84-143">I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali; una configurazione errata di routing; o un server multimediale in overload.</span><span class="sxs-lookup"><span data-stu-id="41c84-143">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="41c84-144">Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.</span><span class="sxs-lookup"><span data-stu-id="41c84-144">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-145"><strong>RoundTripMax</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-145"><strong>RoundTripMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-146">int</span><span class="sxs-lookup"><span data-stu-id="41c84-146">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-147">Importo massimo (in millisecondi) necessario per un pacchetto di protocollo di trasporto in tempo reale per spostarsi in un altro endpoint e quindi viceversa.</span><span class="sxs-lookup"><span data-stu-id="41c84-147">Maximum amount of (in milliseconds) required for a Real-Time Transport Protocol packet to travel to another endpoint and then back.</span></span> <span data-ttu-id="41c84-148">I tempi di andata e ritorno di 200 millisecondi sono considerati di qualità accettabile.</span><span class="sxs-lookup"><span data-stu-id="41c84-148">Round-trip times of 200 milliseconds or less are considered of acceptable quality.</span></span></p>
<p><span data-ttu-id="41c84-149">I valori alti di andata e ritorno possono essere causati da routing delle chiamate internazionali; una configurazione errata di routing; o un server multimediale in overload.</span><span class="sxs-lookup"><span data-stu-id="41c84-149">High round-trip values can be caused by international call routing; a routing misconfiguration; or an overloaded media server.</span></span> <span data-ttu-id="41c84-150">Gli alti tempi di andata e ritorno si verificano in difficoltà con le conversazioni audio in tempo reale a due vie.</span><span class="sxs-lookup"><span data-stu-id="41c84-150">High round-trip times result in difficulties with two-way, real-time audio conversations.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-151"><strong>PacketLossRate</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-151"><strong>PacketLossRate</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-152">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-152">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-153">Tasso medio di perdita di pacchetti RTP (Real-Time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="41c84-153">Average rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="41c84-154">La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione; mancanza di larghezza di banda; congestione o interferenza wireless; o un server multimediale in overload.</span><span class="sxs-lookup"><span data-stu-id="41c84-154">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="41c84-155">La perdita di pacchetti in genere genera un audio distorta o perso.</span><span class="sxs-lookup"><span data-stu-id="41c84-155">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-156"><strong>PacketLossRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-156"><strong>PacketLossRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-157">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-157">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-158">Tasso massimo di perdita di pacchetti RTP (Real-Time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="41c84-158">Maximum rate of Real-Time Transport Protocol (RTP) packet loss.</span></span> <span data-ttu-id="41c84-159">La perdita di pacchetti si verifica quando i pacchetti RTP, un protocollo usato per la trasmissione di audio e video su Internet, non riescono a raggiungere la destinazione. I tassi di perdita elevati sono in genere causati dalla congestione; mancanza di larghezza di banda; congestione o interferenza wireless; o un server multimediale in overload.</span><span class="sxs-lookup"><span data-stu-id="41c84-159">(Packet loss occurs when RTP packets, a protocol used for transmitting audio and video across the Internet, failed to reach their destination.) High loss rates are generally caused by congestion; lack of bandwidth; wireless congestion or interference; or an overloaded media server.</span></span> <span data-ttu-id="41c84-160">La perdita di pacchetti in genere genera un audio distorta o perso.</span><span class="sxs-lookup"><span data-stu-id="41c84-160">Packet loss typically results in distorted or lost audio.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-161"><strong>PacketUtilization</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-161"><strong>PacketUtilization</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-162">int</span><span class="sxs-lookup"><span data-stu-id="41c84-162">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-163">Numero di pacchetti inviati.</span><span class="sxs-lookup"><span data-stu-id="41c84-163">Number of packets sent.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-164"><strong>Larghezza di banda più ampia</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-164"><strong>BandwidthEst</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-165">int</span><span class="sxs-lookup"><span data-stu-id="41c84-165">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-166">Larghezza di banda unidirezionale stimata disponibile alla fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="41c84-166">Estimated one-way bandwidth available at the end of the session.</span></span> <span data-ttu-id="41c84-167">Segnalati in bit al secondo.</span><span class="sxs-lookup"><span data-stu-id="41c84-167">Reported in bits per second.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-168"><strong>AppSharingPayloadDescription</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-168"><strong>AppSharingPayloadDescription</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-169">int</span><span class="sxs-lookup"><span data-stu-id="41c84-169">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-170">Descrizione del payload di condivisione applicazioni.</span><span class="sxs-lookup"><span data-stu-id="41c84-170">Description of the application sharing payload.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-171"><strong>RelativeOneWayTotal</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-171"><strong>RelativeOneWayTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-172">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-172">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-173">Importo totale della latenza unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="41c84-173">Total amount of one-way latency.</span></span> <span data-ttu-id="41c84-174">La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="41c84-174">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-175"><strong>RelativeOneWayAverage</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-175"><strong>RelativeOneWayAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-176">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-176">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-177">Importo medio della latenza unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="41c84-177">Average amount of one-way latency.</span></span> <span data-ttu-id="41c84-178">La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="41c84-178">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-179"><strong>RelativeOneWayMax</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-179"><strong>RelativeOneWayMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-180">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-180">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-181">Importo massimo della latenza unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="41c84-181">Maximum amount of one-way latency.</span></span> <span data-ttu-id="41c84-182">La latenza unidirezionale relativa misura il ritardo tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="41c84-182">Relative one-way latency measures the delay between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-183"><strong>RelativeOneWayBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-183"><strong>RelativeOneWayBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-184">int</span><span class="sxs-lookup"><span data-stu-id="41c84-184">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-185">Occorrenze totali di burst unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="41c84-185">Total one-way burst occurrences.</span></span> <span data-ttu-id="41c84-186">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.</span><span class="sxs-lookup"><span data-stu-id="41c84-186">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="41c84-187">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="41c84-187">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-188"><strong>RelativeOneWayBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-188"><strong>RelativeOneWayBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-189">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-189">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-190">Densità totale burst unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="41c84-190">Total one-way burst density.</span></span> <span data-ttu-id="41c84-191">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.</span><span class="sxs-lookup"><span data-stu-id="41c84-191">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="41c84-192">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="41c84-192">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-193"><strong>RelativeOneWayBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-193"><strong>RelativeOneWayBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-194">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-194">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-195">Totale durata burst unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="41c84-195">Total one-way burst duration.</span></span> <span data-ttu-id="41c84-196">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.</span><span class="sxs-lookup"><span data-stu-id="41c84-196">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span> <span data-ttu-id="41c84-197">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="41c84-197">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-198"><strong>RelativeOneWayGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-198"><strong>RelativeOneWayGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-199">int</span><span class="sxs-lookup"><span data-stu-id="41c84-199">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-200">Occorrenze totali unidirezionali Gap.</span><span class="sxs-lookup"><span data-stu-id="41c84-200">Total one-way gap occurrences.</span></span> <span data-ttu-id="41c84-201">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst.</span><span class="sxs-lookup"><span data-stu-id="41c84-201">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="41c84-202">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="41c84-202">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-203"><strong>RelativeOneWayGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-203"><strong>RelativeOneWayGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-204">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-204">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-205">Densità totale gap unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="41c84-205">Total one-way gap density.</span></span> <span data-ttu-id="41c84-206">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst.</span><span class="sxs-lookup"><span data-stu-id="41c84-206">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="41c84-207">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="41c84-207">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-208"><strong>RelativeOneWayGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-208"><strong>RelativeOneWayGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-209">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-209">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-210">Durata totale del gap unidirezionale.</span><span class="sxs-lookup"><span data-stu-id="41c84-210">Total one-way gap duration.</span></span> <span data-ttu-id="41c84-211">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante; gli spazi vuoti indicano i ritardi tra questi burst.</span><span class="sxs-lookup"><span data-stu-id="41c84-211">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream; gaps indicate delays between these bursts.</span></span> <span data-ttu-id="41c84-212">Questa metrica misura il flusso di dati tra il client e il server.</span><span class="sxs-lookup"><span data-stu-id="41c84-212">This metric measures data flow between the client and the server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-213"><strong>ApplicationSharingType</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-213"><strong>ApplicationSharingType</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-214">varChar (256)</span><span class="sxs-lookup"><span data-stu-id="41c84-214">varChar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-215">Ruolo applicazione (condivisore o visualizzatore) e tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="41c84-215">Application role (Sharer or Viewer) and content type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-216"><strong>RDPTileProcessingLatencyTotal</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-216"><strong>RDPTileProcessingLatencyTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-217">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-217">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-218">Tempo di elaborazione totale per i riquadri RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="41c84-218">Total processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="41c84-219">Un valore complessivo più elevato equivale a un ritardo più lungo nell'esperienza di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="41c84-219">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-220"><strong>RDPTileProcessingLatencyAverage</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-220"><strong>RDPTileProcessingLatencyAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-221">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-221">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-222">Tempo medio di elaborazione per i riquadri RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="41c84-222">Average processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="41c84-223">Un valore complessivo più elevato equivale a un ritardo più lungo nell'esperienza di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="41c84-223">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-224"><strong>RDPTileProcessingLatencyMax</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-224"><strong>RDPTileProcessingLatencyMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-225">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-225">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-226">Tempo di elaborazione massimo per i riquadri RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="41c84-226">Maximum processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="41c84-227">Un valore complessivo più elevato equivale a un ritardo più lungo nell'esperienza di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="41c84-227">A higher total equates to a longer delay in the viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-228"><strong>RDPTileProcessingLatencyBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-229">int</span><span class="sxs-lookup"><span data-stu-id="41c84-229">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-230">Occorrenze burst nel tempo di elaborazione per i riquadri RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="41c84-230">Burst occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="41c84-231">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.</span><span class="sxs-lookup"><span data-stu-id="41c84-231">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-232"><strong>RDPTileProcessingLatencyBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-233">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-233">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-234">Densità di burst nel tempo di elaborazione per i riquadri RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="41c84-234">Burst density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="41c84-235">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.</span><span class="sxs-lookup"><span data-stu-id="41c84-235">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-236"><strong>RDPTileProcessingLatencyBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-237">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-237">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-238">Durata burst nel tempo di elaborazione per i riquadri RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="41c84-238">Burst duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="41c84-239">Una trasmissione "bursty" è una trasmissione in cui i flussi di dati in esplosioni imprevedibili si oppongono a un flusso costante.</span><span class="sxs-lookup"><span data-stu-id="41c84-239">A “bursty” transmission is a transmission where data flows in unpredictable bursts as opposed to a steady stream.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-240"><strong>RDPTileProcessingLatencyGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-241">int</span><span class="sxs-lookup"><span data-stu-id="41c84-241">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-242">Occorrenze gap nel tempo di elaborazione per i riquadri RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="41c84-242">Gap occurrences in the processing time for remote desktop protocol (RDP) tiles.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-243"><strong>RDPTileProcessingLatencyGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-244">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-244">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-245">Densità di gap nel tempo di elaborazione per i riquadri RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="41c84-245">Gap density in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="41c84-246">La densità di Gap ridotta equivale a un'esperienza di visualizzazione migliore.</span><span class="sxs-lookup"><span data-stu-id="41c84-246">Low gap density equates to a better viewing experience.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-247"><strong>RDPTileProcessingLatencyGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-248">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-248">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-249">Durata gap nel tempo di elaborazione per i riquadri RDP (Remote Desktop Protocol).</span><span class="sxs-lookup"><span data-stu-id="41c84-249">Gap duration in the processing time for remote desktop protocol (RDP) tiles.</span></span> <span data-ttu-id="41c84-250">La durata del gap breve equivale a una migliore esperienza di visualizzazione.</span><span class="sxs-lookup"><span data-stu-id="41c84-250">Short gap durations equate to a better viewing experience.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-251"><strong>CaptureTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-251"><strong>CaptureTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-252">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-252">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-253">Tasso totale dei riquadri acquisiti (in riquadri al secondo).</span><span class="sxs-lookup"><span data-stu-id="41c84-253">Total rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-254"><strong>CaptureTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-254"><strong>CaptureTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-255">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-255">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-256">Tasso medio dei riquadri acquisiti (in riquadri al secondo).</span><span class="sxs-lookup"><span data-stu-id="41c84-256">Average rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-257"><strong>CaptureTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-257"><strong>CaptureTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-258">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-258">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-259">Tasso massimo dei riquadri acquisiti (in riquadri al secondo).</span><span class="sxs-lookup"><span data-stu-id="41c84-259">Maximum rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-260"><strong>CaptureTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-260"><strong>CaptureTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-261">in t</span><span class="sxs-lookup"><span data-stu-id="41c84-261">in t</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-262">Occorrenze di burst nella frequenza dei riquadri acquisiti (in riquadri al secondo).</span><span class="sxs-lookup"><span data-stu-id="41c84-262">Burst occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-263"><strong>CaptureTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-263"><strong>CaptureTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-264">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-264">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-265">Densità di burst nella frequenza dei riquadri acquisiti (in riquadri al secondo).</span><span class="sxs-lookup"><span data-stu-id="41c84-265">Burst density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-266"><strong>CaptureTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-266"><strong>CaptureTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-267">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-267">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-268">Durata burst nella frequenza dei riquadri acquisiti (in riquadri al secondo).</span><span class="sxs-lookup"><span data-stu-id="41c84-268">Burst duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-269"><strong>CaptureTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-269"><strong>CaptureTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-270">int</span><span class="sxs-lookup"><span data-stu-id="41c84-270">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-271">Occorrenze gap nella frequenza dei riquadri acquisiti (in riquadri al secondo).</span><span class="sxs-lookup"><span data-stu-id="41c84-271">Gap occurrences in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-272"><strong>CaptureTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-272"><strong>CaptureTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-273">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-273">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-274">Densità di gap nella frequenza dei riquadri acquisiti (in riquadri al secondo).</span><span class="sxs-lookup"><span data-stu-id="41c84-274">Gap density in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-275"><strong>CaptureTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-275"><strong>CaptureTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-276">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-276">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-277">Durata del gap nella frequenza dei riquadri acquisiti (in riquadri al secondo).</span><span class="sxs-lookup"><span data-stu-id="41c84-277">Gap duration in the rate of captured tiles (in tiles per second).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-278"><strong>SpoiledTilePercentTotal</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-278"><strong>SpoiledTilePercentTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-279">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-279">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-280">Percentuale totale del contenuto che non ha raggiunto il visualizzatore, ma che è stato scartato e sovrascritto da contenuto fresco.</span><span class="sxs-lookup"><span data-stu-id="41c84-280">Total percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-281"><strong>SpoiledTilePercentAverage</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-281"><strong>SpoiledTilePercentAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-282">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-282">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-283">Percentuale media del contenuto che non ha raggiunto il visualizzatore ma è stato scartato e sovrascritto da contenuto fresco.</span><span class="sxs-lookup"><span data-stu-id="41c84-283">Average percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-284"><strong>SpoiledTilePercentMax</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-284"><strong>SpoiledTilePercentMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-285">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-285">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-286">Percentuale massima del contenuto che non ha raggiunto il visualizzatore, ma che è stato scartato e sovrascritto da contenuto fresco.</span><span class="sxs-lookup"><span data-stu-id="41c84-286">Maximum percentage of the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-287"><strong>SpoiledTilePercentBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-288">int</span><span class="sxs-lookup"><span data-stu-id="41c84-288">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-289">Occorrenze burst per il contenuto che non ha raggiunto il visualizzatore, ma è stato scartato e sovrascritto da contenuto fresco.</span><span class="sxs-lookup"><span data-stu-id="41c84-289">Burst occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-290"><strong>SpoiledTilePercentBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-290"><strong>SpoiledTilePercentBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-291">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-291">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-292">Densità di burst per il contenuto che non ha raggiunto il visualizzatore, ma è stato scartato e sovrascritto da contenuto fresco.</span><span class="sxs-lookup"><span data-stu-id="41c84-292">Burst density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-293"><strong>SpoiledTilePercentBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-293"><strong>SpoiledTilePercentBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-294">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-294">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-295">Durata burst per il contenuto che non ha raggiunto il visualizzatore, ma è stato scartato e sovrascritto da contenuto fresco.</span><span class="sxs-lookup"><span data-stu-id="41c84-295">Burst duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-296"><strong>SpoiledTilePercentGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-296"><strong>SpoiledTilePercentGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-297">int</span><span class="sxs-lookup"><span data-stu-id="41c84-297">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-298">Occorrenze gap per il contenuto che non ha raggiunto il visualizzatore, ma è stato scartato e sovrascritto da contenuto fresco.</span><span class="sxs-lookup"><span data-stu-id="41c84-298">Gap occurrences for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-299"><strong>SpoiledTilePercentGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-299"><strong>SpoiledTilePercentGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-300">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-300">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-301">Densità di Gap per il contenuto che non ha raggiunto il visualizzatore, ma è stato scartato e sovrascritto da contenuto fresco.</span><span class="sxs-lookup"><span data-stu-id="41c84-301">Gap density for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-302"><strong>SpoiledTilePercentGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-302"><strong>SpoiledTilePercentGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-303">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-303">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-304">Durata gap per il contenuto che non ha raggiunto il visualizzatore, ma è stato scartato e sovrascritto da contenuto fresco.</span><span class="sxs-lookup"><span data-stu-id="41c84-304">Gap duration for the content that did not reach the viewer but was instead discarded and overwritten by fresh content.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-305"><strong>ScrapingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-305"><strong>ScrapingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-306">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-306">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-307">Numero totale di fotogrammi raschiati dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="41c84-307">Total number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-308"><strong>ScrapingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-308"><strong>ScrapingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-309">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-309">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-310">Numero medio di fotogrammi raschiati dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="41c84-310">Average number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-311"><strong>ScrapingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-311"><strong>ScrapingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-312">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-312">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-313">Numero massimo di fotogrammi raschiati dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="41c84-313">Maximum number of frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-314"><strong>ScrapingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-315">int</span><span class="sxs-lookup"><span data-stu-id="41c84-315">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-316">Occorrenze di burst nei fotogrammi raschiati dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="41c84-316">Burst occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-317"><strong>ScrapingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-317"><strong>ScrapingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-318">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-318">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-319">Densità di burst nei fotogrammi raschiati dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="41c84-319">Burst density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-320"><strong>ScrapingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-320"><strong>ScrapingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-321">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-321">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-322">Durata burst nei fotogrammi raschiati dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="41c84-322">Burst duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-323"><strong>ScrapingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-323"><strong>ScrapingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-324">int</span><span class="sxs-lookup"><span data-stu-id="41c84-324">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-325">Occorrenze gap nei fotogrammi raschiati dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="41c84-325">Gap occurrences in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-326"><strong>ScrapingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-326"><strong>ScrapingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-327">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-327">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-328">Densità di gap nei fotogrammi raschiati dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="41c84-328">Gap density in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-329"><strong>ScrapingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-329"><strong>ScrapingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-330">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-330">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-331">Durata del gap nei fotogrammi raschiati dall'origine grafica.</span><span class="sxs-lookup"><span data-stu-id="41c84-331">Gap duration in the frames scraped from the graphics source.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-332"><strong>IncomingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-332"><strong>IncomingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-333">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-333">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-334">Frequenza dei fotogrammi in arrivo totale ricevuta dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="41c84-334">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-335"><strong>IncomingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-335"><strong>IncomingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-336">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-336">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-337">Frequenza fotogrammi in arrivo media ricevuta dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="41c84-337">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-338"><strong>IncomingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-338"><strong>IncomingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-339">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-339">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-340">Numero massimo di tessere in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="41c84-340">Maximum incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-341"><strong>IncomingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-341"><strong>IncomingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-342">int</span><span class="sxs-lookup"><span data-stu-id="41c84-342">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-343">Occorrenze di burst nella frequenza delle tessere in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="41c84-343">Burst occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-344"><strong>IncomingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-344"><strong>IncomingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-345">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-345">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-346">Densità di burst nella frequenza delle tessere in arrivo ricevuta dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="41c84-346">Burst density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-347"><strong>IncomingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-347"><strong>IncomingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-348">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-348">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-349">Durata burst nella tariffa del riquadro in arrivo ricevuta dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="41c84-349">Burst duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-350"><strong>IncomingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-350"><strong>IncomingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-351">int</span><span class="sxs-lookup"><span data-stu-id="41c84-351">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-352">Occorrenze gap nella frequenza delle tessere in arrivo ricevute dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="41c84-352">Gap occurrences in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-353"><strong>IncomingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-353"><strong>IncomingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-354">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-354">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-355">Densità di gap nella frequenza delle tessere in arrivo ricevuta dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="41c84-355">Gap density in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-356"><strong>IncomingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-356"><strong>IncomingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-357">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-357">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-358">Durata del gap nella frequenza delle tessere in arrivo ricevuta dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="41c84-358">Gap duration in the incoming tile rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-359"><strong>IncomingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-359"><strong>IncomingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-360">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-360">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-361">Frequenza dei fotogrammi in arrivo totale ricevuta dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="41c84-361">Total incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-362"><strong>IncomingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-362"><strong>IncomingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-363">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-363">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-364">Frequenza fotogrammi in arrivo media ricevuta dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="41c84-364">Average incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-365"><strong>IncomingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-365"><strong>IncomingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-366">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-366">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-367">Frequenza fotogrammi in arrivo massima ricevuta dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="41c84-367">Maximum incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-368"><strong>IncomingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-368"><strong>IncomingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-369">int</span><span class="sxs-lookup"><span data-stu-id="41c84-369">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-370">Occorrenze burst nella frequenza fotogrammi in arrivo ricevuta dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="41c84-370">Burst occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-371"><strong>IncomingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-371"><strong>IncomingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-372">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-372">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-373">Densità di burst nella frequenza fotogrammi in arrivo ricevuta dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="41c84-373">Burst density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-374"><strong>IncomingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-374"><strong>IncomingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-375">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-375">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-376">Durata burst nella frequenza fotogrammi in arrivo ricevuta dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="41c84-376">Burst duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-377"><strong>IncomingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-377"><strong>IncomingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-378">int</span><span class="sxs-lookup"><span data-stu-id="41c84-378">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-379">Occorrenze gap nella frequenza fotogrammi in arrivo ricevuta dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="41c84-379">Gap occurrences in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-380"><strong>IncomingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-380"><strong>IncomingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-381">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-381">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-382">Densità di gap nella frequenza fotogrammi in arrivo ricevuta dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="41c84-382">Gap density in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-383"><strong>IncomingFrameRateDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-383"><strong>IncomingFrameRateDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-384">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-384">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-385">Durata del gap nella frequenza fotogrammi in arrivo ricevuta dal visualizzatore.</span><span class="sxs-lookup"><span data-stu-id="41c84-385">Gap duration in the incoming frame rate as received by the viewer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-386"><strong>OutgoingTileRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-386"><strong>OutgoingTileRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-387">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-387">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-388">Tasso di riquadri in uscita totale per il mittente.</span><span class="sxs-lookup"><span data-stu-id="41c84-388">Total outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-389"><strong>OutgoingTileRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-389"><strong>OutgoingTileRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-390">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-390">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-391">Tasso di riquadri in uscita medio per il mittente.</span><span class="sxs-lookup"><span data-stu-id="41c84-391">Average outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-392"><strong>OutgoingTileRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-392"><strong>OutgoingTileRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-393">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-393">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-394">Tasso di riquadri in uscita massimo per il mittente.</span><span class="sxs-lookup"><span data-stu-id="41c84-394">Maximum outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-395"><strong>OutgoingTileRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-395"><strong>OutgoingTileRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-396">int</span><span class="sxs-lookup"><span data-stu-id="41c84-396">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-397">Occorrenze di burst nella tariffa del riquadro in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="41c84-397">Burst occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-398"><strong>OutgoingTileRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-398"><strong>OutgoingTileRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-399">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-399">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-400">Densità di burst nella tariffa del riquadro in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="41c84-400">Burst density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-401"><strong>OutgoingTileRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-401"><strong>OutgoingTileRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-402">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-402">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-403">Durata burst nella tariffa del riquadro in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="41c84-403">Burst duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-404"><strong>OutgoingTileRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-404"><strong>OutgoingTileRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-405">int</span><span class="sxs-lookup"><span data-stu-id="41c84-405">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-406">Occorrenze gap nella tariffa del riquadro in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="41c84-406">Gap occurrences in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-407"><strong>OutgoingTileRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-407"><strong>OutgoingTileRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-408">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-408">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-409">Densità di gap nella tariffa del riquadro in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="41c84-409">Gap density in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-410"><strong>OutgoingTileRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-410"><strong>OutgoingTileRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-411">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-411">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-412">Durata gap nella tariffa del riquadro in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="41c84-412">Gap duration in the outgoing tile rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-413"><strong>OutgoingFrameRateTotal</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-413"><strong>OutgoingFrameRateTotal</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-414">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-414">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-415">Frequenza fotogrammi in uscita totale per il mittente.</span><span class="sxs-lookup"><span data-stu-id="41c84-415">Total outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-416"><strong>OutgoingFrameRateAverage</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-416"><strong>OutgoingFrameRateAverage</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-417">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-417">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-418">frequenza fotogrammi in uscita media per il mittente.</span><span class="sxs-lookup"><span data-stu-id="41c84-418">average outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-419"><strong>OutgoingFrameRateMax</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-419"><strong>OutgoingFrameRateMax</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-420">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-420">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-421">Frequenza fotogrammi in uscita massima per il mittente.</span><span class="sxs-lookup"><span data-stu-id="41c84-421">Maximum outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-422"><strong>OutgoingFrameRateBurstOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-423">int</span><span class="sxs-lookup"><span data-stu-id="41c84-423">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-424">Occorrenze di burst nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="41c84-424">Burst occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-425"><strong>OutgoingFrameRateBurstDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-425"><strong>OutgoingFrameRateBurstDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-426">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-426">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-427">Densità di burst nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="41c84-427">Burst density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-428"><strong>OutgoingFrameRateBurstDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-428"><strong>OutgoingFrameRateBurstDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-429">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-429">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-430">Durata burst nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="41c84-430">Burst duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-431"><strong>OutgoingFrameRateGapOccurrences</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-431"><strong>OutgoingFrameRateGapOccurrences</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-432">int</span><span class="sxs-lookup"><span data-stu-id="41c84-432">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-433">Occorrenze gap nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="41c84-433">Gap occurrences in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-434"><strong>OutgoingFrameRateGapDensity</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-434"><strong>OutgoingFrameRateGapDensity</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-435">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-435">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-436">Densità di gap nella frequenza dei fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="41c84-436">Gap density in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-437"><strong>OutgoingFrameRateGapDuration</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-437"><strong>OutgoingFrameRateGapDuration</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-438">galleggiante</span><span class="sxs-lookup"><span data-stu-id="41c84-438">float</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-439">Durata del gap nella frequenza fotogrammi in uscita per il mittente.</span><span class="sxs-lookup"><span data-stu-id="41c84-439">Gap duration in the outgoing frame rate for the sender.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-440"><strong>AverageRectangleHeight</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-440"><strong>AverageRectangleHeight</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-441">int</span><span class="sxs-lookup"><span data-stu-id="41c84-441">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-442">Altezza media di risoluzione video, in pixel.</span><span class="sxs-lookup"><span data-stu-id="41c84-442">Average video resolution height, in pixels.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-443"><strong>AverageRectangleWidth</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-443"><strong>AverageRectangleWidth</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-444">int</span><span class="sxs-lookup"><span data-stu-id="41c84-444">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-445">Larghezza media della risoluzione video in pixel.</span><span class="sxs-lookup"><span data-stu-id="41c84-445">Average video resolution width, in pixels.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-446"><strong>In ingresso</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-446"><strong>Inbound</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-447">po'</span><span class="sxs-lookup"><span data-stu-id="41c84-447">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-448">Frequenza fotogrammi media (in fotogrammi al secondo) per trasmissioni in ingresso.</span><span class="sxs-lookup"><span data-stu-id="41c84-448">Average frame rate (in frames per second) for inbound transmissions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="41c84-449"><strong>Outbound</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-449"><strong>Outbound</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-450">po'</span><span class="sxs-lookup"><span data-stu-id="41c84-450">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-451">Frequenza fotogrammi media (in fotogrammi al secondo) per trasmissioni in uscita.</span><span class="sxs-lookup"><span data-stu-id="41c84-451">Average frame rate (in frames per second) for outbound transmissions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="41c84-452"><strong>SenderIsCallerPAI</strong></span><span class="sxs-lookup"><span data-stu-id="41c84-452"><strong>SenderIsCallerPAI</strong></span></span></p></td>
<td><p><span data-ttu-id="41c84-453">po'</span><span class="sxs-lookup"><span data-stu-id="41c84-453">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="41c84-454">1 indica che la direzione del flusso è dal chiamante al chiamato.</span><span class="sxs-lookup"><span data-stu-id="41c84-454">1 means the stream direction is from the caller to callee.</span></span></p>
<p><span data-ttu-id="41c84-455">0 indica che la direzione del flusso è dal chiamato al chiamante.</span><span class="sxs-lookup"><span data-stu-id="41c84-455">0 means the stream direction is from the callee to the caller.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

