---
title: 'Lync Server 2013: scelta di una topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Choosing a topology
ms:assetid: 23f2aeb6-fed9-4349-8fba-dcbf18ee4b04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425716(v=OCS.15)
ms:contentKeyID: 48183634
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f128c827845ac06a736b849e6fa3242e319decb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529383"
---
# <a name="choosing-a-topology-in-lync-server-2013"></a><span data-ttu-id="23e41-102">Scelta di una topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23e41-102">Choosing a topology in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="23e41-103">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="23e41-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="23e41-104">Quando si sceglie una topologia, è possibile utilizzare una delle opzioni di topologie supportate seguenti:</span><span class="sxs-lookup"><span data-stu-id="23e41-104">When you choose a topology, you can use one the following supported topology options:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="23e41-105">Se non diversamente specificato, se si ha esperienza con Microsoft Lync Server 2010, le linee guida qui sono in gran parte invariate.</span><span class="sxs-lookup"><span data-stu-id="23e41-105">Unless otherwise noted, if you have experience with Microsoft Lync Server 2010, you will find the guidance here is largely unchanged.</span></span>



</div>

  - [<span data-ttu-id="23e41-106">Singolo server perimetrale consolidato con indirizzi IP privati e NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23e41-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="23e41-107">Perimetro consolidato singolo con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23e41-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="23e41-108">Perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23e41-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="23e41-109">Perimetro consolidato in scala, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23e41-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="23e41-110">Perimetro consolidato in scala con i dispositivi di bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="23e41-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> <span data-ttu-id="23e41-p101">Per l'interfaccia perimetrale interna e per quella esterna è necessario utilizzare lo stesso tipo di bilanciamento del carico. Non è possibile utilizzare il bilanciamento del carico DNS in un'interfaccia perimetrale e il bilanciamento del carico hardware nell'altra.</span><span class="sxs-lookup"><span data-stu-id="23e41-p101">The internal Edge interface and external Edge interface must use the same type of load balancing. You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="23e41-113">Nella tabella seguente sono riepilogate le funzionalità disponibili con le topologie di Microsoft Lync Server 2013 supportate.</span><span class="sxs-lookup"><span data-stu-id="23e41-113">The following table summarizes the functionality available with the supported Microsoft Lync Server 2013 topologies.</span></span> <span data-ttu-id="23e41-114">Le intestazioni di colonna indicano la funzionalità disponibile per una determinata opzione di configurazione di server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="23e41-114">The column headings indicate the functionality available for a given Edge configuration option.</span></span> <span data-ttu-id="23e41-115">Utilizzando come esempio l'opzione di server perimetrale con scalabilità implementata e con bilanciamento del carico DNS, è possibile osservare che supporta la disponibilità elevata, può utilizzare indirizzi IP privati non instradabili (con NAT) o indirizzi IP pubblici instradabili assegnati alle interfacce esterne perimetrali e comporta una riduzione dei costi perché non è necessario un dispositivo di bilanciamento del carico hardware.</span><span class="sxs-lookup"><span data-stu-id="23e41-115">Using the Scaled Edge (DNS load balanced) option as an example, you can see that it supports high availability, can use non-routable private IP addresses (with NAT) or routable public IP addresses assigned to the Edge external interfaces, and reduces cost because a hardware load balancer is not required.</span></span>

<span data-ttu-id="23e41-116">Gli scenari di failover dei server perimetrali supportati con il bilanciamento del carico DNS sono sessioni punto-punto di Lync a Lync, sessioni di Lync Conferencing, sessioni Lync-to-PSTN, Office 365 e Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="23e41-116">Edge failover scenarios supported with DNS Load Balancing are Lync-to-Lync point-to-point sessions, Lync conferencing sessions, Lync-to-PSTN sessions, Office 365, and Microsoft 365.</span></span> <span data-ttu-id="23e41-117">Gli scenari di failover del server perimetrale che non beneficiano del bilanciamento del carico DNS sono il failover per la messaggistica unificata di Exchange (prima di Exchange 2010 SP1), la connettività di messaggistica istantanea pubblica e la Federazione con i server che eseguono Office Communications.</span><span class="sxs-lookup"><span data-stu-id="23e41-117">Edge failover scenarios that do not benefit from DNS Load Balancing are failover for remote user Exchange Unified Messaging (UM) (prior to Exchange 2010 SP1), public instant messaging (IM) connectivity, and federation with servers running Office Communications Server.</span></span>

### <a name="summary-of-edge-server-topology-options"></a><span data-ttu-id="23e41-118">Riepilogo delle opzioni di topologia di server perimetrali</span><span class="sxs-lookup"><span data-stu-id="23e41-118">Summary of Edge Server Topology Options</span></span>

<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23e41-119">Topologia</span><span class="sxs-lookup"><span data-stu-id="23e41-119">Topology</span></span></th>
<th><span data-ttu-id="23e41-120">Disponibilità elevata</span><span class="sxs-lookup"><span data-stu-id="23e41-120">High availability</span></span></th>
<th><span data-ttu-id="23e41-121">Record A DNS aggiuntivi necessario per il server perimetrale esterno del pool di server perimetrali</span><span class="sxs-lookup"><span data-stu-id="23e41-121">Additional DNS A records required for external Edge Server in the Edge pool</span></span></th>
<th><span data-ttu-id="23e41-122">Failover del server perimetrale per le sessioni Lync-to-Lync</span><span class="sxs-lookup"><span data-stu-id="23e41-122">Edge Failover for Lync-to-Lync sessions</span></span></th>
<th><span data-ttu-id="23e41-123">Failover perimetrale per sessioni di Federazione di Lync-to-Lync EUM/PIC/OCS</span><span class="sxs-lookup"><span data-stu-id="23e41-123">Edge Failover for Lync-to-Lync EUM/PIC/OCS Federation sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23e41-124">Singolo perimetro con NAT</span><span class="sxs-lookup"><span data-stu-id="23e41-124">Single Edge using NAT</span></span></p></td>
<td><p><span data-ttu-id="23e41-125">No</span><span class="sxs-lookup"><span data-stu-id="23e41-125">No</span></span></p></td>
<td><p><span data-ttu-id="23e41-126">No</span><span class="sxs-lookup"><span data-stu-id="23e41-126">No</span></span></p></td>
<td><p><span data-ttu-id="23e41-127">No</span><span class="sxs-lookup"><span data-stu-id="23e41-127">No</span></span></p></td>
<td><p><span data-ttu-id="23e41-128">No</span><span class="sxs-lookup"><span data-stu-id="23e41-128">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23e41-129">Singolo perimetro con indirizzi IP pubblici</span><span class="sxs-lookup"><span data-stu-id="23e41-129">Single Edge using Public IP</span></span></p></td>
<td><p><span data-ttu-id="23e41-130">No</span><span class="sxs-lookup"><span data-stu-id="23e41-130">No</span></span></p></td>
<td><p><span data-ttu-id="23e41-131">No</span><span class="sxs-lookup"><span data-stu-id="23e41-131">No</span></span></p></td>
<td><p><span data-ttu-id="23e41-132">No</span><span class="sxs-lookup"><span data-stu-id="23e41-132">No</span></span></p></td>
<td><p><span data-ttu-id="23e41-133">No</span><span class="sxs-lookup"><span data-stu-id="23e41-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23e41-134">Perimetro in scala (bilanciamento del carico DNS) con NAT</span><span class="sxs-lookup"><span data-stu-id="23e41-134">Scaled Edge (DNS Load Balanced) using NAT</span></span></p></td>
<td><p><span data-ttu-id="23e41-135">Sì</span><span class="sxs-lookup"><span data-stu-id="23e41-135">Yes</span></span></p></td>
<td><p><span data-ttu-id="23e41-136">Sì</span><span class="sxs-lookup"><span data-stu-id="23e41-136">Yes</span></span></p></td>
<td><p><span data-ttu-id="23e41-137">Sì</span><span class="sxs-lookup"><span data-stu-id="23e41-137">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23e41-138">Perimetro in scala (bilanciamento del carico DNS) con IP pubblico</span><span class="sxs-lookup"><span data-stu-id="23e41-138">Scaled Edge (DNS Load Balanced) using Public IP</span></span></p></td>
<td><p><span data-ttu-id="23e41-139">Sì</span><span class="sxs-lookup"><span data-stu-id="23e41-139">Yes</span></span></p></td>
<td><p><span data-ttu-id="23e41-140">Sì</span><span class="sxs-lookup"><span data-stu-id="23e41-140">Yes</span></span></p></td>
<td><p><span data-ttu-id="23e41-141">Sì</span><span class="sxs-lookup"><span data-stu-id="23e41-141">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23e41-142">Hardware perimetrale in scala (con bilanciamento del carico)</span><span class="sxs-lookup"><span data-stu-id="23e41-142">Scaled Edge Hardware load balanced)</span></span></p></td>
<td><p><span data-ttu-id="23e41-143">Sì</span><span class="sxs-lookup"><span data-stu-id="23e41-143">Yes</span></span></p></td>
<td><p><span data-ttu-id="23e41-144">No (un record A DNS per IP virtuale)</span><span class="sxs-lookup"><span data-stu-id="23e41-144">No (one DNS A record per VIP)</span></span></p></td>
<td><p><span data-ttu-id="23e41-145">Sì</span><span class="sxs-lookup"><span data-stu-id="23e41-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="23e41-146">Sì</span><span class="sxs-lookup"><span data-stu-id="23e41-146">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="23e41-147">**\*** Il failover per la connettività di messaggistica istantanea pubblica e la Federazione con i server che eseguono Office Communications Server non sono disponibili con il bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="23e41-147">**\*** Failover for public instant messaging (IM) connectivity, and federation with servers running Office Communications Server is not available with DNS load balancing.</span></span> <span data-ttu-id="23e41-148">Il failover della messaggistica unificata di Exchange (utente remoto) utilizzando il bilanciamento del carico DNS richiede Exchange Server 2010 SP1 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="23e41-148">Exchange UM (remote user) failover using DNS load balancing requires Exchange Server 2010 SP1 or newer.</span></span>



> [!NOTE]
> <span data-ttu-id="23e41-149">Le topologie perimetrale singola e perimetrale in scala (con bilanciamento del carico DNS) possono utilizzare:</span><span class="sxs-lookup"><span data-stu-id="23e41-149">Single Edge and Scaled Edge (DNS load balanced) topologies can use:</span></span>
> <ul><li><p><span data-ttu-id="23e41-150">Indirizzi IP pubblici instradabili</span><span class="sxs-lookup"><span data-stu-id="23e41-150">Routable public IP addresses</span></span></p></li>
> <li><p><span data-ttu-id="23e41-151">Indirizzo IP privato non instradabile se viene utilizzato NAT (Symmetric Network Address Translation)</span><span class="sxs-lookup"><span data-stu-id="23e41-151">Non-routable private IP address if symmetric network address translation (NAT) is used</span></span></p></li>
>
> <ul><li> <span data-ttu-id="23e41-152">Se si utilizza l'indirizzo IP pubblico o l'indirizzo IP privato con NAT, verrà comunque utilizzato lo stesso numero di indirizzi IP in base alla scelta di configurazione in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="23e41-152">If you use public IP address or private IP address with NAT, you will still use the same number of IP addresses based on your configuration choice in Topology Builder.</span></span> <span data-ttu-id="23e41-153">È possibile configurare il server perimetrale per l'utilizzo di un singolo indirizzo IP con porte distinte per servizio oppure utilizzare indirizzi IP distinti per servizio, ma utilizzare la stessa porta (per impostazione predefinita, TCP 443).</span><span class="sxs-lookup"><span data-stu-id="23e41-153">You can configure the Edge Server to use a single IP address with distinct ports per service, or use distinct IP addresses per service, but use the same port (by default, TCP 443).</span></span></li></ul>>
> <span data-ttu-id="23e41-154">Se si decide di utilizzare indirizzi IP privati non instradabili con NAT:</span><span class="sxs-lookup"><span data-stu-id="23e41-154">If you decide to use non-routable private IP addresses with NAT:</span></span>
> <ul><li><p><span data-ttu-id="23e41-155">È necessario utilizzare indirizzi IP privati instradabili su tutte e tre le interfacce esterne</span><span class="sxs-lookup"><span data-stu-id="23e41-155">You must use routable private IP addresses on all three external interfaces</span></span></p></li>
> <li><p><span data-ttu-id="23e41-156">È necessario configurare NAT simmetrico per il traffico in arrivo e in uscita</span><span class="sxs-lookup"><span data-stu-id="23e41-156">You must configure symmetric NAT for incoming and outgoing traffic</span></span></p></li></ul>>
> <span data-ttu-id="23e41-157">La topologia perimetrale in scala (con bilanciamento del carico hardware) deve utilizzare indirizzi IP pubblici.</span><span class="sxs-lookup"><span data-stu-id="23e41-157">Scaled Edge (hardware load balanced) topology must use public IP addresses.</span></span>



<span data-ttu-id="23e41-158">Lync Server 2013 supporta il posizionamento di interfacce esterne di accesso, Web Conferencing e A/V Edge dietro un router o un firewall che esegue la conversione NAT (Network Address Translation) per topologie di server perimetrali consolidate singole e in scala.</span><span class="sxs-lookup"><span data-stu-id="23e41-158">Lync Server 2013 supports placing Access, Web Conferencing, and A/V Edge external interfaces behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span>

<span data-ttu-id="23e41-p106">L'utilizzo di NAT per tutte le interfacce esterne perimetrali richiede l'utilizzo del bilanciamento del carico DNS. In confronto all'utilizzo di un dispositivo di bilanciamento del carico hardware, il bilanciamento del carico DNS senza NAT consente di ridurre il numero di indirizzi IP pubblici per server perimetrale in un pool di server perimetrali, come descritto nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="23e41-p106">Using NAT for all Edge external interfaces requires the use of DNS load balancing. When compared to using hardware load balancers, using DNS load balancing without NAT allows you to reduce the number of public IP address per Edge Server in an Edge pool as described in the following list:</span></span>

  - <span data-ttu-id="23e41-161">Lync Server 2013 il perimetro consolidato in scala (bilanciamento del carico DNS) richiede tre indirizzi IP pubblici per ogni server perimetrale in un pool perimetrale.</span><span class="sxs-lookup"><span data-stu-id="23e41-161">Lync Server 2013 Scaled Consolidated Edge (DNS load balanced) Requires three public IP addresses for each Edge Server in an Edge pool.</span></span>

  - <span data-ttu-id="23e41-162">Lync Server 2013 il perimetro consolidato in scala (bilanciamento del carico hardware) richiede tre indirizzi IP pubblici per l'indirizzo IP virtuale del dispositivo di bilanciamento del carico (un requisito di tempo che non incrementa il numero di server perimetrali aggiunti al pool) più tre indirizzi IP pubblici per ogni server perimetrale in un pool.</span><span class="sxs-lookup"><span data-stu-id="23e41-162">Lync Server 2013 Scaled Consolidated Edge (hardware load balanced) Requires three public IP address for load balancer virtual IP addresses (one time requirement that does not increment as more Edge Servers are added to the pool) plus three public IP addresses per Edge Server in a pool.</span></span>

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a><span data-ttu-id="23e41-163">Requisiti di indirizzi IP per topologie di server perimetrali consolidati con scalabilità implementata (indirizzo IP per ruolo)</span><span class="sxs-lookup"><span data-stu-id="23e41-163">IP Address Requirements for Scaled Consolidated Edge (IP Address per role)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23e41-164">Numero di server perimetrali per pool</span><span class="sxs-lookup"><span data-stu-id="23e41-164">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="23e41-165">Numero di indirizzi IP necessari Lync Server 2013 (bilanciamento del carico DNS)</span><span class="sxs-lookup"><span data-stu-id="23e41-165">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="23e41-166">Numero di indirizzi IP necessari Lync Server 2013 (bilanciamento del carico hardware)</span><span class="sxs-lookup"><span data-stu-id="23e41-166">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23e41-167">2</span><span class="sxs-lookup"><span data-stu-id="23e41-167">2</span></span></p></td>
<td><p><span data-ttu-id="23e41-168">6 </span><span class="sxs-lookup"><span data-stu-id="23e41-168">6</span></span></p></td>
<td><p><span data-ttu-id="23e41-169">3 (1 per VIP) + 6</span><span class="sxs-lookup"><span data-stu-id="23e41-169">3 (1 per VIP) + 6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23e41-170">3</span><span class="sxs-lookup"><span data-stu-id="23e41-170">3</span></span></p></td>
<td><p><span data-ttu-id="23e41-171">9 </span><span class="sxs-lookup"><span data-stu-id="23e41-171">9</span></span></p></td>
<td><p><span data-ttu-id="23e41-172">3 (1 per VIP) + 9</span><span class="sxs-lookup"><span data-stu-id="23e41-172">3 (1 per VIP) + 9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23e41-173">4 </span><span class="sxs-lookup"><span data-stu-id="23e41-173">4</span></span></p></td>
<td><p><span data-ttu-id="23e41-174">12 </span><span class="sxs-lookup"><span data-stu-id="23e41-174">12</span></span></p></td>
<td><p><span data-ttu-id="23e41-175">3 (1 per VIP) + 12</span><span class="sxs-lookup"><span data-stu-id="23e41-175">3 (1 per VIP) + 12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23e41-176">5 </span><span class="sxs-lookup"><span data-stu-id="23e41-176">5</span></span></p></td>
<td><p><span data-ttu-id="23e41-177">15 </span><span class="sxs-lookup"><span data-stu-id="23e41-177">15</span></span></p></td>
<td><p><span data-ttu-id="23e41-178">3 (1 per IP virtuale) + 15</span><span class="sxs-lookup"><span data-stu-id="23e41-178">3 (1 per VIP) + 15</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a><span data-ttu-id="23e41-179">Requisiti di indirizzi IP per topologie di server perimetrali consolidati con scalabilità implementata (singolo indirizzo IP per tutti i ruoli)</span><span class="sxs-lookup"><span data-stu-id="23e41-179">IP Address Requirements for Scaled Consolidated Edge (Single IP address for all roles)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="23e41-180">Numero di server perimetrali per pool</span><span class="sxs-lookup"><span data-stu-id="23e41-180">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="23e41-181">Numero di indirizzi IP necessari Lync Server 2013 (bilanciamento del carico DNS)</span><span class="sxs-lookup"><span data-stu-id="23e41-181">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="23e41-182">Numero di indirizzi IP necessari Lync Server 2013 (bilanciamento del carico hardware)</span><span class="sxs-lookup"><span data-stu-id="23e41-182">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="23e41-183">2</span><span class="sxs-lookup"><span data-stu-id="23e41-183">2</span></span></p></td>
<td><p><span data-ttu-id="23e41-184">2</span><span class="sxs-lookup"><span data-stu-id="23e41-184">2</span></span></p></td>
<td><p><span data-ttu-id="23e41-185">1 (1 per IP virtuale) + 2</span><span class="sxs-lookup"><span data-stu-id="23e41-185">1 (1 per VIP) + 2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23e41-186">3</span><span class="sxs-lookup"><span data-stu-id="23e41-186">3</span></span></p></td>
<td><p><span data-ttu-id="23e41-187">3</span><span class="sxs-lookup"><span data-stu-id="23e41-187">3</span></span></p></td>
<td><p><span data-ttu-id="23e41-188">3 (1 per IP virtuale) + 6</span><span class="sxs-lookup"><span data-stu-id="23e41-188">1 (1 per VIP) + 3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="23e41-189">4 </span><span class="sxs-lookup"><span data-stu-id="23e41-189">4</span></span></p></td>
<td><p><span data-ttu-id="23e41-190">4 </span><span class="sxs-lookup"><span data-stu-id="23e41-190">4</span></span></p></td>
<td><p><span data-ttu-id="23e41-191">4 (1 per IP virtuale) + 6</span><span class="sxs-lookup"><span data-stu-id="23e41-191">1 (1 per VIP) + 4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="23e41-192">5 </span><span class="sxs-lookup"><span data-stu-id="23e41-192">5</span></span></p></td>
<td><p><span data-ttu-id="23e41-193">5 </span><span class="sxs-lookup"><span data-stu-id="23e41-193">5</span></span></p></td>
<td><p><span data-ttu-id="23e41-194">5 (1 per IP virtuale) + 6</span><span class="sxs-lookup"><span data-stu-id="23e41-194">1 (1 per VIP) + 5</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="23e41-p107">Gli aspetti principali di cui tenere conto per la scelta della topologia sono la disponibilità elevata e il bilanciamento del carico. Il requisito di disponibilità elevata può influire sulla scelta del bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="23e41-p107">The primary decision points for topology selection are high availability and load balancing. The requirement for high availability can influence the load balancing decision.</span></span>

  - <span data-ttu-id="23e41-197">**Disponibilità elevata**   Se è necessaria una disponibilità elevata, distribuire almeno due server perimetrali in un pool.</span><span class="sxs-lookup"><span data-stu-id="23e41-197">**High availability**   If you need high availability, deploy at least two Edge Servers in a pool.</span></span> <span data-ttu-id="23e41-198">Un singolo pool di server perimetrali supporterà fino a un massimo di dodici perimetri.</span><span class="sxs-lookup"><span data-stu-id="23e41-198">A single Edge pool will support up to twelve Edge Servers.</span></span> <span data-ttu-id="23e41-199">Se è necessaria ulteriore capacità, è possibile distribuire più pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="23e41-199">If more capacity is required, you can deploy multiple Edge pools.</span></span> <span data-ttu-id="23e41-200">Come regola generale, il 10% del numero totale di utenti necessiterà dell'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="23e41-200">As a general rule, 10% of a given user base will need external access.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="23e41-201">Generatore di topologie consentirà di configurare fino a venti server perimetrali in un singolo pool di Edge.</span><span class="sxs-lookup"><span data-stu-id="23e41-201">Topology Builder will allow you to configure up to twenty Edge Servers in a single Edge pool.</span></span> <span data-ttu-id="23e41-202">Il numero massimo testato e supportato di server perimetrali in un pool è dodici e il generatore di topologie che consente un numero maggiore di dodici non dovrebbe essere interpretato come supporto implicito per più di dodici server perimetrali in un singolo pool di Edge.</span><span class="sxs-lookup"><span data-stu-id="23e41-202">The tested and supported maximum number of Edge Servers in a pool is twelve and Topology Builder allowing for a number larger than twelve should not be construed as implied support for more than twelve Edge Servers in a single Edge pool.</span></span>

    
    </div>

  - <span data-ttu-id="23e41-203">**Bilanciamento del carico hardware**   Il bilanciamento del carico hardware è supportato per il bilanciamento del carico dei server perimetrali di Lync Server 2013 quando si utilizzano indirizzi IP instradabili pubblicamente per le interfacce esterne perimetrali.</span><span class="sxs-lookup"><span data-stu-id="23e41-203">**Hardware load balancing**   Hardware load balancing is supported for load balancing Lync Server 2013 Edge Servers when using publicly routable IP addresses for the Edge external interfaces.</span></span> <span data-ttu-id="23e41-204">Utilizzare ad esempio questo approccio in situazioni in cui è necessario il failover per le applicazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="23e41-204">For example, you would use this approach in situations where failover is required for any of the following applications:</span></span>
    
      - <span data-ttu-id="23e41-205">Connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="23e41-205">Public IM connectivity</span></span>
    
      - <span data-ttu-id="23e41-206">Federazione con società che eseguono Microsoft Office Communications Server 2007 o Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="23e41-206">Federation with companies running Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2</span></span>
    
      - <span data-ttu-id="23e41-207">Accesso esterno a Messaggistica unificata di Exchange 2007 o di Exchange 2010</span><span class="sxs-lookup"><span data-stu-id="23e41-207">External access to Exchange 2007 Unified Messaging (UM) or Exchange 2010 UM</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="23e41-208">Il bilanciamento del carico DNS per Exchange 2010 SP1 e versioni successive è supportato per la messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="23e41-208">DNS load balancing for Exchange 2010 SP1 and newer is supported for Exchange UM.</span></span>

        
        </div>
    
    <span data-ttu-id="23e41-p111">Queste tre applicazioni continueranno a funzionare, ma non supportano il bilanciamento del carico DNS e si connetteranno solo al primo server perimetrale del pool. Se il server non è disponibile, la connessione avrà esito negativo. Se ad esempio vengono distribuiti più server perimetrali in un pool per gestire il carico del traffico federato, solo un proxy di accesso riceverà effettivamente il traffico, mentre gli altri resteranno inattivi.</span><span class="sxs-lookup"><span data-stu-id="23e41-p111">These three applications will continue to operate, but they are not DNS load balancing aware and will only connect to the first Edge Server in the pool. If that server is unavailable, the connection will fail. For example, if multiple Edge Servers are deployed in a pool to handle the federated traffic load, only one access proxy actually receives traffic while the others are idle.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="23e41-212">L'utilizzo del bilanciamento del carico DNS è consigliato se si sta eseguendo la Federazione con aziende che utilizzano Lync Server 2010 e Office 365 o Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="23e41-212">Using DNS load balancing is recommended if you are federating with companies using Lync Server 2010 and Office 365 or Microsoft 365.</span></span> <span data-ttu-id="23e41-213">Tenere presente che sono presenti effetti significativi sulle prestazioni se la maggior parte dei partner federati utilizza Office Communications Server 2007 o Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="23e41-213">Be aware that there are significant performance impacts if most of your federated partners are using Office Communications Server 2007 or Office Communications Server 2007 R2.</span></span>



<span data-ttu-id="23e41-214"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="23e41-214"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

