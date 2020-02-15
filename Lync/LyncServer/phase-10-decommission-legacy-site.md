---
title: 'Fase 10: rimuovere il sito legacy'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 10: Decommission legacy site'
ms:assetid: d591a310-3b5c-4092-b19e-0349616e40df
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205300(v=OCS.15)
ms:contentKeyID: 48185540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e46c2977289ae8fec1db26e4eb33dfd6736f838
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034376"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="de79e-102">Fase 10: rimuovere il sito legacy</span><span class="sxs-lookup"><span data-stu-id="de79e-102">Phase 10: Decommission legacy site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="de79e-103">_**Ultimo argomento modificato:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="de79e-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="de79e-104">Negli argomenti seguenti vengono fornite indicazioni per la rimozione delle autorizzazioni dei pool e la disattivazione e eliminazione di server e pool da una distribuzione legacy di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="de79e-104">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="de79e-105">Non tutte le procedure elencate in questa sezione sono obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="de79e-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="de79e-106">Leggere le informazioni in ognuno di questi argomenti per determinare quale procedura utilizzare per rimuovere la disponibilità.</span><span class="sxs-lookup"><span data-stu-id="de79e-106">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="de79e-107">Se sono state importate le directory conferenze per le conferenze telefoniche con accesso esterno a Lync Server 2013, è importante eseguire la transizione della proprietà della directory conferenze a Lync Server 2013 prima di iniziare a rimuovere le autorizzazioni dei pool.</span><span class="sxs-lookup"><span data-stu-id="de79e-107">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="de79e-108">Se si rimuove un pool senza prima trasferire la proprietà delle directory conferenze, la funzionalità di accesso esterno non funzionerà più per tutte le riunioni spostate.</span><span class="sxs-lookup"><span data-stu-id="de79e-108">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="de79e-109">È necessario eseguire il passaggio di trasferimento di proprietà una volta per ogni directory conferenze del pool legacy.</span><span class="sxs-lookup"><span data-stu-id="de79e-109">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="de79e-110">Per informazioni su come eseguire la migrazione e l'aggiornamento delle applicazioni Microsoft Unified Communications Managed API (UCMA), prima di rimuovere l'ambiente legacy, vedere<A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="de79e-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="de79e-111">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="de79e-111">In This Section</span></span>

  - [<span data-ttu-id="de79e-112">Spostare le directory conferenze</span><span class="sxs-lookup"><span data-stu-id="de79e-112">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="de79e-113">Aggiornare i record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="de79e-113">Update DNS SRV records</span></span>](update-dns-srv-records_1.md)

  - [<span data-ttu-id="de79e-114">Rimozione di autorizzazioni di server e pool</span><span class="sxs-lookup"><span data-stu-id="de79e-114">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="de79e-115">Rimuovere BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="de79e-115">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

