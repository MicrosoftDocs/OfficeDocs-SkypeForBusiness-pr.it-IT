---
title: 'Lync Server 2013: creazione di una strategia di backup e ripristino'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration strategy
ms:assetid: f545a75f-bbc4-4968-b510-8f6f3920112b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202195(v=OCS.15)
ms:contentKeyID: 51541532
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcdfbb6b51a966149451e8f396b345b0383947e3
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131789"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-strategy-for-lync-server-2013"></a><span data-ttu-id="21bc4-102">Definizione di una strategia di backup e ripristino per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="21bc4-102">Establishing a backup and restoration strategy for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="21bc4-103">_**Ultimo argomento modificato:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="21bc4-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="21bc4-104">Prima di poter sviluppare un piano di backup e ripristino per Lync Server, è necessario sviluppare una strategia compatibile con gli obiettivi dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="21bc4-104">Before you can develop a backup and restoration plan for Lync Server, you need to develop a strategy that fits with your organization's goals.</span></span> <span data-ttu-id="21bc4-105">Per sviluppare una strategia di backup e ripristino efficace, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="21bc4-105">To develop an effective backup and restoration strategy, you will need to:</span></span>

  - <span data-ttu-id="21bc4-106">Stabilire le priorità aziendali.</span><span class="sxs-lookup"><span data-stu-id="21bc4-106">Establish business priorities.</span></span>

  - <span data-ttu-id="21bc4-107">Identificare i requisiti di backup e ripristino.</span><span class="sxs-lookup"><span data-stu-id="21bc4-107">Identify backup and restoration requirements.</span></span>

<div>

## <a name="establishing-business-priorities"></a><span data-ttu-id="21bc4-108">Stabilire le priorità aziendali</span><span class="sxs-lookup"><span data-stu-id="21bc4-108">Establishing Business Priorities</span></span>

<span data-ttu-id="21bc4-p102">Valutare le priorità aziendali dell'organizzazione. In genere, le principali priorità aziendali che incidono sulla strategia di backup e ripristino sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="21bc4-p102">Evaluate the business priorities of your organization. Typically, the primary business priorities that affect your backup and restoration strategy are the following:</span></span>

  - <span data-ttu-id="21bc4-111">Requisiti di continuità aziendale</span><span class="sxs-lookup"><span data-stu-id="21bc4-111">Business continuity requirements</span></span>

  - <span data-ttu-id="21bc4-112">Completezza dei dati</span><span class="sxs-lookup"><span data-stu-id="21bc4-112">Data completeness</span></span>

  - <span data-ttu-id="21bc4-113">Criticità dei dati</span><span class="sxs-lookup"><span data-stu-id="21bc4-113">Data criticality</span></span>

  - <span data-ttu-id="21bc4-114">Requisiti di portabilità</span><span class="sxs-lookup"><span data-stu-id="21bc4-114">Portability requirements</span></span>

  - <span data-ttu-id="21bc4-115">Vincoli dei costi</span><span class="sxs-lookup"><span data-stu-id="21bc4-115">Cost constraints</span></span>

<span data-ttu-id="21bc4-116">Le esigenze aziendali, ad esempio, consentono di determinare i contratti di servizio che si sviluppano con i clienti.</span><span class="sxs-lookup"><span data-stu-id="21bc4-116">Business needs such as these help to determine the service level agreements (SLAs) that you develop with your customers.</span></span> <span data-ttu-id="21bc4-117">I contratti di servizio influenzano enormemente la strategia di backup e ripristino.</span><span class="sxs-lookup"><span data-stu-id="21bc4-117">Service level agreements greatly influence your backup and recovery strategy.</span></span>

</div>

<div>

## <a name="identifying-backup-and-restoration-requirements"></a><span data-ttu-id="21bc4-118">Individuare i requisiti di backup e ripristino</span><span class="sxs-lookup"><span data-stu-id="21bc4-118">Identifying Backup and Restoration Requirements</span></span>

