---
title: 'Lync Server 2013: definizione dei requisiti per il controllo di ammissione di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for call admission control
ms:assetid: 5122171a-a5b0-4059-b033-846caec10d1e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398334(v=OCS.15)
ms:contentKeyID: 48184104
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d26596f48178f53f79b1c4cc136610d45705ffd1
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42032461"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="b11e9-102">Definizione dei requisiti per il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b11e9-102">Defining your requirements for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b11e9-103">_**Ultimo argomento modificato:** 2013-10-28_</span><span class="sxs-lookup"><span data-stu-id="b11e9-103">_**Topic Last Modified:** 2013-10-28_</span></span>

<span data-ttu-id="b11e9-p101">La pianificazione del controllo di ammissione di chiamata (CAC, Call Admission Control) richiede informazioni dettagliate sulla topologia di rete aziendale. Per pianificare più agevolmente i criteri di controllo di ammissione di chiamata, eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="b11e9-p101">Planning for call admission control (CAC) requires detailed information about your enterprise network topology. To help plan your call admission control policies, follow these steps.</span></span>

1.  <span data-ttu-id="b11e9-106">Identificare gli hub/backbone (noti come *aree di rete*) nella rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="b11e9-106">Identify the hubs/backbones (called *network regions*) within your enterprise network.</span></span>

2.  <span data-ttu-id="b11e9-107">Identificare gli uffici o le sedi (noti come *siti di rete*) in ogni area di rete.</span><span class="sxs-lookup"><span data-stu-id="b11e9-107">Identify the offices or locations (called *network sites*) within each network region.</span></span>

3.  <span data-ttu-id="b11e9-108">Stabilire la route di rete tra ogni coppia di aree di rete.</span><span class="sxs-lookup"><span data-stu-id="b11e9-108">Determine the network route between every pair of network regions.</span></span>

4.  <span data-ttu-id="b11e9-109">Determinare i limiti di larghezza di banda per ogni collegamento WAN.</span><span class="sxs-lookup"><span data-stu-id="b11e9-109">Determine the bandwidth limits for each WAN link.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b11e9-110">I limiti di larghezza di banda si riferiscono a quanto la larghezza di banda di un collegamento WAN viene allocata al traffico VoIP aziendale e audio/video.</span><span class="sxs-lookup"><span data-stu-id="b11e9-110">Bandwidth limits refer to how much of the bandwidth on a WAN link is allocated to Enterprise Voice and audio/video traffic.</span></span> <span data-ttu-id="b11e9-111">Se un collegamento WAN è indicato come "con larghezza di banda limitata" significa che il limite della larghezza di banda per il collegamento WAN è inferiore al traffico di picco previsto sul collegamento.</span><span class="sxs-lookup"><span data-stu-id="b11e9-111">When a WAN link is described as “bandwidth-constrained,” the WAN link has a bandwidth limit that is lower than the expected peak traffic over the link.</span></span>

    
    </div>

5.  <span data-ttu-id="b11e9-112">Identificare le subnet IP assegnate a ogni sito di rete.</span><span class="sxs-lookup"><span data-stu-id="b11e9-112">Identify the IP subnets that are assigned to each network site.</span></span>

<span data-ttu-id="b11e9-113">Per illustrare questi concetti verrà utilizzata la topologia di rete di esempio mostrata della figura seguente.</span><span class="sxs-lookup"><span data-stu-id="b11e9-113">To explain these concepts, we’ll use the example network topology shown in the following figure.</span></span>

<span data-ttu-id="b11e9-114">**Topologia di esempio per il controllo di ammissione di chiamata**</span><span class="sxs-lookup"><span data-stu-id="b11e9-114">**Example topology for call admission control**</span></span>

