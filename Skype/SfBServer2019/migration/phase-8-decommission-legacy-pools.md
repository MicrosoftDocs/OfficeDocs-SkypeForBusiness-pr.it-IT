---
title: Fase 8 Rimuovere i pool legacy
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.custom: httpsfix
description: Nell'argomento seguente vengono fornite indicazioni per l'aggiornamento delle voci DNS, lo spostamento di Content Management Server, la rimozione delle autorizzazioni dei pool e la disattivazione e la rimozione di server e pool da una distribuzione legacy. Non tutte le procedure elencate in questa sezione sono necessarie. Leggere la documentazione e determinare quale procedura di rimozione utilizzare.
ms.openlocfilehash: 2406b25436bc13cafca8b09c92220a96e0635ae3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753694"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="5b322-105">Fase 8: rimuovere le autorizzazioni dei pool legacy</span><span class="sxs-lookup"><span data-stu-id="5b322-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="5b322-106">Nell'argomento seguente vengono fornite indicazioni per l'aggiornamento delle voci DNS, lo spostamento di Content Management Server, la rimozione delle autorizzazioni dei pool e la disattivazione e la rimozione di server e pool da una distribuzione legacy.</span><span class="sxs-lookup"><span data-stu-id="5b322-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="5b322-107">Non tutte le procedure elencate in questa sezione sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="5b322-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="5b322-108">Leggere la documentazione e determinare quale procedura di rimozione utilizzare.</span><span class="sxs-lookup"><span data-stu-id="5b322-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="5b322-109">Per un articolo aggiornato ma esaustivo sulla rimozione di server e ruoli del server e per una guida dettagliata alla rimozione delle autorizzazioni di una distribuzione, scaricare Disinstallazione di Microsoft Lync Server e Rimozione dei ruoli [del server.](https://go.microsoft.com/fwlink/p/?linkId=246227)</span><span class="sxs-lookup"><span data-stu-id="5b322-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="5b322-110">Per informazioni sulla migrazione e l'aggiornamento delle applicazioni UCMA (Microsoft Unified Communications Managed API), prima di rimuovere le autorizzazioni dell'ambiente legacy, vedere [Applicazioni UCMA: scenari di coesistenza,](https://go.microsoft.com/fwlink/p/?LinkId=269555)migrazione e aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="5b322-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="5b322-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="5b322-111">In this section</span></span>

> [<span data-ttu-id="5b322-112">Aggiornare i record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="5b322-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="5b322-113">Spostare l'installazione legacy del server di gestione centrale in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="5b322-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="5b322-114">Spostare le directory conferenze</span><span class="sxs-lookup"><span data-stu-id="5b322-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="5b322-115">Rimuovere l'associazione del server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="5b322-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="5b322-116">Rimuovere l'associazione del server di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="5b322-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="5b322-117">Rimuovere enterprise edition Front End Server o Standard Edition Front End Server</span><span class="sxs-lookup"><span data-stu-id="5b322-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="5b322-118">Rimuovere database e istanze di SQL Server nel server back-end</span><span class="sxs-lookup"><span data-stu-id="5b322-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    

