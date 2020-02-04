---
title: 'Lync Server 2013: Panoramica del processo di backup e ripristino'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backup and restoration process overview
ms:assetid: e0f23b21-070f-4df5-b795-cea2f5338d85
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202192(v=OCS.15)
ms:contentKeyID: 51541524
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 559ebb5a5d5ba91b5a4952037c18ad509ed5cec7
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728956"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backup-and-restoration-process-overview-for-lync-server-2013"></a><span data-ttu-id="bc592-102">Panoramica del processo di backup e ripristino per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bc592-102">Backup and restoration process overview for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc592-103">_**Argomento Ultima modifica:** 2013-03-26_</span><span class="sxs-lookup"><span data-stu-id="bc592-103">_**Topic Last Modified:** 2013-03-26_</span></span>

<span data-ttu-id="bc592-104">Questa sezione offre una panoramica del funzionamento del processo di backup e ripristino per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bc592-104">This section provides an overview of how the backup and restoration process works for Lync Server 2013.</span></span> <span data-ttu-id="bc592-105">Si usa lo stesso processo per tutti i server Standard Edition e i server Enterprise Edition, indipendentemente dalla loro posizione.</span><span class="sxs-lookup"><span data-stu-id="bc592-105">You use the same process for all Standard Edition servers and Enterprise Edition servers, regardless of their location.</span></span>

<span data-ttu-id="bc592-106">In generale, il processo di backup funziona nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="bc592-106">In general, the backup process works as follows:</span></span>

  - <span data-ttu-id="bc592-107">Si crea un percorso di backup come cartella condivisa in un computer autonomo che non fa parte di nessun pool.</span><span class="sxs-lookup"><span data-stu-id="bc592-107">You create a backup location as a shared folder on a stand-alone computer that is not part of any pool.</span></span> <span data-ttu-id="bc592-108">In **$backup**viene fatto riferimento alla posizione del backup.</span><span class="sxs-lookup"><span data-stu-id="bc592-108">The location of the backup is referenced in **$Backup**.</span></span>

  - <span data-ttu-id="bc592-109">In base a una normale pianificazione, è possibile eseguire il backup di tutti i database di Lync Server e di tutti gli archivi di file descritti in [requisiti di backup e ripristino in Lync server 2013: dati](lync-server-2013-backup-and-restoration-requirements-data.md) seguendo le procedure descritte in [backup di Lync Server 2013](lync-server-2013-backing-up-lync-server.md) l'archivio di gestione centrale include tutte le impostazioni e le configurazioni del server.</span><span class="sxs-lookup"><span data-stu-id="bc592-109">On a regular, scheduled basis, you back up all the Lync Server databases and all the file stores that are described in [Backup and restoration requirements in Lync Server 2013: data](lync-server-2013-backup-and-restoration-requirements-data.md) by following the procedures described in [Backing up Lync Server 2013](lync-server-2013-backing-up-lync-server.md) The Central Management store includes all the server settings and configurations.</span></span>

  - <span data-ttu-id="bc592-110">Ogni volta che si esegue un backup successivo, si crea una nuova cartella condivisa e si modifica il percorso **$backup** riferimenti.</span><span class="sxs-lookup"><span data-stu-id="bc592-110">Each time you run a subsequent backup, you create a new shared folder and change the path that **$Backup** references.</span></span>

