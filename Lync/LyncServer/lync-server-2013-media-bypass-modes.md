---
title: 'Lync Server 2013: modalità di bypass multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass modes
ms:assetid: 38c06c81-7e45-4423-9e00-7fbfa4befe46
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425862(v=OCS.15)
ms:contentKeyID: 48183898
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fe8133b5becc15d1ecbebfffe0e1314da97682a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="media-bypass-modes-in-lync-server-2013"></a><span data-ttu-id="0061b-102">Modalità di bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0061b-102">Media bypass modes in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0061b-103">_**Ultimo argomento modificato:** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="0061b-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="0061b-p101">È necessario configurare il bypass multimediale sia a livello globale che per i singoli trunk PSTN. Quando si abilita il bypass multimediale a livello globale, sono disponibili due opzioni, ovvero **Ignora sempre** e **Usa le informazioni del sito e dell'area**.</span><span class="sxs-lookup"><span data-stu-id="0061b-p101">You must configure media bypass both globally and for each individual PSTN trunk. When enabling media bypass globally, you have two choices: **Always Bypass** and **Use Site and Region Information**.</span></span>

<span data-ttu-id="0061b-p102">Come indicato dal nome, **Ignora sempre** indica che verrà tentato di eseguire il bypass per tutte le chiamate PSTN. L'opzione **Ignora sempre** viene utilizzata per le distribuzioni in cui non è necessario abilitare il servizio Controllo di ammissione di chiamata né specificare informazioni di configurazione dettagliate in cui indicare quando tentare di eseguire il bypass multimediale. L'opzione **Ignora sempre** viene utilizzata inoltre quando esiste la connettività completa tra i client e i gateway PSTN. In questa configurazione tutte le subnet sono mappate a un solo ID bypass, calcolato dal sistema.</span><span class="sxs-lookup"><span data-stu-id="0061b-p102">As the name suggests, **Always Bypass** means that bypass will be attempted for all PSTN calls. **Always Bypass** is used for deployments where there is no need to enable call admission control, nor is there a need to specify detailed configuration information regarding when to attempt media bypass. Furthermore, **Always Bypass** is used when there is full connectivity between clients and PSTN gateways. In this configuration, all subnets are mapped to one and only one bypass ID, which is computed by the system.</span></span>

<span data-ttu-id="0061b-p103">Con **Utilizza configurazione siti e aree**, l'ID bypass associato alla configurazione dei siti e delle aree viene utilizzato per decidere se eseguire il bypass. Questa configurazione consente di configurare il bypass per le topologie più comuni, poiché offre un controllo granulare su quando eseguire il bypass, oltre a supportare le interazioni con il servizio Controllo di ammissione di chiamata. Il sistema tenta di semplificare l'attività assegnando automaticamente gli ID bypass come indicato di seguito.</span><span class="sxs-lookup"><span data-stu-id="0061b-p103">With **Use Site and Region Information**, the bypass ID associated with site and region configuration is used to make the bypass decision. This configuration provides the flexibility to configure bypass for most common topologies, as it gives you fine-grained control over when bypass happens, in addition to supporting interactions with call admission control (CAC). The system tries to ease your task by automatically assigning bypass IDs as follows.</span></span>

  - <span data-ttu-id="0061b-113">Il sistema assegna automaticamente un singolo ID bypass univoco a ogni area.</span><span class="sxs-lookup"><span data-stu-id="0061b-113">The system automatically assigns a single unique bypass ID to each region.</span></span>

  - <span data-ttu-id="0061b-114">Ogni sito connesso a un'area tramite un collegamento WAN senza vincoli di larghezza di banda eredita lo stesso ID bypass dell'area.</span><span class="sxs-lookup"><span data-stu-id="0061b-114">Any site connected to a region over a WAN link without bandwidth constraints inherits the same bypass ID as the region.</span></span>

  - <span data-ttu-id="0061b-115">A un sito associato all'area tramite un collegamento WAN con vincoli di larghezza di banda è assegnato un ID bypass diverso rispetto a quello dell'area.</span><span class="sxs-lookup"><span data-stu-id="0061b-115">A site associated with the region over a WAN link with constrained bandwidth is assigned a different bypass ID from that of the region.</span></span>

  - <span data-ttu-id="0061b-116">Le subnet associate a ogni sito ereditano l'ID bypass del sito.</span><span class="sxs-lookup"><span data-stu-id="0061b-116">Subnets associated with each site inherit the bypass ID for that site.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="0061b-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="0061b-117">See Also</span></span>


[<span data-ttu-id="0061b-118">Panoramica del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0061b-118">Overview of media bypass in Lync Server 2013</span></span>](lync-server-2013-overview-of-media-bypass.md)  
[<span data-ttu-id="0061b-119">Bypass multimediale e controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0061b-119">Media bypass and call admission control in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-call-admission-control.md)  
[<span data-ttu-id="0061b-120">Requisiti tecnici per il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0061b-120">Technical requirements for media bypass in Lync Server 2013</span></span>](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

