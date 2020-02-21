---
title: 'Lync Server 2013: nuove funzionalità di archiviazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Archiving features
ms:assetid: c002e367-41ad-498d-9d23-8b117ac435b2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205225(v=OCS.15)
ms:contentKeyID: 48185288
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89a8969924acdf8268f059ae3b3660b70ca1dca7
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42217056"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="new-archiving-features-in-lync-server-2013"></a><span data-ttu-id="b7090-102">Nuove funzionalità di archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7090-102">New Archiving features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b7090-103">_**Ultimo argomento modificato:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="b7090-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="b7090-104">L'archiviazione in Lync Server 2013 è in grado di archiviare i tipi di contenuto seguenti:</span><span class="sxs-lookup"><span data-stu-id="b7090-104">Archiving in Lync Server 2013 can archive the following types of content:</span></span>

  - <span data-ttu-id="b7090-105">Messaggi istantanei peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b7090-105">Peer-to-peer instant messages</span></span>

  - <span data-ttu-id="b7090-106">Conferenze (riunioni) costituite da messaggi istantanei tra più parti</span><span class="sxs-lookup"><span data-stu-id="b7090-106">Conferences (meetings) that are multi-party instant messages</span></span>

  - <span data-ttu-id="b7090-107">Contenuto di conferenze, compreso il contenuto caricato (ad esempio, gli stampati) e correlato agli eventi (ad esempio, accesso, uscita, caricamento in condivisione e modifiche della visibilità)</span><span class="sxs-lookup"><span data-stu-id="b7090-107">Conference content, including uploaded content (for example, handouts) and event-related content (for example, joining, leaving, uploading sharing, and changes in visibility)</span></span>

<span data-ttu-id="b7090-108">Inoltre, l'archiviazione in Lync Server 2013 fornisce nuove funzionalità che migliorano la distribuzione e l'efficienza delle operazioni.</span><span class="sxs-lookup"><span data-stu-id="b7090-108">Additionally, Archiving in Lync Server 2013 provides new features that improve deployment and operations efficiency.</span></span> <span data-ttu-id="b7090-109">Queste nuove funzionalità sono le seguenti:</span><span class="sxs-lookup"><span data-stu-id="b7090-109">These new features consist of:</span></span>

  - <span data-ttu-id="b7090-110">**Collocazione dell'archiviazione nei Front End Server.**    Lync Server 2013 non dispone di un ruolo del server di archiviazione distinto.</span><span class="sxs-lookup"><span data-stu-id="b7090-110">**Collocation of Archiving on Front End Servers.**   Lync Server 2013 does not have a separate Archiving Server role.</span></span> <span data-ttu-id="b7090-111">L'archiviazione infatti è una funzionalità facoltativa, disponibile in tutti i Front End Server di una distribuzione Enterprise Edition e nei server Standard Edition, che può essere implementata e configurata per un pool o un sito.</span><span class="sxs-lookup"><span data-stu-id="b7090-111">Archiving is an optional feature available on all Front End Servers in an Enterprise Edition deployment, and on Standard Edition servers, that can be implemented configured for a pool or a site.</span></span>

  - <span data-ttu-id="b7090-112">**Integrazione di Microsoft Exchange.**    Quando si distribuisce l'archiviazione, è possibile integrare l'archiviazione dei dati per l'archiviazione con l'archivio di Exchange 2013 esistente per tutti gli utenti che si trovano in Exchange 2013 e che le cassette postali vengono conservate sul posto, pertanto non è necessario distribuire database di SQL Server distinti per archiviare i dati di Lync.</span><span class="sxs-lookup"><span data-stu-id="b7090-112">**Microsoft Exchange integration.**   When you deploy Archiving, you can integrate data storage for Archiving with your existing Exchange 2013 storage for all users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold, so you don’t need to deploy separate SQL Server databases to archive Lync data.</span></span> <span data-ttu-id="b7090-113">Se non si dispone di una distribuzione di Exchange 2013 o se si preferisce non integrarlo o se sono presenti utenti di Lync 2013 che non sono ospitati in Exchange 2013 con le proprie cassette postali in blocco sul posto, è possibile distribuire database di archiviazione separati utilizzando SQL Server per stor e dati archiviati da Lync Communications.</span><span class="sxs-lookup"><span data-stu-id="b7090-113">If you do not have an Exchange 2013 deployment, or if you prefer not to integrate with it, or if you have any Lync 2013 users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold, you can deploy separate Archiving databases by using SQL Server to store archived data from Lync communications.</span></span> <span data-ttu-id="b7090-114">È possibile utilizzare l'integrazione di Microsoft Exchange e i database di archiviazione di Lync Server 2013 se si desidera utilizzare l'integrazione di Microsoft Exchange per alcuni ma non tutti gli utenti nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b7090-114">You can use both Microsoft Exchange integration and Lync Server 2013 Archiving databases if you want to use Microsoft Exchange integration for some but not all users in your deployment.</span></span> <span data-ttu-id="b7090-115">Per informazioni dettagliate sull'archiviazione sul posto, vedere "blocco sul posto" all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500).</span><span class="sxs-lookup"><span data-stu-id="b7090-115">For details about In-Place Hold, see “In-Place Hold” at [https://go.microsoft.com/fwlink/p/?LinkId=267500](https://go.microsoft.com/fwlink/p/?linkid=267500).</span></span>

  - <span data-ttu-id="b7090-116">**Mirroring dell'archivio SQL.**    Quando si distribuisce l'archiviazione, è possibile abilitare il mirroring del database di SQL Server per il database di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="b7090-116">**SQL Store Mirroring.**   When you deploy Archiving, you can enable SQL Server database mirroring for your Archiving database.</span></span>

  - <span data-ttu-id="b7090-117">**Archiviazione di lavagne e sondaggi.**    Il contenuto delle conferenze archiviate ora include le lavagne e i sondaggi condivisi durante la riunione.</span><span class="sxs-lookup"><span data-stu-id="b7090-117">**Archiving of Whiteboards and Polls.**   Archived conference content now includes whiteboards and polls that are shared during the meeting.</span></span>

<span data-ttu-id="b7090-118">Non vengono archiviati i tipi di contenuto seguenti:</span><span class="sxs-lookup"><span data-stu-id="b7090-118">The following types of content are not archived:</span></span>

  - <span data-ttu-id="b7090-119">Trasferimenti di file peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b7090-119">Peer-to-peer file transfers</span></span>

  - <span data-ttu-id="b7090-120">Audio e video per conferenze e messaggi istantanei peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b7090-120">Audio/video for peer-to-peer instant messages and conferences</span></span>

  - <span data-ttu-id="b7090-121">Condivisione di applicazioni per conferenze e messaggi istantanei peer-to-peer</span><span class="sxs-lookup"><span data-stu-id="b7090-121">Application sharing for peer-to-peer instant messages and conferences</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="b7090-122">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b7090-122">See Also</span></span>


[<span data-ttu-id="b7090-123">Pianificazione dell'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b7090-123">Planning for Archiving in Lync Server 2013</span></span>](lync-server-2013-planning-for-archiving.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

