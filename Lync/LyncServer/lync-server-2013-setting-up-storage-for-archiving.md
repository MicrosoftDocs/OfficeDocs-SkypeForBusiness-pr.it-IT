---
title: "Lync Server 2013: configurazione dello spazio di archiviazione per l'archiviazione"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up storage for Archiving
ms:assetid: f751245c-743e-454f-8325-968ae5e3de71
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205392(v=OCS.15)
ms:contentKeyID: 48185858
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6f299b01b95cddd461893b35518e3c2fe40c694
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-storage-for-archiving-in-lync-server-2013"></a><span data-ttu-id="f980e-102">Configurazione dello spazio di archiviazione per l'archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f980e-102">Setting up storage for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f980e-103">_**Ultimo argomento modificato:** 2013-12-17_</span><span class="sxs-lookup"><span data-stu-id="f980e-103">_**Topic Last Modified:** 2013-12-17_</span></span>

<span data-ttu-id="f980e-104">Lo spazio di archiviazione per Lync Server 2013 include gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f980e-104">Archiving storage for Lync Server 2013 includes the following:</span></span>

  - <span data-ttu-id="f980e-105">\*\*\*\*   Archiviazione dei dati di archiviazione dei dati è necessario per archiviare il contenuto di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="f980e-105">**Data storage**   Data storage is required to store IM content.</span></span>

  - <span data-ttu-id="f980e-106">\*\*\*\* Archiviazione file di archiviazione file è necessario per archiviare l'archiviazione dei dati del contenuto e la conservazione delle conferenze (riunioni).   </span><span class="sxs-lookup"><span data-stu-id="f980e-106">**File storage**   File storage is required to store conferencing (meeting) content data storage and file storage.</span></span>

<div>

## <a name="setting-up-data-storage"></a><span data-ttu-id="f980e-107">Configurazione dell'archivio dati</span><span class="sxs-lookup"><span data-stu-id="f980e-107">Setting Up Data Storage</span></span>

<span data-ttu-id="f980e-108">I requisiti per la configurazione dell'archiviazione dei dati per l'archiviazione in Lync Server 2013 dipendono dal modo in cui si desidera archiviare i dati di archiviazione:</span><span class="sxs-lookup"><span data-stu-id="f980e-108">Requirements for setting up data storage for Archiving in Lync Server 2013 depend on how you want to store archiving data:</span></span>

  - <span data-ttu-id="f980e-109">Integrazione dell'archiviazione di Lync Server 2013 con la distribuzione di Exchange per archiviare i dati di archiviazione mediante l'archiviazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="f980e-109">Integrate Lync Server 2013 Archiving with your Exchange deployment to store Archiving data using Exchange storage.</span></span>

  - <span data-ttu-id="f980e-110">Impostare i server di database di SQL Server separati per archiviare i dati di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f980e-110">Set up separate SQL Server database servers to store Archiving data.</span></span>

<div>

## <a name="setting-up-exchange-storage-for-archiving-data"></a><span data-ttu-id="f980e-111">Configurazione dell'archiviazione di Exchange per l'archiviazione dei dati</span><span class="sxs-lookup"><span data-stu-id="f980e-111">Setting Up Exchange Storage for Archiving Data</span></span>

<span data-ttu-id="f980e-112">La configurazione di Exchange per l'archiviazione dei dati di archiviazione richiede che la distribuzione di Exchange esegua Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="f980e-112">Setting up Exchange for storage of Archiving data requires that your Exchange deployment is running Exchange 2013.</span></span> <span data-ttu-id="f980e-113">Inoltre, le cassette postali degli utenti devono essere ospitate nel server Exchange 2013 e le relative cassette postali devono essere conservate sul posto.</span><span class="sxs-lookup"><span data-stu-id="f980e-113">Additionally, user mailboxes must be homed on the Exchange 2013 server and their mailboxes must be put on In-Place Hold.</span></span> <span data-ttu-id="f980e-114">Per informazioni dettagliate sulla configurazione di Exchange 2013, vedere la documentazione del prodotto Exchange.</span><span class="sxs-lookup"><span data-stu-id="f980e-114">For details about configuring Exchange 2013, see the Exchange product documentation.</span></span>

</div>

<div>

## <a name="setting-up-sql-server-database-servers-for-storage-of-archiving-data"></a><span data-ttu-id="f980e-115">Configurazione dei server database di SQL Server per l'archiviazione dei dati</span><span class="sxs-lookup"><span data-stu-id="f980e-115">Setting Up SQL Server Database Servers for Storage of Archiving Data</span></span>

<span data-ttu-id="f980e-116">L'archiviazione in Lync Server 2013 richiede che il software di database di SQL Server memorizzi i dati archiviati, a meno che non si integri la distribuzione con Exchange.</span><span class="sxs-lookup"><span data-stu-id="f980e-116">Archiving in Lync Server 2013 requires the SQL Server database software to store the archived data, unless you integrate your deployment with Exchange.</span></span>

