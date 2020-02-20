---
title: 'Lync Server 2013: Panoramica dei tipi di indirizzi IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of IP address types for Lync Server
ms:assetid: ee9a695f-5cf5-441e-94fb-6adeca50e8d8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205363(v=OCS.15)
ms:contentKeyID: 48185759
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 975aa4a81b4e44cc20fdbfda946f901610a1b484
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="95f43-102">Panoramica dei tipi di indirizzi IP per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="95f43-102">Overview of IP address types for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="95f43-103">_**Ultimo argomento modificato:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="95f43-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="95f43-104">Sono disponibili tre opzioni per la configurazione degli indirizzi IP in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="95f43-104">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="95f43-105">È possibile configurare Lync Server 2013 per supportare solo IP versione 4 (IPv4), solo IP versione 6 (IPv6) o una combinazione di entrambi (noto come *stack doppio*).</span><span class="sxs-lookup"><span data-stu-id="95f43-105">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="95f43-106">Per ogni tipo di configurazione è necessario considerare diversi problemi:</span><span class="sxs-lookup"><span data-stu-id="95f43-106">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="95f43-107">**IPv4**   è stato creato solo IPv6 perché il mondo è in esecuzione fuori degli indirizzi IPv4.</span><span class="sxs-lookup"><span data-stu-id="95f43-107">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="95f43-108">In futuro IPv6 sarà completamente supportato in tutto il mondo, ma al momento molte aziende e molti dispositivi con cui potrebbe essere necessario comunicare non lo supportano ancora.</span><span class="sxs-lookup"><span data-stu-id="95f43-108">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="95f43-109">Una configurazione solo IPv4 consentirà di garantire che l'implementazione di Lync Server sia in grado di comunicare con la maggior parte dei dispositivi esistenti.</span><span class="sxs-lookup"><span data-stu-id="95f43-109">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="95f43-110">**IPv6 solo**   al contrario, un'implementazione IPv6 completa, in questo momento, escluderà la comunicazione con molti dispositivi esistenti.</span><span class="sxs-lookup"><span data-stu-id="95f43-110">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="95f43-111">**Dual**   stack dual stack è una rete in cui sono abilitati sia gli indirizzi IPv4 che IPv6.</span><span class="sxs-lookup"><span data-stu-id="95f43-111">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="95f43-112">Questa configurazione è supportata in Lync Server 2013 perché, nella maggior parte dei casi, la transizione da Full-IPv4 a full-IPv6 richiederà diversi anni.</span><span class="sxs-lookup"><span data-stu-id="95f43-112">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="95f43-113">Nelle sezioni seguenti viene illustrata la compatibilità tra queste tre configurazioni per diverse funzionalità di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="95f43-113">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="95f43-p104">La configurazione client o server con il solo protocollo IPv6 è supportata solo per fini di ricerca e di convalida. La configurazione Solo IPv6 non è supportata nella distribuzione di produzione.</span><span class="sxs-lookup"><span data-stu-id="95f43-p104">Client or server configuration with IPv6 only is supported only for lab or validation purposes. IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="95f43-116">Registrazione client</span><span class="sxs-lookup"><span data-stu-id="95f43-116">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95f43-117">Rete endpoint client</span><span class="sxs-lookup"><span data-stu-id="95f43-117">Client endpoint network</span></span></th>
<th><span data-ttu-id="95f43-118">Rete server</span><span class="sxs-lookup"><span data-stu-id="95f43-118">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95f43-119">IPv4</span><span class="sxs-lookup"><span data-stu-id="95f43-119">IPv4</span></span></p></td>
<td><p><span data-ttu-id="95f43-120">IPv4</span><span class="sxs-lookup"><span data-stu-id="95f43-120">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f43-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="95f43-121">IPv4</span></span></p></td>
<td><p><span data-ttu-id="95f43-122">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-122">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f43-123">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-123">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="95f43-124">IPv4</span><span class="sxs-lookup"><span data-stu-id="95f43-124">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f43-125">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-125">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="95f43-126">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-126">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f43-127">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-127">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="95f43-128">IPv6</span><span class="sxs-lookup"><span data-stu-id="95f43-128">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f43-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="95f43-129">IPv6</span></span></p></td>
<td><p><span data-ttu-id="95f43-130">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-130">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f43-131">IPv6</span><span class="sxs-lookup"><span data-stu-id="95f43-131">IPv6</span></span></p></td>
<td><p><span data-ttu-id="95f43-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="95f43-132">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="95f43-133">Client peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="95f43-133">Peer-to-Peer Client</span></span>

