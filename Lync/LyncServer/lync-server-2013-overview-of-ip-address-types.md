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
ms.openlocfilehash: 9d1172fc7da9600de036312adb05548b51dea6b0
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755530"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-ip-address-types-for-lync-server-2013"></a><span data-ttu-id="db899-102">Panoramica dei tipi di indirizzi IP per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="db899-102">Overview of IP address types for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="db899-103">_**Argomento Ultima modifica:** 2013-01-29_</span><span class="sxs-lookup"><span data-stu-id="db899-103">_**Topic Last Modified:** 2013-01-29_</span></span>

<span data-ttu-id="db899-104">Sono disponibili tre opzioni per la configurazione degli indirizzi IP in Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="db899-104">You have three options when configuring IP addresses in Lync Server 2013.</span></span> <span data-ttu-id="db899-105">È possibile configurare Lync Server 2013 per supportare solo IP versione 4 (IPv4), solo IP versione 6 (IPv6) o una combinazione di entrambi (noto come *stack doppio*).</span><span class="sxs-lookup"><span data-stu-id="db899-105">You can configure Lync Server 2013 to support only IP version 4 (IPv4), only IP version 6 (IPv6), or a combination of both (known as a *dual stack*).</span></span> <span data-ttu-id="db899-106">Esistono diversi problemi da considerare con ogni tipo di configurazione:</span><span class="sxs-lookup"><span data-stu-id="db899-106">There are several issues to consider with each type of configuration:</span></span>

  - <span data-ttu-id="db899-107">**IPv4 solo**   IPv6 è stato creato perché il mondo è in esaurimento degli indirizzi IPv4.</span><span class="sxs-lookup"><span data-stu-id="db899-107">**IPv4 only**   IPv6 was created because the world is running out of IPv4 addresses.</span></span> <span data-ttu-id="db899-108">In definitiva, IPv6 sarà completamente supportato in tutto il mondo, ma in questo momento, molte aziende e dispositivi di cui l'organizzazione potrebbe dover comunicare non supportano ancora IPv6 e potrebbero non essere da qualche tempo.</span><span class="sxs-lookup"><span data-stu-id="db899-108">Ultimately, IPv6 will be fully supported worldwide, but at this time, many companies and devices that your enterprise might need to communicate with do not yet support IPv6, and may not for some time.</span></span> <span data-ttu-id="db899-109">Una configurazione solo IPv4 consentirà di garantire che l'implementazione di Lync Server possa comunicare con la maggior parte dei dispositivi esistenti.</span><span class="sxs-lookup"><span data-stu-id="db899-109">An IPv4-only configuration will help to ensure that your Lync Server implementation can communicate with most existing devices.</span></span>

  - <span data-ttu-id="db899-110">**IPv6 solo**   al contrario, un'implementazione completa di IPv6, in questo momento, escluderà la comunicazione con molti dispositivi esistenti.</span><span class="sxs-lookup"><span data-stu-id="db899-110">**IPv6 only**   Conversely, a full IPv6 implementation, at this time, will exclude communication with many existing devices.</span></span>

  - <span data-ttu-id="db899-111">**Dual**   stack dual stack è una rete in cui sono abilitati sia gli indirizzi IPv4 che IPv6.</span><span class="sxs-lookup"><span data-stu-id="db899-111">**Dual Stack**   Dual stack is a network where both IPv4 and IPv6 addresses are enabled.</span></span> <span data-ttu-id="db899-112">Questa configurazione è supportata in Lync Server 2013 perché nella maggior parte dei casi la transizione da Full-IPv4 a full-IPv6 avrà diversi anni.</span><span class="sxs-lookup"><span data-stu-id="db899-112">This configuration is supported in Lync Server 2013 because in most cases the transition from full-IPv4 to full-IPv6 will take several years.</span></span>

