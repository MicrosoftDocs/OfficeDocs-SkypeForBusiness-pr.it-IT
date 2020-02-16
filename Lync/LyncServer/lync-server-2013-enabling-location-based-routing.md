---
title: 'Lync Server 2013: attivazione del routing in base alla posizione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b254e7e05a0ac2117b12a0004435898069059f53
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="f61ce-102">Abilitazione del routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f61ce-102">Enabling Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f61ce-103">_**Ultimo argomento modificato:** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="f61ce-103">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="f61ce-104">Dopo la distribuzione di VoIP aziendale e la definizione di aree di rete, siti e subnet, è possibile abilitare il routing in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="f61ce-104">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="f61ce-105">Il routing in base alla posizione deve essere abilitato per gli elementi VoIP Enterprise seguenti:</span><span class="sxs-lookup"><span data-stu-id="f61ce-105">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="f61ce-106">Siti di rete</span><span class="sxs-lookup"><span data-stu-id="f61ce-106">Network sites</span></span>

  - <span data-ttu-id="f61ce-107">Configurazioni trunk</span><span class="sxs-lookup"><span data-stu-id="f61ce-107">Trunk configurations</span></span>

  - <span data-ttu-id="f61ce-108">Criteri vocali</span><span class="sxs-lookup"><span data-stu-id="f61ce-108">Voice policies</span></span>

  - <span data-ttu-id="f61ce-109">Configurazione del routing</span><span class="sxs-lookup"><span data-stu-id="f61ce-109">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="f61ce-110">Abilitare il routing basato sul percorso ai siti di rete</span><span class="sxs-lookup"><span data-stu-id="f61ce-110">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="f61ce-111">Dopo aver distribuito VoIP aziendale e configurato i siti di rete, è possibile configurare il routing in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="f61ce-111">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="f61ce-112">Per prima cosa, è necessario creare un criterio di routing vocale per associare il sito di rete agli utilizzi PSTN corretti.</span><span class="sxs-lookup"><span data-stu-id="f61ce-112">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="f61ce-113">Quando si assegnano gli utilizzi PSTN a un criterio di routing vocale, è necessario utilizzare solo gli utilizzi PSTN associati a route vocali che utilizzano un gateway PSTN locale per il sito o un gateway PSTN che si trova in un'area in cui non sono necessarie restrizioni di routing basate sulla posizione. Utilizzare il comando di Windows PowerShell di Lync Server, New-CsVoiceRoutingPolicy o il pannello di controllo di Lync Server per creare i criteri di routing vocale.</span><span class="sxs-lookup"><span data-stu-id="f61ce-113">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="f61ce-114">Per ulteriori informazioni, vedere [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span><span class="sxs-lookup"><span data-stu-id="f61ce-114">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="f61ce-115">Per questo esempio, nella tabella seguente e nei comandi di Windows PowerShell vengono illustrati due criteri di routing vocale e gli utilizzi PSTN associati definiti in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="f61ce-115">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="f61ce-116">Solo le impostazioni specifiche del routing in base alla posizione sono incluse nella tabella a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="f61ce-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="f61ce-117">Criterio di routing vocale 1</span><span class="sxs-lookup"><span data-stu-id="f61ce-117">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="f61ce-118">Criterio di routing vocale 2</span><span class="sxs-lookup"><span data-stu-id="f61ce-118">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f61ce-119">ID criterio vocale</span><span class="sxs-lookup"><span data-stu-id="f61ce-119">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="f61ce-120">Politica di routing vocale Delhi</span><span class="sxs-lookup"><span data-stu-id="f61ce-120">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="f61ce-121">Criteri di routing vocale Hyderabad</span><span class="sxs-lookup"><span data-stu-id="f61ce-121">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f61ce-122">Utilizzi PSTN</span><span class="sxs-lookup"><span data-stu-id="f61ce-122">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="f61ce-123">Utilizzo di Delhi, utilizzo del sistema PBX del PBX, utilizzo del sistema idraulico HYD</span><span class="sxs-lookup"><span data-stu-id="f61ce-123">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="f61ce-124">Utilizzo di Hyderabad, utilizzo del PBX HYD, utilizzo del sistema PBX del</span><span class="sxs-lookup"><span data-stu-id="f61ce-124">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="f61ce-125">Successivamente, configurare il routing in base alla posizione per i siti di rete applicabili e associargli i criteri di routing vocale.</span><span class="sxs-lookup"><span data-stu-id="f61ce-125">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="f61ce-126">Utilizzare il comando di Windows PowerShell di Lync Server, New-CsNetworkSite, per abilitare il routing in base alla posizione e associare i criteri di routing vocale ai siti di rete che devono applicare restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="f61ce-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="f61ce-127">In questo esempio, nella tabella seguente viene illustrato il routing in base alla posizione per due siti di rete diversi, Delhi e Hyderabad, definiti in questo scenario utilizzando Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f61ce-127">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="f61ce-128">Solo le impostazioni specifiche del routing in base alla posizione sono incluse nella tabella a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="f61ce-128">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="f61ce-129">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f61ce-129">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="f61ce-130">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f61ce-130">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f61ce-131">Nome sito</span><span class="sxs-lookup"><span data-stu-id="f61ce-131">Site Name</span></span></p></td>
