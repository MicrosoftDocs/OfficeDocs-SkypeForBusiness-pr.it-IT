---
title: 'Lync Server 2013: configurazione degli scenari di esempio video'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9800f97c8ccd49780098c29c9c6c1325b072dab5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975288"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="4708a-102">Configurazione di scenari di esempio video per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4708a-102">Configuring video example scenarios for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4708a-103">_**Argomento Ultima modifica:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="4708a-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="4708a-104">Lync 2013 aggiunge nuove funzionalità video per supportare il video della visualizzazione della raccolta e del video in alta definizione (HD) di 1920 x 1080.</span><span class="sxs-lookup"><span data-stu-id="4708a-104">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="4708a-105">Le misurazioni basate sui dati dei clienti mostrano che la larghezza di banda video tipica è aumentata solo leggermente rispetto a Lync 2010, ma la larghezza di banda massima del flusso video è aumentata a causa del supporto di Full HD (per i dettagli, vedere la sezione "utilizzo della rete del traffico multimediale" nei [requisiti di larghezza di banda per il traffico multimediale in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span><span class="sxs-lookup"><span data-stu-id="4708a-105">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="4708a-106">Gli amministratori possono pertanto limitare la larghezza di banda video per alcuni utenti, ad esempio gli utenti di una filiale con meno capacità di rete, e contribuire a garantire la migliore qualità possibile per gli altri utenti, ad esempio i dirigenti.</span><span class="sxs-lookup"><span data-stu-id="4708a-106">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="4708a-107">La tabella seguente contiene un elenco di impostazioni consigliate per la configurazione di video per diverse capacità di rete.</span><span class="sxs-lookup"><span data-stu-id="4708a-107">The following table provides a list of recommended settings for configuring video for different network capacities.</span></span> <span data-ttu-id="4708a-108">Queste impostazioni limitano alcuni scenari utente all'invio e alla ricezione di video con risoluzione superiore (vedi colonna più a destra).</span><span class="sxs-lookup"><span data-stu-id="4708a-108">These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column).</span></span> <span data-ttu-id="4708a-109">L'impostazione minima consentirà di ottenere un video della raccolta non disponibile, a causa della larghezza di banda massima di ricezione della rete.</span><span class="sxs-lookup"><span data-stu-id="4708a-109">The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="4708a-110">Impostazioni video consigliate</span><span class="sxs-lookup"><span data-stu-id="4708a-110">Recommended Video Settings</span></span>

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th>-</th>
<th><span data-ttu-id="4708a-111">AllowMultiView</span><span class="sxs-lookup"><span data-stu-id="4708a-111">AllowMultiView</span></span></th>
<th><span data-ttu-id="4708a-112">EnableMultiViewJoin</span><span class="sxs-lookup"><span data-stu-id="4708a-112">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="4708a-113">VideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="4708a-113">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="4708a-114">TotalReceiveVideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="4708a-114">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="4708a-115">Risoluzione video prevista per un video di qualità ottimale</span><span class="sxs-lookup"><span data-stu-id="4708a-115">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4708a-116">Procedure</span><span class="sxs-lookup"><span data-stu-id="4708a-116">Best</span></span></p></td>
<td><p><span data-ttu-id="4708a-117">True</span><span class="sxs-lookup"><span data-stu-id="4708a-117">True</span></span></p></td>
<td><p><span data-ttu-id="4708a-118">True</span><span class="sxs-lookup"><span data-stu-id="4708a-118">True</span></span></p></td>
<td><p><span data-ttu-id="4708a-119">8000</span><span class="sxs-lookup"><span data-stu-id="4708a-119">8000</span></span></p></td>
<td><p><span data-ttu-id="4708a-120">8000</span><span class="sxs-lookup"><span data-stu-id="4708a-120">8000</span></span></p></td>
<td><p><span data-ttu-id="4708a-121">Peer-to-peer: risoluzione video fino a 1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="4708a-121">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="4708a-122">Visualizzazione raccolta: fino a 2 1920 x 1080 video o più video di risoluzione più piccoli</span><span class="sxs-lookup"><span data-stu-id="4708a-122">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4708a-123">Good</span><span class="sxs-lookup"><span data-stu-id="4708a-123">Good</span></span></p></td>
<td><p><span data-ttu-id="4708a-124">True</span><span class="sxs-lookup"><span data-stu-id="4708a-124">True</span></span></p></td>
<td><p><span data-ttu-id="4708a-125">True</span><span class="sxs-lookup"><span data-stu-id="4708a-125">True</span></span></p></td>
<td><p><span data-ttu-id="4708a-126">2500</span><span class="sxs-lookup"><span data-stu-id="4708a-126">2500</span></span></p></td>
<td><p><span data-ttu-id="4708a-127">2500</span><span class="sxs-lookup"><span data-stu-id="4708a-127">2500</span></span></p></td>
<td><p><span data-ttu-id="4708a-128">Peer-to-peer: risoluzione video fino a 1280 x 720</span><span class="sxs-lookup"><span data-stu-id="4708a-128">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="4708a-129">Visualizzazione raccolta: fino a 5 640 x 360 risoluzione video</span><span class="sxs-lookup"><span data-stu-id="4708a-129">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4708a-130">Media</span><span class="sxs-lookup"><span data-stu-id="4708a-130">Medium</span></span></p></td>
<td><p><span data-ttu-id="4708a-131">True</span><span class="sxs-lookup"><span data-stu-id="4708a-131">True</span></span></p></td>
<td><p><span data-ttu-id="4708a-132">True</span><span class="sxs-lookup"><span data-stu-id="4708a-132">True</span></span></p></td>
<td><p><span data-ttu-id="4708a-133">1000</span><span class="sxs-lookup"><span data-stu-id="4708a-133">1000</span></span></p></td>
<td><p><span data-ttu-id="4708a-134">1000</span><span class="sxs-lookup"><span data-stu-id="4708a-134">1000</span></span></p></td>
<td><p><span data-ttu-id="4708a-135">Peer-to-peer: risoluzione video fino a 960 x 540</span><span class="sxs-lookup"><span data-stu-id="4708a-135">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="4708a-136">Visualizzazione raccolta: fino a 5 424 x 240 risoluzione video</span><span class="sxs-lookup"><span data-stu-id="4708a-136">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4708a-137">Minimo</span><span class="sxs-lookup"><span data-stu-id="4708a-137">Minimum</span></span></p></td>
<td><p><span data-ttu-id="4708a-138">True</span><span class="sxs-lookup"><span data-stu-id="4708a-138">True</span></span></p></td>
<td><p><span data-ttu-id="4708a-139">False</span><span class="sxs-lookup"><span data-stu-id="4708a-139">False</span></span></p></td>
<td><p><span data-ttu-id="4708a-140">350</span><span class="sxs-lookup"><span data-stu-id="4708a-140">350</span></span></p></td>
<td><p><span data-ttu-id="4708a-141">350</span><span class="sxs-lookup"><span data-stu-id="4708a-141">350</span></span></p></td>
<td><p><span data-ttu-id="4708a-142">Peer-to-peer: risoluzione video fino a 424 x 240</span><span class="sxs-lookup"><span data-stu-id="4708a-142">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="4708a-143">Visualizzazione raccolta: non disponibile</span><span class="sxs-lookup"><span data-stu-id="4708a-143">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4708a-144">È possibile usare le informazioni nella tabella precedente per distribuire le nuove caratteristiche di conferenza video e video HD per alcuni utenti dell'organizzazione, consentendo di risoluzioni video diverse per gli altri.</span><span class="sxs-lookup"><span data-stu-id="4708a-144">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="4708a-145">Nell'esempio seguente l'amministratore esegue il rollback delle nuove caratteristiche video con la qualità video più alta disponibile solo per i dirigenti.</span><span class="sxs-lookup"><span data-stu-id="4708a-145">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives.</span></span> <span data-ttu-id="4708a-146">Per i dipendenti in una filiale remota con capacità di rete ridotta, viene distribuita solo l'impostazione minima della tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="4708a-146">For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed.</span></span> <span data-ttu-id="4708a-147">Per tutti gli altri dipendenti, viene distribuita l'impostazione "buona" della tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="4708a-147">For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="4708a-148">Per implementare le nuove funzionalità per i dirigenti, l'amministratore crea un criterio per le conferenze denominato ExecutiveVideo.</span><span class="sxs-lookup"><span data-stu-id="4708a-148">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo.</span></span> <span data-ttu-id="4708a-149">I criteri per i servizi di conferenza includono le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4708a-149">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="4708a-150">VideoBitRateKB è impostato su 8000 kbps</span><span class="sxs-lookup"><span data-stu-id="4708a-150">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="4708a-151">TotalReceiveVideoBitRateKB è impostato su 8000 kbps</span><span class="sxs-lookup"><span data-stu-id="4708a-151">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="4708a-152">AllowMultiview è impostato su true</span><span class="sxs-lookup"><span data-stu-id="4708a-152">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="4708a-153">EnableMultiviewJoin è impostato su true</span><span class="sxs-lookup"><span data-stu-id="4708a-153">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="4708a-154">Per i dipendenti della filiale, l'amministratore crea un criterio per i servizi di conferenza denominato BranchOfficeVideo.</span><span class="sxs-lookup"><span data-stu-id="4708a-154">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo.</span></span> <span data-ttu-id="4708a-155">I criteri per i servizi di conferenza includono le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4708a-155">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="4708a-156">VideoBitRateKB è impostato su 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="4708a-156">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="4708a-157">TotalReceiveVideoBitRateKB è impostato su 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="4708a-157">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="4708a-158">AllowMultiview è impostato su true</span><span class="sxs-lookup"><span data-stu-id="4708a-158">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="4708a-159">EnableMultiviewJoin è impostato su false</span><span class="sxs-lookup"><span data-stu-id="4708a-159">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="4708a-160">Per tutti gli altri dipendenti, l'amministratore crea un criterio per i servizi di conferenza denominato StandardVideo.</span><span class="sxs-lookup"><span data-stu-id="4708a-160">For all other employees, the administrator creates a conferencing policy named StandardVideo.</span></span> <span data-ttu-id="4708a-161">I criteri per i servizi di conferenza includono le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4708a-161">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="4708a-162">VideoBitRateKB è impostato su 2500 kbps</span><span class="sxs-lookup"><span data-stu-id="4708a-162">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="4708a-163">TotalReceiveVideoBitRateKB è impostato su 2500 kbps</span><span class="sxs-lookup"><span data-stu-id="4708a-163">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="4708a-164">AllowMultiview è impostato su true</span><span class="sxs-lookup"><span data-stu-id="4708a-164">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="4708a-165">EnableMultiviewJoin è impostato su true</span><span class="sxs-lookup"><span data-stu-id="4708a-165">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="4708a-166">L'amministratore assegna i criteri di conferenza agli utenti come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4708a-166">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="4708a-167">I criteri di conferenza ExecutiveVideo sono assegnati ai dirigenti.</span><span class="sxs-lookup"><span data-stu-id="4708a-167">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="4708a-168">I criteri di conferenza BranchOfficeVideo sono assegnati a tutti i dipendenti della filiale.</span><span class="sxs-lookup"><span data-stu-id="4708a-168">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="4708a-169">I criteri di conferenza StandardVideo sono assegnati a tutti gli altri dipendenti.</span><span class="sxs-lookup"><span data-stu-id="4708a-169">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="4708a-170">Queste assegnazioni dei criteri di conferenza generano l'esperienza utente seguente:</span><span class="sxs-lookup"><span data-stu-id="4708a-170">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="4708a-171">Tutte le conferenze organizzate da qualsiasi visualizzazione della raccolta di supporto utenti, ma i dipendenti della filiale non possono provare la visualizzazione della raccolta.</span><span class="sxs-lookup"><span data-stu-id="4708a-171">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="4708a-172">Per tutte le conferenze a due o più partecipanti, i dirigenti possono inviare video Full HD di 1920 x 1080, se l'hardware e il collegamento di rete lo supportano e possono ricevere il video completo di 1920 x 1080 in cui gli altri client partecipanti lo supportano.</span><span class="sxs-lookup"><span data-stu-id="4708a-172">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="4708a-173">I dipendenti che non sono dirigenti sperimentano risoluzioni più basse rispetto ai dirigenti delle conferenze a due o più partecipanti, ma ottengono comunque una buona risoluzione.</span><span class="sxs-lookup"><span data-stu-id="4708a-173">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="4708a-174">I dipendenti che si trovano nella filiale otterranno una qualità video ottimale nelle chiamate in due parti quando Lync Visualizza le dimensioni predefinite della finestra del video. Tuttavia, se la finestra di Lync è ingrandita a schermo intero, la risoluzione del video non aumenta.</span><span class="sxs-lookup"><span data-stu-id="4708a-174">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="4708a-175">Per le conferenze multiparte, i dipendenti della filiale vedranno solo un video attivo.</span><span class="sxs-lookup"><span data-stu-id="4708a-175">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

