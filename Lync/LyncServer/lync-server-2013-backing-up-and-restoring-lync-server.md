---
title: 'Lync Server 2013: backup e ripristino di Lync Server'
description: 'Lync Server 2013: backup e ripristino di Lync Server.'
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
ms.openlocfilehash: c1a7024b2264fb895d1562a6da0775f9397644b4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543782"
---
# <a name="backing-up-and-restoring-lync-server-2013"></a><span data-ttu-id="c51a4-103">Backup e ripristino di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c51a4-103">Backing up and restoring Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c51a4-104">_**Ultimo argomento modificato:** 2013-02-21_</span><span class="sxs-lookup"><span data-stu-id="c51a4-104">_**Topic Last Modified:** 2013-02-21_</span></span>

<span data-ttu-id="c51a4-105">In questa sezione sono disponibili le procedure consigliate per il backup dei dati di Lync Server 2013 e per il ripristino in caso di errore.</span><span class="sxs-lookup"><span data-stu-id="c51a4-105">In this section, you’ll find the best practices for backing up your Lync Server 2013 data, and for restoring it if you have a failure.</span></span> <span data-ttu-id="c51a4-106">Queste procedure consigliate sono valide per le situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c51a4-106">These best practices apply to the following situations:</span></span>

  - <span data-ttu-id="c51a4-107">Un intero pool di Lync Server di qualsiasi tipo (front end server, server perimetrale, Mediation Server, server Chat persistente o Director) oppure un singolo server in uno di questi pool.</span><span class="sxs-lookup"><span data-stu-id="c51a4-107">An entire Lync Server pool of any type (Front End Server, Edge Server, Mediation Server, Persistent Chat Server, or Director), or an individual server in one of these pools.</span></span>

  - <span data-ttu-id="c51a4-108">Server di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="c51a4-108">The Central Management Server</span></span>

  - <span data-ttu-id="c51a4-109">Un server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="c51a4-109">A Standard Edition server</span></span>

  - <span data-ttu-id="c51a4-110">Server back-end Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="c51a4-110">An Enterprise Edition Back End Server</span></span>

  - <span data-ttu-id="c51a4-111">Archivio file</span><span class="sxs-lookup"><span data-stu-id="c51a4-111">A File Store</span></span>

  - <span data-ttu-id="c51a4-112">Database di archiviazione, database di monitoraggio o database di chat persistente</span><span class="sxs-lookup"><span data-stu-id="c51a4-112">An Archiving database, Monitoring database, or Persistent Chat database</span></span>

<span data-ttu-id="c51a4-113">In questa sezione non sono incluse informazioni relative al ripristino di un intero sito o allo sviluppo di un sito di standby.</span><span class="sxs-lookup"><span data-stu-id="c51a4-113">This section does not include information about restoring an entire site or for developing a standby site.</span></span> <span data-ttu-id="c51a4-114">Per informazioni dettagliate sullo sviluppo di una soluzione di ripristino di emergenza con pool Front End abbinati, vedere [Planning for High Availability and Disaster Recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="c51a4-114">For details about developing a disaster recovery solution with paired Front End pools, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span> <span data-ttu-id="c51a4-115">Si tratta del metodo consigliato per la pianificazione del ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="c51a4-115">This is the recommended method for planning for disaster recovery.</span></span>

<span data-ttu-id="c51a4-116">Se i pool Front End associati sono stati distribuiti, se uno di questi pool ha esito negativo e diventa irrecuperabile, è possibile ripristinare il pool con un nuovo nome di dominio completo (FQDN) dal pool associato.</span><span class="sxs-lookup"><span data-stu-id="c51a4-116">If you have deployed paired Front End pools, if one of these pools fails and becomes unrecoverable, you can restore this pool with a new fully qualified domain name (FQDN) from its paired pool.</span></span> <span data-ttu-id="c51a4-117">Per informazioni dettagliate sulla procedura per eseguire questo ripristino, vedere [failover di un pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="c51a4-117">For details on the steps to perform this recovery, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="c51a4-118">Inoltre, se si desidera ricreare un pool non riuscito e irrecuperabile che faceva parte di una coppia front end, è possibile utilizzare la procedura descritta in [esecuzione di un failover del pool ABC front end in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span><span class="sxs-lookup"><span data-stu-id="c51a4-118">Additionally, if you later want to recreate a failed and unrecoverable pool that was part of a Front End pair, you can use the steps in [Performing an ABC Front End pool failover in Lync Server 2013](lync-server-2013-performing-an-abc-front-end-pool-failover.md).</span></span>

<span data-ttu-id="c51a4-119">La metodologia descritta in questo documento implica considerazioni speciali durante la fase di pianificazione.</span><span class="sxs-lookup"><span data-stu-id="c51a4-119">The methodology described in this document involves special considerations during the planning phase.</span></span> <span data-ttu-id="c51a4-120">Per informazioni dettagliate, vedere [establishing a backup and Restoration Plan for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span><span class="sxs-lookup"><span data-stu-id="c51a4-120">For details, see [Establishing a backup and restoration plan for Lync Server 2013](lync-server-2013-establishing-a-backup-and-restoration-plan.md).</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c51a4-121">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="c51a4-121">In This Section</span></span>

  - [<span data-ttu-id="c51a4-122">Preparazione per il backup e il ripristino di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c51a4-122">Preparing for Lync Server 2013 backup and restoration</span></span>](lync-server-2013-preparing-for-lync-server-backup-and-restoration.md)

  - [<span data-ttu-id="c51a4-123">Backup dei dati e delle impostazioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c51a4-123">Backing up data and settings in Lync Server 2013</span></span>](lync-server-2013-backing-up-data-and-settings.md)

  - [<span data-ttu-id="c51a4-124">Ripristino dei dati e delle impostazioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c51a4-124">Restoring data and settings in Lync Server 2013</span></span>](lync-server-2013-restoring-data-and-settings.md)

  - [<span data-ttu-id="c51a4-125">Fogli di lavoro per il backup e il ripristino di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c51a4-125">Backup and restoration worksheets for Lync Server 2013</span></span>](lync-server-2013-backup-and-restoration-worksheets.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

