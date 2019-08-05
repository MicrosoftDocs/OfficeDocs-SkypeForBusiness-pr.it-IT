---
title: Fase 8 smantella i pool legacy
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.custom: httpsfix
description: L'argomento seguente fornisce indicazioni per l'aggiornamento delle voci DNS, lo spostamento del server di gestione del contenuto, lo smantellamento dei pool e la disattivazione e la rimozione di server e pool da una distribuzione legacy. Non tutte le procedure elencate in questa sezione sono obbligatorie. Leggere la documentazione e determinare la procedura di disattivazione da usare.
ms.openlocfilehash: 4110e45b2790204e96205dd9552e14fa9c359446
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186641"
---
# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="8fdaf-105">Fase 8: rimuovere i pool legacy</span><span class="sxs-lookup"><span data-stu-id="8fdaf-105">Phase 8: Decommission legacy pools</span></span>

<span data-ttu-id="8fdaf-106">L'argomento seguente fornisce indicazioni per l'aggiornamento delle voci DNS, lo spostamento del server di gestione del contenuto, lo smantellamento dei pool e la disattivazione e la rimozione di server e pool da una distribuzione legacy.</span><span class="sxs-lookup"><span data-stu-id="8fdaf-106">The following topic provides guidance for updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment.</span></span> <span data-ttu-id="8fdaf-107">Non tutte le procedure elencate in questa sezione sono obbligatorie.</span><span class="sxs-lookup"><span data-stu-id="8fdaf-107">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="8fdaf-108">Leggere la documentazione e determinare la procedura di disattivazione da usare.</span><span class="sxs-lookup"><span data-stu-id="8fdaf-108">Read the documentation and determine which decommissioning procedure to use.</span></span> 
  
<span data-ttu-id="8fdaf-109">Per un articolo dettagliato ma esaustivo sulla rimozione di server e ruoli del server e una guida dettagliata per la disattivazione di una distribuzione, scaricare la disinstallazione di [Microsoft Lync Server e la rimozione dei ruoli del server](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="8fdaf-109">For a dated but exhaustive article on removing servers and server roles, and a step-by-step guide to decommissioning a deployment, download [Uninstalling Microsoft Lync Server and Removing Server Roles](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="8fdaf-110">Per informazioni sulla migrazione e l'aggiornamento di Microsoft Unified Communications Managed API (UCMA), prima di rimuovere l'ambiente legacy, vedere [le applicazioni di UCMA: coesistenza, migrazione e aggiornamento](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span><span class="sxs-lookup"><span data-stu-id="8fdaf-110">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, before decommissioning your legacy environment, see [UCMA applications: Coexistence, migration, and upgrade scenarios](https://go.microsoft.com/fwlink/p/?LinkId=269555).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="8fdaf-111">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="8fdaf-111">In this section</span></span>

> [<span data-ttu-id="8fdaf-112">Aggiornare i record SRV DNS</span><span class="sxs-lookup"><span data-stu-id="8fdaf-112">Update DNS SRV records</span></span>](update-dns-srv-records.md)
> 
> [<span data-ttu-id="8fdaf-113">Trasferire il server di gestione centralizzato legacy install in Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="8fdaf-113">Move the legacy install Central Management Server to Skype for Business Server 2019</span></span>](move-the-central-management-server.md)
> 
> [<span data-ttu-id="8fdaf-114">Spostare le directory conferenze</span><span class="sxs-lookup"><span data-stu-id="8fdaf-114">Move Conference Directories</span></span>](move-conference-directories.md)
> 
> [<span data-ttu-id="8fdaf-115">Rimuovere l'associazione del server di archiviazione</span><span class="sxs-lookup"><span data-stu-id="8fdaf-115">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)
> 
> [<span data-ttu-id="8fdaf-116">Rimuovere l'associazione del server di monitoraggio</span><span class="sxs-lookup"><span data-stu-id="8fdaf-116">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)
> 
> [<span data-ttu-id="8fdaf-117">Rimuovere il server front-end Enterprise Edition o front-end Standard Edition</span><span class="sxs-lookup"><span data-stu-id="8fdaf-117">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-front-end-server.md)
> 
> [<span data-ttu-id="8fdaf-118">Rimuovere le istanze e i database di SQL Server nel server back-end</span><span class="sxs-lookup"><span data-stu-id="8fdaf-118">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)
    

