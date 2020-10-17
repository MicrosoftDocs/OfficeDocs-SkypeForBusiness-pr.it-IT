---
title: Esempio di raccolta dei requisiti per il controllo di ammissione di chiamata
description: Esempio di raccolta dei requisiti per il controllo di ammissione di chiamata.
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
ms.openlocfilehash: 25c0b450070bda62c2610d98cfff8c8cd16ad2af
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48564942"
---
# <a name="example-gathering-your-requirements-for-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="5e905-103">Esempio: raccolta dei requisiti per il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5e905-103">Example: Gathering your requirements for call admission control in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5e905-104">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="5e905-104">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="5e905-p101">In questo esempio viene illustrato come pianificare e implementare il servizio Controllo di ammissione di chiamata (CAC). A livello generale, sono previste le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e905-p101">This example shows you how to plan for and implement call admission control (CAC). At a high level, this consists of the following activities:</span></span>

1.  <span data-ttu-id="5e905-107">Identificare tutti gli hub e le backbone di rete (note come *aree di rete*).</span><span class="sxs-lookup"><span data-stu-id="5e905-107">Identify all of your network hubs and backbones (known as *network regions*).</span></span>

2.  <span data-ttu-id="5e905-108">Identificare il sito centrale di Lync Server che gestirà il servizio di controllo di ammissione per ogni area di rete.</span><span class="sxs-lookup"><span data-stu-id="5e905-108">Identify the Lync Server central site that will manage CAC for each network region.</span></span>

3.  <span data-ttu-id="5e905-109">Identificare e definire i *siti di rete* connessi a ogni area di rete.</span><span class="sxs-lookup"><span data-stu-id="5e905-109">Identify and define the *network sites* that are connected to each network region.</span></span>

4.  <span data-ttu-id="5e905-110">Per ogni sito di rete la cui connessione alla WAN è vincolata dalla larghezza di banda, descrivere la capacità della larghezza di banda della connessione WAN e i limiti di larghezza di banda che l'amministratore di rete ha impostato per il traffico multimediale di Lync Server, se applicabile.</span><span class="sxs-lookup"><span data-stu-id="5e905-110">For each network site whose connection to the WAN is bandwidth-constrained, describe the bandwidth capacity of the WAN connection and the bandwidth limits that to the network administrator has set for Lync Server media traffic, if applicable.</span></span> <span data-ttu-id="5e905-111">Non è necessario includere siti con connessione alla WAN non soggetta a vincoli di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="5e905-111">You do not need to include sites whose connection to the WAN is not bandwidth-constrained.</span></span>

5.  <span data-ttu-id="5e905-112">Associare ogni subnet della rete a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="5e905-112">Associate each subnet in your network with a network site.</span></span>

6.  <span data-ttu-id="5e905-113">Eseguire il mapping dei collegamenti tra le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="5e905-113">Map the links between the network regions.</span></span> <span data-ttu-id="5e905-114">Per ogni collegamento, descrivere la capacità della larghezza di banda e gli eventuali limiti imposti dall'amministratore di rete sul traffico multimediale di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5e905-114">For each link, describe its bandwidth capacity and any limits that the network administrator has placed on Lync Server media traffic.</span></span>

7.  <span data-ttu-id="5e905-115">Definire una route tra ogni coppia di aree di rete.</span><span class="sxs-lookup"><span data-stu-id="5e905-115">Define a route between every pair of network regions.</span></span>

<div>

## <a name="gather-the-required-information"></a><span data-ttu-id="5e905-116">Raccogliere le informazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="5e905-116">Gather the Required Information</span></span>

<span data-ttu-id="5e905-117">Per la preparazione per il servizio Controllo di ammissione di chiamata, raccogliere le informazioni descritte nei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e905-117">To prepare for call admission control, gather the information described in the following steps:</span></span>

1.  <span data-ttu-id="5e905-p104">Identificare le aree di rete. Un'area di rete rappresenta una backbone o un hub di rete.</span><span class="sxs-lookup"><span data-stu-id="5e905-p104">Identify your network regions. A network region represents a network backbone or a network hub.</span></span>
    
    <span data-ttu-id="5e905-p105">Una backbone o un hub di rete è una parte dell'infrastruttura della rete del computer che interconnette diverse parti della rete, fornendo un percorso per lo scambio di informazioni tra diverse LAN o subnet. Una backbone può unire reti diverse, da una piccola postazione a un'area geografica estesa. La capacità della backbone è in genere superiore a quella delle reti a essa connesse.</span><span class="sxs-lookup"><span data-stu-id="5e905-p105">A network backbone or a network hub is a part of computer network infrastructure that interconnects various pieces of network, providing a path for the exchange of information between different LANs or subnets. A backbone can tie together diverse networks, from a small location to a wide geographic area. The backbone's capacity is typically greater than that of the networks connected to it.</span></span>
    
    <span data-ttu-id="5e905-p106">Nella topologia di esempio sono presenti tre aree di rete: Nord America, EMEA e APAC. In un'area di rete è contenuto un insieme di siti di rete. Consultarsi con l'amministratore di rete per definire le aree di rete dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5e905-p106">Our example topology has three network regions: North America, EMEA, and APAC. A network region contains a collection of network sites. Work with your network administrator to define the network regions for your enterprise.</span></span>

