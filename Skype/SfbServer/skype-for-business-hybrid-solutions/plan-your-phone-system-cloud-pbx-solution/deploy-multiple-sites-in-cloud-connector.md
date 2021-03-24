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
ms.openlocfilehash: 059b9a39a082e876b1dd9cd772a235c384a29107
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098402"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="2be24-103">Distribuire più siti in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="2be24-103">Deploy multiple sites in Cloud Connector</span></span>

> [!Important] 
> <span data-ttu-id="2be24-104">Cloud Connector Edition andrà in pensione il 31 luglio 2021 insieme a Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="2be24-104">Cloud Connector Edition will retire July 31, 2021 along with Skype for Business Online.</span></span> <span data-ttu-id="2be24-105">Dopo l'aggiornamento dell'organizzazione a Teams, informazioni su come connettere la rete di telefonia locale a Teams tramite [Routing diretto.](/MicrosoftTeams/direct-routing-landing-page)</span><span class="sxs-lookup"><span data-stu-id="2be24-105">Once your organization has upgraded to Teams, learn how to connect your on-premises telephony network to Teams using [Direct Routing](/MicrosoftTeams/direct-routing-landing-page).</span></span>

<span data-ttu-id="2be24-106">Informazioni sulla distribuzione di più siti PSTN in Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="2be24-106">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="2be24-107">In questa sezione viene descritto come distribuire più siti PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="2be24-107">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="2be24-108">I siti vengono distribuiti uno alla volta utilizzando gli stessi passaggi della distribuzione di un singolo sito.</span><span class="sxs-lookup"><span data-stu-id="2be24-108">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="2be24-109">In questo argomento vengono descritte le considerazioni e le differenze tra i siti in una distribuzione a più siti.</span><span class="sxs-lookup"><span data-stu-id="2be24-109">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="2be24-110">Più siti PSTN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="2be24-110">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="2be24-111">Di seguito viene illustrata una configurazione di esempio per distribuire Skype for Business Cloud Connector Edition per diversi siti PSTN.</span><span class="sxs-lookup"><span data-stu-id="2be24-111">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="2be24-112">Verificare che le impostazioni di configurazione siano corrette prima di avviare una distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2be24-112">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="2be24-113">Sito PSTN 1</span><span class="sxs-lookup"><span data-stu-id="2be24-113">PSTN Site 1</span></span>
  
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

<span data-ttu-id="2be24-114">Sito PSTN 2</span><span class="sxs-lookup"><span data-stu-id="2be24-114">PSTN Site 2</span></span>
  
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

