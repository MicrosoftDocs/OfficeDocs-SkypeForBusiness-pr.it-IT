---
title: Fase 8 Rimozione dei pool legacy
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
description: Nell'argomento seguente vengono fornite indicazioni per aggiornare le voci DNS, spostare Content Management Server, rimuovere pool e disattivare e rimuovere server e pool da una distribuzione legacy. Non tutte le procedure elencate in questa sezione sono necessarie. Leggere la documentazione e determinare quale procedura di rimozione utilizzare.
ms.openlocfilehash: b1080c68e3b4075ce92aaef497854855135dc47d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113242"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="b4c55-105">Fase 8: rimuovere le autorizzazioni dei pool legacy</span><span class="sxs-lookup"><span data-stu-id="b4c55-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="b4c55-106">Nell'argomento seguente vengono fornite indicazioni per aggiornare le voci DNS, spostare Content Management Server, rimuovere pool e disattivare e rimuovere server e pool da una distribuzione legacy.</span><span class="sxs-lookup"><span data-stu-id="b4c55-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="b4c55-107">Non tutte le procedure elencate in questa sezione sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="b4c55-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="b4c55-108">Leggere la documentazione e determinare quale procedura di rimozione utilizzare.</span><span class="sxs-lookup"><span data-stu-id="b4c55-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="b4c55-109">Per un articolo aggiornato ma esaustivo sulla rimozione di server e ruoli del server e per una guida dettagliata alla rimozione delle autorizzazioni di una distribuzione, scaricare [Disinstallazione](https://go.microsoft.com/fwlink/p/?linkId=246227)di Microsoft Lync Server e Rimozione dei ruoli del server .</span><span class="sxs-lookup"><span data-stu-id="b4c55-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="b4c55-110">Per informazioni sulla migrazione e l'aggiornamento delle applicazioni UCMA (Microsoft Unified Communications Managed API), prima di rimuovere le autorizzazioni dell'ambiente legacy, vedere [Applicazioni UCMA: scenari di coesistenza,](/previous-versions/office/jj728782(v=office.15))migrazione e aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="b4c55-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](/previous-versions/office/jj728782(v=office.15)).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="b4c55-111">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="b4c55-111">In this section</span></span>

> [<span data-ttu-id="b4c55-112">Aggiornare i record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="b4c55-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="b4c55-113">Spostare l'installazione legacy del server di gestione centrale in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="b4c55-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="b4c55-114">Spostare le directory conferenze</span><span class="sxs-lookup"><span data-stu-id="b4c55-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="b4c55-115">Rimuovere l'associazione del server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="b4c55-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="b4c55-116">Rimuovere l'associazione del server di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="b4c55-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="b4c55-117">Rimuovere il Front End Server Enterprise Edition o il Front End Server Standard Edition</span><span class="sxs-lookup"><span data-stu-id="b4c55-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="b4c55-118">Rimuovere database e istanze di SQL Server nel server back-end</span><span class="sxs-lookup"><span data-stu-id="b4c55-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
