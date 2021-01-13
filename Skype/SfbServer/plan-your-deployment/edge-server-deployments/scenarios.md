---
title: Scenari del server perimetrale in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
audience: ITPro
ms.topic: conceptual
manager: serdars
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 7b9c211b-deb0-479d-b184-973f08b96d07
description: 'Riepilogo: esaminare questi scenari per semplificare la pianificazione della topologia del server perimetrale in Skype for Business Server.'
ms.openlocfilehash: cfcc1e8b34576fbec85464fb8d5e35903b47d8ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813792"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="64fc2-103">Scenari del server perimetrale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="64fc2-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="64fc2-104">**Riepilogo:** Esaminare questi scenari per semplificare la pianificazione della topologia del server perimetrale in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="64fc2-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="64fc2-105">Sono disponibili alcuni diagrammi degli scenari per facilitare la visualizzazione e la scelta di una topologia del server perimetrale di Skype for Business Server che si desidera implementare.</span><span class="sxs-lookup"><span data-stu-id="64fc2-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="64fc2-106">Dopo aver scelto un buon candidato, è possibile andare a leggere i requisiti ambientali necessari per l'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="64fc2-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="64fc2-107">Il seguente è applicabile a tutti gli scenari, per cui viene menzionato per primo.</span><span class="sxs-lookup"><span data-stu-id="64fc2-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="64fc2-108">Queste cifre, che sono mostrate solo a scopo esemplificativo (e come tali contengono dati IPv4 e IPv6 di esempio), non rappresentano il flusso di comunicazione effettivo, bensì una visualizzazione di alto livello del traffico possibile.</span><span class="sxs-lookup"><span data-stu-id="64fc2-108">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic.</span></span> <span data-ttu-id="64fc2-109">I dettagli delle porte possono essere visualizzati anche nei diagrammi delle porte per ogni scenario di seguito.</span><span class="sxs-lookup"><span data-stu-id="64fc2-109">Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="64fc2-110">I diagrammi mostrano. com per l'interfaccia esterna e .NET per l'interno, che è anche materiale di esempio. Naturalmente, è possibile che le proprie voci siano molto diverse quando si sta mettendo insieme il proprio piano definitivo Edge.</span><span class="sxs-lookup"><span data-stu-id="64fc2-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="64fc2-111">Non è incluso il Director (che è un componente facoltativo) in uno dei diagrammi, ma è possibile leggerlo separatamente (è menzionato in altri argomenti di pianificazione).</span><span class="sxs-lookup"><span data-stu-id="64fc2-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="64fc2-112">Come indicato in alto, nei diagrammi sono presenti dati IPv6 di esempio.</span><span class="sxs-lookup"><span data-stu-id="64fc2-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="64fc2-113">La maggior parte della documentazione in [Plan for Edge Server Deployments in Skype for Business Server](edge-server-deployments.md) si riferisce a IPv4, ma è certamente supportato se si desidera utilizzare IPv6.</span><span class="sxs-lookup"><span data-stu-id="64fc2-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="64fc2-114">Tenere presente che gli indirizzi IPv6 sono necessari nello spazio di indirizzi assegnato e dovranno collaborare con l'indirizzamento interno ed esterno, come con gli IP IPv4.</span><span class="sxs-lookup"><span data-stu-id="64fc2-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="64fc2-115">È possibile, grazie a Windows, utilizzare la funzionalità dual stack, che è uno stack di rete distinto e distinti per IPv4 e IPv6.</span><span class="sxs-lookup"><span data-stu-id="64fc2-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="64fc2-116">In questo modo, se necessario, è possibile assegnare contemporaneamente gli indirizzi IPv4 e IPv6.</span><span class="sxs-lookup"><span data-stu-id="64fc2-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="64fc2-117">Esistono dispositivi NAT che consentono NAT64 (IPv6 a IPv4) e NAT66 (IPv6 a IPv6)) e questo è valido per l'utilizzo con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="64fc2-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="64fc2-118">Se si utilizza il controllo di ammissione di chiamata (CAC), è necessario utilizzare IPv4 sull'interfaccia interna affinché funzioni.</span><span class="sxs-lookup"><span data-stu-id="64fc2-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="64fc2-119">Server perimetrale Single Consolidated Skype for Business Server con indirizzi IP privati e NAT</span><span class="sxs-lookup"><span data-stu-id="64fc2-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="64fc2-120">In questo scenario, non è disponibile alcuna opzione per la disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="64fc2-120">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="64fc2-121">In questo modo si spende meno sull'hardware e si dispone di una distribuzione più semplice.</span><span class="sxs-lookup"><span data-stu-id="64fc2-121">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="64fc2-122">Se è necessario disporre di disponibilità elevata, vedere gli scenari consolidati in scala di seguito.</span><span class="sxs-lookup"><span data-stu-id="64fc2-122">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Scenario perimetrale per un singolo server perimetrale consolidato con IP privato tramite NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="64fc2-124">Diagramma porta</span><span class="sxs-lookup"><span data-stu-id="64fc2-124">Port diagram</span></span>

