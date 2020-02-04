---
title: 'Lync Server 2013: Scelta di una topologia'
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
ms.openlocfilehash: 0b9f59648d845f37c7cf6d92c471b81a29415753
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729886"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="choosing-a-topology-in-lync-server-2013"></a><span data-ttu-id="999d0-102">Scelta di una topologia in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="999d0-102">Choosing a topology in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span data-ttu-id="999d0-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="999d0-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="999d0-104">Quando si sceglie una topologia, è possibile usare una delle opzioni seguenti per la topologia supportata:</span><span class="sxs-lookup"><span data-stu-id="999d0-104">When you choose a topology, you can use one the following supported topology options:</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="999d0-105">Se non diversamente specificato, se si ha esperienza con Microsoft Lync Server 2010, le linee guida sono in gran parte invariate.</span><span class="sxs-lookup"><span data-stu-id="999d0-105">Unless otherwise noted, if you have experience with Microsoft Lync Server 2010, you will find the guidance here is largely unchanged.</span></span>



</div>

  - [<span data-ttu-id="999d0-106">Singola topologia perimetrale consolidata con indirizzi IP privati e NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="999d0-106">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md)

  - [<span data-ttu-id="999d0-107">Singola topologia perimetrale consolidata con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="999d0-107">Single consolidated edge with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md)

  - [<span data-ttu-id="999d0-108">Topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP privati tramite NAT in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="999d0-108">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md)

  - [<span data-ttu-id="999d0-109">Topologia perimetrale consolidata con scalabilità implementata, bilanciamento del carico DNS con indirizzi IP pubblici in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="999d0-109">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md)

  - [<span data-ttu-id="999d0-110">Topologia perimetrale consolidata con scalabilità implementata e servizi di bilanciamento del carico hardware in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="999d0-110">Scaled consolidated edge with hardware load balancers in Lync Server 2013</span></span>](lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md)

<div>


> [!IMPORTANT]
> <span data-ttu-id="999d0-111">L'interfaccia perimetrale interna e l'interfaccia perimetrale esterna devono usare lo stesso tipo di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="999d0-111">The internal Edge interface and external Edge interface must use the same type of load balancing.</span></span> <span data-ttu-id="999d0-112">Non è possibile usare il bilanciamento del carico DNS in un'interfaccia perimetrale e il bilanciamento del carico hardware nell'altra.</span><span class="sxs-lookup"><span data-stu-id="999d0-112">You cannot use DNS load balancing on one Edge interface and hardware load balancing on the other Edge interface.</span></span>



</div>

<span data-ttu-id="999d0-113">Nella tabella seguente sono riepilogate le funzionalità disponibili con le topologie di Microsoft Lync Server 2013 supportate.</span><span class="sxs-lookup"><span data-stu-id="999d0-113">The following table summarizes the functionality available with the supported Microsoft Lync Server 2013 topologies.</span></span> <span data-ttu-id="999d0-114">Le intestazioni di colonna indicano la funzionalità disponibile per una determinata opzione di configurazione del bordo.</span><span class="sxs-lookup"><span data-stu-id="999d0-114">The column headings indicate the functionality available for a given Edge configuration option.</span></span> <span data-ttu-id="999d0-115">Usando l'opzione bordo scala (bilanciamento del carico DNS) come esempio, puoi vedere che supporta la disponibilità elevata, puoi usare indirizzi IP privati non instradabili (con NAT) o indirizzi IP pubblici instradabili assegnati alle interfacce esterne del bordo e ridurre i costi perché un il bilanciamento del carico hardware non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="999d0-115">Using the Scaled Edge (DNS load balanced) option as an example, you can see that it supports high availability, can use non-routable private IP addresses (with NAT) or routable public IP addresses assigned to the Edge external interfaces, and reduces cost because a hardware load balancer is not required.</span></span>

