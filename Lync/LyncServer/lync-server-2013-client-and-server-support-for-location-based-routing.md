---
title: 'Lync Server 2013: supporto per client e server per il routing di Location-Based'
description: 'Lync Server 2013: supporto per client e server per il routing Location-Based.'
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
ms.openlocfilehash: 20dca7444f58ee62dbc36edbb7d9e1c976a97807
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549632"
---
# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="5bca7-103">Supporto per client e server per il routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bca7-103">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5bca7-104">_**Ultimo argomento modificato:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="5bca7-104">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="5bca7-105">Il routing Location-Based viene applicato da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5bca7-105">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="5bca7-106">Lync Server è in grado di identificare i siti di rete in cui gli utenti si connettono dall'interno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="5bca7-106">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="5bca7-107">Poiché gli utenti remoti si trovano all'esterno della rete aziendale, la loro posizione è considerata sconosciuta.</span><span class="sxs-lookup"><span data-stu-id="5bca7-107">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="5bca7-108">Supporto di Lync Server</span><span class="sxs-lookup"><span data-stu-id="5bca7-108">Lync Server Support</span></span>

<span data-ttu-id="5bca7-109">Location-Based routing richiede che Lync Server 2013 CU1 sia distribuito su tutti i pool Front end e i server Standard Edition in una determinata topologia.</span><span class="sxs-lookup"><span data-stu-id="5bca7-109">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="5bca7-110">Se Lync Server 2013 CU1 non è installato in alcuni componenti di Lync nella topologia, Location-Based restrizioni di routing non possono essere applicate completamente.</span><span class="sxs-lookup"><span data-stu-id="5bca7-110">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="5bca7-111">La tabella seguente identifica la combinazione di ruoli del server e versioni supportate per il routing Location-Based.</span><span class="sxs-lookup"><span data-stu-id="5bca7-111">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5bca7-112">Versione pool</span><span class="sxs-lookup"><span data-stu-id="5bca7-112">Pool version</span></span></th>
<th><span data-ttu-id="5bca7-113">Versione Mediation Server</span><span class="sxs-lookup"><span data-stu-id="5bca7-113">Mediation Server version</span></span></th>
<th><span data-ttu-id="5bca7-114">Supportato</span><span class="sxs-lookup"><span data-stu-id="5bca7-114">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5bca7-115">Lync Server 2013 febbraio 2013 aggiornamento cumulativo</span><span class="sxs-lookup"><span data-stu-id="5bca7-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="5bca7-116">Lync Server 2013 febbraio 2013 aggiornamento cumulativo</span><span class="sxs-lookup"><span data-stu-id="5bca7-116">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="5bca7-117">sì</span><span class="sxs-lookup"><span data-stu-id="5bca7-117">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bca7-118">Lync Server 2013 febbraio 2013 aggiornamento cumulativo</span><span class="sxs-lookup"><span data-stu-id="5bca7-118">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="5bca7-119">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bca7-119">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="5bca7-120">no</span><span class="sxs-lookup"><span data-stu-id="5bca7-120">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bca7-121">Lync Server 2013 febbraio 2013 aggiornamento cumulativo</span><span class="sxs-lookup"><span data-stu-id="5bca7-121">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="5bca7-122">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="5bca7-122">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="5bca7-123">no</span><span class="sxs-lookup"><span data-stu-id="5bca7-123">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bca7-124">Lync Server 2013 febbraio 2013 aggiornamento cumulativo</span><span class="sxs-lookup"><span data-stu-id="5bca7-124">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="5bca7-125">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="5bca7-125">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="5bca7-126">no</span><span class="sxs-lookup"><span data-stu-id="5bca7-126">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bca7-127">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bca7-127">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="5bca7-128">qualsiasi</span><span class="sxs-lookup"><span data-stu-id="5bca7-128">any</span></span></p></td>
<td><p><span data-ttu-id="5bca7-129">no</span><span class="sxs-lookup"><span data-stu-id="5bca7-129">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bca7-130">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="5bca7-130">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="5bca7-131">qualsiasi</span><span class="sxs-lookup"><span data-stu-id="5bca7-131">any</span></span></p></td>
<td><p><span data-ttu-id="5bca7-132">no</span><span class="sxs-lookup"><span data-stu-id="5bca7-132">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bca7-133">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="5bca7-133">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="5bca7-134">qualsiasi</span><span class="sxs-lookup"><span data-stu-id="5bca7-134">any</span></span></p></td>
<td><p><span data-ttu-id="5bca7-135">no</span><span class="sxs-lookup"><span data-stu-id="5bca7-135">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="5bca7-136">Supporto per client Lync</span><span class="sxs-lookup"><span data-stu-id="5bca7-136">Lync Client Support</span></span>

<span data-ttu-id="5bca7-137">Nella tabella seguente vengono identificati i client che Location-Based i supporti di routing.</span><span class="sxs-lookup"><span data-stu-id="5bca7-137">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="5bca7-138">Tipo di client</span><span class="sxs-lookup"><span data-stu-id="5bca7-138">Client type</span></span></th>
<th><span data-ttu-id="5bca7-139">Supportato</span><span class="sxs-lookup"><span data-stu-id="5bca7-139">Supported</span></span></th>
<th><span data-ttu-id="5bca7-140">Dettagli</span><span class="sxs-lookup"><span data-stu-id="5bca7-140">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="5bca7-141">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="5bca7-141">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="5bca7-142">sì</span><span class="sxs-lookup"><span data-stu-id="5bca7-142">yes</span></span></p></td>
<td><p><span data-ttu-id="5bca7-143">Incluso Lync 2013 febbraio 2013 Cumulative Update</span><span class="sxs-lookup"><span data-stu-id="5bca7-143">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bca7-144">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="5bca7-144">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="5bca7-145">sì</span><span class="sxs-lookup"><span data-stu-id="5bca7-145">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bca7-146">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="5bca7-146">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="5bca7-147">no</span><span class="sxs-lookup"><span data-stu-id="5bca7-147">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bca7-148">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="5bca7-148">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="5bca7-149">sì</span><span class="sxs-lookup"><span data-stu-id="5bca7-149">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bca7-150">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="5bca7-150">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="5bca7-151">sì</span><span class="sxs-lookup"><span data-stu-id="5bca7-151">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bca7-152">Lync per Windows 8</span><span class="sxs-lookup"><span data-stu-id="5bca7-152">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="5bca7-153">no</span><span class="sxs-lookup"><span data-stu-id="5bca7-153">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="5bca7-154">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="5bca7-154">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="5bca7-155">no</span><span class="sxs-lookup"><span data-stu-id="5bca7-155">no</span></span></p></td>
<td><p><span data-ttu-id="5bca7-156">Il VoIP deve essere disabilitato per i client Lync Mobile 2013 se utilizzato dagli utenti con Location-Based routing abilitato.</span><span class="sxs-lookup"><span data-stu-id="5bca7-156">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="5bca7-157">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="5bca7-157">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="5bca7-158">sì</span><span class="sxs-lookup"><span data-stu-id="5bca7-158">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="5bca7-159">Per disabilitare VoIP per i client Lync Mobile 2013, assegnare un criterio per dispositivi mobili con l'impostazione, IP audio/video, disabilitato per tutti gli utenti abilitati per il routing in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="5bca7-159">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="5bca7-160">Per ulteriori informazioni sui criteri per dispositivi mobili, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="5bca7-160">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="5bca7-161">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5bca7-161">See Also</span></span>


[<span data-ttu-id="5bca7-162">Pianificazione del routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5bca7-162">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