<span data-ttu-id="64fc2-125">È inoltre presente un diagramma per le porte per i singoli server perimetrali consolidati.</span><span class="sxs-lookup"><span data-stu-id="64fc2-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Perimetro di rete per lo scenario perimetrale Single Consolidated Edge](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="64fc2-127">Server perimetrale Single Consolidated Skype for Business Server con indirizzi IP pubblici</span><span class="sxs-lookup"><span data-stu-id="64fc2-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="64fc2-128">In questo scenario, non è disponibile alcuna opzione per la disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="64fc2-128">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="64fc2-129">In questo modo si spende meno sull'hardware e si dispone di una distribuzione più semplice.</span><span class="sxs-lookup"><span data-stu-id="64fc2-129">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="64fc2-130">Se è necessario disporre di disponibilità elevata, vedere gli scenari consolidati in scala di seguito.</span><span class="sxs-lookup"><span data-stu-id="64fc2-130">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Scenario perimetrale per un singolo server perimetrale consolidato con IP pubblico](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="64fc2-132">Diagramma porta</span><span class="sxs-lookup"><span data-stu-id="64fc2-132">Port diagram</span></span>

<span data-ttu-id="64fc2-133">È inoltre presente un diagramma per le porte per i singoli server perimetrali consolidati.</span><span class="sxs-lookup"><span data-stu-id="64fc2-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Perimetro di rete per lo scenario perimetrale Single Consolidated Edge](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="64fc2-135">Pool di server perimetrali di Skype for business consolidato in scala, con bilanciamento del carico DNS e indirizzi IP privati e NAT</span><span class="sxs-lookup"><span data-stu-id="64fc2-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="64fc2-136">In questo scenario, è possibile disporre di disponibilità elevata nella distribuzione dei server perimetrali, che offre i vantaggi della scalabilità e del supporto per il failover.</span><span class="sxs-lookup"><span data-stu-id="64fc2-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Scenario perimetrale per il server perimetrale consolidato in scala, DNS LB con IP privato tramite NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="64fc2-138">Diagramma porta</span><span class="sxs-lookup"><span data-stu-id="64fc2-138">Port diagram</span></span>

<span data-ttu-id="64fc2-139">È inoltre presente un diagramma per i pool di server perimetrali consolidati in scala con bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="64fc2-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Perimetro di rete per gli scenari perimetrali in scala consolidata Edge con DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="64fc2-141">Pool di server perimetrali consolidati in scala Skype for business, con bilanciamento del carico DNS e indirizzi IP pubblici</span><span class="sxs-lookup"><span data-stu-id="64fc2-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="64fc2-142">In questo scenario, è possibile disporre di disponibilità elevata nella distribuzione dei server perimetrali, che offre i vantaggi della scalabilità e del supporto per il failover.</span><span class="sxs-lookup"><span data-stu-id="64fc2-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Scenario perimetrale per il server perimetrale consolidato in scala, DNS LB con IP pubblico](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="64fc2-144">Diagramma porta</span><span class="sxs-lookup"><span data-stu-id="64fc2-144">Port diagram</span></span>

<span data-ttu-id="64fc2-145">È inoltre presente un diagramma per i pool di server perimetrali consolidati in scala con bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="64fc2-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Perimetro di rete per gli scenari perimetrali in scala consolidata Edge con DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="64fc2-147">Pool di server perimetrali di Skype for business consolidato in scala con bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="64fc2-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="64fc2-148">In questo scenario, è possibile disporre di disponibilità elevata nella distribuzione dei server perimetrali, che offre i vantaggi della scalabilità e del supporto per il failover.</span><span class="sxs-lookup"><span data-stu-id="64fc2-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Scenario perimetrale per il server perimetrale consolidato in scala con HLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