<span data-ttu-id="2be24-115">Per ogni sito PSTN che si desidera aggiungere, seguire i passaggi descritti in [Deploy a single site in Cloud Connector.](deploy-a-single-site-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="2be24-115">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="2be24-116">La cartella condivisa per la preparazione della disponibilità elevata (HA) è per ogni sito PSTN.</span><span class="sxs-lookup"><span data-stu-id="2be24-116">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="2be24-117">La cartella condivisa **deve** essere diversa tra i siti PSTN.</span><span class="sxs-lookup"><span data-stu-id="2be24-117">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="2be24-118">Non utilizzare la stessa cartella condivisa per più siti.></span><span class="sxs-lookup"><span data-stu-id="2be24-118">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="2be24-119">Sito singolo con disponibilità elevata rispetto alle distribuzioni multisocietà</span><span class="sxs-lookup"><span data-stu-id="2be24-119">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="2be24-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="2be24-120"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="2be24-121">Nella tabella seguente sono elencate le differenze tra un singolo sito con supporto ha e una distribuzione a più siti.</span><span class="sxs-lookup"><span data-stu-id="2be24-121">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="2be24-122">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="2be24-122">**Category**</span></span>|<span data-ttu-id="2be24-123">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="2be24-123">**Item**</span></span>|<span data-ttu-id="2be24-124">**Sito singolo con ha**</span><span class="sxs-lookup"><span data-stu-id="2be24-124">**Single-Site with HA**</span></span>|<span data-ttu-id="2be24-125">**Multisnode**</span><span class="sxs-lookup"><span data-stu-id="2be24-125">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2be24-126">Configurazione</span><span class="sxs-lookup"><span data-stu-id="2be24-126">Configure</span></span>  <br/> |<span data-ttu-id="2be24-127">Nome host appliance</span><span class="sxs-lookup"><span data-stu-id="2be24-127">Appliance Host Name</span></span> <br/> |<span data-ttu-id="2be24-128">**Diversi** tra gli appliance</span><span class="sxs-lookup"><span data-stu-id="2be24-128">**Different** across appliances</span></span> <br/> |<span data-ttu-id="2be24-129">**Diversi** tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="2be24-129">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="2be24-130">Installazione</span><span class="sxs-lookup"><span data-stu-id="2be24-130">Setup</span></span>  <br/> |<span data-ttu-id="2be24-131">Cartella condivisa</span><span class="sxs-lookup"><span data-stu-id="2be24-131">Shared folder</span></span>  <br/> |<span data-ttu-id="2be24-132">Richiede la **stessa cartella** condivisa tra le appliance</span><span class="sxs-lookup"><span data-stu-id="2be24-132">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="2be24-133">Richiede una **cartella condivisa** diversa tra le appliance</span><span class="sxs-lookup"><span data-stu-id="2be24-133">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="2be24-134">Configurazione</span><span class="sxs-lookup"><span data-stu-id="2be24-134">Configure</span></span>  <br/> |<span data-ttu-id="2be24-135">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="2be24-135">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="2be24-136">Richiede lo **stesso dominio** tra le appliance</span><span class="sxs-lookup"><span data-stu-id="2be24-136">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="2be24-137">Richiede lo **stesso dominio** tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="2be24-137">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="2be24-138">Configurazione</span><span class="sxs-lookup"><span data-stu-id="2be24-138">Configure</span></span>  <br/> |<span data-ttu-id="2be24-139">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="2be24-139">SIPDomains</span></span>  <br/> |<span data-ttu-id="2be24-140">I nomi di dominio e l'ordine devono **essere gli stessi tra** le appliance</span><span class="sxs-lookup"><span data-stu-id="2be24-140">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="2be24-141">I nomi di dominio e l'ordine devono **essere uguali nei** siti PSTN</span><span class="sxs-lookup"><span data-stu-id="2be24-141">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="2be24-142">Configurazione</span><span class="sxs-lookup"><span data-stu-id="2be24-142">Configure</span></span>  <br/> |<span data-ttu-id="2be24-143">Nome sito</span><span class="sxs-lookup"><span data-stu-id="2be24-143">Site name</span></span>  <br/> |<span data-ttu-id="2be24-144">**Same** Nome sito tra appliance</span><span class="sxs-lookup"><span data-stu-id="2be24-144">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="2be24-145">**Differente** Nome sito nei siti PSTN</span><span class="sxs-lookup"><span data-stu-id="2be24-145">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="2be24-146">Configurazione</span><span class="sxs-lookup"><span data-stu-id="2be24-146">Configure</span></span>  <br/> |<span data-ttu-id="2be24-147">Nomi dei server</span><span class="sxs-lookup"><span data-stu-id="2be24-147">Server names</span></span>  <br/> |<span data-ttu-id="2be24-148">**Diversi** tra gli appliance</span><span class="sxs-lookup"><span data-stu-id="2be24-148">**Different** across appliances</span></span> <br/> |<span data-ttu-id="2be24-149">**Diversi** tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="2be24-149">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="2be24-150">Configurazione</span><span class="sxs-lookup"><span data-stu-id="2be24-150">Configure</span></span>  <br/> |<span data-ttu-id="2be24-151">FQDN del pool interno</span><span class="sxs-lookup"><span data-stu-id="2be24-151">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="2be24-152">**Uguale per** tutti gli appliance</span><span class="sxs-lookup"><span data-stu-id="2be24-152">**Same** across appliances</span></span> <br/> |<span data-ttu-id="2be24-153">**Stessa cosa** nei siti PSTN</span><span class="sxs-lookup"><span data-stu-id="2be24-153">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="2be24-154">Configurazione</span><span class="sxs-lookup"><span data-stu-id="2be24-154">Configure</span></span>  <br/> |<span data-ttu-id="2be24-155">IP interni</span><span class="sxs-lookup"><span data-stu-id="2be24-155">Internal IPs</span></span>  <br/> |<span data-ttu-id="2be24-156">**Diversi** tra gli appliance</span><span class="sxs-lookup"><span data-stu-id="2be24-156">**Different** across appliances</span></span> <br/> |<span data-ttu-id="2be24-157">**Diversi** tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="2be24-157">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="2be24-158">Configurazione</span><span class="sxs-lookup"><span data-stu-id="2be24-158">Configure</span></span>  <br/> |<span data-ttu-id="2be24-159">FQDN esterno</span><span class="sxs-lookup"><span data-stu-id="2be24-159">External FQDN</span></span>  <br/> |<span data-ttu-id="2be24-160">**Uguale per** tutti gli appliance</span><span class="sxs-lookup"><span data-stu-id="2be24-160">**Same** across appliances</span></span> <br/> |<span data-ttu-id="2be24-161">**Diversi** tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="2be24-161">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="2be24-162">Configurazione</span><span class="sxs-lookup"><span data-stu-id="2be24-162">Configure</span></span>  <br/> |<span data-ttu-id="2be24-163">IP esterni</span><span class="sxs-lookup"><span data-stu-id="2be24-163">External IPs</span></span>  <br/> |<span data-ttu-id="2be24-164">**Diversi** tra gli appliance</span><span class="sxs-lookup"><span data-stu-id="2be24-164">**Different** across appliances</span></span> <br/> |<span data-ttu-id="2be24-165">**Diversi** tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="2be24-165">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="2be24-166">Configurazione</span><span class="sxs-lookup"><span data-stu-id="2be24-166">Configure</span></span>  <br/> |<span data-ttu-id="2be24-167">Impostazioni PSTN GW</span><span class="sxs-lookup"><span data-stu-id="2be24-167">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="2be24-168">**Uguale per** tutti gli appliance</span><span class="sxs-lookup"><span data-stu-id="2be24-168">**Same** across appliances</span></span> <br/> |<span data-ttu-id="2be24-169">**Diversi** tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="2be24-169">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="2be24-170">Configurazione</span><span class="sxs-lookup"><span data-stu-id="2be24-170">Configure</span></span>  <br/> |<span data-ttu-id="2be24-171">Record DNS</span><span class="sxs-lookup"><span data-stu-id="2be24-171">DNS record</span></span>  <br/> |<span data-ttu-id="2be24-172">Aggiungere record con gli **stessi** FQDN di accesso esterno e **indirizzi** IP diversi</span><span class="sxs-lookup"><span data-stu-id="2be24-172">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="2be24-173">Aggiungere record con **fqdn** di accesso esterno diversi e **indirizzi** IP diversi</span><span class="sxs-lookup"><span data-stu-id="2be24-173">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="2be24-174">Installazione</span><span class="sxs-lookup"><span data-stu-id="2be24-174">Setup</span></span>  <br/> |<span data-ttu-id="2be24-175">Tenant ibrido</span><span class="sxs-lookup"><span data-stu-id="2be24-175">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="2be24-176">Set HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="2be24-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="2be24-177">Impostare PeerDestination per il fallback</span><span class="sxs-lookup"><span data-stu-id="2be24-177">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="2be24-178">Set HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="2be24-178">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="2be24-179">Impostare PeerDestination per il fallback</span><span class="sxs-lookup"><span data-stu-id="2be24-179">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="2be24-180">Installazione</span><span class="sxs-lookup"><span data-stu-id="2be24-180">Setup</span></span>  <br/> |<span data-ttu-id="2be24-181">Gateway</span><span class="sxs-lookup"><span data-stu-id="2be24-181">Gateway</span></span>  <br/> |<span data-ttu-id="2be24-182">Ms GW **M:N** mapping in questo sito</span><span class="sxs-lookup"><span data-stu-id="2be24-182">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="2be24-183">I gateway PSTN in ogni sito PSTN devono connettersi solo ai Mediation Server nello stesso sito</span><span class="sxs-lookup"><span data-stu-id="2be24-183">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="2be24-184">Installazione</span><span class="sxs-lookup"><span data-stu-id="2be24-184">Setup</span></span>  <br/> |<span data-ttu-id="2be24-185">User</span><span class="sxs-lookup"><span data-stu-id="2be24-185">User</span></span>  <br/> |<span data-ttu-id="2be24-186">Impostare UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="2be24-186">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="2be24-187">Impostare UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="2be24-187">Set UserPSTNSettings</span></span>  <br/> |
