---
title: 'Lync Server 2013: abilitazione del routing basato sulla posizione'
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
ms.openlocfilehash: e21e1a285fa5b2129d4d0ed0b5d75e8dcee42f2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735806"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="77831-102">Abilitazione del routing basato sulla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77831-102">Enabling Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77831-103">_**Argomento Ultima modifica:** 2013-04-26_</span><span class="sxs-lookup"><span data-stu-id="77831-103">_**Topic Last Modified:** 2013-04-26_</span></span>

<span data-ttu-id="77831-104">Quando Enterprise Voice viene distribuita e vengono definite aree di rete, siti e subnet, è possibile abilitare il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="77831-104">Once Enterprise Voice is deployed and network regions, sites and subnets are defined, you can enable Location-Based Routing.</span></span> <span data-ttu-id="77831-105">Il routing basato sulla posizione deve essere abilitato per gli elementi Voice Enterprise seguenti:</span><span class="sxs-lookup"><span data-stu-id="77831-105">Location-Based Routing must be enabled for the following Enterprise Voice elements:</span></span>

  - <span data-ttu-id="77831-106">Siti di rete</span><span class="sxs-lookup"><span data-stu-id="77831-106">Network sites</span></span>

  - <span data-ttu-id="77831-107">Configurazioni trunk</span><span class="sxs-lookup"><span data-stu-id="77831-107">Trunk configurations</span></span>

  - <span data-ttu-id="77831-108">Criteri vocali</span><span class="sxs-lookup"><span data-stu-id="77831-108">Voice policies</span></span>

  - <span data-ttu-id="77831-109">Configurazione del routing</span><span class="sxs-lookup"><span data-stu-id="77831-109">Routing configuration</span></span>

<div>

## <a name="enable-location-based-routing-to-network-sites"></a><span data-ttu-id="77831-110">Abilitare il routing basato sulla posizione nei siti di rete</span><span class="sxs-lookup"><span data-stu-id="77831-110">Enable Location-Based Routing to Network Sites</span></span>

<span data-ttu-id="77831-111">Dopo aver distribuito Enterprise Voice e i siti di rete configurati, si è pronti per configurare il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="77831-111">After you have deployed Enterprise Voice, and configured network sites, you are ready to configure Location-Based Routing.</span></span> <span data-ttu-id="77831-112">Prima di tutto, crei un criterio di routing vocale per associare il sito di rete agli usi appropriati PSTN.</span><span class="sxs-lookup"><span data-stu-id="77831-112">First, you create a voice routing policy to associate the network site with the appropriate PSTN usages.</span></span> <span data-ttu-id="77831-113">Quando si assegnano gli utilizzi PSTN a un criterio di routing vocale, assicurarsi di usare solo gli usi PSTN associati alle route vocali che usano un gateway PSTN locale per il sito o un gateway PSTN che si trova in un'area geografica in cui non sono necessarie restrizioni di routing basate sulla posizione. Usare il comando Lync Server di Windows PowerShell, New-CsVoiceRoutingPolicy o il pannello di controllo di Lync Server per creare criteri di routing vocale.</span><span class="sxs-lookup"><span data-stu-id="77831-113">When assigning PSTN usages to a voice routing policy, make sure to only use PSTN usages that are associated to voice routes that use a PSTN gateway local to the site or a PSTN gateway that is located in a region where Location-Based Routing restrictions are not needed.Use the Lync Server Windows PowerShell command, New-CsVoiceRoutingPolicy, or Lync Server Control Panel to create voice routing policies.</span></span>

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

