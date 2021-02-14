---
title: Scenari di server perimetrali in Skype for Business Server
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
description: 'Riepilogo: esaminare questi scenari per pianificare la topologia dei server perimetrali in Skype for Business Server.'
ms.openlocfilehash: cfcc1e8b34576fbec85464fb8d5e35903b47d8ef
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813792"
---
# <a name="edge-server-scenarios-in-skype-for-business-server"></a><span data-ttu-id="8580d-103">Scenari di server perimetrali in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8580d-103">Edge Server scenarios in Skype for Business Server</span></span>
 
<span data-ttu-id="8580d-104">**Riepilogo:** Esaminare questi scenari per pianificare la topologia dei server perimetrali in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8580d-104">**Summary:** Review these scenarios to help you plan your Edge Server topology in Skype for Business Server.</span></span>
  
<span data-ttu-id="8580d-105">Alcuni diagrammi di scenari sono utili per visualizzare e decidere quale topologia di Server perimetrale di Skype for Business Server si desidera implementare.</span><span class="sxs-lookup"><span data-stu-id="8580d-105">We have some scenarios diagrams to assist with visualizing and deciding on what Skype for Business Server Edge Server topology you want to implement.</span></span> <span data-ttu-id="8580d-106">Dopo aver scelto un buon candidato, puoi leggere i requisiti ambientali che dovrai soddisfare.</span><span class="sxs-lookup"><span data-stu-id="8580d-106">Once you've picked a good candidate, you can go read up on the environmental requirements you'll need to address.</span></span> <span data-ttu-id="8580d-107">Quanto segue è applicabile a uno qualsiasi degli scenari, quindi viene menzionato per primo.</span><span class="sxs-lookup"><span data-stu-id="8580d-107">The following is applicable to any of the scenarios, so we're mentioning it first.</span></span>
  
<span data-ttu-id="8580d-108">Queste figure, mostrate solo a scopo di esempio (e che contengono dati IPv4 e IPv6 di esempio), non rappresentano il flusso di comunicazione effettivo, ma piuttosto una visualizzazione di alto livello del traffico possibile.</span><span class="sxs-lookup"><span data-stu-id="8580d-108">These figures, which are shown for example purposes only (and as such contains sample IPv4 and IPv6 data), don't represent the actual communication flow, but rather a high-level view of your possible traffic.</span></span> <span data-ttu-id="8580d-109">I dettagli sulle porte sono disponibili anche nei diagrammi delle porte per ogni scenario seguente.</span><span class="sxs-lookup"><span data-stu-id="8580d-109">Port details can also be seen in the Port diagrams for each scenario below.</span></span>
  
<span data-ttu-id="8580d-110">I diagrammi mostrano .com per l'interfaccia esterna e .net per l'interno, che è anche materiale di esempio; Naturalmente, le voci potrebbero essere molto diverse quando si sta mettendo insieme il proprio piano Edge finale.</span><span class="sxs-lookup"><span data-stu-id="8580d-110">The diagrams show .com for the external interface and .net for the internal, which is also sample material; of course your own entries may be quite different when you're putting together your own final Edge plan.</span></span>
  
<span data-ttu-id="8580d-111">Non è incluso il Director (che è un componente facoltativo) in nessuno dei diagrammi, ma è possibile leggerlo separatamente (è menzionato in altri argomenti relativi alla pianificazione).</span><span class="sxs-lookup"><span data-stu-id="8580d-111">We don't include the Director (which is an optional component) in any of the diagrams, but you can read about that separately (it's mentioned in other Planning topics).</span></span>
  