<span data-ttu-id="b11e9-115">![Esempio di topologia di rete di Litware Inc.](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Esempio di topologia di rete di Litware Inc.")</span><span class="sxs-lookup"><span data-stu-id="b11e9-115">![Litware Inc. Network Topology Example](images/Gg398334.477f3b52-2973-4026-9bc0-b1c6bf9f4803(OCS.15).jpg "Litware Inc. Network Topology Example")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b11e9-p103">Tutti i siti di rete sono associati a un'area di rete. Portland, Reno e Albuquerque, ad esempio, sono inclusi nell'area Nord America. In questa figura sono visualizzati solo i collegamenti WAN a cui sono applicati criteri di controllo di ammissione di chiamata, con limiti di larghezza di banda. I siti di rete Chicago, New York e Detroit sono visualizzati all'interno dell'ovale dell'area Nord America perché non presentano limitazioni di larghezza di banda e quindi non richiedono criteri di controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="b11e9-p103">All network sites are associated with a network region. For example, Portland, Reno, and Albuquerque are included in the North America region. In this figure, only WAN links that have CAC policies applied are shown, with bandwidth limits. The network sites of Chicago, New York, and Detroit are shown inside the North America region oval because they are not bandwidth-constrained, and therefore do not require CAC policies.</span></span>



</div>

<span data-ttu-id="b11e9-120">I componenti di questa topologia di esempio sono spiegati nelle sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="b11e9-120">The components of this example topology are explained in the following sections.</span></span> <span data-ttu-id="b11e9-121">Per informazioni dettagliate sulla pianificazione della topologia, inclusi i limiti relativi alla larghezza di banda, vedere [example: Gathering your requirements for Call Admission Control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="b11e9-121">For details about how this topology was planned, including the bandwidth limits, see [Example: Gathering your requirements for call admission control in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md).</span></span>

<div>

## <a name="identify-network-regions"></a><span data-ttu-id="b11e9-122">Identificare le aree di rete</span><span class="sxs-lookup"><span data-stu-id="b11e9-122">Identify Network Regions</span></span>

<span data-ttu-id="b11e9-123">Un'area di rete rappresenta un backbone o un hub della rete.</span><span class="sxs-lookup"><span data-stu-id="b11e9-123">A network region represents a network backbone or a network hub.</span></span>

<span data-ttu-id="b11e9-p105">Un backbone o un hub di rete è una parte dell'infrastruttura di rete di computer che interconnette parti diverse della rete, offrendo un percorso per lo scambio di informazioni tra LAN o subnet diverse. Un backbone può collegare reti diverse, da una piccola sede a un'area geografica più ampia. La capacità del backbone è generalmente più alta rispetto a quella delle reti che vi si connettono.</span><span class="sxs-lookup"><span data-stu-id="b11e9-p105">A network backbone or hub is a part of computer network infrastructure that interconnects different parts of the network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks that connect to it.</span></span>

<span data-ttu-id="b11e9-p106">La topologia dell'esempio include tre aree di rete, ovvero Nord America, EMEA e APAC. Un'area di rete contiene un insieme di siti di rete (vedere la definizione di siti di rete più avanti in questo argomento). Collaborare con il team responsabile delle operazioni di rete per identificare le aree.</span><span class="sxs-lookup"><span data-stu-id="b11e9-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites (see the definition of network sites later in this topic). Work with your network operations team to identify your network regions.</span></span>

</div>

<div>

## <a name="associating-a-central-site-with-each-network-region"></a><span data-ttu-id="b11e9-130">Associazione di un sito centrale a ogni area di rete</span><span class="sxs-lookup"><span data-stu-id="b11e9-130">Associating a Central Site with each Network Region</span></span>

<span data-ttu-id="b11e9-131">Per ogni area di rete è necessario che sia definito un sito centrale di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b11e9-131">CAC requires that a Lync Server central site is defined for each network region.</span></span> <span data-ttu-id="b11e9-132">Il sito centrale selezionato deve avere la connettività di rete più efficiente e la larghezza di banda più ampia verso tutti gli altri siti nell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="b11e9-132">The central site is selected with the best network connectivity and highest bandwidth to all the other sites within that network region.</span></span> <span data-ttu-id="b11e9-133">La topologia di rete dell'esempio precedente mostra tre aree di rete, ognuna con un sito centrale che gestisce le decisioni relative al servizio Controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="b11e9-133">The preceding example of network topology shows three network regions, each with a central site that manages CAC decisions.</span></span> <span data-ttu-id="b11e9-134">Per questo esempio l'associazione appropriata è illustrata nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="b11e9-134">From the preceding example, the appropriate association is shown in the following table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b11e9-135">I siti centrali non corrispondono necessariamente a siti di rete.</span><span class="sxs-lookup"><span data-stu-id="b11e9-135">Central sites do not necessarily correspond to network sites.</span></span> <span data-ttu-id="b11e9-136">Negli esempi in questa documentazione alcuni siti centrali, come Chicago, Londra e Pechino, hanno lo stesso nome di alcuni siti di rete.</span><span class="sxs-lookup"><span data-stu-id="b11e9-136">In the examples in this documentation, some central sites—Chicago, London, and Beijing—share the same name as the network sites.</span></span> <span data-ttu-id="b11e9-137">Tuttavia, anche se un sito centrale e un sito di rete condividono lo stesso nome, il sito centrale è un elemento della topologia di Lync Server, mentre il sito di rete è una parte della rete globale in cui risiede la topologia di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b11e9-137">However, even if a central site and network site share the same name, the central site is an element of the Lync Server topology, whereas the network site is a part of the overall network in which the Lync Server topology resides.</span></span>



</div>

### <a name="network-regions-central-sites-and-network-sites"></a><span data-ttu-id="b11e9-138">Aree di rete, siti centrali e siti di rete</span><span class="sxs-lookup"><span data-stu-id="b11e9-138">Network regions, central sites, and network sites</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b11e9-139">Area di rete</span><span class="sxs-lookup"><span data-stu-id="b11e9-139">Network Region</span></span></th>
<th><span data-ttu-id="b11e9-140">Sito Centrale</span><span class="sxs-lookup"><span data-stu-id="b11e9-140">Central Site</span></span></th>
<th><span data-ttu-id="b11e9-141">Siti di rete</span><span class="sxs-lookup"><span data-stu-id="b11e9-141">Network Sites</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b11e9-142">Nord America</span><span class="sxs-lookup"><span data-stu-id="b11e9-142">North America</span></span></p></td>
<td><p><span data-ttu-id="b11e9-143">Chicago</span><span class="sxs-lookup"><span data-stu-id="b11e9-143">Chicago</span></span></p></td>
<td><p><span data-ttu-id="b11e9-144">Chicago</span><span class="sxs-lookup"><span data-stu-id="b11e9-144">Chicago</span></span></p>
<p><span data-ttu-id="b11e9-145">New York</span><span class="sxs-lookup"><span data-stu-id="b11e9-145">New York</span></span></p>
<p><span data-ttu-id="b11e9-146">Detroit</span><span class="sxs-lookup"><span data-stu-id="b11e9-146">Detroit</span></span></p>
<p><span data-ttu-id="b11e9-147">Portland</span><span class="sxs-lookup"><span data-stu-id="b11e9-147">Portland</span></span></p>
<p><span data-ttu-id="b11e9-148">Reno</span><span class="sxs-lookup"><span data-stu-id="b11e9-148">Reno</span></span></p>
<p><span data-ttu-id="b11e9-149">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="b11e9-149">Albuquerque</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b11e9-150">EMEA</span><span class="sxs-lookup"><span data-stu-id="b11e9-150">EMEA</span></span></p></td>
<td><p><span data-ttu-id="b11e9-151">Londra</span><span class="sxs-lookup"><span data-stu-id="b11e9-151">London</span></span></p></td>
<td><p><span data-ttu-id="b11e9-152">Londra</span><span class="sxs-lookup"><span data-stu-id="b11e9-152">London</span></span></p>
<p><span data-ttu-id="b11e9-153">Colonia</span><span class="sxs-lookup"><span data-stu-id="b11e9-153">Cologne</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b11e9-154">APAC</span><span class="sxs-lookup"><span data-stu-id="b11e9-154">APAC</span></span></p></td>
<td><p><span data-ttu-id="b11e9-155">Pechino</span><span class="sxs-lookup"><span data-stu-id="b11e9-155">Beijing</span></span></p></td>
<td><p><span data-ttu-id="b11e9-156">Pechino</span><span class="sxs-lookup"><span data-stu-id="b11e9-156">Beijing</span></span></p>
<p><span data-ttu-id="b11e9-157">Manila</span><span class="sxs-lookup"><span data-stu-id="b11e9-157">Manila</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-network-sites"></a><span data-ttu-id="b11e9-158">Identificare i siti di rete</span><span class="sxs-lookup"><span data-stu-id="b11e9-158">Identify Network Sites</span></span>

<span data-ttu-id="b11e9-p109">Un sito di rete rappresenta una località in cui l'organizzazione dispone di spazi fisici, ad esempio uffici, un gruppo di edifici o un campus. Uno spazio fisico con connettività LAN e WAN ad altri siti è considerata un sito di rete. Per iniziare, creare un inventario di tutti gli uffici dell'organizzazione. Nella topologia dell'esempio, l'area di rete Nord America è costituita dai siti di rete seguenti: New York, Chicago, Detroit, Portland, Reno e Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="b11e9-p109">A network site represents a location where your organization has a physical venue—for example, offices, a set of buildings, or a campus. A physical venue with a LAN and has WAN connectivity to other sites is considered a network site. Start by inventorying all of your organization’s offices. In our example topology, the North America network region consists of the following network sites: New York, Chicago, Detroit, Portland, Reno, and Albuquerque.</span></span>

<span data-ttu-id="b11e9-p110">È necessario associare ogni sito di rete a un'area di rete. A seconda che il sito di rete abbia o meno un collegamento WAN limitato, al sito di rete vengono associati criteri per la larghezza di banda. Per informazioni dettagliate sui criteri di controllo di ammissione di chiamata e la larghezza di banda che è possibile allocare tramite tali criteri, vedere "Definire i criteri di larghezza di banda" di seguito in questo argomento. Per configurare i criteri di controllo di ammissione di chiamata, è necessario associare i siti di rete alle aree di rete e quindi creare i criteri di allocazione della larghezza di banda da applicare alle connessioni con larghezza di banda limitata tra un determinato sito o una particolare area e le connessioni WAN tra siti e aree.</span><span class="sxs-lookup"><span data-stu-id="b11e9-p110">You must associate every network site with a network region. Depending on whether the network site has a constrained WAN link, a bandwidth policy is associated with the network site. For details about CAC policies and the bandwidth that you allocate by using them, see "Define Bandwidth Policies" later in this topic. To configure CAC, you associate network sites with network regions, and then you create bandwidth-allocating policies to apply to the bandwidth-constrained connections between a given site or region and the WAN connections between the sites and regions.</span></span>

</div>

<div>

## <a name="identify-network-links"></a><span data-ttu-id="b11e9-167">Identificare i collegamenti di rete</span><span class="sxs-lookup"><span data-stu-id="b11e9-167">Identify Network Links</span></span>

<span data-ttu-id="b11e9-p111">I collegamenti di rete rappresentano connessioni alla rete WAN fisica che collega i vari siti e aree. Nell'esempio di topologia utilizzato in questo argomento esistono due collegamenti di rete tra aree, cinque collegamenti di rete tra aree e siti e un collegamento di rete tra due siti.</span><span class="sxs-lookup"><span data-stu-id="b11e9-p111">Network links represent connections to the physical WAN that links different regions and sites. In our example topology, there are two regional network links, five network links between regions and sites, and one network link between two sites.</span></span>

<span data-ttu-id="b11e9-170">I due collegamenti tra aree sono tra l'area Nord America ed EMEA, rappresentato come COLLEGAMENTO-NA-EMEA e tra APAC ed EMEA, rappresentato come COLLEGAMENTO-EMEA-APAC.</span><span class="sxs-lookup"><span data-stu-id="b11e9-170">The two regional links are between North America and EMEA, represented as NA-EMEA-LINK, and between APAC and EMEA, represented as EMEA-APAC-LINK.</span></span>

<span data-ttu-id="b11e9-p112">I collegamenti tra siti sono indicati dalle linee che connettono Portland, Reno e Albuquerque all'area Nord America, Manila all'area APAC e Colonia all'area EMEA. La linea tra Reno e Albuquerque mostra un collegamento di rete diretto tra questi due siti.</span><span class="sxs-lookup"><span data-stu-id="b11e9-p112">The site links are indicated by the lines connecting Portland, Reno, and Albuquerque to the North America region, Manila to the APAC region, and Cologne to the EMEA region. The line between Reno and Albuquerque shows a direct network link between these two sites.</span></span>

</div>

<div>

## <a name="define-bandwidth-policies"></a><span data-ttu-id="b11e9-173">Definire criteri di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="b11e9-173">Define Bandwidth Policies</span></span>

<span data-ttu-id="b11e9-p113">Collaborare con il team responsabile delle operazioni di rete per stabilire la quantità di larghezza di banda WAN disponibile per il traffico audio e video in tempo reale sui collegamenti WAN dell'organizzazione. I criteri di larghezza di banda vengono in genere applicati ai collegamenti WAN se l'uso della larghezza di banda è vincolato, ovvero se è previsto che sia superiore alla larghezza di banda disponibile per l'allocazione alle modalità audio e video.</span><span class="sxs-lookup"><span data-stu-id="b11e9-p113">Work with your network operations team to determine how much WAN bandwidth is available for real-time audio and video traffic across the WAN links in your organization. Bandwidth policies are typically applied to WAN links if the bandwidth usage is constrained; that is, if it expected to be more than the bandwidth that can be allocated for audio and video modalities.</span></span>

<span data-ttu-id="b11e9-p114">I *criteri di larghezza di banda* del servizio Controllo di ammissione di chiamata definiscono la larghezza di banda massima che può essere riservata per le modalità audio e video in tempo reale. Poiché il servizio Controllo di ammissione di chiamata non limita la larghezza di banda di altri tipi di traffico, non può impedire che altri tipi di traffico dati, ad esempio trasferimenti di file di grandi dimensioni o flussi di musica, usino tutta la larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="b11e9-p114">CAC *bandwidth policies* define the maximum bandwidth that can be reserved for real-time audio and video modalities. Since CAC does not limit the bandwidth of other traffic, it cannot prevent other data traffic such as a large file transfer, music streaming, from using up all of the network bandwidth.</span></span>

<span data-ttu-id="b11e9-178">I criteri di larghezza di banda per il controllo di ammissione di chiamata possono definire solo alcuni o tutti gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b11e9-178">CAC bandwidth policies can define any or all of the following:</span></span>

  - <span data-ttu-id="b11e9-179">Larghezza di banda totale massima allocata per i contenuti audio.</span><span class="sxs-lookup"><span data-stu-id="b11e9-179">Maximum total bandwidth allocated for audio.</span></span>

  - <span data-ttu-id="b11e9-180">Larghezza di banda totale massima allocata per i contenuti video.</span><span class="sxs-lookup"><span data-stu-id="b11e9-180">Maximum total bandwidth allocated for video.</span></span>

  - <span data-ttu-id="b11e9-181">Larghezza di banda massima allocata per una singola chiamata (sessione) audio.</span><span class="sxs-lookup"><span data-stu-id="b11e9-181">Maximum bandwidth allocated for a single audio call (session).</span></span>

  - <span data-ttu-id="b11e9-182">Larghezza di banda massima allocata per una singola chiamata (sessione) video.</span><span class="sxs-lookup"><span data-stu-id="b11e9-182">Maximum bandwidth allocated for a single video call (session).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b11e9-183">Tutti i valori di larghezza di banda per il controllo di ammissione di chiamata rappresentano i limiti di larghezza di banda <EM>unidirezionale</EM> massimi.</span><span class="sxs-lookup"><span data-stu-id="b11e9-183">All CAC bandwidth values represent the maximum <EM>unidirectional</EM> bandwidth limits.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b11e9-184">Le caratteristiche dei criteri vocali di Lync Server 2013 offrono la possibilità di ignorare i controlli dei criteri di larghezza di banda per le chiamate in arrivo all'utente (non per le chiamate in uscita inserite dall'utente).</span><span class="sxs-lookup"><span data-stu-id="b11e9-184">The Lync Server 2013 Voice Policy features provide the ability to override bandwidth policy checks for incoming calls to the user (not for outgoing calls that are placed by the user).</span></span> <span data-ttu-id="b11e9-185">Dopo l'attivazione della sessione, il consumo di larghezza di banda verrà conteggiato accuratamente.</span><span class="sxs-lookup"><span data-stu-id="b11e9-185">After the session is established, the bandwidth consumption will be accurately accounted for.</span></span> <span data-ttu-id="b11e9-186">Questa impostazione dovrebbe essere usata raramente.</span><span class="sxs-lookup"><span data-stu-id="b11e9-186">This setting should be used sparingly.</span></span> <span data-ttu-id="b11e9-187">Per informazioni dettagliate, vedere <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">creare un criterio vocale e configurare i record di utilizzo PSTN in Lync server 2013</A> o <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">modificare un criterio vocale e configurare i record di utilizzo PSTN in Lync Server 2013</A> nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b11e9-187">For details, see <A href="lync-server-2013-create-a-voice-policy-and-configure-pstn-usage-records.md">Create a voice policy and configure PSTN usage records in Lync Server 2013</A> or <A href="lync-server-2013-modify-a-voice-policy-and-configure-pstn-usage-records.md">Modify a voice policy and configure PSTN usage records in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<span data-ttu-id="b11e9-p116">Per ottimizzare l'uso della larghezza di banda su base per utente, tenere conto del tipo dei codec audio e video che verranno usati. In particolare, evitare di allocare una quantità di larghezza di banda insufficiente per un codec con uso previsto frequente. Viceversa, se si desidera impedire l'uso di un codec che richiede maggiore larghezza di banda, è consigliabile impostare la larghezza di banda massima per sessione su un valore sufficientemente basso da scoraggiarne l'uso. Per quando riguarda i contenuti audio, non tutti i codec sono disponibili per qualsiasi scenario. Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="b11e9-p116">To optimize bandwidth utilization on a per-session basis, consider the type of audio and video codecs that will be used. In particular, avoid allocating insufficient bandwidth for a codec that you expect to be used frequently. Conversely, if you want to prevent media from using a codec that requires more bandwidth, you should set the maximum bandwidth per session low enough to discourage such use. For audio, not every codec is available for every scenario. For example:</span></span>

  - <span data-ttu-id="b11e9-193">Le chiamate audio peer-to-peer tra gli endpoint di Lync utilizzeranno RTAudio (8kHz) o RTAudio (16kHz) quando si determina la larghezza di banda e la priorità dei codec.</span><span class="sxs-lookup"><span data-stu-id="b11e9-193">Peer-to-peer audio calls between Lync endpoints will use either RTAudio (8kHz) or RTAudio (16kHz) when you factor in the bandwidth and prioritization of codecs.</span></span>

  - <span data-ttu-id="b11e9-194">Le chiamate in conferenza tra gli endpoint di Lync e il servizio A/V Conferencing utilizzeranno G. 722 o Siren.</span><span class="sxs-lookup"><span data-stu-id="b11e9-194">Conference calls between Lync endpoints and the A/V Conferencing service will use either G.722 or Siren.</span></span>

  - <span data-ttu-id="b11e9-195">Le chiamate alla rete PSTN (Public Switched Telephone Network) da o verso endpoint di Lync utilizzeranno G. 711 o RTAudio (8kHz).</span><span class="sxs-lookup"><span data-stu-id="b11e9-195">Calls to the public switched telephone network (PSTN) either to or from Lync endpoints will use either G.711 or RTAudio (8kHz).</span></span>

<span data-ttu-id="b11e9-196">Fare riferimento alla tabella seguente per l'ottimizzazione delle impostazioni di larghezza di banda massima per sessione.</span><span class="sxs-lookup"><span data-stu-id="b11e9-196">Use the following table to help optimize the maximum per-session bandwidth settings.</span></span>

### <a name="bandwidth-utilization-by-codecs"></a><span data-ttu-id="b11e9-197">Utilizzo della larghezza di banda in base ai codec</span><span class="sxs-lookup"><span data-stu-id="b11e9-197">Bandwidth utilization by codecs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b11e9-198">Codec</span><span class="sxs-lookup"><span data-stu-id="b11e9-198">Codec</span></span></th>
<th><span data-ttu-id="b11e9-199">Requisito di larghezza di banda senza correzione FEC (Forward Error Correction)</span><span class="sxs-lookup"><span data-stu-id="b11e9-199">Bandwidth requirement with no forward error correction (FEC)</span></span></th>
<th><span data-ttu-id="b11e9-200">Requisito di larghezza di banda con correzione FEC (Forward Error Correction)</span><span class="sxs-lookup"><span data-stu-id="b11e9-200">Bandwidth requirement with forward error correction (FEC)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b11e9-201">RTAudio (8kHz)</span><span class="sxs-lookup"><span data-stu-id="b11e9-201">RTAudio (8kHz)</span></span></p></td>
<td><p><span data-ttu-id="b11e9-202">49,8 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-202">49.8 kbps</span></span></p></td>
<td><p><span data-ttu-id="b11e9-203">61,6 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-203">61.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b11e9-204">RTAudio (16kHz)</span><span class="sxs-lookup"><span data-stu-id="b11e9-204">RTAudio (16kHz)</span></span></p></td>
<td><p><span data-ttu-id="b11e9-205">67 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-205">67 kbps</span></span></p></td>
<td><p><span data-ttu-id="b11e9-206">96 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-206">96 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b11e9-207">Sirena</span><span class="sxs-lookup"><span data-stu-id="b11e9-207">Siren</span></span></p></td>
<td><p><span data-ttu-id="b11e9-208">57,6 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-208">57.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="b11e9-209">73,6 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-209">73.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b11e9-210">G. 711</span><span class="sxs-lookup"><span data-stu-id="b11e9-210">G.711</span></span></p></td>
<td><p><span data-ttu-id="b11e9-211">102 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-211">102 kbps</span></span></p></td>
<td><p><span data-ttu-id="b11e9-212">166 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-212">166 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b11e9-213">G. 722</span><span class="sxs-lookup"><span data-stu-id="b11e9-213">G.722</span></span></p></td>
<td><p><span data-ttu-id="b11e9-214">105,6 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-214">105.6 kbps</span></span></p></td>
<td><p><span data-ttu-id="b11e9-215">169,6 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-215">169.6 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b11e9-216">RTVideo (CIF 15 fps)</span><span class="sxs-lookup"><span data-stu-id="b11e9-216">RTVideo (CIF 15 fps)</span></span></p></td>
<td><p><span data-ttu-id="b11e9-217">260 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-217">260 kbps</span></span></p></td>
<td><p><span data-ttu-id="b11e9-218">Non applicabile</span><span class="sxs-lookup"><span data-stu-id="b11e9-218">Not applicable</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b11e9-219">RTVideo (VGA 30 fps)</span><span class="sxs-lookup"><span data-stu-id="b11e9-219">RTVideo (VGA 30 fps)</span></span></p></td>
<td><p><span data-ttu-id="b11e9-220">610 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-220">610 kbps</span></span></p></td>
<td><p><span data-ttu-id="b11e9-221">NA</span><span class="sxs-lookup"><span data-stu-id="b11e9-221">Not applicable</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="b11e9-p117">I requisiti di larghezza di banda tengono conto dell'overhead per Ethernet II, IP, UDP (User Datagram Protocol), RTP (Real-time Transport Protocol) e SRTP (Secure Real-time Transport Protocol), oltre a includere 10 kbps per l'overhead RTCP.</span><span class="sxs-lookup"><span data-stu-id="b11e9-p117">Bandwidth requirements take into account overhead for the following: Ethernet II, IP, User Datagram Protocol (UDP), RTP (real-time transport protocol), and SRTP (secure real-time transport protocol). They also include 10 kbps for RTCP overhead.</span></span>



</div>

<span data-ttu-id="b11e9-224">I codec G.722.1 e Siren sono simili, ma offrono velocità in bit diverse.</span><span class="sxs-lookup"><span data-stu-id="b11e9-224">The G.722.1 and Siren codecs are similar, but they offer different bit rates.</span></span>

<span data-ttu-id="b11e9-225">G. 722, il codec predefinito per le conferenze di Lync Server, è completamente diverso dai codec G. 722.1 e Siren.</span><span class="sxs-lookup"><span data-stu-id="b11e9-225">G.722, the default codec for Lync Server conferencing, is completely different from the G.722.1 and Siren codecs.</span></span>

<span data-ttu-id="b11e9-226">Il codec Siren viene utilizzato in Lync Server nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="b11e9-226">The Siren codec is used in Lync Server in the following situations:</span></span>

  - <span data-ttu-id="b11e9-227">Se i criteri di larghezza di banda sono impostati su un valore troppo basso per l'uso di G.722</span><span class="sxs-lookup"><span data-stu-id="b11e9-227">If the bandwidth policy is set too low for G.722 to be used.</span></span>

  - <span data-ttu-id="b11e9-228">Se un client Communications Server 2007 o Communications Server 2007 R2 si connette a un servizio Lync Server Conferencing (poiché tali client non supportano il codec G. 722).</span><span class="sxs-lookup"><span data-stu-id="b11e9-228">If a Communications Server 2007 or Communications Server 2007 R2 client connects to a Lync Server conferencing service (because those clients do not support the G.722 codec).</span></span>

### <a name="bandwidth-utilization-by-scenario"></a><span data-ttu-id="b11e9-229">Utilizzo della larghezza di banda in base allo scenario</span><span class="sxs-lookup"><span data-stu-id="b11e9-229">Bandwidth utilization by scenario</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b11e9-230">Scenario</span><span class="sxs-lookup"><span data-stu-id="b11e9-230">Scenario</span></span></th>
<th><span data-ttu-id="b11e9-231">Requisito di larghezza di banda ottimizzata per la quantità (kbps)</span><span class="sxs-lookup"><span data-stu-id="b11e9-231">Bandwidth requirement optimized for quantity (kbps)</span></span></th>
<th><span data-ttu-id="b11e9-232">Requisito di larghezza di banda per la modalità con bilanciamento (kbps)</span><span class="sxs-lookup"><span data-stu-id="b11e9-232">Bandwidth requirement for Balanced mode (kbps)</span></span></th>
<th><span data-ttu-id="b11e9-233">Requisito di larghezza di banda ottimizzata per la qualità (kbps)</span><span class="sxs-lookup"><span data-stu-id="b11e9-233">Bandwidth requirement optimized for quality (kbps)</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b11e9-234">Chiamate audio peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b11e9-234">Peer-to-peer audio calls</span></span></p></td>
<td><p><span data-ttu-id="b11e9-235">45 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-235">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="b11e9-236">62 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-236">62 kbps</span></span></p></td>
<td><p><span data-ttu-id="b11e9-237">91 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-237">91 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b11e9-238">Conferenze telefoniche</span><span class="sxs-lookup"><span data-stu-id="b11e9-238">Conference calls</span></span></p></td>
<td><p><span data-ttu-id="b11e9-239">53 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-239">53 kbps</span></span></p></td>
<td><p><span data-ttu-id="b11e9-240">101 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-240">101 kbps</span></span></p></td>
<td><p><span data-ttu-id="b11e9-241">165 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-241">165 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b11e9-242">Chiamate PSTN (tra Lync 2013 e il gateway PSTN, con il bypass multimediale)</span><span class="sxs-lookup"><span data-stu-id="b11e9-242">PSTN calls (between Lync 2013 and PSTN gateway, with media bypass)</span></span></p></td>
<td><p><span data-ttu-id="b11e9-243">97 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-243">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="b11e9-244">97 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-244">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="b11e9-245">161 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-245">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b11e9-246">Chiamate PSTN (tra Lync 2013 e Mediation Server, senza bypass multimediale)</span><span class="sxs-lookup"><span data-stu-id="b11e9-246">PSTN calls (between Lync 2013 and Mediation Server, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="b11e9-247">45 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-247">45 kbps</span></span></p></td>
<td><p><span data-ttu-id="b11e9-248">97 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-248">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="b11e9-249">161 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-249">161 kbps</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b11e9-250">Chiamate PSTN (tra Mediation Server e gateway PSTN, senza bypass multimediale)</span><span class="sxs-lookup"><span data-stu-id="b11e9-250">PSTN calls (between Mediation Server and PSTN gateway, without media bypass)</span></span></p></td>
<td><p><span data-ttu-id="b11e9-251">97 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-251">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="b11e9-252">97 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-252">97 kbps</span></span></p></td>
<td><p><span data-ttu-id="b11e9-253">161 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-253">161 kbps</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b11e9-254">Chiamate di Lync-Polycom</span><span class="sxs-lookup"><span data-stu-id="b11e9-254">Lync - Polycom calls</span></span></p></td>
<td><p><span data-ttu-id="b11e9-255">101 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-255">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="b11e9-256">101 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-256">101 Kbps</span></span></p></td>
<td><p><span data-ttu-id="b11e9-257">101 kbps</span><span class="sxs-lookup"><span data-stu-id="b11e9-257">101 Kbps</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="identify-ip-subnets"></a><span data-ttu-id="b11e9-258">Identificare le subnet IP</span><span class="sxs-lookup"><span data-stu-id="b11e9-258">Identify IP Subnets</span></span>

<span data-ttu-id="b11e9-p118">Per ogni sito di rete sarà necessario collaborare con l'amministratore della rete per stabilire quali subnet IP sono assegnate a ogni sito di rete. Se l'amministratore della rete ha già organizzato le subnet IP in aree di rete e siti di rete, il lavoro risulterà notevolmente semplificato.</span><span class="sxs-lookup"><span data-stu-id="b11e9-p118">For each network site, you will need to work with your network administrator to determine what IP subnets are assigned to each network site. If your network administrator has already organized the IP subnets into network regions and network sites, then your work is significantly simplified.</span></span>

<span data-ttu-id="b11e9-p119">In questo esempio, al sito New York nell'area Nord America sono assegnate le subnet IP seguenti: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Si supponga che Bob, che di solito lavora a Detroit, si sposti nell'ufficio di New York per un corso di formazione. Quando accende il suo computer e si connette alla rete, al computer verrà assegnato un indirizzo IP in uno dei quattro intervalli prenotati per New York, ad esempio 172.29.80.103.</span><span class="sxs-lookup"><span data-stu-id="b11e9-p119">In our example, the New York site in the North America region is assigned the following IP subnets: 172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24. Suppose Bob, who typically works in Detroit, travels to the New York office for training. When he turns on his computer and connects to the network, his computer will get an IP address in one of the four ranges reserved for New York, for example 172.29.80.103.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="b11e9-264">Le subnet IP specificate durante la configurazione della rete nel server devono corrispondere al formato specificato dai computer client per poter essere utilizzate correttamente per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="b11e9-264">The IP subnets specified during network configuration on the server must match the format provided by client computers in order to be properly used for media bypass.</span></span> <span data-ttu-id="b11e9-265">Un client Lync prende l'indirizzo IP locale e maschera l'indirizzo IP con la subnet mask associata.</span><span class="sxs-lookup"><span data-stu-id="b11e9-265">A Lync client takes its local IP address and masks the IP address with the associated subnet mask.</span></span> <span data-ttu-id="b11e9-266">Durante la determinazione dell'ID di bypass associato a ogni client, la funzione di registrazione confronterà l'elenco delle subnet IP associate a ogni sito di rete con la subnet fornita dal client per individuare una corrispondenza esatta.</span><span class="sxs-lookup"><span data-stu-id="b11e9-266">When determining the bypass ID associated with each client, the Registrar will compare the list of IP subnets associated with each network site against the subnet provided by the client for an exact match.</span></span> <span data-ttu-id="b11e9-267">Per questo motivo è importante che le subnet immesse durante la configurazione della rete nel server siano subnet effettive, anziché virtuali.</span><span class="sxs-lookup"><span data-stu-id="b11e9-267">For this reason, it is important that subnets entered during network configuration on the server are actual subnets instead of virtual subnets.</span></span> <span data-ttu-id="b11e9-268">Se si implementa il servizio Controllo di ammissione di chiamata ma non Media Bypass, il servizio Controllo di ammissione di chiamata funzionerà in modo corretto anche se si configurano subnet virtuali.</span><span class="sxs-lookup"><span data-stu-id="b11e9-268">(If you deploy call admission control, but not media bypass, call admission control will function properly even if you configure virtual subnets.)</span></span><BR><span data-ttu-id="b11e9-269">Ad esempio, se un client accede a un computer con un indirizzo IP di 172.29.81.57 con una subnet mask IP 255.255.255.0, Lync 2013 richiederà l'ID di bypass associato a subnet 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="b11e9-269">For example, if a client signs in on a computer with an IP address of 172.29.81.57 with an IP subnet mask of 255.255.255.0, Lync 2013 will request the bypass ID associated with subnet 172.29.81.0.</span></span> <span data-ttu-id="b11e9-270">Se la subnet è definita come 172.29.0.0/16, anche se il client appartiene alla subnet virtuale, la funzione di registrazione non la considererà una corrispondenza esatta perché cerca nello specifico la subnet 172.29.81.0.</span><span class="sxs-lookup"><span data-stu-id="b11e9-270">If the subnet is defined as 172.29.0.0/16, although the client belongs to the virtual subnet, the Registrar will not consider this a match because the Registrar is specifically looking for subnet 172.29.81.0.</span></span> <span data-ttu-id="b11e9-271">Pertanto, è importante che l'amministratore entri nelle subnet esattamente come indicato dai client Lync (che vengono provisionati con subnet durante la configurazione di rete in modo statico o tramite DHCP).</span><span class="sxs-lookup"><span data-stu-id="b11e9-271">Therefore, it is important that the administrator enters subnets exactly as provided by Lync clients (which are provisioned with subnets during network configuration either statically or by DHCP.)</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

