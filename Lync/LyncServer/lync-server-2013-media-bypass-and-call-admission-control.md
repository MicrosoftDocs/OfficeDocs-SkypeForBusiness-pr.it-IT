---
title: 'Lync Server 2013: bypass multimediale e controllo di ammissione di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10915a298fe2e50abdef09dc5acf92927a43cc65
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185299"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="8802b-102">Bypass multimediale e controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8802b-102">Media bypass and call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8802b-103">_**Ultimo argomento modificato:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="8802b-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="8802b-p101">Il bypass multimediale (o Media Bypass, ovvero la possibilità di ignorare il Mediation Server) e il servizio Controllo di ammissione di chiamata interagiscono per gestire il controllo della larghezza di banda per i supporti di chiamata. Il bypass multimediale facilita il flusso multimediale su buoni collegamenti. Il servizio Controllo di ammissione di chiamata gestisce il traffico sui collegamenti con vincoli di larghezza di banda. Poiché le due funzionalità si escludono a vicenda, è necessario ricordarsi dell'una quando si pianifica l'altra. Sono supportate le combinazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8802b-p101">Media bypass and call admission control (CAC) work together to manage bandwidth control for call media. Media bypass facilitates media flow over well-connected links; CAC manages traffic on links with bandwidth constraints. Because Media Bypass and CAC are mutually exclusive, you must be mindful of one when planning for the other. The following combinations are supported:</span></span>

  - <span data-ttu-id="8802b-p102">Il controllo di ammissione di chiamata e il bypass multimediale sono entrambi abilitati. Il secondo deve essere impostato su **Utilizza configurazione siti e aree**. Tali informazioni sui siti e sulle aree sono le stesse utilizzate per il controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="8802b-p102">CAC and Media Bypass are both enabled. Media Bypass must be set to **Use Site and Region Information**. This site and region information is the same as that used for CAC.</span></span>
    
    <span data-ttu-id="8802b-p103">Se si abilita il controllo di ammissione di chiamata, non sarà possibile selezionare **Ignora sempre** e viceversa perché le due configurazioni si escludono reciprocamente. In altri termini, solo una delle due funzionalità verrà applicata a una determinata chiamata PSTN. Viene innanzitutto effettuata una verifica per determinare se il bypass multimediale sia applicabile alla chiamata. In caso affermativo, non viene utilizzato il controllo di ammissione di chiamata. Questo comportamento è logico in quanto, se una chiamata è idonea per il bypass, utilizza per definizione una connessione su cui il controllo di ammissione di chiamata non è necessario. Se il bypass non è applicabile alla chiamata, ovvero se gli ID bypass del client e del gateway non corrispondono, viene utilizzato il controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="8802b-p103">If you enable CAC, you cannot select **Always Bypass**, and vice-versa, because the two configurations are mutually exclusive. That is, only one of the two will apply to any given PSTN call. First, a check is made to determine if media bypass applies to the call. If it does, then CAC is not used. This makes sense, because if a call is eligible for bypass, it is by definition using a connection where CAC is not needed. If bypass cannot be applied to the call (that is, if the client’s and gateway’s bypass IDs do not match), then CAC is applied to the call.</span></span>

  - <span data-ttu-id="8802b-117">Il controllo di ammissione di chiamata non è abilitato e il bypass multimediale è impostato su **Ignora sempre**.</span><span class="sxs-lookup"><span data-stu-id="8802b-117">CAC not enabled and Media Bypass set to **Always Bypass**.</span></span>
    
    <span data-ttu-id="8802b-118">In questa configurazione le subnet di client e trunk sono mappate a un solo ID bypass, che viene calcolato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="8802b-118">In this configuration, both client and trunk subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

  - <span data-ttu-id="8802b-119">Il controllo di ammissione di chiamata non è abilitato e il bypass multimediale è impostato su **Utilizza configurazione siti e aree**.</span><span class="sxs-lookup"><span data-stu-id="8802b-119">CAC not enabled and Media Bypass set to **Use Site and Region Information**.</span></span>
    
    <span data-ttu-id="8802b-p104">Quando è abilitata l'impostazione **Utilizza configurazione siti e aree**, la determinazione della possibilità di applicare il bypass funziona essenzialmente nello stesso modo, indipendentemente dal fatto che il controllo di ammissione di chiamata sia abilitato o meno. In altri termini, per una determinata chiamata PSTN, la subnet del client è mappata a un particolare sito e viene estratto l'ID bypass di tale subnet. Analogamente, la subnet del gateway è mappata a un particolare sito e viene estratto l'ID bypass di quella subnet. Il bypass verrà applicato per la chiamata solo se i due ID bypass sono identici, altrimenti non verrà utilizzato.</span><span class="sxs-lookup"><span data-stu-id="8802b-p104">Where **Use Site and Region Information** is enabled, bypass determination works essentially the same way, regardless of whether CAC is enabled or not. That is, for any given PSTN call, the client’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted. Similarly, the gateway’s subnet is mapped to a particular site, and the bypass ID for that subnet is extracted. Only if the two bypass IDs are identical will bypass happen for the call. If they are not identical, media bypass will not occur.</span></span>
    
    <span data-ttu-id="8802b-p105">Anche se il controllo di ammissione di chiamata è disabilitato a livello globale, è necessario definire criteri di larghezza di banda per ogni sito e collegamento se si desidera utilizzare la configurazione dei siti e delle aree per controllare la decisione di applicare o meno il bypass. Il valore effettivo del vincolo di larghezza di banda o la relativa modalità non è importante. Lo scopo finale è avere il sistema che calcola automaticamente ID bypass diversi da associare a impostazioni locali diverse non connesse perfettamente. Se si stabilisce un vincolo di larghezza di banda, significa per definizione che un collegamento non è ben connesso.</span><span class="sxs-lookup"><span data-stu-id="8802b-p105">Even though CAC is disabled globally, bandwidth policy needs to be defined for each site and link if you want to use site-and-region configuration to control the bypass decision. The actual value of the bandwidth constraint or its modality doesn’t matter. The ultimate goal is to have the system automatically calculate different bypass IDs to associate with different locales that are not well connected. Defining a bandwidth constraint by definition means a link is not well connected.</span></span>

  - <span data-ttu-id="8802b-129">Il controllo di ammissione di chiamata è abilitato e il bypass multimediale non è abilitato.</span><span class="sxs-lookup"><span data-stu-id="8802b-129">CAC is enabled and media bypass is not enabled.</span></span> <span data-ttu-id="8802b-130">Questa situazione si verifica esclusivamente se tutti i gateway e i sistemi IP-PBX non sono ben connessi o non soddisfano altri requisiti per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="8802b-130">This would apply only where all gateways and IP-PBXs are not well connected or do not meet other requirements for media bypass.</span></span> <span data-ttu-id="8802b-131">Per informazioni dettagliate sui requisiti per il bypass multimediale, vedere [Technical Requirements for Media Bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="8802b-131">For details about requirements for media bypass, see [Technical requirements for media bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="8802b-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="8802b-132">See Also</span></span>


[<span data-ttu-id="8802b-133">Panoramica del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8802b-133">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="8802b-134">Modalità di bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8802b-134">Media bypass modes in Lync Server 2013</span></span>](lync-server-2013-media-bypass-modes.md)  
[<span data-ttu-id="8802b-135">Requisiti tecnici per il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8802b-135">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