<span data-ttu-id="999d0-116">Gli scenari di failover dei bordi supportati con il bilanciamento del carico DNS sono sessioni Point-to-Point Lync-to-Lync, sessioni di conferenza di Lync, sessioni di Lync-to-PSTN e Office 365.</span><span class="sxs-lookup"><span data-stu-id="999d0-116">Edge failover scenarios supported with DNS Load Balancing are Lync-to-Lync point-to-point sessions, Lync conferencing sessions, Lync-to-PSTN sessions and Office 365.</span></span> <span data-ttu-id="999d0-117">Gli scenari di failover dei bordi che non traggono vantaggio dal bilanciamento del carico DNS sono il failover per la messaggistica unificata di Exchange utente remoto (prima di Exchange 2010 SP1), la connettività messaggistica istantanea pubblica e la Federazione con i server che eseguono le comunicazioni di Office Server.</span><span class="sxs-lookup"><span data-stu-id="999d0-117">Edge failover scenarios that do not benefit from DNS Load Balancing are failover for remote user Exchange Unified Messaging (UM) (prior to Exchange 2010 SP1), public instant messaging (IM) connectivity, and federation with servers running Office Communications Server.</span></span>

### <a name="summary-of-edge-server-topology-options"></a><span data-ttu-id="999d0-118">Riepilogo delle opzioni della topologia di Edge Server</span><span class="sxs-lookup"><span data-stu-id="999d0-118">Summary of Edge Server Topology Options</span></span>

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
<th><span data-ttu-id="999d0-119">Topologia</span><span class="sxs-lookup"><span data-stu-id="999d0-119">Topology</span></span></th>
<th><span data-ttu-id="999d0-120">Disponibilità elevata</span><span class="sxs-lookup"><span data-stu-id="999d0-120">High availability</span></span></th>
<th><span data-ttu-id="999d0-121">Record DNS aggiuntivi necessari per il server perimetrale esterno nel pool di bordi</span><span class="sxs-lookup"><span data-stu-id="999d0-121">Additional DNS A records required for external Edge Server in the Edge pool</span></span></th>
<th><span data-ttu-id="999d0-122">Failover Edge per le sessioni di Lync-to-Lync</span><span class="sxs-lookup"><span data-stu-id="999d0-122">Edge Failover for Lync-to-Lync sessions</span></span></th>
<th><span data-ttu-id="999d0-123">Failover Edge per sessioni di Federazione di Lync-to-Lync EUM/PIC/OCS</span><span class="sxs-lookup"><span data-stu-id="999d0-123">Edge Failover for Lync-to-Lync EUM/PIC/OCS Federation sessions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="999d0-124">Bordo singolo con NAT</span><span class="sxs-lookup"><span data-stu-id="999d0-124">Single Edge using NAT</span></span></p></td>
<td><p><span data-ttu-id="999d0-125">No</span><span class="sxs-lookup"><span data-stu-id="999d0-125">No</span></span></p></td>
<td><p><span data-ttu-id="999d0-126">No</span><span class="sxs-lookup"><span data-stu-id="999d0-126">No</span></span></p></td>
<td><p><span data-ttu-id="999d0-127">No</span><span class="sxs-lookup"><span data-stu-id="999d0-127">No</span></span></p></td>
<td><p><span data-ttu-id="999d0-128">No</span><span class="sxs-lookup"><span data-stu-id="999d0-128">No</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="999d0-129">Singolo bordo con IP pubblico</span><span class="sxs-lookup"><span data-stu-id="999d0-129">Single Edge using Public IP</span></span></p></td>
<td><p><span data-ttu-id="999d0-130">No</span><span class="sxs-lookup"><span data-stu-id="999d0-130">No</span></span></p></td>
<td><p><span data-ttu-id="999d0-131">No</span><span class="sxs-lookup"><span data-stu-id="999d0-131">No</span></span></p></td>
<td><p><span data-ttu-id="999d0-132">No</span><span class="sxs-lookup"><span data-stu-id="999d0-132">No</span></span></p></td>
<td><p><span data-ttu-id="999d0-133">No</span><span class="sxs-lookup"><span data-stu-id="999d0-133">No</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="999d0-134">Edge in scala (bilanciamento del carico DNS) tramite NAT</span><span class="sxs-lookup"><span data-stu-id="999d0-134">Scaled Edge (DNS Load Balanced) using NAT</span></span></p></td>
<td><p><span data-ttu-id="999d0-135">Sì</span><span class="sxs-lookup"><span data-stu-id="999d0-135">Yes</span></span></p></td>
<td><p><span data-ttu-id="999d0-136">Sì</span><span class="sxs-lookup"><span data-stu-id="999d0-136">Yes</span></span></p></td>
<td><p><span data-ttu-id="999d0-137">Sì</span><span class="sxs-lookup"><span data-stu-id="999d0-137">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="999d0-138">Edge in scala (bilanciamento del carico DNS) tramite IP pubblico</span><span class="sxs-lookup"><span data-stu-id="999d0-138">Scaled Edge (DNS Load Balanced) using Public IP</span></span></p></td>
<td><p><span data-ttu-id="999d0-139">Sì</span><span class="sxs-lookup"><span data-stu-id="999d0-139">Yes</span></span></p></td>
<td><p><span data-ttu-id="999d0-140">Sì</span><span class="sxs-lookup"><span data-stu-id="999d0-140">Yes</span></span></p></td>
<td><p><span data-ttu-id="999d0-141">Sì</span><span class="sxs-lookup"><span data-stu-id="999d0-141">Yes</span></span></p></td>
<td><p>*</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="999d0-142">Bilanciamento del carico hardware del bordo scalato)</span><span class="sxs-lookup"><span data-stu-id="999d0-142">Scaled Edge Hardware load balanced)</span></span></p></td>
<td><p><span data-ttu-id="999d0-143">Sì</span><span class="sxs-lookup"><span data-stu-id="999d0-143">Yes</span></span></p></td>
<td><p><span data-ttu-id="999d0-144">No (un record DNS per ogni VIP)</span><span class="sxs-lookup"><span data-stu-id="999d0-144">No (one DNS A record per VIP)</span></span></p></td>
<td><p><span data-ttu-id="999d0-145">Sì</span><span class="sxs-lookup"><span data-stu-id="999d0-145">Yes</span></span></p></td>
<td><p><span data-ttu-id="999d0-146">Sì</span><span class="sxs-lookup"><span data-stu-id="999d0-146">Yes</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="999d0-147">**\*** Il failover per la connettività di messaggistica istantanea pubblica e la Federazione con i server che gestiscono Office Communications Server non è disponibile con il bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="999d0-147">**\*** Failover for public instant messaging (IM) connectivity, and federation with servers running Office Communications Server is not available with DNS load balancing.</span></span> <span data-ttu-id="999d0-148">Il failover della messaggistica unificata di Exchange (utente remoto) con il bilanciamento del carico DNS richiede Exchange Server 2010 SP1 o versioni successive.</span><span class="sxs-lookup"><span data-stu-id="999d0-148">Exchange UM (remote user) failover using DNS load balancing requires Exchange Server 2010 SP1 or newer.</span></span>



