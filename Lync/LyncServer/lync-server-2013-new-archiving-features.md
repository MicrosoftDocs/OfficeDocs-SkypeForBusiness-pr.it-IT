---
title: 'Lync Server 2013: Nuove funzionalità di archiviazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d736e823892aa6d6edcc5ab90df900a5c6b7ac79
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985475"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="c2fab-102">Nuove funzionalità di archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2fab-102">New Archiving features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c2fab-103">_**Argomento Ultima modifica:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="c2fab-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="c2fab-104">L'archiviazione in Lync Server 2013 può archiviare i tipi di contenuto seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2fab-104">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="c2fab-105">Messaggi istantanei peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="c2fab-105">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="c2fab-106">Conferenze (riunioni) che sono messaggi istantanei multiparte</span><span class="sxs-lookup"><span data-stu-id="c2fab-106">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="c2fab-107">Contenuto della conferenza, incluso il contenuto caricato, ad esempio gli stampati, e il contenuto correlato agli eventi (ad esempio, partecipazione, uscita, caricamento della condivisione e modifica della visibilità)</span><span class="sxs-lookup"><span data-stu-id="c2fab-107">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="c2fab-108">Inoltre, l'archiviazione in Lync Server 2013 offre nuove funzionalità che migliorano l'efficienza della distribuzione e delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="c2fab-108">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="c2fab-109">Queste nuove funzionalità sono costituite da:</span><span class="sxs-lookup"><span data-stu-id="c2fab-109">These new features consist of:</span></span>

  - <span data-ttu-id="c2fab-110">**Collocazione dell'archiviazione nei server front-end.**    Lync Server 2013 non ha un ruolo di server di archiviazione distinto.</span><span class="sxs-lookup"><span data-stu-id="c2fab-110">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="c2fab-111">L'archiviazione è una funzionalità facoltativa disponibile in tutti i server front-end in una distribuzione di Enterprise Edition e nei server Standard Edition, che possono essere implementati configurati per un pool o un sito.</span><span class="sxs-lookup"><span data-stu-id="c2fab-111">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="c2fab-112">**Integrazione di Microsoft Exchange.**    Quando si distribuisce l'archiviazione, è possibile integrare lo spazio di archiviazione dei dati per l'archiviazione con l'archiviazione di Exchange 2013 esistente per tutti gli utenti residenti in Exchange 2013 e inserire le cassette postali sul posto, quindi non è necessario distribuire database di SQL Server distinti per archiviare i dati di Lync.</span><span class="sxs-lookup"><span data-stu-id="c2fab-112">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="c2fab-113">Se non si dispone di una distribuzione di Exchange 2013 o se si preferisce non integrarla o se si hanno utenti di Lync 2013 non residenti in Exchange 2013 con le cassette postali inserite nel blocco, è possibile distribuire database di archiviazione distinti tramite SQL Server per stor e dati archiviati da Lync Communications.</span><span class="sxs-lookup"><span data-stu-id="c2fab-113">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="c2fab-114">È possibile usare sia l'integrazione di Microsoft Exchange che i database di archiviazione di Lync Server 2013 se si vuole usare l'integrazione di Microsoft Exchange per alcuni utenti, ma non tutti, nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c2fab-114">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="c2fab-115">Per informazioni dettagliate sul blocco sul posto, vedere "blocco sul posto" [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500).</span><span class="sxs-lookup"><span data-stu-id="c2fab-115">For details about In-Place Hold, see “In-Place Hold” at [http://go.microsoft.com/fwlink/p/?LinkId=267500](http://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="c2fab-116">**Mirroring di SQL Store.**    Quando si distribuisce l'archiviazione, è possibile abilitare il mirroring del database di SQL Server per il database di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="c2fab-116">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="c2fab-117">**Archiviazione di lavagne e sondaggi.**    Il contenuto di una conferenza archiviata ora include lavagne e sondaggi condivisi durante la riunione.</span><span class="sxs-lookup"><span data-stu-id="c2fab-117">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="c2fab-118">I tipi di contenuto seguenti non vengono archiviati:</span><span class="sxs-lookup"><span data-stu-id="c2fab-118">The following types of content are not archived:</span></span>

  - <span data-ttu-id="c2fab-119">Trasferimenti di file peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="c2fab-119">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="c2fab-120">Audio/video per i messaggi istantanei e le conferenze peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="c2fab-120">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="c2fab-121">Condivisione di applicazioni per i messaggi istantanei e le conferenze peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="c2fab-121">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="c2fab-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c2fab-122">See Also</span></span>


[<span data-ttu-id="c2fab-123">Pianificazione dell'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c2fab-123">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