<span data-ttu-id="95f43-p105">La comunicazione peer-to-peer include audio, audio/video, condivisione di applicazioni e trasferimento di file. Dopo la corretta registrazione di entrambi i client, sono supportate le combinazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="95f43-p105">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer. After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95f43-136">Endpoint client 1</span><span class="sxs-lookup"><span data-stu-id="95f43-136">Client endpoint 1</span></span></th>
<th><span data-ttu-id="95f43-137">Endpoint client 2</span><span class="sxs-lookup"><span data-stu-id="95f43-137">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95f43-138">IPv4</span><span class="sxs-lookup"><span data-stu-id="95f43-138">IPv4</span></span></p></td>
<td><p><span data-ttu-id="95f43-139">IPv4</span><span class="sxs-lookup"><span data-stu-id="95f43-139">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f43-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="95f43-140">IPv4</span></span></p></td>
<td><p><span data-ttu-id="95f43-141">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-141">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f43-142">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-142">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="95f43-143">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-143">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f43-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="95f43-144">IPv6</span></span></p></td>
<td><p><span data-ttu-id="95f43-145">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-145">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f43-146">IPv6</span><span class="sxs-lookup"><span data-stu-id="95f43-146">IPv6</span></span></p></td>
<td><p><span data-ttu-id="95f43-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="95f43-147">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="95f43-148">Conferenza</span><span class="sxs-lookup"><span data-stu-id="95f43-148">Conferencing</span></span>

<span data-ttu-id="95f43-149">Servizi di conferenza include audio/video, condivisione di applicazioni e collaborazione dati (condivisione file e lavagna).</span><span class="sxs-lookup"><span data-stu-id="95f43-149">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95f43-150">Rete endpoint client</span><span class="sxs-lookup"><span data-stu-id="95f43-150">Client endpoint network</span></span></th>
<th><span data-ttu-id="95f43-151">Rete server</span><span class="sxs-lookup"><span data-stu-id="95f43-151">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95f43-152">IPv4</span><span class="sxs-lookup"><span data-stu-id="95f43-152">IPv4</span></span></p></td>
<td><p><span data-ttu-id="95f43-153">IPv4</span><span class="sxs-lookup"><span data-stu-id="95f43-153">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f43-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="95f43-154">IPv4</span></span></p></td>
<td><p><span data-ttu-id="95f43-155">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-155">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f43-156">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-156">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="95f43-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="95f43-157">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f43-158">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-158">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="95f43-159">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-159">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f43-160">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-160">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="95f43-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="95f43-161">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f43-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="95f43-162">IPv6</span></span></p></td>
<td><p><span data-ttu-id="95f43-163">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-163">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f43-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="95f43-164">IPv6</span></span></p></td>
<td><p><span data-ttu-id="95f43-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="95f43-165">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="95f43-166">Mediation Server/PSTN</span><span class="sxs-lookup"><span data-stu-id="95f43-166">Mediation Server/PSTN</span></span>

