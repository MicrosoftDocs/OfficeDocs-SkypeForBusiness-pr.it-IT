---
title: Esempio di raccolta dei requisiti per il controllo dell'ammissione alle chiamate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Example of gathering your requirements for call admission control
ms:assetid: 3363ac53-b7c4-4a59-aea1-b2f3ee016ae1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425827(v=OCS.15)
ms:contentKeyID: 48183820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 345f5d7e41dd9da3e6d68c59ce9656d3052c57b5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="22258-102">Esempio: raccogliere i requisiti per il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="22258-102">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="22258-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="22258-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="22258-104">Questo esempio illustra come pianificare e implementare il controllo di ammissione di chiamata (CAC).</span><span class="sxs-lookup"><span data-stu-id="22258-104">This example shows you how to plan for and implement call admission control (CAC).</span></span> <span data-ttu-id="22258-105">Ad alto livello, è costituito dalle attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="22258-105">At a high level, this consists of the following activities:</span></span>

1.  <span data-ttu-id="22258-106">Identificare tutti gli hub di rete e le dorsali (note come *aree di rete*).</span><span class="sxs-lookup"><span data-stu-id="22258-106">Identify all of your network hubs and backbones (known as *network regions*).</span></span>

2.  <span data-ttu-id="22258-107">Identificare il sito centrale di Lync Server che gestirà CAC per ogni area di rete.</span><span class="sxs-lookup"><span data-stu-id="22258-107">Identify the Lync Server central site that will manage CAC for each network region.</span></span>

3.  <span data-ttu-id="22258-108">Identificare e definire i *siti di rete* connessi a ogni area di rete.</span><span class="sxs-lookup"><span data-stu-id="22258-108">Identify and define the *network sites* that are connected to each network region.</span></span>

4.  <span data-ttu-id="22258-109">Per ogni sito di rete la cui connessione alla WAN è vincolata da larghezza di banda, descrivere la capacità di larghezza di banda della connessione WAN e i limiti di larghezza di banda che l'amministratore di rete ha impostato per il traffico multimediale di Lync Server, se applicabile.</span><span class="sxs-lookup"><span data-stu-id="22258-109">For each network site whose connection to the WAN is bandwidth-constrained, describe the bandwidth capacity of the WAN connection and the bandwidth limits that to the network administrator has set for Lync Server media traffic, if applicable.</span></span> <span data-ttu-id="22258-110">Non è necessario includere siti la cui connessione alla rete WAN non è vincolata da larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="22258-110">You do not need to include sites whose connection to the WAN is not bandwidth-constrained.</span></span>

5.  <span data-ttu-id="22258-111">Associare ogni subnet della rete a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="22258-111">Associate each subnet in your network with a network site.</span></span>

6.  <span data-ttu-id="22258-112">Mappare i collegamenti tra le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="22258-112">Map the links between the network regions.</span></span> <span data-ttu-id="22258-113">Per ogni collegamento, Descrivi la sua capacità di larghezza di banda e i limiti che l'amministratore di rete ha inserito nel traffico multimediale di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22258-113">For each link, describe its bandwidth capacity and any limits that the network administrator has placed on Lync Server media traffic.</span></span>

7.  <span data-ttu-id="22258-114">Definire una route tra ogni coppia di aree di rete.</span><span class="sxs-lookup"><span data-stu-id="22258-114">Define a route between every pair of network regions.</span></span>

<div>

## <a name="gather-the-required-information"></a><span data-ttu-id="22258-115">Raccogliere le informazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="22258-115">Gather the Required Information</span></span>

<span data-ttu-id="22258-116">Per preparare il controllo di ammissione alle chiamate, raccogliere le informazioni descritte nei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="22258-116">To prepare for call admission control, gather the information described in the following steps:</span></span>

1.  <span data-ttu-id="22258-117">Identificare le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="22258-117">Identify your network regions.</span></span> <span data-ttu-id="22258-118">Un'area di rete rappresenta un backbone di rete o un hub di rete.</span><span class="sxs-lookup"><span data-stu-id="22258-118">A network region represents a network backbone or a network hub.</span></span>
    
    <span data-ttu-id="22258-119">Un backbone di rete o un hub di rete fa parte dell'infrastruttura di rete di computer che interconnette vari elementi di rete, fornendo un percorso per lo scambio di informazioni tra LAN o subnet diverse.</span><span class="sxs-lookup"><span data-stu-id="22258-119">A network backbone or a network hub is a part of computer network infrastructure that interconnects various pieces of network, providing a path for the exchange of information between different LANs or subnets.</span></span> <span data-ttu-id="22258-120">Una backbone può legare insieme diverse reti, da una piccola posizione a un'area geografica ampia.</span><span class="sxs-lookup"><span data-stu-id="22258-120">A backbone can tie together diverse networks, from a small location to a wide geographic area.</span></span> <span data-ttu-id="22258-121">La capacità della colonna vertebrale è in genere maggiore rispetto a quella delle reti connesse.</span><span class="sxs-lookup"><span data-stu-id="22258-121">The backbone's capacity is typically greater than that of the networks connected to it.</span></span>
    
    <span data-ttu-id="22258-122">La topologia di esempio include tre aree di rete: Nord America, EMEA e APAC.</span><span class="sxs-lookup"><span data-stu-id="22258-122">Our example topology has three network regions: North America, EMEA, and APAC.</span></span> <span data-ttu-id="22258-123">Un'area di rete contiene una raccolta di siti di rete.</span><span class="sxs-lookup"><span data-stu-id="22258-123">A network region contains a collection of network sites.</span></span> <span data-ttu-id="22258-124">Collaborare con l'amministratore di rete per definire le aree di rete per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="22258-124">Work with your network administrator to define the network regions for your enterprise.</span></span>

