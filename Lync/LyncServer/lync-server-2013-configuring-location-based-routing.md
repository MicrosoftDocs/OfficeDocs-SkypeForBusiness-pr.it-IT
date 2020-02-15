---
title: 'Lync Server 2013: configurazione del routing in base alla posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 31e8877c4691decfe0c2e65fd820e97432e095aa
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030560"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="d1972-102">Configurazione del routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1972-102">Configuring Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1972-103">_**Ultimo argomento modificato:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="d1972-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="d1972-104">Lync Server 2013 CU1, il routing in base alla posizione è una funzionalità di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="d1972-104">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="d1972-105">Il routing in base alla posizione è una funzionalità di gestione delle chiamate che controlla il modo in cui vengono instradate da Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="d1972-105">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="d1972-106">Impone restrizioni sul fatto che le chiamate possano essere instradate a destinazioni PBX o PSTN in base alla posizione del chiamante di Lync.</span><span class="sxs-lookup"><span data-stu-id="d1972-106">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="d1972-107">Il routing in base alla posizione applica le regole di autorizzazione di chiamata alle chiamate PSTN basate sul percorso di rete del chiamante.</span><span class="sxs-lookup"><span data-stu-id="d1972-107">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="d1972-108">La posizione del chiamante viene determinata in base al sito di rete associato alla subnet di rete a cui è connesso il chiamante.</span><span class="sxs-lookup"><span data-stu-id="d1972-108">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="d1972-109">La configurazione del routing in base alla posizione richiede la prima distribuzione di VoIP aziendale, quindi la configurazione di aree di rete, siti e subnet.</span><span class="sxs-lookup"><span data-stu-id="d1972-109">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="d1972-110">In questo modo viene impostata la base per l'abilitazione del routing in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="d1972-110">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="d1972-111">Prima di distribuire il routing in base alla posizione, è necessario prima distribuire VoIP aziendale e configurare aree di rete, siti e associare le subnet di rete ai siti di rete.</span><span class="sxs-lookup"><span data-stu-id="d1972-111">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="d1972-112">Una volta completato, è possibile configurare il routing in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="d1972-112">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="d1972-113">Per istruzioni su come configurare aree di rete, siti e subnet, vedere [Deploying Advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="d1972-113">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="d1972-114">In questa sezione viene illustrata la configurazione del routing in base alla posizione utilizzando l'esempio seguente come illustrazione.</span><span class="sxs-lookup"><span data-stu-id="d1972-114">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="d1972-115">![Esempio di routing basato sulla posizione di VoIP aziendale](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Esempio di routing basato sulla posizione di VoIP aziendale")</span><span class="sxs-lookup"><span data-stu-id="d1972-115">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="d1972-116">La tabella seguente rappresenta gli utenti definiti in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="d1972-116">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1972-117">Tipo di endpoint</span><span class="sxs-lookup"><span data-stu-id="d1972-117">Endpoint type</span></span></th>
<th><span data-ttu-id="d1972-118">Posizione</span><span class="sxs-lookup"><span data-stu-id="d1972-118">Location</span></span></th>
<th><span data-ttu-id="d1972-119">Utenti</span><span class="sxs-lookup"><span data-stu-id="d1972-119">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1972-120">Lync</span><span class="sxs-lookup"><span data-stu-id="d1972-120">Lync</span></span></p></td>
<td><p><span data-ttu-id="d1972-121">Ufficio corporativo di Delhi</span><span class="sxs-lookup"><span data-stu-id="d1972-121">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="d1972-122">CANC-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="d1972-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1972-123">Lync</span><span class="sxs-lookup"><span data-stu-id="d1972-123">Lync</span></span></p></td>
<td><p><span data-ttu-id="d1972-124">Ufficio corporativo di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="d1972-124">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="d1972-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="d1972-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1972-126">Lync</span><span class="sxs-lookup"><span data-stu-id="d1972-126">Lync</span></span></p></td>
<td><p><span data-ttu-id="d1972-127">Unknown (vale a dire Hotel)</span><span class="sxs-lookup"><span data-stu-id="d1972-127">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="d1972-128">UNK-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="d1972-128">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1972-129">PBX</span><span class="sxs-lookup"><span data-stu-id="d1972-129">PBX</span></span></p></td>
<td><p><span data-ttu-id="d1972-130">Ufficio corporativo di Delhi</span><span class="sxs-lookup"><span data-stu-id="d1972-130">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="d1972-131">DEL-PBX-1, DEL-PBX-2</span><span class="sxs-lookup"><span data-stu-id="d1972-131">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1972-132">PBX</span><span class="sxs-lookup"><span data-stu-id="d1972-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="d1972-133">Ufficio corporativo di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="d1972-133">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="d1972-134">HYD-PBX-1, HYD-PBX-2</span><span class="sxs-lookup"><span data-stu-id="d1972-134">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1972-135">PSTN</span><span class="sxs-lookup"><span data-stu-id="d1972-135">PSTN</span></span></p></td>
<td><p><span data-ttu-id="d1972-136">Unknown</span><span class="sxs-lookup"><span data-stu-id="d1972-136">Unknown</span></span></p></td>
<td><p><span data-ttu-id="d1972-137">PSTN-1, PSTN-2, PSTN-3</span><span class="sxs-lookup"><span data-stu-id="d1972-137">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="d1972-138">La tabella seguente rappresenta i sistemi illustrati in questo esempio di ambiente.</span><span class="sxs-lookup"><span data-stu-id="d1972-138">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1972-139">Sistema</span><span class="sxs-lookup"><span data-stu-id="d1972-139">System</span></span></th>
<th><span data-ttu-id="d1972-140">Posizione</span><span class="sxs-lookup"><span data-stu-id="d1972-140">Location</span></span></th>
<th><span data-ttu-id="d1972-141">Nome</span><span class="sxs-lookup"><span data-stu-id="d1972-141">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1972-142">Lync Server 2013 CU1 pool</span><span class="sxs-lookup"><span data-stu-id="d1972-142">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="d1972-143">qualsiasi</span><span class="sxs-lookup"><span data-stu-id="d1972-143">any</span></span></p></td>
<td><p><span data-ttu-id="d1972-144">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="d1972-144">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1972-145">Lync Server 2013 CU1, Mediation Server</span><span class="sxs-lookup"><span data-stu-id="d1972-145">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="d1972-146">qualsiasi</span><span class="sxs-lookup"><span data-stu-id="d1972-146">any</span></span></p></td>
<td><p><span data-ttu-id="d1972-147">MS-PL1</span><span class="sxs-lookup"><span data-stu-id="d1972-147">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1972-148">Gateway PSTN 1</span><span class="sxs-lookup"><span data-stu-id="d1972-148">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="d1972-149">Delhi</span><span class="sxs-lookup"><span data-stu-id="d1972-149">Delhi</span></span></p></td>
<td><p><span data-ttu-id="d1972-150">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="d1972-150">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1972-151">Gateway PSTN 2</span><span class="sxs-lookup"><span data-stu-id="d1972-151">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="d1972-152">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="d1972-152">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="d1972-153">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="d1972-153">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1972-154">PBX 1</span><span class="sxs-lookup"><span data-stu-id="d1972-154">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="d1972-155">Delhi</span><span class="sxs-lookup"><span data-stu-id="d1972-155">Delhi</span></span></p></td>
<td><p><span data-ttu-id="d1972-156">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="d1972-156">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1972-157">PBX 2</span><span class="sxs-lookup"><span data-stu-id="d1972-157">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="d1972-158">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="d1972-158">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="d1972-159">ROSSO-PBX</span><span class="sxs-lookup"><span data-stu-id="d1972-159">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="d1972-160">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="d1972-160">In This Section</span></span>

  - [<span data-ttu-id="d1972-161">Configurazione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1972-161">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="d1972-162">Distribuzione di aree di rete, siti e subnet in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1972-162">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="d1972-163">Abilitazione del routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1972-163">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="d1972-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d1972-164">See Also</span></span>


[<span data-ttu-id="d1972-165">Distribuzione di funzionalità di VoIP aziendale avanzate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1972-165">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