<span data-ttu-id="db899-113">Le sezioni seguenti illustrano la compatibilità tra queste tre configurazioni per varie funzionalità di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="db899-113">The following sections outline the compatibility among these three configurations for various Lync Server features.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="db899-114">La configurazione client o server con IPv6 è supportata solo per scopi di laboratorio o di convalida.</span><span class="sxs-lookup"><span data-stu-id="db899-114">Client or server configuration with IPv6 only is supported only for lab or validation purposes.</span></span> <span data-ttu-id="db899-115">La configurazione solo IPv6 non è supportata nella distribuzione della produzione.</span><span class="sxs-lookup"><span data-stu-id="db899-115">IPv6 only configuration is not supported in the production deployment.</span></span>



</div>

<div>

## <a name="client-registration"></a><span data-ttu-id="db899-116">Registrazione client</span><span class="sxs-lookup"><span data-stu-id="db899-116">Client Registration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db899-117">Rete endpoint client</span><span class="sxs-lookup"><span data-stu-id="db899-117">Client endpoint network</span></span></th>
<th><span data-ttu-id="db899-118">Server di rete</span><span class="sxs-lookup"><span data-stu-id="db899-118">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db899-119">IPv4</span><span class="sxs-lookup"><span data-stu-id="db899-119">IPv4</span></span></p></td>
<td><p><span data-ttu-id="db899-120">IPv4</span><span class="sxs-lookup"><span data-stu-id="db899-120">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db899-121">IPv4</span><span class="sxs-lookup"><span data-stu-id="db899-121">IPv4</span></span></p></td>
<td><p><span data-ttu-id="db899-122">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-122">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db899-123">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-123">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="db899-124">IPv4</span><span class="sxs-lookup"><span data-stu-id="db899-124">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db899-125">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-125">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="db899-126">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-126">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db899-127">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-127">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="db899-128">IPv6</span><span class="sxs-lookup"><span data-stu-id="db899-128">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db899-129">IPv6</span><span class="sxs-lookup"><span data-stu-id="db899-129">IPv6</span></span></p></td>
<td><p><span data-ttu-id="db899-130">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-130">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db899-131">IPv6</span><span class="sxs-lookup"><span data-stu-id="db899-131">IPv6</span></span></p></td>
<td><p><span data-ttu-id="db899-132">IPv6</span><span class="sxs-lookup"><span data-stu-id="db899-132">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="peer-to-peer-client"></a><span data-ttu-id="db899-133">Client peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="db899-133">Peer-to-Peer Client</span></span>

<span data-ttu-id="db899-134">Le comunicazioni peer-to-peer includono audio, audio/video, condivisione applicazioni e trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="db899-134">Peer-to-peer communications include audio, audio/video, application sharing, and file transfer.</span></span> <span data-ttu-id="db899-135">Dopo aver registrato correttamente entrambi i client, sono supportate le combinazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="db899-135">After both clients have successfully registered, the following combinations are supported.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db899-136">Endpoint client 1</span><span class="sxs-lookup"><span data-stu-id="db899-136">Client endpoint 1</span></span></th>
<th><span data-ttu-id="db899-137">Endpoint client 2</span><span class="sxs-lookup"><span data-stu-id="db899-137">Client endpoint 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db899-138">IPv4</span><span class="sxs-lookup"><span data-stu-id="db899-138">IPv4</span></span></p></td>
<td><p><span data-ttu-id="db899-139">IPv4</span><span class="sxs-lookup"><span data-stu-id="db899-139">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db899-140">IPv4</span><span class="sxs-lookup"><span data-stu-id="db899-140">IPv4</span></span></p></td>
<td><p><span data-ttu-id="db899-141">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-141">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db899-142">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-142">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="db899-143">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-143">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db899-144">IPv6</span><span class="sxs-lookup"><span data-stu-id="db899-144">IPv6</span></span></p></td>
<td><p><span data-ttu-id="db899-145">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-145">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db899-146">IPv6</span><span class="sxs-lookup"><span data-stu-id="db899-146">IPv6</span></span></p></td>
<td><p><span data-ttu-id="db899-147">IPv6</span><span class="sxs-lookup"><span data-stu-id="db899-147">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="conferencing"></a><span data-ttu-id="db899-148">Servizi di conferenza</span><span class="sxs-lookup"><span data-stu-id="db899-148">Conferencing</span></span>