<span data-ttu-id="95f43-167">Lync Server 2013 non supporta il bypass multimediale per le chiamate PSTN (Public Switched Telephone Network) se il traffico avviene tramite un'interfaccia IPv6.</span><span class="sxs-lookup"><span data-stu-id="95f43-167">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="95f43-168">Se il bypass multimediale è necessario, è consigliabile configurare il gateway PSTN su IPv4.</span><span class="sxs-lookup"><span data-stu-id="95f43-168">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95f43-169">Interfaccia principale\*</span><span class="sxs-lookup"><span data-stu-id="95f43-169">Primary interface\*</span></span></th>
<th><span data-ttu-id="95f43-170">Interfaccia PSTN (in Mediation Server)</span><span class="sxs-lookup"><span data-stu-id="95f43-170">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="95f43-171">Impostazioni del gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="95f43-171">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95f43-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="95f43-172">IPv4</span></span></p></td>
<td><p><span data-ttu-id="95f43-173">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-173">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="95f43-174">IPv4</span><span class="sxs-lookup"><span data-stu-id="95f43-174">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f43-175">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-175">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="95f43-176">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="95f43-177">IPv4</span><span class="sxs-lookup"><span data-stu-id="95f43-177">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f43-178">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-178">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="95f43-179">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="95f43-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="95f43-180">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="95f43-181">\*L'interfaccia principale è l'interfaccia che comunica con i componenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="95f43-181">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="95f43-182">Comunicazioni peer-to-peer con utenti remoti</span><span class="sxs-lookup"><span data-stu-id="95f43-182">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="95f43-183">La comunicazione peer-to-peer con utenti remoti include messaggistica istantanea, audio/video, condivisione di applicazioni e trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="95f43-183">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="95f43-184">Rete utenti remoti</span><span class="sxs-lookup"><span data-stu-id="95f43-184">Remote user network</span></span></th>
<th><span data-ttu-id="95f43-185">Server perimetrale (perimetro esterno)</span><span class="sxs-lookup"><span data-stu-id="95f43-185">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="95f43-186">IPv4</span><span class="sxs-lookup"><span data-stu-id="95f43-186">IPv4</span></span></p></td>
<td><p><span data-ttu-id="95f43-187">IPv4</span><span class="sxs-lookup"><span data-stu-id="95f43-187">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f43-188">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-188">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="95f43-189">IPv4</span><span class="sxs-lookup"><span data-stu-id="95f43-189">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f43-190">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-190">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="95f43-191">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-191">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f43-192">IPv6</span><span class="sxs-lookup"><span data-stu-id="95f43-192">IPv6</span></span></p></td>
<td><p><span data-ttu-id="95f43-193">Dual stack</span><span class="sxs-lookup"><span data-stu-id="95f43-193">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f43-194">IPv6</span><span class="sxs-lookup"><span data-stu-id="95f43-194">IPv6</span></span></p></td>
<td><p><span data-ttu-id="95f43-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="95f43-195">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="95f43-196">Configurazione di pool Front End e di pool di server perimetrali</span><span class="sxs-lookup"><span data-stu-id="95f43-196">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="95f43-197">Nella tabella seguente viene illustrata la matrice di supporto tra il pool Front End Server e il pool di server perimetrali interni.</span><span class="sxs-lookup"><span data-stu-id="95f43-197">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="95f43-198">Matrice di pool Front End e di pool di server perimetrali (perimetro interno)</span><span class="sxs-lookup"><span data-stu-id="95f43-198">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="95f43-199"><strong>Pool di server perimetrali: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="95f43-199"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="95f43-200"><strong>Pool di server perimetrali: Dual Stack</strong></span><span class="sxs-lookup"><span data-stu-id="95f43-200"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="95f43-201"><strong>Pool di server perimetrali: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="95f43-201"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f43-202"><strong>Pool Front End: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="95f43-202"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="95f43-203">Sì</span><span class="sxs-lookup"><span data-stu-id="95f43-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="95f43-204">Sì</span><span class="sxs-lookup"><span data-stu-id="95f43-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="95f43-205">No</span><span class="sxs-lookup"><span data-stu-id="95f43-205">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f43-206"><strong>Pool Front End: Dual Stack</strong></span><span class="sxs-lookup"><span data-stu-id="95f43-206"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="95f43-207">Sì</span><span class="sxs-lookup"><span data-stu-id="95f43-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="95f43-208">Sì</span><span class="sxs-lookup"><span data-stu-id="95f43-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="95f43-209">No</span><span class="sxs-lookup"><span data-stu-id="95f43-209">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f43-210"><strong>Pool Front End: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="95f43-210"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="95f43-211">No</span><span class="sxs-lookup"><span data-stu-id="95f43-211">No</span></span></p></td>
<td><p><span data-ttu-id="95f43-212">No</span><span class="sxs-lookup"><span data-stu-id="95f43-212">No</span></span></p></td>
<td><p><span data-ttu-id="95f43-213">Sì\*</span><span class="sxs-lookup"><span data-stu-id="95f43-213">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="95f43-214">\*Utilizzare questa combinazione solo in un ambiente lab.</span><span class="sxs-lookup"><span data-stu-id="95f43-214">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="95f43-215">La tabella seguente è una matrice delle combinazioni supportate di interfacce di server perimetrali interni ed esterni.</span><span class="sxs-lookup"><span data-stu-id="95f43-215">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="95f43-216">Matrice di pool di server perimetrali (perimetro interno) e di pool di server perimetrali (perimetro esterno)</span><span class="sxs-lookup"><span data-stu-id="95f43-216">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td></td>
<td><p><span data-ttu-id="95f43-217"><strong>Pool di server perimetrali (perimetro esterno): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="95f43-217"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="95f43-218"><strong>Pool di server perimetrali (perimetro esterno): Dual Stack</strong></span><span class="sxs-lookup"><span data-stu-id="95f43-218"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="95f43-219"><strong>Pool di server perimetrali (perimetro esterno): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="95f43-219"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f43-220"><strong>Pool di server perimetrali (perimetro interno): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="95f43-220"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="95f43-221">Sì</span><span class="sxs-lookup"><span data-stu-id="95f43-221">Yes</span></span></p></td>
<td><p><span data-ttu-id="95f43-222">Sì</span><span class="sxs-lookup"><span data-stu-id="95f43-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="95f43-223">No</span><span class="sxs-lookup"><span data-stu-id="95f43-223">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="95f43-224"><strong>Pool di server perimetrali (perimetro interno): Dual Stack</strong></span><span class="sxs-lookup"><span data-stu-id="95f43-224"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="95f43-225">No</span><span class="sxs-lookup"><span data-stu-id="95f43-225">No</span></span></p></td>
<td><p><span data-ttu-id="95f43-226">Sì</span><span class="sxs-lookup"><span data-stu-id="95f43-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="95f43-227">No</span><span class="sxs-lookup"><span data-stu-id="95f43-227">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="95f43-228"><strong>Pool di server perimetrali (perimetro interno): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="95f43-228"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="95f43-229">No</span><span class="sxs-lookup"><span data-stu-id="95f43-229">No</span></span></p></td>
<td><p><span data-ttu-id="95f43-230">No</span><span class="sxs-lookup"><span data-stu-id="95f43-230">No</span></span></p></td>
<td><p><span data-ttu-id="95f43-231">Sì\*</span><span class="sxs-lookup"><span data-stu-id="95f43-231">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="95f43-232">\*Utilizzare questa combinazione solo in un ambiente lab.</span><span class="sxs-lookup"><span data-stu-id="95f43-232">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="95f43-233">Supporto vocale aziendale avanzato per IPv6</span><span class="sxs-lookup"><span data-stu-id="95f43-233">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="95f43-234">Le distribuzioni che includono il servizio Controllo di ammissione di chiamata, Enhanced 9-1-1 (E9-1-1) o il bypass multimediale devono essere configurate come implementazioni Solo IPv4 o Dual Stack.</span><span class="sxs-lookup"><span data-stu-id="95f43-234">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="95f43-235">In una distribuzione con stack doppio, anche se un client Lync si connette a un server Lync utilizzando IPv6, Lync farà il possibile per mappare un indirizzo IPv4 appropriato per il supporto di E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="95f43-235">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="95f43-236">Il servizio informazioni percorso con indirizzi IPv6 non è supportato.</span><span class="sxs-lookup"><span data-stu-id="95f43-236">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="95f43-p107">La messaggistica unificata di Exchange non supporta IPv6. Per la messaggistica unificata di Exchange, assicurasi che la risoluzione DNS non restituisca un indirizzo IPv6. L'utilizzo di IPv6 può causare errori quando le chiamate vengono inviate alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="95f43-p107">Exchange Unified Messaging (UM) does not support IPv6. For Exchange UM, be sure that DNS resolution does not return an IPv6 address. Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="95f43-240">Altre funzionalità di Lync Server 2013 supportate per IPv6</span><span class="sxs-lookup"><span data-stu-id="95f43-240">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="95f43-241">Oltre alle caratteristiche e ai componenti menzionati in precedenza, Lync Server 2013 supporta IPv6 per le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="95f43-241">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="95f43-242">**Chat persistente**</span><span class="sxs-lookup"><span data-stu-id="95f43-242">**Persistent Chat**</span></span>
    
    <span data-ttu-id="95f43-243">È possibile configurare IPv6 per la chat persistente mediante il generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="95f43-243">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="95f43-244">Per informazioni dettagliate sulla configurazione di chat persistente, vedere la documentazione relativa alla distribuzione di Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="95f43-244">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="95f43-245">**Rapporti qualità percepita dagli utenti (QoE) e registrazione dettagli chiamata (CDR)**</span><span class="sxs-lookup"><span data-stu-id="95f43-245">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="95f43-246">Le relazioni di monitoraggio includono l'indirizzo IP così com'è archiviato nel database di Monitoring Server, che sia di tipo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="95f43-246">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

