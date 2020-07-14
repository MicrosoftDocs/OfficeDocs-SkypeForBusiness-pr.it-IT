---
title: Ottimizzazione dei media locali di routing diretto
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
description: Configurare l'ottimizzazione multimediale locale per il routing diretto
appliesto:
- Microsoft Teams
ms.openlocfilehash: e53f9156b6ab6d33223c9b1d3e11a604ba0c1c31
ms.sourcegitcommit: 113e3a7314505cf78da57917ff62642125fb11fd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/14/2020
ms.locfileid: "45121606"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="db5de-103">Configurare l'ottimizzazione multimediale locale per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="db5de-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="db5de-104">La configurazione per l'ottimizzazione media locale si basa sulle impostazioni di rete comuni ad altre caratteristiche vocali del cloud, ad esempio routing basato sulla posizione e chiamate di emergenza dinamiche.</span><span class="sxs-lookup"><span data-stu-id="db5de-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="db5de-105">Per altre informazioni sulle aree di rete, i siti di rete, le subnet di rete e gli indirizzi IP attendibili, vedere [impostazioni di rete per le funzionalità di cloud Voice](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="db5de-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="db5de-106">Prima di configurare l'ottimizzazione multimediale locale, vedere [ottimizzazione dei contenuti multimediali locali per il routing diretto](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="db5de-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="db5de-107">Per configurare l'ottimizzazione multimediale locale, sono necessarie le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="db5de-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="db5de-108">Puoi usare l'interfaccia di amministrazione di teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="db5de-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="db5de-109">Per informazioni dettagliate, vedere [gestire la topologia di rete](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="db5de-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="db5de-110">Configurare l'utente e i siti SBC (come descritto in questo articolo).</span><span class="sxs-lookup"><span data-stu-id="db5de-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="db5de-111">Configurare la SBCs for local Media Optimization (in base alla specifica del fornitore SBC).</span><span class="sxs-lookup"><span data-stu-id="db5de-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="db5de-112">Il diagramma seguente mostra la configurazione della rete usata negli esempi in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="db5de-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="db5de-113">![Diagramma che mostra la configurazione della rete per gli esempi](media/direct-routing-media-op-9.png "Configurazione di rete per gli esempi")</span><span class="sxs-lookup"><span data-stu-id="db5de-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="db5de-114">Configurare l'utente e i siti SBC</span><span class="sxs-lookup"><span data-stu-id="db5de-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="db5de-115">Per configurare l'utente e i siti SBC, sarà necessario:</span><span class="sxs-lookup"><span data-stu-id="db5de-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="db5de-116">[Gestire indirizzi IP attendibili esterni](#manage-external-trusted-ip-addresses).</span><span class="sxs-lookup"><span data-stu-id="db5de-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="db5de-117">[Definire la topologia di rete](#define-the-network-topology) configurando le aree di rete, i siti di rete e le subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="db5de-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="db5de-118">[Definire la topologia di rete virtuale](#define-the-virtual-network-topology) assegnando SBC (s) ai siti con le modalità pertinenti e i valori del proxy SBC.</span><span class="sxs-lookup"><span data-stu-id="db5de-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="db5de-119">Configurare SBC per l'ottimizzazione di elementi multimediali locali in base alla specifica del fornitore SBC</span><span class="sxs-lookup"><span data-stu-id="db5de-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="db5de-120">Questo articolo descrive la configurazione per i componenti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="db5de-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="db5de-121">Per informazioni sulla configurazione di SBC, vedere la documentazione del fornitore SBC.</span><span class="sxs-lookup"><span data-stu-id="db5de-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="db5de-122">L'ottimizzazione media locale è supportata dai seguenti fornitori di SBC:</span><span class="sxs-lookup"><span data-stu-id="db5de-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="db5de-123">Fornitore</span><span class="sxs-lookup"><span data-stu-id="db5de-123">Vendor</span></span> | <span data-ttu-id="db5de-124">Prodotto</span><span class="sxs-lookup"><span data-stu-id="db5de-124">Product</span></span> |    <span data-ttu-id="db5de-125">Versione software</span><span class="sxs-lookup"><span data-stu-id="db5de-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="db5de-126">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="db5de-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="db5de-127">SBC 500 medium</span><span class="sxs-lookup"><span data-stu-id="db5de-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="db5de-128">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="db5de-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="db5de-129">SBC 800 Medium</span><span class="sxs-lookup"><span data-stu-id="db5de-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="db5de-130">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="db5de-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="db5de-131">SBC 2600 medium</span><span class="sxs-lookup"><span data-stu-id="db5de-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="db5de-132">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="db5de-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="db5de-133">SBC 4000 medium</span><span class="sxs-lookup"><span data-stu-id="db5de-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="db5de-134">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="db5de-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="db5de-135">SBC 1000B medium</span><span class="sxs-lookup"><span data-stu-id="db5de-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="db5de-136">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="db5de-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="db5de-137">SBC 9000 medium</span><span class="sxs-lookup"><span data-stu-id="db5de-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="db5de-138">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="db5de-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="db5de-139">SBC virtuale per edizioni medious</span><span class="sxs-lookup"><span data-stu-id="db5de-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="db5de-140">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="db5de-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="db5de-141">SBC Cloud Edition</span><span class="sxs-lookup"><span data-stu-id="db5de-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="db5de-142">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="db5de-142">7.20A.256</span></span> |
| [<span data-ttu-id="db5de-143">Core SBC della barra multifunzione</span><span class="sxs-lookup"><span data-stu-id="db5de-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="db5de-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="db5de-144">SBC 5110</span></span>         | <span data-ttu-id="db5de-145">8,2</span><span class="sxs-lookup"><span data-stu-id="db5de-145">8.2</span></span>  |
|            |  <span data-ttu-id="db5de-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="db5de-146">SBC 5210</span></span>         | <span data-ttu-id="db5de-147">8,2</span><span class="sxs-lookup"><span data-stu-id="db5de-147">8.2</span></span>  |
|            |  <span data-ttu-id="db5de-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="db5de-148">SBC 5400</span></span>         | <span data-ttu-id="db5de-149">8,2</span><span class="sxs-lookup"><span data-stu-id="db5de-149">8.2</span></span>  |
|            |  <span data-ttu-id="db5de-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="db5de-150">SBC 7000</span></span>         | <span data-ttu-id="db5de-151">8,2</span><span class="sxs-lookup"><span data-stu-id="db5de-151">8.2</span></span>  |
|            |  <span data-ttu-id="db5de-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="db5de-152">SBC SWe</span></span>          | <span data-ttu-id="db5de-153">8,2</span><span class="sxs-lookup"><span data-stu-id="db5de-153">8.2</span></span>  |
| [<span data-ttu-id="db5de-154">Bordo SBC della barra multifunzione</span><span class="sxs-lookup"><span data-stu-id="db5de-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="db5de-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="db5de-155">SBC SWe Lite</span></span> | <span data-ttu-id="db5de-156">8.1.5 (Build 239)</span><span class="sxs-lookup"><span data-stu-id="db5de-156">8.1.5 (build 239)</span></span> |
| [<span data-ttu-id="db5de-157">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="db5de-157">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="db5de-158">anynode</span><span class="sxs-lookup"><span data-stu-id="db5de-158">anynode</span></span>          | <span data-ttu-id="db5de-159">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="db5de-159">4.0.1+</span></span> |
| [<span data-ttu-id="db5de-160">Oracle</span><span class="sxs-lookup"><span data-stu-id="db5de-160">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="db5de-161">AP 1100</span><span class="sxs-lookup"><span data-stu-id="db5de-161">AP 1100</span></span> | <span data-ttu-id="db5de-162">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="db5de-162">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="db5de-163">AP 3900</span><span class="sxs-lookup"><span data-stu-id="db5de-163">AP 3900</span></span> | <span data-ttu-id="db5de-164">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="db5de-164">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="db5de-165">AP 4600</span><span class="sxs-lookup"><span data-stu-id="db5de-165">AP 4600</span></span> | <span data-ttu-id="db5de-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="db5de-166">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="db5de-167">AP 6300</span><span class="sxs-lookup"><span data-stu-id="db5de-167">AP 6300</span></span> | <span data-ttu-id="db5de-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="db5de-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="db5de-169">AP 6350</span><span class="sxs-lookup"><span data-stu-id="db5de-169">AP 6350</span></span> | <span data-ttu-id="db5de-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="db5de-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="db5de-171">VME</span><span class="sxs-lookup"><span data-stu-id="db5de-171">VME</span></span>     | <span data-ttu-id="db5de-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="db5de-172">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="db5de-173">Gestire indirizzi IP attendibili esterni</span><span class="sxs-lookup"><span data-stu-id="db5de-173">Manage external trusted IP addresses</span></span>

<span data-ttu-id="db5de-174">Gli IPs attendibili esterni sono gli IPs esterni Internet della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="db5de-174">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="db5de-175">Questi IP sono gli indirizzi IP usati dai client Microsoft teams quando si connettono a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="db5de-175">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="db5de-176">È necessario aggiungere questi IP esterni per ogni sito in cui sono presenti utenti che usano l'ottimizzazione media locale.</span><span class="sxs-lookup"><span data-stu-id="db5de-176">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="db5de-177">Per aggiungere gli indirizzi IP pubblici per ogni sito, usare il cmdlet New-CsTenantTrustedIPAddress.</span><span class="sxs-lookup"><span data-stu-id="db5de-177">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="db5de-178">Puoi definire un numero illimitato di indirizzi IP attendibili per un tenant.</span><span class="sxs-lookup"><span data-stu-id="db5de-178">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="db5de-179">Se gli IPs esterni visti da Microsoft 365 sono sia indirizzi IPv4 che IPv6, è necessario aggiungere entrambi i tipi di indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="db5de-179">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="db5de-180">Per IPv4, USA Mask 32.</span><span class="sxs-lookup"><span data-stu-id="db5de-180">For IPv4, use mask 32.</span></span> <span data-ttu-id="db5de-181">Per IPv6, USA mask 128.</span><span class="sxs-lookup"><span data-stu-id="db5de-181">For IPv6, use mask 128.</span></span> <span data-ttu-id="db5de-182">È possibile aggiungere sia singoli indirizzi IP esterni che subnet IP esterni specificando diversi MaskBits nel cmdlet.</span><span class="sxs-lookup"><span data-stu-id="db5de-182">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="db5de-183">Esempio di aggiunta di indirizzi IP attendibili.</span><span class="sxs-lookup"><span data-stu-id="db5de-183">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="db5de-184">Definire la topologia di rete</span><span class="sxs-lookup"><span data-stu-id="db5de-184">Define the network topology</span></span>

<span data-ttu-id="db5de-185">Questa sezione descrive come definire le aree di rete, i siti di rete e le subnet di rete per la topologia di rete.</span><span class="sxs-lookup"><span data-stu-id="db5de-185">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="db5de-186">Tutti i parametri sono maiuscole/minuscole, quindi devi assicurarti di usare lo stesso caso usato durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="db5de-186">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="db5de-187">Ad esempio, i valori di GatewaySiteID "Vietnam" e "Vietnam" verranno trattati come siti diversi.</span><span class="sxs-lookup"><span data-stu-id="db5de-187">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="db5de-188">Definire le aree di rete</span><span class="sxs-lookup"><span data-stu-id="db5de-188">Define network regions</span></span>

<span data-ttu-id="db5de-189">Per definire le aree di rete, usare il cmdlet New-CsTenantNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="db5de-189">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="db5de-190">Il parametro RegionID è un nome logico che rappresenta la geografia dell'area geografica e non ha dipendenze o restrizioni.</span><span class="sxs-lookup"><span data-stu-id="db5de-190">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="db5de-191">Il <site ID> parametro CentralSite è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="db5de-191">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="db5de-192">L'esempio seguente crea un'area di rete denominata APAC:</span><span class="sxs-lookup"><span data-stu-id="db5de-192">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="db5de-193">Definire i siti di rete</span><span class="sxs-lookup"><span data-stu-id="db5de-193">Define network sites</span></span>

<span data-ttu-id="db5de-194">Per definire i siti di rete, usare il cmdlet New-CsTenantNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="db5de-194">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="db5de-195">Ogni sito di rete deve essere associato a un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="db5de-195">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="db5de-196">L'esempio seguente crea tre nuovi siti di rete, Vietnam, Indonesia e Singapore nell'area APAC:</span><span class="sxs-lookup"><span data-stu-id="db5de-196">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="db5de-197">Definire le subnet di rete</span><span class="sxs-lookup"><span data-stu-id="db5de-197">Define network subnets</span></span>

<span data-ttu-id="db5de-198">Per definire le subnet di rete e associarle ai siti di rete, usare il cmdlet New-CsTenantNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="db5de-198">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="db5de-199">Ogni subnet di rete può essere associata a un solo sito.</span><span class="sxs-lookup"><span data-stu-id="db5de-199">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="db5de-200">L'esempio seguente definisce tre subnet di rete e le associa ai tre siti di rete: Vietnam, Indonesia e Singapore:</span><span class="sxs-lookup"><span data-stu-id="db5de-200">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="db5de-201">Definire la topologia di rete virtuale</span><span class="sxs-lookup"><span data-stu-id="db5de-201">Define the virtual network topology</span></span> 

<span data-ttu-id="db5de-202">Prima di tutto, l'amministratore del tenant crea una nuova configurazione SBC per ogni SBC pertinente usando il cmdlet New-CsOnlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="db5de-202">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="db5de-203">L'amministratore del tenant definisce la topologia di rete virtuale specificando i siti di rete per gli oggetti gateway PSTN usando il cmdlet Set-CsOnlinePSTNGateway:</span><span class="sxs-lookup"><span data-stu-id="db5de-203">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="db5de-204">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="db5de-204">Note the following:</span></span> 
   - <span data-ttu-id="db5de-205">Se il cliente ha un singolo SBC, il parametro-ProxySBC deve essere obbligatorio $null o il valore FQDN di SBC (SBC centrale con lo scenario Trunks centralizzato).</span><span class="sxs-lookup"><span data-stu-id="db5de-205">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="db5de-206">Il parametro-MediaBypass deve essere impostato su $true per supportare l'ottimizzazione dei contenuti multimediali locali.</span><span class="sxs-lookup"><span data-stu-id="db5de-206">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="db5de-207">Se SBC non ha il set di parametri-BypassMode, le intestazioni X-MS non verranno inviate.</span><span class="sxs-lookup"><span data-stu-id="db5de-207">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="db5de-208">Tutti i parametri sono maiuscole/minuscole, quindi devi assicurarti di usare lo stesso caso usato durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="db5de-208">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="db5de-209">Ad esempio, i valori di GatewaySiteID "Vietnam" e "Vietnam" verranno trattati come siti diversi.</span><span class="sxs-lookup"><span data-stu-id="db5de-209">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="db5de-210">L'esempio seguente aggiunge tre SBCs ai siti di rete Vietnam, Indonesia e Singapore nell'area APAC con la modalità Ignora sempre:</span><span class="sxs-lookup"><span data-stu-id="db5de-210">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="db5de-211">Nota: per garantire che le operazioni ininterrotte quando vengono configurate l'ottimizzazione media locale e il routing basato sulla posizione (LBR), SBCs downstream debba essere abilitato per LBR impostando il parametro GatewaySiteLbrEnabled su $true per ogni SBC downstream.</span><span class="sxs-lookup"><span data-stu-id="db5de-211">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="db5de-212">Questa impostazione non è obbligatoria per il proxy SBC.</span><span class="sxs-lookup"><span data-stu-id="db5de-212">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="db5de-213">In base alle informazioni fornite sopra, il routing diretto includerà tre intestazioni SIP proprietarie per SIP invita e invita nuovamente come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="db5de-213">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="db5de-214">Intestazioni X-MS introdotte in routing diretto su invita e invita nuovamente se BypassMode è definito:</span><span class="sxs-lookup"><span data-stu-id="db5de-214">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="db5de-215">Nome intestazione</span><span class="sxs-lookup"><span data-stu-id="db5de-215">Header name</span></span> | <span data-ttu-id="db5de-216">Valori</span><span class="sxs-lookup"><span data-stu-id="db5de-216">Values</span></span> | <span data-ttu-id="db5de-217">Commenti</span><span class="sxs-lookup"><span data-stu-id="db5de-217">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="db5de-218">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="db5de-218">X-MS-UserLocation</span></span> | <span data-ttu-id="db5de-219">interno/esterno</span><span class="sxs-lookup"><span data-stu-id="db5de-219">internal/external</span></span> | <span data-ttu-id="db5de-220">Indica se l'utente è interno o esterno</span><span class="sxs-lookup"><span data-stu-id="db5de-220">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="db5de-221">Request-URI invita SIP: + 84439263000@VNsbc.contoso.com SIP/2,0</span><span class="sxs-lookup"><span data-stu-id="db5de-221">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="db5de-222">FQDN DI SBC</span><span class="sxs-lookup"><span data-stu-id="db5de-222">SBC FQDN</span></span> | <span data-ttu-id="db5de-223">Il nome di dominio completo che è destinato alla chiamata anche se SBC non è connesso direttamente al routing diretto</span><span class="sxs-lookup"><span data-stu-id="db5de-223">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="db5de-224">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="db5de-224">X-MS-MediaPath</span></span> | <span data-ttu-id="db5de-225">Esempio: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db5de-225">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="db5de-226">Ordine di SBCs che deve essere usato per il percorso multimediale tra l'utente e il SBC di destinazione.</span><span class="sxs-lookup"><span data-stu-id="db5de-226">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="db5de-227">Il SBC finale è sempre l'ultima volta</span><span class="sxs-lookup"><span data-stu-id="db5de-227">The final SBC is always last</span></span> |
| <span data-ttu-id="db5de-228">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="db5de-228">X-MS-UserSite</span></span> | <span data-ttu-id="db5de-229">usersiteID</span><span class="sxs-lookup"><span data-stu-id="db5de-229">usersiteID</span></span> | <span data-ttu-id="db5de-230">Stringa definita dall'amministratore del tenant</span><span class="sxs-lookup"><span data-stu-id="db5de-230">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="db5de-231">Flussi delle chiamate</span><span class="sxs-lookup"><span data-stu-id="db5de-231">Call flows</span></span> 

<span data-ttu-id="db5de-232">Di seguito sono illustrati i flussi delle chiamate per due modalità:</span><span class="sxs-lookup"><span data-stu-id="db5de-232">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="db5de-233">Ignorare sempre</span><span class="sxs-lookup"><span data-stu-id="db5de-233">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="db5de-234">Solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="db5de-234">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="db5de-235">Modalità di bypass sempre</span><span class="sxs-lookup"><span data-stu-id="db5de-235">Always Bypass mode</span></span>

<span data-ttu-id="db5de-236">La modalità Ignora sempre è l'opzione più semplice da configurare.</span><span class="sxs-lookup"><span data-stu-id="db5de-236">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="db5de-237">L'amministratore del tenant può configurare un singolo sito per tutti gli utenti e SBCs se tutti i SBCs sono raggiungibili da qualsiasi sito.</span><span class="sxs-lookup"><span data-stu-id="db5de-237">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="db5de-238">Gli esempi mostrano sempre la modalità di bypass per gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="db5de-238">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="db5de-239">Le chiamate in uscita e l'utente si trova nella stessa posizione di SBC</span><span class="sxs-lookup"><span data-stu-id="db5de-239">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="db5de-240">Le chiamate in ingresso e l'utente si trova nella stessa posizione di SBC</span><span class="sxs-lookup"><span data-stu-id="db5de-240">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="db5de-241">Chiamate in uscita e l'utente è esterno</span><span class="sxs-lookup"><span data-stu-id="db5de-241">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="db5de-242">Chiamate in ingresso e l'utente è esterno</span><span class="sxs-lookup"><span data-stu-id="db5de-242">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="db5de-243">La tabella seguente mostra l'FQDN e gli indirizzi IP usati negli esempi:</span><span class="sxs-lookup"><span data-stu-id="db5de-243">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="db5de-244">FQDN</span><span class="sxs-lookup"><span data-stu-id="db5de-244">FQDN</span></span> | <span data-ttu-id="db5de-245">Indirizzo IP esterno SBC</span><span class="sxs-lookup"><span data-stu-id="db5de-245">SBC external IP address</span></span> | <span data-ttu-id="db5de-246">Indirizzo IP interno SBC</span><span class="sxs-lookup"><span data-stu-id="db5de-246">SBC internal IP Address</span></span> | <span data-ttu-id="db5de-247">Subnet interna</span><span class="sxs-lookup"><span data-stu-id="db5de-247">Internal subnet</span></span> | <span data-ttu-id="db5de-248">Posizione</span><span class="sxs-lookup"><span data-stu-id="db5de-248">Location</span></span> | <span data-ttu-id="db5de-249">NAT esterno (IP attendibile)</span><span class="sxs-lookup"><span data-stu-id="db5de-249">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="db5de-250">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db5de-250">VNsbc.contoso.com</span></span> | <span data-ttu-id="db5de-251">Nessuno</span><span class="sxs-lookup"><span data-stu-id="db5de-251">None</span></span> | <span data-ttu-id="db5de-252">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="db5de-252">192.168.1.5</span></span> | <span data-ttu-id="db5de-253">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="db5de-253">192.168.1.0/24</span></span> | <span data-ttu-id="db5de-254">Vietnam</span><span class="sxs-lookup"><span data-stu-id="db5de-254">Vietnam</span></span> | <span data-ttu-id="db5de-255">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="db5de-255">172.16.240.110</span></span> |
| <span data-ttu-id="db5de-256">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db5de-256">IDsbc.contoso.com</span></span> | <span data-ttu-id="db5de-257">Nessuno</span><span class="sxs-lookup"><span data-stu-id="db5de-257">None</span></span> | <span data-ttu-id="db5de-258">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="db5de-258">192.168.2.5</span></span> | <span data-ttu-id="db5de-259">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="db5de-259">192.168.2.0/24</span></span> | <span data-ttu-id="db5de-260">Indonesia</span><span class="sxs-lookup"><span data-stu-id="db5de-260">Indonesia</span></span> | <span data-ttu-id="db5de-261">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="db5de-261">172.16.240.120</span></span> |
| <span data-ttu-id="db5de-262">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db5de-262">proxysbc.contoso.com</span></span> | <span data-ttu-id="db5de-263">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="db5de-263">172.16.240.133</span></span> | <span data-ttu-id="db5de-264">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="db5de-264">192.168.3.5</span></span> | <span data-ttu-id="db5de-265">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="db5de-265">192.168.3.0/24</span></span> | <span data-ttu-id="db5de-266">Singapore</span><span class="sxs-lookup"><span data-stu-id="db5de-266">Singapore</span></span> | <span data-ttu-id="db5de-267">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="db5de-267">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="db5de-268">Le chiamate in uscita e l'utente si trova nella stessa posizione dell'SBC con bypass sempre</span><span class="sxs-lookup"><span data-stu-id="db5de-268">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="db5de-269">Modalità</span><span class="sxs-lookup"><span data-stu-id="db5de-269">Mode</span></span> |    <span data-ttu-id="db5de-270">Utente</span><span class="sxs-lookup"><span data-stu-id="db5de-270">User</span></span> |  <span data-ttu-id="db5de-271">Posizione</span><span class="sxs-lookup"><span data-stu-id="db5de-271">Location</span></span> |  <span data-ttu-id="db5de-272">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="db5de-272">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="db5de-273">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="db5de-273">AlwaysBypass</span></span> |    <span data-ttu-id="db5de-274">Interno</span><span class="sxs-lookup"><span data-stu-id="db5de-274">Internal</span></span> |  <span data-ttu-id="db5de-275">Lo stesso sito di SBC</span><span class="sxs-lookup"><span data-stu-id="db5de-275">The same site as SBC</span></span> |  <span data-ttu-id="db5de-276">Outbound</span><span class="sxs-lookup"><span data-stu-id="db5de-276">Outbound</span></span> |

<span data-ttu-id="db5de-277">La tabella seguente mostra la configurazione e l'azione degli utenti finali:</span><span class="sxs-lookup"><span data-stu-id="db5de-277">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="db5de-278">Posizione fisica dell'utente</span><span class="sxs-lookup"><span data-stu-id="db5de-278">User physical location</span></span>| <span data-ttu-id="db5de-279">L'utente effettua o riceve una chiamata a/da numero</span><span class="sxs-lookup"><span data-stu-id="db5de-279">User makes or receives a call to/from number</span></span> | <span data-ttu-id="db5de-280">Numero di telefono dell'utente</span><span class="sxs-lookup"><span data-stu-id="db5de-280">User phone number</span></span>  | <span data-ttu-id="db5de-281">Criteri di routing vocale online</span><span class="sxs-lookup"><span data-stu-id="db5de-281">Online Voice Routing Policy</span></span> | <span data-ttu-id="db5de-282">Modalità configurata per SBC</span><span class="sxs-lookup"><span data-stu-id="db5de-282">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="db5de-283">Vietnam</span><span class="sxs-lookup"><span data-stu-id="db5de-283">Vietnam</span></span> | <span data-ttu-id="db5de-284">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="db5de-284">+84 4 3926 3000</span></span> | <span data-ttu-id="db5de-285">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="db5de-285">+84 4 5555 5555</span></span>   | <span data-ttu-id="db5de-286">Priorità 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db5de-286">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="db5de-287">Priorità 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db5de-287">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="db5de-288">VNsbc.contoso.com-ignora sempre</span><span class="sxs-lookup"><span data-stu-id="db5de-288">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="db5de-289">proxysbc.contoso.com-ignora sempre</span><span class="sxs-lookup"><span data-stu-id="db5de-289">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="db5de-290">Il diagramma seguente mostra la scala SIP per una chiamata in uscita con la modalità di bypass sempre e l'utente nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="db5de-290">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="db5de-291">![Diagramma che mostra le chiamate in uscita](media/direct-routing-media-op-10.png "Chiamate in uscita")</span><span class="sxs-lookup"><span data-stu-id="db5de-291">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="db5de-292">La tabella seguente mostra le intestazioni X-MS inviate tramite routing diretto:</span><span class="sxs-lookup"><span data-stu-id="db5de-292">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="db5de-293">Parametro</span><span class="sxs-lookup"><span data-stu-id="db5de-293">Parameter</span></span> | <span data-ttu-id="db5de-294">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="db5de-294">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="db5de-295">Invitare + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db5de-295">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="db5de-296">Il nome di dominio completo di destinazione dell'oggetto SBC definito nei criteri di routing vocale online viene inviato nell'URI della richiesta</span><span class="sxs-lookup"><span data-stu-id="db5de-296">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="db5de-297">X-MS-UserLocation: Internal</span><span class="sxs-lookup"><span data-stu-id="db5de-297">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="db5de-298">Il campo indica che l'utente si trova all'interno della rete aziendale</span><span class="sxs-lookup"><span data-stu-id="db5de-298">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="db5de-299">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db5de-299">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="db5de-300">Specifica il SBC che deve essere attraversato dal client al SBC di destinazione.</span><span class="sxs-lookup"><span data-stu-id="db5de-300">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="db5de-301">In questo caso, come abbiamo sempre bypassare, e il client è interno il nome di destinazione inviato come unico nome nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="db5de-301">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="db5de-302">X-MS-UserSite: Vietnam</span><span class="sxs-lookup"><span data-stu-id="db5de-302">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="db5de-303">Campo indicato nel sito in cui si trova l'utente.</span><span class="sxs-lookup"><span data-stu-id="db5de-303">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="db5de-304">Le chiamate in ingresso e l'utente si trova nella stessa posizione dell'SBC con il bypass sempre</span><span class="sxs-lookup"><span data-stu-id="db5de-304">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="db5de-305">Modalità</span><span class="sxs-lookup"><span data-stu-id="db5de-305">Mode</span></span> |    <span data-ttu-id="db5de-306">Utente</span><span class="sxs-lookup"><span data-stu-id="db5de-306">User</span></span> |  <span data-ttu-id="db5de-307">Posizione</span><span class="sxs-lookup"><span data-stu-id="db5de-307">Location</span></span> |  <span data-ttu-id="db5de-308">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="db5de-308">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="db5de-309">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="db5de-309">AlwaysBypass</span></span> |    <span data-ttu-id="db5de-310">Interno</span><span class="sxs-lookup"><span data-stu-id="db5de-310">Internal</span></span> | <span data-ttu-id="db5de-311">Lo stesso sito di SBC</span><span class="sxs-lookup"><span data-stu-id="db5de-311">The same site as SBC</span></span> | <span data-ttu-id="db5de-312">In ingresso</span><span class="sxs-lookup"><span data-stu-id="db5de-312">Inbound</span></span> |


<span data-ttu-id="db5de-313">In una chiamata in ingresso, la posizione dell'utente è sconosciuta e il SBC deve indovinare dove si trova l'utente.</span><span class="sxs-lookup"><span data-stu-id="db5de-313">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="db5de-314">Se l'ipotesi non è corretta, sarà necessario un nuovo invito.</span><span class="sxs-lookup"><span data-stu-id="db5de-314">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="db5de-315">Questo caso presuppone che l'utente sia interno, che l'elemento multimediale possa fluire direttamente e che non siano necessarie altre azioni (re-INVITE).</span><span class="sxs-lookup"><span data-stu-id="db5de-315">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="db5de-316">Il SBC connesso al servizio di routing diretto riporta la posizione del SBC di origine fornendo campi di record-route e Contact.</span><span class="sxs-lookup"><span data-stu-id="db5de-316">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="db5de-317">In base a questi campi, il percorso del supporto viene calcolato tramite routing diretto.</span><span class="sxs-lookup"><span data-stu-id="db5de-317">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="db5de-318">Nota: dato che un utente può avere più endpoint, il supporto di 183 non è possibile.</span><span class="sxs-lookup"><span data-stu-id="db5de-318">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="db5de-319">Il routing diretto userà sempre 180 squillare in questo caso.</span><span class="sxs-lookup"><span data-stu-id="db5de-319">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="db5de-320">Il diagramma seguente mostra la scala SIP per la chiamata in ingresso con la modalità AlwaysBypass e l'utente si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="db5de-320">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="db5de-322">Chiamate in uscita e l'utente è esterno con l'esclusione sempre</span><span class="sxs-lookup"><span data-stu-id="db5de-322">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="db5de-323">Modalità</span><span class="sxs-lookup"><span data-stu-id="db5de-323">Mode</span></span> |    <span data-ttu-id="db5de-324">Utente</span><span class="sxs-lookup"><span data-stu-id="db5de-324">User</span></span> |  <span data-ttu-id="db5de-325">Sito</span><span class="sxs-lookup"><span data-stu-id="db5de-325">Site</span></span> |  <span data-ttu-id="db5de-326">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="db5de-326">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="db5de-327">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="db5de-327">AlwaysBypass</span></span> |  <span data-ttu-id="db5de-328">Esterno</span><span class="sxs-lookup"><span data-stu-id="db5de-328">External</span></span> |  <span data-ttu-id="db5de-329">N/D</span><span class="sxs-lookup"><span data-stu-id="db5de-329">N/A</span></span> | <span data-ttu-id="db5de-330">Outbound</span><span class="sxs-lookup"><span data-stu-id="db5de-330">Outbound</span></span> |


<span data-ttu-id="db5de-331">Il diagramma seguente mostra la scala SIP per una chiamata in uscita con la modalità AlwaysBypass e l'utente è esterno:</span><span class="sxs-lookup"><span data-stu-id="db5de-331">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-12.png)

<span data-ttu-id="db5de-333">La tabella seguente mostra le intestazioni X-MS inviate dal servizio di routing diretto:</span><span class="sxs-lookup"><span data-stu-id="db5de-333">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="db5de-334">Parametro</span><span class="sxs-lookup"><span data-stu-id="db5de-334">Parameter</span></span> |   <span data-ttu-id="db5de-335">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="db5de-335">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="db5de-336">Invitare + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db5de-336">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="db5de-337">Il nome di dominio completo di destinazione dell'SBC come definito nei criteri di routing vocale online viene inviato nell'URI della richiesta.</span><span class="sxs-lookup"><span data-stu-id="db5de-337">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="db5de-338">X-MS-UserLocation: esterno</span><span class="sxs-lookup"><span data-stu-id="db5de-338">X-MS-UserLocation: external</span></span> | <span data-ttu-id="db5de-339">Il campo indica che l'utente si trova all'esterno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="db5de-339">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="db5de-340">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db5de-340">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="db5de-341">Specifica il SBC che deve essere attraversato dal client al SBC di destinazione.</span><span class="sxs-lookup"><span data-stu-id="db5de-341">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="db5de-342">In questo caso, come abbiamo sempre bypassare, e il client è esterno.</span><span class="sxs-lookup"><span data-stu-id="db5de-342">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="db5de-343">Chiamate in ingresso e l'utente è esterno con il bypass sempre</span><span class="sxs-lookup"><span data-stu-id="db5de-343">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="db5de-344">Modalità</span><span class="sxs-lookup"><span data-stu-id="db5de-344">Mode</span></span> | <span data-ttu-id="db5de-345">Utente</span><span class="sxs-lookup"><span data-stu-id="db5de-345">User</span></span> | <span data-ttu-id="db5de-346">Sito</span><span class="sxs-lookup"><span data-stu-id="db5de-346">Site</span></span> |  <span data-ttu-id="db5de-347">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="db5de-347">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="db5de-348">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="db5de-348">AlwaysBypass</span></span> |  <span data-ttu-id="db5de-349">Esterno</span><span class="sxs-lookup"><span data-stu-id="db5de-349">External</span></span> |  <span data-ttu-id="db5de-350">N/D</span><span class="sxs-lookup"><span data-stu-id="db5de-350">N/A</span></span> |   <span data-ttu-id="db5de-351">In ingresso</span><span class="sxs-lookup"><span data-stu-id="db5de-351">Inbound</span></span> |

<span data-ttu-id="db5de-352">Per una chiamata in ingresso, il SBC connesso al routing diretto deve inviare un re-invite (per impostazione predefinita, i candidati multimediali locali sono sempre offerti) se la posizione dell'utente è esterna.</span><span class="sxs-lookup"><span data-stu-id="db5de-352">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="db5de-353">L'X-MediaPath viene calcolato in base a record-route e all'utente SBC specificato.</span><span class="sxs-lookup"><span data-stu-id="db5de-353">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="db5de-354">Il diagramma seguente mostra la scala SIP per una chiamata in ingresso con la modalità AlwaysBypass e l'utente è esterno.</span><span class="sxs-lookup"><span data-stu-id="db5de-354">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="db5de-356">Solo per la modalità utenti locali</span><span class="sxs-lookup"><span data-stu-id="db5de-356">Only for local users mode</span></span>

<span data-ttu-id="db5de-357">I candidati multimediali locali del SBC di destinazione verranno offerti solo se un utente si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="db5de-357">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="db5de-358">In tutti gli altri casi, il flusso multimediale verrà eseguito attraverso un IP interno o esterno del SBC proxy.</span><span class="sxs-lookup"><span data-stu-id="db5de-358">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="db5de-359">Vengono descritti gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="db5de-359">The following scenarios are described:</span></span>

- [<span data-ttu-id="db5de-360">Le chiamate in uscita e l'utente si trova nella stessa posizione di SBC</span><span class="sxs-lookup"><span data-stu-id="db5de-360">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="db5de-361">Le chiamate in ingresso e l'utente si trova nella stessa posizione di SBC</span><span class="sxs-lookup"><span data-stu-id="db5de-361">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="db5de-362">L'utente non si trova nella stessa posizione di SBC, ma nella rete aziendale</span><span class="sxs-lookup"><span data-stu-id="db5de-362">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="db5de-363">Le chiamate in ingresso e l'utente sono interne, ma non si trova nella stessa posizione di SBC</span><span class="sxs-lookup"><span data-stu-id="db5de-363">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="db5de-364">La tabella seguente mostra la configurazione e l'azione degli utenti finali:</span><span class="sxs-lookup"><span data-stu-id="db5de-364">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="db5de-365">Posizione fisica dell'utente</span><span class="sxs-lookup"><span data-stu-id="db5de-365">User physical location</span></span> |  <span data-ttu-id="db5de-366">L'utente effettua o riceve una chiamata a/da numero</span><span class="sxs-lookup"><span data-stu-id="db5de-366">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="db5de-367">Numero di telefono dell'utente</span><span class="sxs-lookup"><span data-stu-id="db5de-367">User phone number</span></span> | <span data-ttu-id="db5de-368">Criteri di routing vocale online</span><span class="sxs-lookup"><span data-stu-id="db5de-368">Online Voice Routing Policy</span></span> |   <span data-ttu-id="db5de-369">Modalità configurata per SBC</span><span class="sxs-lookup"><span data-stu-id="db5de-369">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="db5de-370">Vietnam</span><span class="sxs-lookup"><span data-stu-id="db5de-370">Vietnam</span></span> | <span data-ttu-id="db5de-371">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="db5de-371">+84 4 3926  3000</span></span> |  <span data-ttu-id="db5de-372">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="db5de-372">+84 4 5555 5555</span></span> | <span data-ttu-id="db5de-373">Priorità 1: ^ \+ 84 (\d {9} ) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db5de-373">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="db5de-374">Priorità 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="db5de-374">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="db5de-375">VNsbc.contoso.com-OnlyForLocalUsers Proxysbc.contoso.com-ignora sempre</span><span class="sxs-lookup"><span data-stu-id="db5de-375">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="db5de-376">Le chiamate in uscita e l'utente si trova nella stessa posizione del SBC con solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="db5de-376">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="db5de-377">Modalità</span><span class="sxs-lookup"><span data-stu-id="db5de-377">Mode</span></span> | <span data-ttu-id="db5de-378">Utente</span><span class="sxs-lookup"><span data-stu-id="db5de-378">User</span></span> | <span data-ttu-id="db5de-379">Sito</span><span class="sxs-lookup"><span data-stu-id="db5de-379">Site</span></span> | <span data-ttu-id="db5de-380">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="db5de-380">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="db5de-381">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="db5de-381">OnlyForLocalUsers</span></span> |   <span data-ttu-id="db5de-382">Interno</span><span class="sxs-lookup"><span data-stu-id="db5de-382">Internal</span></span> |<span data-ttu-id="db5de-383">Uguale a SBC</span><span class="sxs-lookup"><span data-stu-id="db5de-383">Same as SBC</span></span>   | <span data-ttu-id="db5de-384">Outbound</span><span class="sxs-lookup"><span data-stu-id="db5de-384">Outbound</span></span> |

<span data-ttu-id="db5de-385">Il diagramma seguente mostra una chiamata in uscita con la modalità OnlyForLocalUsers e l'utente si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="db5de-385">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="db5de-386">Si tratta dello stesso flusso visualizzato nelle [chiamate in uscita quando l'utente si trova nella stessa posizione di SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="db5de-386">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="db5de-388">Le chiamate in ingresso e l'utente si trova nella stessa posizione del SBC con solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="db5de-388">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="db5de-389">Modalità</span><span class="sxs-lookup"><span data-stu-id="db5de-389">Mode</span></span> | <span data-ttu-id="db5de-390">Utente</span><span class="sxs-lookup"><span data-stu-id="db5de-390">User</span></span> | <span data-ttu-id="db5de-391">Sito</span><span class="sxs-lookup"><span data-stu-id="db5de-391">Site</span></span> | <span data-ttu-id="db5de-392">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="db5de-392">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="db5de-393">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="db5de-393">OnlyForLocalUsers</span></span> |   <span data-ttu-id="db5de-394">Interno</span><span class="sxs-lookup"><span data-stu-id="db5de-394">Internal</span></span> | <span data-ttu-id="db5de-395">Uguale a SBC</span><span class="sxs-lookup"><span data-stu-id="db5de-395">Same as SBC</span></span> | <span data-ttu-id="db5de-396">In ingresso</span><span class="sxs-lookup"><span data-stu-id="db5de-396">Inbound</span></span> |

<span data-ttu-id="db5de-397">Il diagramma seguente mostra una chiamata in ingresso con la modalità OnlyForLocalUsers e l'utente si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="db5de-397">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="db5de-398">Si tratta dello stesso flusso illustrato nelle [chiamate in ingresso quando l'utente si trova nella stessa posizione di SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="db5de-398">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="db5de-400">L'utente non si trova nella stessa posizione di SBC, ma è nella rete aziendale solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="db5de-400">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="db5de-401">Modalità</span><span class="sxs-lookup"><span data-stu-id="db5de-401">Mode</span></span> | <span data-ttu-id="db5de-402">Utente</span><span class="sxs-lookup"><span data-stu-id="db5de-402">User</span></span> | <span data-ttu-id="db5de-403">Sito</span><span class="sxs-lookup"><span data-stu-id="db5de-403">Site</span></span> |<span data-ttu-id="db5de-404">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="db5de-404">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="db5de-405">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="db5de-405">OnlyForLocalUsers</span></span>  | <span data-ttu-id="db5de-406">Interno</span><span class="sxs-lookup"><span data-stu-id="db5de-406">Internal</span></span> |   <span data-ttu-id="db5de-407">Diverso da SBC</span><span class="sxs-lookup"><span data-stu-id="db5de-407">Different from SBC</span></span> | <span data-ttu-id="db5de-408">Outbound</span><span class="sxs-lookup"><span data-stu-id="db5de-408">Outbound</span></span> |

<span data-ttu-id="db5de-409">Il routing diretto calcola X-MediaPath in base alla posizione segnalata dell'utente e alla modalità configurata in SBC.</span><span class="sxs-lookup"><span data-stu-id="db5de-409">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="db5de-410">Il diagramma seguente mostra una chiamata in uscita con la modalità OnlyForLocalUsers e un utente interno che non si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="db5de-410">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="db5de-412">Chiamata in ingresso e l'utente è interno, ma non è nella stessa posizione dell'SBC con solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="db5de-412">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="db5de-413">Modalità</span><span class="sxs-lookup"><span data-stu-id="db5de-413">Mode</span></span> |    <span data-ttu-id="db5de-414">Utente</span><span class="sxs-lookup"><span data-stu-id="db5de-414">User</span></span> |  <span data-ttu-id="db5de-415">Sito</span><span class="sxs-lookup"><span data-stu-id="db5de-415">Site</span></span> |  <span data-ttu-id="db5de-416">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="db5de-416">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="db5de-417">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="db5de-417">OnlyForLocalUsers</span></span> | <span data-ttu-id="db5de-418">Interno</span><span class="sxs-lookup"><span data-stu-id="db5de-418">Internal</span></span> |    <span data-ttu-id="db5de-419">Diverso da SBC</span><span class="sxs-lookup"><span data-stu-id="db5de-419">Different from SBC</span></span> |    <span data-ttu-id="db5de-420">In ingresso</span><span class="sxs-lookup"><span data-stu-id="db5de-420">Inbound</span></span> |

<span data-ttu-id="db5de-421">Il diagramma seguente mostra una chiamata in ingresso con la modalità OnlyForLocalUsers e un utente interno che non si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="db5de-421">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-17.png)









