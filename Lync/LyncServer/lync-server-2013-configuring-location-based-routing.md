---
title: 'Lync Server 2013: Configurazione del routing in base alla posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a682f6b550f982f929a83bc8c2f430e89b9452fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978736"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="375bc-102">Configurazione del routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="375bc-102">Configuring Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="375bc-103">_**Argomento Ultima modifica:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="375bc-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="375bc-104">Lync Server 2013 CU1, il routing basato sulla posizione è una caratteristica di Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="375bc-104">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="375bc-105">Il routing basato sulla posizione è una caratteristica di gestione delle chiamate che controlla il modo in cui le chiamate vengono instradate da Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="375bc-105">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="375bc-106">Impone le restrizioni sulla possibilità di indirizzare le chiamate a destinazioni PBX o PSTN in base alla posizione del chiamante di Lync.</span><span class="sxs-lookup"><span data-stu-id="375bc-106">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="375bc-107">Il routing basato sulla posizione applica le regole di autorizzazione delle chiamate alle chiamate PSTN in base al percorso di rete del chiamante.</span><span class="sxs-lookup"><span data-stu-id="375bc-107">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="375bc-108">La posizione del chiamante viene determinata in base al sito di rete associato alla subnet di rete a cui è connesso il chiamante.</span><span class="sxs-lookup"><span data-stu-id="375bc-108">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="375bc-109">La configurazione del routing basato sulla posizione richiede prima di tutto la distribuzione di VoIP aziendale, quindi la configurazione di aree di rete, siti e subnet.</span><span class="sxs-lookup"><span data-stu-id="375bc-109">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="375bc-110">In questo articolo viene impostata la base per l'abilitazione del routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="375bc-110">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="375bc-111">Prima di distribuire il routing basato sulla posizione, è prima necessario distribuire Enterprise Voice e configurare aree di rete, siti e associare subnet di rete ai siti di rete.</span><span class="sxs-lookup"><span data-stu-id="375bc-111">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="375bc-112">Una volta completato, è possibile configurare il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="375bc-112">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="375bc-113">Per istruzioni su come configurare aree di rete, siti e subnet, vedere [distribuzione di funzionalità vocali avanzate in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="375bc-113">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="375bc-114">Questa sezione illustra la configurazione del routing basato sulla posizione usando l'esempio seguente come illustrazione.</span><span class="sxs-lookup"><span data-stu-id="375bc-114">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="375bc-115">(images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Esempio di") routing basato ![sulla posizione]della VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="375bc-115">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="375bc-116">La tabella seguente rappresenta gli utenti definiti in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="375bc-116">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="375bc-117">Tipo di endpoint</span><span class="sxs-lookup"><span data-stu-id="375bc-117">Endpoint type</span></span></th>
<th><span data-ttu-id="375bc-118">Posizione</span><span class="sxs-lookup"><span data-stu-id="375bc-118">Location</span></span></th>
<th><span data-ttu-id="375bc-119">Utenti</span><span class="sxs-lookup"><span data-stu-id="375bc-119">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="375bc-120">Lync</span><span class="sxs-lookup"><span data-stu-id="375bc-120">Lync</span></span></p></td>
<td><p><span data-ttu-id="375bc-121">Ufficio aziendale di Delhi</span><span class="sxs-lookup"><span data-stu-id="375bc-121">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="375bc-122">CANC-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="375bc-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="375bc-123">Lync</span><span class="sxs-lookup"><span data-stu-id="375bc-123">Lync</span></span></p></td>
<td><p><span data-ttu-id="375bc-124">Ufficio aziendale di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="375bc-124">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="375bc-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="375bc-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="375bc-126">Lync</span><span class="sxs-lookup"><span data-stu-id="375bc-126">Lync</span></span></p></td>
<td><p><span data-ttu-id="375bc-127">Sconosciuto (ad esempio Hotel)</span><span class="sxs-lookup"><span data-stu-id="375bc-127">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="375bc-128">UNK-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="375bc-128">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="375bc-129">PBX</span><span class="sxs-lookup"><span data-stu-id="375bc-129">PBX</span></span></p></td>
<td><p><span data-ttu-id="375bc-130">Ufficio aziendale di Delhi</span><span class="sxs-lookup"><span data-stu-id="375bc-130">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="375bc-131">DEL-PBX-1, DEL-PBX-2</span><span class="sxs-lookup"><span data-stu-id="375bc-131">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="375bc-132">PBX</span><span class="sxs-lookup"><span data-stu-id="375bc-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="375bc-133">Ufficio aziendale di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="375bc-133">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="375bc-134">HYD-PBX-1, HYD-PBX-2</span><span class="sxs-lookup"><span data-stu-id="375bc-134">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="375bc-135">PSTN</span><span class="sxs-lookup"><span data-stu-id="375bc-135">PSTN</span></span></p></td>
<td><p><span data-ttu-id="375bc-136">Sconosciuto</span><span class="sxs-lookup"><span data-stu-id="375bc-136">Unknown</span></span></p></td>
<td><p><span data-ttu-id="375bc-137">PSTN-1, PSTN-2, PSTN-3</span><span class="sxs-lookup"><span data-stu-id="375bc-137">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="375bc-138">La tabella seguente rappresenta i sistemi illustrati in questo esempio di ambiente.</span><span class="sxs-lookup"><span data-stu-id="375bc-138">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="375bc-139">Sistema</span><span class="sxs-lookup"><span data-stu-id="375bc-139">System</span></span></th>
<th><span data-ttu-id="375bc-140">Posizione</span><span class="sxs-lookup"><span data-stu-id="375bc-140">Location</span></span></th>
<th><span data-ttu-id="375bc-141">Nome</span><span class="sxs-lookup"><span data-stu-id="375bc-141">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="375bc-142">Pool di Lync Server 2013 CU1</span><span class="sxs-lookup"><span data-stu-id="375bc-142">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="375bc-143">qualsiasi</span><span class="sxs-lookup"><span data-stu-id="375bc-143">any</span></span></p></td>
<td><p><span data-ttu-id="375bc-144">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="375bc-144">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="375bc-145">Lync Server 2013 CU1, Mediation Server</span><span class="sxs-lookup"><span data-stu-id="375bc-145">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="375bc-146">qualsiasi</span><span class="sxs-lookup"><span data-stu-id="375bc-146">any</span></span></p></td>
<td><p><span data-ttu-id="375bc-147">MS-PL1</span><span class="sxs-lookup"><span data-stu-id="375bc-147">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="375bc-148">Gateway PSTN 1</span><span class="sxs-lookup"><span data-stu-id="375bc-148">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="375bc-149">Delhi</span><span class="sxs-lookup"><span data-stu-id="375bc-149">Delhi</span></span></p></td>
<td><p><span data-ttu-id="375bc-150">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="375bc-150">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="375bc-151">Gateway PSTN 2</span><span class="sxs-lookup"><span data-stu-id="375bc-151">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="375bc-152">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="375bc-152">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="375bc-153">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="375bc-153">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="375bc-154">PBX 1</span><span class="sxs-lookup"><span data-stu-id="375bc-154">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="375bc-155">Delhi</span><span class="sxs-lookup"><span data-stu-id="375bc-155">Delhi</span></span></p></td>
<td><p><span data-ttu-id="375bc-156">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="375bc-156">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="375bc-157">PBX 2</span><span class="sxs-lookup"><span data-stu-id="375bc-157">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="375bc-158">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="375bc-158">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="375bc-159">ROSSO-PBX</span><span class="sxs-lookup"><span data-stu-id="375bc-159">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="375bc-160">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="375bc-160">In This Section</span></span>

  - [<span data-ttu-id="375bc-161">Configurazione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="375bc-161">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="375bc-162">Distribuzione di aree geografiche, siti e subnet di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="375bc-162">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="375bc-163">Abilitazione del routing basato sulla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="375bc-163">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="375bc-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="375bc-164">See Also</span></span>


[<span data-ttu-id="375bc-165">Distribuzione di funzionalità vocali avanzate di Enterprise in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="375bc-165">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