<span data-ttu-id="8580d-112">Come indicato in precedenza, sono presenti dati IPv6 di esempio nei diagrammi.</span><span class="sxs-lookup"><span data-stu-id="8580d-112">As noted above, there is sample IPv6 data in the diagrams.</span></span> <span data-ttu-id="8580d-113">La maggior parte della documentazione in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) farà riferimento a IPv4, ma sei sicuramente supportato se vuoi usare IPv6.</span><span class="sxs-lookup"><span data-stu-id="8580d-113">Most of the documentation in [Plan for Edge Server deployments in Skype for Business Server](edge-server-deployments.md) will refer to IPv4, but you are certainly supported if you want to use IPv6.</span></span> <span data-ttu-id="8580d-114">Si noti che gli indirizzi IPv6 saranno necessari nello spazio di indirizzi assegnato e dovranno funzionare con l'indirizzamento interno ed esterno, come con gli INDIRIZZI IP IPv4.</span><span class="sxs-lookup"><span data-stu-id="8580d-114">Note that you'll need IPv6 addresses in your assigned address space, and they'll need to work with internal and external addressing, as with IPv4 IPs.</span></span> <span data-ttu-id="8580d-115">È possibile, grazie a Windows, utilizzare la funzionalità dual stack, che è uno stack di rete separato e distinto per IPv4 e IPv6.</span><span class="sxs-lookup"><span data-stu-id="8580d-115">You can, thanks to Windows, employ the dual stack feature, which is a separate and distinct network stack for IPv4 and IPv6.</span></span> <span data-ttu-id="8580d-116">In questo modo, se necessario, sarà possibile assegnare gli indirizzi IPv4 e IPv6 contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="8580d-116">This will, if you need, allow you to assign IPv4 and IPv6 addresses concurrently.</span></span>
  
<span data-ttu-id="8580d-117">Esistono dispositivi NAT che consentono NAT64 (da IPv6 a IPv4) e NAT66 (da IPv6 a IPv6) e questo è valido per l'uso con Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8580d-117">There are NAT devices that allow for NAT64 (IPv6 to IPv4) and NAT66 (IPv6 to IPv6)), and this is valid for use with Skype for Business Server.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="8580d-118">Se si utilizza il servizio Controllo di ammissione di chiamata, è necessario utilizzare IPv4 sull'interfaccia interna per il funzionamento.</span><span class="sxs-lookup"><span data-stu-id="8580d-118">If you're using Call Admission Control (CAC) you do have to use IPv4 on the internal interface for it to work.</span></span> 
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-private-ip-addresses-and-nat"></a><span data-ttu-id="8580d-119">Singolo server perimetrale di Skype for Business Server consolidato con indirizzi IP privati e NAT</span><span class="sxs-lookup"><span data-stu-id="8580d-119">Single consolidated Skype for Business Server Edge Server with private IP addresses and NAT</span></span>

