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
ms.openlocfilehash: 98890bb3ffe53497c5e915acba5c073c4316f3b7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799696"
---
# <a name="deploy-multiple-sites-in-cloud-connector"></a><span data-ttu-id="e2f2d-103">Distribuire più siti in Cloud Connector</span><span class="sxs-lookup"><span data-stu-id="e2f2d-103">Deploy multiple sites in Cloud Connector</span></span>
 
<span data-ttu-id="e2f2d-104">Informazioni sulla distribuzione di più siti PSTN in Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="e2f2d-104">Learn about deploying multiple PSTN sites in Cloud Connector Edition.</span></span>
  
<span data-ttu-id="e2f2d-105">Questa sezione descrive come distribuire più siti PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="e2f2d-105">This section describes how to deploy multiple Public Switched Telephone Network (PSTN) sites.</span></span> <span data-ttu-id="e2f2d-106">I siti vengono distribuiti uno alla volta con gli stessi passaggi della distribuzione di un singolo sito.</span><span class="sxs-lookup"><span data-stu-id="e2f2d-106">Sites are deployed one at a time using the same steps as deploying a single site.</span></span> <span data-ttu-id="e2f2d-107">In questo argomento vengono illustrate le considerazioni relative alle differenze tra i siti in una distribuzione di più siti.</span><span class="sxs-lookup"><span data-stu-id="e2f2d-107">This topic describes the considerations for and differences between sites in a multiple site deployment.</span></span> 
  
## <a name="multiple-public-switched-telephone-network-pstn-sites"></a><span data-ttu-id="e2f2d-108">Più siti PSTN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="e2f2d-108">Multiple Public Switched Telephone Network (PSTN) Sites</span></span>

<span data-ttu-id="e2f2d-109">Di seguito viene illustrata una configurazione di esempio per distribuire Skype for Business Cloud Connector Edition per diversi siti PSTN.</span><span class="sxs-lookup"><span data-stu-id="e2f2d-109">The following shows an example configuration to deploy Skype for Business Cloud Connector Edition for different PSTN sites.</span></span> <span data-ttu-id="e2f2d-110">Verificare che le impostazioni di configurazione siano corrette prima di avviare una distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e2f2d-110">Make sure your configuration settings are correct before you start a deployment.</span></span>
  
<span data-ttu-id="e2f2d-111">Sito PSTN 1</span><span class="sxs-lookup"><span data-stu-id="e2f2d-111">PSTN Site 1</span></span>
  
```
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

<span data-ttu-id="e2f2d-112">Sito PSTN 2</span><span class="sxs-lookup"><span data-stu-id="e2f2d-112">PSTN Site 2</span></span>
  
```
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

