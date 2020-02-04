---
title: "Lync Server 2013: requisiti tecnici per l'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Technical requirements for Archiving
ms:assetid: 896d60e2-be4b-462d-8357-4cd307ab7304
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205059(v=OCS.15)
ms:contentKeyID: 48184732
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6cc8a64ee7a49971660e7435a51c816bd4367e26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746576"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="technical-requirements-for-archiving-in-lync-server-2013"></a><span data-ttu-id="b10a4-102">Requisiti tecnici per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b10a4-102">Technical requirements for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b10a4-103">_**Argomento Ultima modifica:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="b10a4-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="b10a4-104">I requisiti tecnici di Lync Server 2013 includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="b10a4-104">Lync Server 2013 technical requirements include the following:</span></span>

  - <span data-ttu-id="b10a4-105">Requisiti per l'infrastruttura.</span><span class="sxs-lookup"><span data-stu-id="b10a4-105">Infrastructure requirements.</span></span>

  - <span data-ttu-id="b10a4-106">Software prerequisito che deve essere installato per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b10a4-106">Prerequisite software that must be installed for Archiving.</span></span>

  - <span data-ttu-id="b10a4-107">Requisiti di archiviazione dei dati per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b10a4-107">Data storage requirements for Archiving.</span></span>

  - <span data-ttu-id="b10a4-108">Ridimensionamento di requisiti e considerazioni per la distribuzione dell'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b10a4-108">Scaling requirements and considerations for your Archiving deployment.</span></span>

  - <span data-ttu-id="b10a4-109">Requisiti e considerazioni sulle prestazioni per i database di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b10a4-109">Performance requirements and considerations for your Archiving databases.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b10a4-110">Le informazioni sulla scalabilità e sulle prestazioni non sono disponibili in questa versione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b10a4-110">Scaling and performance information is not available in this Lync Server 2013 release.</span></span>



</div>

<div>

## <a name="infrastructure-requirements"></a><span data-ttu-id="b10a4-111">Requisiti per l'infrastruttura</span><span class="sxs-lookup"><span data-stu-id="b10a4-111">Infrastructure Requirements</span></span>

<span data-ttu-id="b10a4-112">I requisiti dell'infrastruttura di archiviazione di Lync Server 2013 sono uguali a quelli per la distribuzione di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="b10a4-112">Lync Server 2013 Archiving infrastructure requirements are the same as for deployment of Lync Server 2013.</span></span> <span data-ttu-id="b10a4-113">Per informazioni dettagliate, vedere [determinazione dei requisiti di infrastruttura per Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="b10a4-113">For details, see [Determining your infrastructure requirements for Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) in the Planning documentation.</span></span>

</div>

<div>

## <a name="archiving-prerequisites"></a><span data-ttu-id="b10a4-114">Archiviazione di prerequisiti</span><span class="sxs-lookup"><span data-stu-id="b10a4-114">Archiving Prerequisites</span></span>

<span data-ttu-id="b10a4-115">Lync Server 2013 semplifica i prerequisiti per l'archiviazione a causa delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b10a4-115">Lync Server 2013 streamlines prerequisites for Archiving because of the following:</span></span>

  - <span data-ttu-id="b10a4-116">Il server di archiviazione non è più un ruolo del server.</span><span class="sxs-lookup"><span data-stu-id="b10a4-116">Archiving Server is no longer a server role.</span></span> <span data-ttu-id="b10a4-117">Gli agenti di raccolta dati unificati vengono invece eseguiti nei server front-end in un pool e in Server Standard Edition per acquisire dati per l'archiviazione, quindi non è possibile configurare piattaforme di sistema separate per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b10a4-117">Instead, Unified Data Collection Agents run on the Front End Servers in a pool and Standard Edition servers to capture data for Archiving, so you do not set up separate system platforms for Archiving.</span></span>

  - <span data-ttu-id="b10a4-118">L'archiviazione usa l'archiviazione di file di Lync Server 2013 per l'archiviazione temporanea dei file di contenuto della riunione, quindi non è possibile configurare un archivio di file separato per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b10a4-118">Archiving uses the Lync Server 2013 file storage for temporary storage of meeting content files, so you do not set up a separate file store for archiving.</span></span>

  - <span data-ttu-id="b10a4-119">In Lync Server 2013 non è necessario accodare messaggi.</span><span class="sxs-lookup"><span data-stu-id="b10a4-119">In Lync Server 2013, Message Queuing is not required.</span></span>

</div>

<div>

## <a name="data-storage-requirements-for-archiving"></a><span data-ttu-id="b10a4-120">Requisiti di archiviazione dei dati per l'archiviazione</span><span class="sxs-lookup"><span data-stu-id="b10a4-120">Data Storage Requirements for Archiving</span></span>

