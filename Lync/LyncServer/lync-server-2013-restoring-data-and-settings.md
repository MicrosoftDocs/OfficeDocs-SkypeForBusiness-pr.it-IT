---
title: 'Lync Server 2013: ripristino di dati e impostazioni'
description: 'Lync Server 2013: ripristino di dati e impostazioni.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Restoring data and settings
ms:assetid: b07f5dd7-7bed-4819-8cb5-617f5acd478e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202185(v=OCS.15)
ms:contentKeyID: 51541503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 694b1e362d729d354b08367d31c47e8ca866dd91
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48560292"
---
# <a name="restoring-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="444ae-103">Ripristino dei dati e delle impostazioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="444ae-103">Restoring data and settings in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="444ae-104">_**Ultimo argomento modificato:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="444ae-104">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="444ae-105">Se è stata implementata una topologia di ripristino di emergenza con pool associati e uno di questi pool Front End è diminuito ed è necessario ripristinare rapidamente il servizio agli utenti, vedere [failover di un pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="444ae-105">If you have implemented a disaster recovery topology with paired pools, and one of those Front End pools has gone down and you need to quickly restore service to your users, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="444ae-106">In caso contrario, utilizzare le informazioni contenute negli argomenti seguenti, insieme ai fogli di lavoro nei fogli di lavoro di [backup e ripristino per Lync server 2013](lync-server-2013-backup-and-restoration-worksheets.md), per ripristinare Lync Server dopo un errore o un'interruzione.</span><span class="sxs-lookup"><span data-stu-id="444ae-106">Otherwise, use the information in the following topics, along with the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md), to restore Lync Server after a failure or outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="444ae-107">Per ridurre i tempi di inattività e la perdita di dati, eseguire le procedure di ripristino descritte in questo documento solo se le procedure per la risoluzione dei problemi non sono efficaci per identificare e correggere il problema.</span><span class="sxs-lookup"><span data-stu-id="444ae-107">To reduce downtime and potential data loss, perform the restoration procedures described in this document only if troubleshooting procedures are not effective in identifying and correcting the problem.</span></span> <span data-ttu-id="444ae-108">Durante la risoluzione dei problemi, provare a ridurre al minimo l'impatto su altri server e componenti durante l'arresto e il riavvio del server.</span><span class="sxs-lookup"><span data-stu-id="444ae-108">During troubleshooting, try to minimize the impact on other servers and components as you shut down and restart servers.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="444ae-109">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="444ae-109">In This Section</span></span>

  - [<span data-ttu-id="444ae-110">Preparazione per il ripristino di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="444ae-110">Preparing to restore Lync Server 2013</span></span>](lync-server-2013-preparing-to-restore-lync-server.md)

  - [<span data-ttu-id="444ae-111">Ripristino di un server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="444ae-111">Restoring a Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-restoring-a-standard-edition-server.md)

  - [<span data-ttu-id="444ae-112">Ripristino del server che ospita l'archivio di gestione centrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="444ae-112">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)

  - [<span data-ttu-id="444ae-113">Ripristino di un server back-end Enterprise Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="444ae-113">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)

  - [<span data-ttu-id="444ae-114">Ripristino di un server membro Enterprise Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="444ae-114">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

  - [<span data-ttu-id="444ae-115">Ripristino di un pool di Lync Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="444ae-115">Restoring a Lync Server pool in Lync Server 2013</span></span>](lync-server-2013-restoring-a-lync-server-pool.md)

  - [<span data-ttu-id="444ae-116">Esecuzione di un failover del pool ABC front end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="444ae-116">Performing an ABC Front End pool failover in Lync Server 2013</span></span>](lync-server-2013-performing-an-abc-front-end-pool-failover.md)

  - [<span data-ttu-id="444ae-117">Ripristino di un archivio file in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="444ae-117">Restoring a file store in Lync Server 2013</span></span>](lync-server-2013-restoring-a-file-store.md)

  - [<span data-ttu-id="444ae-118">Ripristino dei dati di monitoraggio o archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="444ae-118">Restoring monitoring or archiving data in Lync Server 2013</span></span>](lync-server-2013-restoring-monitoring-or-archiving-data.md)

  - [<span data-ttu-id="444ae-119">Ripristino dei dati di chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="444ae-119">Restoring Persistent Chat data in Lync Server 2013</span></span>](lync-server-2013-restoring-persistent-chat-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

