---
title: Scenari di Edge Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: 'Riepilogo: rivedere questi scenari per pianificare la topologia di Edge Server in Skype for Business Server.'
ms.openlocfilehash: a1d721ffabb78985d90848784cd587bda96300d5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803356"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="9d50a-103">Scenari di Edge Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9d50a-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="9d50a-104">**Riepilogo:** Esaminare questi scenari per pianificare la topologia di Edge Server in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9d50a-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="9d50a-105">Sono disponibili alcuni diagrammi scenari per facilitare la visualizzazione e la scelta della topologia di Skype for Business Server Edge Server che si vuole implementare.</span><span class="sxs-lookup"><span data-stu-id="9d50a-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="9d50a-106">Dopo aver scelto un buon candidato, è possibile leggere i requisiti ambientali che è necessario affrontare.</span><span class="sxs-lookup"><span data-stu-id="9d50a-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="9d50a-107">La procedura seguente è applicabile a qualsiasi scenario, quindi la menzioniamo per primo.</span><span class="sxs-lookup"><span data-stu-id="9d50a-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="9d50a-108">Queste cifre, visualizzate ad esempio solo per scopi (e come tali contengono dati IPv4 e IPv6 di esempio), non rappresentano il flusso di comunicazione effettivo, ma piuttosto una visualizzazione di alto livello del traffico possibile.</span><span class="sxs-lookup"><span data-stu-id="9d50a-108">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic.</span></span> <span data-ttu-id="9d50a-109">I dettagli della porta possono essere visualizzati anche nei diagrammi di porta per ogni scenario seguente.</span><span class="sxs-lookup"><span data-stu-id="9d50a-109">Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="9d50a-110">I diagrammi mostrano. com per l'interfaccia esterna e .NET per l'interno, che è anche materiale di esempio; Naturalmente, le tue voci possono essere molto diverse quando si sta mettendo insieme il proprio piano finale.</span><span class="sxs-lookup"><span data-stu-id="9d50a-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="9d50a-111">Non includiamo il Director (che è un componente facoltativo) in uno dei diagrammi, ma è possibile leggerlo separatamente (menzionato in altri argomenti della pianificazione).</span><span class="sxs-lookup"><span data-stu-id="9d50a-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="9d50a-112">Come indicato in precedenza, nei diagrammi sono presenti dati IPv6 di esempio.</span><span class="sxs-lookup"><span data-stu-id="9d50a-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="9d50a-113">La maggior parte della documentazione in [piano per le distribuzioni di Edge Server in Skype for Business Server](edge-server-deployments.md) si riferisce a IPv4, ma si è certamente supportati se si vuole usare IPv6.</span><span class="sxs-lookup"><span data-stu-id="9d50a-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="9d50a-114">Tieni presente che ti serviranno indirizzi IPv6 nello spazio di indirizzi assegnato e dovrai usare l'indirizzamento interno ed esterno, come per gli IPs IPv4.</span><span class="sxs-lookup"><span data-stu-id="9d50a-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="9d50a-115">Grazie a Windows, è possibile usare la caratteristica dual stack, che è uno stack di rete distinto per IPv4 e IPv6.</span><span class="sxs-lookup"><span data-stu-id="9d50a-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="9d50a-116">Questa operazione, se necessario, consente di assegnare contemporaneamente indirizzi IPv4 e IPv6.</span><span class="sxs-lookup"><span data-stu-id="9d50a-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="9d50a-117">Esistono dispositivi NAT che consentono di NAT64 (IPv6 a IPv4) e NAT66 (IPv6 to IPv6)) e questo è valido per l'uso con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9d50a-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="9d50a-118">Se si usa il controllo di ammissione di chiamata (CAC), è necessario usare IPv4 sull'interfaccia interna per farlo funzionare.</span><span class="sxs-lookup"><span data-stu-id="9d50a-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="9d50a-119">Singolo server Edge Skype for business consolidato con indirizzi IP privati e NAT</span><span class="sxs-lookup"><span data-stu-id="9d50a-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="9d50a-120">Con questo scenario, non esiste alcuna opzione per la disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="9d50a-120">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="9d50a-121">In questo modo si spende meno sull'hardware e si ha una distribuzione più semplice.</span><span class="sxs-lookup"><span data-stu-id="9d50a-121">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="9d50a-122">Se la disponibilità elevata è necessaria, vedere gli scenari consolidati in scala più avanti.</span><span class="sxs-lookup"><span data-stu-id="9d50a-122">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Scenario Edge per il singolo Edge consolidato con IP privato tramite NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="9d50a-124">Diagramma di porta</span><span class="sxs-lookup"><span data-stu-id="9d50a-124">Port diagram</span></span>

