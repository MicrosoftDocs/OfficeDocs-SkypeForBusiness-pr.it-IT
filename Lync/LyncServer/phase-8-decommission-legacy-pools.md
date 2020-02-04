---
title: 'Fase 8: rimuovere le autorizzazioni dei pool legacy'
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
ms.openlocfilehash: a9c21aa29f2e98aacd3ec68076a21ba2b4d2a76e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729076"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="fbd7d-102">Fase 8: rimuovere le autorizzazioni dei pool legacy</span><span class="sxs-lookup"><span data-stu-id="fbd7d-102">Phase 8: Decommission legacy pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fbd7d-103">_**Argomento Ultima modifica:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="fbd7d-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="fbd7d-104">L'argomento seguente fornisce indicazioni per l'aggiornamento delle voci DNS, lo spostamento del server di gestione del contenuto, lo smantellamento dei pool e la disattivazione e la rimozione di server e pool da una distribuzione legacy di Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="fbd7d-104">The following topic provides guidance in updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Lync Server 2010.</span></span> <span data-ttu-id="fbd7d-105">Non tutte le procedure elencate in questa sezione sono obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="fbd7d-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="fbd7d-106">Leggere la documentazione e determinare la procedura di disattivazione da usare.</span><span class="sxs-lookup"><span data-stu-id="fbd7d-106">Read the documentation and determine which decommissioning procedure to use.</span></span>

<span data-ttu-id="fbd7d-107">Per una copertura esaustiva della rimozione di server e ruoli server di Lync Server 2010 e una guida dettagliata per la disattivazione di una distribuzione di Lync Server 2010, vedere "disinstallazione di Microsoft Lync Server 2010 e rimozione dei ruoli del server", a [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)cui è possibile eseguire il download.</span><span class="sxs-lookup"><span data-stu-id="fbd7d-107">For exhaustive coverage of removing Lync Server 2010 servers and server roles, and a step-by-step guide to decommissioning a Lync Server 2010 deployment, see "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="fbd7d-108">Per informazioni su come eseguire la migrazione e l'aggiornamento delle applicazioni Microsoft Unified Communications Managed API (UCMA), prima della disattivazione dell'ambiente legacy, vedere<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="fbd7d-108">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="fbd7d-109">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="fbd7d-109">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="fbd7d-110">Aggiornare i record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="fbd7d-110">Update DNS SRV records</span></span>](update-dns-srv-records.md)

  - <span></span>  
    [<span data-ttu-id="fbd7d-111">Trasferire il server di gestione centrale di Lync Server 2010 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fbd7d-111">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>](move-the-lync-server-2010-central-management-server-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="fbd7d-112">Spostare le directory conferenze</span><span class="sxs-lookup"><span data-stu-id="fbd7d-112">Move Conference Directories</span></span>](move-lync-server-2010-conference-directories-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="fbd7d-113">Rimuovere l'associazione del server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="fbd7d-113">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)

  - <span></span>  
    [<span data-ttu-id="fbd7d-114">Rimuovere l'associazione del server di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="fbd7d-114">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)

  - <span></span>  
    [<span data-ttu-id="fbd7d-115">Rimuovere il server front-end Enterprise Edition o front-end Standard Edition</span><span class="sxs-lookup"><span data-stu-id="fbd7d-115">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-enterprise-edition-front-end-server-or-standard-edition-front-end-server.md)

  - <span></span>  
    [<span data-ttu-id="fbd7d-116">Rimuovere database e istanze di SQL Server nel server back-end</span><span class="sxs-lookup"><span data-stu-id="fbd7d-116">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