<span data-ttu-id="8580d-120">Con questo scenario, non è disponibile alcuna opzione per la disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="8580d-120">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="8580d-121">Questo significa che spendi meno sull'hardware e hai una distribuzione più semplice.</span><span class="sxs-lookup"><span data-stu-id="8580d-121">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="8580d-122">Se la disponibilità elevata è un'opzione importante, vedere gli scenari consolidati con scalabilità orizzontale riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="8580d-122">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Scenario perimetrale per singola topologia perimetrale consolidata con IP privato tramite NAT](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="8580d-124">Diagramma delle porte</span><span class="sxs-lookup"><span data-stu-id="8580d-124">Port diagram</span></span>

<span data-ttu-id="8580d-125">È inoltre disponibile un diagramma per le porte per i singoli server perimetrali consolidati.</span><span class="sxs-lookup"><span data-stu-id="8580d-125">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Perimetro di rete per server perimetrali Singolo server perimetrale consolidato](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="single-consolidated-skype-for-business-server-edge-server-with-public-ip-addresses"></a><span data-ttu-id="8580d-127">Singolo server perimetrale di Skype for Business Server consolidato con indirizzi IP pubblici</span><span class="sxs-lookup"><span data-stu-id="8580d-127">Single consolidated Skype for Business Server Edge Server with public IP addresses</span></span>

<span data-ttu-id="8580d-128">Con questo scenario, non è disponibile alcuna opzione per la disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="8580d-128">With this scenario, there is no option for high availability.</span></span> <span data-ttu-id="8580d-129">Questo significa che spendi meno sull'hardware e hai una distribuzione più semplice.</span><span class="sxs-lookup"><span data-stu-id="8580d-129">This will mean you spend less on hardware and have a simpler deployment.</span></span> <span data-ttu-id="8580d-130">Se la disponibilità elevata è un'opzione importante, vedere gli scenari consolidati con scalabilità orizzontale riportati di seguito.</span><span class="sxs-lookup"><span data-stu-id="8580d-130">If high availability is a must, check out the Scaled consolidated scenarios below.</span></span>
  
![Scenario perimetrale per singola topologia perimetrale consolidata con IP pubblico](../../media/Plan_LyncServer_Edge_Scenario_SingleConsolidatedEdgePublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="8580d-132">Diagramma delle porte</span><span class="sxs-lookup"><span data-stu-id="8580d-132">Port diagram</span></span>

<span data-ttu-id="8580d-133">È inoltre disponibile un diagramma per le porte per i singoli server perimetrali consolidati.</span><span class="sxs-lookup"><span data-stu-id="8580d-133">We also have a diagram for ports for single consolidated Edge Servers.</span></span>
  
![Perimetro di rete per server perimetrali Singolo server perimetrale consolidato](../../media/Plan_LyncServer_Edge_NetPerimeter_SingleConsolidatedEdge.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-private-ip-addresses-and-nat"></a><span data-ttu-id="8580d-135">Pool di server perimetrali Skype for Business Server consolidato con scalabilità verticale, con bilanciamento del carico DNS, indirizzi IP privati e NAT</span><span class="sxs-lookup"><span data-stu-id="8580d-135">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing, and private IP addresses and NAT</span></span>

<span data-ttu-id="8580d-136">Con questo scenario, è possibile avere disponibilità elevata nella distribuzione edge, che offre i vantaggi del supporto di scalabilità e failover.</span><span class="sxs-lookup"><span data-stu-id="8580d-136">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Scenario perimetrale per topologia perimetrale consolidata con scalabilità consolidata, DNS LB con IP privato tramite NAT](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPrivateIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="8580d-138">Diagramma delle porte</span><span class="sxs-lookup"><span data-stu-id="8580d-138">Port diagram</span></span>

<span data-ttu-id="8580d-139">È inoltre disponibile un diagramma per pool di server perimetrali consolidati con scalabilità consolidata con bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="8580d-139">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Perimetro di rete per server perimetrale consolidato con scalabilità orizzontale utilizzando DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-dns-load-balancing-and-public-ip-addresses"></a><span data-ttu-id="8580d-141">Pool di server perimetrali Skype for Business Server consolidato con scalabilità consolidata, con bilanciamento del carico DNS e indirizzi IP pubblici</span><span class="sxs-lookup"><span data-stu-id="8580d-141">Scaled consolidated Skype for Business Server Edge pool, with DNS load balancing and public IP addresses</span></span>

<span data-ttu-id="8580d-142">Con questo scenario, è possibile avere disponibilità elevata nella distribuzione edge, che offre i vantaggi del supporto di scalabilità e failover.</span><span class="sxs-lookup"><span data-stu-id="8580d-142">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Scenario perimetrale per topologia perimetrale consolidata con scalabilità orizzontale, DNS LB con IP pubblico](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeDNSLBPublicIP.jpg)
  
### <a name="port-diagram"></a><span data-ttu-id="8580d-144">Diagramma delle porte</span><span class="sxs-lookup"><span data-stu-id="8580d-144">Port diagram</span></span>

<span data-ttu-id="8580d-145">È inoltre disponibile un diagramma per pool di server perimetrali consolidati con scalabilità consolidata con bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="8580d-145">We also have a diagram for scaled consolidated Edge pools with DNS load balancing.</span></span>
  
![Perimetro di rete per server perimetrale consolidato con scalabilità orizzontale utilizzando DNS LB](../../media/Plan_LyncServer_Edge_NetPerimeter_ScaledConsolidatedEdgeDNSLB.jpg)
  
## <a name="scaled-consolidated-skype-for-business-server-edge-pool-with-hardware-load-balancing"></a><span data-ttu-id="8580d-147">Pool di server perimetrali Skype for Business Server consolidato con scalabilità consolidata, con bilanciamento del carico hardware</span><span class="sxs-lookup"><span data-stu-id="8580d-147">Scaled consolidated Skype for Business Server Edge pool, with hardware load balancing</span></span>

<span data-ttu-id="8580d-148">Con questo scenario, è possibile avere disponibilità elevata nella distribuzione edge, che offre i vantaggi del supporto di scalabilità e failover.</span><span class="sxs-lookup"><span data-stu-id="8580d-148">With this scenario, you are able to have high availability in your Edge deployment, which gives you the advantages of scalability and failover support.</span></span>
  
![Scenario perimetrale per server perimetrale consolidato con scalabilità orizzontale con bilanciamento del carico di rete](../../media/Plan_LyncServer_Edge_Scenario_ScaledConsolidatedEdgeHLB.jpg)
 