<span data-ttu-id="9d50a-125">È inoltre presente un diagramma per le porte per i singoli server perimetrali consolidati.</span><span class="sxs-lookup"><span data-stu-id="9d50a-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Perimetro di rete per lo scenario Edge Single Edge consolidato](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="9d50a-127">Singolo server Edge Skype for business consolidato con indirizzi IP pubblici</span><span class="sxs-lookup"><span data-stu-id="9d50a-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="9d50a-128">Con questo scenario, non esiste alcuna opzione per la disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="9d50a-128">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="9d50a-129">In questo modo si spende meno sull'hardware e si ha una distribuzione più semplice.</span><span class="sxs-lookup"><span data-stu-id="9d50a-129">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="9d50a-130">Se la disponibilità elevata è necessaria, vedere gli scenari consolidati in scala più avanti.</span><span class="sxs-lookup"><span data-stu-id="9d50a-130">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Scenario Edge per il singolo Edge consolidato con IP pubblico](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="9d50a-132">Diagramma di porta</span><span class="sxs-lookup"><span data-stu-id="9d50a-132">Port diagram</span></span>

<span data-ttu-id="9d50a-133">È inoltre presente un diagramma per le porte per i singoli server perimetrali consolidati.</span><span class="sxs-lookup"><span data-stu-id="9d50a-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Perimetro di rete per lo scenario Edge Single Edge consolidato](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="9d50a-135">In scala consolidato Skype for Business Server Edge pool, con DNS bilanciamento del carico e indirizzi IP privati e NAT</span><span class="sxs-lookup"><span data-stu-id="9d50a-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="9d50a-136">Con questo scenario puoi avere una disponibilità elevata nella distribuzione di Edge, che ti offre i vantaggi della scalabilità e del supporto per il failover.</span><span class="sxs-lookup"><span data-stu-id="9d50a-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Scenario Edge per Edge consolidato in scala, DNS LB con IP privato tramite NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="9d50a-138">Diagramma di porta</span><span class="sxs-lookup"><span data-stu-id="9d50a-138">Port diagram</span></span>

<span data-ttu-id="9d50a-139">È inoltre presente un diagramma per i pool di bordi consolidati in scala con il bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="9d50a-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Perimetro di rete per lo scenario Edge in scala consolidata con DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="9d50a-141">In scala consolidato Skype for Business Server Edge pool, con DNS di bilanciamento del carico e indirizzi IP pubblici</span><span class="sxs-lookup"><span data-stu-id="9d50a-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="9d50a-142">Con questo scenario puoi avere una disponibilità elevata nella distribuzione di Edge, che ti offre i vantaggi della scalabilità e del supporto per il failover.</span><span class="sxs-lookup"><span data-stu-id="9d50a-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Scenario Edge per Edge consolidato in scala, DNS LB con IP pubblico](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="9d50a-144">Diagramma di porta</span><span class="sxs-lookup"><span data-stu-id="9d50a-144">Port diagram</span></span>

<span data-ttu-id="9d50a-145">È inoltre presente un diagramma per i pool di bordi consolidati in scala con il bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="9d50a-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Perimetro di rete per lo scenario Edge in scala consolidata con DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="9d50a-147">Scala consolidata di Skype for Business Server Edge pool con bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="9d50a-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="9d50a-148">Con questo scenario puoi avere una disponibilità elevata nella distribuzione di Edge, che ti offre i vantaggi della scalabilità e del supporto per il failover.</span><span class="sxs-lookup"><span data-stu-id="9d50a-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Scenario Edge per il bordo consolidato in scala con HLB](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
