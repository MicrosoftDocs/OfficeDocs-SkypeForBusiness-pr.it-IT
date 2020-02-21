---
title: 'Fase 8: rimuovere i pool legacy'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 8: Decommission legacy pools'
ms:assetid: 1c68e5d8-fb5f-45e6-b6e3-27f5e830c966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204724(v=OCS.15)
ms:contentKeyID: 48183557
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 474cc5ee3f508ed5a9069f3e8625bcc6ee451153
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209492"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="282a1-102">Fase 8: rimuovere i pool legacy</span><span class="sxs-lookup"><span data-stu-id="282a1-102">Phase 8: Decommission legacy pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="282a1-103">_**Ultimo argomento modificato:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="282a1-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="282a1-104">Nell'argomento seguente vengono fornite indicazioni per l'aggiornamento delle voci DNS, lo spostamento del server di gestione del contenuto, la rimozione delle autorizzazioni dei pool e la disattivazione di server e pool da una distribuzione legacy di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="282a1-104">The following topic provides guidance in updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Lync Server 2010.</span></span> <span data-ttu-id="282a1-105">Non tutte le procedure elencate in questa sezione sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="282a1-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="282a1-106">Leggere la documentazione e determinare quale procedura di rimozione utilizzare.</span><span class="sxs-lookup"><span data-stu-id="282a1-106">Read the documentation and determine which decommissioning procedure to use.</span></span>

<span data-ttu-id="282a1-107">Per una copertura esaustiva sulla rimozione di server e ruoli del server di Lync Server 2010 e una guida dettagliata per rimuovere una distribuzione di Lync Server 2010, vedere la sezione relativa alla disinstallazione di Microsoft Lync Server 2010 e alla rimozione dei ruoli del server, che [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)possono essere scaricati in.</span><span class="sxs-lookup"><span data-stu-id="282a1-107">For exhaustive coverage of removing Lync Server 2010 servers and server roles, and a step-by-step guide to decommissioning a Lync Server 2010 deployment, see "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="282a1-108">Per informazioni su come eseguire la migrazione e l'aggiornamento delle applicazioni Microsoft Unified Communications Managed API (UCMA), prima di rimuovere l'ambiente legacy, vedere<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="282a1-108">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="282a1-109">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="282a1-109">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="282a1-110">Aggiornare i record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="282a1-110">Update DNS SRV records</span></span>](update-dns-srv-records.md)

  - <span></span>  
    [<span data-ttu-id="282a1-111">Spostare il server di gestione centrale Lync Server 2010 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="282a1-111">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>](move-the-lync-server-2010-central-management-server-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="282a1-112">Spostare le directory conferenze</span><span class="sxs-lookup"><span data-stu-id="282a1-112">Move Conference Directories</span></span>](move-lync-server-2010-conference-directories-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="282a1-113">Rimuovere l'associazione del server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="282a1-113">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)

  - <span></span>  
    [<span data-ttu-id="282a1-114">Rimuovere l'associazione di Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="282a1-114">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)

  - <span></span>  
    [<span data-ttu-id="282a1-115">Rimuovere Enterprise Edition Front End Server o Standard Edition Front End Server</span><span class="sxs-lookup"><span data-stu-id="282a1-115">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-enterprise-edition-front-end-server-or-standard-edition-front-end-server.md)

  - <span></span>  
    [<span data-ttu-id="282a1-116">Rimuovere le istanze e i database di SQL Server nel server back-end</span><span class="sxs-lookup"><span data-stu-id="282a1-116">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