2.  <span data-ttu-id="22258-125">Identificare il sito centrale associato di ogni area di rete.</span><span class="sxs-lookup"><span data-stu-id="22258-125">Identify each network region’s associated central site.</span></span> <span data-ttu-id="22258-126">Un sito centrale contiene almeno un server front-end ed è la distribuzione di Lync Server che gestirà CAC per tutto il traffico multimediale che passa attraverso la connessione WAN dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="22258-126">A central site contains at least one Front End Server and is the Lync Server deployment that will manage CAC for all media traffic that passes through the network region’s WAN connection.</span></span>
    
    <span data-ttu-id="22258-127">**Esempio di rete aziendale divisa in tre aree di rete**</span><span class="sxs-lookup"><span data-stu-id="22258-127">**An example enterprise network divided into three network regions**</span></span>
    
    <span data-ttu-id="22258-128">![Esempio di topologia di rete con tre aree di rete](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Esempio di topologia di rete con tre aree di rete")</span><span class="sxs-lookup"><span data-stu-id="22258-128">![Network Topology Example with 3 Network Regions](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Network Topology Example with 3 Network Regions")</span></span>  
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="22258-129">Una rete MPLS (Multiprotocol Label Switching) deve essere rappresentata come area di rete in cui ogni posizione geografica contiene un sito di rete corrispondente.</span><span class="sxs-lookup"><span data-stu-id="22258-129">A Multiprotocol Label Switching (MPLS) network should be represented as a network region in which each geographic location has a corresponding network site.</span></span> <span data-ttu-id="22258-130">Per informazioni dettagliate, vedere l'argomento "<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">controllo ammissione chiamata in rete MPLS con Lync Server 2013</A>" nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="22258-130">For details, see the “<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Call admission control on an MPLS network with Lync Server 2013</A>” topic in the Planning documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="22258-131">Nella topologia di rete di esempio precedente sono presenti tre aree di rete, ognuna con un sito centrale di Lync Server che gestisce CAC.</span><span class="sxs-lookup"><span data-stu-id="22258-131">In the preceding example network topology, there are three network regions, each with a Lync Server central site that manages CAC.</span></span> <span data-ttu-id="22258-132">Il sito centrale appropriato per un'area geografica di rete viene scelto dalle vicinanze geografiche.</span><span class="sxs-lookup"><span data-stu-id="22258-132">The appropriate central site for a network region is chosen by the geographic vicinity.</span></span> <span data-ttu-id="22258-133">Poiché il traffico multimediale sarà più pesante nelle aree di rete, la proprietà per le vicinanze geografiche lo rende autonomo e continuerà a essere funzionante anche se altri siti centrali diventano non disponibili.</span><span class="sxs-lookup"><span data-stu-id="22258-133">Because media traffic will be heaviest within network regions, the ownership by geographic vicinity makes it self-contained and will continue to be functional even if other central sites become unavailable.</span></span>
    
    <span data-ttu-id="22258-134">In questo esempio, una distribuzione di Lync Server denominata Chicago è il sito centrale per l'area Nord America.</span><span class="sxs-lookup"><span data-stu-id="22258-134">In this example, a Lync Server deployment named Chicago is the central site for the North America region.</span></span>
    
    <span data-ttu-id="22258-135">Tutti gli utenti di Lync in Nord America vengono ospitati nei server della distribuzione di Chicago.</span><span class="sxs-lookup"><span data-stu-id="22258-135">All Lync users in North America are homed on servers in the Chicago deployment.</span></span> <span data-ttu-id="22258-136">La tabella seguente mostra i siti centrali per tutte e tre le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="22258-136">The following table shows central sites for all three network regions.</span></span>
    
    ### <a name="network-regions-and-their-associated-central-sites"></a><span data-ttu-id="22258-137">Aree di rete e relativi siti centrali associati</span><span class="sxs-lookup"><span data-stu-id="22258-137">Network Regions and their Associated Central Sites</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="22258-138">Area di rete</span><span class="sxs-lookup"><span data-stu-id="22258-138">Network Region</span></span></th>
    <th><span data-ttu-id="22258-139">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="22258-139">Central Site</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="22258-140">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-140">North America</span></span></p></td>
    <td><p><span data-ttu-id="22258-141">Chicago</span><span class="sxs-lookup"><span data-stu-id="22258-141">Chicago</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="22258-142">EMEA</span><span class="sxs-lookup"><span data-stu-id="22258-142">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="22258-143">Londra</span><span class="sxs-lookup"><span data-stu-id="22258-143">London</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="22258-144">APAC</span><span class="sxs-lookup"><span data-stu-id="22258-144">APAC</span></span></p></td>
    <td><p><span data-ttu-id="22258-145">Pechino</span><span class="sxs-lookup"><span data-stu-id="22258-145">Beijing</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="22258-146">A seconda della topologia di Lync Server, è possibile assegnare lo stesso sito centrale a più aree di rete.</span><span class="sxs-lookup"><span data-stu-id="22258-146">Depending on your Lync Server topology, the same central site can be assigned to multiple network regions.</span></span>

    
    </div>

3.  <span data-ttu-id="22258-147">Per ogni area geografica di rete, identificare tutti i siti di rete (uffici o posizioni) le cui connessioni WAN non sono vincolate da larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="22258-147">For each network region, identify all of the network sites (offices or locations) whose WAN connections are not bandwidth-constrained.</span></span> <span data-ttu-id="22258-148">Poiché questi siti non sono vincolati alla larghezza di banda, non è necessario applicare i criteri di larghezza di banda CAC.</span><span class="sxs-lookup"><span data-stu-id="22258-148">Because these sites are not bandwidth constrained, you do not need to apply CAC bandwidth policies to them.</span></span>
    
    <span data-ttu-id="22258-149">Nell'esempio illustrato nella tabella seguente tre siti di rete non dispongono di collegamenti WAN con larghezza di banda limitata: New York, Chicago e Detroit.</span><span class="sxs-lookup"><span data-stu-id="22258-149">In the example shown in the following table, three network sites do not have bandwidth-constrained WAN links: New York, Chicago, and Detroit.</span></span>
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a><span data-ttu-id="22258-150">Siti di rete non vincolati dalla larghezza di banda WAN</span><span class="sxs-lookup"><span data-stu-id="22258-150">Network Sites not Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="22258-151">Sito di rete</span><span class="sxs-lookup"><span data-stu-id="22258-151">Network Site</span></span></th>
    <th><span data-ttu-id="22258-152">Area di rete</span><span class="sxs-lookup"><span data-stu-id="22258-152">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="22258-153">New York</span><span class="sxs-lookup"><span data-stu-id="22258-153">New York</span></span></p></td>
    <td><p><span data-ttu-id="22258-154">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-154">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="22258-155">Chicago</span><span class="sxs-lookup"><span data-stu-id="22258-155">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="22258-156">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-156">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="22258-157">Detroit</span><span class="sxs-lookup"><span data-stu-id="22258-157">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="22258-158">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-158">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>


