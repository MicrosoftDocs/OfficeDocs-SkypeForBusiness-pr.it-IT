---
title: 'Lync Server 2013: eseguire il backup e il ripristino di Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Backing up and restoring Lync Server 2013
ms:assetid: 07dc1f5e-af66-4e18-bf39-881dceff8bc3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202160(v=OCS.15)
ms:contentKeyID: 51541443
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 43a96f47bfe9d28fdbc37eea0ae62ef6cd763098
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41740146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="backing-up-and-restoring-lync-server-2013"></a><span data-ttu-id="e5000-102">Backup e ripristino di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5000-102">Backing up and restoring Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e5000-103">_**Argomento Ultima modifica:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="e5000-103">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="e5000-104">In questa sezione sono disponibili le procedure consigliate per eseguire il backup dei dati di Lync Server 2013 e per ripristinarlo in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="e5000-104">In this section, you’ll find the best practices for backing up your Lync Server 2013 data, and for restoring it if you have a failure.</span></span> <span data-ttu-id="e5000-105">Queste procedure consigliate si applicano alle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e5000-105">These best practices apply to the following situations:</span></span>

  - <span data-ttu-id="e5000-106">Un intero pool di Lync Server di qualsiasi tipo (front end server, Edge Server, Mediation Server, Persistent Chat Server o Director) o un singolo server in uno di questi pool.</span><span class="sxs-lookup"><span data-stu-id="e5000-106">An entire Lync Server pool of any type (Front End Server, Edge Server, Mediation Server, Persistent Chat Server, or Director), or an individual server in one of these pools.</span></span>

  - <span data-ttu-id="e5000-107">Server di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="e5000-107">The Central Management Server</span></span>

  - <span data-ttu-id="e5000-108">Un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="e5000-108">A Standard Edition server</span></span>

  - <span data-ttu-id="e5000-109">Server back-end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e5000-109">An Enterprise Edition Back End Server</span></span>

  - <span data-ttu-id="e5000-110">Un archivio di file</span><span class="sxs-lookup"><span data-stu-id="e5000-110">A File Store</span></span>

  - <span data-ttu-id="e5000-111">Database di archiviazione, database di monitoraggio o database di chat persistente</span><span class="sxs-lookup"><span data-stu-id="e5000-111">An Archiving database, Monitoring database, or Persistent Chat database</span></span>

<span data-ttu-id="e5000-112">Questa sezione non include informazioni sul ripristino di un intero sito o per lo sviluppo di un sito standby.</span><span class="sxs-lookup"><span data-stu-id="e5000-112">This section does not include information about restoring an entire site or for developing a standby site.</span></span> <span data-ttu-id="e5000-113">Per informazioni dettagliate sullo sviluppo di una soluzione di ripristino di emergenza con pool Front-End associati, vedere [pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="e5000-113">For details about developing a disaster recovery solution with paired Front End pools, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="e5000-114">Questo è il metodo consigliato per pianificare il ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="e5000-114">This is the recommended method for planning for disaster recovery.</span></span>

<span data-ttu-id="e5000-115">Se sono stati distribuiti pool Front-End associati, se uno di questi pool non riesce e diventa irrecuperabile, è possibile ripristinare questo pool con un nuovo nome di dominio completo (FQDN) dal pool associato.</span><span class="sxs-lookup"><span data-stu-id="e5000-115">If you have deployed paired Front End pools, if one of these pools fails and becomes unrecoverable, you can restore this pool with a new fully qualified domain name (FQDN) from its paired pool.</span></span> <span data-ttu-id="e5000-116">Per informazioni dettagliate sui passaggi per eseguire questo ripristino, vedere [mancanza di un pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="e5000-116">For details on the steps to perform this recovery, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="e5000-117">Inoltre, se in seguito si vuole ricreare un pool non riuscito e non recuperabile che faceva parte di una coppia front-end, è possibile usare la procedura descritta in [esecuzione di un failover del pool di front end ABC in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span><span class="sxs-lookup"><span data-stu-id="e5000-117">Additionally, if you later want to recreate a failed and unrecoverable pool that was part of a Front End pair, you can use the steps in [Performing an ABC Front End pool failover in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span></span>

<span data-ttu-id="e5000-118">La metodologia descritta in questo documento comporta considerazioni particolari durante la fase di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="e5000-118">The methodology described in this document involves special considerations during the planning phase.</span></span> <span data-ttu-id="e5000-119">Per informazioni dettagliate, vedere [creazione di un piano di backup e ripristino per Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span><span class="sxs-lookup"><span data-stu-id="e5000-119">For details, see [Establishing a backup and restoration plan for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e5000-120">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="e5000-120">In This Section</span></span>

  - [<span data-ttu-id="e5000-121">Preparazione per il backup e il ripristino di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5000-121">Preparing for Lync Server 2013 backup and restoration</span></span>](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [<span data-ttu-id="e5000-122">Backup dei dati e delle impostazioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5000-122">Backing up data and settings in Lync Server 2013</span></span>](lync-server-2013-backing-up-data-and-settings.md)

  - [<span data-ttu-id="e5000-123">Ripristino di dati e impostazioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5000-123">Restoring data and settings in Lync Server 2013</span></span>](lync-server-2013-restoring-data-and-settings.md)

  - [<span data-ttu-id="e5000-124">Fogli di lavoro di backup e ripristino per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e5000-124">Backup and restoration worksheets for Lync Server 2013</span></span>](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

