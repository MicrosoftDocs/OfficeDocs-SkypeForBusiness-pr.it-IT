---
title: 'Lync Server 2013: configurazione degli scenari di esempio video'
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
ms.openlocfilehash: 71eb886bb50f503b43eb757cc41310583fc11303
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154138"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-video-example-scenarios-for-lync-server-2013"></a><span data-ttu-id="4adb5-102">Configurazione di scenari di esempio video per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4adb5-102">Configuring video example scenarios for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4adb5-103">_**Ultimo argomento modificato:** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="4adb5-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="4adb5-104">Lync 2013 aggiunge nuove funzionalità video per il supporto del video per la visualizzazione di video e raccolta di 1920 x 1080 Full High Definition (HD).</span><span class="sxs-lookup"><span data-stu-id="4adb5-104">Lync 2013 adds new video features to support 1920 x 1080 full high definition (HD) video and Gallery View video.</span></span> <span data-ttu-id="4adb5-105">Le misure basate sui dati dei clienti mostrano che la larghezza di banda video tipica è aumentata solo leggermente rispetto a Lync 2010, ma la larghezza di banda massima del flusso video è aumentata a causa del supporto di Full HD (per informazioni dettagliate, vedere la sezione "utilizzo di Network Traffic media" nei [requisiti di larghezza di banda di rete per il traffico multimediale in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span><span class="sxs-lookup"><span data-stu-id="4adb5-105">Measurements based on customer data show that the typical video bandwidth increased only slightly compared to Lync 2010, but the maximum video stream bandwidth has increased due to full HD support (for details, see the "Media Traffic Network Usage" section in [Network bandwidth requirements for media traffic in Lync Server 2013](lync-server-2013-network-bandwidth-requirements-for-media-traffic.md)).</span></span> <span data-ttu-id="4adb5-106">Gli amministratori possono quindi limitare la larghezza di banda video per determinati utenti, ad esempio gli utenti in una succursale con meno capacità di rete, e contribuire a garantire la migliore qualità video possibile per gli altri utenti, ad esempio i dirigenti.</span><span class="sxs-lookup"><span data-stu-id="4adb5-106">Therefore, administrators may want to restrict video bandwidth for certain users (such as users in a branch office that has less network capacity) and help to ensure the best possible video quality for other users (such as executives).</span></span>

<span data-ttu-id="4adb5-107">Nella tabella seguente viene fornito un elenco delle impostazioni consigliate per la configurazione di video per le diverse capacità di rete.</span><span class="sxs-lookup"><span data-stu-id="4adb5-107">The following table provides a list of recommended settings for configuring video for different network capacities.</span></span> <span data-ttu-id="4adb5-108">Queste impostazioni impediscono ad alcuni scenari degli utenti di inviare e ricevere video con risoluzione superiore (vedere la colonna a destra).</span><span class="sxs-lookup"><span data-stu-id="4adb5-108">These settings will restrict some user scenarios from sending and receiving higher resolution videos (see rightmost column).</span></span> <span data-ttu-id="4adb5-109">L'impostazione minima consentirà la mancata disponibilità del video della raccolta a causa della larghezza di banda massima della rete di ricezione.</span><span class="sxs-lookup"><span data-stu-id="4adb5-109">The minimum setting will result in Gallery Video being unavailable, due to the low maximum receive network bandwidth.</span></span>