> [!NOTE]
> <span data-ttu-id="999d0-149">Le topologie a bordo singolo e in scala (bilanciamento del carico DNS) possono essere usate:</span><span class="sxs-lookup"><span data-stu-id="999d0-149">Single Edge and Scaled Edge (DNS load balanced) topologies can use:</span></span>
> <ul><li><p><span data-ttu-id="999d0-150">Indirizzi IP pubblici instradabili</span><span class="sxs-lookup"><span data-stu-id="999d0-150">Routable public IP addresses</span></span></p></li>
> <li><p><span data-ttu-id="999d0-151">Indirizzo IP privato non instradabile se viene usato NAT (Symmetric Network Address Translation)</span><span class="sxs-lookup"><span data-stu-id="999d0-151">Non-routable private IP address if symmetric network address translation (NAT) is used</span></span></p></li>
>
> <ul><li> <span data-ttu-id="999d0-152">Se si usa l'indirizzo IP pubblico o l'indirizzo IP privato con NAT, si utilizzerà comunque lo stesso numero di indirizzi IP in base alla scelta di configurazione in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="999d0-152">If you use public IP address or private IP address with NAT, you will still use the same number of IP addresses based on your configuration choice in Topology Builder.</span></span> <span data-ttu-id="999d0-153">È possibile configurare l'Edge Server in modo da usare un singolo indirizzo IP con porte distinte per servizio oppure usare indirizzi IP distinti per servizio, ma usare la stessa porta (per impostazione predefinita, TCP 443).</span><span class="sxs-lookup"><span data-stu-id="999d0-153">You can configure the Edge Server to use a single IP address with distinct ports per service, or use distinct IP addresses per service, but use the same port (by default, TCP 443).</span></span></li></ul>>
> <span data-ttu-id="999d0-154">Se si decide di usare indirizzi IP privati non instradabili con NAT:</span><span class="sxs-lookup"><span data-stu-id="999d0-154">If you decide to use non-routable private IP addresses with NAT:</span></span>
> <ul><li><p><span data-ttu-id="999d0-155">È necessario usare indirizzi IP privati instradabili su tutte e tre le interfacce esterne</span><span class="sxs-lookup"><span data-stu-id="999d0-155">You must use routable private IP addresses on all three external interfaces</span></span></p></li>
> <li><p><span data-ttu-id="999d0-156">È necessario configurare il NAT simmetrico per il traffico in entrata e in uscita</span><span class="sxs-lookup"><span data-stu-id="999d0-156">You must configure symmetric NAT for incoming and outgoing traffic</span></span></p></li></ul>>
> <span data-ttu-id="999d0-157">La topologia di Edge in scala (bilanciamento del carico hardware) deve usare indirizzi IP pubblici.</span><span class="sxs-lookup"><span data-stu-id="999d0-157">Scaled Edge (hardware load balanced) topology must use public IP addresses.</span></span>



