---
title: Pubblica topologia, pagina Seleziona l'archivio di gestione centrale
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.PublishTopologySelectCmsPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: df447066-2840-431b-bc4e-acf8aa692d71
ROBOTS: NOINDEX, NOFOLLOW
description: Pubblicare la topologia configurata utilizzando Generatore di topologie. Viene richiesto di selezionare da un elenco quale Front End Server o pool Front End assumerà il ruolo di conservare l'archivio di gestione centrale. Solo un Front End Server o un pool Front End può mantenere questo ruolo in un determinato momento.
ms.openlocfilehash: fe3e7ed8c0a58b0547ede0eb02f0ea476bce94bc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096882"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="ad293-105">Pubblicare topologia, pagina Seleziona l'archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="ad293-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="ad293-106">Pubblicare la topologia configurata utilizzando Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="ad293-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="ad293-107">Viene richiesto di selezionare da un elenco quale Front End Server o pool Front End assumerà il ruolo di conservare l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="ad293-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="ad293-108">Solo un Front End Server o un pool Front End può mantenere questo ruolo in un determinato momento.</span><span class="sxs-lookup"><span data-stu-id="ad293-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="ad293-109">Informazioni sul server di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="ad293-109">About the Central Management Server</span></span>
<span data-ttu-id="ad293-110">Il server di gestione centrale è un singolo sistema di replica master/a più repliche, in cui la copia di lettura/scrittura del database viene mantenuta dal Front End Server che contiene il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="ad293-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="ad293-111">Ogni computer della topologia, incluso il Front End Server contenente il server di gestione centrale, dispone di una copia di sola lettura dei dati dell'archivio di gestione centrale nel database di SQL Server (denominato RTCLOCAL per impostazione predefinita) installato nel computer durante l'installazione e la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ad293-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="ad293-112">Il database locale riceve gli aggiornamenti delle repliche tramite l'agente Replicator di Lync Server eseguito come servizio in tutti i computer.</span><span class="sxs-lookup"><span data-stu-id="ad293-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="ad293-113">Il nome del database effettivo nel server di gestione centrale e della replica locale è XDS, costituito da file xds.mdf e xds.ldf.</span><span class="sxs-lookup"><span data-stu-id="ad293-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="ad293-114">Al percorso del database master fa riferimento un punto di controllo del servizio (SCP) in Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ad293-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="ad293-115">Tutti gli strumenti che utilizzano il server di gestione centrale per gestire e configurare Lync Server utilizzano il pannello SCP per individuare l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="ad293-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ad293-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ad293-116">See also</span></span>

[<span data-ttu-id="ad293-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="ad293-117">Move-CsManagementServer</span></span>](/powershell/module/skype/move-csmanagementserver?view=skype-ps)