---
title: "Lync Server 2013: Definizione dei requisiti dell'organizzazione per il controllo di ammissione di chiamata"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7737d303c7239df451c71b4f92d4dcd8dfe5b2e4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980542"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="f048e-102">Definizione dei requisiti dell'organizzazione per il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f048e-102">Defining your requirements for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f048e-103">_**Argomento Ultima modifica:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="f048e-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="f048e-104">Pianificazione per il controllo di ammissione alle chiamate (CAC) richiede informazioni dettagliate sulla topologia di rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="f048e-104">Planning for call admission control (CAC) requires detailed information about your enterprise network topology.</span></span> <span data-ttu-id="f048e-105">Per pianificare i criteri di controllo dell'ammissione alle chiamate, eseguire le operazioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f048e-105">To help plan your call admission control policies, follow these steps.</span></span>

1.  <span data-ttu-id="f048e-106">Identificare gli hub/backbone (chiamati aree di *rete*) all'interno della rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="f048e-106">Identify the hubs/backbones (called *network regions*) within your enterprise network.</span></span>

2.  <span data-ttu-id="f048e-107">Identificare gli uffici o le posizioni (detti *siti di rete*) all'interno di ogni area di rete.</span><span class="sxs-lookup"><span data-stu-id="f048e-107">Identify the offices or locations (called *network sites*) within each network region.</span></span>

3.  <span data-ttu-id="f048e-108">Determinare la route di rete tra ogni coppia di aree della rete.</span><span class="sxs-lookup"><span data-stu-id="f048e-108">Determine the network route between every pair of network regions.</span></span>

4.  <span data-ttu-id="f048e-109">Determinare i limiti di larghezza di banda per ogni collegamento WAN.</span><span class="sxs-lookup"><span data-stu-id="f048e-109">Determine the bandwidth limits for each WAN link.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f048e-110">I limiti di larghezza di banda si riferiscono alla quantità di larghezza di banda di un collegamento WAN assegnata al traffico VoIP aziendale e audio/video.</span><span class="sxs-lookup"><span data-stu-id="f048e-110">Bandwidth limits refer to how much of the bandwidth on a WAN link is allocated to Enterprise Voice and audio/video traffic.</span></span> <span data-ttu-id="f048e-111">Quando un collegamento WAN viene descritto come "vincolato alla larghezza di banda", il collegamento WAN ha un limite di larghezza di banda inferiore al traffico di picco previsto sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="f048e-111">When a WAN link is described as “bandwidth-constrained,” the WAN link has a bandwidth limit that is lower than the expected peak traffic over the link.</span></span>

    
    </div>

5.  <span data-ttu-id="f048e-112">Identificare le subnet IP assegnate a ogni sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f048e-112">Identify the IP subnets that are assigned to each network site.</span></span>

<span data-ttu-id="f048e-113">Per spiegare questi concetti, useremo la topologia di rete di esempio mostrata nella figura seguente.</span><span class="sxs-lookup"><span data-stu-id="f048e-113">To explain these concepts, we’ll use the example network topology shown in the following figure.</span></span>

<span data-ttu-id="f048e-114">**Topologia di esempio per il controllo dell'ammissione alle chiamate**</span><span class="sxs-lookup"><span data-stu-id="f048e-114">**Example topology for call admission control**</span></span>

<span data-ttu-id="f048e-115">Esempio di topologia di rete Inc. ![Litware]di(images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc.")</span><span class="sxs-lookup"><span data-stu-id="f048e-115">![Litware Inc. Network Topology Example](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. Network Topology Example")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f048e-116">Tutti i siti di rete sono associati a un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="f048e-116">All network sites are associated with a network region.</span></span> <span data-ttu-id="f048e-117">Ad esempio, Portland, Reno e Albuquerque sono inclusi nell'area Nord America.</span><span class="sxs-lookup"><span data-stu-id="f048e-117">For example, Portland, Reno, and Albuquerque are included in the North America region.</span></span> <span data-ttu-id="f048e-118">In questa figura sono mostrati solo i collegamenti WAN con i criteri di CAC, con limiti di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="f048e-118">In this figure, only WAN links that have CAC policies applied are shown, with bandwidth limits.</span></span> <span data-ttu-id="f048e-119">I siti di rete di Chicago, New York e Detroit sono visualizzati all'interno dell'area geografica Nord America, perché non sono vincolati alla larghezza di banda e quindi non richiedono criteri di CAC.</span><span class="sxs-lookup"><span data-stu-id="f048e-119">The network sites of Chicago, New York, and Detroit are shown inside the North America region oval because they are not bandwidth-constrained, and therefore do not require CAC policies.</span></span>



</div>

