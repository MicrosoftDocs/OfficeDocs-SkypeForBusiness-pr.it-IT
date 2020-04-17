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
ms.openlocfilehash: 8a69a46d7620628c7afffb706354c0f6e7868f3d
ms.sourcegitcommit: 3dd6499416e9fbdcb48187c6322bd607290502ce
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/16/2020
ms.locfileid: "43541593"
---
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="bbf8f-103">Configurare l'ottimizzazione multimediale locale per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="bbf8f-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="bbf8f-104">La configurazione per l'ottimizzazione media locale si basa sulle impostazioni di rete comuni ad altre caratteristiche vocali del cloud, ad esempio routing basato sulla posizione e chiamate di emergenza dinamiche.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="bbf8f-105">Per altre informazioni sulle aree di rete, i siti di rete, le subnet di rete e gli indirizzi IP attendibili, vedere [impostazioni di rete per le funzionalità di cloud Voice](cloud-voice-network-settings.md).</span><span class="sxs-lookup"><span data-stu-id="bbf8f-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="bbf8f-106">Prima di configurare l'ottimizzazione multimediale locale, vedere [ottimizzazione dei contenuti multimediali locali per il routing diretto](direct-routing-media-optimization.md).</span><span class="sxs-lookup"><span data-stu-id="bbf8f-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="bbf8f-107">Per configurare l'ottimizzazione multimediale locale, sono necessarie le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="bbf8f-108">Puoi usare l'interfaccia di amministrazione di teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="bbf8f-109">Per informazioni dettagliate, vedere [gestire la topologia di rete](manage-your-network-topology.md).</span><span class="sxs-lookup"><span data-stu-id="bbf8f-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="bbf8f-110">Configurare l'utente e i siti SBC (come descritto in questo articolo).</span><span class="sxs-lookup"><span data-stu-id="bbf8f-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="bbf8f-111">Configurare la SBCs for local Media Optimization (in base alla specifica del fornitore SBC).</span><span class="sxs-lookup"><span data-stu-id="bbf8f-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="bbf8f-112">Il diagramma seguente mostra la configurazione della rete usata negli esempi in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="bbf8f-113">![Diagramma che mostra la configurazione della rete per gli esempi](media/direct-routing-media-op-9.png "Configurazione di rete per gli esempi")</span><span class="sxs-lookup"><span data-stu-id="bbf8f-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="bbf8f-114">Configurare l'utente e i siti SBC</span><span class="sxs-lookup"><span data-stu-id="bbf8f-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="bbf8f-115">Per configurare l'utente e i siti SBC, sarà necessario:</span><span class="sxs-lookup"><span data-stu-id="bbf8f-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="bbf8f-116">[Gestire indirizzi IP attendibili esterni](#manage-external-trusted-ip-addresses).</span><span class="sxs-lookup"><span data-stu-id="bbf8f-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="bbf8f-117">[Definire la topologia di rete](#define-the-network-topology) configurando le aree di rete, i siti di rete e le subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="bbf8f-118">[Definire la topologia di rete virtuale](#define-the-virtual-network-topology) assegnando SBC (s) ai siti con le modalità pertinenti e i valori del proxy SBC.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="bbf8f-119">Configurare SBC per l'ottimizzazione di elementi multimediali locali in base alla specifica del fornitore SBC</span><span class="sxs-lookup"><span data-stu-id="bbf8f-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="bbf8f-120">Questo articolo descrive la configurazione per i componenti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="bbf8f-121">Per informazioni sulla configurazione di SBC, vedere il fornitore di SBC documentazione.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-121">For information on SBC configuration, see your SBC vendor documenation.</span></span>

<span data-ttu-id="bbf8f-122">L'ottimizzazione media locale è supportata dai seguenti fornitori di SBC:</span><span class="sxs-lookup"><span data-stu-id="bbf8f-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="bbf8f-123">Fornitore</span><span class="sxs-lookup"><span data-stu-id="bbf8f-123">Vendor</span></span> | <span data-ttu-id="bbf8f-124">Prodotto</span><span class="sxs-lookup"><span data-stu-id="bbf8f-124">Product</span></span> |    <span data-ttu-id="bbf8f-125">Versione software</span><span class="sxs-lookup"><span data-stu-id="bbf8f-125">Software version</span></span> |
|:------------|:-------|:-------| :-------|
| [<span data-ttu-id="bbf8f-126">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="bbf8f-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="bbf8f-127">SBC 500 medium</span><span class="sxs-lookup"><span data-stu-id="bbf8f-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="bbf8f-128">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="bbf8f-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="bbf8f-129">SBC 800 Medium</span><span class="sxs-lookup"><span data-stu-id="bbf8f-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="bbf8f-130">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="bbf8f-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="bbf8f-131">SBC 2600 medium</span><span class="sxs-lookup"><span data-stu-id="bbf8f-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="bbf8f-132">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="bbf8f-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="bbf8f-133">SBC 4000 medium</span><span class="sxs-lookup"><span data-stu-id="bbf8f-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="bbf8f-134">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="bbf8f-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="bbf8f-135">SBC 1000B medium</span><span class="sxs-lookup"><span data-stu-id="bbf8f-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="bbf8f-136">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="bbf8f-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="bbf8f-137">SBC 9000 medium</span><span class="sxs-lookup"><span data-stu-id="bbf8f-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="bbf8f-138">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="bbf8f-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="bbf8f-139">SBC virtuale per edizioni medious</span><span class="sxs-lookup"><span data-stu-id="bbf8f-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="bbf8f-140">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="bbf8f-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="bbf8f-141">SBC Cloud Edition</span><span class="sxs-lookup"><span data-stu-id="bbf8f-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="bbf8f-142">7.20 a. 256</span><span class="sxs-lookup"><span data-stu-id="bbf8f-142">7.20A.256</span></span> |
| [<span data-ttu-id="bbf8f-143">Core SBC della barra multifunzione</span><span class="sxs-lookup"><span data-stu-id="bbf8f-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="bbf8f-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="bbf8f-144">SBC 5110</span></span>         | <span data-ttu-id="bbf8f-145">8,2</span><span class="sxs-lookup"><span data-stu-id="bbf8f-145">8.2</span></span>  |
|            |  <span data-ttu-id="bbf8f-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="bbf8f-146">SBC 5210</span></span>         | <span data-ttu-id="bbf8f-147">8,2</span><span class="sxs-lookup"><span data-stu-id="bbf8f-147">8.2</span></span>  |
|            |  <span data-ttu-id="bbf8f-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="bbf8f-148">SBC 5400</span></span>         | <span data-ttu-id="bbf8f-149">8,2</span><span class="sxs-lookup"><span data-stu-id="bbf8f-149">8.2</span></span>  |
|            |  <span data-ttu-id="bbf8f-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="bbf8f-150">SBC 7000</span></span>         | <span data-ttu-id="bbf8f-151">8,2</span><span class="sxs-lookup"><span data-stu-id="bbf8f-151">8.2</span></span>  |
|            |  <span data-ttu-id="bbf8f-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="bbf8f-152">SBC SWe</span></span>          | <span data-ttu-id="bbf8f-153">8,2</span><span class="sxs-lookup"><span data-stu-id="bbf8f-153">8.2</span></span>  |
| [<span data-ttu-id="bbf8f-154">Bordo SBC della barra multifunzione</span><span class="sxs-lookup"><span data-stu-id="bbf8f-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Microsoft+Teams+Direct+Routing+-+On+Premises+Deployment)  |  <span data-ttu-id="bbf8f-155">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="bbf8f-155">SBC 1000</span></span>         | <span data-ttu-id="bbf8f-156">8.1.1, Build 527</span><span class="sxs-lookup"><span data-stu-id="bbf8f-156">8.1.1, build 527</span></span> |
|            |  <span data-ttu-id="bbf8f-157">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="bbf8f-157">SBC 2000</span></span>         | <span data-ttu-id="bbf8f-158">8.1.1, Build 527</span><span class="sxs-lookup"><span data-stu-id="bbf8f-158">8.1.1, build 527</span></span> |
|            |  <span data-ttu-id="bbf8f-159">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="bbf8f-159">SBC SWe Lite</span></span>     | <span data-ttu-id="bbf8f-160">8.1.0, build 222</span><span class="sxs-lookup"><span data-stu-id="bbf8f-160">8.1.0, build 222</span></span> |
| [<span data-ttu-id="bbf8f-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="bbf8f-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="bbf8f-162">anynode</span><span class="sxs-lookup"><span data-stu-id="bbf8f-162">anynode</span></span>          | <span data-ttu-id="bbf8f-163">4.0.1 +</span><span class="sxs-lookup"><span data-stu-id="bbf8f-163">4.0.1+</span></span> |
| [<span data-ttu-id="bbf8f-164">Oracle</span><span class="sxs-lookup"><span data-stu-id="bbf8f-164">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="bbf8f-165">AP 1100</span><span class="sxs-lookup"><span data-stu-id="bbf8f-165">AP 1100</span></span> | <span data-ttu-id="bbf8f-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="bbf8f-166">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="bbf8f-167">AP 3900</span><span class="sxs-lookup"><span data-stu-id="bbf8f-167">AP 3900</span></span> | <span data-ttu-id="bbf8f-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="bbf8f-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="bbf8f-169">AP 4600</span><span class="sxs-lookup"><span data-stu-id="bbf8f-169">AP 4600</span></span> | <span data-ttu-id="bbf8f-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="bbf8f-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="bbf8f-171">AP 6300</span><span class="sxs-lookup"><span data-stu-id="bbf8f-171">AP 6300</span></span> | <span data-ttu-id="bbf8f-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="bbf8f-172">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="bbf8f-173">AP 6350</span><span class="sxs-lookup"><span data-stu-id="bbf8f-173">AP 6350</span></span> | <span data-ttu-id="bbf8f-174">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="bbf8f-174">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="bbf8f-175">VME</span><span class="sxs-lookup"><span data-stu-id="bbf8f-175">VME</span></span>     | <span data-ttu-id="bbf8f-176">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="bbf8f-176">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="bbf8f-177">Gestire indirizzi IP attendibili esterni</span><span class="sxs-lookup"><span data-stu-id="bbf8f-177">Manage external trusted IP addresses</span></span>

<span data-ttu-id="bbf8f-178">Gli IPs attendibili esterni sono gli IPs esterni Internet della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-178">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="bbf8f-179">Questi IP sono gli indirizzi IP usati dai client Microsoft teams quando si connettono a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-179">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="bbf8f-180">È necessario aggiungere questi IP esterni per ogni sito in cui sono presenti utenti che usano l'ottimizzazione media locale.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-180">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="bbf8f-181">Per aggiungere gli indirizzi IP pubblici per ogni sito, usare il cmdlet New-CsTenantTrustedIPAddress.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-181">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="bbf8f-182">Puoi definire un numero illimitato di indirizzi IP attendibili per un tenant.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-182">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="bbf8f-183">Se gli IPs esterni visti da Microsoft 365 sono sia indirizzi IPv4 che IPv6, è necessario aggiungere entrambi i tipi di indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-183">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="bbf8f-184">Per IPv4, USA Mask 32.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-184">For IPv4, use mask 32.</span></span> <span data-ttu-id="bbf8f-185">Per IPv6, USA mask 128.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-185">For IPv6, use mask 128.</span></span> <span data-ttu-id="bbf8f-186">È possibile aggiungere sia singoli indirizzi IP esterni che subnet IP esterni specificando diversi MaskBits nel cmdlet.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-186">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="bbf8f-187">Esempio di aggiunta di indirizzi IP attendibili.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-187">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="bbf8f-188">Definire la topologia di rete</span><span class="sxs-lookup"><span data-stu-id="bbf8f-188">Define the network topology</span></span>

<span data-ttu-id="bbf8f-189">Questa sezione descrive come definire le aree di rete, i siti di rete e le subnet di rete per la topologia di rete.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-189">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="bbf8f-190">Tutti i parametri sono maiuscole/minuscole, quindi devi assicurarti di usare lo stesso caso usato durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-190">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="bbf8f-191">Ad esempio, i valori di GatewaySiteID "Vietnam" e "Vietnam" verranno trattati come siti diversi.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-191">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="bbf8f-192">Definire le aree di rete</span><span class="sxs-lookup"><span data-stu-id="bbf8f-192">Define network regions</span></span>

<span data-ttu-id="bbf8f-193">Per definire le aree di rete, usare il cmdlet New-CsTenantNetworkRegion.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-193">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="bbf8f-194">Il parametro RegionID è un nome logico che rappresenta la geografia dell'area geografica e non ha dipendenze o restrizioni.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-194">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="bbf8f-195">Il parametro <site ID> CentralSite è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-195">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="bbf8f-196">L'esempio seguente crea un'area di rete denominata APAC:</span><span class="sxs-lookup"><span data-stu-id="bbf8f-196">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="bbf8f-197">Definire i siti di rete</span><span class="sxs-lookup"><span data-stu-id="bbf8f-197">Define network sites</span></span>

<span data-ttu-id="bbf8f-198">Per definire i siti di rete, usare il cmdlet New-CsTenantNetworkSite.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-198">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="bbf8f-199">Ogni sito di rete deve essere associato a un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-199">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="bbf8f-200">L'esempio seguente crea tre nuovi siti di rete, Vietnam, Indonesia e Singapore nell'area APAC:</span><span class="sxs-lookup"><span data-stu-id="bbf8f-200">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="bbf8f-201">Definire le subnet di rete</span><span class="sxs-lookup"><span data-stu-id="bbf8f-201">Define network subnets</span></span>

<span data-ttu-id="bbf8f-202">Per definire le subnet di rete e associarle ai siti di rete, usare il cmdlet New-CsTenantNetworkSubnet.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-202">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="bbf8f-203">Ogni subnet di rete può essere associata a un solo sito.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-203">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="bbf8f-204">L'esempio seguente definisce tre subnet di rete e le associa ai tre siti di rete: Vietnam, Indonesia e Singapore:</span><span class="sxs-lookup"><span data-stu-id="bbf8f-204">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="bbf8f-205">Definire la topologia di rete virtuale</span><span class="sxs-lookup"><span data-stu-id="bbf8f-205">Define the virtual network topology</span></span> 

<span data-ttu-id="bbf8f-206">Prima di tutto, l'amministratore del tenant crea una nuova configurazione SBC per ogni SBC pertinente usando il cmdlet New-CsOnlinePSTNGateway.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-206">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="bbf8f-207">L'amministratore del tenant definisce la topologia di rete virtuale specificando i siti di rete per gli oggetti gateway PSTN usando il cmdlet Set-CsOnlinePSTNGateway:</span><span class="sxs-lookup"><span data-stu-id="bbf8f-207">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="bbf8f-208">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="bbf8f-208">Note the following:</span></span> 
   - <span data-ttu-id="bbf8f-209">Se il cliente ha un singolo SBC, il parametro-ProxySBC deve essere obbligatorio $null o il valore FQDN di SBC (SBC centrale con lo scenario Trunks centralizzato).</span><span class="sxs-lookup"><span data-stu-id="bbf8f-209">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="bbf8f-210">Il parametro-MediaBypass deve essere impostato su $true per supportare l'ottimizzazione dei contenuti multimediali locali.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-210">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="bbf8f-211">Se SBC non ha il set di parametri-BypassMode, le intestazioni X-MS non verranno inviate.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-211">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="bbf8f-212">Tutti i parametri sono maiuscole/minuscole, quindi devi assicurarti di usare lo stesso caso usato durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-212">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="bbf8f-213">Ad esempio, i valori di GatewaySiteID "Vietnam" e "Vietnam" verranno trattati come siti diversi.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-213">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="bbf8f-214">L'esempio seguente aggiunge tre SBCs ai siti di rete Vietnam, Indonesia e Singapore nell'area APAC con la modalità Ignora sempre:</span><span class="sxs-lookup"><span data-stu-id="bbf8f-214">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="bbf8f-215">Nota: per garantire che le operazioni ininterrotte quando vengono configurate l'ottimizzazione media locale e il routing basato sulla posizione (LBR), SBCs downstream debba essere abilitato per LBR impostando il parametro GatewaySiteLbrEnabled su $true per ogni SBC downstream.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-215">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="bbf8f-216">Questa impostazione non è obbligatoria per il proxy SBC.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-216">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="bbf8f-217">In base alle informazioni fornite sopra, il routing diretto includerà tre intestazioni SIP proprietarie per SIP invita e invita nuovamente come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-217">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="bbf8f-218">Intestazioni X-MS introdotte in routing diretto su invita e invita nuovamente se BypassMode è definito:</span><span class="sxs-lookup"><span data-stu-id="bbf8f-218">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="bbf8f-219">Nome intestazione</span><span class="sxs-lookup"><span data-stu-id="bbf8f-219">Header name</span></span> | <span data-ttu-id="bbf8f-220">Valori</span><span class="sxs-lookup"><span data-stu-id="bbf8f-220">Values</span></span> | <span data-ttu-id="bbf8f-221">Commenti</span><span class="sxs-lookup"><span data-stu-id="bbf8f-221">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="bbf8f-222">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="bbf8f-222">X-MS-UserLocation</span></span> | <span data-ttu-id="bbf8f-223">interno/esterno</span><span class="sxs-lookup"><span data-stu-id="bbf8f-223">internal/external</span></span> | <span data-ttu-id="bbf8f-224">Indica se l'utente è interno o esterno</span><span class="sxs-lookup"><span data-stu-id="bbf8f-224">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="bbf8f-225">Request-URI invita SIP: + 84439263000@VNsbc.contoso.com SIP/2,0</span><span class="sxs-lookup"><span data-stu-id="bbf8f-225">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="bbf8f-226">FQDN DI SBC</span><span class="sxs-lookup"><span data-stu-id="bbf8f-226">SBC FQDN</span></span> | <span data-ttu-id="bbf8f-227">Il nome di dominio completo che è destinato alla chiamata anche se SBC non è connesso direttamente al routing diretto</span><span class="sxs-lookup"><span data-stu-id="bbf8f-227">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="bbf8f-228">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="bbf8f-228">X-MS-MediaPath</span></span> | <span data-ttu-id="bbf8f-229">Esempio: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bbf8f-229">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="bbf8f-230">Ordine di SBCs che deve essere usato per il percorso multimediale tra l'utente e il SBC di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-230">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="bbf8f-231">Il SBC finale è sempre l'ultima volta</span><span class="sxs-lookup"><span data-stu-id="bbf8f-231">The final SBC is always last</span></span> |
| <span data-ttu-id="bbf8f-232">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="bbf8f-232">X-MS-UserSite</span></span> | <span data-ttu-id="bbf8f-233">usersiteID</span><span class="sxs-lookup"><span data-stu-id="bbf8f-233">usersiteID</span></span> | <span data-ttu-id="bbf8f-234">Stringa definita dall'amministratore del tenant</span><span class="sxs-lookup"><span data-stu-id="bbf8f-234">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="bbf8f-235">Flussi delle chiamate</span><span class="sxs-lookup"><span data-stu-id="bbf8f-235">Call flows</span></span> 

<span data-ttu-id="bbf8f-236">Di seguito sono illustrati i flussi delle chiamate per due modalità:</span><span class="sxs-lookup"><span data-stu-id="bbf8f-236">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="bbf8f-237">Ignorare sempre</span><span class="sxs-lookup"><span data-stu-id="bbf8f-237">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="bbf8f-238">Solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="bbf8f-238">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="bbf8f-239">Modalità di bypass sempre</span><span class="sxs-lookup"><span data-stu-id="bbf8f-239">Always Bypass mode</span></span>

<span data-ttu-id="bbf8f-240">La modalità Ignora sempre è l'opzione più semplice da configurare.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-240">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="bbf8f-241">L'amministratore del tenant può configurare un singolo sito per tutti gli utenti e SBCs se tutti i SBCs sono raggiungibili da qualsiasi sito.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-241">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="bbf8f-242">Gli esempi mostrano sempre la modalità di bypass per gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbf8f-242">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="bbf8f-243">Le chiamate in uscita e l'utente si trova nella stessa posizione di SBC</span><span class="sxs-lookup"><span data-stu-id="bbf8f-243">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="bbf8f-244">Le chiamate in ingresso e l'utente si trova nella stessa posizione di SBC</span><span class="sxs-lookup"><span data-stu-id="bbf8f-244">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="bbf8f-245">Chiamate in uscita e l'utente è esterno</span><span class="sxs-lookup"><span data-stu-id="bbf8f-245">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="bbf8f-246">Chiamate in ingresso e l'utente è esterno</span><span class="sxs-lookup"><span data-stu-id="bbf8f-246">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="bbf8f-247">La tabella seguente mostra l'FQDN e gli indirizzi IP usati negli esempi:</span><span class="sxs-lookup"><span data-stu-id="bbf8f-247">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="bbf8f-248">FQDN</span><span class="sxs-lookup"><span data-stu-id="bbf8f-248">FQDN</span></span> | <span data-ttu-id="bbf8f-249">Indirizzo IP esterno SBC</span><span class="sxs-lookup"><span data-stu-id="bbf8f-249">SBC external IP address</span></span> | <span data-ttu-id="bbf8f-250">Indirizzo IP interno SBC</span><span class="sxs-lookup"><span data-stu-id="bbf8f-250">SBC internal IP Address</span></span> | <span data-ttu-id="bbf8f-251">Subnet interna</span><span class="sxs-lookup"><span data-stu-id="bbf8f-251">Internal subnet</span></span> | <span data-ttu-id="bbf8f-252">Posizione</span><span class="sxs-lookup"><span data-stu-id="bbf8f-252">Location</span></span> | <span data-ttu-id="bbf8f-253">NAT esterno (IP attendibile)</span><span class="sxs-lookup"><span data-stu-id="bbf8f-253">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="bbf8f-254">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bbf8f-254">VNsbc.contoso.com</span></span> | <span data-ttu-id="bbf8f-255">Nessuno</span><span class="sxs-lookup"><span data-stu-id="bbf8f-255">None</span></span> | <span data-ttu-id="bbf8f-256">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="bbf8f-256">192.168.1.5</span></span> | <span data-ttu-id="bbf8f-257">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="bbf8f-257">192.168.1.0/24</span></span> | <span data-ttu-id="bbf8f-258">Vietnam</span><span class="sxs-lookup"><span data-stu-id="bbf8f-258">Vietnam</span></span> | <span data-ttu-id="bbf8f-259">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="bbf8f-259">172.16.240.110</span></span> |
| <span data-ttu-id="bbf8f-260">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bbf8f-260">IDsbc.contoso.com</span></span> | <span data-ttu-id="bbf8f-261">Nessuno</span><span class="sxs-lookup"><span data-stu-id="bbf8f-261">None</span></span> | <span data-ttu-id="bbf8f-262">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="bbf8f-262">192.168.2.5</span></span> | <span data-ttu-id="bbf8f-263">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="bbf8f-263">192.168.2.0/24</span></span> | <span data-ttu-id="bbf8f-264">Indonesia</span><span class="sxs-lookup"><span data-stu-id="bbf8f-264">Indonesia</span></span> | <span data-ttu-id="bbf8f-265">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="bbf8f-265">172.16.240.120</span></span> |
| <span data-ttu-id="bbf8f-266">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bbf8f-266">proxysbc.contoso.com</span></span> | <span data-ttu-id="bbf8f-267">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="bbf8f-267">172.16.240.133</span></span> | <span data-ttu-id="bbf8f-268">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="bbf8f-268">192.168.3.5</span></span> | <span data-ttu-id="bbf8f-269">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="bbf8f-269">192.168.3.0/24</span></span> | <span data-ttu-id="bbf8f-270">Singapore</span><span class="sxs-lookup"><span data-stu-id="bbf8f-270">Singapore</span></span> | <span data-ttu-id="bbf8f-271">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="bbf8f-271">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="bbf8f-272">Le chiamate in uscita e l'utente si trova nella stessa posizione dell'SBC con bypass sempre</span><span class="sxs-lookup"><span data-stu-id="bbf8f-272">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="bbf8f-273">Modalità</span><span class="sxs-lookup"><span data-stu-id="bbf8f-273">Mode</span></span> |    <span data-ttu-id="bbf8f-274">Utente</span><span class="sxs-lookup"><span data-stu-id="bbf8f-274">User</span></span> |  <span data-ttu-id="bbf8f-275">Posizione</span><span class="sxs-lookup"><span data-stu-id="bbf8f-275">Location</span></span> |  <span data-ttu-id="bbf8f-276">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="bbf8f-276">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="bbf8f-277">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="bbf8f-277">AlwaysBypass</span></span> |    <span data-ttu-id="bbf8f-278">Interno</span><span class="sxs-lookup"><span data-stu-id="bbf8f-278">Internal</span></span> |  <span data-ttu-id="bbf8f-279">Lo stesso sito di SBC</span><span class="sxs-lookup"><span data-stu-id="bbf8f-279">The same site as SBC</span></span> |  <span data-ttu-id="bbf8f-280">Outbound</span><span class="sxs-lookup"><span data-stu-id="bbf8f-280">Outbound</span></span> |

<span data-ttu-id="bbf8f-281">La tabella seguente mostra la configurazione e l'azione degli utenti finali:</span><span class="sxs-lookup"><span data-stu-id="bbf8f-281">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="bbf8f-282">Posizione fisica dell'utente</span><span class="sxs-lookup"><span data-stu-id="bbf8f-282">User physical location</span></span>| <span data-ttu-id="bbf8f-283">L'utente effettua o riceve una chiamata a/da numero</span><span class="sxs-lookup"><span data-stu-id="bbf8f-283">User makes or receives a call to/from number</span></span> | <span data-ttu-id="bbf8f-284">Numero di telefono dell'utente</span><span class="sxs-lookup"><span data-stu-id="bbf8f-284">User phone number</span></span>  | <span data-ttu-id="bbf8f-285">Criteri di routing vocale online</span><span class="sxs-lookup"><span data-stu-id="bbf8f-285">Online Voice Routing Policy</span></span> | <span data-ttu-id="bbf8f-286">Modalità configurata per SBC</span><span class="sxs-lookup"><span data-stu-id="bbf8f-286">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="bbf8f-287">Vietnam</span><span class="sxs-lookup"><span data-stu-id="bbf8f-287">Vietnam</span></span> | <span data-ttu-id="bbf8f-288">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="bbf8f-288">+84 4 3926 3000</span></span> | <span data-ttu-id="bbf8f-289">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="bbf8f-289">+84 4 5555 5555</span></span>   | <span data-ttu-id="bbf8f-290">Priorità 1: ^\+84 (\d{9}) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bbf8f-290">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="bbf8f-291">Priorità 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bbf8f-291">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="bbf8f-292">VNsbc.contoso.com-ignora sempre</span><span class="sxs-lookup"><span data-stu-id="bbf8f-292">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="bbf8f-293">proxysbc.contoso.com-ignora sempre</span><span class="sxs-lookup"><span data-stu-id="bbf8f-293">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="bbf8f-294">Il diagramma seguente mostra la scala SIP per una chiamata in uscita con la modalità di bypass sempre e l'utente nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-294">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="bbf8f-295">![Diagramma che mostra le chiamate in uscita](media/direct-routing-media-op-10.png "Chiamate in uscita")</span><span class="sxs-lookup"><span data-stu-id="bbf8f-295">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="bbf8f-296">La tabella seguente mostra le intestazioni X-MS inviate tramite routing diretto:</span><span class="sxs-lookup"><span data-stu-id="bbf8f-296">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="bbf8f-297">Parametro</span><span class="sxs-lookup"><span data-stu-id="bbf8f-297">Parameter</span></span> | <span data-ttu-id="bbf8f-298">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="bbf8f-298">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="bbf8f-299">Invitare + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bbf8f-299">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="bbf8f-300">Il nome di destinazione dell'SBC come definito nei criteri di routing vocale online viene inviato nell'URI della richiesta</span><span class="sxs-lookup"><span data-stu-id="bbf8f-300">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="bbf8f-301">X-MS-UserLocation: Internal</span><span class="sxs-lookup"><span data-stu-id="bbf8f-301">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="bbf8f-302">Il campo indica che l'utente si trova all'interno della rete aziendale</span><span class="sxs-lookup"><span data-stu-id="bbf8f-302">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="bbf8f-303">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bbf8f-303">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="bbf8f-304">Specifica il SBC che deve essere attraversato dal client al SBC di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-304">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="bbf8f-305">In questo caso, come abbiamo sempre bypassare, e il client è interno il nome di destinazione inviato come unico nome nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-305">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="bbf8f-306">X-MS-UserSite: Vietnam</span><span class="sxs-lookup"><span data-stu-id="bbf8f-306">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="bbf8f-307">Campo indicato nel sito in cui si trova l'utente.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-307">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="bbf8f-308">Le chiamate in ingresso e l'utente si trova nella stessa posizione dell'SBC con il bypass sempre</span><span class="sxs-lookup"><span data-stu-id="bbf8f-308">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="bbf8f-309">Modalità</span><span class="sxs-lookup"><span data-stu-id="bbf8f-309">Mode</span></span> |    <span data-ttu-id="bbf8f-310">Utente</span><span class="sxs-lookup"><span data-stu-id="bbf8f-310">User</span></span> |  <span data-ttu-id="bbf8f-311">Posizione</span><span class="sxs-lookup"><span data-stu-id="bbf8f-311">Location</span></span> |  <span data-ttu-id="bbf8f-312">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="bbf8f-312">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="bbf8f-313">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="bbf8f-313">AlwaysBypass</span></span> |    <span data-ttu-id="bbf8f-314">Interno</span><span class="sxs-lookup"><span data-stu-id="bbf8f-314">Internal</span></span> | <span data-ttu-id="bbf8f-315">Lo stesso sito di SBC</span><span class="sxs-lookup"><span data-stu-id="bbf8f-315">The same site as SBC</span></span> | <span data-ttu-id="bbf8f-316">In ingresso</span><span class="sxs-lookup"><span data-stu-id="bbf8f-316">Inbound</span></span> |


<span data-ttu-id="bbf8f-317">In una chiamata in ingresso, la posizione dell'utente è sconosciuta e il SBC deve indovinare dove si trova l'utente.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-317">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="bbf8f-318">Se l'ipotesi non è corretta, sarà necessario un nuovo invito.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-318">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="bbf8f-319">Questo caso presuppone che l'utente sia interno, che l'elemento multimediale possa fluire direttamente e che non siano necessarie altre azioni (re-INVITE).</span><span class="sxs-lookup"><span data-stu-id="bbf8f-319">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="bbf8f-320">Il SBC connesso al servizio di routing diretto riporta la posizione del SBC di origine fornendo campi di record-route e Contact.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-320">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="bbf8f-321">In base a questi campi, il percorso del supporto viene calcolato tramite routing diretto.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-321">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="bbf8f-322">Nota: dato che un utente può avere più endpoint, il supporto di 183 non è possibile.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-322">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="bbf8f-323">Il routing diretto userà sempre 180 squillare in questo caso.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-323">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="bbf8f-324">Il diagramma seguente mostra la scala SIP per la chiamata in ingresso con la modalità AlwaysBypass e l'utente si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-324">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="bbf8f-326">Chiamate in uscita e l'utente è esterno con l'esclusione sempre</span><span class="sxs-lookup"><span data-stu-id="bbf8f-326">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="bbf8f-327">Modalità</span><span class="sxs-lookup"><span data-stu-id="bbf8f-327">Mode</span></span> |    <span data-ttu-id="bbf8f-328">Utente</span><span class="sxs-lookup"><span data-stu-id="bbf8f-328">User</span></span> |  <span data-ttu-id="bbf8f-329">Sito</span><span class="sxs-lookup"><span data-stu-id="bbf8f-329">Site</span></span> |  <span data-ttu-id="bbf8f-330">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="bbf8f-330">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="bbf8f-331">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="bbf8f-331">AlwaysBypass</span></span> |  <span data-ttu-id="bbf8f-332">Esterno</span><span class="sxs-lookup"><span data-stu-id="bbf8f-332">External</span></span> |  <span data-ttu-id="bbf8f-333">N/D</span><span class="sxs-lookup"><span data-stu-id="bbf8f-333">N/A</span></span> | <span data-ttu-id="bbf8f-334">Outbound</span><span class="sxs-lookup"><span data-stu-id="bbf8f-334">Outbound</span></span> |


<span data-ttu-id="bbf8f-335">Il diagramma seguente mostra la scala SIP per una chiamata in uscita con la modalità AlwaysBypass e l'utente è esterno:</span><span class="sxs-lookup"><span data-stu-id="bbf8f-335">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-12.png)

<span data-ttu-id="bbf8f-337">La tabella seguente mostra le intestazioni X-MS inviate dal servizio di routing diretto:</span><span class="sxs-lookup"><span data-stu-id="bbf8f-337">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="bbf8f-338">Parametro</span><span class="sxs-lookup"><span data-stu-id="bbf8f-338">Parameter</span></span> |   <span data-ttu-id="bbf8f-339">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="bbf8f-339">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="bbf8f-340">Invitare + 8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bbf8f-340">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="bbf8f-341">Il nome di destinazione dell'SBC come definito nei criteri di routing vocale online viene inviato nell'URI della richiesta.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-341">The target name of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="bbf8f-342">X-MS-UserLocation: esterno</span><span class="sxs-lookup"><span data-stu-id="bbf8f-342">X-MS-UserLocation: external</span></span> | <span data-ttu-id="bbf8f-343">Il campo indica che l'utente si trova all'esterno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-343">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="bbf8f-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bbf8f-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="bbf8f-345">Specifica il SBC che deve essere attraversato dal client al SBC di destinazione.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-345">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="bbf8f-346">In questo caso, come abbiamo sempre bypassare, e il client è esterno.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-346">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="bbf8f-347">Chiamate in ingresso e l'utente è esterno con il bypass sempre</span><span class="sxs-lookup"><span data-stu-id="bbf8f-347">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="bbf8f-348">Modalità</span><span class="sxs-lookup"><span data-stu-id="bbf8f-348">Mode</span></span> | <span data-ttu-id="bbf8f-349">Utente</span><span class="sxs-lookup"><span data-stu-id="bbf8f-349">User</span></span> | <span data-ttu-id="bbf8f-350">Sito</span><span class="sxs-lookup"><span data-stu-id="bbf8f-350">Site</span></span> |  <span data-ttu-id="bbf8f-351">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="bbf8f-351">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="bbf8f-352">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="bbf8f-352">AlwaysBypass</span></span> |  <span data-ttu-id="bbf8f-353">Esterno</span><span class="sxs-lookup"><span data-stu-id="bbf8f-353">External</span></span> |  <span data-ttu-id="bbf8f-354">N/D</span><span class="sxs-lookup"><span data-stu-id="bbf8f-354">N/A</span></span> |   <span data-ttu-id="bbf8f-355">In ingresso</span><span class="sxs-lookup"><span data-stu-id="bbf8f-355">Inbound</span></span> |

<span data-ttu-id="bbf8f-356">Per una chiamata in ingresso, il SBC connesso al routing diretto deve inviare un re-invite (per impostazione predefinita, i candidati multimediali locali sono sempre offerti) se la posizione dell'utente è esterna.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-356">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="bbf8f-357">L'X-MediaPath viene calcolato in base a record-route e all'utente SBC specificato.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-357">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="bbf8f-358">Il diagramma seguente mostra la scala SIP per una chiamata in ingresso con la modalità AlwaysBypass e l'utente è esterno.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-358">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="bbf8f-360">Solo per la modalità utenti locali</span><span class="sxs-lookup"><span data-stu-id="bbf8f-360">Only for local users mode</span></span>

<span data-ttu-id="bbf8f-361">I candidati multimediali locali del SBC di destinazione verranno offerti solo se un utente si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-361">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="bbf8f-362">In tutti gli altri casi, il flusso multimediale verrà eseguito attraverso un IP interno o esterno del SBC proxy.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-362">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="bbf8f-363">Vengono descritti gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="bbf8f-363">The following scenarios are described:</span></span>

- [<span data-ttu-id="bbf8f-364">Le chiamate in uscita e l'utente si trova nella stessa posizione di SBC</span><span class="sxs-lookup"><span data-stu-id="bbf8f-364">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="bbf8f-365">Le chiamate in ingresso e l'utente si trova nella stessa posizione di SBC</span><span class="sxs-lookup"><span data-stu-id="bbf8f-365">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="bbf8f-366">L'utente non si trova nella stessa posizione di SBC, ma nella rete aziendale</span><span class="sxs-lookup"><span data-stu-id="bbf8f-366">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="bbf8f-367">Le chiamate in ingresso e l'utente sono interne, ma non si trova nella stessa posizione di SBC</span><span class="sxs-lookup"><span data-stu-id="bbf8f-367">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="bbf8f-368">La tabella seguente mostra la configurazione e l'azione degli utenti finali:</span><span class="sxs-lookup"><span data-stu-id="bbf8f-368">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="bbf8f-369">Posizione fisica dell'utente</span><span class="sxs-lookup"><span data-stu-id="bbf8f-369">User physical location</span></span> |  <span data-ttu-id="bbf8f-370">L'utente effettua o riceve una chiamata a/da numero</span><span class="sxs-lookup"><span data-stu-id="bbf8f-370">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="bbf8f-371">Numero di telefono dell'utente</span><span class="sxs-lookup"><span data-stu-id="bbf8f-371">User phone number</span></span> | <span data-ttu-id="bbf8f-372">Criteri di routing vocale online</span><span class="sxs-lookup"><span data-stu-id="bbf8f-372">Online Voice Routing Policy</span></span> |   <span data-ttu-id="bbf8f-373">Modalità configurata per SBC</span><span class="sxs-lookup"><span data-stu-id="bbf8f-373">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="bbf8f-374">Vietnam</span><span class="sxs-lookup"><span data-stu-id="bbf8f-374">Vietnam</span></span> | <span data-ttu-id="bbf8f-375">+ 84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="bbf8f-375">+84 4 3926  3000</span></span> |  <span data-ttu-id="bbf8f-376">+ 84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="bbf8f-376">+84 4 5555 5555</span></span> | <span data-ttu-id="bbf8f-377">Priorità 1: ^\+84 (\d{9}) $-VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bbf8f-377">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="bbf8f-378">Priorità 2:. \*-proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="bbf8f-378">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="bbf8f-379">VNsbc.contoso.com-OnlyForLocalUsers Proxysbc.contoso.com-ignora sempre</span><span class="sxs-lookup"><span data-stu-id="bbf8f-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="bbf8f-380">Le chiamate in uscita e l'utente si trova nella stessa posizione del SBC con solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="bbf8f-380">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="bbf8f-381">Modalità</span><span class="sxs-lookup"><span data-stu-id="bbf8f-381">Mode</span></span> | <span data-ttu-id="bbf8f-382">Utente</span><span class="sxs-lookup"><span data-stu-id="bbf8f-382">User</span></span> | <span data-ttu-id="bbf8f-383">Sito</span><span class="sxs-lookup"><span data-stu-id="bbf8f-383">Site</span></span> | <span data-ttu-id="bbf8f-384">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="bbf8f-384">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="bbf8f-385">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="bbf8f-385">OnlyForLocalUsers</span></span> |   <span data-ttu-id="bbf8f-386">Interno</span><span class="sxs-lookup"><span data-stu-id="bbf8f-386">Internal</span></span> |<span data-ttu-id="bbf8f-387">Uguale a SBC</span><span class="sxs-lookup"><span data-stu-id="bbf8f-387">Same as SBC</span></span>   | <span data-ttu-id="bbf8f-388">Outbound</span><span class="sxs-lookup"><span data-stu-id="bbf8f-388">Outbound</span></span> |

<span data-ttu-id="bbf8f-389">Il diagramma seguente mostra una chiamata in uscita con la modalità OnlyForLocalUsers e l'utente si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-389">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="bbf8f-390">Si tratta dello stesso flusso visualizzato nelle [chiamate in uscita quando l'utente si trova nella stessa posizione di SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="bbf8f-390">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="bbf8f-392">Le chiamate in ingresso e l'utente si trova nella stessa posizione del SBC con solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="bbf8f-392">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="bbf8f-393">Modalità</span><span class="sxs-lookup"><span data-stu-id="bbf8f-393">Mode</span></span> | <span data-ttu-id="bbf8f-394">Utente</span><span class="sxs-lookup"><span data-stu-id="bbf8f-394">User</span></span> | <span data-ttu-id="bbf8f-395">Sito</span><span class="sxs-lookup"><span data-stu-id="bbf8f-395">Site</span></span> | <span data-ttu-id="bbf8f-396">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="bbf8f-396">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="bbf8f-397">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="bbf8f-397">OnlyForLocalUsers</span></span> |   <span data-ttu-id="bbf8f-398">Interno</span><span class="sxs-lookup"><span data-stu-id="bbf8f-398">Internal</span></span> | <span data-ttu-id="bbf8f-399">Uguale a SBC</span><span class="sxs-lookup"><span data-stu-id="bbf8f-399">Same as SBC</span></span> | <span data-ttu-id="bbf8f-400">In ingresso</span><span class="sxs-lookup"><span data-stu-id="bbf8f-400">Inbound</span></span> |

<span data-ttu-id="bbf8f-401">Il diagramma seguente mostra una chiamata in ingresso con la modalità OnlyForLocalUsers e l'utente si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-401">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="bbf8f-402">Si tratta dello stesso flusso illustrato nelle [chiamate in ingresso quando l'utente si trova nella stessa posizione di SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span><span class="sxs-lookup"><span data-stu-id="bbf8f-402">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="bbf8f-404">L'utente non si trova nella stessa posizione di SBC, ma è nella rete aziendale solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="bbf8f-404">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="bbf8f-405">Modalità</span><span class="sxs-lookup"><span data-stu-id="bbf8f-405">Mode</span></span> | <span data-ttu-id="bbf8f-406">Utente</span><span class="sxs-lookup"><span data-stu-id="bbf8f-406">User</span></span> | <span data-ttu-id="bbf8f-407">Sito</span><span class="sxs-lookup"><span data-stu-id="bbf8f-407">Site</span></span> |<span data-ttu-id="bbf8f-408">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="bbf8f-408">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="bbf8f-409">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="bbf8f-409">OnlyForLocalUsers</span></span>  | <span data-ttu-id="bbf8f-410">Interno</span><span class="sxs-lookup"><span data-stu-id="bbf8f-410">Internal</span></span> |   <span data-ttu-id="bbf8f-411">Diverso da SBC</span><span class="sxs-lookup"><span data-stu-id="bbf8f-411">Different from SBC</span></span> | <span data-ttu-id="bbf8f-412">Outbound</span><span class="sxs-lookup"><span data-stu-id="bbf8f-412">Outbound</span></span> |

<span data-ttu-id="bbf8f-413">Il routing diretto calcola X-MediaPath in base alla posizione segnalata dell'utente e alla modalità configurata in SBC.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-413">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="bbf8f-414">Il diagramma seguente mostra una chiamata in uscita con la modalità OnlyForLocalUsers e un utente interno che non si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-414">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="bbf8f-416">Chiamata in ingresso e l'utente è interno, ma non è nella stessa posizione dell'SBC con solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="bbf8f-416">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="bbf8f-417">Modalità</span><span class="sxs-lookup"><span data-stu-id="bbf8f-417">Mode</span></span> |    <span data-ttu-id="bbf8f-418">Utente</span><span class="sxs-lookup"><span data-stu-id="bbf8f-418">User</span></span> |  <span data-ttu-id="bbf8f-419">Sito</span><span class="sxs-lookup"><span data-stu-id="bbf8f-419">Site</span></span> |  <span data-ttu-id="bbf8f-420">Direzione chiamata</span><span class="sxs-lookup"><span data-stu-id="bbf8f-420">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="bbf8f-421">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="bbf8f-421">OnlyForLocalUsers</span></span> | <span data-ttu-id="bbf8f-422">Interno</span><span class="sxs-lookup"><span data-stu-id="bbf8f-422">Internal</span></span> |    <span data-ttu-id="bbf8f-423">Diverso da SBC</span><span class="sxs-lookup"><span data-stu-id="bbf8f-423">Different from SBC</span></span> |    <span data-ttu-id="bbf8f-424">In ingresso</span><span class="sxs-lookup"><span data-stu-id="bbf8f-424">Inbound</span></span> |

<span data-ttu-id="bbf8f-425">Il diagramma seguente mostra una chiamata in ingresso con la modalità OnlyForLocalUsers e un utente interno che non si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="bbf8f-425">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-17.png)