<span data-ttu-id="db899-149">I servizi di conferenza includono audio/video, condivisione applicazioni e collaborazione ai dati (lavagna e condivisione di file).</span><span class="sxs-lookup"><span data-stu-id="db899-149">Conferencing includes audio/video, application sharing, and data collaboration (whiteboarding and file sharing).</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db899-150">Rete endpoint client</span><span class="sxs-lookup"><span data-stu-id="db899-150">Client endpoint network</span></span></th>
<th><span data-ttu-id="db899-151">Server di rete</span><span class="sxs-lookup"><span data-stu-id="db899-151">Server network</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db899-152">IPv4</span><span class="sxs-lookup"><span data-stu-id="db899-152">IPv4</span></span></p></td>
<td><p><span data-ttu-id="db899-153">IPv4</span><span class="sxs-lookup"><span data-stu-id="db899-153">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db899-154">IPv4</span><span class="sxs-lookup"><span data-stu-id="db899-154">IPv4</span></span></p></td>
<td><p><span data-ttu-id="db899-155">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-155">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db899-156">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-156">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="db899-157">IPv4</span><span class="sxs-lookup"><span data-stu-id="db899-157">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db899-158">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-158">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="db899-159">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-159">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db899-160">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-160">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="db899-161">IPv6</span><span class="sxs-lookup"><span data-stu-id="db899-161">IPv6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db899-162">IPv6</span><span class="sxs-lookup"><span data-stu-id="db899-162">IPv6</span></span></p></td>
<td><p><span data-ttu-id="db899-163">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-163">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db899-164">IPv6</span><span class="sxs-lookup"><span data-stu-id="db899-164">IPv6</span></span></p></td>
<td><p><span data-ttu-id="db899-165">IPv6</span><span class="sxs-lookup"><span data-stu-id="db899-165">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="mediation-serverpstn"></a><span data-ttu-id="db899-166">Mediation Server/PSTN</span><span class="sxs-lookup"><span data-stu-id="db899-166">Mediation Server/PSTN</span></span>

<span data-ttu-id="db899-167">Lync Server 2013 non supporta il bypass multimediale per le chiamate PSTN (Public Switched Telephone Network), se il traffico avviene tramite un'interfaccia IPv6.</span><span class="sxs-lookup"><span data-stu-id="db899-167">Lync Server 2013 does not support media bypass for public switched telephone network (PSTN) calls if the traffic is through an IPv6 interface.</span></span> <span data-ttu-id="db899-168">Se è necessario un bypass multimediale, è consigliabile che il gateway PSTN sia configurato per IPv4.</span><span class="sxs-lookup"><span data-stu-id="db899-168">If media bypass is required, we recommend that the PSTN gateway is configured to IPv4.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db899-169">Interfaccia primaria \*</span><span class="sxs-lookup"><span data-stu-id="db899-169">Primary interface\*</span></span></th>
<th><span data-ttu-id="db899-170">Interfaccia PSTN (in Mediation Server)</span><span class="sxs-lookup"><span data-stu-id="db899-170">PSTN interface (on Mediation Server)</span></span></th>
<th><span data-ttu-id="db899-171">Impostazione del gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="db899-171">PSTN gateway setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db899-172">IPv4</span><span class="sxs-lookup"><span data-stu-id="db899-172">IPv4</span></span></p></td>
<td><p><span data-ttu-id="db899-173">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-173">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="db899-174">IPv4</span><span class="sxs-lookup"><span data-stu-id="db899-174">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db899-175">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-175">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="db899-176">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-176">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="db899-177">IPv4</span><span class="sxs-lookup"><span data-stu-id="db899-177">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db899-178">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-178">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="db899-179">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-179">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="db899-180">IPv6</span><span class="sxs-lookup"><span data-stu-id="db899-180">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="db899-181">\*L'interfaccia principale è l'interfaccia che comunica con i componenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="db899-181">\* The primary interface is the interface that communicates with the Lync Server components.</span></span>

</div>

<div>

## <a name="remote-user-peer-to-peer-communications"></a><span data-ttu-id="db899-182">Comunicazioni peer-to-peer degli utenti remoti</span><span class="sxs-lookup"><span data-stu-id="db899-182">Remote User Peer-to-Peer Communications</span></span>