<span data-ttu-id="999d0-158">Lync Server 2013 supporta l'immissione di interfacce esterne di Access, Web Conferencing e A/V Edge dietro un router o un firewall che esegue NAT (Network Address Translation) sia per le topologie di server Edge consolidate singole che in scala.</span><span class="sxs-lookup"><span data-stu-id="999d0-158">Lync Server 2013 supports placing Access, Web Conferencing, and A/V Edge external interfaces behind a router or firewall that performs network address translation (NAT) for both single and scaled consolidated Edge Server topologies.</span></span>

<span data-ttu-id="999d0-159">L'uso di NAT per tutte le interfacce esterne Edge richiede l'utilizzo del bilanciamento del carico DNS.</span><span class="sxs-lookup"><span data-stu-id="999d0-159">Using NAT for all Edge external interfaces requires the use of DNS load balancing.</span></span> <span data-ttu-id="999d0-160">Se confrontato con l'uso di bilanciamento del carico hardware, l'uso del bilanciamento del carico DNS senza NAT consente di ridurre il numero di indirizzi IP pubblici per ogni server perimetrale in un pool di bordi, come descritto nell'elenco seguente:</span><span class="sxs-lookup"><span data-stu-id="999d0-160">When compared to using hardware load balancers, using DNS load balancing without NAT allows you to reduce the number of public IP address per Edge Server in an Edge pool as described in the following list:</span></span>

  - <span data-ttu-id="999d0-161">Lync Server 2013 Edge consolidato ridimensionato (bilanciamento del carico DNS) richiede tre indirizzi IP pubblici per ogni Edge Server in un pool di bordi.</span><span class="sxs-lookup"><span data-stu-id="999d0-161">Lync Server 2013 Scaled Consolidated Edge (DNS load balanced) Requires three public IP addresses for each Edge Server in an Edge pool.</span></span>

  - <span data-ttu-id="999d0-162">Lync Server 2013 Edge consolidato ridimensionato (bilanciamento del carico hardware) richiede tre indirizzi IP pubblici per l'indirizzo IP virtuale di bilanciamento del carico (un requisito di tempo che non viene incrementato man mano che vengono aggiunti altri Edge Server al pool) più tre indirizzi IP pubblici per Server perimetrale in un pool.</span><span class="sxs-lookup"><span data-stu-id="999d0-162">Lync Server 2013 Scaled Consolidated Edge (hardware load balanced) Requires three public IP address for load balancer virtual IP addresses (one time requirement that does not increment as more Edge Servers are added to the pool) plus three public IP addresses per Edge Server in a pool.</span></span>

