---
title: 'Lync Server 2013: configurazione del routing Location-Based'
description: 'Lync Server 2013: configurazione del routing Location-Based.'
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
ms.openlocfilehash: 080c2a3a82a8714fc35ce882b0c6cb1630552f27
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570882"
---
# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="fdc0f-103">Configurazione del routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fdc0f-103">Configuring Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fdc0f-104">_**Ultimo argomento modificato:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="fdc0f-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="fdc0f-105">Lync Server 2013 CU1, Location-Based routing è una funzionalità di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="fdc0f-105">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="fdc0f-106">Location-Based routing è una funzionalità di gestione delle chiamate che controlla il modo in cui vengono instradate tramite Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="fdc0f-106">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="fdc0f-107">Impone restrizioni sul fatto che le chiamate possano essere instradate a destinazioni PBX o PSTN in base alla posizione del chiamante di Lync.</span><span class="sxs-lookup"><span data-stu-id="fdc0f-107">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="fdc0f-108">Location-Based routing applica le regole di autorizzazione di chiamata alle chiamate PSTN in base al percorso di rete del chiamante.</span><span class="sxs-lookup"><span data-stu-id="fdc0f-108">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="fdc0f-109">La posizione del chiamante viene determinata in base al sito di rete associato alla subnet di rete a cui è connesso il chiamante.</span><span class="sxs-lookup"><span data-stu-id="fdc0f-109">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="fdc0f-110">La configurazione di Location-Based routing richiede innanzitutto la distribuzione di VoIP aziendale e quindi la configurazione di aree di rete, siti e subnet.</span><span class="sxs-lookup"><span data-stu-id="fdc0f-110">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="fdc0f-111">In questo modo viene impostata la base per l'abilitazione del routing Location-Based.</span><span class="sxs-lookup"><span data-stu-id="fdc0f-111">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="fdc0f-112">Prima di distribuire Location-Based routing, è necessario prima distribuire VoIP aziendale e configurare le aree di rete, i siti e associare le subnet di rete ai siti di rete.</span><span class="sxs-lookup"><span data-stu-id="fdc0f-112">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="fdc0f-113">Una volta completato, è possibile configurare il routing Location-Based.</span><span class="sxs-lookup"><span data-stu-id="fdc0f-113">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="fdc0f-114">Per istruzioni su come configurare aree di rete, siti e subnet, vedere [Deploying Advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="fdc0f-114">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="fdc0f-115">In questa sezione viene illustrata la configurazione del routing Location-Based utilizzando l'esempio seguente come illustrato.</span><span class="sxs-lookup"><span data-stu-id="fdc0f-115">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="fdc0f-116">![Esempio di routing basato sulla posizione di VoIP aziendale](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Esempio di routing basato sulla posizione di VoIP aziendale")</span><span class="sxs-lookup"><span data-stu-id="fdc0f-116">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="fdc0f-117">La tabella seguente rappresenta gli utenti definiti in questo esempio.</span><span class="sxs-lookup"><span data-stu-id="fdc0f-117">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fdc0f-118">Tipo di endpoint</span><span class="sxs-lookup"><span data-stu-id="fdc0f-118">Endpoint type</span></span></th>
<th><span data-ttu-id="fdc0f-119">Posizione</span><span class="sxs-lookup"><span data-stu-id="fdc0f-119">Location</span></span></th>
<th><span data-ttu-id="fdc0f-120">Utenti</span><span class="sxs-lookup"><span data-stu-id="fdc0f-120">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdc0f-121">Lync</span><span class="sxs-lookup"><span data-stu-id="fdc0f-121">Lync</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-122">Ufficio corporativo di Delhi</span><span class="sxs-lookup"><span data-stu-id="fdc0f-122">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-123">CANC-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="fdc0f-123">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdc0f-124">Lync</span><span class="sxs-lookup"><span data-stu-id="fdc0f-124">Lync</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-125">Ufficio corporativo di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="fdc0f-125">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-126">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="fdc0f-126">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdc0f-127">Lync</span><span class="sxs-lookup"><span data-stu-id="fdc0f-127">Lync</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-128">Unknown (vale a dire Hotel)</span><span class="sxs-lookup"><span data-stu-id="fdc0f-128">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-129">UNK-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="fdc0f-129">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdc0f-130">PBX</span><span class="sxs-lookup"><span data-stu-id="fdc0f-130">PBX</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-131">Ufficio corporativo di Delhi</span><span class="sxs-lookup"><span data-stu-id="fdc0f-131">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-132">DEL-PBX-1, DEL-PBX-2</span><span class="sxs-lookup"><span data-stu-id="fdc0f-132">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdc0f-133">PBX</span><span class="sxs-lookup"><span data-stu-id="fdc0f-133">PBX</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-134">Ufficio corporativo di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="fdc0f-134">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-135">HYD-PBX-1, HYD-PBX-2</span><span class="sxs-lookup"><span data-stu-id="fdc0f-135">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdc0f-136">PSTN</span><span class="sxs-lookup"><span data-stu-id="fdc0f-136">PSTN</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-137">Unknown</span><span class="sxs-lookup"><span data-stu-id="fdc0f-137">Unknown</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-138">PSTN-1, PSTN-2, PSTN-3</span><span class="sxs-lookup"><span data-stu-id="fdc0f-138">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="fdc0f-139">La tabella seguente rappresenta i sistemi illustrati in questo esempio di ambiente.</span><span class="sxs-lookup"><span data-stu-id="fdc0f-139">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="fdc0f-140">Sistema</span><span class="sxs-lookup"><span data-stu-id="fdc0f-140">System</span></span></th>
<th><span data-ttu-id="fdc0f-141">Posizione</span><span class="sxs-lookup"><span data-stu-id="fdc0f-141">Location</span></span></th>
<th><span data-ttu-id="fdc0f-142">Nome</span><span class="sxs-lookup"><span data-stu-id="fdc0f-142">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fdc0f-143">Lync Server 2013 CU1 pool</span><span class="sxs-lookup"><span data-stu-id="fdc0f-143">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-144">qualsiasi</span><span class="sxs-lookup"><span data-stu-id="fdc0f-144">any</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-145">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="fdc0f-145">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdc0f-146">Lync Server 2013 CU1, Mediation Server</span><span class="sxs-lookup"><span data-stu-id="fdc0f-146">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-147">qualsiasi</span><span class="sxs-lookup"><span data-stu-id="fdc0f-147">any</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-148">MS-PL1</span><span class="sxs-lookup"><span data-stu-id="fdc0f-148">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdc0f-149">Gateway PSTN 1</span><span class="sxs-lookup"><span data-stu-id="fdc0f-149">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-150">Delhi</span><span class="sxs-lookup"><span data-stu-id="fdc0f-150">Delhi</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-151">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="fdc0f-151">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdc0f-152">Gateway PSTN 2</span><span class="sxs-lookup"><span data-stu-id="fdc0f-152">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-153">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="fdc0f-153">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-154">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="fdc0f-154">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fdc0f-155">PBX 1</span><span class="sxs-lookup"><span data-stu-id="fdc0f-155">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-156">Delhi</span><span class="sxs-lookup"><span data-stu-id="fdc0f-156">Delhi</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-157">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="fdc0f-157">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fdc0f-158">PBX 2</span><span class="sxs-lookup"><span data-stu-id="fdc0f-158">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-159">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="fdc0f-159">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="fdc0f-160">ROSSO-PBX</span><span class="sxs-lookup"><span data-stu-id="fdc0f-160">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="fdc0f-161">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="fdc0f-161">In This Section</span></span>

  - [<span data-ttu-id="fdc0f-162">Configurazione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fdc0f-162">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="fdc0f-163">Distribuzione di aree di rete, siti e subnet in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fdc0f-163">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="fdc0f-164">Abilitazione del routing Location-Based in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fdc0f-164">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="fdc0f-165">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fdc0f-165">See Also</span></span>


[<span data-ttu-id="fdc0f-166">Distribuzione di funzionalità di VoIP aziendale avanzate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fdc0f-166">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