<span data-ttu-id="77831-114">Per altre informazioni, vedere [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span><span class="sxs-lookup"><span data-stu-id="77831-114">For more information, see [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).</span></span>

<span data-ttu-id="77831-115">Per questo esempio, la tabella seguente e i comandi di Windows PowerShell illustrano due criteri di routing vocale e gli usi PSTN associati definiti in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="77831-115">For this example, the following table and Windows PowerShell commands illustrate two voice routing policies and their associated PSTN usages defined in this scenario.</span></span> <span data-ttu-id="77831-116">Nella tabella sono incluse solo le impostazioni specifiche del routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="77831-116">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="77831-117">Criteri di routing vocale 1</span><span class="sxs-lookup"><span data-stu-id="77831-117">Voice routing policy 1</span></span></th>
<th><span data-ttu-id="77831-118">Criteri di routing vocale 2</span><span class="sxs-lookup"><span data-stu-id="77831-118">Voice routing policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77831-119">ID criterio vocale</span><span class="sxs-lookup"><span data-stu-id="77831-119">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="77831-120">Politica di routing vocale Delhi</span><span class="sxs-lookup"><span data-stu-id="77831-120">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="77831-121">Criteri di routing vocale di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="77831-121">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77831-122">Usi PSTN</span><span class="sxs-lookup"><span data-stu-id="77831-122">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="77831-123">Uso di Delhi, uso del PBX, uso di HYD PBX</span><span class="sxs-lookup"><span data-stu-id="77831-123">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="77831-124">Uso di Hyderabad, uso del PBX HYD, uso del PBX</span><span class="sxs-lookup"><span data-stu-id="77831-124">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="77831-125">Configurare quindi il routing basato sulla posizione per i siti di rete applicabili e associarvi i criteri di routing vocale.</span><span class="sxs-lookup"><span data-stu-id="77831-125">Next, configure Location-Based Routing for the applicable network sites and associate your voice routing policies to them.</span></span> <span data-ttu-id="77831-126">Usare il comando di Windows PowerShell di Lync Server, New-CsNetworkSite, per abilitare il routing basato sulla posizione e associare i criteri di routing vocale ai siti di rete che devono applicare restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="77831-126">Use the Lync Server Windows PowerShell command, New-CsNetworkSite, to enable Location-Based Routing and associate voice routing policies to your network sites that must enforce routing restrictions.</span></span>

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

<span data-ttu-id="77831-127">In questo esempio la tabella seguente illustra il routing basato sulla posizione per due diversi siti di rete, Delhi e Hyderabad, definiti in questo scenario tramite Lync Server Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="77831-127">In this example, the following table illustrates Location-Based Routing for two different network sites, Delhi and Hyderabad, defined in this scenario using the Lync Server Windows PowerShell.</span></span> <span data-ttu-id="77831-128">Nella tabella sono incluse solo le impostazioni specifiche del routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="77831-128">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="77831-129">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="77831-129">Site 1 (Delhi)</span></span></th>
<th><span data-ttu-id="77831-130">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="77831-130">Site 2 (Hyderabad)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77831-131">Nome sito</span><span class="sxs-lookup"><span data-stu-id="77831-131">Site Name</span></span></p></td>
<td><p><span data-ttu-id="77831-132">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="77831-132">Site 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="77831-133">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="77831-133">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77831-134">EnableLocationBasedRouting</span><span class="sxs-lookup"><span data-stu-id="77831-134">EnableLocationBasedRouting</span></span></p></td>
<td><p><span data-ttu-id="77831-135">True</span><span class="sxs-lookup"><span data-stu-id="77831-135">True</span></span></p></td>
<td><p><span data-ttu-id="77831-136">True</span><span class="sxs-lookup"><span data-stu-id="77831-136">True</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77831-137">Criteri di routing vocale</span><span class="sxs-lookup"><span data-stu-id="77831-137">Voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="77831-138">Politica di routing vocale Delhi</span><span class="sxs-lookup"><span data-stu-id="77831-138">Delhi voice routing policy</span></span></p></td>
<td><p><span data-ttu-id="77831-139">Criteri di routing vocale di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="77831-139">Hyderabad voice routing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77831-140">Subnet</span><span class="sxs-lookup"><span data-stu-id="77831-140">Subnets</span></span></p></td>
<td><p><span data-ttu-id="77831-141">Subnet 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="77831-141">Subnet 1 (Delhi)</span></span></p></td>
<td><p><span data-ttu-id="77831-142">Subnet 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="77831-142">Subnet 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a><span data-ttu-id="77831-143">Abilitare il routing basato sulla posizione ai trunk</span><span class="sxs-lookup"><span data-stu-id="77831-143">Enable Location-Based Routing to Trunks</span></span>

<span data-ttu-id="77831-144">Prima di poter abilitare una configurazione trunk per il routing basato sulla posizione, è necessario creare una configurazione trunk per ogni trunk o ogni sito di rete.</span><span class="sxs-lookup"><span data-stu-id="77831-144">Before a trunk configuration can be enabled for Location-Based Routing, you need to create a trunk configuration for each trunk or each network site.</span></span> <span data-ttu-id="77831-145">Usare il comando di Windows PowerShell di Lync Server, New-CsTrunkConfiguration, per creare una configurazione trunk.</span><span class="sxs-lookup"><span data-stu-id="77831-145">Use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, to create a trunk configuration.</span></span> <span data-ttu-id="77831-146">Se più trunk sono associati a un sistema specifico (ad esempio gateway o PBX), è necessario modificare ogni configurazione trunk per abilitare le restrizioni di routing basate sul percorso.</span><span class="sxs-lookup"><span data-stu-id="77831-146">If multiple trunks are associated with a given system (i.e. Gateway or PBX), each trunk configuration must be modified to enable Location-Based Routing restrictions.</span></span>

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

<span data-ttu-id="77831-147">Per altre informazioni, vedere [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="77831-147">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="77831-148">Per questo esempio, i comandi di Windows PowerShell seguenti illustrano la creazione di una configurazione trunk per ogni trunk nella distribuzione definita in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="77831-148">For this example, the following Windows PowerShell commands illustrate creating one trunk configuration for each trunk in the deployment defined in this scenario.</span></span>

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

<span data-ttu-id="77831-149">Una volta configurata una configurazione trunk per ogni trunk, è possibile usare il comando Lync Server di Windows PowerShell, Set-CsTrunkConfiguration, per abilitare il routing basato sulla posizione nei trunk che deve applicare le restrizioni di routing.</span><span class="sxs-lookup"><span data-stu-id="77831-149">Once a trunk configuration is configured per trunk, you can use the Lync Server Windows PowerShell command, Set-CsTrunkConfiguration, to enable Location-Based Routing to your trunks that must enforce routing restrictions.</span></span> <span data-ttu-id="77831-150">Abilitare il routing basato sulla posizione per i trunk che instradano le chiamate ai gateway PSTN che instradano le chiamate alla rete PSTN e associano il sito in cui si trova il gateway.</span><span class="sxs-lookup"><span data-stu-id="77831-150">Enable Location-Based Routing to trunks that route calls to PSTN gateways that route calls to the PSTN, and associate the network site where the gateway is located.</span></span>

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

<span data-ttu-id="77831-151">Per altre informazioni, vedere [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span><span class="sxs-lookup"><span data-stu-id="77831-151">For more information, see [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).</span></span>

<span data-ttu-id="77831-152">In questo esempio, il routing basato sulla posizione è abilitato per ogni trunk associato ai gateway PSTN di Delhi e Hyderabad:</span><span class="sxs-lookup"><span data-stu-id="77831-152">In this example, Location-Based Routing is enabled for each trunk that is associated to PSTN gateways in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

<span data-ttu-id="77831-153">Non abilitare il routing basato sulla posizione per i trunk che non instradano le chiamate alla rete PSTN; Tuttavia, devi comunque associare il trunk al sito di rete in cui il sistema è situato come le restrizioni di routing basate sulla posizione devono essere applicate per le chiamate PSTN raggiungendo endpoint connessi tramite questo trunk.</span><span class="sxs-lookup"><span data-stu-id="77831-153">Do not enable Location-Based Routing for trunks that do not route calls to the PSTN; however, you must still associate the trunk to the network site where the system is located as Location-Based Routing restrictions need to be enforced for PSTN calls reaching endpoints connected via this trunk.</span></span> <span data-ttu-id="77831-154">Per questo esempio, il routing basato sulla posizione non è abilitato per ogni trunk associato ai sistemi PBX di Delhi e Hyderabad:</span><span class="sxs-lookup"><span data-stu-id="77831-154">For this example, Location-Based Routing is not enabled for each trunk that is associated to PBX systems in Delhi and Hyderabad:</span></span>

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
<span data-ttu-id="77831-155">Gli endpoint connessi a sistemi che non instradano le chiamate alla rete PSTN (ad esempio PBX) avranno restrizioni simili agli endpoint di Lync degli utenti abilitati per il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="77831-155">Endpoints that are connected to systems that do not route calls to the PSTN (i.e. a PBX) will have similar restrictions as Lync endpoints of users enabled for Location-Based Routing.</span></span> <span data-ttu-id="77831-156">Questo significa che questi utenti potranno effettuare e ricevere chiamate da e verso l'utente di Lync indipendentemente dalla posizione dell'utente.</span><span class="sxs-lookup"><span data-stu-id="77831-156">This means that these users will be able to place and receive calls to and from Lync user regardless of the user’s location.</span></span> <span data-ttu-id="77831-157">Potranno anche effettuare chiamate di ricezione da e verso altri sistemi che non instradano le chiamate alla rete PSTN (ad esempio un endpoint connesso a un PBX diverso), indipendentemente dal sito di rete a cui è associato il sistema.</span><span class="sxs-lookup"><span data-stu-id="77831-157">They will also be able to place an receive calls to and from other systems that do not route calls to the PSTN network (i.e. an endpoint connected to a different PBX) regardless of the network site to which the system is associated.</span></span> <span data-ttu-id="77831-158">Tutte le chiamate in ingresso, le chiamate in uscita, i trasferimenti delle chiamate e l'inoltro di chiamata che coinvolgono endpoint PSTN saranno soggetti a imposte di routing basate sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="77831-158">All inbound calls, outbound calls, call transfers and call forwarding involving PSTN endpoints will be subject to Location-Based Routing enforcements.</span></span> <span data-ttu-id="77831-159">Tali chiamate devono usare solo gateway PSTN definiti come locali per tali sistemi.</span><span class="sxs-lookup"><span data-stu-id="77831-159">Such calls must use only PSTN gateways that are defined as local to such systems.</span></span>

<span data-ttu-id="77831-160">La tabella seguente illustra la configurazione trunk di quattro trunk in due diversi siti di rete: due collegati a gateway PSTN e due collegati a sistemi PBX.</span><span class="sxs-lookup"><span data-stu-id="77831-160">The following table illustrates the trunk configuration of four trunks in two different network sites: two connected to PSTN gateways and two connected to PBX systems.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="77831-161">Nome</span><span class="sxs-lookup"><span data-stu-id="77831-161">Name</span></span></th>
<th><span data-ttu-id="77831-162">EnableLocationRestriction</span><span class="sxs-lookup"><span data-stu-id="77831-162">EnableLocationRestriction</span></span></th>
<th><span data-ttu-id="77831-163">NetworkSiteID</span><span class="sxs-lookup"><span data-stu-id="77831-163">NetworkSiteID</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77831-164">PstnGateway: tronco 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="77831-164">PstnGateway:Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="77831-165">True</span><span class="sxs-lookup"><span data-stu-id="77831-165">True</span></span></p></td>
<td><p><span data-ttu-id="77831-166">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="77831-166">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77831-167">PstnGateway: tronco 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="77831-167">PstnGateway:Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="77831-168">True</span><span class="sxs-lookup"><span data-stu-id="77831-168">True</span></span></p></td>
<td><p><span data-ttu-id="77831-169">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="77831-169">Site 2 (Hyderabad)</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77831-170">PstnGateway: Trunk 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="77831-170">PstnGateway:Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="77831-171">False</span><span class="sxs-lookup"><span data-stu-id="77831-171">False</span></span></p></td>
<td><p><span data-ttu-id="77831-172">Sito 1 (Delhi)</span><span class="sxs-lookup"><span data-stu-id="77831-172">Site 1 (Delhi)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77831-173">PstnGateway: trunk 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="77831-173">PstnGateway:Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="77831-174">False</span><span class="sxs-lookup"><span data-stu-id="77831-174">False</span></span></p></td>
<td><p><span data-ttu-id="77831-175">Sito 2 (Hyderabad)</span><span class="sxs-lookup"><span data-stu-id="77831-175">Site 2 (Hyderabad)</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a><span data-ttu-id="77831-176">Abilitare il routing basato sulla posizione ai criteri vocali</span><span class="sxs-lookup"><span data-stu-id="77831-176">Enable Location-Based Routing to Voice Policies</span></span>

<span data-ttu-id="77831-177">Per applicare il routing basato sulla posizione a utenti specifici, configurare i criteri vocali degli utenti per evitare l'esclusione del pedaggio PSTN.</span><span class="sxs-lookup"><span data-stu-id="77831-177">To enforce Location-Based Routing to specific users, configure those users’ voice policy to prevent PSTN toll bypass.</span></span> <span data-ttu-id="77831-178">Usare il comando di Windows PowerShell di Lync Server, New-CsVoicePolicy, per creare un nuovo criterio vocale o Set-CsVoicePolicy, se si usa un criterio esistente, per abilitare il routing basato sulla posizione impedendo l'esclusione del pedaggio PSTN.</span><span class="sxs-lookup"><span data-stu-id="77831-178">Use the Lync Server Windows PowerShell command, New-CsVoicePolicy, to create a new voice policy or Set-CsVoicePolicy, if using an existing policy, to enable Location-Based Routing by preventing PSTN toll bypass.</span></span>

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

<span data-ttu-id="77831-179">Per altre informazioni, vedere [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span><span class="sxs-lookup"><span data-stu-id="77831-179">For more information, see [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).</span></span>

<span data-ttu-id="77831-180">Per questo esempio, la tabella seguente e i comandi di Windows PowerShell illustrano l'abilitazione della prevenzione del bypass a pedaggio PSTN per i criteri vocali di Delhi e Hyderabad definiti in questo scenario.</span><span class="sxs-lookup"><span data-stu-id="77831-180">For this example, the following table and Windows PowerShell commands illustrate enabling the prevention of PSTN toll bypass to the Delhi and Hyderabad voice policies defined in this scenario.</span></span> <span data-ttu-id="77831-181">Nella tabella sono incluse solo le impostazioni specifiche del routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="77831-181">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

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
<th><span data-ttu-id="77831-182">Criterio vocale 1</span><span class="sxs-lookup"><span data-stu-id="77831-182">Voice policy 1</span></span></th>
<th><span data-ttu-id="77831-183">Criterio vocale 2</span><span class="sxs-lookup"><span data-stu-id="77831-183">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="77831-184">ID criterio vocale</span><span class="sxs-lookup"><span data-stu-id="77831-184">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="77831-185">Politica vocale di Delhi</span><span class="sxs-lookup"><span data-stu-id="77831-185">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="77831-186">Politica vocale di Hyderabad</span><span class="sxs-lookup"><span data-stu-id="77831-186">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="77831-187">Usi PSTN</span><span class="sxs-lookup"><span data-stu-id="77831-187">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="77831-188">Uso di Delhi, uso del PBX, uso di HYD PBX</span><span class="sxs-lookup"><span data-stu-id="77831-188">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="77831-189">Uso di Hyderabad, uso del PBX HYD, uso del PBX</span><span class="sxs-lookup"><span data-stu-id="77831-189">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="77831-190">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="77831-190">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="77831-191">True</span><span class="sxs-lookup"><span data-stu-id="77831-191">True</span></span></p></td>
<td><p><span data-ttu-id="77831-192">True</span><span class="sxs-lookup"><span data-stu-id="77831-192">True</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a><span data-ttu-id="77831-193">Abilitare il routing basato sulla posizione nella configurazione di routing</span><span class="sxs-lookup"><span data-stu-id="77831-193">Enable Location-Based Routing in the routing configuration</span></span>

<span data-ttu-id="77831-194">Infine, abilitare globalmente il routing basato sulla posizione alla configurazione di routing.</span><span class="sxs-lookup"><span data-stu-id="77831-194">Finally, globally enable Location-Based Routing to your routing configuration.</span></span> <span data-ttu-id="77831-195">Usare il comando di Windows PowerShell di Lync Server, New-CsRoutingConfiguration, per abilitare il routing basato sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="77831-195">Use the Lync Server Windows PowerShell command, New-CsRoutingConfiguration, to enable Location-Based Routing.</span></span>

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

<span data-ttu-id="77831-196">Per altre informazioni, vedere [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span><span class="sxs-lookup"><span data-stu-id="77831-196">For more information, see [Set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77831-197">mentre il routing basato sulla posizione deve essere abilitato tramite una configurazione globale, il set di regole da applicare verrà applicato solo per i siti, gli utenti e i trunk per i quali è stato configurato come specificato in questa documentazione.</span><span class="sxs-lookup"><span data-stu-id="77831-197">while Location-Based Routing must be enabled via a global configuration, the set of rules to be applied will only be enforced for the sites, users and trunks for which it has been configured as specified in this documentation.</span></span>



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="77831-198">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="77831-198">See Also</span></span>


[<span data-ttu-id="77831-199">Configurazione del routing in base alla posizione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="77831-199">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

