---
title: Distribuire più siti in Cloud Connector
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: e62413fd-f68e-4825-8384-c983076bdf23
description: Informazioni sulla distribuzione di più siti PSTN in Cloud Connector Edition.
ms.openlocfilehash: 3c777c54690b1eb31671f71cff915f1bb4854a0d
ms.sourcegitcommit: b424ab14683ab5080ebfd085adff7c0dbe1be84c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/03/2020
ms.locfileid: "47358922"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="502bd-103">Distribuire più siti in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="502bd-103">Deploy multiple sites in Cloud Connector</span></span>

> [!Important] 
> <span data-ttu-id="502bd-104">Cloud Connector Edition si ritirerà il 31 luglio 2021 insieme a Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="502bd-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="502bd-105">Dopo che l'organizzazione ha eseguito l'aggiornamento ai team, informazioni su come connettere la rete di telefonia locale ai team che utilizzano il [routing diretto](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span><span class="sxs-lookup"><span data-stu-id="502bd-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](https://docs.microsoft.com/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="502bd-106">Informazioni sulla distribuzione di più siti PSTN in Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="502bd-106">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="502bd-107">In questa sezione viene descritto come distribuire più siti PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="502bd-107">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="502bd-108">I siti vengono distribuiti uno alla volta utilizzando gli stessi passaggi della distribuzione di un singolo sito.</span><span class="sxs-lookup"><span data-stu-id="502bd-108">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="502bd-109">In questo argomento vengono illustrate le considerazioni relative alle differenze tra i siti di una distribuzione a più siti.</span><span class="sxs-lookup"><span data-stu-id="502bd-109">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="502bd-110">Più siti PSTN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="502bd-110">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="502bd-111">Di seguito viene illustrata una configurazione di esempio per la distribuzione di Skype for Business Cloud Connector Edition per diversi siti PSTN.</span><span class="sxs-lookup"><span data-stu-id="502bd-111">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="502bd-112">Verificare che le impostazioni di configurazione siano corrette prima di avviare una distribuzione.</span><span class="sxs-lookup"><span data-stu-id="502bd-112">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="502bd-113">Sito PSTN 1</span><span class="sxs-lookup"><span data-stu-id="502bd-113">PSTN Site 1</span></span>
  
```console
[Common]
SiteName=Site1
[EdgeServer]
InternalMachineName= cc-edge1
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.241

ExternalSIPPoolName=access1
ExternalSIPIPs=192.168.1.4

ExternalMRFQDNPoolName=mr1
ExternalMRIPs=192.168.1.4
ExternalMRPublicIPs=23.99.115.35
```

<span data-ttu-id="502bd-114">Sito PSTN 2</span><span class="sxs-lookup"><span data-stu-id="502bd-114">PSTN Site 2</span></span>
  
```console
[Common]
SiteName=Site2
[EdgeServer]
InternalMachineName= cc-edge2
InternalPoolName=cc-edgepool
InternalMachineIPs=192.168.0.242

ExternalSIPPoolName=access2
ExternalSIPIPs=192.168.1.5

ExternalMRFQDNPoolName=mr2
ExternalMRIPs=192.168.1.5
ExternalMRPublicIPs=104.42.226.134
```

<span data-ttu-id="502bd-115">Per ogni sito PSTN che si desidera aggiungere, seguire la procedura illustrata in [deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="502bd-115">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="502bd-116">La cartella condivisa per la preparazione della disponibilità elevata (HA) è per ogni sito PSTN.</span><span class="sxs-lookup"><span data-stu-id="502bd-116">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="502bd-117">La cartella condivisa **deve** essere diversa tra i siti PSTN.</span><span class="sxs-lookup"><span data-stu-id="502bd-117">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="502bd-118">Non utilizzare la stessa cartella condivisa per più siti. ></span><span class="sxs-lookup"><span data-stu-id="502bd-118">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="502bd-119">Sito singolo con disponibilità elevata (HA) rispetto alle distribuzioni multisito</span><span class="sxs-lookup"><span data-stu-id="502bd-119">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="502bd-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="502bd-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="502bd-121">Nella tabella seguente sono elencate le differenze tra sito singolo con supporto HA e una distribuzione a più siti.</span><span class="sxs-lookup"><span data-stu-id="502bd-121">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="502bd-122">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="502bd-122">**Category**</span></span>|<span data-ttu-id="502bd-123">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="502bd-123">**Item**</span></span>|<span data-ttu-id="502bd-124">**Sito singolo con HA**</span><span class="sxs-lookup"><span data-stu-id="502bd-124">**Single-Site with HA**</span></span>|<span data-ttu-id="502bd-125">**Multi-sito**</span><span class="sxs-lookup"><span data-stu-id="502bd-125">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="502bd-126">Configurazione</span><span class="sxs-lookup"><span data-stu-id="502bd-126">Configure</span></span>  <br/> |<span data-ttu-id="502bd-127">Nome host dell'accessorio</span><span class="sxs-lookup"><span data-stu-id="502bd-127">Appliance Host Name</span></span> <br/> |<span data-ttu-id="502bd-128">**Diversa** tra gli strumenti</span><span class="sxs-lookup"><span data-stu-id="502bd-128">**Different** across appliances</span></span> <br/> |<span data-ttu-id="502bd-129">**Diversa** tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="502bd-129">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="502bd-130">Configurazione</span><span class="sxs-lookup"><span data-stu-id="502bd-130">Setup</span></span>  <br/> |<span data-ttu-id="502bd-131">Cartella condivisa</span><span class="sxs-lookup"><span data-stu-id="502bd-131">Shared folder</span></span>  <br/> |<span data-ttu-id="502bd-132">Richiede la **stessa** cartella condivisa tra gli strumenti</span><span class="sxs-lookup"><span data-stu-id="502bd-132">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="502bd-133">Richiede una cartella condivisa **diversa** tra gli strumenti</span><span class="sxs-lookup"><span data-stu-id="502bd-133">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="502bd-134">Configurazione</span><span class="sxs-lookup"><span data-stu-id="502bd-134">Configure</span></span>  <br/> |<span data-ttu-id="502bd-135">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="502bd-135">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="502bd-136">Richiede lo **stesso** dominio tra gli strumenti</span><span class="sxs-lookup"><span data-stu-id="502bd-136">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="502bd-137">Richiede lo **stesso** dominio tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="502bd-137">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="502bd-138">Configurazione</span><span class="sxs-lookup"><span data-stu-id="502bd-138">Configure</span></span>  <br/> |<span data-ttu-id="502bd-139">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="502bd-139">SIPDomains</span></span>  <br/> |<span data-ttu-id="502bd-140">I nomi di dominio e l'ordine devono essere **uguali** tra gli strumenti</span><span class="sxs-lookup"><span data-stu-id="502bd-140">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="502bd-141">I nomi di dominio e l'ordine devono essere **uguali** nei siti PSTN</span><span class="sxs-lookup"><span data-stu-id="502bd-141">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="502bd-142">Configurazione</span><span class="sxs-lookup"><span data-stu-id="502bd-142">Configure</span></span>  <br/> |<span data-ttu-id="502bd-143">Nome sito</span><span class="sxs-lookup"><span data-stu-id="502bd-143">Site name</span></span>  <br/> |<span data-ttu-id="502bd-144">**Lo stesso** Nome del sito tra gli strumenti</span><span class="sxs-lookup"><span data-stu-id="502bd-144">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="502bd-145">**Diversa** Nome del sito tra siti PSTN</span><span class="sxs-lookup"><span data-stu-id="502bd-145">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="502bd-146">Configurazione</span><span class="sxs-lookup"><span data-stu-id="502bd-146">Configure</span></span>  <br/> |<span data-ttu-id="502bd-147">Nomi dei server</span><span class="sxs-lookup"><span data-stu-id="502bd-147">Server names</span></span>  <br/> |<span data-ttu-id="502bd-148">**Diversa** tra gli strumenti</span><span class="sxs-lookup"><span data-stu-id="502bd-148">**Different** across appliances</span></span> <br/> |<span data-ttu-id="502bd-149">**Diversa** tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="502bd-149">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="502bd-150">Configurazione</span><span class="sxs-lookup"><span data-stu-id="502bd-150">Configure</span></span>  <br/> |<span data-ttu-id="502bd-151">FQDN del pool interno</span><span class="sxs-lookup"><span data-stu-id="502bd-151">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="502bd-152">**Stesso** tra gli elettrodomestici</span><span class="sxs-lookup"><span data-stu-id="502bd-152">**Same** across appliances</span></span> <br/> |<span data-ttu-id="502bd-153">**Lo stesso** tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="502bd-153">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="502bd-154">Configurazione</span><span class="sxs-lookup"><span data-stu-id="502bd-154">Configure</span></span>  <br/> |<span data-ttu-id="502bd-155">Indirizzi IP interni</span><span class="sxs-lookup"><span data-stu-id="502bd-155">Internal IPs</span></span>  <br/> |<span data-ttu-id="502bd-156">**Diversa** tra gli strumenti</span><span class="sxs-lookup"><span data-stu-id="502bd-156">**Different** across appliances</span></span> <br/> |<span data-ttu-id="502bd-157">**Diversa** tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="502bd-157">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="502bd-158">Configurazione</span><span class="sxs-lookup"><span data-stu-id="502bd-158">Configure</span></span>  <br/> |<span data-ttu-id="502bd-159">FQDN esterno</span><span class="sxs-lookup"><span data-stu-id="502bd-159">External FQDN</span></span>  <br/> |<span data-ttu-id="502bd-160">**Stesso** tra gli elettrodomestici</span><span class="sxs-lookup"><span data-stu-id="502bd-160">**Same** across appliances</span></span> <br/> |<span data-ttu-id="502bd-161">**Diversa** tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="502bd-161">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="502bd-162">Configurazione</span><span class="sxs-lookup"><span data-stu-id="502bd-162">Configure</span></span>  <br/> |<span data-ttu-id="502bd-163">Indirizzi IP esterni</span><span class="sxs-lookup"><span data-stu-id="502bd-163">External IPs</span></span>  <br/> |<span data-ttu-id="502bd-164">**Diversa** tra gli strumenti</span><span class="sxs-lookup"><span data-stu-id="502bd-164">**Different** across appliances</span></span> <br/> |<span data-ttu-id="502bd-165">**Diversa** tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="502bd-165">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="502bd-166">Configurazione</span><span class="sxs-lookup"><span data-stu-id="502bd-166">Configure</span></span>  <br/> |<span data-ttu-id="502bd-167">Impostazioni GW PSTN</span><span class="sxs-lookup"><span data-stu-id="502bd-167">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="502bd-168">**Stesso** tra gli elettrodomestici</span><span class="sxs-lookup"><span data-stu-id="502bd-168">**Same** across appliances</span></span> <br/> |<span data-ttu-id="502bd-169">**Diversa** tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="502bd-169">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="502bd-170">Configurazione</span><span class="sxs-lookup"><span data-stu-id="502bd-170">Configure</span></span>  <br/> |<span data-ttu-id="502bd-171">Record DNS</span><span class="sxs-lookup"><span data-stu-id="502bd-171">DNS record</span></span>  <br/> |<span data-ttu-id="502bd-172">Aggiungere record con gli **stessi** FQDN di accesso esterno e indirizzi IP **diversi**</span><span class="sxs-lookup"><span data-stu-id="502bd-172">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="502bd-173">Aggiungere record con nomi FQDN di accesso esterno **diversi** e indirizzi IP **diversi**</span><span class="sxs-lookup"><span data-stu-id="502bd-173">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="502bd-174">Configurazione</span><span class="sxs-lookup"><span data-stu-id="502bd-174">Setup</span></span>  <br/> |<span data-ttu-id="502bd-175">Tenant ibrido</span><span class="sxs-lookup"><span data-stu-id="502bd-175">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="502bd-176">Impostare HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="502bd-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="502bd-177">Impostare PeerDestination per il fallback</span><span class="sxs-lookup"><span data-stu-id="502bd-177">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="502bd-178">Impostare HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="502bd-178">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="502bd-179">Impostare PeerDestination per il fallback</span><span class="sxs-lookup"><span data-stu-id="502bd-179">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="502bd-180">Configurazione</span><span class="sxs-lookup"><span data-stu-id="502bd-180">Setup</span></span>  <br/> |<span data-ttu-id="502bd-181">Gateway</span><span class="sxs-lookup"><span data-stu-id="502bd-181">Gateway</span></span>  <br/> |<span data-ttu-id="502bd-182">Mapping di MS GW **M:N** in questo sito</span><span class="sxs-lookup"><span data-stu-id="502bd-182">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="502bd-183">I gateway PSTN in ciascun sito PSTN devono connettersi solo ai Mediation Server nello stesso sito.</span><span class="sxs-lookup"><span data-stu-id="502bd-183">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="502bd-184">Configurazione</span><span class="sxs-lookup"><span data-stu-id="502bd-184">Setup</span></span>  <br/> |<span data-ttu-id="502bd-185">Utente</span><span class="sxs-lookup"><span data-stu-id="502bd-185">User</span></span>  <br/> |<span data-ttu-id="502bd-186">Impostare UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="502bd-186">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="502bd-187">Impostare UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="502bd-187">Set UserPSTNSettings</span></span>  <br/> |
   