<span data-ttu-id="21bc4-119">Le priorità aziendali e i contratti di servizio agiscono per determinare i requisiti delle organizzazioni per il backup e il ripristino di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="21bc4-119">Your business priorities and service level agreements act in determining your organizations' requirements for backing up and restoring Lync Server.</span></span> <span data-ttu-id="21bc4-120">Individuare e documentare i requisiti per i seguenti fattori:</span><span class="sxs-lookup"><span data-stu-id="21bc4-120">Identify and document your requirements for the following:</span></span>

  - <span data-ttu-id="21bc4-121">**Frequenza dei backup**   per informazioni dettagliate sulle procedure consigliate per la frequenza di backup, vedere procedure consigliate [per il backup e il ripristino di Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span><span class="sxs-lookup"><span data-stu-id="21bc4-121">**Frequency of backups**   For details about best practices for backup frequency, see [Best practices for backup and restoration for Lync Server 2013](lync-server-2013-best-practices-for-backup-and-restoration.md).</span></span>

  - <span data-ttu-id="21bc4-122">**Gli strumenti**   di backup e ripristino includono gli utenti che devono utilizzare gli strumenti e i computer.</span><span class="sxs-lookup"><span data-stu-id="21bc4-122">**Backup and restoration tools**   Include who is to use the tools, and on which computers.</span></span> <span data-ttu-id="21bc4-123">Per informazioni dettagliate sugli strumenti descritti in questo argomento e sulle autorizzazioni necessarie, vedere [backup and Restoration requirements in Lync Server 2013: Tools and Permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="21bc4-123">For details about the tools discussed in this topic and necessary permissions, see [Backup and restoration requirements in Lync Server 2013: tools and permissions](lync-server-2013-backup-and-restoration-requirements-tools-and-permissions.md).</span></span>

  - <span data-ttu-id="21bc4-124">**Il percorso**   di backup identifica se i backup vengono mantenuti localmente o in remoto, tenendo in considerazione la sicurezza e l'accessibilità.</span><span class="sxs-lookup"><span data-stu-id="21bc4-124">**Backup location**   Identify whether the backups are kept locally or remotely, taking security and accessibility into consideration.</span></span> <span data-ttu-id="21bc4-125">Specificare i supporti da utilizzare per i backup.</span><span class="sxs-lookup"><span data-stu-id="21bc4-125">Specify the media to be used for the backups.</span></span>

  - <span data-ttu-id="21bc4-126">**Requisiti hardware e software**   identificare e documentare i requisiti hardware e software specifici, inclusi l'hardware per l'archiviazione e il ripristino del backup di componenti specifici e qualsiasi software e connettività di rete necessari per supportare il backup e il ripristino.</span><span class="sxs-lookup"><span data-stu-id="21bc4-126">**Hardware and software requirements**   Identify and document your specific hardware and software requirements, including the hardware for backup storage and restoration of specific components and any software and network connectivity required to support backup and restoration.</span></span> <span data-ttu-id="21bc4-127">Nello sviluppo dei requisiti hardware e software, valutare i diversi scenari di ripristino illustrati di seguito.</span><span class="sxs-lookup"><span data-stu-id="21bc4-127">As you develop your hardware and software requirements, keep in mind the various restoration scenarios that follow.</span></span>

  - <span data-ttu-id="21bc4-128">**Scenari di ripristino**   di seguito sono riportati i processi di ripristino per gli scenari seguenti:</span><span class="sxs-lookup"><span data-stu-id="21bc4-128">**Restoration scenarios**   Here are the restoration processes for the following scenarios:</span></span>
    
      - <span data-ttu-id="21bc4-129">Esito negativo di un pool di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="21bc4-129">A Lync Server pool fails.</span></span> <span data-ttu-id="21bc4-130">Questo scenario richiede la ricostruzione di ogni server nel pool.</span><span class="sxs-lookup"><span data-stu-id="21bc4-130">This scenario requires rebuilding each server in the pool.</span></span>
    
      - <span data-ttu-id="21bc4-131">Un server Standard Edition ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="21bc4-131">A Standard Edition server fails.</span></span> <span data-ttu-id="21bc4-132">Questo scenario richiede la ricostruzione del server in un computer nuovo o sottoposto a pulizia e il ripristino dei database.</span><span class="sxs-lookup"><span data-stu-id="21bc4-132">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="21bc4-133">Perdita dell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="21bc4-133">Loss of the Central Management store.</span></span> <span data-ttu-id="21bc4-134">Questo scenario richiede almeno il ripristino e la pubblicazione dell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="21bc4-134">At a minimum, this scenario requires restoring and publishing the Central Management store.</span></span>
    
      - <span data-ttu-id="21bc4-135">Perdita di un server back-end quando l'archivio di gestione centrale è ancora in funzione normalmente.</span><span class="sxs-lookup"><span data-stu-id="21bc4-135">Loss of a Back End Server when the Central Management store is still functioning normally.</span></span> <span data-ttu-id="21bc4-136">Questo scenario richiede la ricostruzione del server in un computer nuovo o sottoposto a pulizia e il ripristino dei database.</span><span class="sxs-lookup"><span data-stu-id="21bc4-136">This scenario requires rebuilding the server on a new or clean computer and restoring databases.</span></span>
    
      - <span data-ttu-id="21bc4-137">Un server membro di un pool di Lync Server ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="21bc4-137">A server that is a member of a Lync Server pool fails.</span></span> <span data-ttu-id="21bc4-138">Questo scenario richiede la ricostruzione del server in un computer nuovo o sottoposto a pulizia e il ripristino dei database.</span><span class="sxs-lookup"><span data-stu-id="21bc4-138">This scenario requires rebuilding the server on a new or clean computer.</span></span>
    
      - <span data-ttu-id="21bc4-139">Un archivio file ha esito negativo.</span><span class="sxs-lookup"><span data-stu-id="21bc4-139">A File Store fails.</span></span> <span data-ttu-id="21bc4-140">Questo scenario richiede il ripristino del file server o del file cluster.</span><span class="sxs-lookup"><span data-stu-id="21bc4-140">This scenario requires restoring the file server or file cluster.</span></span>
    
      - <span data-ttu-id="21bc4-141">Esito negativo di un database di archiviazione, monitoraggio o Persistent Chat.</span><span class="sxs-lookup"><span data-stu-id="21bc4-141">An Archiving, Monitoring, or Persistent Chat database fails.</span></span> <span data-ttu-id="21bc4-142">Questo scenario richiede di ricreare i database e di ripristinare i dati, se questi sono critici per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="21bc4-142">This scenario requires recreating the databases, and, if the data is critical to your organization, restoring the data.</span></span> <span data-ttu-id="21bc4-143">I dati di archiviazione, monitoraggio e Persistent Chat non sono necessari per ottenere il backup e l'esecuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="21bc4-143">Archiving, Monitoring, and Persistent Chat data is not required to get Lync Server back up and running.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