<span data-ttu-id="f980e-117">Per i database di archiviazione di SQL Server, è necessario installare SQL Server nel computer che ospiterà il database di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f980e-117">For SQL Server archiving databases, you must install SQL Server on the computer that will host the Archiving database.</span></span> <span data-ttu-id="f980e-118">È possibile utilizzare la stessa istanza SQL utilizzata per il database back-end di un pool Front End.</span><span class="sxs-lookup"><span data-stu-id="f980e-118">You can use the same SQL instance that you use for the back-end database of a Front End pool.</span></span> <span data-ttu-id="f980e-119">Per ottenere prestazioni ottimali, è consigliabile distribuire il database di archiviazione in un computer distinto dall'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="f980e-119">For best performance, you should deploy the Archiving database on a computer that is separate from the Central Management store.</span></span> <span data-ttu-id="f980e-120">Per informazioni dettagliate sulla collocazione dei componenti di Lync Server 2013, vedere [supported server Collocation in Lync server 2013](lync-server-2013-supported-server-collocation.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="f980e-120">For details about collocating Lync Server 2013 components, see [Supported server collocation in Lync Server 2013](lync-server-2013-supported-server-collocation.md) in the Supportability documentation.</span></span>

<span data-ttu-id="f980e-121">Ogni server di database deve eseguire una versione supportata di SQL Server.</span><span class="sxs-lookup"><span data-stu-id="f980e-121">Each database server must be running a supported version of SQL Server.</span></span> <span data-ttu-id="f980e-122">Per informazioni dettagliate sulle versioni supportate, vedere [Technical Requirements for archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="f980e-122">For details about the supported versions, see [Technical requirements for Archiving in Lync Server 2013](lync-server-2013-technical-requirements-for-archiving.md) in the Planning documentation.</span></span>

<span data-ttu-id="f980e-123">È necessario configurare le piattaforme SQL Server prima di distribuire e abilitare l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f980e-123">You must set up the SQL Server platforms prior to deploying and enabling Archiving.</span></span> <span data-ttu-id="f980e-124">Se l'account utilizzato per pubblicare la topologia dispone delle autorizzazioni e dei diritti di amministratore appropriati, è possibile creare il database di archiviazione (LcsLog) quando si pubblica la topologia.</span><span class="sxs-lookup"><span data-stu-id="f980e-124">If the account to be used to publish the topology has the appropriate administrator rights and permissions, you can create the Archiving database (LcsLog) when you publish your topology.</span></span> <span data-ttu-id="f980e-125">È inoltre possibile creare il database in un secondo momento, come parte della procedura di installazione.</span><span class="sxs-lookup"><span data-stu-id="f980e-125">You can also create the database later, including as part of the installation procedure.</span></span> <span data-ttu-id="f980e-126">Per informazioni dettagliate su SQL Server, vedere il sito Web di [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045)SQL Server TechCenter all'indirizzo.</span><span class="sxs-lookup"><span data-stu-id="f980e-126">For details about SQL Server, see the SQL Server TechCenter at [https://go.microsoft.com/fwlink/p/?linkID=129045](https://go.microsoft.com/fwlink/p/?linkid=129045).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="f980e-127">Verificare che il tipo di avvio del servizio SQL Server Agent sia automatico e che il servizio SQL Server Agent sia in esecuzione per l'istanza di SQL che contiene il database di archiviazione, in modo che il processo di manutenzione di SQL Server predefinito di archiviazione possa essere eseguito nella sua base pianificata nell'ambito del controllo del servizio SQL Server Agent.</span><span class="sxs-lookup"><span data-stu-id="f980e-127">Ensure that the SQL Server Agent Service Startup Type is Automatic and the SQL Server Agent Service is running for the SQL Instance which is holding the Archiving database, so that the Default Archiving SQL Server Maintenance Job can run on its scheduled basis under the control of the SQL Server Agent Service.</span></span>



</div>

</div>

</div>

<div>

## <a name="setting-up-file-storage"></a><span data-ttu-id="f980e-128">Configurazione dell'archiviazione dei file</span><span class="sxs-lookup"><span data-stu-id="f980e-128">Setting Up File Storage</span></span>

<span data-ttu-id="f980e-129">L'archiviazione utilizza la condivisione file di Lync Server 2013 specificata durante la configurazione del pool Front end o del server Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="f980e-129">Archiving uses the Lync Server 2013 file share that you specified when you set up your Front End pool or Standard Edition server.</span></span> <span data-ttu-id="f980e-130">Non è possibile modificare la condivisione di file utilizzata per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f980e-130">You cannot change the file share used for Archiving.</span></span> <span data-ttu-id="f980e-131">Per informazioni dettagliate sui sistemi di archiviazione dei file supportati, vedere [file Storage Support in Lync Server 2013](lync-server-2013-file-storage-support.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="f980e-131">For details about supported file storage systems, see [File storage support in Lync Server 2013](lync-server-2013-file-storage-support.md) in the Supportability documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