<span data-ttu-id="db899-183">Le comunicazioni peer-to-peer con gli utenti remoti includono messaggistica istantanea, audio/video, condivisione applicazioni e trasferimento di file.</span><span class="sxs-lookup"><span data-stu-id="db899-183">Peer-to-peer communications with remote users include instant messaging, audio/video, application sharing, and file transfer.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="db899-184">Rete remota degli utenti</span><span class="sxs-lookup"><span data-stu-id="db899-184">Remote user network</span></span></th>
<th><span data-ttu-id="db899-185">Edge Server (bordo esterno)</span><span class="sxs-lookup"><span data-stu-id="db899-185">Edge server (External edge)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="db899-186">IPv4</span><span class="sxs-lookup"><span data-stu-id="db899-186">IPv4</span></span></p></td>
<td><p><span data-ttu-id="db899-187">IPv4</span><span class="sxs-lookup"><span data-stu-id="db899-187">IPv4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db899-188">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-188">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="db899-189">IPv4</span><span class="sxs-lookup"><span data-stu-id="db899-189">IPv4</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db899-190">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-190">Dual stack</span></span></p></td>
<td><p><span data-ttu-id="db899-191">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-191">Dual stack</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db899-192">IPv6</span><span class="sxs-lookup"><span data-stu-id="db899-192">IPv6</span></span></p></td>
<td><p><span data-ttu-id="db899-193">Stack doppio</span><span class="sxs-lookup"><span data-stu-id="db899-193">Dual stack</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db899-194">IPv6</span><span class="sxs-lookup"><span data-stu-id="db899-194">IPv6</span></span></p></td>
<td><p><span data-ttu-id="db899-195">IPv6</span><span class="sxs-lookup"><span data-stu-id="db899-195">IPv6</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="front-end-pool-and-edge-pool-configuration"></a><span data-ttu-id="db899-196">Configurazione di pool e Edge pool Front-End</span><span class="sxs-lookup"><span data-stu-id="db899-196">Front End Pool and Edge Pool Configuration</span></span>

<span data-ttu-id="db899-197">La tabella seguente mostra la matrice di supporto tra il pool del server front-end e il pool di Edge Server interno.</span><span class="sxs-lookup"><span data-stu-id="db899-197">The following table shows the support matrix between the Front End Server pool and the internal Edge Server pool.</span></span>

### <a name="front-end-pool-and-edge-pool-internal-edge-matrix"></a><span data-ttu-id="db899-198">Pool di front end e pool Edge (bordo interno)</span><span class="sxs-lookup"><span data-stu-id="db899-198">Front End Pool and Edge Pool (Internal Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="db899-199"><strong>Bordo piscina: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="db899-199"><strong>Edge Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="db899-200"><strong>Bordo piscina: doppia pila</strong></span><span class="sxs-lookup"><span data-stu-id="db899-200"><strong>Edge Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="db899-201"><strong>Pool Edge: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="db899-201"><strong>Edge Pool: IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db899-202"><strong>Pool Front-end: IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="db899-202"><strong>Front End Pool: IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="db899-203">Sì</span><span class="sxs-lookup"><span data-stu-id="db899-203">Yes</span></span></p></td>
<td><p><span data-ttu-id="db899-204">Sì</span><span class="sxs-lookup"><span data-stu-id="db899-204">Yes</span></span></p></td>
<td><p><span data-ttu-id="db899-205">Supporto per riunioni private con ID conferenza di riunione dinamici</span><span class="sxs-lookup"><span data-stu-id="db899-205">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db899-206"><strong>Pool Front-end: doppia pila</strong></span><span class="sxs-lookup"><span data-stu-id="db899-206"><strong>Front End Pool: Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="db899-207">Sì</span><span class="sxs-lookup"><span data-stu-id="db899-207">Yes</span></span></p></td>
<td><p><span data-ttu-id="db899-208">Sì</span><span class="sxs-lookup"><span data-stu-id="db899-208">Yes</span></span></p></td>
<td><p><span data-ttu-id="db899-209">Supporto per riunioni private con ID conferenza di riunione dinamici</span><span class="sxs-lookup"><span data-stu-id="db899-209">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db899-210"><strong>Pool Front-end: IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="db899-210"><strong>Front End Pool: IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="db899-211">No</span><span class="sxs-lookup"><span data-stu-id="db899-211">No</span></span></p></td>
<td><p><span data-ttu-id="db899-212">No</span><span class="sxs-lookup"><span data-stu-id="db899-212">No</span></span></p></td>
<td><p><span data-ttu-id="db899-213">Sì</span><span class="sxs-lookup"><span data-stu-id="db899-213">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="db899-214">\*Usare questa combinazione solo in un ambiente lab.</span><span class="sxs-lookup"><span data-stu-id="db899-214">\* Use this combination only in a lab environment.</span></span>