4.  <span data-ttu-id="22258-159">Per ogni area geografica di rete, identificare tutti i siti di rete che si connettono all'area di rete tramite collegamenti WAN con larghezza di banda limitata.</span><span class="sxs-lookup"><span data-stu-id="22258-159">For each network region, identify all of the network sites that connect to the network region through bandwidth-constrained WAN links.</span></span>
    
    <span data-ttu-id="22258-160">Per garantire la qualità audio e video, è consigliabile che i siti di rete con vincoli di larghezza di banda dispongano delle WAN monitorate e dei criteri di larghezza di banda CAC che limitano il flusso di traffico multimediale (vocale o video) da e verso l'area di rete.</span><span class="sxs-lookup"><span data-stu-id="22258-160">To help ensure audio and video quality, we recommend that these bandwidth-constrained network sites have their WANs monitored and CAC bandwidth policies that limit media (voice or video) traffic flow to and from the network region.</span></span>
    
    <span data-ttu-id="22258-161">Nell'esempio illustrato nella tabella seguente sono disponibili tre siti di rete vincolati da larghezza di banda WAN: Portland, Reno e Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="22258-161">In the example shown in the following table, there are three network sites that are constrained by WAN bandwidth: Portland, Reno and Albuquerque.</span></span>
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a><span data-ttu-id="22258-162">Siti di rete vincolati da larghezza di banda WAN</span><span class="sxs-lookup"><span data-stu-id="22258-162">Network Sites Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="22258-163">Sito di rete</span><span class="sxs-lookup"><span data-stu-id="22258-163">Network Site</span></span></th>
    <th><span data-ttu-id="22258-164">Area di rete</span><span class="sxs-lookup"><span data-stu-id="22258-164">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="22258-165">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="22258-165">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="22258-166">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-166">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="22258-167">Reno</span><span class="sxs-lookup"><span data-stu-id="22258-167">Reno</span></span></p></td>
    <td><p><span data-ttu-id="22258-168">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-168">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="22258-169">Portland</span><span class="sxs-lookup"><span data-stu-id="22258-169">Portland</span></span></p></td>
    <td><p><span data-ttu-id="22258-170">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-170">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="22258-171">**Area di rete CAC Nord America con tre siti di rete non vincolati per larghezza di banda (Chicago, New York e Detroit) e tre siti di rete vincolati dalla larghezza di banda WAN (Portland, Reno e Albuquerque)**</span><span class="sxs-lookup"><span data-stu-id="22258-171">**CAC network region North America with three network sites that are unconstrained by bandwidth (Chicago, New York, and Detroit) and three network sites that are constrained by WAN bandwidth (Portland, Reno, and Albuquerque)**</span></span>
    
    <span data-ttu-id="22258-172">![Siti di rete di esempio vincolati dalla larghezza di banda WAN](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Siti di rete di esempio vincolati dalla larghezza di banda WAN")</span><span class="sxs-lookup"><span data-stu-id="22258-172">![Example network sites constrained by WAN bandwidth](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Example network sites constrained by WAN bandwidth")</span></span>  