<span data-ttu-id="f048e-120">I componenti della topologia di esempio sono descritti nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="f048e-120">The components of this example topology are explained in the following sections.</span></span> <span data-ttu-id="f048e-121">Per informazioni dettagliate sulla pianificazione della topologia, inclusi i limiti di larghezza di banda, vedere [esempio: raccolta dei requisiti per il controllo dell'ammissione delle chiamate in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="f048e-121">For details about how this topology was planned, including the bandwidth limits, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span></span>

<div>

## <a name="identify-network-regions"></a><span data-ttu-id="f048e-122">Identificare le aree di rete</span><span class="sxs-lookup"><span data-stu-id="f048e-122">Identify Network Regions</span></span>

<span data-ttu-id="f048e-123">Un'area di rete rappresenta un backbone di rete o un hub di rete.</span><span class="sxs-lookup"><span data-stu-id="f048e-123">A network region represents a network backbone or a network hub.</span></span>

<span data-ttu-id="f048e-124">Un backbone o un hub di rete fa parte dell'infrastruttura di rete di computer che interconnette diverse parti della rete, fornendo un percorso per lo scambio di informazioni tra LAN o subnet diverse.</span><span class="sxs-lookup"><span data-stu-id="f048e-124">A network backbone or hub is a part of computer network infrastructure that interconnects different parts of the network, providing a path for the exchange of information between different LANs or subnets.</span></span> <span data-ttu-id="f048e-125">Una backbone può legare insieme diverse reti da una piccola posizione a un'area geografica ampia.</span><span class="sxs-lookup"><span data-stu-id="f048e-125">A backbone can tie together diverse networks from a small location to a wide geographic area.</span></span> <span data-ttu-id="f048e-126">La capacità della colonna vertebrale è in genere maggiore rispetto a quella delle reti che si connettono.</span><span class="sxs-lookup"><span data-stu-id="f048e-126">The backbone's capacity is typically greater than that of the networks that connect to it.</span></span>

<span data-ttu-id="f048e-127">La topologia di esempio include tre aree di rete: Nord America, EMEA e APAC.</span><span class="sxs-lookup"><span data-stu-id="f048e-127">Our example topology has three network regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="f048e-128">Un'area di rete contiene una raccolta di siti di rete (vedere la definizione dei siti di rete più avanti in questo argomento).</span><span class="sxs-lookup"><span data-stu-id="f048e-128">A network region contains a collection of network sites (see the definition of network sites later in this topic).</span></span> <span data-ttu-id="f048e-129">Collaborare con il team delle operazioni di rete per identificare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="f048e-129">Work with your network operations team to identify your network regions.</span></span>

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a><span data-ttu-id="f048e-130">Associazione di un sito centrale a ogni area di rete</span><span class="sxs-lookup"><span data-stu-id="f048e-130">Associating a Central Site with each Network Region</span></span>

<span data-ttu-id="f048e-131">Il CAC richiede che sia definito un sito centrale di Lync Server per ogni area di rete.</span><span class="sxs-lookup"><span data-stu-id="f048e-131">CAC requires that a Lync Server central site is defined for each network region.</span></span> <span data-ttu-id="f048e-132">Il sito centrale è selezionato con la connettività di rete migliore e la larghezza di banda più alta per tutti gli altri siti all'interno dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="f048e-132">The central site is selected with the best network connectivity and highest bandwidth to all the other sites within that network region.</span></span> <span data-ttu-id="f048e-133">L'esempio precedente della topologia di rete mostra tre aree di rete, ognuna con un sito centrale che gestisce le decisioni di CAC.</span><span class="sxs-lookup"><span data-stu-id="f048e-133">The preceding example of network topology shows three network regions, each with a central site that manages CAC decisions.</span></span> <span data-ttu-id="f048e-134">Nell'esempio precedente l'associazione appropriata è illustrata nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="f048e-134">From the preceding example, the appropriate association is shown in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f048e-135">I siti centrali non corrispondono necessariamente ai siti di rete.</span><span class="sxs-lookup"><span data-stu-id="f048e-135">Central sites do not necessarily correspond to network sites.</span></span> <span data-ttu-id="f048e-136">Negli esempi di questa documentazione, alcuni siti centrali, ovvero Chicago, Londra e Pechino, condividono lo stesso nome dei siti di rete.</span><span class="sxs-lookup"><span data-stu-id="f048e-136">In the examples in this documentation, some central sites—Chicago, London, and Beijing—share the same name as the network sites.</span></span> <span data-ttu-id="f048e-137">Tuttavia, anche se un sito centrale e un sito di rete condividono lo stesso nome, il sito centrale è un elemento della topologia di Lync Server, mentre il sito di rete fa parte della rete complessiva in cui risiede la topologia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="f048e-137">However, even if a central site and network site share the same name, the central site is an element of the Lync Server topology, whereas the network site is a part of the overall network in which the Lync Server topology resides.</span></span>



</div>

### <a name="network-regions-central-sites-and-network-sites"></a><span data-ttu-id="f048e-138">Aree di rete, siti centrali e siti di rete</span><span class="sxs-lookup"><span data-stu-id="f048e-138">Network regions, central sites, and network sites</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f048e-139">Area di rete</span><span class="sxs-lookup"><span data-stu-id="f048e-139">Network Region</span></span></th>
<th><span data-ttu-id="f048e-140">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="f048e-140">Central Site</span></span></th>
<th><span data-ttu-id="f048e-141">Siti di rete</span><span class="sxs-lookup"><span data-stu-id="f048e-141">Network Sites</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f048e-142">America del Nord</span><span class="sxs-lookup"><span data-stu-id="f048e-142">North America</span></span></p></td>
<td><p><span data-ttu-id="f048e-143">Chicago</span><span class="sxs-lookup"><span data-stu-id="f048e-143">Chicago</span></span></p></td>
<td><p><span data-ttu-id="f048e-144">Chicago</span><span class="sxs-lookup"><span data-stu-id="f048e-144">Chicago</span></span></p>
<p><span data-ttu-id="f048e-145">New York</span><span class="sxs-lookup"><span data-stu-id="f048e-145">New York</span></span></p>
<p><span data-ttu-id="f048e-146">Detroit</span><span class="sxs-lookup"><span data-stu-id="f048e-146">Detroit</span></span></p>
<p><span data-ttu-id="f048e-147">Portland</span><span class="sxs-lookup"><span data-stu-id="f048e-147">Portland</span></span></p>
<p><span data-ttu-id="f048e-148">Reno</span><span class="sxs-lookup"><span data-stu-id="f048e-148">Reno</span></span></p>
<p><span data-ttu-id="f048e-149">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="f048e-149">Albuquerque</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f048e-150">EMEA</span><span class="sxs-lookup"><span data-stu-id="f048e-150">EMEA</span></span></p></td>
<td><p><span data-ttu-id="f048e-151">Londra</span><span class="sxs-lookup"><span data-stu-id="f048e-151">London</span></span></p></td>
<td><p><span data-ttu-id="f048e-152">Londra</span><span class="sxs-lookup"><span data-stu-id="f048e-152">London</span></span></p>
<p><span data-ttu-id="f048e-153">Colonia</span><span class="sxs-lookup"><span data-stu-id="f048e-153">Cologne</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f048e-154">APAC</span><span class="sxs-lookup"><span data-stu-id="f048e-154">APAC</span></span></p></td>
<td><p><span data-ttu-id="f048e-155">Pechino</span><span class="sxs-lookup"><span data-stu-id="f048e-155">Beijing</span></span></p></td>
<td><p><span data-ttu-id="f048e-156">Pechino</span><span class="sxs-lookup"><span data-stu-id="f048e-156">Beijing</span></span></p>
<p><span data-ttu-id="f048e-157">Manila</span><span class="sxs-lookup"><span data-stu-id="f048e-157">Manila</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a><span data-ttu-id="f048e-158">Identificare i siti di rete</span><span class="sxs-lookup"><span data-stu-id="f048e-158">Identify Network Sites</span></span>

<span data-ttu-id="f048e-159">Un sito di rete rappresenta una posizione in cui l'organizzazione ha una sede fisica, ad esempio uffici, un set di edifici o un campus.</span><span class="sxs-lookup"><span data-stu-id="f048e-159">A network site represents a location where your organization has a physical venue—for example, offices, a set of buildings, or a campus.</span></span> <span data-ttu-id="f048e-160">Un luogo fisico con una LAN e una connettività WAN ad altri siti è considerato un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f048e-160">A physical venue with a LAN and has WAN connectivity to other sites is considered a network site.</span></span> <span data-ttu-id="f048e-161">Iniziare a inventariare tutti gli uffici dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f048e-161">Start by inventorying all of your organization’s offices.</span></span> <span data-ttu-id="f048e-162">Nella topologia di esempio l'area di rete Nord America è costituita dai siti di rete seguenti: New York, Chicago, Detroit, Portland, Reno e Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="f048e-162">In our example topology, the North America network region consists of the following network sites: New York, Chicago, Detroit, Portland, Reno, and Albuquerque.</span></span>

<span data-ttu-id="f048e-163">È necessario associare ogni sito di rete a un'area di rete.</span><span class="sxs-lookup"><span data-stu-id="f048e-163">You must associate every network site with a network region.</span></span> <span data-ttu-id="f048e-164">A seconda che il sito di rete disponga di un collegamento WAN vincolato, un criterio di larghezza di banda è associato al sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f048e-164">Depending on whether the network site has a constrained WAN link, a bandwidth policy is associated with the network site.</span></span> <span data-ttu-id="f048e-165">Per informazioni dettagliate sui criteri di CAC e sulla larghezza di banda allocata usandoli, vedere "definire i criteri di larghezza di banda" più avanti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="f048e-165">For details about CAC policies and the bandwidth that you allocate by using them, see "Define Bandwidth Policies" later in this topic.</span></span> <span data-ttu-id="f048e-166">Per configurare CAC, è possibile associare i siti di rete alle aree di rete e quindi creare criteri di assegnazione della larghezza di banda da applicare alle connessioni con vincoli di larghezza di banda tra un sito o un'area geografica specifica e le connessioni WAN tra i siti e le aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="f048e-166">To configure CAC, you associate network sites with network regions, and then you create bandwidth-allocating policies to apply to the bandwidth-constrained connections between a given site or region and the WAN connections between the sites and regions.</span></span>

</div>

<div>

## <a name="identify-network-links"></a><span data-ttu-id="f048e-167">Identificare i collegamenti di rete</span><span class="sxs-lookup"><span data-stu-id="f048e-167">Identify Network Links</span></span>

<span data-ttu-id="f048e-168">I collegamenti di rete rappresentano connessioni alla WAN fisica che collega aree e siti diversi.</span><span class="sxs-lookup"><span data-stu-id="f048e-168">Network links represent connections to the physical WAN that links different regions and sites.</span></span> <span data-ttu-id="f048e-169">Nella topologia di esempio ci sono due collegamenti di rete regionali, cinque collegamenti di rete tra aree geografiche e siti e un collegamento di rete tra due siti.</span><span class="sxs-lookup"><span data-stu-id="f048e-169">In our example topology, there are two regional network links, five network links between regions and sites, and one network link between two sites.</span></span>

<span data-ttu-id="f048e-170">I due collegamenti internazionali si trovano tra Nord America e EMEA, rappresentati come NA-EMEA-LINK e tra APAC e EMEA, rappresentati come EMEA-APAC-LINK.</span><span class="sxs-lookup"><span data-stu-id="f048e-170">The two regional links are between North America and EMEA, represented as NA-EMEA-LINK, and between APAC and EMEA, represented as EMEA-APAC-LINK.</span></span>

<span data-ttu-id="f048e-171">I collegamenti ai siti sono indicati dalle linee che collegano Portland, Reno e Albuquerque all'area Nord America, Manila alla regione APAC e Colonia nell'area EMEA.</span><span class="sxs-lookup"><span data-stu-id="f048e-171">The site links are indicated by the lines connecting Portland, Reno, and Albuquerque to the North America region, Manila to the APAC region, and Cologne to the EMEA region.</span></span> <span data-ttu-id="f048e-172">La linea tra Reno e Albuquerque Mostra un collegamento di rete diretta tra questi due siti.</span><span class="sxs-lookup"><span data-stu-id="f048e-172">The line between Reno and Albuquerque shows a direct network link between these two sites.</span></span>

</div>

<div>

## <a name="define-bandwidth-policies"></a><span data-ttu-id="f048e-173">Definire i criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="f048e-173">Define Bandwidth Policies</span></span>

<span data-ttu-id="f048e-174">Collaborare con il team operazioni di rete per determinare la quantità di larghezza di banda WAN disponibile per il traffico audio e video in tempo reale nei collegamenti WAN dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="f048e-174">Work with your network operations team to determine how much WAN bandwidth is available for real-time audio and video traffic across the WAN links in your organization.</span></span> <span data-ttu-id="f048e-175">I criteri di larghezza di banda vengono in genere applicati ai collegamenti WAN se l'utilizzo della larghezza di banda è vincolato; Se si prevede che la larghezza di banda può essere allocata per le modalità audio e video.</span><span class="sxs-lookup"><span data-stu-id="f048e-175">Bandwidth policies are typically applied to WAN links if the bandwidth usage is constrained; that is, if it expected to be more than the bandwidth that can be allocated for audio and video modalities.</span></span>

<span data-ttu-id="f048e-176">I *criteri di larghezza di banda* CAC definiscono la larghezza di banda massima che può essere riservata per le modalità audio e video in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="f048e-176">CAC *bandwidth policies* define the maximum bandwidth that can be reserved for real-time audio and video modalities.</span></span> <span data-ttu-id="f048e-177">Dato che CAC non limita la larghezza di banda di un altro traffico, non può impedire l'uso di tutta la larghezza di banda della rete, ad esempio un trasferimento di file di grandi dimensioni, lo streaming di musica.</span><span class="sxs-lookup"><span data-stu-id="f048e-177">Since CAC does not limit the bandwidth of other traffic, it cannot prevent other data traffic such as a large file transfer, music streaming, from using up all of the network bandwidth.</span></span>

<span data-ttu-id="f048e-178">I criteri di larghezza di banda CAC possono definire uno o tutti gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f048e-178">CAC bandwidth policies can define any or all of the following:</span></span>

  - <span data-ttu-id="f048e-179">Larghezza di banda totale massima allocata per l'audio.</span><span class="sxs-lookup"><span data-stu-id="f048e-179">Maximum total bandwidth allocated for audio.</span></span>

  - <span data-ttu-id="f048e-180">Larghezza di banda totale massima allocata per il video.</span><span class="sxs-lookup"><span data-stu-id="f048e-180">Maximum total bandwidth allocated for video.</span></span>

  - <span data-ttu-id="f048e-181">Larghezza di banda massima allocata per una singola chiamata audio (sessione).</span><span class="sxs-lookup"><span data-stu-id="f048e-181">Maximum bandwidth allocated for a single audio call (session).</span></span>

  - <span data-ttu-id="f048e-182">Larghezza di banda massima allocata per una singola chiamata video (sessione).</span><span class="sxs-lookup"><span data-stu-id="f048e-182">Maximum bandwidth allocated for a single video call (session).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f048e-183">Tutti i valori di larghezza di banda CAC rappresentano i limiti massimi di larghezza di banda <EM>unidirezionali</EM> .</span><span class="sxs-lookup"><span data-stu-id="f048e-183">All CAC bandwidth values represent the maximum <EM>unidirectional</EM> bandwidth limits.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="f048e-184">Le caratteristiche dei criteri vocali di Lync Server 2013 consentono di ignorare i controlli dei criteri di larghezza di banda per le chiamate in arrivo all'utente (non per le chiamate in uscita inserite dall'utente).</span><span class="sxs-lookup"><span data-stu-id="f048e-184">The Lync Server 2013 Voice Policy features provide the ability to override bandwidth policy checks for incoming calls to the user (not for outgoing calls that are placed by the user).</span></span> <span data-ttu-id="f048e-185">Dopo la creazione della sessione, il consumo di larghezza di banda verrà contabilizzato in modo accurato.</span><span class="sxs-lookup"><span data-stu-id="f048e-185">After the session is established, the bandwidth consumption will be accurately accounted for.</span></span> <span data-ttu-id="f048e-186">Questa impostazione deve essere usata con parsimonia.</span><span class="sxs-lookup"><span data-stu-id="f048e-186">This setting should be used sparingly.</span></span> <span data-ttu-id="f048e-187">Per informazioni dettagliate, vedere <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">creare un criterio vocale e configurare i record di utilizzo PSTN in Lync server 2013</A> o <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f048e-187">For details, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="f048e-188">Per ottimizzare l'utilizzo della larghezza di banda per ogni singola sessione, prendere in considerazione il tipo di codec audio e video che verranno usati.</span><span class="sxs-lookup"><span data-stu-id="f048e-188">To optimize bandwidth utilization on a per-session basis, consider the type of audio and video codecs that will be used.</span></span> <span data-ttu-id="f048e-189">In particolare, evitare di allocare larghezza di banda insufficiente per un codec che si prevede di usare di frequente.</span><span class="sxs-lookup"><span data-stu-id="f048e-189">In particular, avoid allocating insufficient bandwidth for a codec that you expect to be used frequently.</span></span> <span data-ttu-id="f048e-190">Se invece si vuole impedire l'uso di un codec che richiede più larghezza di banda, è consigliabile impostare la larghezza di banda massima per ogni sessione abbastanza bassa da scoraggiare tale utilizzo.</span><span class="sxs-lookup"><span data-stu-id="f048e-190">Conversely, if you want to prevent media from using a codec that requires more bandwidth, you should set the maximum bandwidth per session low enough to discourage such use.</span></span> <span data-ttu-id="f048e-191">Per l'audio, non tutti i codec sono disponibili per ogni scenario.</span><span class="sxs-lookup"><span data-stu-id="f048e-191">For audio, not every codec is available for every scenario.</span></span> <span data-ttu-id="f048e-192">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="f048e-192">For example:</span></span>

  - <span data-ttu-id="f048e-193">Le chiamate audio peer-to-peer tra endpoint Lync utilizzeranno RTAudio (8kHz) o RTAudio (16kHz) quando si fattorizza la larghezza di banda e la priorità dei codec.</span><span class="sxs-lookup"><span data-stu-id="f048e-193">Peer-to-peer audio calls between Lync endpoints will use either RTAudio (8kHz) or RTAudio (16kHz) when you factor in the bandwidth and prioritization of codecs.</span></span>

  - <span data-ttu-id="f048e-194">Le chiamate in conferenza tra endpoint Lync e il servizio di conferenza A/V utilizzeranno G. 722 o Siren.</span><span class="sxs-lookup"><span data-stu-id="f048e-194">Conference calls between Lync endpoints and the A/V Conferencing service will use either G.722 or Siren.</span></span>

  - <span data-ttu-id="f048e-195">Le chiamate alla rete PSTN (Public Switched Telephone Network) in o da endpoint di Lync utilizzeranno G. 711 o RTAudio (8kHz).</span><span class="sxs-lookup"><span data-stu-id="f048e-195">Calls to the public switched telephone network (PSTN) either to or from Lync endpoints will use either G.711 or RTAudio (8kHz).</span></span>

<span data-ttu-id="f048e-196">Usare la tabella seguente per ottimizzare le impostazioni di larghezza di banda massima per sessione.</span><span class="sxs-lookup"><span data-stu-id="f048e-196">Use the following table to help optimize the maximum per-session bandwidth settings.</span></span>

### <a name="bandwidth-utilization-by-codecs"></a><span data-ttu-id="f048e-197">Utilizzo della larghezza di banda per codec</span><span class="sxs-lookup"><span data-stu-id="f048e-197">Bandwidth utilization by codecs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f048e-198">Codec</span><span class="sxs-lookup"><span data-stu-id="f048e-198">Codec</span></span></th>
<th><span data-ttu-id="f048e-199">Requisito della larghezza di banda senza correzione degli errori in avanti (FEC)</span><span class="sxs-lookup"><span data-stu-id="f048e-199">Bandwidth requirement with no forward error correction (FEC)</span></span></th>
<th><span data-ttu-id="f048e-200">Requisito della larghezza di banda con la correzione degli errori in avanti (FEC)</span><span class="sxs-lookup"><span data-stu-id="f048e-200">Bandwidth requirement with forward error correction (FEC)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f048e-201">RTAudio (8kHz)</span><span class="sxs-lookup"><span data-stu-id="f048e-201">RTAudio (8kHz)</span></span></p></td>
<td><p><span data-ttu-id="f048e-202">49,8 Kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-202">49.8 kbps</span></span></p></td>
<td><p><span data-ttu-id="f048e-203">61,6 Kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-203">61.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f048e-204">RTAudio (16kHz)</span><span class="sxs-lookup"><span data-stu-id="f048e-204">RTAudio (16kHz)</span></span></p></td>
<td><p><span data-ttu-id="f048e-205">67 kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-205">67 kbps</span></span></p></td>
<td><p><span data-ttu-id="f048e-206">96 kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-206">96 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f048e-207">Sirena</span><span class="sxs-lookup"><span data-stu-id="f048e-207">Siren</span></span></p></td>
<td><p><span data-ttu-id="f048e-208">57,6 Kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-208">57.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="f048e-209">73,6 Kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-209">73.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f048e-210">G. 711</span><span class="sxs-lookup"><span data-stu-id="f048e-210">G.711</span></span></p></td>
<td><p><span data-ttu-id="f048e-211">102 Kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-211">102 kbps</span></span></p></td>
<td><p><span data-ttu-id="f048e-212">166 kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-212">166 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f048e-213">G. 722</span><span class="sxs-lookup"><span data-stu-id="f048e-213">G.722</span></span></p></td>
<td><p><span data-ttu-id="f048e-214">105,6 Kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-214">105.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="f048e-215">169,6 Kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-215">169.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f048e-216">RTVideo (CIF 15 fps)</span><span class="sxs-lookup"><span data-stu-id="f048e-216">RTVideo (CIF 15 fps)</span></span></p></td>
<td><p><span data-ttu-id="f048e-217">260 Kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-217">260 kbps</span></span></p></td>
<td><p><span data-ttu-id="f048e-218">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f048e-218">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f048e-219">RTVideo (VGA 30 fps)</span><span class="sxs-lookup"><span data-stu-id="f048e-219">RTVideo (VGA 30 fps)</span></span></p></td>
<td><p><span data-ttu-id="f048e-220">610 Kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-220">610 kbps</span></span></p></td>
<td><p><span data-ttu-id="f048e-221">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="f048e-221">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="f048e-222">I requisiti di larghezza di banda prendono in considerazione i costi seguenti: Ethernet II, IP, User Datagram Protocol (UDP), RTP (protocollo di trasporto in tempo reale) e SRTP (Secure Real-Time Transport Protocol).</span><span class="sxs-lookup"><span data-stu-id="f048e-222">Bandwidth requirements take into account overhead for the following: Ethernet II, IP, User Datagram Protocol (UDP), RTP (real-time transport protocol), and SRTP (secure real-time transport protocol).</span></span> <span data-ttu-id="f048e-223">Includono inoltre 10 Kbps per l'overhead di RTCP.</span><span class="sxs-lookup"><span data-stu-id="f048e-223">They also include 10 kbps for RTCP overhead.</span></span>



</div>

<span data-ttu-id="f048e-224">I codec G. 722.1 e Siren sono simili, ma offrono diversi bitrate.</span><span class="sxs-lookup"><span data-stu-id="f048e-224">The G.722.1 and Siren codecs are similar, but they offer different bit rates.</span></span>

<span data-ttu-id="f048e-225">G. 722, il codec predefinito per i servizi di conferenza di Lync Server, è completamente diverso dai codec G. 722.1 e Siren.</span><span class="sxs-lookup"><span data-stu-id="f048e-225">G.722, the default codec for Lync Server conferencing, is completely different from the G.722.1 and Siren codecs.</span></span>

<span data-ttu-id="f048e-226">Il codec Siren viene usato in Lync Server nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f048e-226">The Siren codec is used in Lync Server in the following situations:</span></span>

  - <span data-ttu-id="f048e-227">Se i criteri di larghezza di banda sono impostati troppo bassi per l'uso di G. 722.</span><span class="sxs-lookup"><span data-stu-id="f048e-227">If the bandwidth policy is set too low for G.722 to be used.</span></span>

  - <span data-ttu-id="f048e-228">Se un client di Communications Server 2007 o Communications Server 2007 R2 si connette a un servizio di conferenza di Lync Server (poiché tali client non supportano il codec G. 722).</span><span class="sxs-lookup"><span data-stu-id="f048e-228">If a Communications Server 2007 or Communications Server 2007 R2 client connects to a Lync Server conferencing service (because those clients do not support the G.722 codec).</span></span>

### <a name="bandwidth-utilization-by-scenario"></a><span data-ttu-id="f048e-229">Utilizzo della larghezza di banda per scenario</span><span class="sxs-lookup"><span data-stu-id="f048e-229">Bandwidth utilization by scenario</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f048e-230">Scenario</span><span class="sxs-lookup"><span data-stu-id="f048e-230">Scenario</span></span></th>
<th><span data-ttu-id="f048e-231">Requisito di larghezza di banda ottimizzato per quantità (Kbps)</span><span class="sxs-lookup"><span data-stu-id="f048e-231">Bandwidth requirement optimized for quantity (kbps)</span></span></th>
<th><span data-ttu-id="f048e-232">Requisito della larghezza di banda per la modalità bilanciata (Kbps)</span><span class="sxs-lookup"><span data-stu-id="f048e-232">Bandwidth requirement for Balanced mode (kbps)</span></span></th>
<th><span data-ttu-id="f048e-233">Requisiti di larghezza di banda ottimizzati per la qualità (Kbps)</span><span class="sxs-lookup"><span data-stu-id="f048e-233">Bandwidth requirement optimized for quality (kbps)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f048e-234">Chiamate audio peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="f048e-234">Peer-to-peer audio calls</span></span></p></td>
<td><p><span data-ttu-id="f048e-235">45 Kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-235">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="f048e-236">62 kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-236">62 kbps</span></span></p></td>
<td><p><span data-ttu-id="f048e-237">91 kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-237">91 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f048e-238">Chiamate in conferenza</span><span class="sxs-lookup"><span data-stu-id="f048e-238">Conference calls</span></span></p></td>
<td><p><span data-ttu-id="f048e-239">53 Kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-239">53 kbps</span></span></p></td>
<td><p><span data-ttu-id="f048e-240">101 kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-240">101 kbps</span></span></p></td>
<td><p><span data-ttu-id="f048e-241">165 kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-241">165 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f048e-242">Chiamate PSTN (tra Lync 2013 e gateway PSTN, con il bypass multimediale)</span><span class="sxs-lookup"><span data-stu-id="f048e-242">PSTN calls (between Lync 2013 and PSTN gateway, with media bypass)</span></span></p></td>
<td><p><span data-ttu-id="f048e-243">97 kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-243">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="f048e-244">97 kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-244">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="f048e-245">161 kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-245">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f048e-246">Chiamate PSTN (tra Lync 2013 e Mediation Server, senza bypass multimediale)</span><span class="sxs-lookup"><span data-stu-id="f048e-246">PSTN calls (between Lync 2013 and Mediation Server, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="f048e-247">45 Kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-247">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="f048e-248">97 kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-248">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="f048e-249">161 kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-249">161 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f048e-250">Chiamate PSTN (tra Mediation Server e gateway PSTN, senza bypass multimediale)</span><span class="sxs-lookup"><span data-stu-id="f048e-250">PSTN calls (between Mediation Server and PSTN gateway, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="f048e-251">97 kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-251">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="f048e-252">97 kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-252">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="f048e-253">161 kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-253">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f048e-254">Chiamate di Lync-Polycom</span><span class="sxs-lookup"><span data-stu-id="f048e-254">Lync - Polycom calls</span></span></p></td>
<td><p><span data-ttu-id="f048e-255">101 kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-255">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="f048e-256">101 kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-256">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="f048e-257">101 kbps</span><span class="sxs-lookup"><span data-stu-id="f048e-257">101 Kbps</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="f048e-258">Identificare le subnet IP</span><span class="sxs-lookup"><span data-stu-id="f048e-258">Identify IP Subnets</span></span>

<span data-ttu-id="f048e-259">Per ogni sito di rete, è necessario collaborare con l'amministratore di rete per determinare quali subnet IP vengono assegnate a ogni sito di rete.</span><span class="sxs-lookup"><span data-stu-id="f048e-259">For each network site, you will need to work with your network administrator to determine what IP subnets are assigned to each network site.</span></span> <span data-ttu-id="f048e-260">Se l'amministratore di rete ha già organizzato le subnet IP nelle aree di rete e nei siti di rete, il lavoro è semplificato in modo significativo.</span><span class="sxs-lookup"><span data-stu-id="f048e-260">If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="f048e-261">In questo esempio, nel sito di New York nell'area Nord America sono assegnate le subnet IP seguenti: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24.</span><span class="sxs-lookup"><span data-stu-id="f048e-261">In our example, the New York site in the North America region is assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24.</span></span> <span data-ttu-id="f048e-262">Supponiamo che Roberto, che lavora in genere a Detroit, viaggi nell'ufficio di New York per la formazione.</span><span class="sxs-lookup"><span data-stu-id="f048e-262">Suppose Bob, who typically works in Detroit, travels to the New York office for training.</span></span> <span data-ttu-id="f048e-263">Quando accende il computer e si connette alla rete, il computer riceverà un indirizzo IP in uno dei quattro intervalli riservati a New York, ad esempio 172.29.80.103.</span><span class="sxs-lookup"><span data-stu-id="f048e-263">When he turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges reserved for New York, for example 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="f048e-264">Le subnet IP specificate durante la configurazione di rete nel server devono corrispondere al formato fornito dai computer client per poter essere usate correttamente per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="f048e-264">The IP subnets specified during network configuration on the server must match the format provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="f048e-265">Un client Lync prende l'indirizzo IP locale e maschera l'indirizzo IP con la subnet mask associata.</span><span class="sxs-lookup"><span data-stu-id="f048e-265">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="f048e-266">Quando si determina l'ID di bypass associato a ogni client, il registrar confronterà l'elenco delle subnet IP associate a ogni sito di rete rispetto alla subnet fornita dal client per una corrispondenza esatta.</span><span class="sxs-lookup"><span data-stu-id="f048e-266">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet provided by the client for an exact match.</span></span> <span data-ttu-id="f048e-267">Per questo motivo, è importante che le subnet immesse durante la configurazione di rete sul server siano subnet effettive anziché sottoreti virtuali.</span><span class="sxs-lookup"><span data-stu-id="f048e-267">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="f048e-268">Se si distribuisce il controllo di ammissione alle chiamate, ma non il bypass multimediale, il controllo di ammissione delle chiamate funzionerà correttamente anche se si configurano sottoreti virtuali.</span><span class="sxs-lookup"><span data-stu-id="f048e-268">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="f048e-269">Ad esempio, se un client esegue l'accesso in un computer con un indirizzo IP di 172.29.81.57 con una subnet mask IP 255.255.255.0, Lync 2013 richiederà l'ID di bypass associato alla subnet 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="f048e-269">For example, if a client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, Lync 2013 will request the bypass ID associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="f048e-270">Se la subnet è definita come 172.29.0.0/16, anche se il client appartiene alla subnet virtuale, il registrar non considererà questa corrispondenza perché il registrar Cerca specificamente la subnet 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="f048e-270">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="f048e-271">Di conseguenza, è importante che l'amministratore immetta le subnet esattamente come fornite dai client Lync (che vengono provisionate con subnet durante la configurazione di rete in modo statico o tramite DHCP).</span><span class="sxs-lookup"><span data-stu-id="f048e-271">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration either statically or by DHCP.)</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

