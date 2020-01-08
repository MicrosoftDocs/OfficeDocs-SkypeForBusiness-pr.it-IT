---
title: 'Lync Server 2013: ripristino di dati e impostazioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring data and settings
ms:assetid: b07f5dd7-7bed-4819-8cb5-617f5acd478e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202185(v=OCS.15)
ms:contentKeyID: 51541503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b7562e0899a5129832ef4651c041b8c7daf545e7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-data-and-settings-in-lync-server-2013"></a><span data-ttu-id="fce7a-102">Ripristino di dati e impostazioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce7a-102">Restoring data and settings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fce7a-103">_**Argomento Ultima modifica:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="fce7a-103">_**Topic Last Modified:** 2013-02-17_</span></span>

<span data-ttu-id="fce7a-104">Se è stata implementata una topologia di ripristino di emergenza con pool associati e uno di questi pool di front-end è diminuito ed è necessario ripristinare rapidamente il servizio agli utenti, vedere [mancanza di un pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span><span class="sxs-lookup"><span data-stu-id="fce7a-104">If you have implemented a disaster recovery topology with paired pools, and one of those Front End pools has gone down and you need to quickly restore service to your users, see [Failing over a pool in Lync Server 2013](lync-server-2013-failing-over-a-pool.md).</span></span> <span data-ttu-id="fce7a-105">In caso contrario, usare le informazioni degli argomenti seguenti, insieme ai fogli di lavoro nei fogli di lavoro di [backup e ripristino per Lync server 2013](lync-server-2013-backup-and-restoration-worksheets.md), per ripristinare Lync Server dopo un errore o un'interruzione.</span><span class="sxs-lookup"><span data-stu-id="fce7a-105">Otherwise, use the information in the following topics, along with the worksheets in [Backup and restoration worksheets for Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md), to restore Lync Server after a failure or outage.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="fce7a-106">Per ridurre i tempi di inattività e le potenziali perdite di dati, eseguire le procedure di ripristino descritte in questo documento solo se le procedure di risoluzione dei problemi non sono efficaci per identificare e correggere il problema.</span><span class="sxs-lookup"><span data-stu-id="fce7a-106">To reduce downtime and potential data loss, perform the restoration procedures described in this document only if troubleshooting procedures are not effective in identifying and correcting the problem.</span></span> <span data-ttu-id="fce7a-107">Durante la risoluzione dei problemi, provare a ridurre al minimo l'impatto su altri server e componenti mentre si arrestano e si riavviano i server.</span><span class="sxs-lookup"><span data-stu-id="fce7a-107">During troubleshooting, try to minimize the impact on other servers and components as you shut down and restart servers.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fce7a-108">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="fce7a-108">In This Section</span></span>

  - [<span data-ttu-id="fce7a-109">Preparazione per il ripristino di Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce7a-109">Preparing to restore Lync Server 2013</span></span>](lync-server-2013-preparing-to-restore-lync-server.md)

  - [<span data-ttu-id="fce7a-110">Ripristino di un server Standard Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce7a-110">Restoring a Standard Edition server in Lync Server 2013</span></span>](lync-server-2013-restoring-a-standard-edition-server.md)

  - [<span data-ttu-id="fce7a-111">Ripristino del server che ospita l'archivio di gestione centrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce7a-111">Restoring the server hosting the Central Management store in Lync Server 2013</span></span>](lync-server-2013-restoring-the-server-hosting-the-central-management-store.md)

  - [<span data-ttu-id="fce7a-112">Ripristino di un server back-end Enterprise Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce7a-112">Restoring an Enterprise Edition Back End Server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-back-end-server.md)

  - [<span data-ttu-id="fce7a-113">Ripristino di un server membro di Enterprise Edition in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce7a-113">Restoring an Enterprise Edition member server in Lync Server 2013</span></span>](lync-server-2013-restoring-an-enterprise-edition-member-server.md)

  - [<span data-ttu-id="fce7a-114">Ripristino di un pool di Lync Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce7a-114">Restoring a Lync Server pool in Lync Server 2013</span></span>](lync-server-2013-restoring-a-lync-server-pool.md)

  - [<span data-ttu-id="fce7a-115">Esecuzione di un failover del pool di front end ABC in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce7a-115">Performing an ABC Front End pool failover in Lync Server 2013</span></span>](lync-server-2013-performing-an-abc-front-end-pool-failover.md)

  - [<span data-ttu-id="fce7a-116">Ripristino di un archivio di file in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce7a-116">Restoring a file store in Lync Server 2013</span></span>](lync-server-2013-restoring-a-file-store.md)

  - [<span data-ttu-id="fce7a-117">Ripristinare il monitoraggio o l'archiviazione dei dati in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce7a-117">Restoring monitoring or archiving data in Lync Server 2013</span></span>](lync-server-2013-restoring-monitoring-or-archiving-data.md)

  - [<span data-ttu-id="fce7a-118">Ripristino dei dati della chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fce7a-118">Restoring Persistent Chat data in Lync Server 2013</span></span>](lync-server-2013-restoring-persistent-chat-data.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

