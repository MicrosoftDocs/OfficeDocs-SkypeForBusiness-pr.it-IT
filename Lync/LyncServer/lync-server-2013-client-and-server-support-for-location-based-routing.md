---
title: 'Lync Server 2013: Supporto per client e server per il routing in base alla posizione'
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
ms.openlocfilehash: 5ad7ead20eb9961180fec9204a84b3392b7fa96f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729856"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="2b1dd-102">Supporto per client e server per il routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b1dd-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b1dd-103">_**Argomento Ultima modifica:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="2b1dd-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="2b1dd-104">Il routing basato sulla posizione viene applicato da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2b1dd-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="2b1dd-105">Lync Server può identificare i siti di rete in cui gli utenti si connettono dall'interno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="2b1dd-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="2b1dd-106">Poiché gli utenti remoti si trovano all'esterno della rete aziendale, la loro posizione è considerata sconosciuta.</span><span class="sxs-lookup"><span data-stu-id="2b1dd-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="2b1dd-107">Supporto di Lync Server</span><span class="sxs-lookup"><span data-stu-id="2b1dd-107">Lync Server Support</span></span>

<span data-ttu-id="2b1dd-108">Il routing basato sulla posizione richiede che Lync Server 2013 CU1 sia distribuito in tutti i pool Front end e nei server Standard Edition in una determinata topologia.</span><span class="sxs-lookup"><span data-stu-id="2b1dd-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="2b1dd-109">Se Lync Server 2013 CU1 non è installato in alcuni componenti Lync della topologia, le restrizioni di routing basate sulla posizione non possono essere applicate completamente.</span><span class="sxs-lookup"><span data-stu-id="2b1dd-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="2b1dd-110">La tabella seguente identifica la combinazione di ruoli server e versioni supportate per il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="2b1dd-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b1dd-111">Versione pool</span><span class="sxs-lookup"><span data-stu-id="2b1dd-111">Pool version</span></span></th>
<th><span data-ttu-id="2b1dd-112">Versione Mediation Server</span><span class="sxs-lookup"><span data-stu-id="2b1dd-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="2b1dd-113">Supportati</span><span class="sxs-lookup"><span data-stu-id="2b1dd-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b1dd-114">Aggiornamento cumulativo di Lync Server 2013 febbraio 2013</span><span class="sxs-lookup"><span data-stu-id="2b1dd-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-115">Aggiornamento cumulativo di Lync Server 2013 febbraio 2013</span><span class="sxs-lookup"><span data-stu-id="2b1dd-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-116">Sì</span><span class="sxs-lookup"><span data-stu-id="2b1dd-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b1dd-117">Aggiornamento cumulativo di Lync Server 2013 febbraio 2013</span><span class="sxs-lookup"><span data-stu-id="2b1dd-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b1dd-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-119">non</span><span class="sxs-lookup"><span data-stu-id="2b1dd-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b1dd-120">Aggiornamento cumulativo di Lync Server 2013 febbraio 2013</span><span class="sxs-lookup"><span data-stu-id="2b1dd-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2b1dd-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-122">non</span><span class="sxs-lookup"><span data-stu-id="2b1dd-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b1dd-123">Aggiornamento cumulativo di Lync Server 2013 febbraio 2013</span><span class="sxs-lookup"><span data-stu-id="2b1dd-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="2b1dd-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-125">non</span><span class="sxs-lookup"><span data-stu-id="2b1dd-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b1dd-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b1dd-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-127">qualsiasi</span><span class="sxs-lookup"><span data-stu-id="2b1dd-127">any</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-128">non</span><span class="sxs-lookup"><span data-stu-id="2b1dd-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b1dd-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="2b1dd-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-130">qualsiasi</span><span class="sxs-lookup"><span data-stu-id="2b1dd-130">any</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-131">non</span><span class="sxs-lookup"><span data-stu-id="2b1dd-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b1dd-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="2b1dd-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-133">qualsiasi</span><span class="sxs-lookup"><span data-stu-id="2b1dd-133">any</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-134">non</span><span class="sxs-lookup"><span data-stu-id="2b1dd-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="2b1dd-135">Supporto client Lync</span><span class="sxs-lookup"><span data-stu-id="2b1dd-135">Lync Client Support</span></span>

<span data-ttu-id="2b1dd-136">La tabella seguente identifica i client supportati dal routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="2b1dd-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b1dd-137">Tipo di client</span><span class="sxs-lookup"><span data-stu-id="2b1dd-137">Client type</span></span></th>
<th><span data-ttu-id="2b1dd-138">Supportati</span><span class="sxs-lookup"><span data-stu-id="2b1dd-138">Supported</span></span></th>
<th><span data-ttu-id="2b1dd-139">Dettagli</span><span class="sxs-lookup"><span data-stu-id="2b1dd-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b1dd-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="2b1dd-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-141">Sì</span><span class="sxs-lookup"><span data-stu-id="2b1dd-141">yes</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-142">Incluso l'aggiornamento cumulativo di Lync 2013 febbraio 2013</span><span class="sxs-lookup"><span data-stu-id="2b1dd-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b1dd-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="2b1dd-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-144">Sì</span><span class="sxs-lookup"><span data-stu-id="2b1dd-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b1dd-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="2b1dd-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-146">non</span><span class="sxs-lookup"><span data-stu-id="2b1dd-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b1dd-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="2b1dd-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-148">Sì</span><span class="sxs-lookup"><span data-stu-id="2b1dd-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b1dd-149">Assistente di Lync</span><span class="sxs-lookup"><span data-stu-id="2b1dd-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-150">Sì</span><span class="sxs-lookup"><span data-stu-id="2b1dd-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b1dd-151">Lync per Windows 8</span><span class="sxs-lookup"><span data-stu-id="2b1dd-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-152">non</span><span class="sxs-lookup"><span data-stu-id="2b1dd-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b1dd-153">Lync Mobile 2013</span><span class="sxs-lookup"><span data-stu-id="2b1dd-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-154">non</span><span class="sxs-lookup"><span data-stu-id="2b1dd-154">no</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-155">Il VoIP deve essere disabilitato per i client Lync Mobile 2013 se usato dagli utenti con il routing basato sulla posizione abilitato.</span><span class="sxs-lookup"><span data-stu-id="2b1dd-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b1dd-156">Lync Mobile 2010</span><span class="sxs-lookup"><span data-stu-id="2b1dd-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="2b1dd-157">Sì</span><span class="sxs-lookup"><span data-stu-id="2b1dd-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="2b1dd-158">Per disabilitare il VoIP per i client di Lync Mobile 2013, assegnare un criterio di mobilità con l'impostazione, l'audio/video IP, disabilitato per tutti gli utenti abilitati per il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="2b1dd-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="2b1dd-159">Per altre informazioni sui criteri di mobilità, vedere <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="2b1dd-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="2b1dd-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b1dd-160">See Also</span></span>


[<span data-ttu-id="2b1dd-161">Pianificazione del routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2b1dd-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