<span data-ttu-id="db899-215">La tabella seguente è una matrice delle combinazioni supportate delle interfacce Edge interne ed esterne.</span><span class="sxs-lookup"><span data-stu-id="db899-215">The following table is a matrix of the supported combinations of internal and external edge interfaces.</span></span>

### <a name="edge-pool-internal-edge-and-edge-pool-external-edge-matrix"></a><span data-ttu-id="db899-216">Matrice pool Edge (bordo interno) e bordo piscina (bordo esterno)</span><span class="sxs-lookup"><span data-stu-id="db899-216">Edge Pool (Internal Edge) and Edge pool (External Edge) Matrix</span></span>

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
<td><p><span data-ttu-id="db899-217"><strong>Pool Edge (bordo esterno): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="db899-217"><strong>Edge Pool (External Edge) : IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="db899-218"><strong>Pool Edge (bordo esterno): doppia pila</strong></span><span class="sxs-lookup"><span data-stu-id="db899-218"><strong>Edge Pool (External Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="db899-219"><strong>Pool Edge (bordo esterno): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="db899-219"><strong>Edge Pool (External Edge): IPv6</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db899-220"><strong>Pool Edge (bordo interno): IPv4</strong></span><span class="sxs-lookup"><span data-stu-id="db899-220"><strong>Edge Pool (Internal Edge): IPv4</strong></span></span></p></td>
<td><p><span data-ttu-id="db899-221">Sì</span><span class="sxs-lookup"><span data-stu-id="db899-221">Yes</span></span></p></td>
<td><p><span data-ttu-id="db899-222">Sì</span><span class="sxs-lookup"><span data-stu-id="db899-222">Yes</span></span></p></td>
<td><p><span data-ttu-id="db899-223">Supporto per riunioni private con ID conferenza di riunione dinamici</span><span class="sxs-lookup"><span data-stu-id="db899-223">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="db899-224"><strong>Pool di bordi (bordo interno): doppia pila</strong></span><span class="sxs-lookup"><span data-stu-id="db899-224"><strong>Edge Pool (Internal Edge): Dual Stack</strong></span></span></p></td>
<td><p><span data-ttu-id="db899-225">No</span><span class="sxs-lookup"><span data-stu-id="db899-225">No</span></span></p></td>
<td><p><span data-ttu-id="db899-226">Sì</span><span class="sxs-lookup"><span data-stu-id="db899-226">Yes</span></span></p></td>
<td><p><span data-ttu-id="db899-227">Supporto per riunioni private con ID conferenza di riunione dinamici</span><span class="sxs-lookup"><span data-stu-id="db899-227">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="db899-228"><strong>Pool Edge (bordo interno): IPv6</strong></span><span class="sxs-lookup"><span data-stu-id="db899-228"><strong>Edge Pool (Internal Edge): IPv6</strong></span></span></p></td>
<td><p><span data-ttu-id="db899-229">No</span><span class="sxs-lookup"><span data-stu-id="db899-229">No</span></span></p></td>
<td><p><span data-ttu-id="db899-230">No</span><span class="sxs-lookup"><span data-stu-id="db899-230">No</span></span></p></td>
<td><p><span data-ttu-id="db899-231">Sì</span><span class="sxs-lookup"><span data-stu-id="db899-231">Yes\*</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="db899-232">\*Usare questa combinazione solo in un ambiente lab.</span><span class="sxs-lookup"><span data-stu-id="db899-232">\* Use this combination only in a lab environment.</span></span>

</div>

<div>

## <a name="advanced-enterprise-voice-support-for-ipv6"></a><span data-ttu-id="db899-233">Supporto per VoIP aziendale avanzato per IPv6</span><span class="sxs-lookup"><span data-stu-id="db899-233">Advanced Enterprise Voice Support for IPv6</span></span>

<span data-ttu-id="db899-234">Le distribuzioni che includono il controllo di ammissione alle chiamate (CAC), il 9-1-1 avanzato (E9-1-1) o l'esclusione multimediale devono essere configurate solo come IPv4 o come implementazione a doppio stack.</span><span class="sxs-lookup"><span data-stu-id="db899-234">Deployments that include call admission control (CAC), Enhanced 9-1-1 (E9-1-1), or media bypass must be configured as IPv4 only or as a dual-stacked implementation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="db899-235">In una distribuzione in pila doppia, anche se un client Lync si connette a un server Lync usando IPv6, Lync sarà utile per eseguire il mapping di un indirizzo IPv4 appropriato per supportare il servizio E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="db899-235">In a dual-stacked deployment, even if a Lync client connects to a Lync Server by using IPv6, Lync will make a best effort to map an appropriate IPv4 address to support E9-1-1.</span></span>



</div>

<span data-ttu-id="db899-236">Il servizio informazioni sulla posizione con indirizzi IPv6 non è supportato.</span><span class="sxs-lookup"><span data-stu-id="db899-236">Location Information service with IPv6 addresses is not supported.</span></span>

<span data-ttu-id="db899-237">La messaggistica unificata di Exchange non supporta IPv6.</span><span class="sxs-lookup"><span data-stu-id="db899-237">Exchange Unified Messaging (UM) does not support IPv6.</span></span> <span data-ttu-id="db899-238">Per la messaggistica unificata di Exchange, assicurati che la risoluzione DNS non restituisca un indirizzo IPv6.</span><span class="sxs-lookup"><span data-stu-id="db899-238">For Exchange UM, be sure that DNS resolution does not return an IPv6 address.</span></span> <span data-ttu-id="db899-239">L'uso di IPv6 può causare un errore quando le chiamate vengono inviate alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="db899-239">Using IPv6 may cause failure when calls are sent to voice mail.</span></span>

</div>

<div>

## <a name="other-lync-server-2013-feature-support-for-ipv6"></a><span data-ttu-id="db899-240">Altre funzionalità di Lync Server 2013 supportate per IPv6</span><span class="sxs-lookup"><span data-stu-id="db899-240">Other Lync Server 2013 Feature Support for IPv6</span></span>

<span data-ttu-id="db899-241">Oltre alle funzionalità e ai componenti menzionati in precedenza, Lync Server 2013 supporta IPv6 per le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="db899-241">In addition to the features and components mentioned previously, Lync Server 2013 supports IPv6 for the following features:</span></span>

  - <span data-ttu-id="db899-242">**Chat persistente**</span><span class="sxs-lookup"><span data-stu-id="db899-242">**Persistent Chat**</span></span>
    
    <span data-ttu-id="db899-243">Si configura IPv6 per la chat persistente usando generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="db899-243">You configure IPv6 for Persistent Chat by using Topology Builder.</span></span> <span data-ttu-id="db899-244">Per informazioni dettagliate sulla configurazione della chat persistente, vedere la documentazione relativa alla distribuzione di Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="db899-244">For details about configuring Persistent Chat, see the Deploying Persistent Chat Server documentation.</span></span>

  - <span data-ttu-id="db899-245">**Report di qualità dei dati (QoE) e registrazione dei dettagli delle chiamate (CDR)**</span><span class="sxs-lookup"><span data-stu-id="db899-245">**Quality of Experience (QoE) and call detail recording (CDR) reports**</span></span>
    
    <span data-ttu-id="db899-246">I report di monitoraggio includono l'indirizzo IP archiviato nel database del server di monitoraggio, indipendentemente dal tipo IPv4 o IPv6.</span><span class="sxs-lookup"><span data-stu-id="db899-246">Monitoring reports include the IP address as it is stored in the Monitoring Server database, whether of type IPv4 or IPv6.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