### <a name="recommended-video-settings"></a><span data-ttu-id="4adb5-110">Impostazioni video consigliate</span><span class="sxs-lookup"><span data-stu-id="4adb5-110">Recommended Video Settings</span></span>

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
<th><span data-ttu-id="4adb5-111">AllowMultiView</span><span class="sxs-lookup"><span data-stu-id="4adb5-111">AllowMultiView</span></span></th>
<th><span data-ttu-id="4adb5-112">EnableMultiViewJoin</span><span class="sxs-lookup"><span data-stu-id="4adb5-112">EnableMultiViewJoin</span></span></th>
<th><span data-ttu-id="4adb5-113">VideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="4adb5-113">VideoBitRateKB</span></span></th>
<th><span data-ttu-id="4adb5-114">TotalReceiveVideoBitRateKB</span><span class="sxs-lookup"><span data-stu-id="4adb5-114">TotalReceiveVideoBitRateKB</span></span></th>
<th><span data-ttu-id="4adb5-115">Risoluzione video prevista per un video di qualità buona</span><span class="sxs-lookup"><span data-stu-id="4adb5-115">Expected video resolution for good quality video</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4adb5-116">Elevate</span><span class="sxs-lookup"><span data-stu-id="4adb5-116">Best</span></span></p></td>
<td><p><span data-ttu-id="4adb5-117">True</span><span class="sxs-lookup"><span data-stu-id="4adb5-117">True</span></span></p></td>
<td><p><span data-ttu-id="4adb5-118">True</span><span class="sxs-lookup"><span data-stu-id="4adb5-118">True</span></span></p></td>
<td><p><span data-ttu-id="4adb5-119">8000</span><span class="sxs-lookup"><span data-stu-id="4adb5-119">8000</span></span></p></td>
<td><p><span data-ttu-id="4adb5-120">8000</span><span class="sxs-lookup"><span data-stu-id="4adb5-120">8000</span></span></p></td>
<td><p><span data-ttu-id="4adb5-121">Risoluzione video peer-to-peer: fino a 1920 x 1080</span><span class="sxs-lookup"><span data-stu-id="4adb5-121">Peer-to-peer: Up to 1920 x 1080 video resolution</span></span></p>
<p><span data-ttu-id="4adb5-122">Visualizzazione raccolta: fino a 2 1920 x 1080 video o più video con risoluzione più piccola</span><span class="sxs-lookup"><span data-stu-id="4adb5-122">Gallery View: Up to two 1920 x 1080 videos or multiple smaller resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4adb5-123">Buone</span><span class="sxs-lookup"><span data-stu-id="4adb5-123">Good</span></span></p></td>
<td><p><span data-ttu-id="4adb5-124">True</span><span class="sxs-lookup"><span data-stu-id="4adb5-124">True</span></span></p></td>
<td><p><span data-ttu-id="4adb5-125">True</span><span class="sxs-lookup"><span data-stu-id="4adb5-125">True</span></span></p></td>
<td><p><span data-ttu-id="4adb5-126">2500</span><span class="sxs-lookup"><span data-stu-id="4adb5-126">2500</span></span></p></td>
<td><p><span data-ttu-id="4adb5-127">2500</span><span class="sxs-lookup"><span data-stu-id="4adb5-127">2500</span></span></p></td>
<td><p><span data-ttu-id="4adb5-128">Risoluzione video peer-to-peer: fino a 1280 x 720</span><span class="sxs-lookup"><span data-stu-id="4adb5-128">Peer-to-peer: Up to 1280 x 720 video resolution</span></span></p>
<p><span data-ttu-id="4adb5-129">Visualizzazione raccolta: fino a 5 640 x 360 risoluzione video</span><span class="sxs-lookup"><span data-stu-id="4adb5-129">Gallery View: Up to five 640 x 360 resolution videos</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4adb5-130">Medio</span><span class="sxs-lookup"><span data-stu-id="4adb5-130">Medium</span></span></p></td>
<td><p><span data-ttu-id="4adb5-131">True</span><span class="sxs-lookup"><span data-stu-id="4adb5-131">True</span></span></p></td>
<td><p><span data-ttu-id="4adb5-132">True</span><span class="sxs-lookup"><span data-stu-id="4adb5-132">True</span></span></p></td>
<td><p><span data-ttu-id="4adb5-133">1000</span><span class="sxs-lookup"><span data-stu-id="4adb5-133">1000</span></span></p></td>
<td><p><span data-ttu-id="4adb5-134">1000</span><span class="sxs-lookup"><span data-stu-id="4adb5-134">1000</span></span></p></td>
<td><p><span data-ttu-id="4adb5-135">Risoluzione video peer-to-peer: fino a 960 x 540</span><span class="sxs-lookup"><span data-stu-id="4adb5-135">Peer-to-peer: Up to 960 x 540 video resolution</span></span></p>
<p><span data-ttu-id="4adb5-136">Visualizzazione raccolta: fino a 5 424 x 240 risoluzione video</span><span class="sxs-lookup"><span data-stu-id="4adb5-136">Gallery View: Up to five 424 x 240 resolution videos</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4adb5-137">Minimo</span><span class="sxs-lookup"><span data-stu-id="4adb5-137">Minimum</span></span></p></td>
<td><p><span data-ttu-id="4adb5-138">True</span><span class="sxs-lookup"><span data-stu-id="4adb5-138">True</span></span></p></td>
<td><p><span data-ttu-id="4adb5-139">False</span><span class="sxs-lookup"><span data-stu-id="4adb5-139">False</span></span></p></td>
<td><p><span data-ttu-id="4adb5-140">350</span><span class="sxs-lookup"><span data-stu-id="4adb5-140">350</span></span></p></td>
<td><p><span data-ttu-id="4adb5-141">350</span><span class="sxs-lookup"><span data-stu-id="4adb5-141">350</span></span></p></td>
<td><p><span data-ttu-id="4adb5-142">Risoluzione video peer-to-peer: fino a 424 x 240</span><span class="sxs-lookup"><span data-stu-id="4adb5-142">Peer-to-peer: Up to 424 x 240 video resolution</span></span></p>
<p><span data-ttu-id="4adb5-143">Visualizzazione raccolta: non disponibile</span><span class="sxs-lookup"><span data-stu-id="4adb5-143">Gallery View: Unavailable</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="4adb5-144">È possibile utilizzare le informazioni contenute nella tabella precedente per distribuire le nuove funzionalità di conferenza video HD e visualizzazione raccolta per alcuni utenti dell'organizzazione, consentendo di risoluzioni video diverse per gli altri.</span><span class="sxs-lookup"><span data-stu-id="4adb5-144">You can use the information in the preceding table to deploy the new HD video and Gallery View video conferencing features for some users in your organization, while allowing different video resolutions for others.</span></span>

