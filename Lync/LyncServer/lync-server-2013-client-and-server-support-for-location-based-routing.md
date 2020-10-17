---
title: 'Lync Server 2013: supporto per client e server per il routing di Location-Based'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d85e2ce1738ee5de9d4d542cedd7a9e544771938
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529343"
---
# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="1393b-102">Supporto per client e server per il routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1393b-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1393b-103">_**Ultimo argomento modificato:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="1393b-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="1393b-104">Il routing Location-Based viene applicato da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1393b-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="1393b-105">Lync Server è in grado di identificare i siti di rete in cui gli utenti si connettono dall'interno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="1393b-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="1393b-106">Poiché gli utenti remoti si trovano all'esterno della rete aziendale, la loro posizione è considerata sconosciuta.</span><span class="sxs-lookup"><span data-stu-id="1393b-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="1393b-107">Supporto di Lync Server</span><span class="sxs-lookup"><span data-stu-id="1393b-107">Lync Server Support</span></span>

<span data-ttu-id="1393b-108">Location-Based routing richiede che Lync Server 2013 CU1 sia distribuito su tutti i pool Front end e i server Standard Edition in una determinata topologia.</span><span class="sxs-lookup"><span data-stu-id="1393b-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="1393b-109">Se Lync Server 2013 CU1 non è installato in alcuni componenti di Lync nella topologia, Location-Based restrizioni di routing non possono essere applicate completamente.</span><span class="sxs-lookup"><span data-stu-id="1393b-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="1393b-110">La tabella seguente identifica la combinazione di ruoli del server e versioni supportate per il routing Location-Based.</span><span class="sxs-lookup"><span data-stu-id="1393b-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1393b-111">Versione pool</span><span class="sxs-lookup"><span data-stu-id="1393b-111">Pool version</span></span></th>
<th><span data-ttu-id="1393b-112">Versione Mediation Server</span><span class="sxs-lookup"><span data-stu-id="1393b-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="1393b-113">Supportato</span><span class="sxs-lookup"><span data-stu-id="1393b-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1393b-114">Lync Server 2013 febbraio 2013 aggiornamento cumulativo</span><span class="sxs-lookup"><span data-stu-id="1393b-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="1393b-115">Lync Server 2013 febbraio 2013 aggiornamento cumulativo</span><span class="sxs-lookup"><span data-stu-id="1393b-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="1393b-116">sì</span><span class="sxs-lookup"><span data-stu-id="1393b-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1393b-117">Lync Server 2013 febbraio 2013 aggiornamento cumulativo</span><span class="sxs-lookup"><span data-stu-id="1393b-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="1393b-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1393b-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="1393b-119">no</span><span class="sxs-lookup"><span data-stu-id="1393b-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1393b-120">Lync Server 2013 febbraio 2013 aggiornamento cumulativo</span><span class="sxs-lookup"><span data-stu-id="1393b-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="1393b-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="1393b-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="1393b-122">no</span><span class="sxs-lookup"><span data-stu-id="1393b-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1393b-123">Lync Server 2013 febbraio 2013 aggiornamento cumulativo</span><span class="sxs-lookup"><span data-stu-id="1393b-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="1393b-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="1393b-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="1393b-125">no</span><span class="sxs-lookup"><span data-stu-id="1393b-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1393b-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1393b-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="1393b-127">qualsiasi</span><span class="sxs-lookup"><span data-stu-id="1393b-127">any</span></span></p></td>
<td><p><span data-ttu-id="1393b-128">no</span><span class="sxs-lookup"><span data-stu-id="1393b-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1393b-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="1393b-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="1393b-130">qualsiasi</span><span class="sxs-lookup"><span data-stu-id="1393b-130">any</span></span></p></td>
<td><p><span data-ttu-id="1393b-131">no</span><span class="sxs-lookup"><span data-stu-id="1393b-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1393b-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="1393b-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="1393b-133">qualsiasi</span><span class="sxs-lookup"><span data-stu-id="1393b-133">any</span></span></p></td>
<td><p><span data-ttu-id="1393b-134">no</span><span class="sxs-lookup"><span data-stu-id="1393b-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="1393b-135">Supporto per client Lync</span><span class="sxs-lookup"><span data-stu-id="1393b-135">Lync Client Support</span></span>

<span data-ttu-id="1393b-136">Nella tabella seguente vengono identificati i client che Location-Based i supporti di routing.</span><span class="sxs-lookup"><span data-stu-id="1393b-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1393b-137">Tipo di client</span><span class="sxs-lookup"><span data-stu-id="1393b-137">Client type</span></span></th>
<th><span data-ttu-id="1393b-138">Supportato</span><span class="sxs-lookup"><span data-stu-id="1393b-138">Supported</span></span></th>
<th><span data-ttu-id="1393b-139">Dettagli</span><span class="sxs-lookup"><span data-stu-id="1393b-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1393b-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="1393b-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="1393b-141">sì</span><span class="sxs-lookup"><span data-stu-id="1393b-141">yes</span></span></p></td>
<td><p><span data-ttu-id="1393b-142">Incluso Lync 2013 febbraio 2013 Cumulative Update</span><span class="sxs-lookup"><span data-stu-id="1393b-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1393b-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="1393b-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="1393b-144">sì</span><span class="sxs-lookup"><span data-stu-id="1393b-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1393b-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="1393b-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="1393b-146">no</span><span class="sxs-lookup"><span data-stu-id="1393b-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1393b-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="1393b-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="1393b-148">sì</span><span class="sxs-lookup"><span data-stu-id="1393b-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1393b-149">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="1393b-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="1393b-150">sì</span><span class="sxs-lookup"><span data-stu-id="1393b-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1393b-151">Lync per Windows 8</span><span class="sxs-lookup"><span data-stu-id="1393b-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="1393b-152">no</span><span class="sxs-lookup"><span data-stu-id="1393b-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1393b-153">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="1393b-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="1393b-154">no</span><span class="sxs-lookup"><span data-stu-id="1393b-154">no</span></span></p></td>
<td><p><span data-ttu-id="1393b-155">Il VoIP deve essere disabilitato per i client Lync Mobile 2013 se utilizzato dagli utenti con Location-Based routing abilitato.</span><span class="sxs-lookup"><span data-stu-id="1393b-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1393b-156">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="1393b-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="1393b-157">sì</span><span class="sxs-lookup"><span data-stu-id="1393b-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="1393b-158">Per disabilitare VoIP per i client Lync Mobile 2013, assegnare un criterio per dispositivi mobili con l'impostazione, IP audio/video, disabilitato per tutti gli utenti abilitati per il routing in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="1393b-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="1393b-159">Per ulteriori informazioni sui criteri per dispositivi mobili, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="1393b-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1393b-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1393b-160">See Also</span></span>


[<span data-ttu-id="1393b-161">Pianificazione del routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1393b-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

