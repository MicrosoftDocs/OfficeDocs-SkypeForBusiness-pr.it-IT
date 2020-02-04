---
title: 'Fase 10: sito legacy decommission'
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
ms.openlocfilehash: 8110d41e5f6436bfdbecc64fe07d514b5d0538ac
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757710"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-10-decommission-legacy-site"></a><span data-ttu-id="0f4b5-102">Fase 10: sito legacy decommission</span><span class="sxs-lookup"><span data-stu-id="0f4b5-102">Phase 10: Decommission legacy site</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f4b5-103">_**Argomento Ultima modifica:** 2012-10-16_</span><span class="sxs-lookup"><span data-stu-id="0f4b5-103">_**Topic Last Modified:** 2012-10-16_</span></span>

<span data-ttu-id="0f4b5-104">Gli argomenti seguenti includono indicazioni per lo smantellamento dei pool e la disattivazione e la rimozione di server e pool da una distribuzione legacy di Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="0f4b5-104">The following topics provide guidance in decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Office Communications Server 2007 R2.</span></span> <span data-ttu-id="0f4b5-105">Non tutte le procedure elencate in questa sezione sono obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="0f4b5-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="0f4b5-106">Leggere le informazioni in ognuno di questi argomenti per determinare la procedura di disattivazione da usare.</span><span class="sxs-lookup"><span data-stu-id="0f4b5-106">Read the information in each of these topics to determine which decommissioning procedure to use.</span></span>

<div>


> [!WARNING]  
> <span data-ttu-id="0f4b5-107">Se sono state importate le directory conferenza per le conferenze telefoniche con accesso esterno a Lync Server 2013, è importante eseguire la transizione della proprietà della directory conferenza a Lync Server 2013 prima di iniziare la disattivazione dei pool.</span><span class="sxs-lookup"><span data-stu-id="0f4b5-107">If you imported conference directories for dial-in conferencing to Lync Server 2013, it is important to transition conference directory ownership to Lync Server 2013 before you begin to decommission your pools.</span></span> <span data-ttu-id="0f4b5-108">Se si rimuove la Commissione da un pool senza la prima transizione della proprietà della directory conferenza, la funzionalità di accesso esterno per tutte le riunioni migrate non funzionerà più.</span><span class="sxs-lookup"><span data-stu-id="0f4b5-108">If you decommission a pool without first transitioning conference directory ownership, the dial-in feature for all migrated meetings will no longer work.</span></span> <span data-ttu-id="0f4b5-109">È necessario eseguire il passaggio per la proprietà transizione una sola volta per ogni directory di conferenza nel pool legacy.</span><span class="sxs-lookup"><span data-stu-id="0f4b5-109">You must perform the step to transition ownership once for each conference directory in your legacy pool.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="0f4b5-110">Per informazioni su come eseguire la migrazione e l'aggiornamento delle applicazioni Microsoft Unified Communications Managed API (UCMA), prima della disattivazione dell'ambiente legacy, vedere<A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="0f4b5-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="http://go.microsoft.com/fwlink/p/?linkid=269555">http://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="0f4b5-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="0f4b5-111">In This Section</span></span>

  - [<span data-ttu-id="0f4b5-112">Trasferire le directory conferenza</span><span class="sxs-lookup"><span data-stu-id="0f4b5-112">Move conference directories</span></span>](move-conference-directories.md)

  - [<span data-ttu-id="0f4b5-113">Aggiornare i record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="0f4b5-113">Update DNS SRV records</span></span>](update-dns-srv-records_1.md)

  - [<span data-ttu-id="0f4b5-114">Disattivazione di server e pool</span><span class="sxs-lookup"><span data-stu-id="0f4b5-114">Decommissioning servers and pools</span></span>](decommissioning-servers-and-pools.md)

  - [<span data-ttu-id="0f4b5-115">Rimuovere BackCompatSite</span><span class="sxs-lookup"><span data-stu-id="0f4b5-115">Remove BackCompatSite</span></span>](remove-backcompatsite.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