<span data-ttu-id="4adb5-145">Nell'esempio seguente, l'amministratore esegue il rollback delle nuove funzionalità video con la qualità video più alta disponibile solo per i dirigenti.</span><span class="sxs-lookup"><span data-stu-id="4adb5-145">In the following example, the administrator rolls out the new video features with the highest video quality available only to executives.</span></span> <span data-ttu-id="4adb5-146">Per i dipendenti di una filiale remota con capacità di rete ridotta, viene distribuita solo l'impostazione minima della tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="4adb5-146">For employees in a remote branch office that has low network capacity, only the minimum setting from the preceding table is deployed.</span></span> <span data-ttu-id="4adb5-147">Per tutti gli altri dipendenti, viene distribuita l'impostazione "buona" dalla tabella precedente.</span><span class="sxs-lookup"><span data-stu-id="4adb5-147">For all other employees, the "Good" setting from the preceding table is deployed.</span></span>

<span data-ttu-id="4adb5-148">Per implementare le nuove funzionalità ai dirigenti, l'amministratore crea un criterio di conferenza denominato ExecutiveVideo.</span><span class="sxs-lookup"><span data-stu-id="4adb5-148">To roll out the new features to the executives, the administrator creates a conferencing policy named ExecutiveVideo.</span></span> <span data-ttu-id="4adb5-149">I criteri di conferenza sono disponibili nelle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4adb5-149">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="4adb5-150">VideoBitRateKB è impostato su 8000 kbps</span><span class="sxs-lookup"><span data-stu-id="4adb5-150">VideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="4adb5-151">TotalReceiveVideoBitRateKB è impostato su 8000 kbps</span><span class="sxs-lookup"><span data-stu-id="4adb5-151">TotalReceiveVideoBitRateKB is set to 8000 Kbps</span></span>

  - <span data-ttu-id="4adb5-152">AllowMultiview è impostato su true</span><span class="sxs-lookup"><span data-stu-id="4adb5-152">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="4adb5-153">EnableMultiviewJoin è impostato su true</span><span class="sxs-lookup"><span data-stu-id="4adb5-153">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="4adb5-154">Per i dipendenti della succursale, l'amministratore crea un criterio di conferenza denominato BranchOfficeVideo.</span><span class="sxs-lookup"><span data-stu-id="4adb5-154">For employees in the branch office, the administrator creates a conferencing policy named BranchOfficeVideo.</span></span> <span data-ttu-id="4adb5-155">I criteri di conferenza sono disponibili nelle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4adb5-155">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="4adb5-156">VideoBitRateKB è impostato su 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="4adb5-156">VideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="4adb5-157">TotalReceiveVideoBitRateKB è impostato su 350 Kbps</span><span class="sxs-lookup"><span data-stu-id="4adb5-157">TotalReceiveVideoBitRateKB is set to 350 Kbps</span></span>

  - <span data-ttu-id="4adb5-158">AllowMultiview è impostato su true</span><span class="sxs-lookup"><span data-stu-id="4adb5-158">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="4adb5-159">EnableMultiviewJoin è impostato su false</span><span class="sxs-lookup"><span data-stu-id="4adb5-159">EnableMultiviewJoin is set to False</span></span>

