---
title: 'Lync Server 2013: elenco di controllo per la distribuzione delle chiamate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Call admission control deployment checklist
ms:assetid: d56a525f-3da5-4ac0-a311-0c5efd98c9df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398928(v=OCS.15)
ms:contentKeyID: 48185525
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cdda2e5231beb9f8303684ff29075c6322654945
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="call-admission-control-deployment-checklist-for-lync-server-2013"></a><span data-ttu-id="afa01-102">Elenco di controllo della distribuzione dei controlli di ammissione delle chiamate per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="afa01-102">Call admission control deployment checklist for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="afa01-103">_**Argomento Ultima modifica:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="afa01-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="afa01-104">Usare l'elenco di controllo seguente per verificare di aver completato tutte le attività di configurazione necessarie per distribuire il controllo di ammissione di chiamata (CAC).</span><span class="sxs-lookup"><span data-stu-id="afa01-104">Use the following checklist to verify that you have completed all the necessary configuration tasks to deploy call admission control (CAC).</span></span>

  - <span data-ttu-id="afa01-105">Se vengono distribuiti uno o più Edge Server, ogni indirizzo IP dell'interfaccia esterna deve essere aggiunto all'elenco subnet nelle impostazioni di configurazione della rete, con una maschera di bit di 32.</span><span class="sxs-lookup"><span data-stu-id="afa01-105">If one or more Edge Servers are deployed, each external interface IP address must be added to the subnet list in the network configuration settings, with a bit mask of 32.</span></span> <span data-ttu-id="afa01-106">Devi anche associare questa subnet (indirizzo IP) con l'ID sito di rete per la posizione geografica in cui è distribuito il servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="afa01-106">You should also associate this subnet (IP address) with the network site ID for the geographic location where the A/V Edge service is deployed.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="afa01-107">I server perimetrali non sono obbligatori per implementare CAC.</span><span class="sxs-lookup"><span data-stu-id="afa01-107">Edge servers are not required to implement CAC.</span></span>

    
    </div>

  - <span data-ttu-id="afa01-108">Verificare che CAC sia abilitato, tramite il pannello di controllo di Lync Server o eseguendo il cmdlet come specificato in [Abilita controllo ammissione chiamata in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="afa01-108">Make sure that CAC is enabled, either through Lync Server Control Panel or by running the cmdlet as specified in [Enable call admission control in Lync Server 2013](lync-server-2013-enable-call-admission-control.md).</span></span>

  - <span data-ttu-id="afa01-109">Verificare che CAC sia abilitato in tutti i siti centrali.</span><span class="sxs-lookup"><span data-stu-id="afa01-109">Make sure that CAC is enabled in all central sites.</span></span> <span data-ttu-id="afa01-110">Questa operazione può essere eseguita tramite il generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="afa01-110">This can be done through the Topology Builder.</span></span> <span data-ttu-id="afa01-111">Se viene generato un avviso durante la pubblicazione, *non* ignorarlo.</span><span class="sxs-lookup"><span data-stu-id="afa01-111">If a warning is generated when you publish, *do not* ignore it.</span></span>

  - <span data-ttu-id="afa01-112">Verificare che tutte le subnet gestite nella rete aziendale siano configurate nelle impostazioni di configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="afa01-112">Make sure that all the subnets that are managed in the enterprise network are configured in the network configuration settings.</span></span> <span data-ttu-id="afa01-113">È anche essenziale che ogni subnet sia associata a un sito di rete, come spiegato in [associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span><span class="sxs-lookup"><span data-stu-id="afa01-113">It is also essential that every subnet be associated to a network site, as explained in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).</span></span>

  - <span data-ttu-id="afa01-114">Verificare che la subnet o gli indirizzi IP di tutti i server front-end, Survivable Branch Appliances (SBAs), audio/video Conferencing Servers (se in un pool separato) e Mediation Server siano configurati nelle impostazioni di configurazione della rete.</span><span class="sxs-lookup"><span data-stu-id="afa01-114">Make sure that the subnet or IP addresses of all Front End Servers, Survivable Branch Appliances (SBAs), Audio/Video Conferencing Servers (if in a separate pool), and Mediation Servers are configured in the network configuration settings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

