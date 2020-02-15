---
title: 'Lync Server 2013: ripristino di dati e impostazioni'
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
ms.openlocfilehash: e5b8575ee1362b240df0bfc0a1a1a6b27afde268
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="cd6c6-102">Ripristino dei dati e delle impostazioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd6c6-102">Restoring data and settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd6c6-103">_**Ultimo argomento modificato:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="cd6c6-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="cd6c6-104">Se è stata implementata una topologia di ripristino di emergenza con pool associati e uno di questi pool Front End è diminuito ed è necessario ripristinare rapidamente il servizio agli utenti, vedere [failover di un pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="cd6c6-104">If you have implemented a disaster recovery topology with paired pools, and one of those Front End pools has gone down and you need to quickly restore service to your users, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="cd6c6-105">In caso contrario, utilizzare le informazioni contenute negli argomenti seguenti, insieme ai fogli di lavoro nei fogli di lavoro di [backup e ripristino per Lync server 2013](lync-server-2013-backup-and-restoration-worksheets.md), per ripristinare Lync Server dopo un errore o un'interruzione.</span><span class="sxs-lookup"><span data-stu-id="cd6c6-105">Otherwise, use the information in the following topics, along with the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md), to restore Lync Server after a failure or outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="cd6c6-106">Per ridurre i tempi di inattività e la perdita di dati, eseguire le procedure di ripristino descritte in questo documento solo se le procedure per la risoluzione dei problemi non sono efficaci per identificare e correggere il problema.</span><span class="sxs-lookup"><span data-stu-id="cd6c6-106">To reduce downtime and potential data loss, perform the restoration procedures described in this document only if troubleshooting procedures are not effective in identifying and correcting the problem.</span></span> <span data-ttu-id="cd6c6-107">Durante la risoluzione dei problemi, provare a ridurre al minimo l'impatto su altri server e componenti durante l'arresto e il riavvio del server.</span><span class="sxs-lookup"><span data-stu-id="cd6c6-107">During troubleshooting, try to minimize the impact on other servers and components as you shut down and restart servers.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cd6c6-108">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="cd6c6-108">In This Section</span></span>

  - [<span data-ttu-id="cd6c6-109">Preparazione per il ripristino di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd6c6-109">Preparing to restore Lync Server 2013</span></span>](lync-server-2013-preparing-to-restore-lync-server.md)

  - [<span data-ttu-id="cd6c6-110">Ripristino di un server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd6c6-110">Restoring a Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-restoring-a-standard-edition-server.md)

  - [<span data-ttu-id="cd6c6-111">Ripristino del server che ospita l'archivio di gestione centrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd6c6-111">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)

  - [<span data-ttu-id="cd6c6-112">Ripristino di un server back-end Enterprise Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd6c6-112">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)

  - [<span data-ttu-id="cd6c6-113">Ripristino di un server membro Enterprise Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd6c6-113">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

  - [<span data-ttu-id="cd6c6-114">Ripristino di un pool di Lync Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd6c6-114">Restoring a Lync Server pool in Lync Server 2013</span></span>](lync-server-2013-restoring-a-lync-server-pool.md)

  - [<span data-ttu-id="cd6c6-115">Esecuzione di un failover del pool ABC front end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd6c6-115">Performing an ABC Front End pool failover in Lync Server 2013</span></span>](lync-server-2013-performing-an-abc-front-end-pool-failover.md)

  - [<span data-ttu-id="cd6c6-116">Ripristino di un archivio file in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd6c6-116">Restoring a file store in Lync Server 2013</span></span>](lync-server-2013-restoring-a-file-store.md)

  - [<span data-ttu-id="cd6c6-117">Ripristino dei dati di monitoraggio o archiviazione in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd6c6-117">Restoring monitoring or archiving data in Lync Server 2013</span></span>](lync-server-2013-restoring-monitoring-or-archiving-data.md)

  - [<span data-ttu-id="cd6c6-118">Ripristino dei dati di chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cd6c6-118">Restoring Persistent Chat data in Lync Server 2013</span></span>](lync-server-2013-restoring-persistent-chat-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