<span data-ttu-id="e2f2d-113">Per ogni sito PSTN che si vuole aggiungere, seguire la procedura descritta in [distribuire un singolo sito nel connettore Cloud](deploy-a-single-site-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="e2f2d-113">For each PSTN site that you want to add, follow the steps in [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="e2f2d-114">La cartella condivisa per la preparazione della disponibilità elevata (HA) è per ogni sito PSTN.</span><span class="sxs-lookup"><span data-stu-id="e2f2d-114">The shared folder for preparing High Availability (HA) is per PSTN site.</span></span> <span data-ttu-id="e2f2d-115">La cartella condivisa **deve** essere diversa tra i siti PSTN.</span><span class="sxs-lookup"><span data-stu-id="e2f2d-115">The shared folder **must** be different between PSTN sites.</span></span> <span data-ttu-id="e2f2d-116">Non usare la stessa cartella condivisa per più siti. ></span><span class="sxs-lookup"><span data-stu-id="e2f2d-116">Do not use the same shared folder for multiple sites.></span></span> 
  
## <a name="single-site-with-high-availability-ha-compared-to-multi-site-deployments"></a><span data-ttu-id="e2f2d-117">Sito singolo con elevata disponibilità (HA) rispetto alle distribuzioni multisito</span><span class="sxs-lookup"><span data-stu-id="e2f2d-117">Single site with High Availability (HA) compared to multi-site deployments</span></span>
<span data-ttu-id="e2f2d-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span><span class="sxs-lookup"><span data-stu-id="e2f2d-118"><a name="BKMK_SingleSitecomparedtomulti-site"> </a></span></span>

<span data-ttu-id="e2f2d-119">La tabella seguente elenca le differenze tra il sito singolo con il supporto di HA e una distribuzione di più siti.</span><span class="sxs-lookup"><span data-stu-id="e2f2d-119">The following table lists the differences between single site with HA support and a multiple site deployment.</span></span>
  
|<span data-ttu-id="e2f2d-120">**Categoria**</span><span class="sxs-lookup"><span data-stu-id="e2f2d-120">**Category**</span></span>|<span data-ttu-id="e2f2d-121">**Elemento**</span><span class="sxs-lookup"><span data-stu-id="e2f2d-121">**Item**</span></span>|<span data-ttu-id="e2f2d-122">**Singolo sito con HA**</span><span class="sxs-lookup"><span data-stu-id="e2f2d-122">**Single-Site with HA**</span></span>|<span data-ttu-id="e2f2d-123">**Multi-sito**</span><span class="sxs-lookup"><span data-stu-id="e2f2d-123">**Multi-Site**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e2f2d-124">Configurare</span><span class="sxs-lookup"><span data-stu-id="e2f2d-124">Configure</span></span>  <br/> |<span data-ttu-id="e2f2d-125">Nome host Appliance</span><span class="sxs-lookup"><span data-stu-id="e2f2d-125">Appliance Host Name</span></span> <br/> |<span data-ttu-id="e2f2d-126">**Diversi** dispositivi tra loro</span><span class="sxs-lookup"><span data-stu-id="e2f2d-126">**Different** across appliances</span></span> <br/> |<span data-ttu-id="e2f2d-127">**Diversi** tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="e2f2d-127">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="e2f2d-128">Configurazione</span><span class="sxs-lookup"><span data-stu-id="e2f2d-128">Setup</span></span>  <br/> |<span data-ttu-id="e2f2d-129">Cartella condivisa</span><span class="sxs-lookup"><span data-stu-id="e2f2d-129">Shared folder</span></span>  <br/> |<span data-ttu-id="e2f2d-130">Richiede la **stessa** cartella condivisa tra gli elettrodomestici</span><span class="sxs-lookup"><span data-stu-id="e2f2d-130">Requires the **same** shared folder across appliances</span></span> <br/> |<span data-ttu-id="e2f2d-131">Richiede una cartella condivisa **diversa** tra gli elettrodomestici</span><span class="sxs-lookup"><span data-stu-id="e2f2d-131">Requires a **different** shared folder across appliances</span></span> <br/> |
|<span data-ttu-id="e2f2d-132">Configurare</span><span class="sxs-lookup"><span data-stu-id="e2f2d-132">Configure</span></span>  <br/> |<span data-ttu-id="e2f2d-133">VirtualMachineDomain</span><span class="sxs-lookup"><span data-stu-id="e2f2d-133">VirtualMachineDomain</span></span>  <br/> |<span data-ttu-id="e2f2d-134">Richiede lo **stesso** dominio tra gli elettrodomestici</span><span class="sxs-lookup"><span data-stu-id="e2f2d-134">Requires the **same** domain across appliances</span></span> <br/> |<span data-ttu-id="e2f2d-135">Richiede lo **stesso** dominio nei siti PSTN</span><span class="sxs-lookup"><span data-stu-id="e2f2d-135">Requires the **same** domain across PSTN sites</span></span> <br/> |
|<span data-ttu-id="e2f2d-136">Configurare</span><span class="sxs-lookup"><span data-stu-id="e2f2d-136">Configure</span></span>  <br/> |<span data-ttu-id="e2f2d-137">SIPDomains</span><span class="sxs-lookup"><span data-stu-id="e2f2d-137">SIPDomains</span></span>  <br/> |<span data-ttu-id="e2f2d-138">I nomi di dominio e l'ordine devono essere **uguali** per tutti gli elettrodomestici</span><span class="sxs-lookup"><span data-stu-id="e2f2d-138">Domain names and order should be the **same** across appliances</span></span> <br/> |<span data-ttu-id="e2f2d-139">I nomi di dominio e l'ordine devono essere **uguali** in tutti i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="e2f2d-139">Domain names and order should be the **same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="e2f2d-140">Configurare</span><span class="sxs-lookup"><span data-stu-id="e2f2d-140">Configure</span></span>  <br/> |<span data-ttu-id="e2f2d-141">Nome sito</span><span class="sxs-lookup"><span data-stu-id="e2f2d-141">Site name</span></span>  <br/> |<span data-ttu-id="e2f2d-142">**Stessa** Nome sito tra gli elettrodomestici</span><span class="sxs-lookup"><span data-stu-id="e2f2d-142">**Same** Site Name across appliances</span></span> <br/> |<span data-ttu-id="e2f2d-143">**Diversi** Nome sito nei siti PSTN</span><span class="sxs-lookup"><span data-stu-id="e2f2d-143">**Different** Site Name across PSTN sites</span></span> <br/> |
|<span data-ttu-id="e2f2d-144">Configurare</span><span class="sxs-lookup"><span data-stu-id="e2f2d-144">Configure</span></span>  <br/> |<span data-ttu-id="e2f2d-145">Nomi dei server</span><span class="sxs-lookup"><span data-stu-id="e2f2d-145">Server names</span></span>  <br/> |<span data-ttu-id="e2f2d-146">**Diversi** dispositivi tra loro</span><span class="sxs-lookup"><span data-stu-id="e2f2d-146">**Different** across appliances</span></span> <br/> |<span data-ttu-id="e2f2d-147">**Diversi** tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="e2f2d-147">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="e2f2d-148">Configurare</span><span class="sxs-lookup"><span data-stu-id="e2f2d-148">Configure</span></span>  <br/> |<span data-ttu-id="e2f2d-149">FQDN del pool interno</span><span class="sxs-lookup"><span data-stu-id="e2f2d-149">Internal pool FQDNs</span></span>  <br/> |<span data-ttu-id="e2f2d-150">**Stessa** tra gli elettrodomestici</span><span class="sxs-lookup"><span data-stu-id="e2f2d-150">**Same** across appliances</span></span> <br/> |<span data-ttu-id="e2f2d-151">**Lo stesso** per tutti i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="e2f2d-151">**Same** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="e2f2d-152">Configurare</span><span class="sxs-lookup"><span data-stu-id="e2f2d-152">Configure</span></span>  <br/> |<span data-ttu-id="e2f2d-153">IPs interno</span><span class="sxs-lookup"><span data-stu-id="e2f2d-153">Internal IPs</span></span>  <br/> |<span data-ttu-id="e2f2d-154">**Diversi** dispositivi tra loro</span><span class="sxs-lookup"><span data-stu-id="e2f2d-154">**Different** across appliances</span></span> <br/> |<span data-ttu-id="e2f2d-155">**Diversi** tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="e2f2d-155">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="e2f2d-156">Configurare</span><span class="sxs-lookup"><span data-stu-id="e2f2d-156">Configure</span></span>  <br/> |<span data-ttu-id="e2f2d-157">FQDN esterno</span><span class="sxs-lookup"><span data-stu-id="e2f2d-157">External FQDN</span></span>  <br/> |<span data-ttu-id="e2f2d-158">**Stessa** tra gli elettrodomestici</span><span class="sxs-lookup"><span data-stu-id="e2f2d-158">**Same** across appliances</span></span> <br/> |<span data-ttu-id="e2f2d-159">**Diversi** tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="e2f2d-159">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="e2f2d-160">Configurare</span><span class="sxs-lookup"><span data-stu-id="e2f2d-160">Configure</span></span>  <br/> |<span data-ttu-id="e2f2d-161">IPs esterni</span><span class="sxs-lookup"><span data-stu-id="e2f2d-161">External IPs</span></span>  <br/> |<span data-ttu-id="e2f2d-162">**Diversi** dispositivi tra loro</span><span class="sxs-lookup"><span data-stu-id="e2f2d-162">**Different** across appliances</span></span> <br/> |<span data-ttu-id="e2f2d-163">**Diversi** tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="e2f2d-163">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="e2f2d-164">Configurare</span><span class="sxs-lookup"><span data-stu-id="e2f2d-164">Configure</span></span>  <br/> |<span data-ttu-id="e2f2d-165">Impostazioni GW PSTN</span><span class="sxs-lookup"><span data-stu-id="e2f2d-165">PSTN GW settings</span></span>  <br/> |<span data-ttu-id="e2f2d-166">**Stessa** tra gli elettrodomestici</span><span class="sxs-lookup"><span data-stu-id="e2f2d-166">**Same** across appliances</span></span> <br/> |<span data-ttu-id="e2f2d-167">**Diversi** tra i siti PSTN</span><span class="sxs-lookup"><span data-stu-id="e2f2d-167">**Different** across PSTN sites</span></span> <br/> |
|<span data-ttu-id="e2f2d-168">Configurare</span><span class="sxs-lookup"><span data-stu-id="e2f2d-168">Configure</span></span>  <br/> |<span data-ttu-id="e2f2d-169">Record DNS</span><span class="sxs-lookup"><span data-stu-id="e2f2d-169">DNS record</span></span>  <br/> |<span data-ttu-id="e2f2d-170">Aggiungere record con gli **stessi** FQDN di accesso esterno e indirizzi IP **diversi**</span><span class="sxs-lookup"><span data-stu-id="e2f2d-170">Add records with the **same** External Access FQDNs and **different** IP addresses</span></span> <br/> |<span data-ttu-id="e2f2d-171">Aggiungere record con FQDN di accesso esterno **diverso** e indirizzi IP **diversi**</span><span class="sxs-lookup"><span data-stu-id="e2f2d-171">Add records with **different** External Access FQDNs and **different** IP addresses</span></span> <br/> |
|<span data-ttu-id="e2f2d-172">Configurazione</span><span class="sxs-lookup"><span data-stu-id="e2f2d-172">Setup</span></span>  <br/> |<span data-ttu-id="e2f2d-173">Tenant ibrido</span><span class="sxs-lookup"><span data-stu-id="e2f2d-173">Hybrid tenant</span></span>  <br/> |<span data-ttu-id="e2f2d-174">Impostare HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="e2f2d-174">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="e2f2d-175">Impostare PeerDestination per il fallback</span><span class="sxs-lookup"><span data-stu-id="e2f2d-175">Set PeerDestination for fallback</span></span>  <br/> |<span data-ttu-id="e2f2d-176">Impostare HybridPSTNSite</span><span class="sxs-lookup"><span data-stu-id="e2f2d-176">Set HybridPSTNSite</span></span>  <br/> <span data-ttu-id="e2f2d-177">Impostare PeerDestination per il fallback</span><span class="sxs-lookup"><span data-stu-id="e2f2d-177">Set PeerDestination for fallback</span></span>  <br/> |
|<span data-ttu-id="e2f2d-178">Configurazione</span><span class="sxs-lookup"><span data-stu-id="e2f2d-178">Setup</span></span>  <br/> |<span data-ttu-id="e2f2d-179">Gateway</span><span class="sxs-lookup"><span data-stu-id="e2f2d-179">Gateway</span></span>  <br/> |<span data-ttu-id="e2f2d-180">Mappatura di MS GW **M:N** in questo sito</span><span class="sxs-lookup"><span data-stu-id="e2f2d-180">MS GW **M:N** mapping in this site</span></span> <br/> |<span data-ttu-id="e2f2d-181">I gateway PSTN in ogni sito PSTN devono connettersi solo ai server di mediazione nello stesso sito</span><span class="sxs-lookup"><span data-stu-id="e2f2d-181">PSTN gateway(s) in each PSTN site should only connect to the Mediation Server(s) in the same site</span></span>  <br/> |
|<span data-ttu-id="e2f2d-182">Configurazione</span><span class="sxs-lookup"><span data-stu-id="e2f2d-182">Setup</span></span>  <br/> |<span data-ttu-id="e2f2d-183">Utente</span><span class="sxs-lookup"><span data-stu-id="e2f2d-183">User</span></span>  <br/> |<span data-ttu-id="e2f2d-184">Impostare UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="e2f2d-184">Set UserPSTNSettings</span></span>  <br/> |<span data-ttu-id="e2f2d-185">Impostare UserPSTNSettings</span><span class="sxs-lookup"><span data-stu-id="e2f2d-185">Set UserPSTNSettings</span></span>  <br/> |
   

