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
ms.openlocfilehash: 3097f97a856dc4e947281847c65669c23c73a408
ms.sourcegitcommit: 25e70de7c943e22fe6ac6e8d6b4353ca68f81f83
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/06/2020
ms.locfileid: "43158108"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="8fc3c-103">Configurare l'ottimizzazione multimediale locale per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="8fc3c-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="8fc3c-104">La configurazione per l'ottimizzazione media locale si basa sulle impostazioni di rete comuni ad altre caratteristiche vocali del cloud, ad esempio routing basato sulla posizione e chiamate di emergenza dinamiche.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="8fc3c-105">Per altre informazioni sulle aree di rete, i siti di rete, le subnet di rete e gli indirizzi IP attendibili, vedere [impostazioni di rete per le funzionalità di cloud Voice](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="8fc3c-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="8fc3c-106">Prima di configurare l'ottimizzazione multimediale locale, vedere [ottimizzazione dei contenuti multimediali locali per il routing diretto](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="8fc3c-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="8fc3c-107">Per configurare l'ottimizzazione multimediale locale, sono necessarie le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="8fc3c-108">Puoi usare l'interfaccia di amministrazione di teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="8fc3c-109">Per informazioni dettagliate, vedere [gestire la topologia di rete](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="8fc3c-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="8fc3c-110">Configurare l'utente e i siti SBC (come descritto in questo articolo).</span><span class="sxs-lookup"><span data-stu-id="8fc3c-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="8fc3c-111">Configurare la SBCs for local Media Optimization (in base alla specifica del fornitore SBC).</span><span class="sxs-lookup"><span data-stu-id="8fc3c-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="8fc3c-112">Il diagramma seguente mostra la configurazione della rete usata negli esempi in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="8fc3c-113">![Diagramma che mostra la configurazione della rete per gli esempi](media/direct-routing-media-op-9.png "Configurazione di rete per gli esempi")</span><span class="sxs-lookup"><span data-stu-id="8fc3c-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="8fc3c-114">Configurare l'utente e i siti SBC</span><span class="sxs-lookup"><span data-stu-id="8fc3c-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="8fc3c-115">Per configurare l'utente e i siti SBC, sarà necessario:</span><span class="sxs-lookup"><span data-stu-id="8fc3c-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="8fc3c-116">[Gestire indirizzi IP attendibili esterni](#manage-external-trusted-ip-addresses).</span><span class="sxs-lookup"><span data-stu-id="8fc3c-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="8fc3c-117">[Definire la topologia di rete](#define-the-network-topology) configurando le aree di rete, i siti di rete e le subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="8fc3c-118">[Definire la topologia di rete virtuale](#define-the-virtual-network-topology) assegnando SBC (s) ai siti con le modalità pertinenti e i valori del proxy SBC.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="8fc3c-119">Configurare SBC per l'ottimizzazione di elementi multimediali locali in base alla specifica del fornitore SBC</span><span class="sxs-lookup"><span data-stu-id="8fc3c-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="8fc3c-120">Questo articolo descrive la configurazione per i componenti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="8fc3c-121">Per informazioni sulla configurazione di SBC, vedere il fornitore di SBC documentazione.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-121">For information on SBC configuration, see your SBC vendor documenation.</span></span>

<span data-ttu-id="8fc3c-122">L'ottimizzazione media locale è supportata dai seguenti fornitori di SBC:</span><span class="sxs-lookup"><span data-stu-id="8fc3c-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="8fc3c-123">Fornitore</span><span class="sxs-lookup"><span data-stu-id="8fc3c-123">Vendor</span></span> | <span data-ttu-id="8fc3c-124">Prodotto</span><span class="sxs-lookup"><span data-stu-id="8fc3c-124">Product</span></span> |    <span data-ttu-id="8fc3c-125">Versione software</span><span class="sxs-lookup"><span data-stu-id="8fc3c-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="8fc3c-126">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="8fc3c-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="8fc3c-127">SBC 500 medium</span><span class="sxs-lookup"><span data-stu-id="8fc3c-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="8fc3c-128">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="8fc3c-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="8fc3c-129">SBC 800 Medium</span><span class="sxs-lookup"><span data-stu-id="8fc3c-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="8fc3c-130">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="8fc3c-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="8fc3c-131">SBC 2600 medium</span><span class="sxs-lookup"><span data-stu-id="8fc3c-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="8fc3c-132">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="8fc3c-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="8fc3c-133">SBC 4000 medium</span><span class="sxs-lookup"><span data-stu-id="8fc3c-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="8fc3c-134">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="8fc3c-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="8fc3c-135">SBC 1000B medium</span><span class="sxs-lookup"><span data-stu-id="8fc3c-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="8fc3c-136">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="8fc3c-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="8fc3c-137">SBC 9000 medium</span><span class="sxs-lookup"><span data-stu-id="8fc3c-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="8fc3c-138">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="8fc3c-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="8fc3c-139">SBC virtuale per edizioni medious</span><span class="sxs-lookup"><span data-stu-id="8fc3c-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="8fc3c-140">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="8fc3c-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="8fc3c-141">SBC Cloud Edition</span><span class="sxs-lookup"><span data-stu-id="8fc3c-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="8fc3c-142">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="8fc3c-142">7.20A.256</span></span> |
| [<span data-ttu-id="8fc3c-143">Core SBC della barra multifunzione</span><span class="sxs-lookup"><span data-stu-id="8fc3c-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="8fc3c-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="8fc3c-144">SBC 5110</span></span>         | <span data-ttu-id="8fc3c-145">8,2</span><span class="sxs-lookup"><span data-stu-id="8fc3c-145">8.2</span></span>  |
|            |  <span data-ttu-id="8fc3c-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="8fc3c-146">SBC 5210</span></span>         | <span data-ttu-id="8fc3c-147">8,2</span><span class="sxs-lookup"><span data-stu-id="8fc3c-147">8.2</span></span>  |
|            |  <span data-ttu-id="8fc3c-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="8fc3c-148">SBC 5400</span></span>         | <span data-ttu-id="8fc3c-149">8,2</span><span class="sxs-lookup"><span data-stu-id="8fc3c-149">8.2</span></span>  |
|            |  <span data-ttu-id="8fc3c-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="8fc3c-150">SBC 7000</span></span>         | <span data-ttu-id="8fc3c-151">8,2</span><span class="sxs-lookup"><span data-stu-id="8fc3c-151">8.2</span></span>  |
|            |  <span data-ttu-id="8fc3c-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="8fc3c-152">SBC SWe</span></span>          | <span data-ttu-id="8fc3c-153">8,2</span><span class="sxs-lookup"><span data-stu-id="8fc3c-153">8.2</span></span>  |
| [<span data-ttu-id="8fc3c-154">Bordo SBC della barra multifunzione</span><span class="sxs-lookup"><span data-stu-id="8fc3c-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Microsoft+Teams+Direct+Routing+-+On+Premises+Deployment)  |  <span data-ttu-id="8fc3c-155">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="8fc3c-155">SBC 1000</span></span>         | <span data-ttu-id="8fc3c-156">8.1.1, Build 527</span><span class="sxs-lookup"><span data-stu-id="8fc3c-156">8.1.1, build 527</span></span> |
|            |  <span data-ttu-id="8fc3c-157">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="8fc3c-157">SBC 2000</span></span>         | <span data-ttu-id="8fc3c-158">8.1.1, Build 527</span><span class="sxs-lookup"><span data-stu-id="8fc3c-158">8.1.1, build 527</span></span> |
|            |  <span data-ttu-id="8fc3c-159">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="8fc3c-159">SBC SWe Lite</span></span>     | <span data-ttu-id="8fc3c-160">8.1.0, build 222</span><span class="sxs-lookup"><span data-stu-id="8fc3c-160">8.1.0, build 222</span></span> |
| [<span data-ttu-id="8fc3c-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="8fc3c-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="8fc3c-162">anynode</span><span class="sxs-lookup"><span data-stu-id="8fc3c-162">anynode</span></span>          | <span data-ttu-id="8fc3c-163">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="8fc3c-163">4.0.1+</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="8fc3c-164">Gestire indirizzi IP attendibili esterni</span><span class="sxs-lookup"><span data-stu-id="8fc3c-164">Manage external trusted IP addresses</span></span>

<span data-ttu-id="8fc3c-165">Gli IPs attendibili esterni sono gli IPs esterni Internet della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-165">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="8fc3c-166">Questi IP sono gli indirizzi IP usati dai client Microsoft teams quando si connettono a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-166">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="8fc3c-167">È necessario aggiungere questi IP esterni per ogni sito in cui sono presenti utenti che usano l'ottimizzazione media locale.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-167">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="8fc3c-168">Per aggiungere gli indirizzi IP pubblici per ogni sito, usare il cmdlet New-CsTenantTrustedIPAddress.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-168">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="8fc3c-169">Puoi definire un numero illimitato di indirizzi IP attendibili per un tenant.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-169">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="8fc3c-170">Se gli IPs esterni visti da Microsoft 365 sono sia indirizzi IPv4 che IPv6, è necessario aggiungere entrambi i tipi di indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-170">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="8fc3c-171">Per IPv4, USA Mask 32.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-171">For IPv4, use mask 32.</span></span> <span data-ttu-id="8fc3c-172">Per IPv6, USA mask 128.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-172">For IPv6, use mask 128.</span></span> <span data-ttu-id="8fc3c-173">È possibile aggiungere sia singoli indirizzi IP esterni che subnet IP esterni specificando diversi MaskBits nel cmdlet.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-173">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="8fc3c-174">Esempio di aggiunta di indirizzi IP attendibili.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-174">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="8fc3c-175">Definire la topologia di rete</span><span class="sxs-lookup"><span data-stu-id="8fc3c-175">Define the network topology</span></span>

<span data-ttu-id="8fc3c-176">Questa sezione descrive come definire le aree di rete, i siti di rete e le subnet di rete per la topologia di rete.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-176">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="8fc3c-177">Tutti i parametri sono maiuscole/minuscole, quindi devi assicurarti di usare lo stesso caso usato durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-177">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="8fc3c-178">Ad esempio, i valori di GatewaySiteID "Vietnam" e "Vietnam" verranno trattati come siti diversi.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-178">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="8fc3c-179">Definire le aree di rete</span><span class="sxs-lookup"><span data-stu-id="8fc3c-179">Define network regions</span></span>

<span data-ttu-id="8fc3c-180">Per definire le aree di rete, usare il cmdlet New-CsTenantNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-180">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="8fc3c-181">Il parametro RegionID è un nome logico che rappresenta la geografia dell'area geografica e non ha dipendenze o restrizioni.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-181">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="8fc3c-182">Il parametro <site ID> CentralSite è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-182">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="8fc3c-183">L'esempio seguente crea un'area di rete denominata APAC:</span><span class="sxs-lookup"><span data-stu-id="8fc3c-183">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="8fc3c-184">Definire i siti di rete</span><span class="sxs-lookup"><span data-stu-id="8fc3c-184">Define network sites</span></span>

<span data-ttu-id="8fc3c-185">Per definire i siti di rete, usare il cmdlet New-CsTenantNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-185">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="8fc3c-186">Ogni sito di rete deve essere associato a un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-186">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="8fc3c-187">L'esempio seguente crea tre nuovi siti di rete, Vietnam, Indonesia e Singapore nell'area APAC:</span><span class="sxs-lookup"><span data-stu-id="8fc3c-187">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="8fc3c-188">Definire le subnet di rete</span><span class="sxs-lookup"><span data-stu-id="8fc3c-188">Define network subnets</span></span>

<span data-ttu-id="8fc3c-189">Per definire le subnet di rete e associarle ai siti di rete, usare il cmdlet New-CsTenantNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-189">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="8fc3c-190">Ogni subnet di rete può essere associata a un solo sito.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-190">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="8fc3c-191">L'esempio seguente definisce tre subnet di rete e le associa ai tre siti di rete: Vietnam, Indonesia e Singapore:</span><span class="sxs-lookup"><span data-stu-id="8fc3c-191">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="8fc3c-192">Definire la topologia di rete virtuale</span><span class="sxs-lookup"><span data-stu-id="8fc3c-192">Define the virtual network topology</span></span> 

<span data-ttu-id="8fc3c-193">Prima di tutto, l'amministratore del tenant crea una nuova configurazione SBC per ogni SBC pertinente usando il cmdlet New-CsOnlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-193">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="8fc3c-194">L'amministratore del tenant definisce la topologia di rete virtuale specificando i siti di rete per gli oggetti gateway PSTN usando il cmdlet Set-CsOnlinePSTNGateway:</span><span class="sxs-lookup"><span data-stu-id="8fc3c-194">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="8fc3c-195">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8fc3c-195">Note the following:</span></span> 
   - <span data-ttu-id="8fc3c-196">Se il cliente ha un singolo SBC, il parametro-ProxySBC deve essere obbligatorio $null o il valore FQDN di SBC (SBC centrale con lo scenario Trunks centralizzato).</span><span class="sxs-lookup"><span data-stu-id="8fc3c-196">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="8fc3c-197">Il parametro-MediaBypass deve essere impostato su $true per supportare l'ottimizzazione dei contenuti multimediali locali.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-197">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="8fc3c-198">Se SBC non ha il set di parametri-BypassMode, le intestazioni X-MS non verranno inviate.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-198">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="8fc3c-199">Tutti i parametri sono maiuscole/minuscole, quindi devi assicurarti di usare lo stesso caso usato durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-199">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="8fc3c-200">Ad esempio, i valori di GatewaySiteID "Vietnam" e "Vietnam" verranno trattati come siti diversi.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-200">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="8fc3c-201">L'esempio seguente aggiunge tre SBCs ai siti di rete Vietnam, Indonesia e Singapore nell'area APAC con la modalità Ignora sempre:</span><span class="sxs-lookup"><span data-stu-id="8fc3c-201">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="8fc3c-202">Nota: per garantire che le operazioni ininterrotte quando vengono configurate l'ottimizzazione media locale e il routing basato sulla posizione (LBR), SBCs downstream debba essere abilitato per LBR impostando il parametro GatewaySiteLbrEnabled su $true per ogni SBC downstream.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-202">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="8fc3c-203">Questa impostazione non è obbligatoria per il proxy SBC.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-203">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="8fc3c-204">In base alle informazioni fornite sopra, il routing diretto includerà tre intestazioni SIP proprietarie per SIP invita e invita nuovamente come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-204">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="8fc3c-205">Intestazioni X-MS introdotte in routing diretto su invita e invita nuovamente se BypassMode è definito:</span><span class="sxs-lookup"><span data-stu-id="8fc3c-205">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="8fc3c-206">Nome intestazione</span><span class="sxs-lookup"><span data-stu-id="8fc3c-206">Header name</span></span> | <span data-ttu-id="8fc3c-207">Valori</span><span class="sxs-lookup"><span data-stu-id="8fc3c-207">Values</span></span> | <span data-ttu-id="8fc3c-208">Commenti</span><span class="sxs-lookup"><span data-stu-id="8fc3c-208">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="8fc3c-209">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="8fc3c-209">X-MS-UserLocation</span></span> | <span data-ttu-id="8fc3c-210">interno/esterno</span><span class="sxs-lookup"><span data-stu-id="8fc3c-210">internal/external</span></span> | <span data-ttu-id="8fc3c-211">Indica se l'utente è interno o esterno</span><span class="sxs-lookup"><span data-stu-id="8fc3c-211">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="8fc3c-212">Request-URI invita SIP: + 84439263000@VNsbc.contoso.com SIP/2,0</span><span class="sxs-lookup"><span data-stu-id="8fc3c-212">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="8fc3c-213">FQDN DI SBC</span><span class="sxs-lookup"><span data-stu-id="8fc3c-213">SBC FQDN</span></span> | <span data-ttu-id="8fc3c-214">Il nome di dominio completo che è destinato alla chiamata anche se SBC non è connesso direttamente al routing diretto</span><span class="sxs-lookup"><span data-stu-id="8fc3c-214">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="8fc3c-215">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="8fc3c-215">X-MS-MediaPath</span></span> | <span data-ttu-id="8fc3c-216">Esempio: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8fc3c-216">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="8fc3c-217">Ordine di SBCs che deve essere usato per il percorso multimediale tra l'utente e il SBC di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-217">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="8fc3c-218">Il SBC finale è sempre l'ultima volta</span><span class="sxs-lookup"><span data-stu-id="8fc3c-218">The final SBC is always last</span></span> |
| <span data-ttu-id="8fc3c-219">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="8fc3c-219">X-MS-UserSite</span></span> | <span data-ttu-id="8fc3c-220">usersiteID</span><span class="sxs-lookup"><span data-stu-id="8fc3c-220">usersiteID</span></span> | <span data-ttu-id="8fc3c-221">Stringa definita dall'amministratore del tenant</span><span class="sxs-lookup"><span data-stu-id="8fc3c-221">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="8fc3c-222">Flussi delle chiamate</span><span class="sxs-lookup"><span data-stu-id="8fc3c-222">Call flows</span></span> 

<span data-ttu-id="8fc3c-223">Di seguito sono illustrati i flussi delle chiamate per due modalità:</span><span class="sxs-lookup"><span data-stu-id="8fc3c-223">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="8fc3c-224">Ignorare sempre</span><span class="sxs-lookup"><span data-stu-id="8fc3c-224">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="8fc3c-225">Solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="8fc3c-225">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="8fc3c-226">Modalità di bypass sempre</span><span class="sxs-lookup"><span data-stu-id="8fc3c-226">Always Bypass mode</span></span>

<span data-ttu-id="8fc3c-227">La modalità Ignora sempre è l'opzione più semplice da configurare.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-227">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="8fc3c-228">L'amministratore del tenant può configurare un singolo sito per tutti gli utenti e SBCs se tutti i SBCs sono raggiungibili da qualsiasi sito.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-228">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="8fc3c-229">Gli esempi mostrano sempre la modalità di bypass per gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fc3c-229">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="8fc3c-230">Le chiamate in uscita e l'utente si trova nella stessa posizione di SBC</span><span class="sxs-lookup"><span data-stu-id="8fc3c-230">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="8fc3c-231">Le chiamate in ingresso e l'utente si trova nella stessa posizione di SBC</span><span class="sxs-lookup"><span data-stu-id="8fc3c-231">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="8fc3c-232">Chiamate in uscita e l'utente è esterno</span><span class="sxs-lookup"><span data-stu-id="8fc3c-232">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="8fc3c-233">Chiamate in ingresso e l'utente è esterno</span><span class="sxs-lookup"><span data-stu-id="8fc3c-233">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="8fc3c-234">La tabella seguente mostra l'FQDN e gli indirizzi IP usati negli esempi:</span><span class="sxs-lookup"><span data-stu-id="8fc3c-234">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="8fc3c-235">FQDN</span><span class="sxs-lookup"><span data-stu-id="8fc3c-235">FQDN</span></span> | <span data-ttu-id="8fc3c-236">Indirizzo IP esterno SBC</span><span class="sxs-lookup"><span data-stu-id="8fc3c-236">SBC external IP address</span></span> | <span data-ttu-id="8fc3c-237">Indirizzo IP interno SBC</span><span class="sxs-lookup"><span data-stu-id="8fc3c-237">SBC internal IP Address</span></span> | <span data-ttu-id="8fc3c-238">Subnet interna</span><span class="sxs-lookup"><span data-stu-id="8fc3c-238">Internal subnet</span></span> | <span data-ttu-id="8fc3c-239">Posizione</span><span class="sxs-lookup"><span data-stu-id="8fc3c-239">Location</span></span> | <span data-ttu-id="8fc3c-240">NAT esterno (IP attendibile)</span><span class="sxs-lookup"><span data-stu-id="8fc3c-240">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="8fc3c-241">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8fc3c-241">VNsbc.contoso.com</span></span> | <span data-ttu-id="8fc3c-242">Nessuno</span><span class="sxs-lookup"><span data-stu-id="8fc3c-242">None</span></span> | <span data-ttu-id="8fc3c-243">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="8fc3c-243">192.168.1.5</span></span> | <span data-ttu-id="8fc3c-244">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="8fc3c-244">192.168.1.0/24</span></span> | <span data-ttu-id="8fc3c-245">Vietnam</span><span class="sxs-lookup"><span data-stu-id="8fc3c-245">Vietnam</span></span> | <span data-ttu-id="8fc3c-246">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="8fc3c-246">172.16.240.110</span></span> |
| <span data-ttu-id="8fc3c-247">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8fc3c-247">IDsbc.contoso.com</span></span> | <span data-ttu-id="8fc3c-248">Nessuno</span><span class="sxs-lookup"><span data-stu-id="8fc3c-248">None</span></span> | <span data-ttu-id="8fc3c-249">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="8fc3c-249">192.168.2.5</span></span> | <span data-ttu-id="8fc3c-250">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="8fc3c-250">192.168.2.0/24</span></span> | <span data-ttu-id="8fc3c-251">Indonesia</span><span class="sxs-lookup"><span data-stu-id="8fc3c-251">Indonesia</span></span> | <span data-ttu-id="8fc3c-252">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="8fc3c-252">172.16.240.120</span></span> |
| <span data-ttu-id="8fc3c-253">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8fc3c-253">proxysbc.contoso.com</span></span> | <span data-ttu-id="8fc3c-254">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="8fc3c-254">172.16.240.133</span></span> | <span data-ttu-id="8fc3c-255">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="8fc3c-255">192.168.3.5</span></span> | <span data-ttu-id="8fc3c-256">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="8fc3c-256">192.168.3.0/24</span></span> | <span data-ttu-id="8fc3c-257">Singapore</span><span class="sxs-lookup"><span data-stu-id="8fc3c-257">Singapore</span></span> | <span data-ttu-id="8fc3c-258">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="8fc3c-258">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="8fc3c-259">Le chiamate in uscita e l'utente si trova nella stessa posizione dell'SBC con bypass sempre</span><span class="sxs-lookup"><span data-stu-id="8fc3c-259">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="8fc3c-260">Modalità</span><span class="sxs-lookup"><span data-stu-id="8fc3c-260">Mode</span></span> |    <span data-ttu-id="8fc3c-261">Utente</span><span class="sxs-lookup"><span data-stu-id="8fc3c-261">User</span></span> |  <span data-ttu-id="8fc3c-262">Posizione</span><span class="sxs-lookup"><span data-stu-id="8fc3c-262">Location</span></span> |  <span data-ttu-id="8fc3c-263">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="8fc3c-263">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="8fc3c-264">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="8fc3c-264">AlwaysBypass</span></span> |    <span data-ttu-id="8fc3c-265">Interno</span><span class="sxs-lookup"><span data-stu-id="8fc3c-265">Internal</span></span> |  <span data-ttu-id="8fc3c-266">Lo stesso sito di SBC</span><span class="sxs-lookup"><span data-stu-id="8fc3c-266">The same site as SBC</span></span> |  <span data-ttu-id="8fc3c-267">Outbound</span><span class="sxs-lookup"><span data-stu-id="8fc3c-267">Outbound</span></span> |

<span data-ttu-id="8fc3c-268">La tabella seguente mostra la configurazione e l'azione degli utenti finali:</span><span class="sxs-lookup"><span data-stu-id="8fc3c-268">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="8fc3c-269">Posizione fisica dell'utente</span><span class="sxs-lookup"><span data-stu-id="8fc3c-269">User physical location</span></span>| <span data-ttu-id="8fc3c-270">L'utente effettua o riceve una chiamata a/da numero</span><span class="sxs-lookup"><span data-stu-id="8fc3c-270">User makes or receives a call to/from number</span></span> | <span data-ttu-id="8fc3c-271">Numero di telefono dell'utente</span><span class="sxs-lookup"><span data-stu-id="8fc3c-271">User phone number</span></span>  | <span data-ttu-id="8fc3c-272">Criteri di routing vocale online</span><span class="sxs-lookup"><span data-stu-id="8fc3c-272">Online Voice Routing Policy</span></span> | <span data-ttu-id="8fc3c-273">Modalità configurata per SBC</span><span class="sxs-lookup"><span data-stu-id="8fc3c-273">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="8fc3c-274">Vietnam</span><span class="sxs-lookup"><span data-stu-id="8fc3c-274">Vietnam</span></span> | <span data-ttu-id="8fc3c-275">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="8fc3c-275">+84 4 3926 3000</span></span> | <span data-ttu-id="8fc3c-276">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="8fc3c-276">+84 4 5555 5555</span></span>   | <span data-ttu-id="8fc3c-277">Priorità 1: ^\+84 (\d{9}) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8fc3c-277">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="8fc3c-278">Priorità 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8fc3c-278">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="8fc3c-279">VNsbc.contoso.com-ignora sempre</span><span class="sxs-lookup"><span data-stu-id="8fc3c-279">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="8fc3c-280">proxysbc.contoso.com-ignora sempre</span><span class="sxs-lookup"><span data-stu-id="8fc3c-280">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="8fc3c-281">Il diagramma seguente mostra la scala SIP per una chiamata in uscita con la modalità di bypass sempre e l'utente nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-281">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="8fc3c-282">![Diagramma che mostra le chiamate in uscita](media/direct-routing-media-op-10.png "Chiamate in uscita")</span><span class="sxs-lookup"><span data-stu-id="8fc3c-282">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="8fc3c-283">La tabella seguente mostra le intestazioni X-MS inviate tramite routing diretto:</span><span class="sxs-lookup"><span data-stu-id="8fc3c-283">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="8fc3c-284">Parametro</span><span class="sxs-lookup"><span data-stu-id="8fc3c-284">Parameter</span></span> | <span data-ttu-id="8fc3c-285">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="8fc3c-285">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="8fc3c-286">Invitare + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8fc3c-286">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="8fc3c-287">Il nome di destinazione dell'SBC come definito nei criteri di routing vocale online viene inviato nell'URI della richiesta</span><span class="sxs-lookup"><span data-stu-id="8fc3c-287">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="8fc3c-288">X-MS-UserLocation: Internal</span><span class="sxs-lookup"><span data-stu-id="8fc3c-288">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="8fc3c-289">Il campo indica che l'utente si trova all'interno della rete aziendale</span><span class="sxs-lookup"><span data-stu-id="8fc3c-289">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="8fc3c-290">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8fc3c-290">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="8fc3c-291">Specifica il SBC che deve essere attraversato dal client al SBC di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-291">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="8fc3c-292">In questo caso, come abbiamo sempre bypassare, e il client è interno il nome di destinazione inviato come unico nome nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-292">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="8fc3c-293">X-MS-UserSite: Vietnam</span><span class="sxs-lookup"><span data-stu-id="8fc3c-293">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="8fc3c-294">Campo indicato nel sito in cui si trova l'utente.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-294">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="8fc3c-295">Le chiamate in ingresso e l'utente si trova nella stessa posizione dell'SBC con il bypass sempre</span><span class="sxs-lookup"><span data-stu-id="8fc3c-295">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="8fc3c-296">Modalità</span><span class="sxs-lookup"><span data-stu-id="8fc3c-296">Mode</span></span> |    <span data-ttu-id="8fc3c-297">Utente</span><span class="sxs-lookup"><span data-stu-id="8fc3c-297">User</span></span> |  <span data-ttu-id="8fc3c-298">Posizione</span><span class="sxs-lookup"><span data-stu-id="8fc3c-298">Location</span></span> |  <span data-ttu-id="8fc3c-299">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="8fc3c-299">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="8fc3c-300">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="8fc3c-300">AlwaysBypass</span></span> |    <span data-ttu-id="8fc3c-301">Interno</span><span class="sxs-lookup"><span data-stu-id="8fc3c-301">Internal</span></span> | <span data-ttu-id="8fc3c-302">Lo stesso sito di SBC</span><span class="sxs-lookup"><span data-stu-id="8fc3c-302">The same site as SBC</span></span> | <span data-ttu-id="8fc3c-303">In ingresso</span><span class="sxs-lookup"><span data-stu-id="8fc3c-303">Inbound</span></span> |


<span data-ttu-id="8fc3c-304">In una chiamata in ingresso, la posizione dell'utente è sconosciuta e il SBC deve indovinare dove si trova l'utente.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-304">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="8fc3c-305">Se l'ipotesi non è corretta, sarà necessario un nuovo invito.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-305">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="8fc3c-306">Questo caso presuppone che l'utente sia interno, che l'elemento multimediale possa fluire direttamente e che non siano necessarie altre azioni (re-INVITE).</span><span class="sxs-lookup"><span data-stu-id="8fc3c-306">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="8fc3c-307">Il SBC connesso al servizio di routing diretto riporta la posizione del SBC di origine fornendo campi di record-route e Contact.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-307">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="8fc3c-308">In base a questi campi, il percorso del supporto viene calcolato tramite routing diretto.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-308">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="8fc3c-309">Nota: dato che un utente può avere più endpoint, il supporto di 183 non è possibile.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-309">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="8fc3c-310">Il routing diretto userà sempre 180 squillare in questo caso.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-310">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="8fc3c-311">Il diagramma seguente mostra la scala SIP per la chiamata in ingresso con la modalità AlwaysBypass e l'utente si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-311">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="8fc3c-313">Chiamate in uscita e l'utente è esterno con l'esclusione sempre</span><span class="sxs-lookup"><span data-stu-id="8fc3c-313">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="8fc3c-314">Modalità</span><span class="sxs-lookup"><span data-stu-id="8fc3c-314">Mode</span></span> |    <span data-ttu-id="8fc3c-315">Utente</span><span class="sxs-lookup"><span data-stu-id="8fc3c-315">User</span></span> |  <span data-ttu-id="8fc3c-316">Sito</span><span class="sxs-lookup"><span data-stu-id="8fc3c-316">Site</span></span> |  <span data-ttu-id="8fc3c-317">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="8fc3c-317">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="8fc3c-318">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="8fc3c-318">AlwaysBypass</span></span> |  <span data-ttu-id="8fc3c-319">Esterno</span><span class="sxs-lookup"><span data-stu-id="8fc3c-319">External</span></span> |  <span data-ttu-id="8fc3c-320">N/D</span><span class="sxs-lookup"><span data-stu-id="8fc3c-320">N/A</span></span> | <span data-ttu-id="8fc3c-321">Outbound</span><span class="sxs-lookup"><span data-stu-id="8fc3c-321">Outbound</span></span> |


<span data-ttu-id="8fc3c-322">Il diagramma seguente mostra la scala SIP per una chiamata in uscita con la modalità AlwaysBypass e l'utente è esterno:</span><span class="sxs-lookup"><span data-stu-id="8fc3c-322">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-12.png)

<span data-ttu-id="8fc3c-324">La tabella seguente mostra le intestazioni X-MS inviate dal servizio di routing diretto:</span><span class="sxs-lookup"><span data-stu-id="8fc3c-324">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="8fc3c-325">Parametro</span><span class="sxs-lookup"><span data-stu-id="8fc3c-325">Parameter</span></span> |   <span data-ttu-id="8fc3c-326">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="8fc3c-326">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="8fc3c-327">Invitare + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8fc3c-327">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="8fc3c-328">Il nome di destinazione dell'SBC come definito nei criteri di routing vocale online viene inviato nell'URI della richiesta.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-328">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="8fc3c-329">X-MS-UserLocation: esterno</span><span class="sxs-lookup"><span data-stu-id="8fc3c-329">X-MS-UserLocation: external</span></span> | <span data-ttu-id="8fc3c-330">Il campo indica che l'utente si trova all'esterno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-330">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="8fc3c-331">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8fc3c-331">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="8fc3c-332">Specifica il SBC che deve essere attraversato dal client al SBC di destinazione.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-332">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="8fc3c-333">In questo caso, come abbiamo sempre bypassare, e il client è esterno.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-333">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="8fc3c-334">Chiamate in ingresso e l'utente è esterno con il bypass sempre</span><span class="sxs-lookup"><span data-stu-id="8fc3c-334">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="8fc3c-335">Modalità</span><span class="sxs-lookup"><span data-stu-id="8fc3c-335">Mode</span></span> | <span data-ttu-id="8fc3c-336">Utente</span><span class="sxs-lookup"><span data-stu-id="8fc3c-336">User</span></span> | <span data-ttu-id="8fc3c-337">Sito</span><span class="sxs-lookup"><span data-stu-id="8fc3c-337">Site</span></span> |  <span data-ttu-id="8fc3c-338">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="8fc3c-338">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="8fc3c-339">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="8fc3c-339">AlwaysBypass</span></span> |  <span data-ttu-id="8fc3c-340">Esterno</span><span class="sxs-lookup"><span data-stu-id="8fc3c-340">External</span></span> |  <span data-ttu-id="8fc3c-341">N/D</span><span class="sxs-lookup"><span data-stu-id="8fc3c-341">N/A</span></span> |   <span data-ttu-id="8fc3c-342">In ingresso</span><span class="sxs-lookup"><span data-stu-id="8fc3c-342">Inbound</span></span> |

<span data-ttu-id="8fc3c-343">Per una chiamata in ingresso, il SBC connesso al routing diretto deve inviare un re-invite (per impostazione predefinita, i candidati multimediali locali sono sempre offerti) se la posizione dell'utente è esterna.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-343">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="8fc3c-344">L'X-MediaPath viene calcolato in base a record-route e all'utente SBC specificato.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-344">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="8fc3c-345">Il diagramma seguente mostra la scala SIP per una chiamata in ingresso con la modalità AlwaysBypass e l'utente è esterno.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-345">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="8fc3c-347">Solo per la modalità utenti locali</span><span class="sxs-lookup"><span data-stu-id="8fc3c-347">Only for local users mode</span></span>

<span data-ttu-id="8fc3c-348">I candidati multimediali locali del SBC di destinazione verranno offerti solo se un utente si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-348">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="8fc3c-349">In tutti gli altri casi, il flusso multimediale verrà eseguito attraverso un IP interno o esterno del SBC proxy.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-349">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="8fc3c-350">Vengono descritti gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="8fc3c-350">The following scenarios are described:</span></span>

- [<span data-ttu-id="8fc3c-351">Le chiamate in uscita e l'utente si trova nella stessa posizione di SBC</span><span class="sxs-lookup"><span data-stu-id="8fc3c-351">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="8fc3c-352">Le chiamate in ingresso e l'utente si trova nella stessa posizione di SBC</span><span class="sxs-lookup"><span data-stu-id="8fc3c-352">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="8fc3c-353">L'utente non si trova nella stessa posizione di SBC, ma nella rete aziendale</span><span class="sxs-lookup"><span data-stu-id="8fc3c-353">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="8fc3c-354">Le chiamate in ingresso e l'utente sono interne, ma non si trova nella stessa posizione di SBC</span><span class="sxs-lookup"><span data-stu-id="8fc3c-354">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="8fc3c-355">La tabella seguente mostra la configurazione e l'azione degli utenti finali:</span><span class="sxs-lookup"><span data-stu-id="8fc3c-355">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="8fc3c-356">Posizione fisica dell'utente</span><span class="sxs-lookup"><span data-stu-id="8fc3c-356">User physical location</span></span> |  <span data-ttu-id="8fc3c-357">L'utente effettua o riceve una chiamata a/da numero</span><span class="sxs-lookup"><span data-stu-id="8fc3c-357">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="8fc3c-358">Numero di telefono dell'utente</span><span class="sxs-lookup"><span data-stu-id="8fc3c-358">User phone number</span></span> | <span data-ttu-id="8fc3c-359">Criteri di routing vocale online</span><span class="sxs-lookup"><span data-stu-id="8fc3c-359">Online Voice Routing Policy</span></span> |   <span data-ttu-id="8fc3c-360">Modalità configurata per SBC</span><span class="sxs-lookup"><span data-stu-id="8fc3c-360">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="8fc3c-361">Vietnam</span><span class="sxs-lookup"><span data-stu-id="8fc3c-361">Vietnam</span></span> | <span data-ttu-id="8fc3c-362">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="8fc3c-362">+84 4 3926  3000</span></span> |  <span data-ttu-id="8fc3c-363">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="8fc3c-363">+84 4 5555 5555</span></span> | <span data-ttu-id="8fc3c-364">Priorità 1: ^\+84 (\d{9}) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8fc3c-364">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="8fc3c-365">Priorità 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="8fc3c-365">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="8fc3c-366">VNsbc.contoso.com-OnlyForLocalUsers Proxysbc.contoso.com-ignora sempre</span><span class="sxs-lookup"><span data-stu-id="8fc3c-366">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="8fc3c-367">Le chiamate in uscita e l'utente si trova nella stessa posizione del SBC con solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="8fc3c-367">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="8fc3c-368">Modalità</span><span class="sxs-lookup"><span data-stu-id="8fc3c-368">Mode</span></span> | <span data-ttu-id="8fc3c-369">Utente</span><span class="sxs-lookup"><span data-stu-id="8fc3c-369">User</span></span> | <span data-ttu-id="8fc3c-370">Sito</span><span class="sxs-lookup"><span data-stu-id="8fc3c-370">Site</span></span> | <span data-ttu-id="8fc3c-371">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="8fc3c-371">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="8fc3c-372">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="8fc3c-372">OnlyForLocalUsers</span></span> |   <span data-ttu-id="8fc3c-373">Interno</span><span class="sxs-lookup"><span data-stu-id="8fc3c-373">Internal</span></span> |<span data-ttu-id="8fc3c-374">Uguale a SBC</span><span class="sxs-lookup"><span data-stu-id="8fc3c-374">Same as SBC</span></span>   | <span data-ttu-id="8fc3c-375">Outbound</span><span class="sxs-lookup"><span data-stu-id="8fc3c-375">Outbound</span></span> |

<span data-ttu-id="8fc3c-376">Il diagramma seguente mostra una chiamata in uscita con la modalità OnlyForLocalUsers e l'utente si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-376">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="8fc3c-377">Si tratta dello stesso flusso visualizzato nelle [chiamate in uscita quando l'utente si trova nella stessa posizione di SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="8fc3c-377">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="8fc3c-379">Le chiamate in ingresso e l'utente si trova nella stessa posizione del SBC con solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="8fc3c-379">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="8fc3c-380">Modalità</span><span class="sxs-lookup"><span data-stu-id="8fc3c-380">Mode</span></span> | <span data-ttu-id="8fc3c-381">Utente</span><span class="sxs-lookup"><span data-stu-id="8fc3c-381">User</span></span> | <span data-ttu-id="8fc3c-382">Sito</span><span class="sxs-lookup"><span data-stu-id="8fc3c-382">Site</span></span> | <span data-ttu-id="8fc3c-383">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="8fc3c-383">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="8fc3c-384">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="8fc3c-384">OnlyForLocalUsers</span></span> |   <span data-ttu-id="8fc3c-385">Interno</span><span class="sxs-lookup"><span data-stu-id="8fc3c-385">Internal</span></span> | <span data-ttu-id="8fc3c-386">Uguale a SBC</span><span class="sxs-lookup"><span data-stu-id="8fc3c-386">Same as SBC</span></span> | <span data-ttu-id="8fc3c-387">In ingresso</span><span class="sxs-lookup"><span data-stu-id="8fc3c-387">Inbound</span></span> |

<span data-ttu-id="8fc3c-388">Il diagramma seguente mostra una chiamata in ingresso con la modalità OnlyForLocalUsers e l'utente si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-388">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="8fc3c-389">Si tratta dello stesso flusso illustrato nelle [chiamate in ingresso quando l'utente si trova nella stessa posizione di SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="8fc3c-389">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="8fc3c-391">L'utente non si trova nella stessa posizione di SBC, ma è nella rete aziendale solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="8fc3c-391">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="8fc3c-392">Modalità</span><span class="sxs-lookup"><span data-stu-id="8fc3c-392">Mode</span></span> | <span data-ttu-id="8fc3c-393">Utente</span><span class="sxs-lookup"><span data-stu-id="8fc3c-393">User</span></span> | <span data-ttu-id="8fc3c-394">Sito</span><span class="sxs-lookup"><span data-stu-id="8fc3c-394">Site</span></span> |<span data-ttu-id="8fc3c-395">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="8fc3c-395">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="8fc3c-396">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="8fc3c-396">OnlyForLocalUsers</span></span>  | <span data-ttu-id="8fc3c-397">Interno</span><span class="sxs-lookup"><span data-stu-id="8fc3c-397">Internal</span></span> |   <span data-ttu-id="8fc3c-398">Diverso da SBC</span><span class="sxs-lookup"><span data-stu-id="8fc3c-398">Different from SBC</span></span> | <span data-ttu-id="8fc3c-399">Outbound</span><span class="sxs-lookup"><span data-stu-id="8fc3c-399">Outbound</span></span> |

<span data-ttu-id="8fc3c-400">Il routing diretto calcola X-MediaPath in base alla posizione segnalata dell'utente e alla modalità configurata in SBC.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-400">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="8fc3c-401">Il diagramma seguente mostra una chiamata in uscita con la modalità OnlyForLocalUsers e un utente interno che non si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-401">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="8fc3c-403">Chiamata in ingresso e l'utente è interno, ma non è nella stessa posizione dell'SBC con solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="8fc3c-403">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="8fc3c-404">Modalità</span><span class="sxs-lookup"><span data-stu-id="8fc3c-404">Mode</span></span> |    <span data-ttu-id="8fc3c-405">Utente</span><span class="sxs-lookup"><span data-stu-id="8fc3c-405">User</span></span> |  <span data-ttu-id="8fc3c-406">Sito</span><span class="sxs-lookup"><span data-stu-id="8fc3c-406">Site</span></span> |  <span data-ttu-id="8fc3c-407">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="8fc3c-407">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="8fc3c-408">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="8fc3c-408">OnlyForLocalUsers</span></span> | <span data-ttu-id="8fc3c-409">Interno</span><span class="sxs-lookup"><span data-stu-id="8fc3c-409">Internal</span></span> |    <span data-ttu-id="8fc3c-410">Diverso da SBC</span><span class="sxs-lookup"><span data-stu-id="8fc3c-410">Different from SBC</span></span> |    <span data-ttu-id="8fc3c-411">In ingresso</span><span class="sxs-lookup"><span data-stu-id="8fc3c-411">Inbound</span></span> |

<span data-ttu-id="8fc3c-412">Il diagramma seguente mostra una chiamata in ingresso con la modalità OnlyForLocalUsers e un utente interno che non si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="8fc3c-412">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-17.png)