<span data-ttu-id="b10a4-121">Inoltre, è necessario configurare l'infrastruttura per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b10a4-121">Additionally, you need to set up the infrastructure for Archiving storage.</span></span> <span data-ttu-id="b10a4-122">Questo include una o entrambe le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="b10a4-122">This includes one or both of the following:</span></span>

  - <span data-ttu-id="b10a4-123">**Archiviazione di Microsoft Exchange**.</span><span class="sxs-lookup"><span data-stu-id="b10a4-123">**Microsoft Exchange storage**.</span></span> <span data-ttu-id="b10a4-124">I file di contenuto della riunione, ad esempio le presentazioni di PowerPoint, vengono archiviati come allegati.</span><span class="sxs-lookup"><span data-stu-id="b10a4-124">Meeting content files, such as PowerPoint presentations, are archived as attachments.</span></span> <span data-ttu-id="b10a4-125">Se si vuole usare l'integrazione di Microsoft Exchange in modo che i dati di archiviazione di Lync vengano archiviati con i dati di conformità di Exchange, è necessario usare Exchange 2013 per la distribuzione di Exchange e verificare che le dimensioni massime dello spazio di archiviazione supportino l'archiviazione dei file di contenuto della riunione.</span><span class="sxs-lookup"><span data-stu-id="b10a4-125">If you want to use Microsoft Exchange integration so that Lync archive data is stored with Exchange compliance data, you must use Exchange 2013 for your Exchange deployment and ensure that the maximum storage size supports storage of the meeting content files.</span></span> <span data-ttu-id="b10a4-126">Se si distribuisce l'archiviazione con l'opzione di integrazione di Microsoft Exchange, i dati di archiviazione di Lync vengono archiviati con i dati di conformità di Exchange 2013 solo per gli utenti residenti nei server di Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="b10a4-126">If you deploy Archiving using the Microsoft Exchange integration option, Lync archive data is stored with Exchange 2013 compliance data only for the users who are homed on your Exchange 2013 servers.</span></span> <span data-ttu-id="b10a4-127">È necessario distribuire Exchange 2013 prima di distribuire e abilitare l'archiviazione con l'opzione di integrazione di Microsoft Exchange.</span><span class="sxs-lookup"><span data-stu-id="b10a4-127">You must deploy Exchange 2013 prior to deploying and enabling Archiving using the Microsoft Exchange integration option.</span></span> <span data-ttu-id="b10a4-128">Se si sceglie di usare lo spazio di archiviazione di Exchange 2013, non è necessario distribuire database di SQL Server distinti per l'archiviazione, a meno che non siano presenti utenti di Lync non residenti nei server di Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="b10a4-128">If you choose to use Exchange 2013 storage, you do not need to deploy separate SQL Server databases for Archiving, unless you have Lync users who are not homed on your Exchange 2013 servers.</span></span>

  - <span data-ttu-id="b10a4-129">**Archiviazione di database di SQL Server per l'archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="b10a4-129">**SQL Server database storage for Archiving**.</span></span> <span data-ttu-id="b10a4-130">Per supportare gli utenti non residenti nei server di Exchange 2013 o se non si vuole usare l'opzione di integrazione di Microsoft Exchange, è necessario distribuire archiviazione di archiviazione tramite un database di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b10a4-130">To support users who are not homed on Exchange 2013 servers, or if you do not want to use the Microsoft Exchange integration option, you must deploy Archiving storage using a SQL Server database.</span></span> <span data-ttu-id="b10a4-131">Lync Server 2013 supporta le versioni di SQL Server seguenti a 64 bit:</span><span class="sxs-lookup"><span data-stu-id="b10a4-131">Lync Server 2013 supports the following 64-bit versions of SQL Server:</span></span>
    
      - <span data-ttu-id="b10a4-132">Microsoft SQL Server 2008 R2 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b10a4-132">Microsoft SQL Server 2008 R2 Enterprise</span></span>
    
      - <span data-ttu-id="b10a4-133">Microsoft SQL Server 2008 R2 Standard</span><span class="sxs-lookup"><span data-stu-id="b10a4-133">Microsoft SQL Server 2008 R2 Standard</span></span>
    
      - <span data-ttu-id="b10a4-134">Microsoft SQL Server 2012 Enterprise</span><span class="sxs-lookup"><span data-stu-id="b10a4-134">Microsoft SQL Server 2012 Enterprise</span></span>
    
      - <span data-ttu-id="b10a4-135">Microsoft SQL Server 2012 standard</span><span class="sxs-lookup"><span data-stu-id="b10a4-135">Microsoft SQL Server 2012 Standard</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b10a4-136">Microsoft SQL Server 2008 R2 Express e Microsoft SQL Server 2012 Express non sono supportati per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b10a4-136">Microsoft SQL Server 2008 R2 Express and Microsoft SQL Server 2012 Express are not supported for Archiving.</span></span> <span data-ttu-id="b10a4-137">le versioni a 32 bit di SQL Server non sono supportate.</span><span class="sxs-lookup"><span data-stu-id="b10a4-137">32-bit versions of SQL Server are not supported.</span></span> <span data-ttu-id="b10a4-138">Per ulteriori requisiti e restrizioni di SQL Server, vedere <A href="lync-server-2013-database-software-support.md">supporto del software di database in Lync Server 2013</A> nella documentazione relativa alla pianificazione o nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="b10a4-138">For additional SQL Server requirements and restrictions, see <A href="lync-server-2013-database-software-support.md">Database software support in Lync Server 2013</A> in the Planning documentation or in the Supportability documentation.</span></span>

    
    </div>
    
    <span data-ttu-id="b10a4-139">È necessario configurare le piattaforme SQL Server prima di distribuire e abilitare l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b10a4-139">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="b10a4-140">Se l'account da usare per pubblicare la topologia include i diritti e le autorizzazioni di amministratore appropriati, è possibile creare il database di archiviazione (LcsLog) durante la pubblicazione della topologia.</span><span class="sxs-lookup"><span data-stu-id="b10a4-140">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="b10a4-141">È anche possibile creare il database in un secondo momento, incluso come parte della procedura di installazione.</span><span class="sxs-lookup"><span data-stu-id="b10a4-141">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="b10a4-142">Per informazioni dettagliate su SQL Server, vedere SQL Server TechCenter at [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).</span><span class="sxs-lookup"><span data-stu-id="b10a4-142">For details about SQL Server, see the SQL Server TechCenter at [http://go.microsoft.com/fwlink/p/?linkID=129045](http://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

