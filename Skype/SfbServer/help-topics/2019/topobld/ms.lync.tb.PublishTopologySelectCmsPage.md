---
title: Pagina Selezionare CMS per la pubblicazione della topologia
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Viene pubblicata la topologia configurata con generatore di topologia. Viene richiesto di selezionare un elenco da un server front-end o da un pool Front-end che assumerà il ruolo di Holding The Central Management store. Solo un server front-end o un pool Front-end può contenere questo ruolo in un momento specifico.
ms.openlocfilehash: 9cecdc170934f7359597484e56299e2fe76499b9
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41701671"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="ceed8-105">Pagina Selezionare CMS per la pubblicazione della topologia</span><span class="sxs-lookup"><span data-stu-id="ceed8-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="ceed8-106">Viene pubblicata la topologia configurata con generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="ceed8-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="ceed8-107">Viene richiesto di selezionare un elenco da un server front-end o da un pool Front-end che assumerà il ruolo di Holding The Central Management store.</span><span class="sxs-lookup"><span data-stu-id="ceed8-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="ceed8-108">Solo un server front-end o un pool Front-end può contenere questo ruolo in un momento specifico.</span><span class="sxs-lookup"><span data-stu-id="ceed8-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="ceed8-109">Informazioni sul server di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="ceed8-109">About the Central Management Server</span></span>
<span data-ttu-id="ceed8-110">Il server di gestione centrale è un singolo sistema master/replica multipla, in cui la copia di lettura/scrittura del database è tenuta dal server front-end che contiene il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="ceed8-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="ceed8-111">Ogni computer della topologia, incluso il front end server che contiene il server di gestione centrale, ha una copia di sola lettura dei dati di Central Management store nel database di SQL Server (denominata RTCLOCAL per impostazione predefinita) installati nel computer durante l'installazione e distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ceed8-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="ceed8-112">Il database locale riceve gli aggiornamenti della replica tramite l'agente replicatore di Lync Server che viene eseguito come servizio in tutti i computer.</span><span class="sxs-lookup"><span data-stu-id="ceed8-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="ceed8-113">Il nome del database effettivo nel server di gestione centrale e la replica locale è XDS, costituito dai file XDS. mdf e XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="ceed8-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="ceed8-114">Il percorso del database master viene fatto riferimento da un punto di controllo del servizio (SCP) in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ceed8-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="ceed8-115">Tutti gli strumenti che usano il server di gestione centralizzato per gestire e configurare Lync Server usano l'SCP per individuare l'Central Management store.</span><span class="sxs-lookup"><span data-stu-id="ceed8-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ceed8-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ceed8-116">See also</span></span>

[<span data-ttu-id="ceed8-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="ceed8-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