5.  <span data-ttu-id="22258-173">Per ogni collegamento WAN con larghezza di banda limitata, determinare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="22258-173">For each bandwidth-constrained WAN link, determine the following:</span></span>
    
      - <span data-ttu-id="22258-174">Limite di larghezza di banda complessivo che si vuole impostare per tutte le sessioni audio simultanee.</span><span class="sxs-lookup"><span data-stu-id="22258-174">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="22258-175">Se una nuova sessione audio causa il superamento di questo limite, Lync Server non consente l'avvio della sessione.</span><span class="sxs-lookup"><span data-stu-id="22258-175">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="22258-176">Limite di larghezza di banda che si vuole impostare per ogni singola sessione audio.</span><span class="sxs-lookup"><span data-stu-id="22258-176">Bandwidth limit that you want to set for each individual audio session.</span></span> <span data-ttu-id="22258-177">Il limite di larghezza di banda predefinito di CAC è di 175 kbps, ma può essere modificato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="22258-177">The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="22258-178">Limite di larghezza di banda complessivo che si vuole impostare per tutte le sessioni video simultanee.</span><span class="sxs-lookup"><span data-stu-id="22258-178">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="22258-179">Se una nuova sessione video causerà il superamento di questo limite, Lync Server non consente l'avvio della sessione.</span><span class="sxs-lookup"><span data-stu-id="22258-179">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="22258-180">Limite di larghezza di banda che si vuole impostare per ogni singola sessione video.</span><span class="sxs-lookup"><span data-stu-id="22258-180">Bandwidth limit that you want to set for each individual video session.</span></span> <span data-ttu-id="22258-181">Il limite di larghezza di banda predefinito di CAC è di 700 Kbps, ma può essere modificato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="22258-181">The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a><span data-ttu-id="22258-182">Siti di rete con informazioni sui vincoli di larghezza di banda WAN (larghezza di banda in Kbps)</span><span class="sxs-lookup"><span data-stu-id="22258-182">Network Sites with WAN Bandwidth Constraint Information (Bandwidth in kbps)</span></span>
    
    <table style="width:100%;">
    <colgroup>
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    <col style="width: 14%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="22258-183">Sito di rete</span><span class="sxs-lookup"><span data-stu-id="22258-183">Network Site</span></span></th>
    <th><span data-ttu-id="22258-184">Area di rete</span><span class="sxs-lookup"><span data-stu-id="22258-184">Network Region</span></span></th>
    <th><span data-ttu-id="22258-185">Limite di BW</span><span class="sxs-lookup"><span data-stu-id="22258-185">BW Limit</span></span></th>
    <th><span data-ttu-id="22258-186">Limite audio</span><span class="sxs-lookup"><span data-stu-id="22258-186">Audio Limit</span></span></th>
    <th><span data-ttu-id="22258-187">Limite della sessione audio</span><span class="sxs-lookup"><span data-stu-id="22258-187">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="22258-188">Limite video</span><span class="sxs-lookup"><span data-stu-id="22258-188">Video Limit</span></span></th>
    <th><span data-ttu-id="22258-189">Limite di sessione video</span><span class="sxs-lookup"><span data-stu-id="22258-189">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="22258-190">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="22258-190">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="22258-191">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-191">North America</span></span></p></td>
    <td><p><span data-ttu-id="22258-192">5.000</span><span class="sxs-lookup"><span data-stu-id="22258-192">5,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-193">2.000</span><span class="sxs-lookup"><span data-stu-id="22258-193">2,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-194">175</span><span class="sxs-lookup"><span data-stu-id="22258-194">175</span></span></p></td>
    <td><p><span data-ttu-id="22258-195">1.400</span><span class="sxs-lookup"><span data-stu-id="22258-195">1,400</span></span></p></td>
    <td><p><span data-ttu-id="22258-196">700</span><span class="sxs-lookup"><span data-stu-id="22258-196">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="22258-197">Reno</span><span class="sxs-lookup"><span data-stu-id="22258-197">Reno</span></span></p></td>
    <td><p><span data-ttu-id="22258-198">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-198">North America</span></span></p></td>
    <td><p><span data-ttu-id="22258-199">10.000</span><span class="sxs-lookup"><span data-stu-id="22258-199">10,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-200">4.000</span><span class="sxs-lookup"><span data-stu-id="22258-200">4,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-201">175</span><span class="sxs-lookup"><span data-stu-id="22258-201">175</span></span></p></td>
    <td><p><span data-ttu-id="22258-202">2.800</span><span class="sxs-lookup"><span data-stu-id="22258-202">2,800</span></span></p></td>
    <td><p><span data-ttu-id="22258-203">700</span><span class="sxs-lookup"><span data-stu-id="22258-203">700</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="22258-204">Portland</span><span class="sxs-lookup"><span data-stu-id="22258-204">Portland</span></span></p></td>
    <td><p><span data-ttu-id="22258-205">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-205">North America</span></span></p></td>
    <td><p><span data-ttu-id="22258-206">5.000</span><span class="sxs-lookup"><span data-stu-id="22258-206">5,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-207">4.000</span><span class="sxs-lookup"><span data-stu-id="22258-207">4,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-208">175</span><span class="sxs-lookup"><span data-stu-id="22258-208">175</span></span></p></td>
    <td><p><span data-ttu-id="22258-209">2.800</span><span class="sxs-lookup"><span data-stu-id="22258-209">2,800</span></span></p></td>
    <td><p><span data-ttu-id="22258-210">700</span><span class="sxs-lookup"><span data-stu-id="22258-210">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="22258-211">New York</span><span class="sxs-lookup"><span data-stu-id="22258-211">New York</span></span></p></td>
    <td><p><span data-ttu-id="22258-212">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-212">North America</span></span></p></td>
    <td><p><span data-ttu-id="22258-213">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-213">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-214">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-214">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-215">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-215">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-216">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-216">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-217">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-217">(no limit)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="22258-218">Chicago</span><span class="sxs-lookup"><span data-stu-id="22258-218">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="22258-219">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-219">North America</span></span></p></td>
    <td><p><span data-ttu-id="22258-220">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-220">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-221">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-221">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-222">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-222">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-223">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-223">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-224">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-224">(no limit)</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="22258-225">Detroit</span><span class="sxs-lookup"><span data-stu-id="22258-225">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="22258-226">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-226">North America</span></span></p></td>
    <td><p><span data-ttu-id="22258-227">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-227">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-228">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-228">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-229">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-229">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-230">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-230">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-231">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-231">(no limit)</span></span></p></td>
    </tr>
    </tbody>
    </table>


