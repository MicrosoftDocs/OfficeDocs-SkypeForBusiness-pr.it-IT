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
# <a name="configure-local-media-optimization-for-direct-routing"></a><span data-ttu-id="5e0ea-103">Configurare l'ottimizzazione del supporto locale per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="5e0ea-103">Configure Local Media Optimization for Direct Routing</span></span>

<span data-ttu-id="5e0ea-104">La configurazione per l'ottimizzazione multimediale locale si basa su impostazioni di rete comuni ad altre funzionalità vocali cloud, ad esempio routing Location-Based e chiamate di emergenza dinamiche.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-104">Configuration for Local Media Optimization is based on network settings that are common to other cloud voice features, such as Location-Based Routing and dynamic emergency calling.</span></span> <span data-ttu-id="5e0ea-105">Per altre informazioni sulle aree di rete, i siti di rete, le subnet di rete e gli indirizzi IP attendibili, vedere Impostazioni di rete [per le funzionalità vocali cloud.](cloud-voice-network-settings.md)</span><span class="sxs-lookup"><span data-stu-id="5e0ea-105">To learn more about network regions, network sites, network subnets, and trusted IP addresses, see [Network settings for cloud voice features](cloud-voice-network-settings.md).</span></span>

<span data-ttu-id="5e0ea-106">Prima di configurare l'ottimizzazione del supporto locale, vedere [Ottimizzazione dei supporti locali per il routing diretto.](direct-routing-media-optimization.md)</span><span class="sxs-lookup"><span data-stu-id="5e0ea-106">Before you configure Local Media Optimization, see [Local media Optimization for Direct Routing](direct-routing-media-optimization.md).</span></span>  

<span data-ttu-id="5e0ea-107">Per configurare l'ottimizzazione del supporto locale, sono necessari i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-107">To configure Local Media Optimization, the following steps are required.</span></span> <span data-ttu-id="5e0ea-108">È possibile usare l'Teams di amministrazione o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-108">You can use the Teams Admin Center or PowerShell.</span></span> <span data-ttu-id="5e0ea-109">Per informazioni dettagliate, vedere [Gestire la topologia di rete.](manage-your-network-topology.md)</span><span class="sxs-lookup"><span data-stu-id="5e0ea-109">For details, see [Manage your network topology](manage-your-network-topology.md).</span></span>

1. <span data-ttu-id="5e0ea-110">Configurare l'utente e i siti SBC (come descritto in questo articolo).</span><span class="sxs-lookup"><span data-stu-id="5e0ea-110">Configure the user and the SBC sites (as described in this article).</span></span>
2. <span data-ttu-id="5e0ea-111">Configurare gli SBC per l'ottimizzazione dei supporti locali (in base alle specifiche del fornitore SBC).</span><span class="sxs-lookup"><span data-stu-id="5e0ea-111">Configure the SBCs for Local Media Optimization (according to your SBC vendor specification).</span></span>

<span data-ttu-id="5e0ea-112">Il diagramma seguente mostra la configurazione di rete usata negli esempi di questo articolo.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-112">The following diagram shows the network setup used in the examples throughout this article.</span></span>

<span data-ttu-id="5e0ea-113">![Diagramma che mostra la configurazione della rete per esempi](media/direct-routing-media-op-9.png "Configurazione di rete per esempi")</span><span class="sxs-lookup"><span data-stu-id="5e0ea-113">![Diagram showing network setup for examples](media/direct-routing-media-op-9.png "Network setup for examples")</span></span>


## <a name="configure-the-user-and-the-sbc-sites"></a><span data-ttu-id="5e0ea-114">Configurare l'utente e i siti SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-114">Configure the user and the SBC sites</span></span>

<span data-ttu-id="5e0ea-115">Per configurare l'utente e i siti SBC, è necessario:</span><span class="sxs-lookup"><span data-stu-id="5e0ea-115">To configure the user and the SBC sites, you will need to:</span></span>

