---
title: Ottimizzazione del supporto locale per il routing diretto
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 04/07/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: filippse
search.appverid: MET150
f1.keywords:
- NOCSH
description: Configurare l'ottimizzazione del supporto locale per il routing diretto
appliesto:
- Microsoft Teams
ms.openlocfilehash: ecbbb4f01267265f9f1041e7d51652d063ced353
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46576988"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="1a5ec-103">Configurare l'ottimizzazione del supporto locale per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="1a5ec-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="1a5ec-104">La configurazione dell'ottimizzazione del supporto locale si basa sulle impostazioni di rete comuni ad altre caratteristiche vocali del cloud, come il routing Location-Based e le chiamate di emergenza dinamiche.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="1a5ec-105">Per altre informazioni sulle aree geografiche di rete, i siti di rete, le subnet di rete e gli indirizzi IP attendibili, vedere Impostazioni di rete [per le funzionalità vocali nel cloud.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="1a5ec-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="1a5ec-106">Prima di configurare l'ottimizzazione del supporto locale, vedere [Ottimizzazione supporto locale per il routing diretto.](direct-routing-media-optimization.md)</span><span class="sxs-lookup"><span data-stu-id="1a5ec-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="1a5ec-107">Per configurare l'ottimizzazione del supporto locale, sono necessari i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="1a5ec-108">È possibile usare l'interfaccia di amministrazione di Teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="1a5ec-109">Per informazioni dettagliate, vedere [Gestire la topologia della rete.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="1a5ec-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="1a5ec-110">Configurare l'utente e i siti SBC come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="1a5ec-111">Configurare gli SBC per l'ottimizzazione degli elementi multimediali locali (in base alle specifiche del fornitore di SBC).</span><span class="sxs-lookup"><span data-stu-id="1a5ec-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="1a5ec-112">Il diagramma seguente illustra la configurazione della rete usata negli esempi di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="1a5ec-113">![Diagramma che illustra la configurazione della rete per esempi](media/direct-routing-media-op-9.png "Configurazione della rete per esempi")</span><span class="sxs-lookup"><span data-stu-id="1a5ec-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="1a5ec-114">Configurare l'utente e i siti SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="1a5ec-115">Per configurare l'utente e i siti SBC, è necessario:</span><span class="sxs-lookup"><span data-stu-id="1a5ec-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="1a5ec-116">[Gestire indirizzi IP attendibili esterni.](#manage-external-trusted-ip-addresses)</span><span class="sxs-lookup"><span data-stu-id="1a5ec-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="1a5ec-117">[Definire la topologia della rete](#define-the-network-topology) configurando le aree di rete, i siti di rete e le subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="1a5ec-118">[Definire la topologia di rete virtuale](#define-the-virtual-network-topology) assegnando Ibc ai siti con le modalità pertinenti e i valori SBC del proxy.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="1a5ec-119">Configurare SBC per l'ottimizzazione degli elementi multimediali locali in base alle specifiche del fornitore di SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="1a5ec-120">Questo articolo descrive la configurazione per i componenti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="1a5ec-121">Per informazioni sulla configurazione di SBC, vedere la documentazione del fornitore di SBC.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="1a5ec-122">L'ottimizzazione degli elementi multimediali locali è supportata dai fornitori di SBC seguenti:</span><span class="sxs-lookup"><span data-stu-id="1a5ec-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="1a5ec-123">Fornitore</span><span class="sxs-lookup"><span data-stu-id="1a5ec-123">Vendor</span></span> | <span data-ttu-id="1a5ec-124">Prodotto</span><span class="sxs-lookup"><span data-stu-id="1a5ec-124">Product</span></span> |    <span data-ttu-id="1a5ec-125">Versione software</span><span class="sxs-lookup"><span data-stu-id="1a5ec-125">Software version</span></span> |
|:------------|:-------|:-------|
| [<span data-ttu-id="1a5ec-126">Audiocodes</span><span class="sxs-lookup"><span data-stu-id="1a5ec-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="1a5ec-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="1a5ec-128">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="1a5ec-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1a5ec-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="1a5ec-130">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="1a5ec-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1a5ec-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="1a5ec-132">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="1a5ec-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1a5ec-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="1a5ec-134">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="1a5ec-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1a5ec-135">Mediant 1000B SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="1a5ec-136">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="1a5ec-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1a5ec-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="1a5ec-138">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="1a5ec-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1a5ec-139">Mediant Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="1a5ec-140">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="1a5ec-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="1a5ec-141">Mediant Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="1a5ec-142">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="1a5ec-142">7.20A.256</span></span> |
| [<span data-ttu-id="1a5ec-143">Barra multifunzione SBC Core</span><span class="sxs-lookup"><span data-stu-id="1a5ec-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="1a5ec-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="1a5ec-144">SBC 5110</span></span>         | <span data-ttu-id="1a5ec-145">8.2</span><span class="sxs-lookup"><span data-stu-id="1a5ec-145">8.2</span></span>  |
|            |  <span data-ttu-id="1a5ec-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="1a5ec-146">SBC 5210</span></span>         | <span data-ttu-id="1a5ec-147">8.2</span><span class="sxs-lookup"><span data-stu-id="1a5ec-147">8.2</span></span>  |
|            |  <span data-ttu-id="1a5ec-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="1a5ec-148">SBC 5400</span></span>         | <span data-ttu-id="1a5ec-149">8.2</span><span class="sxs-lookup"><span data-stu-id="1a5ec-149">8.2</span></span>  |
|            |  <span data-ttu-id="1a5ec-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="1a5ec-150">SBC 7000</span></span>         | <span data-ttu-id="1a5ec-151">8.2</span><span class="sxs-lookup"><span data-stu-id="1a5ec-151">8.2</span></span>  |
|            |  <span data-ttu-id="1a5ec-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="1a5ec-152">SBC SWe</span></span>          | <span data-ttu-id="1a5ec-153">8.2</span><span class="sxs-lookup"><span data-stu-id="1a5ec-153">8.2</span></span>  |
| [<span data-ttu-id="1a5ec-154">Bordo SBC della barra multifunzione</span><span class="sxs-lookup"><span data-stu-id="1a5ec-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="1a5ec-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="1a5ec-155">SBC SWe Lite</span></span> | <span data-ttu-id="1a5ec-156">8.1.5</span><span class="sxs-lookup"><span data-stu-id="1a5ec-156">8.1.5</span></span> |
|               | <span data-ttu-id="1a5ec-157">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="1a5ec-157">SBC 1000</span></span> | <span data-ttu-id="1a5ec-158">8.1.5</span><span class="sxs-lookup"><span data-stu-id="1a5ec-158">8.1.5</span></span>  |
|               | <span data-ttu-id="1a5ec-159">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="1a5ec-159">SBC 2000</span></span> | <span data-ttu-id="1a5ec-160">8.1.5</span><span class="sxs-lookup"><span data-stu-id="1a5ec-160">8.1.5</span></span>  |
| [<span data-ttu-id="1a5ec-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="1a5ec-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="1a5ec-162">anynode</span><span class="sxs-lookup"><span data-stu-id="1a5ec-162">anynode</span></span>          | <span data-ttu-id="1a5ec-163">4.0.1+</span><span class="sxs-lookup"><span data-stu-id="1a5ec-163">4.0.1+</span></span> |
| [<span data-ttu-id="1a5ec-164">Oracle</span><span class="sxs-lookup"><span data-stu-id="1a5ec-164">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="1a5ec-165">AP 1100</span><span class="sxs-lookup"><span data-stu-id="1a5ec-165">AP 1100</span></span> | <span data-ttu-id="1a5ec-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="1a5ec-166">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="1a5ec-167">AP 3900</span><span class="sxs-lookup"><span data-stu-id="1a5ec-167">AP 3900</span></span> | <span data-ttu-id="1a5ec-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="1a5ec-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="1a5ec-169">AP 4600</span><span class="sxs-lookup"><span data-stu-id="1a5ec-169">AP 4600</span></span> | <span data-ttu-id="1a5ec-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="1a5ec-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="1a5ec-171">AP 6300</span><span class="sxs-lookup"><span data-stu-id="1a5ec-171">AP 6300</span></span> | <span data-ttu-id="1a5ec-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="1a5ec-172">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="1a5ec-173">AP 6350</span><span class="sxs-lookup"><span data-stu-id="1a5ec-173">AP 6350</span></span> | <span data-ttu-id="1a5ec-174">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="1a5ec-174">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="1a5ec-175">VME</span><span class="sxs-lookup"><span data-stu-id="1a5ec-175">VME</span></span>     | <span data-ttu-id="1a5ec-176">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="1a5ec-176">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="1a5ec-177">Gestire indirizzi IP attendibili esterni</span><span class="sxs-lookup"><span data-stu-id="1a5ec-177">Manage external trusted IP addresses</span></span>

<span data-ttu-id="1a5ec-178">Gli IP attendibili esterni sono gli IP esterni Internet della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-178">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="1a5ec-179">Questi indirizzi IP sono gli indirizzi IP usati dai client di Microsoft Teams quando si connettono a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-179">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="1a5ec-180">È necessario aggiungere questi IP esterni per ogni sito in cui gli utenti usano l'ottimizzazione degli elementi multimediali locali.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-180">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="1a5ec-181">Per aggiungere gli indirizzi IP pubblici per ogni sito, usare il cmdlet New-CsTenantTrustedIPAddress public.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-181">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="1a5ec-182">È possibile definire un numero illimitato di indirizzi IP attendibili per un tenant.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-182">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="1a5ec-183">Se gli IP esterni visti da Microsoft 365 sono indirizzi IPv4 e IPv6, è necessario aggiungere entrambi i tipi di indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-183">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="1a5ec-184">Per IPv4, usare la maschera 32.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-184">For IPv4, use mask 32.</span></span> <span data-ttu-id="1a5ec-185">Per IPv6, usare la maschera 128.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-185">For IPv6, use mask 128.</span></span> <span data-ttu-id="1a5ec-186">È possibile aggiungere sia singoli indirizzi IP esterni che subnet IP esterne specificando MaskBit diversi nel cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-186">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="1a5ec-187">Esempio di aggiunta di indirizzi IP attendibili.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-187">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="1a5ec-188">Definire la topologia della rete</span><span class="sxs-lookup"><span data-stu-id="1a5ec-188">Define the network topology</span></span>

<span data-ttu-id="1a5ec-189">Questa sezione descrive come definire le aree di rete, i siti di rete e le subnet di rete per la topologia della rete.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-189">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="1a5ec-190">Tutti i parametri fa distinzione tra maiuscole e minuscole, quindi è necessario assicurarsi di usare lo stesso tipo di maiuscole/minuscole usato durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-190">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="1a5ec-191">Ad esempio, i valori GatewaySiteID "Vietnam" e "Vietnam" verranno trattati come siti diversi.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-191">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="1a5ec-192">Definire le aree di rete</span><span class="sxs-lookup"><span data-stu-id="1a5ec-192">Define network regions</span></span>

<span data-ttu-id="1a5ec-193">Per definire le aree geografiche di rete, usare New-CsTenantNetworkRegion cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-193">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="1a5ec-194">Il parametro RegionID è un nome logico che rappresenta la geografia dell'area geografica e non ha dipendenze o restrizioni.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-194">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="1a5ec-195">Il parametro CentralSite <site ID> è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-195">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="1a5ec-196">L'esempio seguente crea un'area di rete denominata APAC:</span><span class="sxs-lookup"><span data-stu-id="1a5ec-196">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="1a5ec-197">Definire i siti di rete</span><span class="sxs-lookup"><span data-stu-id="1a5ec-197">Define network sites</span></span>

<span data-ttu-id="1a5ec-198">Per definire i siti di rete, usare New-CsTenantNetworkSite cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-198">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="1a5ec-199">Ogni sito di rete deve essere associato a un'area geografica di rete.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-199">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="1a5ec-200">L'esempio seguente crea tre nuovi siti di rete, Vietnam, Indonesia e Singapore, nell'area APAC:</span><span class="sxs-lookup"><span data-stu-id="1a5ec-200">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="1a5ec-201">Definire le subnet di rete</span><span class="sxs-lookup"><span data-stu-id="1a5ec-201">Define network subnets</span></span>

<span data-ttu-id="1a5ec-202">Per definire le subnet di rete e associarle ai siti di rete, usare il cmdlet New-CsTenantNetworkSubnet rete.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-202">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="1a5ec-203">Ogni subnet di rete può essere associata a un solo sito.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-203">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="1a5ec-204">L'esempio seguente definisce tre subnet di rete e le associa ai tre siti di rete: Vietnam, Indonesia e Singapore:</span><span class="sxs-lookup"><span data-stu-id="1a5ec-204">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="1a5ec-205">Definire la topologia della rete virtuale</span><span class="sxs-lookup"><span data-stu-id="1a5ec-205">Define the virtual network topology</span></span> 

<span data-ttu-id="1a5ec-206">Prima di tutto, l'amministratore del tenant crea una nuova configurazione SBC per ogni SBC pertinente usando il cmdlet New-CsOnlinePSTNGateway tenant.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-206">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="1a5ec-207">L'amministratore del tenant definisce la topologia di rete virtuale specificando i siti di rete per gli oggetti gateway PSTN usando il cmdlet Set-CsOnlinePSTNGateway:</span><span class="sxs-lookup"><span data-stu-id="1a5ec-207">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="1a5ec-208">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="1a5ec-208">Note the following:</span></span> 
   - <span data-ttu-id="1a5ec-209">Se il cliente ha un singolo valore SBC, il parametro -ProxySBC deve essere obbligatorio $null o un valore FQDN SBC (central SBC con trunk centralizzati).</span><span class="sxs-lookup"><span data-stu-id="1a5ec-209">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="1a5ec-210">Il parametro -MediaBypass deve essere impostato su $true per supportare l'ottimizzazione di elementi multimediali locali.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-210">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="1a5ec-211">Se per SBC non è impostato il parametro -BypassMode, le intestazioni X-MS non vengono inviate.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-211">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="1a5ec-212">Tutti i parametri fa distinzione tra maiuscole e minuscole, quindi è necessario assicurarsi di usare lo stesso tipo di maiuscole/minuscole usato durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-212">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="1a5ec-213">Ad esempio, i valori GatewaySiteID "Vietnam" e "Vietnam" verranno trattati come siti diversi.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-213">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="1a5ec-214">L'esempio seguente aggiunge tre SBC ai siti di rete Vietnam, Indonesia e Singapore nell'area APAC con la modalità Bypass sempre:</span><span class="sxs-lookup"><span data-stu-id="1a5ec-214">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="1a5ec-215">Nota: per garantire operazioni ininterrotte durante la configurazione contemporaneamente dell'ottimizzazione degli elementi multimediali locali e del Location-Based Routing (LBR), è necessario abilitare le SBC a valle per LBR impostando il parametro GatewaySiteLbrEnabled su $true per ogni SBC a valle.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-215">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="1a5ec-216">Questa impostazione non è obbligatoria per il proxy SBC.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-216">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="1a5ec-217">In base alle informazioni precedenti, l'instradamento diretto includerà tre intestazioni SIP proprietarie per gli inviti SIP e i nuovi inviti, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-217">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="1a5ec-218">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span><span class="sxs-lookup"><span data-stu-id="1a5ec-218">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="1a5ec-219">Nome intestazione</span><span class="sxs-lookup"><span data-stu-id="1a5ec-219">Header name</span></span> | <span data-ttu-id="1a5ec-220">Valori</span><span class="sxs-lookup"><span data-stu-id="1a5ec-220">Values</span></span> | <span data-ttu-id="1a5ec-221">Commenti</span><span class="sxs-lookup"><span data-stu-id="1a5ec-221">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="1a5ec-222">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="1a5ec-222">X-MS-UserLocation</span></span> | <span data-ttu-id="1a5ec-223">interno/esterno</span><span class="sxs-lookup"><span data-stu-id="1a5ec-223">internal/external</span></span> | <span data-ttu-id="1a5ec-224">Indica se l'utente è interno o esterno</span><span class="sxs-lookup"><span data-stu-id="1a5ec-224">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="1a5ec-225">Request-URI INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span><span class="sxs-lookup"><span data-stu-id="1a5ec-225">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="1a5ec-226">SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="1a5ec-226">SBC FQDN</span></span> | <span data-ttu-id="1a5ec-227">L'FQDN mirato per la chiamata anche se SBC non è connesso direttamente al routing diretto</span><span class="sxs-lookup"><span data-stu-id="1a5ec-227">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="1a5ec-228">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="1a5ec-228">X-MS-MediaPath</span></span> | <span data-ttu-id="1a5ec-229">Esempio: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a5ec-229">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="1a5ec-230">Ordine degli SBC da usare per il percorso multimediale tra l'utente e il sito SBC di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-230">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="1a5ec-231">Il valore SBC finale è sempre l'ultimo</span><span class="sxs-lookup"><span data-stu-id="1a5ec-231">The final SBC is always last</span></span> |
| <span data-ttu-id="1a5ec-232">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="1a5ec-232">X-MS-UserSite</span></span> | <span data-ttu-id="1a5ec-233">usersiteID</span><span class="sxs-lookup"><span data-stu-id="1a5ec-233">usersiteID</span></span> | <span data-ttu-id="1a5ec-234">Stringa definita dall'amministratore del tenant</span><span class="sxs-lookup"><span data-stu-id="1a5ec-234">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="1a5ec-235">Flussi delle chiamate</span><span class="sxs-lookup"><span data-stu-id="1a5ec-235">Call flows</span></span> 

<span data-ttu-id="1a5ec-236">Di seguito sono illustrati i flussi delle chiamate per due modalità:</span><span class="sxs-lookup"><span data-stu-id="1a5ec-236">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="1a5ec-237">Ignora sempre</span><span class="sxs-lookup"><span data-stu-id="1a5ec-237">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="1a5ec-238">Solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="1a5ec-238">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="1a5ec-239">Modalità bypass sempre</span><span class="sxs-lookup"><span data-stu-id="1a5ec-239">Always Bypass mode</span></span>

<span data-ttu-id="1a5ec-240">La modalità bypass è l'opzione più semplice da configurare.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-240">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="1a5ec-241">L'amministratore tenant può configurare un singolo sito per tutti gli utenti e gli SBC se tutti gli SBC sono raggiungibili da qualsiasi sito.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-241">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="1a5ec-242">Gli esempi mostrano la modalità bypass sempre per gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="1a5ec-242">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="1a5ec-243">Chiamate in uscita e l'utente si trova nella stessa posizione dell'SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-243">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="1a5ec-244">Chiamate in ingresso e l'utente si trova nella stessa posizione del controller SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-244">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="1a5ec-245">Chiamate in uscita e l'utente è esterno</span><span class="sxs-lookup"><span data-stu-id="1a5ec-245">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="1a5ec-246">Chiamate in ingresso e l'utente è esterno</span><span class="sxs-lookup"><span data-stu-id="1a5ec-246">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="1a5ec-247">La tabella seguente mostra l'FQDN e gli indirizzi IP usati negli esempi:</span><span class="sxs-lookup"><span data-stu-id="1a5ec-247">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="1a5ec-248">FQDN</span><span class="sxs-lookup"><span data-stu-id="1a5ec-248">FQDN</span></span> | <span data-ttu-id="1a5ec-249">Indirizzo IP esterno SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-249">SBC external IP address</span></span> | <span data-ttu-id="1a5ec-250">Indirizzo IP interno SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-250">SBC internal IP Address</span></span> | <span data-ttu-id="1a5ec-251">Subnet interna</span><span class="sxs-lookup"><span data-stu-id="1a5ec-251">Internal subnet</span></span> | <span data-ttu-id="1a5ec-252">Posizione</span><span class="sxs-lookup"><span data-stu-id="1a5ec-252">Location</span></span> | <span data-ttu-id="1a5ec-253">NAT esterno (IP attendibile)</span><span class="sxs-lookup"><span data-stu-id="1a5ec-253">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="1a5ec-254">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a5ec-254">VNsbc.contoso.com</span></span> | <span data-ttu-id="1a5ec-255">Nessuno</span><span class="sxs-lookup"><span data-stu-id="1a5ec-255">None</span></span> | <span data-ttu-id="1a5ec-256">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="1a5ec-256">192.168.1.5</span></span> | <span data-ttu-id="1a5ec-257">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="1a5ec-257">192.168.1.0/24</span></span> | <span data-ttu-id="1a5ec-258">Vietnam</span><span class="sxs-lookup"><span data-stu-id="1a5ec-258">Vietnam</span></span> | <span data-ttu-id="1a5ec-259">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="1a5ec-259">172.16.240.110</span></span> |
| <span data-ttu-id="1a5ec-260">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a5ec-260">IDsbc.contoso.com</span></span> | <span data-ttu-id="1a5ec-261">Nessuno</span><span class="sxs-lookup"><span data-stu-id="1a5ec-261">None</span></span> | <span data-ttu-id="1a5ec-262">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="1a5ec-262">192.168.2.5</span></span> | <span data-ttu-id="1a5ec-263">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="1a5ec-263">192.168.2.0/24</span></span> | <span data-ttu-id="1a5ec-264">Indonesia</span><span class="sxs-lookup"><span data-stu-id="1a5ec-264">Indonesia</span></span> | <span data-ttu-id="1a5ec-265">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="1a5ec-265">172.16.240.120</span></span> |
| <span data-ttu-id="1a5ec-266">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a5ec-266">proxysbc.contoso.com</span></span> | <span data-ttu-id="1a5ec-267">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="1a5ec-267">172.16.240.133</span></span> | <span data-ttu-id="1a5ec-268">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="1a5ec-268">192.168.3.5</span></span> | <span data-ttu-id="1a5ec-269">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="1a5ec-269">192.168.3.0/24</span></span> | <span data-ttu-id="1a5ec-270">Singapore</span><span class="sxs-lookup"><span data-stu-id="1a5ec-270">Singapore</span></span> | <span data-ttu-id="1a5ec-271">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="1a5ec-271">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="1a5ec-272">Le chiamate in uscita e l'utente si trova nella stessa posizione dell'SBC con Always Bypass</span><span class="sxs-lookup"><span data-stu-id="1a5ec-272">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="1a5ec-273">Modalità</span><span class="sxs-lookup"><span data-stu-id="1a5ec-273">Mode</span></span> |    <span data-ttu-id="1a5ec-274">Utente</span><span class="sxs-lookup"><span data-stu-id="1a5ec-274">User</span></span> |  <span data-ttu-id="1a5ec-275">Posizione</span><span class="sxs-lookup"><span data-stu-id="1a5ec-275">Location</span></span> |  <span data-ttu-id="1a5ec-276">Direzione della chiamata</span><span class="sxs-lookup"><span data-stu-id="1a5ec-276">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="1a5ec-277">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="1a5ec-277">AlwaysBypass</span></span> |    <span data-ttu-id="1a5ec-278">Interno</span><span class="sxs-lookup"><span data-stu-id="1a5ec-278">Internal</span></span> |  <span data-ttu-id="1a5ec-279">Lo stesso sito di SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-279">The same site as SBC</span></span> |  <span data-ttu-id="1a5ec-280">In uscita</span><span class="sxs-lookup"><span data-stu-id="1a5ec-280">Outbound</span></span> |

<span data-ttu-id="1a5ec-281">La tabella seguente mostra la configurazione e l'azione dell'utente finale:</span><span class="sxs-lookup"><span data-stu-id="1a5ec-281">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="1a5ec-282">Posizione fisica dell'utente</span><span class="sxs-lookup"><span data-stu-id="1a5ec-282">User physical location</span></span>| <span data-ttu-id="1a5ec-283">Un utente effettua o riceve una chiamata a/da un numero</span><span class="sxs-lookup"><span data-stu-id="1a5ec-283">User makes or receives a call to/from number</span></span> | <span data-ttu-id="1a5ec-284">Numero di telefono utente</span><span class="sxs-lookup"><span data-stu-id="1a5ec-284">User phone number</span></span>  | <span data-ttu-id="1a5ec-285">Criteri per l'instradamento vocale online</span><span class="sxs-lookup"><span data-stu-id="1a5ec-285">Online Voice Routing Policy</span></span> | <span data-ttu-id="1a5ec-286">Modalità configurata per SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-286">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="1a5ec-287">Vietnam</span><span class="sxs-lookup"><span data-stu-id="1a5ec-287">Vietnam</span></span> | <span data-ttu-id="1a5ec-288">+84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="1a5ec-288">+84 4 3926 3000</span></span> | <span data-ttu-id="1a5ec-289">+84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="1a5ec-289">+84 4 5555 5555</span></span>   | <span data-ttu-id="1a5ec-290">Priorità 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a5ec-290">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="1a5ec-291">Priorità 2: .\* - proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a5ec-291">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="1a5ec-292">VNsbc.contoso.com - Ignora sempre</span><span class="sxs-lookup"><span data-stu-id="1a5ec-292">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="1a5ec-293">proxysbc.contoso.com - Ignora sempre</span><span class="sxs-lookup"><span data-stu-id="1a5ec-293">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="1a5ec-294">Il diagramma seguente mostra il profilo SIP di una chiamata in uscita con la modalità bypass sempre e l'utente nella stessa posizione del controller SBC.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-294">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="1a5ec-295">![Diagramma che illustra le chiamate in uscita](media/direct-routing-media-op-10.png "Chiamate in uscita")</span><span class="sxs-lookup"><span data-stu-id="1a5ec-295">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="1a5ec-296">La tabella seguente mostra le intestazioni X-MS inviate dal routing diretto:</span><span class="sxs-lookup"><span data-stu-id="1a5ec-296">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="1a5ec-297">Parametro</span><span class="sxs-lookup"><span data-stu-id="1a5ec-297">Parameter</span></span> | <span data-ttu-id="1a5ec-298">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="1a5ec-298">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="1a5ec-299">Invita +8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a5ec-299">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="1a5ec-300">L'FQDN di destinazione del servizio SBC definito nel criterio di routing vocale online viene inviato nell'URI richiesta</span><span class="sxs-lookup"><span data-stu-id="1a5ec-300">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="1a5ec-301">X-MS-UserLocation: interno</span><span class="sxs-lookup"><span data-stu-id="1a5ec-301">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="1a5ec-302">Il campo indica che l'utente si trova all'interno della rete aziendale</span><span class="sxs-lookup"><span data-stu-id="1a5ec-302">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="1a5ec-303">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a5ec-303">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="1a5ec-304">Specifica quale SBC deve attraversare il client fino al valore SBC di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-304">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="1a5ec-305">In questo caso, se l'opzione Bypass è sempre ignorata e il client è interno, il nome di destinazione inviato è l'unico nome nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-305">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="1a5ec-306">X-MS-UserSite: Vietnam</span><span class="sxs-lookup"><span data-stu-id="1a5ec-306">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="1a5ec-307">Il campo indicato all'interno del sito in cui si trova l'utente.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-307">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="1a5ec-308">Chiamate in entrata e l'utente si trova nella stessa posizione del controller SBC con Bypass sempre</span><span class="sxs-lookup"><span data-stu-id="1a5ec-308">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="1a5ec-309">Modalità</span><span class="sxs-lookup"><span data-stu-id="1a5ec-309">Mode</span></span> |    <span data-ttu-id="1a5ec-310">Utente</span><span class="sxs-lookup"><span data-stu-id="1a5ec-310">User</span></span> |  <span data-ttu-id="1a5ec-311">Posizione</span><span class="sxs-lookup"><span data-stu-id="1a5ec-311">Location</span></span> |  <span data-ttu-id="1a5ec-312">Direzione della chiamata</span><span class="sxs-lookup"><span data-stu-id="1a5ec-312">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="1a5ec-313">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="1a5ec-313">AlwaysBypass</span></span> |    <span data-ttu-id="1a5ec-314">Interno</span><span class="sxs-lookup"><span data-stu-id="1a5ec-314">Internal</span></span> | <span data-ttu-id="1a5ec-315">Lo stesso sito di SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-315">The same site as SBC</span></span> | <span data-ttu-id="1a5ec-316">In ingresso</span><span class="sxs-lookup"><span data-stu-id="1a5ec-316">Inbound</span></span> |


<span data-ttu-id="1a5ec-317">Durante una chiamata in ingresso, la posizione dell'utente è sconosciuta e il servizio SBC deve indovinare dove si trova l'utente.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-317">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="1a5ec-318">Se l'ipotesi non è corretta, sarà richiesto un nuovo invito.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-318">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="1a5ec-319">In questo caso si presuppone che l'utente sia interno, che il flusso dei contenuti multimediali sia diretto e che non siano necessarie altre azioni (invitarlo di nuovo).</span><span class="sxs-lookup"><span data-stu-id="1a5ec-319">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="1a5ec-320">Il servizio SBC connesso al servizio di instradamento diretto segnala la posizione SBC di origine fornendo i campi Record-Route contatti.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-320">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="1a5ec-321">In base a questi campi, il percorso del supporto viene calcolato tramite routing diretto.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-321">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="1a5ec-322">Nota: dato che un utente può avere più endpoint, il supporto di 183 non è possibile.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-322">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="1a5ec-323">In questo caso, l'instradamento diretto userà sempre lo squillo 180.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-323">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="1a5ec-324">Il diagramma seguente illustra la proprietà SIP per le chiamate in ingresso con la modalità AlwaysBypass e l'utente si trova nella stessa posizione del controller SBC.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-324">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagramma che mostra la sip](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="1a5ec-326">Chiamate in uscita e l'utente è esterno con Bypass sempre</span><span class="sxs-lookup"><span data-stu-id="1a5ec-326">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="1a5ec-327">Modalità</span><span class="sxs-lookup"><span data-stu-id="1a5ec-327">Mode</span></span> |    <span data-ttu-id="1a5ec-328">Utente</span><span class="sxs-lookup"><span data-stu-id="1a5ec-328">User</span></span> |  <span data-ttu-id="1a5ec-329">Sito</span><span class="sxs-lookup"><span data-stu-id="1a5ec-329">Site</span></span> |  <span data-ttu-id="1a5ec-330">Direzione della chiamata</span><span class="sxs-lookup"><span data-stu-id="1a5ec-330">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="1a5ec-331">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="1a5ec-331">AlwaysBypass</span></span> |  <span data-ttu-id="1a5ec-332">Esterna</span><span class="sxs-lookup"><span data-stu-id="1a5ec-332">External</span></span> |  <span data-ttu-id="1a5ec-333">N/D</span><span class="sxs-lookup"><span data-stu-id="1a5ec-333">N/A</span></span> | <span data-ttu-id="1a5ec-334">In uscita</span><span class="sxs-lookup"><span data-stu-id="1a5ec-334">Outbound</span></span> |


<span data-ttu-id="1a5ec-335">Il diagramma seguente mostra la classe SIP per una chiamata in uscita con la modalità AlwaysBypass e l'utente è esterno:</span><span class="sxs-lookup"><span data-stu-id="1a5ec-335">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagramma che mostra la sip](media/direct-routing-media-op-12.png)

<span data-ttu-id="1a5ec-337">La tabella seguente mostra le intestazioni X-MS inviate dal servizio di routing diretto:</span><span class="sxs-lookup"><span data-stu-id="1a5ec-337">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="1a5ec-338">Parametro</span><span class="sxs-lookup"><span data-stu-id="1a5ec-338">Parameter</span></span> |   <span data-ttu-id="1a5ec-339">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="1a5ec-339">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="1a5ec-340">Invita +8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a5ec-340">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="1a5ec-341">L'FQDN di destinazione del servizio SBC definito nel criterio di routing vocale online viene inviato nell'URI richiesta.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-341">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="1a5ec-342">X-MS-UserLocation: esterna</span><span class="sxs-lookup"><span data-stu-id="1a5ec-342">X-MS-UserLocation: external</span></span> | <span data-ttu-id="1a5ec-343">Il campo indica che l'utente si trova all'esterno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-343">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="1a5ec-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a5ec-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="1a5ec-345">Specifica quale SBC deve attraversare il client fino al valore SBC di destinazione.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-345">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="1a5ec-346">In questo caso, poiché è sempre stato ignorato, il client è esterno.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-346">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="1a5ec-347">Chiamate in ingresso e l'utente è esterno con Bypass sempre</span><span class="sxs-lookup"><span data-stu-id="1a5ec-347">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="1a5ec-348">Modalità</span><span class="sxs-lookup"><span data-stu-id="1a5ec-348">Mode</span></span> | <span data-ttu-id="1a5ec-349">Utente</span><span class="sxs-lookup"><span data-stu-id="1a5ec-349">User</span></span> | <span data-ttu-id="1a5ec-350">Sito</span><span class="sxs-lookup"><span data-stu-id="1a5ec-350">Site</span></span> |  <span data-ttu-id="1a5ec-351">Direzione della chiamata</span><span class="sxs-lookup"><span data-stu-id="1a5ec-351">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="1a5ec-352">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="1a5ec-352">AlwaysBypass</span></span> |  <span data-ttu-id="1a5ec-353">Esterna</span><span class="sxs-lookup"><span data-stu-id="1a5ec-353">External</span></span> |  <span data-ttu-id="1a5ec-354">N/D</span><span class="sxs-lookup"><span data-stu-id="1a5ec-354">N/A</span></span> |   <span data-ttu-id="1a5ec-355">In ingresso</span><span class="sxs-lookup"><span data-stu-id="1a5ec-355">Inbound</span></span> |

<span data-ttu-id="1a5ec-356">Per una chiamata in ingresso, l'SBC connesso al routing diretto deve inviare un nuovo invito (per impostazione predefinita, i candidati per i supporti locali sono sempre offerti) se la posizione dell'utente è esterna.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-356">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="1a5ec-357">X-MediaPath viene calcolato in base Record-Route'utente SBC specificato.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-357">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="1a5ec-358">Il diagramma seguente illustra il profilo SIP per una chiamata in ingresso con la modalità AlwaysBypass e l'utente è esterno.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-358">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagramma che mostra la sip](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="1a5ec-360">Solo per la modalità utenti locali</span><span class="sxs-lookup"><span data-stu-id="1a5ec-360">Only for local users mode</span></span>

<span data-ttu-id="1a5ec-361">I candidati per gli elementi multimediali locali del sito SBC di destinazione verranno offerti solo se un utente si trova nella stessa posizione del database SBC.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-361">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="1a5ec-362">In tutti gli altri casi, il flusso degli elementi multimediali verrà attraverso un INDIRIZZO IP interno o esterno del proxy SBC.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-362">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="1a5ec-363">Sono descritti gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="1a5ec-363">The following scenarios are described:</span></span>

- [<span data-ttu-id="1a5ec-364">Chiamate in uscita e l'utente si trova nella stessa posizione dell'SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-364">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="1a5ec-365">Chiamate in ingresso e l'utente si trova nella stessa posizione del controller SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-365">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="1a5ec-366">L'utente non si trova nella stessa posizione del database SBC ma si trova nella rete aziendale</span><span class="sxs-lookup"><span data-stu-id="1a5ec-366">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="1a5ec-367">Chiamate in ingresso e l'utente è interno, ma non si trova nella stessa posizione del controller SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-367">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="1a5ec-368">La tabella seguente mostra la configurazione e l'azione degli utenti finali:</span><span class="sxs-lookup"><span data-stu-id="1a5ec-368">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="1a5ec-369">Posizione fisica dell'utente</span><span class="sxs-lookup"><span data-stu-id="1a5ec-369">User physical location</span></span> |  <span data-ttu-id="1a5ec-370">Un utente effettua o riceve una chiamata a/da un numero</span><span class="sxs-lookup"><span data-stu-id="1a5ec-370">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="1a5ec-371">Numero di telefono utente</span><span class="sxs-lookup"><span data-stu-id="1a5ec-371">User phone number</span></span> | <span data-ttu-id="1a5ec-372">Criteri per l'instradamento vocale online</span><span class="sxs-lookup"><span data-stu-id="1a5ec-372">Online Voice Routing Policy</span></span> |   <span data-ttu-id="1a5ec-373">Modalità configurata per SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-373">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="1a5ec-374">Vietnam</span><span class="sxs-lookup"><span data-stu-id="1a5ec-374">Vietnam</span></span> | <span data-ttu-id="1a5ec-375">+84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="1a5ec-375">+84 4 3926  3000</span></span> |  <span data-ttu-id="1a5ec-376">+84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="1a5ec-376">+84 4 5555 5555</span></span> | <span data-ttu-id="1a5ec-377">Priorità 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a5ec-377">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="1a5ec-378">Priorità 2: .\* - proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="1a5ec-378">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="1a5ec-379">VNsbc.contoso.com - OnlyForLocalUsers Proxysbc.contoso.com – Bypass sempre</span><span class="sxs-lookup"><span data-stu-id="1a5ec-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="1a5ec-380">Chiamate in uscita e l'utente si trova nella stessa posizione del servizio SBC con Solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="1a5ec-380">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="1a5ec-381">Modalità</span><span class="sxs-lookup"><span data-stu-id="1a5ec-381">Mode</span></span> | <span data-ttu-id="1a5ec-382">Utente</span><span class="sxs-lookup"><span data-stu-id="1a5ec-382">User</span></span> | <span data-ttu-id="1a5ec-383">Sito</span><span class="sxs-lookup"><span data-stu-id="1a5ec-383">Site</span></span> | <span data-ttu-id="1a5ec-384">Direzione della chiamata</span><span class="sxs-lookup"><span data-stu-id="1a5ec-384">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="1a5ec-385">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="1a5ec-385">OnlyForLocalUsers</span></span> |   <span data-ttu-id="1a5ec-386">Interno</span><span class="sxs-lookup"><span data-stu-id="1a5ec-386">Internal</span></span> |<span data-ttu-id="1a5ec-387">Come SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-387">Same as SBC</span></span>   | <span data-ttu-id="1a5ec-388">In uscita</span><span class="sxs-lookup"><span data-stu-id="1a5ec-388">Outbound</span></span> |

<span data-ttu-id="1a5ec-389">Il diagramma seguente mostra una chiamata in uscita con la modalità OnlyForLocalUsers e l'utente si trova nella stessa posizione del database SBC.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-389">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="1a5ec-390">Si tratta dello stesso flusso mostrato nelle chiamate in uscita quando l'utente si trova nella [stessa posizione del servizio SBC.](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)</span><span class="sxs-lookup"><span data-stu-id="1a5ec-390">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramma che mostra la sip](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="1a5ec-392">Chiamate in ingresso e l'utente si trova nella stessa posizione del servizio SBC con Solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="1a5ec-392">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="1a5ec-393">Modalità</span><span class="sxs-lookup"><span data-stu-id="1a5ec-393">Mode</span></span> | <span data-ttu-id="1a5ec-394">Utente</span><span class="sxs-lookup"><span data-stu-id="1a5ec-394">User</span></span> | <span data-ttu-id="1a5ec-395">Sito</span><span class="sxs-lookup"><span data-stu-id="1a5ec-395">Site</span></span> | <span data-ttu-id="1a5ec-396">Direzione della chiamata</span><span class="sxs-lookup"><span data-stu-id="1a5ec-396">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="1a5ec-397">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="1a5ec-397">OnlyForLocalUsers</span></span> |   <span data-ttu-id="1a5ec-398">Interno</span><span class="sxs-lookup"><span data-stu-id="1a5ec-398">Internal</span></span> | <span data-ttu-id="1a5ec-399">Come SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-399">Same as SBC</span></span> | <span data-ttu-id="1a5ec-400">In ingresso</span><span class="sxs-lookup"><span data-stu-id="1a5ec-400">Inbound</span></span> |

<span data-ttu-id="1a5ec-401">Il diagramma seguente mostra una chiamata in ingresso con la modalità OnlyForLocalUsers e l'utente si trova nella stessa posizione del database SBC.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-401">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="1a5ec-402">Si tratta dello stesso flusso illustrato nelle chiamate in ingresso quando l'utente si trova nella stessa [posizione del servizio SBC.](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)</span><span class="sxs-lookup"><span data-stu-id="1a5ec-402">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramma che mostra la sip](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="1a5ec-404">L'utente non si trova nella stessa posizione del database SBC, ma si trova nella rete aziendale con l'account solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="1a5ec-404">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="1a5ec-405">Modalità</span><span class="sxs-lookup"><span data-stu-id="1a5ec-405">Mode</span></span> | <span data-ttu-id="1a5ec-406">Utente</span><span class="sxs-lookup"><span data-stu-id="1a5ec-406">User</span></span> | <span data-ttu-id="1a5ec-407">Sito</span><span class="sxs-lookup"><span data-stu-id="1a5ec-407">Site</span></span> |<span data-ttu-id="1a5ec-408">Direzione della chiamata</span><span class="sxs-lookup"><span data-stu-id="1a5ec-408">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="1a5ec-409">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="1a5ec-409">OnlyForLocalUsers</span></span>  | <span data-ttu-id="1a5ec-410">Interno</span><span class="sxs-lookup"><span data-stu-id="1a5ec-410">Internal</span></span> |   <span data-ttu-id="1a5ec-411">Diverso da SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-411">Different from SBC</span></span> | <span data-ttu-id="1a5ec-412">In uscita</span><span class="sxs-lookup"><span data-stu-id="1a5ec-412">Outbound</span></span> |

<span data-ttu-id="1a5ec-413">Il routing diretto calcola X-MediaPath in base alla posizione segnalata dell'utente e alla modalità configurata nel database SBC.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-413">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="1a5ec-414">Il diagramma seguente mostra una chiamata in uscita con la modalità OnlyForLocalUsers e un utente interno che non si trova nella stessa posizione del database SBC.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-414">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramma che mostra la sip](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="1a5ec-416">Chiamata in ingresso e l'utente è interno, ma non si trova nella stessa posizione del database SBC con solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="1a5ec-416">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="1a5ec-417">Modalità</span><span class="sxs-lookup"><span data-stu-id="1a5ec-417">Mode</span></span> |    <span data-ttu-id="1a5ec-418">Utente</span><span class="sxs-lookup"><span data-stu-id="1a5ec-418">User</span></span> |  <span data-ttu-id="1a5ec-419">Sito</span><span class="sxs-lookup"><span data-stu-id="1a5ec-419">Site</span></span> |  <span data-ttu-id="1a5ec-420">Direzione della chiamata</span><span class="sxs-lookup"><span data-stu-id="1a5ec-420">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="1a5ec-421">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="1a5ec-421">OnlyForLocalUsers</span></span> | <span data-ttu-id="1a5ec-422">Interno</span><span class="sxs-lookup"><span data-stu-id="1a5ec-422">Internal</span></span> |    <span data-ttu-id="1a5ec-423">Diverso da SBC</span><span class="sxs-lookup"><span data-stu-id="1a5ec-423">Different from SBC</span></span> |    <span data-ttu-id="1a5ec-424">In ingresso</span><span class="sxs-lookup"><span data-stu-id="1a5ec-424">Inbound</span></span> |

<span data-ttu-id="1a5ec-425">Il diagramma seguente mostra una chiamata in ingresso con la modalità OnlyForLocalUsers e un utente interno che non si trova nella stessa posizione del database SBC.</span><span class="sxs-lookup"><span data-stu-id="1a5ec-425">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramma che mostra la sip](media/direct-routing-media-op-17.png)