### <a name="ip-address-requirements-for-scaled-consolidated-edge-ip-address-per-role"></a><span data-ttu-id="999d0-163">Requisiti per l'indirizzo IP per il bordo consolidato in scala (indirizzo IP per ruolo)</span><span class="sxs-lookup"><span data-stu-id="999d0-163">IP Address Requirements for Scaled Consolidated Edge (IP Address per role)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="999d0-164">Numero di server perimetrali per pool</span><span class="sxs-lookup"><span data-stu-id="999d0-164">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="999d0-165">Numero di indirizzi IP necessari Lync Server 2013 (bilanciamento del carico DNS)</span><span class="sxs-lookup"><span data-stu-id="999d0-165">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="999d0-166">Numero di indirizzi IP necessari Lync Server 2013 (bilanciamento del carico hardware)</span><span class="sxs-lookup"><span data-stu-id="999d0-166">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="999d0-167">2</span><span class="sxs-lookup"><span data-stu-id="999d0-167">2</span></span></p></td>
<td><p><span data-ttu-id="999d0-168">6</span><span class="sxs-lookup"><span data-stu-id="999d0-168">6</span></span></p></td>
<td><p><span data-ttu-id="999d0-169">3 (1 per VIP) + 6</span><span class="sxs-lookup"><span data-stu-id="999d0-169">3 (1 per VIP) + 6</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="999d0-170">3</span><span class="sxs-lookup"><span data-stu-id="999d0-170">3</span></span></p></td>
<td><p><span data-ttu-id="999d0-171">9</span><span class="sxs-lookup"><span data-stu-id="999d0-171">9</span></span></p></td>
<td><p><span data-ttu-id="999d0-172">3 (1 per VIP) + 9</span><span class="sxs-lookup"><span data-stu-id="999d0-172">3 (1 per VIP) + 9</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="999d0-173">4</span><span class="sxs-lookup"><span data-stu-id="999d0-173">4</span></span></p></td>
<td><p><span data-ttu-id="999d0-174">12</span><span class="sxs-lookup"><span data-stu-id="999d0-174">12</span></span></p></td>
<td><p><span data-ttu-id="999d0-175">3 (1 per VIP) + 12</span><span class="sxs-lookup"><span data-stu-id="999d0-175">3 (1 per VIP) + 12</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="999d0-176">5</span><span class="sxs-lookup"><span data-stu-id="999d0-176">5</span></span></p></td>
<td><p><span data-ttu-id="999d0-177">15</span><span class="sxs-lookup"><span data-stu-id="999d0-177">15</span></span></p></td>
<td><p><span data-ttu-id="999d0-178">3 (1 per VIP) + 15</span><span class="sxs-lookup"><span data-stu-id="999d0-178">3 (1 per VIP) + 15</span></span></p></td>
</tr>
</tbody>
</table>


