---
title: 'Lync Server 2013: configurazione degli scenari di esempio video'
description: 'Lync Server 2013: configurazione degli scenari di esempio video.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring video example scenarios
ms:assetid: da0d61a2-7ac4-4562-bf6a-18473a29acb2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205297(v=OCS.15)
ms:contentKeyID: 48185536
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 625899887926de9afe2e6ff94df70ab725c0190a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575142"
---
# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="bb324-103">Configurazione di scenari di esempio video per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bb324-103">Configuring video example scenarios for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bb324-104">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="bb324-104">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="bb324-105">Lync 2013 aggiunge nuove funzionalità video per il supporto del video per la visualizzazione di video e raccolta di 1920 x 1080 Full High Definition (HD).</span><span class="sxs-lookup"><span data-stu-id="bb324-105">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="bb324-106">Le misure basate sui dati dei clienti mostrano che la larghezza di banda video tipica è aumentata solo leggermente rispetto a Lync 2010, ma la larghezza di banda massima del flusso video è aumentata a causa del supporto di Full HD (per informazioni dettagliate, vedere la sezione "utilizzo di Network Traffic media" nei [requisiti di larghezza di banda di rete per il traffico multimediale in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span><span class="sxs-lookup"><span data-stu-id="bb324-106">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="bb324-107">Gli amministratori possono quindi limitare la larghezza di banda video per determinati utenti, ad esempio gli utenti in una succursale con meno capacità di rete, e contribuire a garantire la migliore qualità video possibile per gli altri utenti, ad esempio i dirigenti.</span><span class="sxs-lookup"><span data-stu-id="bb324-107">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="bb324-108">Nella tabella seguente viene fornito un elenco delle impostazioni consigliate per la configurazione di video per le diverse capacità di rete.</span><span class="sxs-lookup"><span data-stu-id="bb324-108">The following table provides a list of recommended settings for configuring video for different network capacities.</span></span> <span data-ttu-id="bb324-109">Queste impostazioni impediscono ad alcuni scenari degli utenti di inviare e ricevere video con risoluzione superiore (vedere la colonna a destra).</span><span class="sxs-lookup"><span data-stu-id="bb324-109">These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column).</span></span> <span data-ttu-id="bb324-110">L'impostazione minima consentirà la mancata disponibilità del video della raccolta a causa della larghezza di banda massima della rete di ricezione.</span><span class="sxs-lookup"><span data-stu-id="bb324-110">The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="bb324-111">Impostazioni video consigliate</span><span class="sxs-lookup"><span data-stu-id="bb324-111">Recommended Video Settings</span></span>

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
<th><span data-ttu-id="bb324-112">AllowMultiView</span><span class="sxs-lookup"><span data-stu-id="bb324-112">AllowMultiView</span></span></th>
<th><span data-ttu-id="bb324-113">EnableMultiViewJoin</span><span class="sxs-lookup"><span data-stu-id="bb324-113">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="bb324-114">VideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="bb324-114">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="bb324-115">TotalReceiveVideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="bb324-115">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="bb324-116">Risoluzione video prevista per un video di qualità buona</span><span class="sxs-lookup"><span data-stu-id="bb324-116">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bb324-117">Elevate</span><span class="sxs-lookup"><span data-stu-id="bb324-117">Best</span></span></p></td>
<td><p><span data-ttu-id="bb324-118">True</span><span class="sxs-lookup"><span data-stu-id="bb324-118">True</span></span></p></td>
<td><p><span data-ttu-id="bb324-119">True</span><span class="sxs-lookup"><span data-stu-id="bb324-119">True</span></span></p></td>
<td><p><span data-ttu-id="bb324-120">8000</span><span class="sxs-lookup"><span data-stu-id="bb324-120">8000</span></span></p></td>
<td><p><span data-ttu-id="bb324-121">8000</span><span class="sxs-lookup"><span data-stu-id="bb324-121">8000</span></span></p></td>
<td><p><span data-ttu-id="bb324-122">Risoluzione video peer-to-peer: fino a 1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="bb324-122">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="bb324-123">Visualizzazione raccolta: fino a 2 1920 x 1080 video o più video con risoluzione più piccola</span><span class="sxs-lookup"><span data-stu-id="bb324-123">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb324-124">Buone</span><span class="sxs-lookup"><span data-stu-id="bb324-124">Good</span></span></p></td>
<td><p><span data-ttu-id="bb324-125">True</span><span class="sxs-lookup"><span data-stu-id="bb324-125">True</span></span></p></td>
<td><p><span data-ttu-id="bb324-126">True</span><span class="sxs-lookup"><span data-stu-id="bb324-126">True</span></span></p></td>
<td><p><span data-ttu-id="bb324-127">2500</span><span class="sxs-lookup"><span data-stu-id="bb324-127">2500</span></span></p></td>
<td><p><span data-ttu-id="bb324-128">2500</span><span class="sxs-lookup"><span data-stu-id="bb324-128">2500</span></span></p></td>
<td><p><span data-ttu-id="bb324-129">Risoluzione video peer-to-peer: fino a 1280 x 720</span><span class="sxs-lookup"><span data-stu-id="bb324-129">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="bb324-130">Visualizzazione raccolta: fino a 5 640 x 360 risoluzione video</span><span class="sxs-lookup"><span data-stu-id="bb324-130">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bb324-131">Media</span><span class="sxs-lookup"><span data-stu-id="bb324-131">Medium</span></span></p></td>
<td><p><span data-ttu-id="bb324-132">True</span><span class="sxs-lookup"><span data-stu-id="bb324-132">True</span></span></p></td>
<td><p><span data-ttu-id="bb324-133">True</span><span class="sxs-lookup"><span data-stu-id="bb324-133">True</span></span></p></td>
<td><p><span data-ttu-id="bb324-134">1000</span><span class="sxs-lookup"><span data-stu-id="bb324-134">1000</span></span></p></td>
<td><p><span data-ttu-id="bb324-135">1000</span><span class="sxs-lookup"><span data-stu-id="bb324-135">1000</span></span></p></td>
<td><p><span data-ttu-id="bb324-136">Risoluzione video peer-to-peer: fino a 960 x 540</span><span class="sxs-lookup"><span data-stu-id="bb324-136">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="bb324-137">Visualizzazione raccolta: fino a 5 424 x 240 risoluzione video</span><span class="sxs-lookup"><span data-stu-id="bb324-137">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bb324-138">Minimo</span><span class="sxs-lookup"><span data-stu-id="bb324-138">Minimum</span></span></p></td>
<td><p><span data-ttu-id="bb324-139">Vero</span><span class="sxs-lookup"><span data-stu-id="bb324-139">True</span></span></p></td>
<td><p><span data-ttu-id="bb324-140">False</span><span class="sxs-lookup"><span data-stu-id="bb324-140">False</span></span></p></td>
<td><p><span data-ttu-id="bb324-141">350</span><span class="sxs-lookup"><span data-stu-id="bb324-141">350</span></span></p></td>
<td><p><span data-ttu-id="bb324-142">350</span><span class="sxs-lookup"><span data-stu-id="bb324-142">350</span></span></p></td>
<td><p><span data-ttu-id="bb324-143">Risoluzione video peer-to-peer: fino a 424 x 240</span><span class="sxs-lookup"><span data-stu-id="bb324-143">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="bb324-144">Visualizzazione raccolta: non disponibile</span><span class="sxs-lookup"><span data-stu-id="bb324-144">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="bb324-145">È possibile utilizzare le informazioni contenute nella tabella precedente per distribuire le nuove funzionalità di conferenza video HD e visualizzazione raccolta per alcuni utenti dell'organizzazione, consentendo di risoluzioni video diverse per gli altri.</span><span class="sxs-lookup"><span data-stu-id="bb324-145">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="bb324-146">Nell'esempio seguente, l'amministratore esegue il rollback delle nuove funzionalità video con la qualità video più alta disponibile solo per i dirigenti.</span><span class="sxs-lookup"><span data-stu-id="bb324-146">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives.</span></span> <span data-ttu-id="bb324-147">Per i dipendenti di una filiale remota con capacità di rete ridotta, viene distribuita solo l'impostazione minima della tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="bb324-147">For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed.</span></span> <span data-ttu-id="bb324-148">Per tutti gli altri dipendenti, viene distribuita l'impostazione "buona" dalla tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="bb324-148">For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="bb324-149">Per implementare le nuove funzionalità ai dirigenti, l'amministratore crea un criterio di conferenza denominato ExecutiveVideo.</span><span class="sxs-lookup"><span data-stu-id="bb324-149">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo.</span></span> <span data-ttu-id="bb324-150">I criteri di conferenza sono disponibili nelle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb324-150">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="bb324-151">VideoBitRateKB è impostato su 8000 kbps</span><span class="sxs-lookup"><span data-stu-id="bb324-151">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="bb324-152">TotalReceiveVideoBitRateKB è impostato su 8000 kbps</span><span class="sxs-lookup"><span data-stu-id="bb324-152">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="bb324-153">AllowMultiview è impostato su true</span><span class="sxs-lookup"><span data-stu-id="bb324-153">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="bb324-154">EnableMultiviewJoin è impostato su true</span><span class="sxs-lookup"><span data-stu-id="bb324-154">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="bb324-155">Per i dipendenti della succursale, l'amministratore crea un criterio di conferenza denominato BranchOfficeVideo.</span><span class="sxs-lookup"><span data-stu-id="bb324-155">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo.</span></span> <span data-ttu-id="bb324-156">I criteri di conferenza sono disponibili nelle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb324-156">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="bb324-157">VideoBitRateKB è impostato su 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="bb324-157">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="bb324-158">TotalReceiveVideoBitRateKB è impostato su 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="bb324-158">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="bb324-159">AllowMultiview è impostato su true</span><span class="sxs-lookup"><span data-stu-id="bb324-159">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="bb324-160">EnableMultiviewJoin è impostato su false</span><span class="sxs-lookup"><span data-stu-id="bb324-160">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="bb324-161">Per tutti gli altri dipendenti, l'amministratore crea un criterio di conferenza denominato StandardVideo.</span><span class="sxs-lookup"><span data-stu-id="bb324-161">For all other employees, the administrator creates a conferencing policy named StandardVideo.</span></span> <span data-ttu-id="bb324-162">I criteri di conferenza sono disponibili nelle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb324-162">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="bb324-163">VideoBitRateKB è impostato su 2500 kbps</span><span class="sxs-lookup"><span data-stu-id="bb324-163">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="bb324-164">TotalReceiveVideoBitRateKB è impostato su 2500 kbps</span><span class="sxs-lookup"><span data-stu-id="bb324-164">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="bb324-165">AllowMultiview è impostato su true</span><span class="sxs-lookup"><span data-stu-id="bb324-165">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="bb324-166">EnableMultiviewJoin è impostato su true</span><span class="sxs-lookup"><span data-stu-id="bb324-166">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="bb324-167">L'amministratore assegna i criteri di conferenza agli utenti, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="bb324-167">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="bb324-168">I criteri di conferenza di ExecutiveVideo sono assegnati ai dirigenti.</span><span class="sxs-lookup"><span data-stu-id="bb324-168">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="bb324-169">Il criterio di conferenza BranchOfficeVideo viene assegnato a tutti i dipendenti della succursale.</span><span class="sxs-lookup"><span data-stu-id="bb324-169">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="bb324-170">Il criterio di conferenza StandardVideo viene assegnato a tutti gli altri dipendenti.</span><span class="sxs-lookup"><span data-stu-id="bb324-170">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="bb324-171">Queste assegnazioni dei criteri di conferenza determinano l'esperienza utente seguente:</span><span class="sxs-lookup"><span data-stu-id="bb324-171">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="bb324-172">Tutte le conferenze organizzate da qualsiasi visualizzazione raccolta supporto utenti, ma i dipendenti della succursale non possono sperimentare la visualizzazione della raccolta.</span><span class="sxs-lookup"><span data-stu-id="bb324-172">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="bb324-173">Per tutte le conferenze a due o più parti, i dirigenti possono inviare video Full HD 1920 x 1080, se il loro collegamento hardware e di rete lo supporta, e possono ricevere un video Full HD da 1920 x 1080 in cui gli altri client dei partecipanti lo supportano.</span><span class="sxs-lookup"><span data-stu-id="bb324-173">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="bb324-174">I dipendenti che non sono dirigenti sperimentano risoluzioni più basse rispetto ai dirigenti nelle conferenze a due o più parti, ma ottengono comunque una buona risoluzione.</span><span class="sxs-lookup"><span data-stu-id="bb324-174">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="bb324-175">I dipendenti che si trovano nella succursale ricevono una buona qualità video nelle chiamate a due parti quando Lync Visualizza le dimensioni predefinite della finestra video. Tuttavia, se la finestra di Lync è ingrandita a schermo intero, la risoluzione video non aumenterà.</span><span class="sxs-lookup"><span data-stu-id="bb324-175">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="bb324-176">Per le conferenze con più partecipanti, i dipendenti della succursale vedranno un solo video attivo.</span><span class="sxs-lookup"><span data-stu-id="bb324-176">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