6.  <span data-ttu-id="22258-232">Per ogni subnet della rete, specificare il sito di rete associato.</span><span class="sxs-lookup"><span data-stu-id="22258-232">For every subnet in your network, specify its associated network site.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="22258-233">Ogni subnet della rete deve essere associata a un sito di rete, anche se il sito di rete non è vincolato alla larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="22258-233">Every subnet in your network must be associated with a network site, even if the network site is not bandwidth constrained.</span></span> <span data-ttu-id="22258-234">Questo perché il controllo di ammissione delle chiamate usa le informazioni sulla subnet per determinare in quale sito di rete si trova un endpoint.</span><span class="sxs-lookup"><span data-stu-id="22258-234">This is because call admission control uses subnet information to determine at which network site an endpoint is located.</span></span> <span data-ttu-id="22258-235">Quando vengono determinate le posizioni di entrambe le parti della sessione, il controllo di ammissione delle chiamate può determinare se è disponibile una larghezza di banda sufficiente per stabilire una chiamata.</span><span class="sxs-lookup"><span data-stu-id="22258-235">When the locations of both parties in the session are determined, call admission control can determine if there is sufficient bandwidth to establish a call.</span></span> <span data-ttu-id="22258-236">Quando viene stabilita una sessione su un collegamento che non contiene limiti di larghezza di banda, viene generato un avviso.</span><span class="sxs-lookup"><span data-stu-id="22258-236">When a session is established over a link that has no bandwidth limits, an alert is generated.</span></span><BR><span data-ttu-id="22258-237">Se si distribuiscono server Edge audio/video, gli indirizzi IP pubblici di ogni Edge Server devono essere associati al sito di rete in cui è distribuito il server perimetrale.</span><span class="sxs-lookup"><span data-stu-id="22258-237">If you deploy Audio/Video Edge Servers, the public IP addresses of each Edge Server must be associated with the network site where the Edge Server is deployed.</span></span> <span data-ttu-id="22258-238">Ogni indirizzo IP pubblico di un/V Edge Server deve essere aggiunto alle impostazioni di configurazione della rete come subnet con una subnet mask di 32.</span><span class="sxs-lookup"><span data-stu-id="22258-238">Each public IP address of the A/V Edge Server must be added to your network configuration settings as a subnet with a subnet mask of 32.</span></span> <span data-ttu-id="22258-239">Ad esempio, se si distribuisce un/V Edge Server a Chicago, per ogni indirizzo IP esterno di questi server è possibile creare una subnet con una subnet mask di 32 e associare il sito di rete a Chicago con tali subnet.</span><span class="sxs-lookup"><span data-stu-id="22258-239">For example, if you deploy A/V Edge Servers in Chicago, then for each external IP address of those servers create a subnet with a subnet mask of 32 and associate network site Chicago with those subnets.</span></span> <span data-ttu-id="22258-240">Per informazioni dettagliate sugli indirizzi IP pubblici, vedere <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">determinare i requisiti per il firewall e la porta a/V esterni per Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="22258-240">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="22258-241">Viene generato un avviso KHI (Key Health Indicator), che specifica un elenco di indirizzi IP presenti nella rete, ma che non sono associati a una subnet oppure che la subnet che include gli indirizzi IP non è associata a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="22258-241">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site.</span></span> <span data-ttu-id="22258-242">Questo avviso non verrà generato più di una volta entro un periodo di 8 ore.</span><span class="sxs-lookup"><span data-stu-id="22258-242">This alert will not be raised more than once within an 8 hour period.</span></span> <span data-ttu-id="22258-243">Di seguito sono riportate le informazioni relative agli avvisi e un esempio:</span><span class="sxs-lookup"><span data-stu-id="22258-243">The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="22258-244"><STRONG>Origine:</STRONG> Servizio di criteri di larghezza di banda CS (Core)</span><span class="sxs-lookup"><span data-stu-id="22258-244"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="22258-245"><STRONG>Numero evento:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="22258-245"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="22258-246"><STRONG>Livello:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="22258-246"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="22258-247"><STRONG>Descrizione:</STRONG> Le subnet per gli indirizzi IP seguenti: &lt;l'elenco di indirizzi&gt; IP non è configurato o le subnet non sono associate a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="22258-247"><STRONG>Description:</STRONG> The subnets for the following IP Addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="22258-248"><STRONG>Causa:</STRONG> Le subnet per gli indirizzi IP corrispondenti sono mancanti nelle impostazioni di configurazione della rete o le subnet non sono associate a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="22258-248"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="22258-249"><STRONG>Risoluzione:</STRONG> Aggiungere subnet che corrispondono all'elenco precedente di indirizzi IP nelle impostazioni di configurazione della rete e associare ogni subnet a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="22258-249"><STRONG>Resolution:</STRONG> Add subnets corresponding to the preceding list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="22258-250">Ad esempio, se l'elenco di indirizzi IP nell'avviso specifica 10.121.248.226 e 10.121.249.20, questi indirizzi IP non sono associati a una subnet o la subnet a cui sono associati non appartiene a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="22258-250">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet, or the subnet that they are associated with does not belong to a network site.</span></span> <span data-ttu-id="22258-251">Se 10.121.248.0/24 e 10.121.249.0/24 sono le subnet corrispondenti per questi indirizzi, è possibile risolvere il problema come segue:</span><span class="sxs-lookup"><span data-stu-id="22258-251">If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="22258-252">Assicurarsi che l'indirizzo IP 10.121.248.226 sia associato alla subnet 10.121.248.0/24 e l'indirizzo IP 10.121.249.20 sia associato alla subnet 10.121.249.0/24.</span><span class="sxs-lookup"><span data-stu-id="22258-252">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="22258-253">Assicurarsi che le subnet 10.121.248.0/24 e 10.121.249.0/24 siano associate a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="22258-253">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a><span data-ttu-id="22258-254">Siti di rete e subnet associate (larghezza di banda in Kbps)</span><span class="sxs-lookup"><span data-stu-id="22258-254">Network Sites and Associated Subnets (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="22258-255">Sito di rete</span><span class="sxs-lookup"><span data-stu-id="22258-255">Network Site</span></span></th>
    <th><span data-ttu-id="22258-256">Area di rete</span><span class="sxs-lookup"><span data-stu-id="22258-256">Network Region</span></span></th>
    <th><span data-ttu-id="22258-257">Limite di BW</span><span class="sxs-lookup"><span data-stu-id="22258-257">BW Limit</span></span></th>
    <th><span data-ttu-id="22258-258">Limite audio</span><span class="sxs-lookup"><span data-stu-id="22258-258">Audio Limit</span></span></th>
    <th><span data-ttu-id="22258-259">Limite della sessione audio</span><span class="sxs-lookup"><span data-stu-id="22258-259">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="22258-260">Limite video</span><span class="sxs-lookup"><span data-stu-id="22258-260">Video Limit</span></span></th>
    <th><span data-ttu-id="22258-261">Limite di sessione video</span><span class="sxs-lookup"><span data-stu-id="22258-261">Video Session Limit</span></span></th>
    <th><span data-ttu-id="22258-262">Subnet</span><span class="sxs-lookup"><span data-stu-id="22258-262">Subnets</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="22258-263">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="22258-263">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="22258-264">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-264">North America</span></span></p></td>
    <td><p><span data-ttu-id="22258-265">5.000</span><span class="sxs-lookup"><span data-stu-id="22258-265">5,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-266">2.000</span><span class="sxs-lookup"><span data-stu-id="22258-266">2,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-267">175</span><span class="sxs-lookup"><span data-stu-id="22258-267">175</span></span></p></td>
    <td><p><span data-ttu-id="22258-268">1.400</span><span class="sxs-lookup"><span data-stu-id="22258-268">1,400</span></span></p></td>
    <td><p><span data-ttu-id="22258-269">700</span><span class="sxs-lookup"><span data-stu-id="22258-269">700</span></span></p></td>
    <td><p><span data-ttu-id="22258-270">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span><span class="sxs-lookup"><span data-stu-id="22258-270">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="22258-271">Reno</span><span class="sxs-lookup"><span data-stu-id="22258-271">Reno</span></span></p></td>
    <td><p><span data-ttu-id="22258-272">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-272">North America</span></span></p></td>
    <td><p><span data-ttu-id="22258-273">10.000</span><span class="sxs-lookup"><span data-stu-id="22258-273">10,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-274">4.000</span><span class="sxs-lookup"><span data-stu-id="22258-274">4,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-275">175</span><span class="sxs-lookup"><span data-stu-id="22258-275">175</span></span></p></td>
    <td><p><span data-ttu-id="22258-276">2.800</span><span class="sxs-lookup"><span data-stu-id="22258-276">2,800</span></span></p></td>
    <td><p><span data-ttu-id="22258-277">700</span><span class="sxs-lookup"><span data-stu-id="22258-277">700</span></span></p></td>
    <td><p><span data-ttu-id="22258-278">157.57.210.0/23, 172.28.151.128/25</span><span class="sxs-lookup"><span data-stu-id="22258-278">157.57.210.0/23, 172.28.151.128/25</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="22258-279">Portland</span><span class="sxs-lookup"><span data-stu-id="22258-279">Portland</span></span></p></td>
    <td><p><span data-ttu-id="22258-280">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-280">North America</span></span></p></td>
    <td><p><span data-ttu-id="22258-281">5.000</span><span class="sxs-lookup"><span data-stu-id="22258-281">5,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-282">4.000</span><span class="sxs-lookup"><span data-stu-id="22258-282">4,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-283">175</span><span class="sxs-lookup"><span data-stu-id="22258-283">175</span></span></p></td>
    <td><p><span data-ttu-id="22258-284">2.800</span><span class="sxs-lookup"><span data-stu-id="22258-284">2,800</span></span></p></td>
    <td><p><span data-ttu-id="22258-285">700</span><span class="sxs-lookup"><span data-stu-id="22258-285">700</span></span></p></td>
    <td><p><span data-ttu-id="22258-286">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span><span class="sxs-lookup"><span data-stu-id="22258-286">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="22258-287">New York</span><span class="sxs-lookup"><span data-stu-id="22258-287">New York</span></span></p></td>
    <td><p><span data-ttu-id="22258-288">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-288">North America</span></span></p></td>
    <td><p><span data-ttu-id="22258-289">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-289">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-290">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-290">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-291">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-291">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-292">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-292">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-293">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-293">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-294">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span><span class="sxs-lookup"><span data-stu-id="22258-294">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="22258-295">Chicago</span><span class="sxs-lookup"><span data-stu-id="22258-295">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="22258-296">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-296">North America</span></span></p></td>
    <td><p><span data-ttu-id="22258-297">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-297">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-298">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-298">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-299">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-299">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-300">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-300">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-301">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-301">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-302">157.57.211.0/23, 172.28.152.128/25</span><span class="sxs-lookup"><span data-stu-id="22258-302">157.57.211.0/23, 172.28.152.128/25</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="22258-303">Detroit</span><span class="sxs-lookup"><span data-stu-id="22258-303">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="22258-304">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-304">North America</span></span></p></td>
    <td><p><span data-ttu-id="22258-305">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-305">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-306">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-306">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-307">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-307">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-308">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-308">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-309">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="22258-309">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="22258-310">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span><span class="sxs-lookup"><span data-stu-id="22258-310">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span></span></p></td>
    </tr>
    </tbody>
    </table>