2.  <span data-ttu-id="5e905-126">Identificare il sito centrale associato a ogni area di rete.</span><span class="sxs-lookup"><span data-stu-id="5e905-126">Identify each network region’s associated central site.</span></span> <span data-ttu-id="5e905-127">Un sito centrale contiene almeno un front end server ed è la distribuzione di Lync Server che gestirà il servizio di controllo di accesso per tutto il traffico multimediale che passa attraverso la connessione WAN dell'area di rete.</span><span class="sxs-lookup"><span data-stu-id="5e905-127">A central site contains at least one Front End Server and is the Lync Server deployment that will manage CAC for all media traffic that passes through the network region’s WAN connection.</span></span>
    
    <span data-ttu-id="5e905-128">**Rete aziendale di esempio divisa in tre aree di rete**</span><span class="sxs-lookup"><span data-stu-id="5e905-128">**An example enterprise network divided into three network regions**</span></span>
    
    <span data-ttu-id="5e905-129">![Esempio di topologia di rete con tre aree di rete](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Esempio di topologia di rete con tre aree di rete")</span><span class="sxs-lookup"><span data-stu-id="5e905-129">![Network Topology Example with 3 Network Regions](images/Gg425827.08937347-250f-488f-ba5f-c256e6afcd8b(OCS.15).jpg "Network Topology Example with 3 Network Regions")</span></span>  
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="5e905-130">Una rete Multiprotocol Label Switching (MPLS) dovrebbe essere rappresentata come area di rete in cui a ogni posizione geografica corrisponde un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="5e905-130">A Multiprotocol Label Switching (MPLS) network should be represented as a network region in which each geographic location has a corresponding network site.</span></span> <span data-ttu-id="5e905-131">Per ulteriori informazioni, vedere l'argomento "<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">controllo di ammissione di chiamata su una rete MPLS con Lync Server 2013</A>" nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="5e905-131">For details, see the “<A href="lync-server-2013-call-admission-control-on-an-mpls-network.md">Call admission control on an MPLS network with Lync Server 2013</A>” topic in the Planning documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="5e905-132">Nella topologia di rete di esempio precedente esistono tre aree di rete, ognuna con un sito centrale di Lync Server che gestisce il servizio di controllo di ammissione.</span><span class="sxs-lookup"><span data-stu-id="5e905-132">In the preceding example network topology, there are three network regions, each with a Lync Server central site that manages CAC.</span></span> <span data-ttu-id="5e905-133">Il sito centrale appropriato per un'area di rete viene scelto in base alla vicinanza geografica.</span><span class="sxs-lookup"><span data-stu-id="5e905-133">The appropriate central site for a network region is chosen by the geographic vicinity.</span></span> <span data-ttu-id="5e905-134">Poiché il traffico multimediale sarà più intenso all'interno delle aree di rete, la proprietà per vicinanza geografica rende il traffico autonomo e ne garantisce il funzionamento anche in caso di non disponibilità degli altri siti centrali.</span><span class="sxs-lookup"><span data-stu-id="5e905-134">Because media traffic will be heaviest within network regions, the ownership by geographic vicinity makes it self-contained and will continue to be functional even if other central sites become unavailable.</span></span>
    
    <span data-ttu-id="5e905-135">In questo esempio, una distribuzione di Lync Server denominata Chicago è il sito centrale per l'area Nord America.</span><span class="sxs-lookup"><span data-stu-id="5e905-135">In this example, a Lync Server deployment named Chicago is the central site for the North America region.</span></span>
    
    <span data-ttu-id="5e905-136">Tutti gli utenti di Lync nel Nord America sono ospitati nei server della distribuzione di Chicago.</span><span class="sxs-lookup"><span data-stu-id="5e905-136">All Lync users in North America are homed on servers in the Chicago deployment.</span></span> <span data-ttu-id="5e905-137">Nella tabella seguente sono elencati i siti centrali per tutte e tre le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="5e905-137">The following table shows central sites for all three network regions.</span></span>
    
    ### <a name="network-regions-and-their-associated-central-sites"></a><span data-ttu-id="5e905-138">Aree di rete e siti centrali associati</span><span class="sxs-lookup"><span data-stu-id="5e905-138">Network Regions and their Associated Central Sites</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="5e905-139">Area di rete</span><span class="sxs-lookup"><span data-stu-id="5e905-139">Network Region</span></span></th>
    <th><span data-ttu-id="5e905-140">Sito centrale</span><span class="sxs-lookup"><span data-stu-id="5e905-140">Central Site</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="5e905-141">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-141">North America</span></span></p></td>
    <td><p><span data-ttu-id="5e905-142">Chicago</span><span class="sxs-lookup"><span data-stu-id="5e905-142">Chicago</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5e905-143">EMEA</span><span class="sxs-lookup"><span data-stu-id="5e905-143">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="5e905-144">Londra</span><span class="sxs-lookup"><span data-stu-id="5e905-144">London</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5e905-145">APAC</span><span class="sxs-lookup"><span data-stu-id="5e905-145">APAC</span></span></p></td>
    <td><p><span data-ttu-id="5e905-146">Pechino</span><span class="sxs-lookup"><span data-stu-id="5e905-146">Beijing</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="5e905-147">A seconda della topologia di Lync Server, lo stesso sito centrale può essere assegnato a più aree di rete.</span><span class="sxs-lookup"><span data-stu-id="5e905-147">Depending on your Lync Server topology, the same central site can be assigned to multiple network regions.</span></span>

    
    </div>

3.  <span data-ttu-id="5e905-p111">Per ogni area di rete, identificare tutti i siti di rete (uffici o postazioni) le cui connessioni WAN non siano vincolate dalla larghezza di banda. Poiché questi siti non sono vincolati dalla larghezza di banda, non è necessario applicare criteri di larghezza di banda del servizio Controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="5e905-p111">For each network region, identify all of the network sites (offices or locations) whose WAN connections are not bandwidth-constrained. Because these sites are not bandwidth constrained, you do not need to apply CAC bandwidth policies to them.</span></span>
    
    <span data-ttu-id="5e905-150">Nell'esempio illustrato nella tabella seguente tre siti di rete non dispongono di collegamenti WAN con vincoli di larghezza di banda: New York, Chicago e Detroit.</span><span class="sxs-lookup"><span data-stu-id="5e905-150">In the example shown in the following table, three network sites do not have bandwidth-constrained WAN links: New York, Chicago, and Detroit.</span></span>
    
    ### <a name="network-sites-not-constrained-by-wan-bandwidth"></a><span data-ttu-id="5e905-151">Siti di rete non vincolati dalla larghezza di banda della WAN</span><span class="sxs-lookup"><span data-stu-id="5e905-151">Network Sites not Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="5e905-152">Sito di rete</span><span class="sxs-lookup"><span data-stu-id="5e905-152">Network Site</span></span></th>
    <th><span data-ttu-id="5e905-153">Area di rete</span><span class="sxs-lookup"><span data-stu-id="5e905-153">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="5e905-154">New York</span><span class="sxs-lookup"><span data-stu-id="5e905-154">New York</span></span></p></td>
    <td><p><span data-ttu-id="5e905-155">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-155">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5e905-156">Chicago</span><span class="sxs-lookup"><span data-stu-id="5e905-156">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="5e905-157">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-157">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5e905-158">Detroit</span><span class="sxs-lookup"><span data-stu-id="5e905-158">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="5e905-159">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-159">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>


4.  <span data-ttu-id="5e905-160">Per ogni area di rete identificare tutti i siti di rete che si connettono all'area di rete mediante collegamenti WAN con vincoli di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="5e905-160">For each network region, identify all of the network sites that connect to the network region through bandwidth-constrained WAN links.</span></span>
    
    <span data-ttu-id="5e905-161">Per garantire la qualità audio e video, è consigliabile fare in modo che le WAN dei siti di rete con vincoli di larghezza di banda siano monitorate e applicare criteri di larghezza di banda del servizio Controllo di ammissione di chiamata che limitino il flusso del traffico multimediale (vocale o video) scambiato con l'area di rete.</span><span class="sxs-lookup"><span data-stu-id="5e905-161">To help ensure audio and video quality, we recommend that these bandwidth-constrained network sites have their WANs monitored and CAC bandwidth policies that limit media (voice or video) traffic flow to and from the network region.</span></span>
    
    <span data-ttu-id="5e905-162">Nell'esempio illustrato nella tabella seguente sono presenti tre siti di rete vincolati dalla larghezza di banda della WAN: Portland, Reno e Albuquerque.</span><span class="sxs-lookup"><span data-stu-id="5e905-162">In the example shown in the following table, there are three network sites that are constrained by WAN bandwidth: Portland, Reno and Albuquerque.</span></span>
    
    ### <a name="network-sites-constrained-by-wan-bandwidth"></a><span data-ttu-id="5e905-163">Siti di rete vincolati dalla larghezza di banda della WAN</span><span class="sxs-lookup"><span data-stu-id="5e905-163">Network Sites Constrained by WAN Bandwidth</span></span>
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="5e905-164">Sito di rete</span><span class="sxs-lookup"><span data-stu-id="5e905-164">Network Site</span></span></th>
    <th><span data-ttu-id="5e905-165">Area di rete</span><span class="sxs-lookup"><span data-stu-id="5e905-165">Network Region</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="5e905-166">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="5e905-166">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="5e905-167">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-167">North America</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5e905-168">Reno</span><span class="sxs-lookup"><span data-stu-id="5e905-168">Reno</span></span></p></td>
    <td><p><span data-ttu-id="5e905-169">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-169">North America</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5e905-170">Portland</span><span class="sxs-lookup"><span data-stu-id="5e905-170">Portland</span></span></p></td>
    <td><p><span data-ttu-id="5e905-171">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-171">North America</span></span></p></td>
    </tr>
    </tbody>
    </table>
    
    <span data-ttu-id="5e905-172">**Area di rete Nord America con servizio Controllo di ammissione di chiamata con tre siti di rete non vincolati dalla larghezza di banda (Chicago, New York e Detroit) e tre siti di rete vincolati dalla larghezza di banda della WAN (Portland, Reno e Albuquerque)**</span><span class="sxs-lookup"><span data-stu-id="5e905-172">**CAC network region North America with three network sites that are unconstrained by bandwidth (Chicago, New York, and Detroit) and three network sites that are constrained by WAN bandwidth (Portland, Reno, and Albuquerque)**</span></span>
    
    <span data-ttu-id="5e905-173">![Siti di rete di esempio vincolati dalla larghezza di banda WAN](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Siti di rete di esempio vincolati dalla larghezza di banda WAN")</span><span class="sxs-lookup"><span data-stu-id="5e905-173">![Example network sites constrained by WAN bandwidth](images/Gg425827.d9d1f231-db4d-4dd7-8fbc-eb0b6d1e705d(OCS.15).jpg "Example network sites constrained by WAN bandwidth")</span></span>  

5.  <span data-ttu-id="5e905-174">Per ogni collegamento WAN con vincoli di larghezza di banda, determinare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5e905-174">For each bandwidth-constrained WAN link, determine the following:</span></span>
    
      - <span data-ttu-id="5e905-175">Limite di larghezza di banda globale che si desidera impostare per tutte le sessioni audio simultanee.</span><span class="sxs-lookup"><span data-stu-id="5e905-175">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="5e905-176">Se una nuova sessione audio provocherà il superamento di questo limite, Lync Server non consentirà di avviare la sessione.</span><span class="sxs-lookup"><span data-stu-id="5e905-176">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="5e905-p113">Limite di larghezza di banda che si desidera impostare per ogni singola sessione audio. Il limite di larghezza di banda predefinito per il servizio Controllo di ammissione di chiamata è 175 kbps, ma può essere modificato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="5e905-p113">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="5e905-179">Limite di larghezza di banda globale che si desidera impostare per tutte le sessioni video simultanee.</span><span class="sxs-lookup"><span data-stu-id="5e905-179">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="5e905-180">Se una nuova sessione video provocherà il superamento di questo limite, Lync Server non consentirà di avviare la sessione.</span><span class="sxs-lookup"><span data-stu-id="5e905-180">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="5e905-p115">Limite di larghezza di banda che si desidera impostare per ogni singola sessione video. Il limite di larghezza di banda predefinito per il servizio Controllo di ammissione di chiamata è 700 kbps, ma può essere modificato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="5e905-p115">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    ### <a name="network-sites-with-wan-bandwidth-constraint-information-bandwidth-in-kbps"></a><span data-ttu-id="5e905-183">Siti di rete con informazioni sui vincoli della larghezza di banda della WAN (larghezza di banda in kbps)</span><span class="sxs-lookup"><span data-stu-id="5e905-183">Network Sites with WAN Bandwidth Constraint Information (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="5e905-184">Sito di rete</span><span class="sxs-lookup"><span data-stu-id="5e905-184">Network Site</span></span></th>
    <th><span data-ttu-id="5e905-185">Area di rete</span><span class="sxs-lookup"><span data-stu-id="5e905-185">Network Region</span></span></th>
    <th><span data-ttu-id="5e905-186">Limite di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="5e905-186">BW Limit</span></span></th>
    <th><span data-ttu-id="5e905-187">Limite audio</span><span class="sxs-lookup"><span data-stu-id="5e905-187">Audio Limit</span></span></th>
    <th><span data-ttu-id="5e905-188">Limite sessione audio</span><span class="sxs-lookup"><span data-stu-id="5e905-188">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="5e905-189">Limite video</span><span class="sxs-lookup"><span data-stu-id="5e905-189">Video Limit</span></span></th>
    <th><span data-ttu-id="5e905-190">Limite sessione video</span><span class="sxs-lookup"><span data-stu-id="5e905-190">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="5e905-191">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="5e905-191">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="5e905-192">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-192">North America</span></span></p></td>
    <td><p><span data-ttu-id="5e905-193">5,000</span><span class="sxs-lookup"><span data-stu-id="5e905-193">5,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-194">2.000</span><span class="sxs-lookup"><span data-stu-id="5e905-194">2,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-195">175</span><span class="sxs-lookup"><span data-stu-id="5e905-195">175</span></span></p></td>
    <td><p><span data-ttu-id="5e905-196">1.400</span><span class="sxs-lookup"><span data-stu-id="5e905-196">1,400</span></span></p></td>
    <td><p><span data-ttu-id="5e905-197">700</span><span class="sxs-lookup"><span data-stu-id="5e905-197">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5e905-198">Reno</span><span class="sxs-lookup"><span data-stu-id="5e905-198">Reno</span></span></p></td>
    <td><p><span data-ttu-id="5e905-199">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-199">North America</span></span></p></td>
    <td><p><span data-ttu-id="5e905-200">10.000</span><span class="sxs-lookup"><span data-stu-id="5e905-200">10,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-201">4.000</span><span class="sxs-lookup"><span data-stu-id="5e905-201">4,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-202">175</span><span class="sxs-lookup"><span data-stu-id="5e905-202">175</span></span></p></td>
    <td><p><span data-ttu-id="5e905-203">2.800</span><span class="sxs-lookup"><span data-stu-id="5e905-203">2,800</span></span></p></td>
    <td><p><span data-ttu-id="5e905-204">700</span><span class="sxs-lookup"><span data-stu-id="5e905-204">700</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5e905-205">Portland</span><span class="sxs-lookup"><span data-stu-id="5e905-205">Portland</span></span></p></td>
    <td><p><span data-ttu-id="5e905-206">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-206">North America</span></span></p></td>
    <td><p><span data-ttu-id="5e905-207">5,000</span><span class="sxs-lookup"><span data-stu-id="5e905-207">5,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-208">4.000</span><span class="sxs-lookup"><span data-stu-id="5e905-208">4,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-209">175</span><span class="sxs-lookup"><span data-stu-id="5e905-209">175</span></span></p></td>
    <td><p><span data-ttu-id="5e905-210">2.800</span><span class="sxs-lookup"><span data-stu-id="5e905-210">2,800</span></span></p></td>
    <td><p><span data-ttu-id="5e905-211">700</span><span class="sxs-lookup"><span data-stu-id="5e905-211">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5e905-212">New York</span><span class="sxs-lookup"><span data-stu-id="5e905-212">New York</span></span></p></td>
    <td><p><span data-ttu-id="5e905-213">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-213">North America</span></span></p></td>
    <td><p><span data-ttu-id="5e905-214">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-214">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-215">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-215">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-216">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-216">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-217">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-217">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-218">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-218">(no limit)</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5e905-219">Chicago</span><span class="sxs-lookup"><span data-stu-id="5e905-219">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="5e905-220">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-220">North America</span></span></p></td>
    <td><p><span data-ttu-id="5e905-221">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-221">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-222">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-222">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-223">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-223">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-224">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-224">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-225">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-225">(no limit)</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5e905-226">Detroit</span><span class="sxs-lookup"><span data-stu-id="5e905-226">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="5e905-227">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-227">North America</span></span></p></td>
    <td><p><span data-ttu-id="5e905-228">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-228">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-229">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-229">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-230">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-230">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-231">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-231">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-232">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-232">(no limit)</span></span></p></td>
    </tr>
    </tbody>
    </table>


6.  <span data-ttu-id="5e905-233">Per ogni subnet della rete, specificare il sito di rete associato.</span><span class="sxs-lookup"><span data-stu-id="5e905-233">For every subnet in your network, specify its associated network site.</span></span>
    
    <div>
    

    > [!IMPORTANT]
    > <span data-ttu-id="5e905-p116">Ogni subnet della rete deve essere associata a un sito di rete, anche se non vincolato dalla larghezza di banda, poiché il servizio Controllo di ammissione di chiamata utilizza le informazioni delle subnet per determinate il sito di rete in cui è posizionato un endpoint. Dopo che sono state determinate le posizioni in entrambe le parti della sessione, il servizio Controllo di ammissione di chiamata può determinare se la larghezza di banda è sufficiente per stabilire una chiamata. Quando viene stabilita una sessione su un collegamento senza limiti di larghezza di banda, viene generato un avviso.</span><span class="sxs-lookup"><span data-stu-id="5e905-p116">Every subnet in your network must be associated with a network site, even if the network site is not bandwidth constrained. This is because call admission control uses subnet information to determine at which network site an endpoint is located. When the locations of both parties in the session are determined, call admission control can determine if there is sufficient bandwidth to establish a call. When a session is established over a link that has no bandwidth limits, an alert is generated.</span></span><BR><span data-ttu-id="5e905-238">Se si distribuiscono Audio/Video Edge Server, gli indirizzi IP pubblici di ognuno di questi server deve essere associato al sito di rete in cui è distribuito il server.</span><span class="sxs-lookup"><span data-stu-id="5e905-238">If you deploy Audio/Video Edge Servers, the public IP addresses of each Edge Server must be associated with the network site where the Edge Server is deployed.</span></span> <span data-ttu-id="5e905-239">Ogni indirizzo IP pubblico dell'A/V Edge Server deve essere aggiunto alle impostazioni di configurazione di rete come subnet con subnet mask 32.</span><span class="sxs-lookup"><span data-stu-id="5e905-239">Each public IP address of the A/V Edge Server must be added to your network configuration settings as a subnet with a subnet mask of 32.</span></span> <span data-ttu-id="5e905-240">Se ad esempio si distribuiscono A/V Edge Server nel sito di Chicago, creare per ogni indirizzo IP esterno di tali server una subnet con subnet mask 32 e associare il sito di rete Chicago a tali subnet.</span><span class="sxs-lookup"><span data-stu-id="5e905-240">For example, if you deploy A/V Edge Servers in Chicago, then for each external IP address of those servers create a subnet with a subnet mask of 32 and associate network site Chicago with those subnets.</span></span> <span data-ttu-id="5e905-241">Per informazioni dettagliate sugli indirizzi IP pubblici, vedere <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine External a/V firewall and Port requirements for Lync Server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="5e905-241">For details about public IP addresses, see <A href="lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md">Determine external A/V firewall and port requirements for Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="5e905-p118">Viene generato un avviso Key Health Indicator (KHI) in cui viene specificato un elenco di indirizzi IP presenti nella rete che non sono associati a una subnet oppure la cui subnet non è associata a un sito di rete. Questo avviso viene generato una sola volta ogni 8 ore. Di seguito vengono riportati un esempio e le informazioni rilevanti dell'avviso:</span><span class="sxs-lookup"><span data-stu-id="5e905-p118">A Key Health Indicator (KHI) alert is raised, specifying a list of IP addresses that are present in your network but are either not associated with a subnet, or the subnet that includes the IP addresses is not associated with a network site. This alert will not be raised more than once within an 8 hour period. The relevant alert information and an example are as follows:</span></span><BR><span data-ttu-id="5e905-245"><STRONG>Origine:</STRONG> Servizio criteri di larghezza di banda CS (Core)</span><span class="sxs-lookup"><span data-stu-id="5e905-245"><STRONG>Source:</STRONG> CS Bandwidth Policy Service (Core)</span></span><BR><span data-ttu-id="5e905-246"><STRONG>Numero evento:</STRONG> 36034</span><span class="sxs-lookup"><span data-stu-id="5e905-246"><STRONG>Event number:</STRONG> 36034</span></span><BR><span data-ttu-id="5e905-247"><STRONG>Livello:</STRONG> 2</span><span class="sxs-lookup"><span data-stu-id="5e905-247"><STRONG>Level:</STRONG> 2</span></span><BR><span data-ttu-id="5e905-248"><STRONG>Descrizione:</STRONG> Le subnet per gli indirizzi IP seguenti: &lt; elenco di indirizzi IP &gt; non sono configurati o le subnet non sono associate a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="5e905-248"><STRONG>Description:</STRONG> The subnets for the following IP Addresses: &lt;List of IP Addresses&gt; are either not configured or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="5e905-249"><STRONG>Causa:</STRONG> Le subnet per gli indirizzi IP corrispondenti sono mancanti nelle impostazioni di configurazione di rete o le subnet non sono associate a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="5e905-249"><STRONG>Cause:</STRONG> The subnets for the corresponding IP addresses are missing from the network configuration settings or the subnets are not associated to a network site.</span></span><BR><span data-ttu-id="5e905-250"><STRONG>Soluzione:</STRONG> Aggiungere le subnet corrispondenti all'elenco precedente di indirizzi IP nelle impostazioni di configurazione di rete e associare ogni subnet a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="5e905-250"><STRONG>Resolution:</STRONG> Add subnets corresponding to the preceding list of IP addresses into the network configuration settings and associate every subnet to a network site.</span></span><BR><span data-ttu-id="5e905-p119">Se ad esempio nell'elenco di indirizzi IP nell'avviso sono specificati sia 10.121.248.226 che 10.121.249.20, questi indirizzi IP non sono associati a una subnet oppure la subnet a cui sono associati non appartiene a un sito di rete. Se 10.121.248.0/24 e 10.121.249.0/24 sono le subnet corrispondenti per questi indirizzi, è possibile risolvere il problema in questo modo:</span><span class="sxs-lookup"><span data-stu-id="5e905-p119">For example, if the IP address list in the alert specifies 10.121.248.226 and 10.121.249.20, either these IP addresses are not associated with a subnet, or the subnet that they are associated with does not belong to a network site. If 10.121.248.0/24 and 10.121.249.0/24 are the corresponding subnets for these addresses, you can resolve this issue as follows:</span></span> 
    > <OL>
    > <LI>
    > <P><span data-ttu-id="5e905-253">Verificare che l'indirizzo IP 10.121.248.226 sia associato alla subnet 10.121.248.0/24 e che l'indirizzo IP 10.121.249.20 sia associato alla subnet 10.121.249.0/24.</span><span class="sxs-lookup"><span data-stu-id="5e905-253">Be sure that IP address 10.121.248.226 is associated with the 10.121.248.0/24 subnet and IP address 10.121.249.20 is associated with the 10.121.249.0/24 subnet.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="5e905-254">Verificare che le subnet 10.121.248.0/24 e 10.121.249.0/24 siano associate ognuna a un sito di rete.</span><span class="sxs-lookup"><span data-stu-id="5e905-254">Be sure that the 10.121.248.0/24 and 10.121.249.0/24 subnets are each associated with a network site.</span></span></P></LI></OL>

    
    </div>
    
    ### <a name="network-sites-and-associated-subnets-bandwidth-in-kbps"></a><span data-ttu-id="5e905-255">Siti di rete e subnet associate (larghezza di banda in kbps)</span><span class="sxs-lookup"><span data-stu-id="5e905-255">Network Sites and Associated Subnets (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="5e905-256">Sito di rete</span><span class="sxs-lookup"><span data-stu-id="5e905-256">Network Site</span></span></th>
    <th><span data-ttu-id="5e905-257">Area di rete</span><span class="sxs-lookup"><span data-stu-id="5e905-257">Network Region</span></span></th>
    <th><span data-ttu-id="5e905-258">Limite di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="5e905-258">BW Limit</span></span></th>
    <th><span data-ttu-id="5e905-259">Limite audio</span><span class="sxs-lookup"><span data-stu-id="5e905-259">Audio Limit</span></span></th>
    <th><span data-ttu-id="5e905-260">Limite sessione audio</span><span class="sxs-lookup"><span data-stu-id="5e905-260">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="5e905-261">Limite video</span><span class="sxs-lookup"><span data-stu-id="5e905-261">Video Limit</span></span></th>
    <th><span data-ttu-id="5e905-262">Limite sessione video</span><span class="sxs-lookup"><span data-stu-id="5e905-262">Video Session Limit</span></span></th>
    <th><span data-ttu-id="5e905-263">Subnet</span><span class="sxs-lookup"><span data-stu-id="5e905-263">Subnets</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="5e905-264">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="5e905-264">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="5e905-265">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-265">North America</span></span></p></td>
    <td><p><span data-ttu-id="5e905-266">5,000</span><span class="sxs-lookup"><span data-stu-id="5e905-266">5,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-267">2.000</span><span class="sxs-lookup"><span data-stu-id="5e905-267">2,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-268">175</span><span class="sxs-lookup"><span data-stu-id="5e905-268">175</span></span></p></td>
    <td><p><span data-ttu-id="5e905-269">1.400</span><span class="sxs-lookup"><span data-stu-id="5e905-269">1,400</span></span></p></td>
    <td><p><span data-ttu-id="5e905-270">700</span><span class="sxs-lookup"><span data-stu-id="5e905-270">700</span></span></p></td>
    <td><p><span data-ttu-id="5e905-271">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span><span class="sxs-lookup"><span data-stu-id="5e905-271">172.29.79.0/23, 157.57.215.0/25, 172.29.90.0/23, 172.29.80.0/24</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5e905-272">Reno</span><span class="sxs-lookup"><span data-stu-id="5e905-272">Reno</span></span></p></td>
    <td><p><span data-ttu-id="5e905-273">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-273">North America</span></span></p></td>
    <td><p><span data-ttu-id="5e905-274">10.000</span><span class="sxs-lookup"><span data-stu-id="5e905-274">10,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-275">4.000</span><span class="sxs-lookup"><span data-stu-id="5e905-275">4,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-276">175</span><span class="sxs-lookup"><span data-stu-id="5e905-276">175</span></span></p></td>
    <td><p><span data-ttu-id="5e905-277">2.800</span><span class="sxs-lookup"><span data-stu-id="5e905-277">2,800</span></span></p></td>
    <td><p><span data-ttu-id="5e905-278">700</span><span class="sxs-lookup"><span data-stu-id="5e905-278">700</span></span></p></td>
    <td><p><span data-ttu-id="5e905-279">157.57.210.0/23, 172.28.151.128/25</span><span class="sxs-lookup"><span data-stu-id="5e905-279">157.57.210.0/23, 172.28.151.128/25</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5e905-280">Portland</span><span class="sxs-lookup"><span data-stu-id="5e905-280">Portland</span></span></p></td>
    <td><p><span data-ttu-id="5e905-281">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-281">North America</span></span></p></td>
    <td><p><span data-ttu-id="5e905-282">5,000</span><span class="sxs-lookup"><span data-stu-id="5e905-282">5,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-283">4.000</span><span class="sxs-lookup"><span data-stu-id="5e905-283">4,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-284">175</span><span class="sxs-lookup"><span data-stu-id="5e905-284">175</span></span></p></td>
    <td><p><span data-ttu-id="5e905-285">2.800</span><span class="sxs-lookup"><span data-stu-id="5e905-285">2,800</span></span></p></td>
    <td><p><span data-ttu-id="5e905-286">700</span><span class="sxs-lookup"><span data-stu-id="5e905-286">700</span></span></p></td>
    <td><p><span data-ttu-id="5e905-287">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span><span class="sxs-lookup"><span data-stu-id="5e905-287">172.29.77.0/24 10.71.108.0/24, 157.57.208.0/23</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5e905-288">New York</span><span class="sxs-lookup"><span data-stu-id="5e905-288">New York</span></span></p></td>
    <td><p><span data-ttu-id="5e905-289">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-289">North America</span></span></p></td>
    <td><p><span data-ttu-id="5e905-290">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-290">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-291">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-291">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-292">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-292">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-293">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-293">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-294">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-294">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-295">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span><span class="sxs-lookup"><span data-stu-id="5e905-295">172.29.80.0/23, 157.57.216.0/25, 172.29.91.0/23, 172.29.81.0/24</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5e905-296">Chicago</span><span class="sxs-lookup"><span data-stu-id="5e905-296">Chicago</span></span></p></td>
    <td><p><span data-ttu-id="5e905-297">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-297">North America</span></span></p></td>
    <td><p><span data-ttu-id="5e905-298">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-298">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-299">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-299">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-300">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-300">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-301">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-301">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-302">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-302">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-303">157.57.211.0/23, 172.28.152.128/25</span><span class="sxs-lookup"><span data-stu-id="5e905-303">157.57.211.0/23, 172.28.152.128/25</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5e905-304">Detroit</span><span class="sxs-lookup"><span data-stu-id="5e905-304">Detroit</span></span></p></td>
    <td><p><span data-ttu-id="5e905-305">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-305">North America</span></span></p></td>
    <td><p><span data-ttu-id="5e905-306">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-306">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-307">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-307">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-308">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-308">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-309">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-309">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-310">(nessun limite)</span><span class="sxs-lookup"><span data-stu-id="5e905-310">(no limit)</span></span></p></td>
    <td><p><span data-ttu-id="5e905-311">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span><span class="sxs-lookup"><span data-stu-id="5e905-311">172.29.78.0/24 10.71.109.0/24, 157.57.209.0/23</span></span></p></td>
    </tr>
    </tbody>
    </table>


7.  <span data-ttu-id="5e905-312">Nel controllo di ammissione di chiamata di Lync Server, le connessioni tra aree di rete sono denominate *collegamenti area*.</span><span class="sxs-lookup"><span data-stu-id="5e905-312">In Lync Server call admission control, the connections between network regions are called *region links*.</span></span> <span data-ttu-id="5e905-313">Come per i siti di rete, determinare per ogni collegamento area gli aspetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5e905-313">For each region link, determine the following, just as you did for the network sites:</span></span>
    
      - <span data-ttu-id="5e905-314">Limite di larghezza di banda globale che si desidera impostare per tutte le sessioni audio simultanee.</span><span class="sxs-lookup"><span data-stu-id="5e905-314">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="5e905-315">Se una nuova sessione audio provocherà il superamento di questo limite, Lync Server non consentirà di avviare la sessione.</span><span class="sxs-lookup"><span data-stu-id="5e905-315">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="5e905-p122">Limite di larghezza di banda che si desidera impostare per ogni singola sessione audio. Il limite di larghezza di banda predefinito per il servizio Controllo di ammissione di chiamata è 175 kbps, ma può essere modificato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="5e905-p122">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="5e905-318">Limite di larghezza di banda globale che si desidera impostare per tutte le sessioni video simultanee.</span><span class="sxs-lookup"><span data-stu-id="5e905-318">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="5e905-319">Se una nuova sessione video provocherà il superamento di questo limite, Lync Server non consentirà di avviare la sessione.</span><span class="sxs-lookup"><span data-stu-id="5e905-319">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="5e905-p124">Limite di larghezza di banda che si desidera impostare per ogni singola sessione video. Il limite di larghezza di banda predefinito per il servizio Controllo di ammissione di chiamata è 700 kbps, ma può essere modificato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="5e905-p124">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="5e905-322">**Collegamenti aree di rete con limiti di larghezza di banda associati**</span><span class="sxs-lookup"><span data-stu-id="5e905-322">**Network Region links with associated bandwidth limits**</span></span>
    
    <span data-ttu-id="5e905-323">![Esempio di limitazioni tra 3 aree](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Esempio di limitazioni tra 3 aree")</span><span class="sxs-lookup"><span data-stu-id="5e905-323">![Example of Limitations between 3 Regions](images/Gg425827.25259afa-ee7c-4d26-bc41-92ba9cb56dec(OCS.15).jpg "Example of Limitations between 3 Regions")</span></span>  
    
    ### <a name="region-link-bandwidth-information-bandwidth-in-kbps"></a><span data-ttu-id="5e905-324">Informazioni sulla larghezza di banda dei collegamenti aree (larghezza di banda in kbps)</span><span class="sxs-lookup"><span data-stu-id="5e905-324">Region Link Bandwidth Information (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="5e905-325">Nome collegamento area</span><span class="sxs-lookup"><span data-stu-id="5e905-325">Region Link Name</span></span></th>
    <th><span data-ttu-id="5e905-326">Prima area</span><span class="sxs-lookup"><span data-stu-id="5e905-326">First Region</span></span></th>
    <th><span data-ttu-id="5e905-327">Seconda area</span><span class="sxs-lookup"><span data-stu-id="5e905-327">Second Region</span></span></th>
    <th><span data-ttu-id="5e905-328">Limite di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="5e905-328">BW Limit</span></span></th>
    <th><span data-ttu-id="5e905-329">Limite audio</span><span class="sxs-lookup"><span data-stu-id="5e905-329">Audio Limit</span></span></th>
    <th><span data-ttu-id="5e905-330">Limite sessione audio</span><span class="sxs-lookup"><span data-stu-id="5e905-330">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="5e905-331">Limite video</span><span class="sxs-lookup"><span data-stu-id="5e905-331">Video Limit</span></span></th>
    <th><span data-ttu-id="5e905-332">Limite sessione video</span><span class="sxs-lookup"><span data-stu-id="5e905-332">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="5e905-333">NA-EMEA-COLLEGAMENTO</span><span class="sxs-lookup"><span data-stu-id="5e905-333">NA-EMEA-LINK</span></span></p></td>
    <td><p><span data-ttu-id="5e905-334">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-334">North America</span></span></p></td>
    <td><p><span data-ttu-id="5e905-335">EMEA</span><span class="sxs-lookup"><span data-stu-id="5e905-335">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="5e905-336">50.000</span><span class="sxs-lookup"><span data-stu-id="5e905-336">50,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-337">20,000</span><span class="sxs-lookup"><span data-stu-id="5e905-337">20,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-338">175</span><span class="sxs-lookup"><span data-stu-id="5e905-338">175</span></span></p></td>
    <td><p><span data-ttu-id="5e905-339">14.000</span><span class="sxs-lookup"><span data-stu-id="5e905-339">14,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-340">700</span><span class="sxs-lookup"><span data-stu-id="5e905-340">700</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5e905-341">EMEA-APAC-COLLEGAMENTO</span><span class="sxs-lookup"><span data-stu-id="5e905-341">EMEA-APAC-LINK</span></span></p></td>
    <td><p><span data-ttu-id="5e905-342">EMEA</span><span class="sxs-lookup"><span data-stu-id="5e905-342">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="5e905-343">APAC</span><span class="sxs-lookup"><span data-stu-id="5e905-343">APAC</span></span></p></td>
    <td><p><span data-ttu-id="5e905-344">25.000</span><span class="sxs-lookup"><span data-stu-id="5e905-344">25,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-345">10.000</span><span class="sxs-lookup"><span data-stu-id="5e905-345">10,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-346">175</span><span class="sxs-lookup"><span data-stu-id="5e905-346">175</span></span></p></td>
    <td><p><span data-ttu-id="5e905-347">7.000</span><span class="sxs-lookup"><span data-stu-id="5e905-347">7,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-348">700</span><span class="sxs-lookup"><span data-stu-id="5e905-348">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


8.  <span data-ttu-id="5e905-349">Definire una route tra ogni coppia di aree di rete.</span><span class="sxs-lookup"><span data-stu-id="5e905-349">Define a route between every pair of network regions.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="5e905-350">Sono necessari due collegamenti per la route tra le aree Nord America e APAC poiché non sono connesse direttamente tramite un collegamento area.</span><span class="sxs-lookup"><span data-stu-id="5e905-350">Two links are required for the route between the North America and APAC regions because there is no region link that directly connects them.</span></span>

    
    </div>
    
    ### <a name="region-routes"></a><span data-ttu-id="5e905-351">Route aree</span><span class="sxs-lookup"><span data-stu-id="5e905-351">Region Routes</span></span>
    
    <table>
    <colgroup>
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    <col style="width: 25%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><span data-ttu-id="5e905-352">Nome route area</span><span class="sxs-lookup"><span data-stu-id="5e905-352">Region Route Name</span></span></th>
    <th><span data-ttu-id="5e905-353">Prima area</span><span class="sxs-lookup"><span data-stu-id="5e905-353">First Region</span></span></th>
    <th><span data-ttu-id="5e905-354">Seconda area</span><span class="sxs-lookup"><span data-stu-id="5e905-354">Second Region</span></span></th>
    <th><span data-ttu-id="5e905-355">Collegamenti aree</span><span class="sxs-lookup"><span data-stu-id="5e905-355">Region Links</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="5e905-356">NA-EMEA-ROUTE</span><span class="sxs-lookup"><span data-stu-id="5e905-356">NA-EMEA-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="5e905-357">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-357">North America</span></span></p></td>
    <td><p><span data-ttu-id="5e905-358">EMEA</span><span class="sxs-lookup"><span data-stu-id="5e905-358">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="5e905-359">NA-EMEA-COLLEGAMENTO</span><span class="sxs-lookup"><span data-stu-id="5e905-359">NA-EMEA-LINK</span></span></p></td>
    </tr>
    <tr class="even">
    <td><p><span data-ttu-id="5e905-360">EMEA-APAC-ROUTE</span><span class="sxs-lookup"><span data-stu-id="5e905-360">EMEA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="5e905-361">EMEA</span><span class="sxs-lookup"><span data-stu-id="5e905-361">EMEA</span></span></p></td>
    <td><p><span data-ttu-id="5e905-362">APAC</span><span class="sxs-lookup"><span data-stu-id="5e905-362">APAC</span></span></p></td>
    <td><p><span data-ttu-id="5e905-363">EMEA-APAC-COLLEGAMENTO</span><span class="sxs-lookup"><span data-stu-id="5e905-363">EMEA-APAC-LINK</span></span></p></td>
    </tr>
    <tr class="odd">
    <td><p><span data-ttu-id="5e905-364">NA-APAC-ROUTE</span><span class="sxs-lookup"><span data-stu-id="5e905-364">NA-APAC-ROUTE</span></span></p></td>
    <td><p><span data-ttu-id="5e905-365">Nord America</span><span class="sxs-lookup"><span data-stu-id="5e905-365">North America</span></span></p></td>
    <td><p><span data-ttu-id="5e905-366">APAC</span><span class="sxs-lookup"><span data-stu-id="5e905-366">APAC</span></span></p></td>
    <td><p><span data-ttu-id="5e905-367">COLLEGAMENTO-NA-EMEA, COLLEGAMENTO-EMEA-APAC</span><span class="sxs-lookup"><span data-stu-id="5e905-367">NA-EMEA-LINK, EMEA-APAC-LINK</span></span></p></td>
    </tr>
    </tbody>
    </table>


9.  <span data-ttu-id="5e905-368">Per ogni coppia di siti di rete direttamente connessi tramite un collegamento singolo, denominato collegamento *tra siti*, determinare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="5e905-368">For every pair of network sites that are directly connected by a single link (called an *inter-site* link), determine the following:</span></span>
    
      - <span data-ttu-id="5e905-369">Limite di larghezza di banda globale che si desidera impostare per tutte le sessioni audio simultanee.</span><span class="sxs-lookup"><span data-stu-id="5e905-369">Overall bandwidth limit that you want to set for all concurrent audio sessions.</span></span> <span data-ttu-id="5e905-370">Se una nuova sessione audio provocherà il superamento di questo limite, Lync Server non consentirà di avviare la sessione.</span><span class="sxs-lookup"><span data-stu-id="5e905-370">If a new audio session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="5e905-p126">Limite di larghezza di banda che si desidera impostare per ogni singola sessione audio. Il limite di larghezza di banda predefinito per il servizio Controllo di ammissione di chiamata è 175 kbps, ma può essere modificato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="5e905-p126">Bandwidth limit that you want to set for each individual audio session. The default CAC bandwidth limit is 175 kbps, but it can be modified by the administrator.</span></span>
    
      - <span data-ttu-id="5e905-373">Limite di larghezza di banda globale che si desidera impostare per tutte le sessioni video simultanee.</span><span class="sxs-lookup"><span data-stu-id="5e905-373">Overall bandwidth limit that you want to set for all concurrent video sessions.</span></span> <span data-ttu-id="5e905-374">Se una nuova sessione video provocherà il superamento di questo limite, Lync Server non consentirà di avviare la sessione.</span><span class="sxs-lookup"><span data-stu-id="5e905-374">If a new video session will cause this limit to be exceeded, Lync Server does not allow the session to start.</span></span>
    
      - <span data-ttu-id="5e905-p128">Limite di larghezza di banda che si desidera impostare per ogni singola sessione video. Il limite di larghezza di banda predefinito per il servizio Controllo di ammissione di chiamata è 700 kbps, ma può essere modificato dall'amministratore.</span><span class="sxs-lookup"><span data-stu-id="5e905-p128">Bandwidth limit that you want to set for each individual video session. The default CAC bandwidth limit is 700 kbps, but it can be modified by the administrator.</span></span>
    
    <span data-ttu-id="5e905-377">**Area di rete Nord America con servizio Controllo di ammissione di chiamata in cui vengono indicate le capacità di larghezza di banda e i limiti di larghezza di banda per il collegamento tra siti tra Reno e Albuquerque**</span><span class="sxs-lookup"><span data-stu-id="5e905-377">**CAC network region North America showing the bandwidth capacities and bandwidth limits for the inter-site link between Reno and Albuquerque**</span></span>
    
    <span data-ttu-id="5e905-378">![Esempio di siti di rete vincolati dall'ampiezza della larghezza di banda WAN](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Esempio di siti di rete vincolati dall'ampiezza della larghezza di banda WAN")</span><span class="sxs-lookup"><span data-stu-id="5e905-378">![Network Sites Constrained by WAN Bandwidth example](images/Gg425827.063e5e1d-b6c8-4e8c-98db-c227c78f671d(OCS.15).jpg "Network Sites Constrained by WAN Bandwidth example")</span></span>  
    
    ### <a name="bandwidth-information-for-an-inter-site-link-between-two-network-sites-bandwidth-in-kbps"></a><span data-ttu-id="5e905-379">Informazioni sulla larghezza di banda per un collegamento tra siti tra due siti di rete (larghezza di banda in kbps)</span><span class="sxs-lookup"><span data-stu-id="5e905-379">Bandwidth Information for an Inter-Site Link between Two Network Sites (Bandwidth in kbps)</span></span>
    
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
    <th><span data-ttu-id="5e905-380">Nome collegamento tra siti</span><span class="sxs-lookup"><span data-stu-id="5e905-380">Inter-Site Link Name</span></span></th>
    <th><span data-ttu-id="5e905-381">Primo sito</span><span class="sxs-lookup"><span data-stu-id="5e905-381">First Site</span></span></th>
    <th><span data-ttu-id="5e905-382">Secondo sito</span><span class="sxs-lookup"><span data-stu-id="5e905-382">Second Site</span></span></th>
    <th><span data-ttu-id="5e905-383">Limite di larghezza di banda</span><span class="sxs-lookup"><span data-stu-id="5e905-383">BW Limit</span></span></th>
    <th><span data-ttu-id="5e905-384">Limite audio</span><span class="sxs-lookup"><span data-stu-id="5e905-384">Audio Limit</span></span></th>
    <th><span data-ttu-id="5e905-385">Limite sessione audio</span><span class="sxs-lookup"><span data-stu-id="5e905-385">Audio Session Limit</span></span></th>
    <th><span data-ttu-id="5e905-386">Limite video</span><span class="sxs-lookup"><span data-stu-id="5e905-386">Video Limit</span></span></th>
    <th><span data-ttu-id="5e905-387">Limite sessione video</span><span class="sxs-lookup"><span data-stu-id="5e905-387">Video Session Limit</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><span data-ttu-id="5e905-388">Reno-albu-collegamento tra siti</span><span class="sxs-lookup"><span data-stu-id="5e905-388">Reno-Albu-Intersite-Link</span></span></p></td>
    <td><p><span data-ttu-id="5e905-389">Reno</span><span class="sxs-lookup"><span data-stu-id="5e905-389">Reno</span></span></p></td>
    <td><p><span data-ttu-id="5e905-390">Albuquerque</span><span class="sxs-lookup"><span data-stu-id="5e905-390">Albuquerque</span></span></p></td>
    <td><p><span data-ttu-id="5e905-391">20,000</span><span class="sxs-lookup"><span data-stu-id="5e905-391">20,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-392">12.000</span><span class="sxs-lookup"><span data-stu-id="5e905-392">12,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-393">175</span><span class="sxs-lookup"><span data-stu-id="5e905-393">175</span></span></p></td>
    <td><p><span data-ttu-id="5e905-394">5,000</span><span class="sxs-lookup"><span data-stu-id="5e905-394">5,000</span></span></p></td>
    <td><p><span data-ttu-id="5e905-395">700</span><span class="sxs-lookup"><span data-stu-id="5e905-395">700</span></span></p></td>
    </tr>
    </tbody>
    </table>


<div>

## <a name="next-steps"></a><span data-ttu-id="5e905-396">Operazioni successive</span><span class="sxs-lookup"><span data-stu-id="5e905-396">Next Steps</span></span>

<span data-ttu-id="5e905-397">Dopo aver raccolto le informazioni necessarie, è possibile eseguire la distribuzione di CAC utilizzando Lync Server Management Shell o il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="5e905-397">After you have gathered the required information, you can perform CAC deployment either by using the Lync Server Management Shell or Lync Server Control Panel.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="5e905-398">Anche se è possibile eseguire la maggior parte delle attività di configurazione di rete utilizzando il pannello di controllo di Lync Server, per creare subnet e collegamenti tra siti, è necessario utilizzare Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5e905-398">Although you can perform most network configuration tasks by using Lync Server Control Panel, to create subnets and intersite links, you must use Lync Server Management Shell.</span></span> <span data-ttu-id="5e905-399">Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell per il cmdlet <STRONG>New-CsNetworkSubnet</STRONG> e il cmdlet <STRONG>New-CsNetworkIntersitePolicy</STRONG> .</span><span class="sxs-lookup"><span data-stu-id="5e905-399">For details, see the Lync Server Management Shell documentation for the <STRONG>New-CsNetworkSubnet</STRONG> cmdlet and the <STRONG>New-CsNetworkIntersitePolicy</STRONG> cmdlet.</span></span>



</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