<span data-ttu-id="4adb5-160">Per tutti gli altri dipendenti, l'amministratore crea un criterio di conferenza denominato StandardVideo.</span><span class="sxs-lookup"><span data-stu-id="4adb5-160">For all other employees, the administrator creates a conferencing policy named StandardVideo.</span></span> <span data-ttu-id="4adb5-161">I criteri di conferenza sono disponibili nelle impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4adb5-161">This conferencing policy has the following settings:</span></span>

  - <span data-ttu-id="4adb5-162">VideoBitRateKB è impostato su 2500 kbps</span><span class="sxs-lookup"><span data-stu-id="4adb5-162">VideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="4adb5-163">TotalReceiveVideoBitRateKB è impostato su 2500 kbps</span><span class="sxs-lookup"><span data-stu-id="4adb5-163">TotalReceiveVideoBitRateKB is set to 2500 Kbps</span></span>

  - <span data-ttu-id="4adb5-164">AllowMultiview è impostato su true</span><span class="sxs-lookup"><span data-stu-id="4adb5-164">AllowMultiview is set to True</span></span>

  - <span data-ttu-id="4adb5-165">EnableMultiviewJoin è impostato su true</span><span class="sxs-lookup"><span data-stu-id="4adb5-165">EnableMultiviewJoin is set to True</span></span>

<span data-ttu-id="4adb5-166">L'amministratore assegna i criteri di conferenza agli utenti, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="4adb5-166">The administrator assigns conferencing policy to users as follows:</span></span>

  - <span data-ttu-id="4adb5-167">I criteri di conferenza di ExecutiveVideo sono assegnati ai dirigenti.</span><span class="sxs-lookup"><span data-stu-id="4adb5-167">The ExecutiveVideo conferencing policy is assigned to the executives.</span></span>

  - <span data-ttu-id="4adb5-168">Il criterio di conferenza BranchOfficeVideo viene assegnato a tutti i dipendenti della succursale.</span><span class="sxs-lookup"><span data-stu-id="4adb5-168">The BranchOfficeVideo conferencing policy is assigned to all employees in the branch office.</span></span>

  - <span data-ttu-id="4adb5-169">Il criterio di conferenza StandardVideo viene assegnato a tutti gli altri dipendenti.</span><span class="sxs-lookup"><span data-stu-id="4adb5-169">The StandardVideo conferencing policy is assigned to all other employees.</span></span>

<span data-ttu-id="4adb5-170">Queste assegnazioni dei criteri di conferenza determinano l'esperienza utente seguente:</span><span class="sxs-lookup"><span data-stu-id="4adb5-170">These conferencing policy assignments result in the following user experience:</span></span>

  - <span data-ttu-id="4adb5-171">Tutte le conferenze organizzate da qualsiasi visualizzazione raccolta supporto utenti, ma i dipendenti della succursale non possono sperimentare la visualizzazione della raccolta.</span><span class="sxs-lookup"><span data-stu-id="4adb5-171">All conferences organized by any user support Gallery View, but employees in the branch office cannot experience Gallery View.</span></span>

  - <span data-ttu-id="4adb5-172">Per tutte le conferenze a due o più parti, i dirigenti possono inviare video Full HD 1920 x 1080, se il loro collegamento hardware e di rete lo supporta, e possono ricevere un video Full HD da 1920 x 1080 in cui gli altri client dei partecipanti lo supportano.</span><span class="sxs-lookup"><span data-stu-id="4adb5-172">For any two-party or multiparty conferences, executives can send 1920 x 1080 full HD video, if their hardware and network link supports it, and can receive 1920 x 1080 full HD video where the other participant clients support it.</span></span>

  - <span data-ttu-id="4adb5-173">I dipendenti che non sono dirigenti sperimentano risoluzioni più basse rispetto ai dirigenti nelle conferenze a due o più parti, ma ottengono comunque una buona risoluzione.</span><span class="sxs-lookup"><span data-stu-id="4adb5-173">Employees who are not executives experience lower resolutions than the executives in their two-party or multiparty conferences, but still get good resolution.</span></span>

  - <span data-ttu-id="4adb5-174">I dipendenti che si trovano nella succursale ricevono una buona qualità video nelle chiamate a due parti quando Lync Visualizza le dimensioni predefinite della finestra video. Tuttavia, se la finestra di Lync è ingrandita a schermo intero, la risoluzione video non aumenterà.</span><span class="sxs-lookup"><span data-stu-id="4adb5-174">Employees who are in the branch office will get good video quality in two-party calls when Lync displays the default video window size; however, if the Lync window is maximized to full screen, the video resolution will not increase.</span></span> <span data-ttu-id="4adb5-175">Per le conferenze con più partecipanti, i dipendenti della succursale vedranno un solo video attivo.</span><span class="sxs-lookup"><span data-stu-id="4adb5-175">For multiparty conferences, the employees in the branch office will see only one active video.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