7.  <span data-ttu-id="22258-311">Nel controllo di ammissione alle chiamate di Lync Server le connessioni tra le aree di rete sono chiamate *collegamenti di area geografica*.</span><span class="sxs-lookup"><span data-stu-id="22258-311">In Lync Server call admission control, the connections between network regions are called *region links*.</span></span> <span data-ttu-id="22258-312">Per ogni collegamento all'area geografica, determinare quanto segue, come per i siti di rete:</span><span class="sxs-lookup"><span data-stu-id="22258-312">For each region link, determine the following, just as you did for the network sites:</span></span>
    
      - <span data-ttu-id="22258-313">Limite di larghezza di banda complessivo che si vuole impostare per tutte le sessioni audio simultanee.</span><span class="sxs-lookup"><span data-stu-id="22258-313">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="22258-314">Se una nuova sessione audio causa il superamento di questo limite, Lync Server non consente l'avvio della sessione.</span><span class="sxs-lookup"><span data-stu-id="22258-314">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="22258-315">Limite di larghezza di banda che si vuole impostare per ogni singola sessione audio.</span><span class="sxs-lookup"><span data-stu-id="22258-315">Bandwidth limit that you want to set for each individual audio session.</span></span> <span data-ttu-id="22258-316">Il limite di larghezza di banda predefinito di CAC è di 175 kbps, ma può essere modificato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="22258-316">The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="22258-317">Limite di larghezza di banda complessivo che si vuole impostare per tutte le sessioni video simultanee.</span><span class="sxs-lookup"><span data-stu-id="22258-317">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="22258-318">Se una nuova sessione video causerà il superamento di questo limite, Lync Server non consente l'avvio della sessione.</span><span class="sxs-lookup"><span data-stu-id="22258-318">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="22258-319">Limite di larghezza di banda che si vuole impostare per ogni singola sessione video.</span><span class="sxs-lookup"><span data-stu-id="22258-319">Bandwidth limit that you want to set for each individual video session.</span></span> <span data-ttu-id="22258-320">Il limite di larghezza di banda predefinito di CAC è di 700 Kbps, ma può essere modificato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="22258-320">The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="22258-321">**Collegamenti all'area di rete con limiti di larghezza di banda associati**</span><span class="sxs-lookup"><span data-stu-id="22258-321">**Network Region links with associated bandwidth limits**</span></span>
    
    <span data-ttu-id="22258-322">![Esempio di limitazioni fra tre aree](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Esempio di limitazioni fra tre aree")</span><span class="sxs-lookup"><span data-stu-id="22258-322">![Example of Limitations between 3 Regions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Example of Limitations between 3 Regions")</span></span>  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a><span data-ttu-id="22258-323">Informazioni sulla larghezza di banda del collegamento geografica (larghezza di banda in Kbps)</span><span class="sxs-lookup"><span data-stu-id="22258-323">Region Link Bandwidth Information (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="22258-324">Nome collegamento area geografica</span><span class="sxs-lookup"><span data-stu-id="22258-324">Region Link Name</span></span></th>
    <th><span data-ttu-id="22258-325">First Region</span><span class="sxs-lookup"><span data-stu-id="22258-325">First Region</span></span></th>
    <th><span data-ttu-id="22258-326">Second Region</span><span class="sxs-lookup"><span data-stu-id="22258-326">Second Region</span></span></th>
    <th><span data-ttu-id="22258-327">Limite di BW</span><span class="sxs-lookup"><span data-stu-id="22258-327">BW Limit</span></span></th>
    <th><span data-ttu-id="22258-328">Limite audio</span><span class="sxs-lookup"><span data-stu-id="22258-328">Audio Limit</span></span></th>
    <th><span data-ttu-id="22258-329">Limite della sessione audio</span><span class="sxs-lookup"><span data-stu-id="22258-329">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="22258-330">Limite video</span><span class="sxs-lookup"><span data-stu-id="22258-330">Video Limit</span></span></th>
    <th><span data-ttu-id="22258-331">Limite di sessione video</span><span class="sxs-lookup"><span data-stu-id="22258-331">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="22258-332">NA-EMEA-COLLEGAMENTO</span><span class="sxs-lookup"><span data-stu-id="22258-332">NA-EMEA-LINK</span></span></p></td>
    <td><p><span data-ttu-id="22258-333">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-333">North America</span></span></p></td>
    <td><p><span data-ttu-id="22258-334">EMEA</span><span class="sxs-lookup"><span data-stu-id="22258-334">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="22258-335">50.000</span><span class="sxs-lookup"><span data-stu-id="22258-335">50,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-336">20.000</span><span class="sxs-lookup"><span data-stu-id="22258-336">20,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-337">175</span><span class="sxs-lookup"><span data-stu-id="22258-337">175</span></span></p></td>
    <td><p><span data-ttu-id="22258-338">14.000</span><span class="sxs-lookup"><span data-stu-id="22258-338">14,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-339">700</span><span class="sxs-lookup"><span data-stu-id="22258-339">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="22258-340">EMEA-APAC-COLLEGAMENTO</span><span class="sxs-lookup"><span data-stu-id="22258-340">EMEA-APAC-LINK</span></span></p></td>
    <td><p><span data-ttu-id="22258-341">EMEA</span><span class="sxs-lookup"><span data-stu-id="22258-341">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="22258-342">APAC</span><span class="sxs-lookup"><span data-stu-id="22258-342">APAC</span></span></p></td>
    <td><p><span data-ttu-id="22258-343">25.000</span><span class="sxs-lookup"><span data-stu-id="22258-343">25,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-344">10.000</span><span class="sxs-lookup"><span data-stu-id="22258-344">10,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-345">175</span><span class="sxs-lookup"><span data-stu-id="22258-345">175</span></span></p></td>
    <td><p><span data-ttu-id="22258-346">7.000</span><span class="sxs-lookup"><span data-stu-id="22258-346">7,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-347">700</span><span class="sxs-lookup"><span data-stu-id="22258-347">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="22258-348">Definire una route tra ogni coppia di aree di rete.</span><span class="sxs-lookup"><span data-stu-id="22258-348">Define a route between every pair of network regions.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="22258-349">Sono necessari due collegamenti per la route tra il Nord America e le aree APAC perché non è presente un collegamento all'area geografica che li connette direttamente.</span><span class="sxs-lookup"><span data-stu-id="22258-349">Two links are required for the route between the North America and APAC regions because there is no region link that directly connects them.</span></span>

    
    </div>
    
    ### <a name="region-routes"></a><span data-ttu-id="22258-350">Route di area geografica</span><span class="sxs-lookup"><span data-stu-id="22258-350">Region Routes</span></span>
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="22258-351">Nome route dell'area geografica</span><span class="sxs-lookup"><span data-stu-id="22258-351">Region Route Name</span></span></th>
    <th><span data-ttu-id="22258-352">First Region</span><span class="sxs-lookup"><span data-stu-id="22258-352">First Region</span></span></th>
    <th><span data-ttu-id="22258-353">Second Region</span><span class="sxs-lookup"><span data-stu-id="22258-353">Second Region</span></span></th>
    <th><span data-ttu-id="22258-354">Collegamenti all'area geografica</span><span class="sxs-lookup"><span data-stu-id="22258-354">Region Links</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="22258-355">NA-EMEA-ROUTE</span><span class="sxs-lookup"><span data-stu-id="22258-355">NA-EMEA-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="22258-356">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-356">North America</span></span></p></td>
    <td><p><span data-ttu-id="22258-357">EMEA</span><span class="sxs-lookup"><span data-stu-id="22258-357">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="22258-358">NA-EMEA-COLLEGAMENTO</span><span class="sxs-lookup"><span data-stu-id="22258-358">NA-EMEA-LINK</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="22258-359">EMEA-APAC-ROUTE</span><span class="sxs-lookup"><span data-stu-id="22258-359">EMEA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="22258-360">EMEA</span><span class="sxs-lookup"><span data-stu-id="22258-360">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="22258-361">APAC</span><span class="sxs-lookup"><span data-stu-id="22258-361">APAC</span></span></p></td>
    <td><p><span data-ttu-id="22258-362">EMEA-APAC-COLLEGAMENTO</span><span class="sxs-lookup"><span data-stu-id="22258-362">EMEA-APAC-LINK</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="22258-363">NA-APAC-ROUTE</span><span class="sxs-lookup"><span data-stu-id="22258-363">NA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="22258-364">America del Nord</span><span class="sxs-lookup"><span data-stu-id="22258-364">North America</span></span></p></td>
    <td><p><span data-ttu-id="22258-365">APAC</span><span class="sxs-lookup"><span data-stu-id="22258-365">APAC</span></span></p></td>
    <td><p><span data-ttu-id="22258-366">NA-EMEA-LINK, EMEA-APAC-LINK</span><span class="sxs-lookup"><span data-stu-id="22258-366">NA-EMEA-LINK, EMEA-APAC-LINK</span></span></p></td>
    </tr>
    </tbody>
    </table>


9.  <span data-ttu-id="22258-367">Per ogni coppia di siti di rete collegati direttamente da un singolo collegamento (denominato collegamento *tra siti* ), determinare le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="22258-367">For every pair of network sites that are directly connected by a single link (called an *inter-site* link), determine the following:</span></span>
    
      - <span data-ttu-id="22258-368">Limite di larghezza di banda complessivo che si vuole impostare per tutte le sessioni audio simultanee.</span><span class="sxs-lookup"><span data-stu-id="22258-368">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="22258-369">Se una nuova sessione audio causa il superamento di questo limite, Lync Server non consente l'avvio della sessione.</span><span class="sxs-lookup"><span data-stu-id="22258-369">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="22258-370">Limite di larghezza di banda che si vuole impostare per ogni singola sessione audio.</span><span class="sxs-lookup"><span data-stu-id="22258-370">Bandwidth limit that you want to set for each individual audio session.</span></span> <span data-ttu-id="22258-371">Il limite di larghezza di banda predefinito di CAC è di 175 kbps, ma può essere modificato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="22258-371">The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="22258-372">Limite di larghezza di banda complessivo che si vuole impostare per tutte le sessioni video simultanee.</span><span class="sxs-lookup"><span data-stu-id="22258-372">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="22258-373">Se una nuova sessione video causerà il superamento di questo limite, Lync Server non consente l'avvio della sessione.</span><span class="sxs-lookup"><span data-stu-id="22258-373">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="22258-374">Limite di larghezza di banda che si vuole impostare per ogni singola sessione video.</span><span class="sxs-lookup"><span data-stu-id="22258-374">Bandwidth limit that you want to set for each individual video session.</span></span> <span data-ttu-id="22258-375">Il limite di larghezza di banda predefinito di CAC è di 700 Kbps, ma può essere modificato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="22258-375">The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="22258-376">**Area di rete CAC Nord America che mostra le capacità di larghezza di banda e i limiti di larghezza di banda per il collegamento tra siti tra Reno e Albuquerque**</span><span class="sxs-lookup"><span data-stu-id="22258-376">**CAC network region North America showing the bandwidth capacities and bandwidth limits for the inter-site link between Reno and Albuquerque**</span></span>
    
    <span data-ttu-id="22258-377">![Esempio di siti di rete vincolati dalla larghezza di banda WAN](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Esempio di siti di rete vincolati dalla larghezza di banda WAN")</span><span class="sxs-lookup"><span data-stu-id="22258-377">![Network Sites Constrained by WAN Bandwidth example](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Network Sites Constrained by WAN Bandwidth example")</span></span>  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a><span data-ttu-id="22258-378">Informazioni sulla larghezza di banda per un collegamento intersito tra due siti di rete (larghezza di banda in Kbps)</span><span class="sxs-lookup"><span data-stu-id="22258-378">Bandwidth Information for an Inter-Site Link between Two Network Sites (Bandwidth in kbps)</span></span>
    
    <table>
    <colgroup>
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    <col style="width: 12%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="22258-379">Nome collegamento tra siti</span><span class="sxs-lookup"><span data-stu-id="22258-379">Inter-Site Link Name</span></span></th>
    <th><span data-ttu-id="22258-380">Primo sito</span><span class="sxs-lookup"><span data-stu-id="22258-380">First Site</span></span></th>
    <th><span data-ttu-id="22258-381">Secondo sito</span><span class="sxs-lookup"><span data-stu-id="22258-381">Second Site</span></span></th>
    <th><span data-ttu-id="22258-382">Limite di BW</span><span class="sxs-lookup"><span data-stu-id="22258-382">BW Limit</span></span></th>
    <th><span data-ttu-id="22258-383">Limite audio</span><span class="sxs-lookup"><span data-stu-id="22258-383">Audio Limit</span></span></th>
    <th><span data-ttu-id="22258-384">Limite della sessione audio</span><span class="sxs-lookup"><span data-stu-id="22258-384">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="22258-385">Limite video</span><span class="sxs-lookup"><span data-stu-id="22258-385">Video Limit</span></span></th>
    <th><span data-ttu-id="22258-386">Limite di sessione video</span><span class="sxs-lookup"><span data-stu-id="22258-386">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="22258-387">Reno-albu-collegamento intersito</span><span class="sxs-lookup"><span data-stu-id="22258-387">Reno-Albu-Intersite-Link</span></span></p></td>
    <td><p><span data-ttu-id="22258-388">Reno</span><span class="sxs-lookup"><span data-stu-id="22258-388">Reno</span></span></p></td>
    <td><p><span data-ttu-id="22258-389">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="22258-389">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="22258-390">20.000</span><span class="sxs-lookup"><span data-stu-id="22258-390">20,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-391">12.000</span><span class="sxs-lookup"><span data-stu-id="22258-391">12,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-392">175</span><span class="sxs-lookup"><span data-stu-id="22258-392">175</span></span></p></td>
    <td><p><span data-ttu-id="22258-393">5.000</span><span class="sxs-lookup"><span data-stu-id="22258-393">5,000</span></span></p></td>
    <td><p><span data-ttu-id="22258-394">700</span><span class="sxs-lookup"><span data-stu-id="22258-394">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a><span data-ttu-id="22258-395">Operazioni successive</span><span class="sxs-lookup"><span data-stu-id="22258-395">Next Steps</span></span>

<span data-ttu-id="22258-396">Dopo aver raccolto le informazioni necessarie, è possibile eseguire la distribuzione di CAC usando il pannello di controllo di Lync Server Management Shell o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="22258-396">After you have gathered the required information, you can perform CAC deployment either by using the Lync Server Management Shell or Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="22258-397">Anche se è possibile eseguire la maggior parte delle attività di configurazione della rete tramite il pannello di controllo di Lync Server, per creare subnet e collegamenti intersito, è necessario usare Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="22258-397">Although you can perform most network configuration tasks by using Lync Server Control Panel, to create subnets and intersite links, you must use Lync Server Management Shell.</span></span> <span data-ttu-id="22258-398">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell per il cmdlet <STRONG>New-CsNetworkSubnet</STRONG> e il cmdlet <STRONG>New-CsNetworkIntersitePolicy</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="22258-398">For details, see the Lync Server Management Shell documentation for the <STRONG>New-CsNetworkSubnet</STRONG> cmdlet and the <STRONG>New-CsNetworkIntersitePolicy</STRONG> cmdlet.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