1. <span data-ttu-id="5e0ea-116">[Gestire gli indirizzi IP attendibili esterni](#manage-external-trusted-ip-addresses).</span><span class="sxs-lookup"><span data-stu-id="5e0ea-116">[Manage external trusted IP addresses](#manage-external-trusted-ip-addresses).</span></span>  

2. <span data-ttu-id="5e0ea-117">[Definire la topologia di rete](#define-the-network-topology) configurando le aree di rete, i siti di rete e le subnet di rete.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-117">[Define the network topology](#define-the-network-topology) by configuring the network regions, network sites, and network subnets.</span></span>

3. <span data-ttu-id="5e0ea-118">[Definire la topologia della rete virtuale](#define-the-virtual-network-topology) assegnando SBC ai siti con modalità pertinenti e valori SBC proxy.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-118">[Define the virtual network topology](#define-the-virtual-network-topology) by assigning SBC(s) to site(s) with relevant modes and proxy SBC values.</span></span>


## <a name="configure-sbcs-for-local-media-optimization-according-to-the-sbc-vendor-specification"></a><span data-ttu-id="5e0ea-119">Configurare SBC(s) per l'ottimizzazione dei supporti locali in base alla specifica del fornitore SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-119">Configure SBC(s) for Local Media Optimization according to the SBC vendor specification</span></span>

<span data-ttu-id="5e0ea-120">Questo articolo descrive la configurazione per i componenti Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-120">This article describes configuration for Microsoft components.</span></span> <span data-ttu-id="5e0ea-121">Per informazioni sulla configurazione SBC, vedere la documentazione del fornitore SBC.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-121">For information on SBC configuration, see your SBC vendor documentation.</span></span>

<span data-ttu-id="5e0ea-122">L'ottimizzazione multimediale locale è supportata dai fornitori SBC seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e0ea-122">Local Media Optimization is supported by the following SBC vendors:</span></span>

| <span data-ttu-id="5e0ea-123">Fornitore</span><span class="sxs-lookup"><span data-stu-id="5e0ea-123">Vendor</span></span> | <span data-ttu-id="5e0ea-124">Prodotto</span><span class="sxs-lookup"><span data-stu-id="5e0ea-124">Product</span></span> |    <span data-ttu-id="5e0ea-125">Versione software</span><span class="sxs-lookup"><span data-stu-id="5e0ea-125">Software version</span></span> |
|:------------|:-------|:-------|
| [<span data-ttu-id="5e0ea-126">Audiocodice</span><span class="sxs-lookup"><span data-stu-id="5e0ea-126">Audiocodes</span></span>](https://www.audiocodes.com/media/13253/connecting-audiocodes-sbc-to-microsoft-teams-direct-routing-enterprise-model-configuration-note.pdf) |    <span data-ttu-id="5e0ea-127">Mediant 500 SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-127">Mediant 500 SBC</span></span> |   <span data-ttu-id="5e0ea-128">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="5e0ea-128">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5e0ea-129">Mediant 800 SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-129">Mediant 800 SBC</span></span> |   <span data-ttu-id="5e0ea-130">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="5e0ea-130">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5e0ea-131">Mediant 2600 SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-131">Mediant 2600 SBC</span></span> |  <span data-ttu-id="5e0ea-132">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="5e0ea-132">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5e0ea-133">Mediant 4000 SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-133">Mediant 4000 SBC</span></span> |  <span data-ttu-id="5e0ea-134">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="5e0ea-134">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5e0ea-135">Mediant 1000B SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-135">Mediant 1000B SBC</span></span> | <span data-ttu-id="5e0ea-136">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="5e0ea-136">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5e0ea-137">Mediant 9000 SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-137">Mediant 9000 SBC</span></span> |  <span data-ttu-id="5e0ea-138">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="5e0ea-138">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5e0ea-139">Mediant Virtual Edition SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-139">Mediant Virtual Edition SBC</span></span> |   <span data-ttu-id="5e0ea-140">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="5e0ea-140">7.20A.256</span></span> | 
|            |  <span data-ttu-id="5e0ea-141">Mediant Cloud Edition SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-141">Mediant Cloud Edition SBC</span></span> | <span data-ttu-id="5e0ea-142">7.20A.256</span><span class="sxs-lookup"><span data-stu-id="5e0ea-142">7.20A.256</span></span> |
| [<span data-ttu-id="5e0ea-143">Componente di base SBC della barra multifunzione</span><span class="sxs-lookup"><span data-stu-id="5e0ea-143">Ribbon SBC Core</span></span>](https://support.sonus.net/display/ALLDOC/SBC+8.2+-+Configure+Local+Media+Optimization)  |  <span data-ttu-id="5e0ea-144">SBC 5110</span><span class="sxs-lookup"><span data-stu-id="5e0ea-144">SBC 5110</span></span>         | <span data-ttu-id="5e0ea-145">8.2</span><span class="sxs-lookup"><span data-stu-id="5e0ea-145">8.2</span></span>  |
|            |  <span data-ttu-id="5e0ea-146">SBC 5210</span><span class="sxs-lookup"><span data-stu-id="5e0ea-146">SBC 5210</span></span>         | <span data-ttu-id="5e0ea-147">8.2</span><span class="sxs-lookup"><span data-stu-id="5e0ea-147">8.2</span></span>  |
|            |  <span data-ttu-id="5e0ea-148">SBC 5400</span><span class="sxs-lookup"><span data-stu-id="5e0ea-148">SBC 5400</span></span>         | <span data-ttu-id="5e0ea-149">8.2</span><span class="sxs-lookup"><span data-stu-id="5e0ea-149">8.2</span></span>  |
|            |  <span data-ttu-id="5e0ea-150">SBC 7000</span><span class="sxs-lookup"><span data-stu-id="5e0ea-150">SBC 7000</span></span>         | <span data-ttu-id="5e0ea-151">8.2</span><span class="sxs-lookup"><span data-stu-id="5e0ea-151">8.2</span></span>  |
|            |  <span data-ttu-id="5e0ea-152">SBC SWe</span><span class="sxs-lookup"><span data-stu-id="5e0ea-152">SBC SWe</span></span>          | <span data-ttu-id="5e0ea-153">8.2</span><span class="sxs-lookup"><span data-stu-id="5e0ea-153">8.2</span></span>  |
| [<span data-ttu-id="5e0ea-154">Bordo SBC della barra multifunzione</span><span class="sxs-lookup"><span data-stu-id="5e0ea-154">Ribbon SBC Edge</span></span>](https://support.sonus.net/display/UXDOC81/Best+Practice+-+Configuring+Microsoft+Teams+Local+Media+Optimization)  |  <span data-ttu-id="5e0ea-155">SBC SWe Lite</span><span class="sxs-lookup"><span data-stu-id="5e0ea-155">SBC SWe Lite</span></span> | <span data-ttu-id="5e0ea-156">8.1.5</span><span class="sxs-lookup"><span data-stu-id="5e0ea-156">8.1.5</span></span> |
|               | <span data-ttu-id="5e0ea-157">SBC 1000</span><span class="sxs-lookup"><span data-stu-id="5e0ea-157">SBC 1000</span></span> | <span data-ttu-id="5e0ea-158">8.1.5</span><span class="sxs-lookup"><span data-stu-id="5e0ea-158">8.1.5</span></span>  |
|               | <span data-ttu-id="5e0ea-159">SBC 2000</span><span class="sxs-lookup"><span data-stu-id="5e0ea-159">SBC 2000</span></span> | <span data-ttu-id="5e0ea-160">8.1.5</span><span class="sxs-lookup"><span data-stu-id="5e0ea-160">8.1.5</span></span>  |
| [<span data-ttu-id="5e0ea-161">TE-SYSTEMS</span><span class="sxs-lookup"><span data-stu-id="5e0ea-161">TE-SYSTEMS</span></span>](https://www.anynode.de/local_media_optimization/) |  <span data-ttu-id="5e0ea-162">anynode</span><span class="sxs-lookup"><span data-stu-id="5e0ea-162">anynode</span></span>          | <span data-ttu-id="5e0ea-163">4.0.1+</span><span class="sxs-lookup"><span data-stu-id="5e0ea-163">4.0.1+</span></span> |
| [<span data-ttu-id="5e0ea-164">Oracle</span><span class="sxs-lookup"><span data-stu-id="5e0ea-164">Oracle</span></span>](https://www.oracle.com/industries/communications/enterprise-communications/session-border-controller/microsoft.html) | <span data-ttu-id="5e0ea-165">AP 1100</span><span class="sxs-lookup"><span data-stu-id="5e0ea-165">AP 1100</span></span> | <span data-ttu-id="5e0ea-166">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="5e0ea-166">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="5e0ea-167">AP 3900</span><span class="sxs-lookup"><span data-stu-id="5e0ea-167">AP 3900</span></span> | <span data-ttu-id="5e0ea-168">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="5e0ea-168">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="5e0ea-169">AP 4600</span><span class="sxs-lookup"><span data-stu-id="5e0ea-169">AP 4600</span></span> | <span data-ttu-id="5e0ea-170">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="5e0ea-170">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="5e0ea-171">AP 6300</span><span class="sxs-lookup"><span data-stu-id="5e0ea-171">AP 6300</span></span> | <span data-ttu-id="5e0ea-172">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="5e0ea-172">8.4.0.0.0</span></span> |
|        | <span data-ttu-id="5e0ea-173">AP 6350</span><span class="sxs-lookup"><span data-stu-id="5e0ea-173">AP 6350</span></span> | <span data-ttu-id="5e0ea-174">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="5e0ea-174">8.4.0.0.0</span></span> | 
|        | <span data-ttu-id="5e0ea-175">VME</span><span class="sxs-lookup"><span data-stu-id="5e0ea-175">VME</span></span>     | <span data-ttu-id="5e0ea-176">8.4.0.0.0</span><span class="sxs-lookup"><span data-stu-id="5e0ea-176">8.4.0.0.0</span></span> |


## <a name="manage-external-trusted-ip-addresses"></a><span data-ttu-id="5e0ea-177">Gestire indirizzi IP attendibili esterni</span><span class="sxs-lookup"><span data-stu-id="5e0ea-177">Manage external trusted IP addresses</span></span>

<span data-ttu-id="5e0ea-178">Gli INDIRIZZI IP attendibili esterni sono gli INDIRIZZI IP esterni Internet della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-178">External trusted IPs are the Internet external IPs of the enterprise network.</span></span> <span data-ttu-id="5e0ea-179">Questi indirizzi IP sono gli indirizzi IP usati dai client Microsoft Teams quando si connettono a Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-179">These IP’s are the IP addresses used by Microsoft Teams clients when they connect to Microsoft 365.</span></span> <span data-ttu-id="5e0ea-180">È necessario aggiungere questi IP esterni per ogni sito in cui si hanno utenti che usano l'ottimizzazione del supporto locale.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-180">You need to add these external IPs for each site where you have users using Local Media Optimization.</span></span>

<span data-ttu-id="5e0ea-181">Per aggiungere gli indirizzi IP pubblici per ogni sito, usare il cmdlet New-CsTenantTrustedIPAddress.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-181">To add the public IP addresses for each site, use the New-CsTenantTrustedIPAddress cmdlet.</span></span> <span data-ttu-id="5e0ea-182">È possibile definire un numero illimitato di indirizzi IP attendibili per un tenant.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-182">You can define an unlimited number of trusted IP addresses for a tenant.</span></span> <span data-ttu-id="5e0ea-183">Se gli INDIRIZZI IP esterni visti Microsoft 365 indirizzi IPv4 e IPv6, è necessario aggiungere entrambi i tipi di indirizzi IP.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-183">If the external IPs seen by Microsoft 365 are both IPv4 and IPv6 addresses, you need to add both types of IP addresses.</span></span> <span data-ttu-id="5e0ea-184">Per IPv4, usare la maschera 32.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-184">For IPv4, use mask 32.</span></span> <span data-ttu-id="5e0ea-185">Per IPv6, usare la maschera 128.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-185">For IPv6, use mask 128.</span></span> <span data-ttu-id="5e0ea-186">È possibile aggiungere sia singoli indirizzi IP esterni che subnet IP esterne specificando maskBit diversi nel cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-186">You can add both individual external IP addresses and external IP subnets by specifying different MaskBits on the cmdlet.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress <External IP address> -MaskBits <Subnet bitmask> -Description <description>
```


<span data-ttu-id="5e0ea-187">Esempio di aggiunta di indirizzi IP attendibili.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-187">Example of adding trusted IP addresses.</span></span>

```
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.110 -MaskBits 32 -Description "Vietnam site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.120 -MaskBits 32 -Description "Indonesia site trusted IP"
New-CsTenantTrustedIPAddress -IPAddress 172.16.240.130 -MaskBits 32 -Description "Singapore site trusted IP"
```


## <a name="define-the-network-topology"></a><span data-ttu-id="5e0ea-188">Definire la topologia di rete</span><span class="sxs-lookup"><span data-stu-id="5e0ea-188">Define the network topology</span></span>

<span data-ttu-id="5e0ea-189">Questa sezione descrive come definire le aree di rete, i siti di rete e le subnet di rete per la topologia di rete.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-189">This section describes how to define the network regions, network sites, and network subnets for your network topology.</span></span>

<span data-ttu-id="5e0ea-190">Per tutti i parametri viene fatto distinzione tra maiuscole e minuscole, quindi è necessario assicurarsi di usare lo stesso caso usato durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-190">All parameters are case sensitive so you need to ensure that you use the same case that was used during setup.</span></span>  <span data-ttu-id="5e0ea-191">Ad esempio, i valori gatewaySiteID "Vietnam" e "vietnam" verranno trattati come siti diversi.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-191">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

### <a name="define-network-regions"></a><span data-ttu-id="5e0ea-192">Definire le aree di rete</span><span class="sxs-lookup"><span data-stu-id="5e0ea-192">Define network regions</span></span>

<span data-ttu-id="5e0ea-193">Per definire le aree di rete, usare il cmdlet New-CsTenantNetworkRegion rete.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-193">To define network regions, use the New-CsTenantNetworkRegion cmdlet.</span></span> <span data-ttu-id="5e0ea-194">Il parametro RegionID è un nome logico che rappresenta la geografia dell'area geografica e non ha dipendenze o restrizioni.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-194">The RegionID parameter is a logical name that represents the geography of the region and has no dependencies or restrictions.</span></span> <span data-ttu-id="5e0ea-195">Il parametro CentralSite <site ID> è facoltativo.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-195">The CentralSite <site ID> parameter is optional.</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID <region ID>  
```

<span data-ttu-id="5e0ea-196">L'esempio seguente crea un'area di rete denominata APAC:</span><span class="sxs-lookup"><span data-stu-id="5e0ea-196">The following example creates a network region named APAC:</span></span>

```
New-CsTenantNetworkRegion -NetworkRegionID "APAC"  
```

###  <a name="define-network-sites"></a><span data-ttu-id="5e0ea-197">Definire i siti di rete</span><span class="sxs-lookup"><span data-stu-id="5e0ea-197">Define network sites</span></span>

<span data-ttu-id="5e0ea-198">Per definire i siti di rete, usare il cmdlet New-CsTenantNetworkSite rete.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-198">To define network sites, use the New-CsTenantNetworkSite cmdlet.</span></span> <span data-ttu-id="5e0ea-199">Ogni sito di rete deve essere associato a un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-199">Each network site must be associated with a network region.</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID <site ID> -NetworkRegionID <region ID>
```

<span data-ttu-id="5e0ea-200">L'esempio seguente crea tre nuovi siti di rete, Vietnam, Indonesia e Singapore nell'area APAC:</span><span class="sxs-lookup"><span data-stu-id="5e0ea-200">The following example creates three new network sites, Vietnam, Indonesia, and Singapore in the APAC region:</span></span>

```
New-CsTenantNetworkSite -NetworkSiteID "Vietnam" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Indonesia" -NetworkRegionID "APAC"
New-CsTenantNetworkSite -NetworkSiteID "Singapore" -NetworkRegionID "APAC"
```

### <a name="define-network-subnets"></a><span data-ttu-id="5e0ea-201">Definire subnet di rete</span><span class="sxs-lookup"><span data-stu-id="5e0ea-201">Define network subnets</span></span>

<span data-ttu-id="5e0ea-202">Per definire subnet di rete e associarle ai siti di rete, usare il cmdlet New-CsTenantNetworkSubnet rete.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-202">To define network subnets and associate them to network sites, use the New-CsTenantNetworkSubnet cmdlet.</span></span> <span data-ttu-id="5e0ea-203">Ogni subnet di rete può essere associata a un solo sito.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-203">Each network subnet can only be associated with one site.</span></span> 

```
New-CsTenantNetworkSubnet -SubnetID <Subnet IP address> -MaskBits <Subnet bitmask> -NetworkSiteID <site ID>
```

<span data-ttu-id="5e0ea-204">L'esempio seguente definisce tre subnet di rete e le associa ai tre siti di rete: Vietnam, Indonesia e Singapore:</span><span class="sxs-lookup"><span data-stu-id="5e0ea-204">The following example defines three network subnets and associates them with the three network sites:  Vietnam, Indonesia, and Singapore:</span></span>

```
New-CsTenantNetworkSubnet -SubnetID 192.168.1.0 -MaskBits 24 -NetworkSiteID “Vietnam”
New-CsTenantNetworkSubnet -SubnetID 192.168.2.0 -MaskBits 24 -NetworkSiteID “Indonesia”
New-CsTenantNetworkSubnet -SubnetID 192.168.3.0 -MaskBits 24 -NetworkSiteID “Singapore”
```

## <a name="define-the-virtual-network-topology"></a><span data-ttu-id="5e0ea-205">Definire la topologia della rete virtuale</span><span class="sxs-lookup"><span data-stu-id="5e0ea-205">Define the virtual network topology</span></span> 

<span data-ttu-id="5e0ea-206">Prima di tutto, l'amministratore tenant crea una nuova configurazione SBC per ogni SBC pertinente usando il cmdlet New-CsOnlinePSTNGateway tenant.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-206">First, the tenant administrator creates a new SBC configuration for each relevant SBC by using the New-CsOnlinePSTNGateway cmdlet.</span></span>
<span data-ttu-id="5e0ea-207">L'amministratore tenant definisce la topologia della rete virtuale specificando i siti di rete per gli oggetti gateway PSTN usando il cmdlet Set-CsOnlinePSTNGateway:</span><span class="sxs-lookup"><span data-stu-id="5e0ea-207">The tenant administrator defines the virtual network topology by specifying the network sites for the PSTN gateway objects using the Set-CsOnlinePSTNGateway cmdlet:</span></span>

```
PS C:\> Set-CsOnlinePSTNGateway -Identity <Identity> -GatewaySiteID <site ID> -MediaBypass <true/false> -BypassMode <Always/OnlyForLocalUsers> -ProxySBC  <proxy SBC FQDN or $null>
```

<span data-ttu-id="5e0ea-208">Tenere presente quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5e0ea-208">Note the following:</span></span> 
   - <span data-ttu-id="5e0ea-209">Se il cliente ha un singolo SBC, il parametro -ProxySBC deve essere obbligatorio $null o il valore FQDN SBC (scenario SBC centrale con trunk centralizzati).</span><span class="sxs-lookup"><span data-stu-id="5e0ea-209">If the customer has a single SBC, the -ProxySBC parameter must be either mandatory $null or SBC FQDN value (Central SBC with centralized trunks scenario).</span></span>
   - <span data-ttu-id="5e0ea-210">Il parametro -MediaBypass deve essere impostato su $true per supportare l'ottimizzazione multimediale locale.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-210">The -MediaBypass parameter must be set to $true in order to support Local Media Optimization.</span></span>
   - <span data-ttu-id="5e0ea-211">Se per SBC non è impostato il parametro -BypassMode, le intestazioni X-MS non verranno inviate.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-211">If the SBC doesn’t have the -BypassMode parameter set, X-MS headers will not be sent.</span></span> 
   - <span data-ttu-id="5e0ea-212">Tutti i parametri usano la distinzione tra maiuscole e minuscole, quindi è necessario assicurarsi di usare lo stesso caso usato durante l'installazione.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-212">All parameters are case sensitive so you need to ensure that you use the same case that was used used during setup.</span></span>  <span data-ttu-id="5e0ea-213">Ad esempio, i valori gatewaySiteID "Vietnam" e "vietnam" verranno trattati come siti diversi.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-213">(For example, GatewaySiteID values “Vietnam” and “vietnam” will be treated as different sites.)</span></span>

<span data-ttu-id="5e0ea-214">L'esempio seguente aggiunge tre SBC ai siti di rete Vietnam, Indonesia e Singapore nell'area APAC con modalità Ignora sempre:</span><span class="sxs-lookup"><span data-stu-id="5e0ea-214">The following example adds three SBCs to the network sites Vietnam, Indonesia, and Singapore in the APAC region with mode Always bypass:</span></span>

```
Set-CSOnlinePSTNGateway -Identity “proxysbc.contoso.com” -GatewaySiteID “Singapore” -MediaBypass $true -BypassMode “Always” -ProxySBC $null

Set-CSOnlinePSTNGateway -Identity “VNsbc.contoso.com” -GatewaySiteID “Vietnam” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”

Set-CSOnlinePSTNGateway -Identity “IDsbc.contoso.com” -GatewaySiteID “Indonesia” -MediaBypass $true -BypassMode “Always” -ProxySBC “proxysbc.contoso.com”
```

<span data-ttu-id="5e0ea-215">Nota: per garantire operazioni ininterrotte quando l'ottimizzazione del supporto locale e il routing di Location-Based (LBR) sono configurati contemporaneamente, gli SBC downstream devono essere abilitati per LBR impostando il parametro GatewaySiteLbrEnabled su $true per ogni SBC downstream.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-215">Note: To ensure uninterrupted operations when Local Media Optimization and Location-Based Routing (LBR) are configured at the same time, downstream SBCs must be enabled for LBR by setting the GatewaySiteLbrEnabled parameter to $true for each downstream SBC.</span></span> <span data-ttu-id="5e0ea-216">Questa impostazione non è obbligatoria per il proxy SBC.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-216">(This setting is not mandatory for the proxy SBC.)</span></span>

<span data-ttu-id="5e0ea-217">In base alle informazioni precedenti, il routing diretto includerà tre intestazioni SIP proprietarie per gli inviti SIP e i nuovi inviti, come illustrato nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-217">Based on the information above, Direct Routing will include three proprietary SIP Headers to SIP Invites and Re-invites as shown  in the following table.</span></span>

<span data-ttu-id="5e0ea-218">Intestazioni X-MS introdotte in Routing diretto su inviti e Re-Invites se è definito BypassMode:</span><span class="sxs-lookup"><span data-stu-id="5e0ea-218">X-MS Headers introduced in Direct Routing on Invites and Re-Invites if BypassMode is defined:</span></span>

| <span data-ttu-id="5e0ea-219">Nome intestazione</span><span class="sxs-lookup"><span data-stu-id="5e0ea-219">Header name</span></span> | <span data-ttu-id="5e0ea-220">Valori</span><span class="sxs-lookup"><span data-stu-id="5e0ea-220">Values</span></span> | <span data-ttu-id="5e0ea-221">Commenti</span><span class="sxs-lookup"><span data-stu-id="5e0ea-221">Comments</span></span> | 
|:------------|:-------|:-------|
| <span data-ttu-id="5e0ea-222">X-MS-UserLocation</span><span class="sxs-lookup"><span data-stu-id="5e0ea-222">X-MS-UserLocation</span></span> | <span data-ttu-id="5e0ea-223">interno/esterno</span><span class="sxs-lookup"><span data-stu-id="5e0ea-223">internal/external</span></span> | <span data-ttu-id="5e0ea-224">Indica se l'utente è interno o esterno</span><span class="sxs-lookup"><span data-stu-id="5e0ea-224">Indicates if user is internal or external</span></span> |
| <span data-ttu-id="5e0ea-225">Request-URI INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span><span class="sxs-lookup"><span data-stu-id="5e0ea-225">Request-URI   INVITE sip: +84439263000@VNsbc.contoso.com SIP /2.0</span></span> | <span data-ttu-id="5e0ea-226">SBC FQDN</span><span class="sxs-lookup"><span data-stu-id="5e0ea-226">SBC FQDN</span></span> | <span data-ttu-id="5e0ea-227">Fqdn destinato alla chiamata anche se il servizio SBC non è connesso direttamente a Direct Routing</span><span class="sxs-lookup"><span data-stu-id="5e0ea-227">The FQDN which is targeted for the call even if the SBC is not directly connected to Direct Routing</span></span> |
| <span data-ttu-id="5e0ea-228">X-MS-MediaPath</span><span class="sxs-lookup"><span data-stu-id="5e0ea-228">X-MS-MediaPath</span></span> | <span data-ttu-id="5e0ea-229">Esempio: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5e0ea-229">Example: proxysbc.contoso.com, VNsbc.contoso.com</span></span> | <span data-ttu-id="5e0ea-230">Ordine di SBC da usare per il percorso multimediale tra l'utente e il SBC di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-230">Order of SBCs that should be used for Media path between the user and target SBC.</span></span> <span data-ttu-id="5e0ea-231">Il valore SBC finale è sempre l'ultimo</span><span class="sxs-lookup"><span data-stu-id="5e0ea-231">The final SBC is always last</span></span> |
| <span data-ttu-id="5e0ea-232">X-MS-UserSite</span><span class="sxs-lookup"><span data-stu-id="5e0ea-232">X-MS-UserSite</span></span> | <span data-ttu-id="5e0ea-233">usersiteID</span><span class="sxs-lookup"><span data-stu-id="5e0ea-233">usersiteID</span></span> | <span data-ttu-id="5e0ea-234">Stringa definita dall'amministratore del tenant</span><span class="sxs-lookup"><span data-stu-id="5e0ea-234">String defined by tenant administrator</span></span> |

## <a name="call-flows"></a><span data-ttu-id="5e0ea-235">Flussi di chiamata</span><span class="sxs-lookup"><span data-stu-id="5e0ea-235">Call flows</span></span> 

<span data-ttu-id="5e0ea-236">Di seguito sono illustrati i flussi delle chiamate per due modalità:</span><span class="sxs-lookup"><span data-stu-id="5e0ea-236">The following shows call flows for two modes:</span></span>

- [<span data-ttu-id="5e0ea-237">Ignora sempre</span><span class="sxs-lookup"><span data-stu-id="5e0ea-237">Always Bypass</span></span>](#always-bypass-mode)
- [<span data-ttu-id="5e0ea-238">Solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="5e0ea-238">Only for local users</span></span>](#only-for-local-users-mode)

### <a name="always-bypass-mode"></a><span data-ttu-id="5e0ea-239">Modalità ignora sempre</span><span class="sxs-lookup"><span data-stu-id="5e0ea-239">Always Bypass mode</span></span>

<span data-ttu-id="5e0ea-240">La modalità Ignora sempre è l'opzione più semplice da configurare.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-240">Always Bypass mode is the simplest option to configure.</span></span> <span data-ttu-id="5e0ea-241">L'amministratore tenant può configurare un singolo sito per tutti gli utenti e gli SBC se tutti gli SBC sono raggiungibili da qualsiasi sito.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-241">The tenant administrator can configure a single site for all users and SBCs if all SBCs are reachable from any site.</span></span>

<span data-ttu-id="5e0ea-242">Gli esempi mostrano la modalità ignora sempre per gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e0ea-242">The examples show Always bypass mode for the following scenarios:</span></span>

- [<span data-ttu-id="5e0ea-243">Chiamate in uscita e l'utente si trova nella stessa posizione dell'SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-243">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="5e0ea-244">Chiamate in ingresso e l'utente si trova nella stessa posizione dell'SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-244">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)
- [<span data-ttu-id="5e0ea-245">Chiamate in uscita e l'utente è esterno</span><span class="sxs-lookup"><span data-stu-id="5e0ea-245">Outbound calls and the user is external</span></span>](#outbound-calls-and-the-user-is-external-with-always-bypass)
- [<span data-ttu-id="5e0ea-246">Chiamate in ingresso e l'utente è esterno</span><span class="sxs-lookup"><span data-stu-id="5e0ea-246">Inbound calls and the user is external</span></span>](#inbound-calls-and-the-user-is-external-with-always-bypass)

<span data-ttu-id="5e0ea-247">La tabella seguente mostra l'FQDN e gli indirizzi IP usati negli esempi:</span><span class="sxs-lookup"><span data-stu-id="5e0ea-247">The following table shows the FQDN and IP addresses used in the examples:</span></span>

| <span data-ttu-id="5e0ea-248">FQDN</span><span class="sxs-lookup"><span data-stu-id="5e0ea-248">FQDN</span></span> | <span data-ttu-id="5e0ea-249">Indirizzo IP esterno SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-249">SBC external IP address</span></span> | <span data-ttu-id="5e0ea-250">Indirizzo IP interno SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-250">SBC internal IP Address</span></span> | <span data-ttu-id="5e0ea-251">Subnet interna</span><span class="sxs-lookup"><span data-stu-id="5e0ea-251">Internal subnet</span></span> | <span data-ttu-id="5e0ea-252">Posizione</span><span class="sxs-lookup"><span data-stu-id="5e0ea-252">Location</span></span> | <span data-ttu-id="5e0ea-253">NAT esterno (IP attendibile)</span><span class="sxs-lookup"><span data-stu-id="5e0ea-253">External NAT (Trusted IP)</span></span> |
|:------------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="5e0ea-254">VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5e0ea-254">VNsbc.contoso.com</span></span> | <span data-ttu-id="5e0ea-255">Nessuno</span><span class="sxs-lookup"><span data-stu-id="5e0ea-255">None</span></span> | <span data-ttu-id="5e0ea-256">192.168.1.5</span><span class="sxs-lookup"><span data-stu-id="5e0ea-256">192.168.1.5</span></span> | <span data-ttu-id="5e0ea-257">192.168.1.0/24</span><span class="sxs-lookup"><span data-stu-id="5e0ea-257">192.168.1.0/24</span></span> | <span data-ttu-id="5e0ea-258">Vietnam</span><span class="sxs-lookup"><span data-stu-id="5e0ea-258">Vietnam</span></span> | <span data-ttu-id="5e0ea-259">172.16.240.110</span><span class="sxs-lookup"><span data-stu-id="5e0ea-259">172.16.240.110</span></span> |
| <span data-ttu-id="5e0ea-260">IDsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5e0ea-260">IDsbc.contoso.com</span></span> | <span data-ttu-id="5e0ea-261">Nessuno</span><span class="sxs-lookup"><span data-stu-id="5e0ea-261">None</span></span> | <span data-ttu-id="5e0ea-262">192.168.2.5</span><span class="sxs-lookup"><span data-stu-id="5e0ea-262">192.168.2.5</span></span> | <span data-ttu-id="5e0ea-263">192.168.2.0/24</span><span class="sxs-lookup"><span data-stu-id="5e0ea-263">192.168.2.0/24</span></span> | <span data-ttu-id="5e0ea-264">Indonesia</span><span class="sxs-lookup"><span data-stu-id="5e0ea-264">Indonesia</span></span> | <span data-ttu-id="5e0ea-265">172.16.240.120</span><span class="sxs-lookup"><span data-stu-id="5e0ea-265">172.16.240.120</span></span> |
| <span data-ttu-id="5e0ea-266">proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5e0ea-266">proxysbc.contoso.com</span></span> | <span data-ttu-id="5e0ea-267">172.16.240.133</span><span class="sxs-lookup"><span data-stu-id="5e0ea-267">172.16.240.133</span></span> | <span data-ttu-id="5e0ea-268">192.168.3.5</span><span class="sxs-lookup"><span data-stu-id="5e0ea-268">192.168.3.5</span></span> | <span data-ttu-id="5e0ea-269">192.168.3.0/24</span><span class="sxs-lookup"><span data-stu-id="5e0ea-269">192.168.3.0/24</span></span> | <span data-ttu-id="5e0ea-270">Singapore</span><span class="sxs-lookup"><span data-stu-id="5e0ea-270">Singapore</span></span> | <span data-ttu-id="5e0ea-271">172.16.240.130</span><span class="sxs-lookup"><span data-stu-id="5e0ea-271">172.16.240.130</span></span> |



#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="5e0ea-272">Chiamate in uscita e l'utente si trova nella stessa posizione della SBC con Bypass sempre</span><span class="sxs-lookup"><span data-stu-id="5e0ea-272">Outbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="5e0ea-273">Modalità</span><span class="sxs-lookup"><span data-stu-id="5e0ea-273">Mode</span></span> |    <span data-ttu-id="5e0ea-274">Utente</span><span class="sxs-lookup"><span data-stu-id="5e0ea-274">User</span></span> |  <span data-ttu-id="5e0ea-275">Posizione</span><span class="sxs-lookup"><span data-stu-id="5e0ea-275">Location</span></span> |  <span data-ttu-id="5e0ea-276">Direzione della chiamata</span><span class="sxs-lookup"><span data-stu-id="5e0ea-276">Call direction</span></span> |
|:------------|:-------|:-------| :-------|
| <span data-ttu-id="5e0ea-277">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="5e0ea-277">AlwaysBypass</span></span> |    <span data-ttu-id="5e0ea-278">Interno</span><span class="sxs-lookup"><span data-stu-id="5e0ea-278">Internal</span></span> |  <span data-ttu-id="5e0ea-279">Lo stesso sito di SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-279">The same site as SBC</span></span> |  <span data-ttu-id="5e0ea-280">In uscita</span><span class="sxs-lookup"><span data-stu-id="5e0ea-280">Outbound</span></span> |

<span data-ttu-id="5e0ea-281">La tabella seguente mostra la configurazione e l'azione dell'utente finale:</span><span class="sxs-lookup"><span data-stu-id="5e0ea-281">The following table shows the end user configuration and action:</span></span>

| <span data-ttu-id="5e0ea-282">Posizione fisica dell'utente</span><span class="sxs-lookup"><span data-stu-id="5e0ea-282">User physical location</span></span>| <span data-ttu-id="5e0ea-283">L'utente effettua o riceve una chiamata a/da numero</span><span class="sxs-lookup"><span data-stu-id="5e0ea-283">User makes or receives a call to/from number</span></span> | <span data-ttu-id="5e0ea-284">Numero di telefono dell'utente</span><span class="sxs-lookup"><span data-stu-id="5e0ea-284">User phone number</span></span>  | <span data-ttu-id="5e0ea-285">Criteri di routing vocale online</span><span class="sxs-lookup"><span data-stu-id="5e0ea-285">Online Voice Routing Policy</span></span> | <span data-ttu-id="5e0ea-286">Modalità configurata per SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-286">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="5e0ea-287">Vietnam</span><span class="sxs-lookup"><span data-stu-id="5e0ea-287">Vietnam</span></span> | <span data-ttu-id="5e0ea-288">+84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="5e0ea-288">+84 4 3926 3000</span></span> | <span data-ttu-id="5e0ea-289">+84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="5e0ea-289">+84 4 5555 5555</span></span>   | <span data-ttu-id="5e0ea-290">Priorità 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5e0ea-290">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="5e0ea-291">Priorità 2: .\* - proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5e0ea-291">Priority 2: .\* - proxysbc.contoso.com</span></span>   | <span data-ttu-id="5e0ea-292">VNsbc.contoso.com – Ignora sempre</span><span class="sxs-lookup"><span data-stu-id="5e0ea-292">VNsbc.contoso.com – Always Bypass</span></span> <br> <span data-ttu-id="5e0ea-293">proxysbc.contoso.com – Ignora sempre</span><span class="sxs-lookup"><span data-stu-id="5e0ea-293">proxysbc.contoso.com – Always Bypass</span></span>


<span data-ttu-id="5e0ea-294">Il diagramma seguente mostra la scala SIP per una chiamata in uscita con modalità ignora sempre e l'utente nella stessa posizione del SBC.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-294">The following diagram shows the SIP ladder for an outbound call with Always bypass mode, and the user in the same location as the SBC.</span></span>

<span data-ttu-id="5e0ea-295">![Diagramma che mostra le chiamate in uscita](media/direct-routing-media-op-10.png "Chiamate in uscita")</span><span class="sxs-lookup"><span data-stu-id="5e0ea-295">![Diagram showing outbound calls](media/direct-routing-media-op-10.png "Outbound calls")</span></span>

<span data-ttu-id="5e0ea-296">La tabella seguente mostra le intestazioni X-MS inviate da Direct Routing:</span><span class="sxs-lookup"><span data-stu-id="5e0ea-296">The following table shows the X-MS headers sent by Direct Routing:</span></span>

| <span data-ttu-id="5e0ea-297">Parametro</span><span class="sxs-lookup"><span data-stu-id="5e0ea-297">Parameter</span></span> | <span data-ttu-id="5e0ea-298">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="5e0ea-298">Explanation</span></span> |
|:------------|:-------|
| <span data-ttu-id="5e0ea-299">Invita +8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5e0ea-299">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="5e0ea-300">L'FQDN di destinazione di SBC come definito nei criteri di routing vocale online viene inviato nell'URI della richiesta</span><span class="sxs-lookup"><span data-stu-id="5e0ea-300">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI</span></span> | 
| <span data-ttu-id="5e0ea-301">X-MS-UserLocation: interno</span><span class="sxs-lookup"><span data-stu-id="5e0ea-301">X-MS-UserLocation: internal</span></span> | <span data-ttu-id="5e0ea-302">Il campo indica che l'utente si trova all'interno della rete aziendale</span><span class="sxs-lookup"><span data-stu-id="5e0ea-302">The field indicated that user is located inside the corporate network</span></span> |
| <span data-ttu-id="5e0ea-303">X-MS-MediaPath: VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5e0ea-303">X-MS-MediaPath: VNsbc.contoso.com</span></span> |   <span data-ttu-id="5e0ea-304">Specifica quale SBC deve attraversare il client fino al valore SBC di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-304">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="5e0ea-305">In questo caso, poiché è stato ignorato sempre, il client è interno al nome di destinazione inviato come unico nome nell'intestazione.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-305">In this case as we have Always Bypass, and the client is internal the target name sent as the only name in the header.</span></span> | 
|<span data-ttu-id="5e0ea-306">X-MS-UserSite: Vietnam</span><span class="sxs-lookup"><span data-stu-id="5e0ea-306">X-MS-UserSite: Vietnam</span></span> |   <span data-ttu-id="5e0ea-307">Campo indicato all'interno del sito in cui si trova l'utente.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-307">The field indicated within the site the user is located.</span></span> |


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass"></a><span data-ttu-id="5e0ea-308">Chiamate in ingresso e l'utente si trova nella stessa posizione della SBC con Bypass sempre</span><span class="sxs-lookup"><span data-stu-id="5e0ea-308">Inbound calls and the user is in the same location as the SBC with Always Bypass</span></span>

| <span data-ttu-id="5e0ea-309">Modalità</span><span class="sxs-lookup"><span data-stu-id="5e0ea-309">Mode</span></span> |    <span data-ttu-id="5e0ea-310">Utente</span><span class="sxs-lookup"><span data-stu-id="5e0ea-310">User</span></span> |  <span data-ttu-id="5e0ea-311">Posizione</span><span class="sxs-lookup"><span data-stu-id="5e0ea-311">Location</span></span> |  <span data-ttu-id="5e0ea-312">Direzione della chiamata</span><span class="sxs-lookup"><span data-stu-id="5e0ea-312">Call direction</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="5e0ea-313">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="5e0ea-313">AlwaysBypass</span></span> |    <span data-ttu-id="5e0ea-314">Interno</span><span class="sxs-lookup"><span data-stu-id="5e0ea-314">Internal</span></span> | <span data-ttu-id="5e0ea-315">Lo stesso sito di SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-315">The same site as SBC</span></span> | <span data-ttu-id="5e0ea-316">In ingresso</span><span class="sxs-lookup"><span data-stu-id="5e0ea-316">Inbound</span></span> |


<span data-ttu-id="5e0ea-317">In una chiamata in ingresso, la posizione dell'utente è sconosciuta e SBC deve indovinare dove si trova l'utente.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-317">On an inbound call, the location of the user is unknown, and the SBC must guess where the user is.</span></span> <span data-ttu-id="5e0ea-318">Se l'ipotesi non è corretta, sarà necessario un nuovo invito.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-318">If the guess is not correct, a re-invite will be required.</span></span> <span data-ttu-id="5e0ea-319">Questo caso presuppone che l'utente sia interno, che i supporti multimediali possano fluire direttamente e che non siano necessarie altre azioni (invito di nuovo).</span><span class="sxs-lookup"><span data-stu-id="5e0ea-319">This case assumes user is internal, media can flow directly, and no further actions are required (re-invite).</span></span>
<span data-ttu-id="5e0ea-320">Il servizio SBC connesso al servizio di routing diretto segnala la posizione SBC di origine fornendo i campi Record-Route e Contatto.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-320">The SBC connected to the Direct Routing service reports the originating SBC location by providing Record-Route and Contact fields.</span></span> <span data-ttu-id="5e0ea-321">In base a questi campi, il percorso multimediale viene calcolato tramite Routing diretto.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-321">Based on these fields, the media path is calculated by Direct Routing.</span></span>

<span data-ttu-id="5e0ea-322">Nota: dato che un utente può avere più endpoint, il supporto di 183 non è possibile.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-322">Note: Given that a user can have multiple endpoints, support of 183 is not possible.</span></span> <span data-ttu-id="5e0ea-323">In questo caso l'instradamento diretto userà sempre 180 squilli.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-323">The Direct Routing will always use 180 Ringing in this case.</span></span> 

<span data-ttu-id="5e0ea-324">Il diagramma seguente mostra la scala SIP per le chiamate in ingresso con la modalità AlwaysBypass e l'utente si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-324">The following diagram shows the SIP ladder for in inbound call with AlwaysBypass mode, and the user is in the same location as the SBC.</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-11.png)


#### <a name="outbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="5e0ea-326">Chiamate in uscita e l'utente è esterno con Bypass sempre</span><span class="sxs-lookup"><span data-stu-id="5e0ea-326">Outbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="5e0ea-327">Modalità</span><span class="sxs-lookup"><span data-stu-id="5e0ea-327">Mode</span></span> |    <span data-ttu-id="5e0ea-328">Utente</span><span class="sxs-lookup"><span data-stu-id="5e0ea-328">User</span></span> |  <span data-ttu-id="5e0ea-329">Sito</span><span class="sxs-lookup"><span data-stu-id="5e0ea-329">Site</span></span> |  <span data-ttu-id="5e0ea-330">Direzione della chiamata</span><span class="sxs-lookup"><span data-stu-id="5e0ea-330">Call direction</span></span>
|:------------|:-------|:-------|:-------|
<span data-ttu-id="5e0ea-331">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="5e0ea-331">AlwaysBypass</span></span> |  <span data-ttu-id="5e0ea-332">Esterno</span><span class="sxs-lookup"><span data-stu-id="5e0ea-332">External</span></span> |  <span data-ttu-id="5e0ea-333">N/D</span><span class="sxs-lookup"><span data-stu-id="5e0ea-333">N/A</span></span> | <span data-ttu-id="5e0ea-334">In uscita</span><span class="sxs-lookup"><span data-stu-id="5e0ea-334">Outbound</span></span> |


<span data-ttu-id="5e0ea-335">Il diagramma seguente mostra la scala SIP per una chiamata in uscita con modalità AlwaysBypass e l'utente è esterno:</span><span class="sxs-lookup"><span data-stu-id="5e0ea-335">The following diagram shows the SIP ladder for an outbound call with AlwaysBypass mode, and the user is external:</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-12.png)

<span data-ttu-id="5e0ea-337">La tabella seguente mostra le intestazioni X-MS inviate dal servizio Routing diretto:</span><span class="sxs-lookup"><span data-stu-id="5e0ea-337">The following table shows the X-MS headers sent by the Direct Routing service:</span></span>

| <span data-ttu-id="5e0ea-338">Parametro</span><span class="sxs-lookup"><span data-stu-id="5e0ea-338">Parameter</span></span> |   <span data-ttu-id="5e0ea-339">Spiegazione</span><span class="sxs-lookup"><span data-stu-id="5e0ea-339">Explanation</span></span> |
|:------------|:-------|
|<span data-ttu-id="5e0ea-340">Invita +8443926300@VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5e0ea-340">Invite +8443926300@VNsbc.contoso.com</span></span> | <span data-ttu-id="5e0ea-341">L'FQDN di destinazione del servizio SBC come definito nei criteri di routing vocale online viene inviato nell'URI della richiesta.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-341">The target FQDN of the SBC as defined in the Online Voice Routing Policy is sent in the Request URI.</span></span>|
| <span data-ttu-id="5e0ea-342">X-MS-UserLocation: esterno</span><span class="sxs-lookup"><span data-stu-id="5e0ea-342">X-MS-UserLocation: external</span></span> | <span data-ttu-id="5e0ea-343">Il campo indica che l'utente si trova all'esterno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-343">The field indicated that user is located outside the corporate network.</span></span> |
| <span data-ttu-id="5e0ea-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5e0ea-344">X-MS-MediaPath: proxysbc.contoso.com, VNsbc.contoso.com</span></span>    | <span data-ttu-id="5e0ea-345">Specifica quale SBC deve attraversare il client fino al valore SBC di destinazione.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-345">Specifies which SBC the client must traverse to the target SBC.</span></span> <span data-ttu-id="5e0ea-346">In questo caso, poiché è sempre stato ignorato e il client è esterno.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-346">In this case as we have Always Bypass, and the client is external.</span></span> |

#### <a name="inbound-calls-and-the-user-is-external-with-always-bypass"></a><span data-ttu-id="5e0ea-347">Chiamate in ingresso e l'utente è esterno con Bypass sempre</span><span class="sxs-lookup"><span data-stu-id="5e0ea-347">Inbound calls and the user is external with Always Bypass</span></span>

| <span data-ttu-id="5e0ea-348">Modalità</span><span class="sxs-lookup"><span data-stu-id="5e0ea-348">Mode</span></span> | <span data-ttu-id="5e0ea-349">Utente</span><span class="sxs-lookup"><span data-stu-id="5e0ea-349">User</span></span> | <span data-ttu-id="5e0ea-350">Sito</span><span class="sxs-lookup"><span data-stu-id="5e0ea-350">Site</span></span> |  <span data-ttu-id="5e0ea-351">Direzione della chiamata</span><span class="sxs-lookup"><span data-stu-id="5e0ea-351">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
<span data-ttu-id="5e0ea-352">AlwaysBypass</span><span class="sxs-lookup"><span data-stu-id="5e0ea-352">AlwaysBypass</span></span> |  <span data-ttu-id="5e0ea-353">Esterno</span><span class="sxs-lookup"><span data-stu-id="5e0ea-353">External</span></span> |  <span data-ttu-id="5e0ea-354">N/D</span><span class="sxs-lookup"><span data-stu-id="5e0ea-354">N/A</span></span> |   <span data-ttu-id="5e0ea-355">In ingresso</span><span class="sxs-lookup"><span data-stu-id="5e0ea-355">Inbound</span></span> |

<span data-ttu-id="5e0ea-356">Per una chiamata in ingresso, la SBC connessa a Direct Routing deve inviare un nuovo invito (per impostazione predefinita, i media candidati locali sono sempre offerti) se la posizione dell'utente è esterna.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-356">For an inbound call, the SBC connected to Direct Routing needs to send a re-invite (by default, local media candidates are always offered) if the location of the user is external.</span></span>  <span data-ttu-id="5e0ea-357">X-MediaPath viene calcolato in base Record-Route e all'utente SBC specificato.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-357">The X-MediaPath is calculated based on Record-Route and the SBC user specified.</span></span>

<span data-ttu-id="5e0ea-358">Il diagramma seguente mostra la scala SIP per una chiamata in ingresso con modalità AlwaysBypass e l'utente è esterno.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-358">The following diagram shows the SIP ladder for an inbound call with AlwaysBypass mode, and the user is external.</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-13.png)


### <a name="only-for-local-users-mode"></a><span data-ttu-id="5e0ea-360">Solo per la modalità utenti locali</span><span class="sxs-lookup"><span data-stu-id="5e0ea-360">Only for local users mode</span></span>

<span data-ttu-id="5e0ea-361">I media candidati locali dell'SBC di destinazione verranno offerti solo se un utente si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-361">Local media candidates of the target SBC will be offered only if a user is in the same location as the SBC.</span></span> <span data-ttu-id="5e0ea-362">In tutti gli altri casi, i supporti multimediali fluiranno attraverso un IP interno o esterno del proxy SBC.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-362">In all other cases, media will flow through either an internal or external IP of the proxy SBC.</span></span>

<span data-ttu-id="5e0ea-363">Vengono descritti gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e0ea-363">The following scenarios are described:</span></span>

- [<span data-ttu-id="5e0ea-364">Chiamate in uscita e l'utente si trova nella stessa posizione dell'SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-364">Outbound calls and the user is in the same location as the SBC</span></span>](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="5e0ea-365">Chiamate in ingresso e l'utente si trova nella stessa posizione dell'SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-365">Inbound calls and the user is in the same location as the SBC</span></span>](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users)
- [<span data-ttu-id="5e0ea-366">L'utente non si trova nella stessa posizione di SBC, ma si trova nella rete aziendale</span><span class="sxs-lookup"><span data-stu-id="5e0ea-366">User is not at the same location as the SBC but is in the corporate network</span></span>](#user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users)
- [<span data-ttu-id="5e0ea-367">Chiamate in ingresso e l'utente è interno, ma non si trova nella stessa posizione dell'SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-367">Inbound calls and the user is internal but is not at the same location as the SBC</span></span>](#inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users)

<span data-ttu-id="5e0ea-368">La tabella seguente mostra la configurazione e l'azione dell'utente finale:</span><span class="sxs-lookup"><span data-stu-id="5e0ea-368">The following table shows end user configuration and action:</span></span>

| <span data-ttu-id="5e0ea-369">Posizione fisica dell'utente</span><span class="sxs-lookup"><span data-stu-id="5e0ea-369">User physical location</span></span> |  <span data-ttu-id="5e0ea-370">L'utente effettua o riceve una chiamata a/da numero</span><span class="sxs-lookup"><span data-stu-id="5e0ea-370">User makes or receives a call to/from number</span></span> |  <span data-ttu-id="5e0ea-371">Numero di telefono dell'utente</span><span class="sxs-lookup"><span data-stu-id="5e0ea-371">User phone number</span></span> | <span data-ttu-id="5e0ea-372">Criteri di routing vocale online</span><span class="sxs-lookup"><span data-stu-id="5e0ea-372">Online Voice Routing Policy</span></span> |   <span data-ttu-id="5e0ea-373">Modalità configurata per SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-373">Mode configured for SBC</span></span> |
|:------------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="5e0ea-374">Vietnam</span><span class="sxs-lookup"><span data-stu-id="5e0ea-374">Vietnam</span></span> | <span data-ttu-id="5e0ea-375">+84 4 3926 3000</span><span class="sxs-lookup"><span data-stu-id="5e0ea-375">+84 4 3926  3000</span></span> |  <span data-ttu-id="5e0ea-376">+84 4 5555 5555</span><span class="sxs-lookup"><span data-stu-id="5e0ea-376">+84 4 5555 5555</span></span> | <span data-ttu-id="5e0ea-377">Priorità 1: ^ \+ 84(\d {9} )$ -VNsbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5e0ea-377">Priority 1: ^\+84(\d{9})$ -VNsbc.contoso.com</span></span> <br> <span data-ttu-id="5e0ea-378">Priorità 2: .\* - proxysbc.contoso.com</span><span class="sxs-lookup"><span data-stu-id="5e0ea-378">Priority 2: .\* - proxysbc.contoso.com</span></span> | <span data-ttu-id="5e0ea-379">VNsbc.contoso.com - OnlyForLocalUsers Proxysbc.contoso.com – Ignora sempre</span><span class="sxs-lookup"><span data-stu-id="5e0ea-379">VNsbc.contoso.com – OnlyForLocalUsers Proxysbc.contoso.com – Always Bypass</span></span> |

#### <a name="outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="5e0ea-380">Chiamate in uscita e l'utente si trova nella stessa posizione dell'SBC con Solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="5e0ea-380">Outbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="5e0ea-381">Modalità</span><span class="sxs-lookup"><span data-stu-id="5e0ea-381">Mode</span></span> | <span data-ttu-id="5e0ea-382">Utente</span><span class="sxs-lookup"><span data-stu-id="5e0ea-382">User</span></span> | <span data-ttu-id="5e0ea-383">Sito</span><span class="sxs-lookup"><span data-stu-id="5e0ea-383">Site</span></span> | <span data-ttu-id="5e0ea-384">Direzione della chiamata</span><span class="sxs-lookup"><span data-stu-id="5e0ea-384">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="5e0ea-385">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="5e0ea-385">OnlyForLocalUsers</span></span> |   <span data-ttu-id="5e0ea-386">Interno</span><span class="sxs-lookup"><span data-stu-id="5e0ea-386">Internal</span></span> |<span data-ttu-id="5e0ea-387">Uguale a SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-387">Same as SBC</span></span>   | <span data-ttu-id="5e0ea-388">In uscita</span><span class="sxs-lookup"><span data-stu-id="5e0ea-388">Outbound</span></span> |

<span data-ttu-id="5e0ea-389">Il diagramma seguente mostra una chiamata in uscita in modalità OnlyForLocalUsers e l'utente si trova nella stessa posizione del servizio SBC.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-389">The following diagram shows an outbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="5e0ea-390">Questo è lo stesso flusso visualizzato nelle chiamate in uscita quando l'utente si trova nella stessa [posizione di SBC.](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)</span><span class="sxs-lookup"><span data-stu-id="5e0ea-390">This is the same flow shown in [Outbound calls when the user is in the same location as the SBC](#outbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-14.png)


#### <a name="inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="5e0ea-392">Chiamate in ingresso e l'utente si trova nella stessa posizione della SBC con Solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="5e0ea-392">Inbound calls and the user is in the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="5e0ea-393">Modalità</span><span class="sxs-lookup"><span data-stu-id="5e0ea-393">Mode</span></span> | <span data-ttu-id="5e0ea-394">Utente</span><span class="sxs-lookup"><span data-stu-id="5e0ea-394">User</span></span> | <span data-ttu-id="5e0ea-395">Sito</span><span class="sxs-lookup"><span data-stu-id="5e0ea-395">Site</span></span> | <span data-ttu-id="5e0ea-396">Direzione della chiamata</span><span class="sxs-lookup"><span data-stu-id="5e0ea-396">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="5e0ea-397">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="5e0ea-397">OnlyForLocalUsers</span></span> |   <span data-ttu-id="5e0ea-398">Interno</span><span class="sxs-lookup"><span data-stu-id="5e0ea-398">Internal</span></span> | <span data-ttu-id="5e0ea-399">Uguale a SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-399">Same as SBC</span></span> | <span data-ttu-id="5e0ea-400">In ingresso</span><span class="sxs-lookup"><span data-stu-id="5e0ea-400">Inbound</span></span> |

<span data-ttu-id="5e0ea-401">Il diagramma seguente mostra una chiamata in ingresso in modalità OnlyForLocalUsers e l'utente si trova nella stessa posizione del servizio SBC.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-401">The following diagram shows an inbound call with OnlyForLocalUsers mode, and the user is in the same location as the SBC.</span></span> <span data-ttu-id="5e0ea-402">Questo è lo stesso flusso mostrato nelle chiamate in ingresso quando l'utente si trova nella stessa posizione [del servizio SBC.](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass)</span><span class="sxs-lookup"><span data-stu-id="5e0ea-402">This is the same flow as shown in [Inbound calls when the user is in the same location as the SBC](#inbound-calls-and-the-user-is-in-the-same-location-as-the-sbc-with-always-bypass).</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-15.png)


#### <a name="user-is-not-at-the-same-location-as-the-sbc-but-is-in-the-corporate-network-with-only-for-local-users"></a><span data-ttu-id="5e0ea-404">L'utente non si trova nella stessa posizione di SBC, ma si trova nella rete aziendale con Solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="5e0ea-404">User is not at the same location as the SBC but is in the corporate network with Only for local users</span></span>

| <span data-ttu-id="5e0ea-405">Modalità</span><span class="sxs-lookup"><span data-stu-id="5e0ea-405">Mode</span></span> | <span data-ttu-id="5e0ea-406">Utente</span><span class="sxs-lookup"><span data-stu-id="5e0ea-406">User</span></span> | <span data-ttu-id="5e0ea-407">Sito</span><span class="sxs-lookup"><span data-stu-id="5e0ea-407">Site</span></span> |<span data-ttu-id="5e0ea-408">Direzione della chiamata</span><span class="sxs-lookup"><span data-stu-id="5e0ea-408">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="5e0ea-409">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="5e0ea-409">OnlyForLocalUsers</span></span>  | <span data-ttu-id="5e0ea-410">Interno</span><span class="sxs-lookup"><span data-stu-id="5e0ea-410">Internal</span></span> |   <span data-ttu-id="5e0ea-411">Diverso da SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-411">Different from SBC</span></span> | <span data-ttu-id="5e0ea-412">In uscita</span><span class="sxs-lookup"><span data-stu-id="5e0ea-412">Outbound</span></span> |

<span data-ttu-id="5e0ea-413">Il routing diretto calcola X-MediaPath in base alla posizione segnalata dell'utente e alla modalità configurata in SBC.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-413">Direct routing calculates X-MediaPath based on the reported location of the user and mode configured on the SBC.</span></span>


<span data-ttu-id="5e0ea-414">Il diagramma seguente mostra una chiamata in uscita con la modalità OnlyForLocalUsers e un utente interno che non si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-414">The following diagram shows an outbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-16.png)


#### <a name="inbound-call-and-the-user-is-internal-but-is-not-at-the-same-location-as-the-sbc-with-only-for-local-users"></a><span data-ttu-id="5e0ea-416">Chiamata in ingresso e l'utente è interno, ma non si trova nella stessa posizione di SBC con Solo per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="5e0ea-416">Inbound call and the user is internal but is not at the same location as the SBC with Only for local users</span></span>

| <span data-ttu-id="5e0ea-417">Modalità</span><span class="sxs-lookup"><span data-stu-id="5e0ea-417">Mode</span></span> |    <span data-ttu-id="5e0ea-418">Utente</span><span class="sxs-lookup"><span data-stu-id="5e0ea-418">User</span></span> |  <span data-ttu-id="5e0ea-419">Sito</span><span class="sxs-lookup"><span data-stu-id="5e0ea-419">Site</span></span> |  <span data-ttu-id="5e0ea-420">Direzione della chiamata</span><span class="sxs-lookup"><span data-stu-id="5e0ea-420">Call direction</span></span> |
|:------------|:-------|:-------|:-------|
| <span data-ttu-id="5e0ea-421">OnlyForLocalUsers</span><span class="sxs-lookup"><span data-stu-id="5e0ea-421">OnlyForLocalUsers</span></span> | <span data-ttu-id="5e0ea-422">Interno</span><span class="sxs-lookup"><span data-stu-id="5e0ea-422">Internal</span></span> |    <span data-ttu-id="5e0ea-423">Diverso da SBC</span><span class="sxs-lookup"><span data-stu-id="5e0ea-423">Different from SBC</span></span> |    <span data-ttu-id="5e0ea-424">In ingresso</span><span class="sxs-lookup"><span data-stu-id="5e0ea-424">Inbound</span></span> |

<span data-ttu-id="5e0ea-425">Il diagramma seguente mostra una chiamata in ingresso con la modalità OnlyForLocalUsers e un utente interno che non si trova nella stessa posizione di SBC.</span><span class="sxs-lookup"><span data-stu-id="5e0ea-425">The following diagram shows an inbound call with OnlyForLocalUsers mode, and an internal user who is not at the same location as the SBC.</span></span>

![Diagramma che mostra la scala SIP](media/direct-routing-media-op-17.png)