<td><p><span data-ttu-id="f61ce-132">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f61ce-132">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="f61ce-133">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f61ce-133">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f61ce-134">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="f61ce-134">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="f61ce-135">True</span><span class="sxs-lookup"><span data-stu-id="f61ce-135">True</span></span></p></td>
<td><p><span data-ttu-id="f61ce-136">True</span><span class="sxs-lookup"><span data-stu-id="f61ce-136">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f61ce-137">Criterio di routing vocale</span><span class="sxs-lookup"><span data-stu-id="f61ce-137">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="f61ce-138">Politica di routing vocale Delhi</span><span class="sxs-lookup"><span data-stu-id="f61ce-138">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="f61ce-139">Criteri di routing vocale Hyderabad</span><span class="sxs-lookup"><span data-stu-id="f61ce-139">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f61ce-140">Subnet</span><span class="sxs-lookup"><span data-stu-id="f61ce-140">Subnets</span></span></p></td>
<td><p><span data-ttu-id="f61ce-141">Subnet 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f61ce-141">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="f61ce-142">Subnet 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f61ce-142">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="f61ce-143">Abilitare il routing basato sul percorso ai trunk</span><span class="sxs-lookup"><span data-stu-id="f61ce-143">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="f61ce-144">Prima di poter abilitare una configurazione trunk per il routing in base alla posizione, è necessario creare una configurazione trunk per ogni trunk o ogni sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f61ce-144">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="f61ce-145">Utilizzare il comando di Windows PowerShell di Lync Server, New-CsTrunkConfiguration, per creare una configurazione trunk.</span><span class="sxs-lookup"><span data-stu-id="f61ce-145">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="f61ce-146">Se più trunk sono associati a un determinato sistema, ad esempio il gateway o il PBX, è necessario modificare ogni configurazione del trunk per abilitare le restrizioni di routing basate sul percorso.</span><span class="sxs-lookup"><span data-stu-id="f61ce-146">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="f61ce-147">Per ulteriori informazioni, vedere [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="f61ce-147">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="f61ce-148">In questo esempio, i comandi di Windows PowerShell seguenti illustrano la creazione di una configurazione trunk per ogni trunk nella distribuzione definita in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="f61ce-148">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="f61ce-149">Una volta configurata una configurazione trunk per trunk, è possibile utilizzare il comando di Windows PowerShell di Lync Server, Set-CsTrunkConfiguration, per abilitare il routing basato sul percorso ai trunk che devono applicare restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="f61ce-149">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="f61ce-150">Abilitare il routing in base alla posizione ai trunk che instradano le chiamate ai gateway PSTN che instradano le chiamate alla rete PSTN e associano il sito in cui si trova il gateway.</span><span class="sxs-lookup"><span data-stu-id="f61ce-150">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="f61ce-151">Per ulteriori informazioni, vedere [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="f61ce-151">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="f61ce-152">In questo esempio, il routing in base alla posizione è abilitato per ogni trunk associato ai gateway PSTN di Delhi e Hyderabad:</span><span class="sxs-lookup"><span data-stu-id="f61ce-152">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="f61ce-153">Non abilitare il routing basato sulla posizione per i trunk che non instradano le chiamate alla rete PSTN; Tuttavia, è necessario associare il trunk al sito di rete in cui si trova il sistema come le restrizioni di routing basate sulla posizione devono essere applicate per le chiamate PSTN raggiungendo gli endpoint connessi tramite questo trunk.</span><span class="sxs-lookup"><span data-stu-id="f61ce-153">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="f61ce-154">Per questo esempio, il routing in base alla posizione non è abilitato per ogni trunk associato a sistemi PBX a Delhi e Hyderabad:</span><span class="sxs-lookup"><span data-stu-id="f61ce-154">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="f61ce-155">Gli endpoint connessi a sistemi che non instradano le chiamate alla rete PSTN (ovvero a un sistema PBX) avranno restrizioni simili a quelle degli endpoint di Lync degli utenti abilitati per il routing in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="f61ce-155">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="f61ce-156">Questo significa che gli utenti potranno effettuare e ricevere chiamate da e verso l'utente di Lync indipendentemente dalla posizione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f61ce-156">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="f61ce-157">Sarà inoltre possibile effettuare chiamate di ricezione verso e da altri sistemi che non instradano le chiamate alla rete PSTN (ovvero un endpoint connesso a un altro PBX) indipendentemente dal sito di rete a cui è associato il sistema.</span><span class="sxs-lookup"><span data-stu-id="f61ce-157">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="f61ce-158">Tutte le chiamate in ingresso, le chiamate in uscita, i trasferimenti di chiamata e l'inoltro di chiamata che coinvolgono endpoint PSTN saranno soggetti alle imposte del routing basate sul percorso.</span><span class="sxs-lookup"><span data-stu-id="f61ce-158">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="f61ce-159">Tali chiamate devono utilizzare solo gateway PSTN definiti come locali per tali sistemi.</span><span class="sxs-lookup"><span data-stu-id="f61ce-159">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="f61ce-160">Nella tabella seguente viene illustrata la configurazione trunk di quattro trunk in due siti di rete diversi: due connessi a gateway PSTN e due connessi a sistemi PBX.</span><span class="sxs-lookup"><span data-stu-id="f61ce-160">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f61ce-161">Name</span><span class="sxs-lookup"><span data-stu-id="f61ce-161">Name</span></span></th>
<th><span data-ttu-id="f61ce-162">EnableLocationRestriction</span><span class="sxs-lookup"><span data-stu-id="f61ce-162">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="f61ce-163">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="f61ce-163">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f61ce-164">PstnGateway: trunk 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="f61ce-164">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="f61ce-165">True</span><span class="sxs-lookup"><span data-stu-id="f61ce-165">True</span></span></p></td>
<td><p><span data-ttu-id="f61ce-166">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f61ce-166">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f61ce-167">PstnGateway: tronco 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="f61ce-167">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="f61ce-168">True</span><span class="sxs-lookup"><span data-stu-id="f61ce-168">True</span></span></p></td>
<td><p><span data-ttu-id="f61ce-169">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f61ce-169">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f61ce-170">PstnGateway: Trunk 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="f61ce-170">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="f61ce-171">False</span><span class="sxs-lookup"><span data-stu-id="f61ce-171">False</span></span></p></td>
<td><p><span data-ttu-id="f61ce-172">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="f61ce-172">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f61ce-173">PstnGateway: trunk 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="f61ce-173">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="f61ce-174">False</span><span class="sxs-lookup"><span data-stu-id="f61ce-174">False</span></span></p></td>
<td><p><span data-ttu-id="f61ce-175">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="f61ce-175">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="f61ce-176">Abilitare il routing basato sul percorso ai criteri vocali</span><span class="sxs-lookup"><span data-stu-id="f61ce-176">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="f61ce-177">Per applicare il routing basato sul percorso a utenti specifici, configurare i criteri vocali di tali utenti per impedire il bypass a pedaggio PSTN.</span><span class="sxs-lookup"><span data-stu-id="f61ce-177">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="f61ce-178">Utilizzare il comando di Windows PowerShell di Lync Server, New-CsVoicePolicy, per creare un nuovo criterio vocale o Set-CsVoicePolicy, se si utilizza un criterio esistente, per abilitare il routing basato sulla posizione impedendo il bypass a pedaggio PSTN.</span><span class="sxs-lookup"><span data-stu-id="f61ce-178">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="f61ce-179">Per ulteriori informazioni, vedere [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="f61ce-179">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="f61ce-180">Per questo esempio, nella tabella seguente e nei comandi di Windows PowerShell viene illustrato come abilitare la prevenzione del bypass a pedaggio PSTN nei criteri vocali Delhi e Hyderabad definiti in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="f61ce-180">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="f61ce-181">Solo le impostazioni specifiche del routing in base alla posizione sono incluse nella tabella a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="f61ce-181">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="f61ce-182">Criterio vocale 1</span><span class="sxs-lookup"><span data-stu-id="f61ce-182">Voice policy 1</span></span></th>
<th><span data-ttu-id="f61ce-183">Criterio vocale 2</span><span class="sxs-lookup"><span data-stu-id="f61ce-183">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f61ce-184">ID criterio vocale</span><span class="sxs-lookup"><span data-stu-id="f61ce-184">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="f61ce-185">Criteri vocali Delhi</span><span class="sxs-lookup"><span data-stu-id="f61ce-185">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="f61ce-186">Criteri vocali di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="f61ce-186">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f61ce-187">Utilizzi PSTN</span><span class="sxs-lookup"><span data-stu-id="f61ce-187">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="f61ce-188">Utilizzo di Delhi, utilizzo del sistema PBX del PBX, utilizzo del sistema idraulico HYD</span><span class="sxs-lookup"><span data-stu-id="f61ce-188">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="f61ce-189">Utilizzo di Hyderabad, utilizzo del PBX HYD, utilizzo del sistema PBX del</span><span class="sxs-lookup"><span data-stu-id="f61ce-189">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f61ce-190">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="f61ce-190">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="f61ce-191">True</span><span class="sxs-lookup"><span data-stu-id="f61ce-191">True</span></span></p></td>
<td><p><span data-ttu-id="f61ce-192">True</span><span class="sxs-lookup"><span data-stu-id="f61ce-192">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="f61ce-193">Abilitare il routing in base alla posizione nella configurazione del routing</span><span class="sxs-lookup"><span data-stu-id="f61ce-193">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="f61ce-194">Infine, abilitare globalmente il routing basato sulla posizione alla configurazione di routing.</span><span class="sxs-lookup"><span data-stu-id="f61ce-194">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="f61ce-195">Utilizzare il comando di Windows PowerShell di Lync Server, New-CsRoutingConfiguration, per abilitare il routing in base alla posizione.</span><span class="sxs-lookup"><span data-stu-id="f61ce-195">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="f61ce-196">Per ulteriori informazioni, vedere [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span><span class="sxs-lookup"><span data-stu-id="f61ce-196">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f61ce-197">mentre il routing in base alla posizione deve essere abilitato tramite una configurazione globale, l'insieme di regole da applicare verrà applicato solo per i siti, gli utenti e i trunk per i quali è stata configurata come specificato nella presente documentazione.</span><span class="sxs-lookup"><span data-stu-id="f61ce-197">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="f61ce-198">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f61ce-198">See Also</span></span>


[<span data-ttu-id="f61ce-199">Configurazione del routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f61ce-199">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