<span data-ttu-id="bc592-111">In generale, il processo di ripristino funziona nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="bc592-111">In general, the restoration process works as follows:</span></span>

  - <span data-ttu-id="bc592-112">Quando si verifica un errore o un'interruzione, ripristinare i dati nella posizione a cui fa riferimento **$backup** ai computer nuovi o puliti.</span><span class="sxs-lookup"><span data-stu-id="bc592-112">When a failure or outage occurs, you restore the data in the location referenced by **$Backup** to new or clean computers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="bc592-113">Questo processo di ripristino non ripristina i dati su uno stato del server esistente.</span><span class="sxs-lookup"><span data-stu-id="bc592-113">This restoration process does not restore data onto an existing server state.</span></span> <span data-ttu-id="bc592-114">Questo processo richiede che il server sia pulito o nuovo.</span><span class="sxs-lookup"><span data-stu-id="bc592-114">That is, this process requires that the server is clean or new.</span></span>

    
    </div>

  - <span data-ttu-id="bc592-115">Per consentire all'utente e alle informazioni della conferenza di essere recuperabili fino al punto di errore, è possibile implementare una topologia di ripristino di emergenza con pool Front-End associati, come descritto in [pianificazione per l'elevata disponibilità e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="bc592-115">To enable your user and conference information to be recoverable to the point of failure, you can implement a disaster recovery topology with paired Front End pools, as described in [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="bc592-116">Tutte le configurazioni DNS (Domain Name System), la configurazione DHCP (Dynamic Host Configuration Protocol), i nomi di dominio, i nomi di dominio completi di computer (FQDN), i percorsi di archiviazione dei file e così via devono essere uguali al momento del ripristino eseguire il backup.</span><span class="sxs-lookup"><span data-stu-id="bc592-116">All Domain Name System (DNS) configuration, Dynamic Host Configuration Protocol (DHCP) configuration, domain names, computer fully qualified domain names (FQDNs), file store paths, and so on must be the same at the time of restoration that they were at the time of back up.</span></span>

<span data-ttu-id="bc592-117">Se un server che esegue Lync Server non riesce, il ripristino include i passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="bc592-117">If a server running Lync Server fails, recovery includes the following steps:</span></span>

  - <span data-ttu-id="bc592-118">Installare il sistema operativo in un computer nuovo o pulito con lo stesso nome di dominio completo del computer non riuscito.</span><span class="sxs-lookup"><span data-stu-id="bc592-118">Install the operating system on a new or clean computer with the same FQDN as the failed computer.</span></span>

  - <span data-ttu-id="bc592-119">Reinstallare i certificati.</span><span class="sxs-lookup"><span data-stu-id="bc592-119">Reinstall certificates.</span></span>

  - <span data-ttu-id="bc592-120">Se il server ha ospitato un database, installare Microsoft SQL Server 2012 o Microsoft SQL Server 2008 R2.</span><span class="sxs-lookup"><span data-stu-id="bc592-120">If the server hosted a database, install Microsoft SQL Server 2012 or Microsoft SQL Server 2008 R2.</span></span>

  - <span data-ttu-id="bc592-121">In generale, se il server ha ospitato un database, eseguire Generatore di topologie per creare e installare il database e configurare gli elenchi di controllo di accesso (ACL).</span><span class="sxs-lookup"><span data-stu-id="bc592-121">In general, if the server hosted a database, run Topology Builder to create and install the database and set up access control lists (ACLs).</span></span>

  - <span data-ttu-id="bc592-122">In generale, se il server ha ospitato un ruolo del server, eseguire il passaggio 1 al passaggio 4 della distribuzione guidata di Lync Server per installare i file di configurazione locali, installare i componenti del ruolo del server, assegnare i certificati e avviare i servizi.</span><span class="sxs-lookup"><span data-stu-id="bc592-122">In general, if the server hosted a server role, run step 1 through step 4 of the Lync Server Deployment Wizard to install the local configuration files, install the server role components, assign certificates, and start the services.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="bc592-123">Se il server ha ospitato un database collocato con il ruolo del server, l'applicazione del passaggio 2 della distribuzione guidata di Lync Server ricrea il database.</span><span class="sxs-lookup"><span data-stu-id="bc592-123">If the server hosted a database collocated with the server role, running step 2 of the Lync Server Deployment Wizard recreates the database.</span></span>

    
    </div>

  - <span data-ttu-id="bc592-124">Se il server ha ospitato un database, ripristinare i dati di cui è stato eseguito il backup.</span><span class="sxs-lookup"><span data-stu-id="bc592-124">If the server hosted a database, restore the backed up data.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

