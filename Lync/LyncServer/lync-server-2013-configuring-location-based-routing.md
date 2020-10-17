---
title: 'Lync Server 2013: configurazione del routing Location-Based'
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
ms.openlocfilehash: 7b703aa084204a2c103e02ebff5f913a6647ae94
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517417"
---
# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="52575-102">Configurazione del routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52575-102">Configuring Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="52575-103">_**Ultimo argomento modificato:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="52575-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="52575-104">Lync Server 2013 CU1, Location-Based routing è una funzionalità di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="52575-104">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="52575-105">Location-Based routing è una funzionalità di gestione delle chiamate che controlla il modo in cui vengono instradate tramite Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="52575-105">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="52575-106">Impone restrizioni sul fatto che le chiamate possano essere instradate a destinazioni PBX o PSTN in base alla posizione del chiamante di Lync.</span><span class="sxs-lookup"><span data-stu-id="52575-106">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="52575-107">Location-Based routing applica le regole di autorizzazione di chiamata alle chiamate PSTN in base al percorso di rete del chiamante.</span><span class="sxs-lookup"><span data-stu-id="52575-107">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="52575-108">La posizione del chiamante viene determinata in base al sito di rete associato alla subnet di rete a cui è connesso il chiamante.</span><span class="sxs-lookup"><span data-stu-id="52575-108">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="52575-109">La configurazione di Location-Based routing richiede innanzitutto la distribuzione di VoIP aziendale e quindi la configurazione di aree di rete, siti e subnet.</span><span class="sxs-lookup"><span data-stu-id="52575-109">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="52575-110">In questo modo viene impostata la base per l'abilitazione del routing Location-Based.</span><span class="sxs-lookup"><span data-stu-id="52575-110">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="52575-111">Prima di distribuire Location-Based routing, è necessario prima distribuire VoIP aziendale e configurare le aree di rete, i siti e associare le subnet di rete ai siti di rete.</span><span class="sxs-lookup"><span data-stu-id="52575-111">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="52575-112">Una volta completato, è possibile configurare il routing Location-Based.</span><span class="sxs-lookup"><span data-stu-id="52575-112">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="52575-113">Per istruzioni su come configurare aree di rete, siti e subnet, vedere [Deploying Advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="52575-113">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="52575-114">In questa sezione viene illustrata la configurazione del routing Location-Based utilizzando l'esempio seguente come illustrato.</span><span class="sxs-lookup"><span data-stu-id="52575-114">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="52575-115">![Esempio di routing basato sulla posizione di VoIP aziendale](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Esempio di routing basato sulla posizione di VoIP aziendale")</span><span class="sxs-lookup"><span data-stu-id="52575-115">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="52575-116">La tabella seguente rappresenta gli utenti definiti in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="52575-116">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52575-117">Tipo di endpoint</span><span class="sxs-lookup"><span data-stu-id="52575-117">Endpoint type</span></span></th>
<th><span data-ttu-id="52575-118">Posizione</span><span class="sxs-lookup"><span data-stu-id="52575-118">Location</span></span></th>
<th><span data-ttu-id="52575-119">Utenti</span><span class="sxs-lookup"><span data-stu-id="52575-119">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52575-120">Lync</span><span class="sxs-lookup"><span data-stu-id="52575-120">Lync</span></span></p></td>
<td><p><span data-ttu-id="52575-121">Ufficio corporativo di Delhi</span><span class="sxs-lookup"><span data-stu-id="52575-121">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="52575-122">CANC-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="52575-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52575-123">Lync</span><span class="sxs-lookup"><span data-stu-id="52575-123">Lync</span></span></p></td>
<td><p><span data-ttu-id="52575-124">Ufficio corporativo di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="52575-124">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="52575-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="52575-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52575-126">Lync</span><span class="sxs-lookup"><span data-stu-id="52575-126">Lync</span></span></p></td>
<td><p><span data-ttu-id="52575-127">Unknown (vale a dire Hotel)</span><span class="sxs-lookup"><span data-stu-id="52575-127">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="52575-128">UNK-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="52575-128">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52575-129">PBX</span><span class="sxs-lookup"><span data-stu-id="52575-129">PBX</span></span></p></td>
<td><p><span data-ttu-id="52575-130">Ufficio corporativo di Delhi</span><span class="sxs-lookup"><span data-stu-id="52575-130">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="52575-131">DEL-PBX-1, DEL-PBX-2</span><span class="sxs-lookup"><span data-stu-id="52575-131">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52575-132">PBX</span><span class="sxs-lookup"><span data-stu-id="52575-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="52575-133">Ufficio corporativo di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="52575-133">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="52575-134">HYD-PBX-1, HYD-PBX-2</span><span class="sxs-lookup"><span data-stu-id="52575-134">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52575-135">PSTN</span><span class="sxs-lookup"><span data-stu-id="52575-135">PSTN</span></span></p></td>
<td><p><span data-ttu-id="52575-136">Unknown</span><span class="sxs-lookup"><span data-stu-id="52575-136">Unknown</span></span></p></td>
<td><p><span data-ttu-id="52575-137">PSTN-1, PSTN-2, PSTN-3</span><span class="sxs-lookup"><span data-stu-id="52575-137">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="52575-138">La tabella seguente rappresenta i sistemi illustrati in questo esempio di ambiente.</span><span class="sxs-lookup"><span data-stu-id="52575-138">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="52575-139">Sistema</span><span class="sxs-lookup"><span data-stu-id="52575-139">System</span></span></th>
<th><span data-ttu-id="52575-140">Posizione</span><span class="sxs-lookup"><span data-stu-id="52575-140">Location</span></span></th>
<th><span data-ttu-id="52575-141">Nome</span><span class="sxs-lookup"><span data-stu-id="52575-141">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="52575-142">Lync Server 2013 CU1 pool</span><span class="sxs-lookup"><span data-stu-id="52575-142">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="52575-143">qualsiasi</span><span class="sxs-lookup"><span data-stu-id="52575-143">any</span></span></p></td>
<td><p><span data-ttu-id="52575-144">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="52575-144">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52575-145">Lync Server 2013 CU1, Mediation Server</span><span class="sxs-lookup"><span data-stu-id="52575-145">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="52575-146">qualsiasi</span><span class="sxs-lookup"><span data-stu-id="52575-146">any</span></span></p></td>
<td><p><span data-ttu-id="52575-147">MS-PL1</span><span class="sxs-lookup"><span data-stu-id="52575-147">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52575-148">Gateway PSTN 1</span><span class="sxs-lookup"><span data-stu-id="52575-148">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="52575-149">Delhi</span><span class="sxs-lookup"><span data-stu-id="52575-149">Delhi</span></span></p></td>
<td><p><span data-ttu-id="52575-150">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="52575-150">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52575-151">Gateway PSTN 2</span><span class="sxs-lookup"><span data-stu-id="52575-151">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="52575-152">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="52575-152">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="52575-153">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="52575-153">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="52575-154">PBX 1</span><span class="sxs-lookup"><span data-stu-id="52575-154">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="52575-155">Delhi</span><span class="sxs-lookup"><span data-stu-id="52575-155">Delhi</span></span></p></td>
<td><p><span data-ttu-id="52575-156">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="52575-156">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="52575-157">PBX 2</span><span class="sxs-lookup"><span data-stu-id="52575-157">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="52575-158">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="52575-158">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="52575-159">ROSSO-PBX</span><span class="sxs-lookup"><span data-stu-id="52575-159">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="52575-160">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="52575-160">In This Section</span></span>

  - [<span data-ttu-id="52575-161">Configurazione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52575-161">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="52575-162">Distribuzione di aree di rete, siti e subnet in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52575-162">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="52575-163">Abilitazione del routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52575-163">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="52575-164">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="52575-164">See Also</span></span>


[<span data-ttu-id="52575-165">Distribuzione di funzionalità di VoIP aziendale avanzate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="52575-165">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