### <a name="ip-address-requirements-for-scaled-consolidated-edge-single-ip-address-for-all-roles"></a><span data-ttu-id="999d0-179">Requisiti per l'indirizzo IP per il bordo consolidato in scala (singolo indirizzo IP per tutti i ruoli)</span><span class="sxs-lookup"><span data-stu-id="999d0-179">IP Address Requirements for Scaled Consolidated Edge (Single IP address for all roles)</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="999d0-180">Numero di server perimetrali per pool</span><span class="sxs-lookup"><span data-stu-id="999d0-180">Number of Edge Servers per pool</span></span></th>
<th><span data-ttu-id="999d0-181">Numero di indirizzi IP necessari Lync Server 2013 (bilanciamento del carico DNS)</span><span class="sxs-lookup"><span data-stu-id="999d0-181">Number of required IP addresses Lync Server 2013 (DNS load balanced)</span></span></th>
<th><span data-ttu-id="999d0-182">Numero di indirizzi IP necessari Lync Server 2013 (bilanciamento del carico hardware)</span><span class="sxs-lookup"><span data-stu-id="999d0-182">Number of required IP addresses Lync Server 2013 (hardware load balanced)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="999d0-183">2</span><span class="sxs-lookup"><span data-stu-id="999d0-183">2</span></span></p></td>
<td><p><span data-ttu-id="999d0-184">2</span><span class="sxs-lookup"><span data-stu-id="999d0-184">2</span></span></p></td>
<td><p><span data-ttu-id="999d0-185">1 (1 per VIP) + 2</span><span class="sxs-lookup"><span data-stu-id="999d0-185">1 (1 per VIP) + 2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="999d0-186">3</span><span class="sxs-lookup"><span data-stu-id="999d0-186">3</span></span></p></td>
<td><p><span data-ttu-id="999d0-187">3</span><span class="sxs-lookup"><span data-stu-id="999d0-187">3</span></span></p></td>
<td><p><span data-ttu-id="999d0-188">1 (1 per VIP) + 3</span><span class="sxs-lookup"><span data-stu-id="999d0-188">1 (1 per VIP) + 3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="999d0-189">4</span><span class="sxs-lookup"><span data-stu-id="999d0-189">4</span></span></p></td>
<td><p><span data-ttu-id="999d0-190">4</span><span class="sxs-lookup"><span data-stu-id="999d0-190">4</span></span></p></td>
<td><p><span data-ttu-id="999d0-191">1 (1 per VIP) + 4</span><span class="sxs-lookup"><span data-stu-id="999d0-191">1 (1 per VIP) + 4</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="999d0-192">5</span><span class="sxs-lookup"><span data-stu-id="999d0-192">5</span></span></p></td>
<td><p><span data-ttu-id="999d0-193">5</span><span class="sxs-lookup"><span data-stu-id="999d0-193">5</span></span></p></td>
<td><p><span data-ttu-id="999d0-194">1 (1 per VIP) + 5</span><span class="sxs-lookup"><span data-stu-id="999d0-194">1 (1 per VIP) + 5</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="999d0-195">I punti decisionali principali per la selezione della topologia sono elevata disponibilità e bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="999d0-195">The primary decision points for topology selection are high availability and load balancing.</span></span> <span data-ttu-id="999d0-196">Il requisito per l'elevata disponibilità può influenzare la decisione di bilanciamento del carico.</span><span class="sxs-lookup"><span data-stu-id="999d0-196">The requirement for high availability can influence the load balancing decision.</span></span>

  - <span data-ttu-id="999d0-197">**Disponibilità elevata**   Se è necessaria una disponibilità elevata, distribuire almeno due server perimetrali in un pool.</span><span class="sxs-lookup"><span data-stu-id="999d0-197">**High availability**   If you need high availability, deploy at least two Edge Servers in a pool.</span></span> <span data-ttu-id="999d0-198">Un singolo pool Edge supporta fino a dodici Edge Server.</span><span class="sxs-lookup"><span data-stu-id="999d0-198">A single Edge pool will support up to twelve Edge Servers.</span></span> <span data-ttu-id="999d0-199">Se è necessaria più capacità, è possibile distribuire più pool di bordi.</span><span class="sxs-lookup"><span data-stu-id="999d0-199">If more capacity is required, you can deploy multiple Edge pools.</span></span> <span data-ttu-id="999d0-200">Come regola generale, il 10% di una determinata base utenti richiederà l'accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="999d0-200">As a general rule, 10% of a given user base will need external access.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="999d0-201">Generatore di topologia consente di configurare un massimo di venti server Edge in un unico pool di Edge.</span><span class="sxs-lookup"><span data-stu-id="999d0-201">Topology Builder will allow you to configure up to twenty Edge Servers in a single Edge pool.</span></span> <span data-ttu-id="999d0-202">Il numero massimo testato e supportato di Edge Server in un pool è dodici e il generatore di topologia che consente un numero maggiore di dodici non deve essere interpretato come supporto implicito per più di dodici Edge Server in un unico pool di Edge.</span><span class="sxs-lookup"><span data-stu-id="999d0-202">The tested and supported maximum number of Edge Servers in a pool is twelve and Topology Builder allowing for a number larger than twelve should not be construed as implied support for more than twelve Edge Servers in a single Edge pool.</span></span>

    
    </div>

  - <span data-ttu-id="999d0-203">**Bilanciamento del carico hardware**   Il bilanciamento del carico hardware è supportato per il bilanciamento del carico di Lync Server 2013 Edge Server quando si usano indirizzi IP instradabili pubblicamente per le interfacce esterne di Edge.</span><span class="sxs-lookup"><span data-stu-id="999d0-203">**Hardware load balancing**   Hardware load balancing is supported for load balancing Lync Server 2013 Edge Servers when using publicly routable IP addresses for the Edge external interfaces.</span></span> <span data-ttu-id="999d0-204">Ad esempio, questo approccio dovrebbe essere usato in situazioni in cui è necessario il failover per una delle applicazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="999d0-204">For example, you would use this approach in situations where failover is required for any of the following applications:</span></span>
    
      - <span data-ttu-id="999d0-205">Connettività per messaggistica istantanea pubblica</span><span class="sxs-lookup"><span data-stu-id="999d0-205">Public IM connectivity</span></span>
    
      - <span data-ttu-id="999d0-206">Federazione con società che utilizzano Microsoft Office Communications Server 2007 o Microsoft Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="999d0-206">Federation with companies running Microsoft Office Communications Server 2007 or Microsoft Office Communications Server 2007 R2</span></span>
    
      - <span data-ttu-id="999d0-207">Accesso esterno alla messaggistica unificata di Exchange 2007 o messaggistica unificata di Exchange 2010</span><span class="sxs-lookup"><span data-stu-id="999d0-207">External access to Exchange 2007 Unified Messaging (UM) or Exchange 2010 UM</span></span>
        
        <div>
        

        > [!IMPORTANT]
        > <span data-ttu-id="999d0-208">Il bilanciamento del carico DNS per Exchange 2010 SP1 e versioni successive è supportato per la messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="999d0-208">DNS load balancing for Exchange 2010 SP1 and newer is supported for Exchange UM.</span></span>

        
        </div>
    
    <span data-ttu-id="999d0-209">Queste tre applicazioni continueranno a funzionare, ma non sono consapevoli del bilanciamento del carico DNS e si connetteranno solo al primo server perimetrale nel pool.</span><span class="sxs-lookup"><span data-stu-id="999d0-209">These three applications will continue to operate, but they are not DNS load balancing aware and will only connect to the first Edge Server in the pool.</span></span> <span data-ttu-id="999d0-210">Se il server non è disponibile, la connessione non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="999d0-210">If that server is unavailable, the connection will fail.</span></span> <span data-ttu-id="999d0-211">Ad esempio, se più Edge Server vengono distribuiti in un pool per gestire il carico di traffico federativo, un solo proxy di Access riceve effettivamente il traffico mentre gli altri sono inattivi.</span><span class="sxs-lookup"><span data-stu-id="999d0-211">For example, if multiple Edge Servers are deployed in a pool to handle the federated traffic load, only one access proxy actually receives traffic while the others are idle.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="999d0-212">È consigliabile usare il bilanciamento del carico DNS se si sta eseguendo la Federazione con aziende che usano Lync Server 2010 e Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="999d0-212">Using DNS load balancing is recommended if you are federating with companies using Lync Server 2010 and Microsoft Office 365.</span></span> <span data-ttu-id="999d0-213">Tenere presente che sono presenti effetti significativi sulle prestazioni se la maggior parte dei partner federati usa Office Communications Server 2007 o Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="999d0-213">Be aware that there are significant performance impacts if most of your federated partners are using Office Communications Server 2007 or Office Communications Server 2007 R2.</span></span>



<span data-ttu-id="999d0-214"></div>

</div>

<span> </span>

</div>

</div>

</span><span class="sxs-lookup"><span data-stu-id="999d0-214"></div>

</div>

<span> </span>

</div>

</div>

</span></span></div>

