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
description: È possibile pubblicare la topologia configurata utilizzando Generatore di topologie. Viene chiesto di selezionare da un elenco il front end server o il pool Front End assumerà il ruolo di Holding The Central Management store. Solo un front end server o un pool Front end può contenere questo ruolo in un determinato momento.
ms.openlocfilehash: d4af4756dc42c54790ee1120b418eb5e6a349387
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49822186"
---
# <a name="publish-topology-select-cms-page"></a><span data-ttu-id="b5077-105">Pubblicare topologia, pagina Seleziona l'archivio di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="b5077-105">Publish Topology Select CMS Page</span></span>
 
<span data-ttu-id="b5077-106">È possibile pubblicare la topologia configurata utilizzando Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="b5077-106">You publish the topology that you have configured using Topology Builder.</span></span> <span data-ttu-id="b5077-107">Viene chiesto di selezionare da un elenco il front end server o il pool Front End assumerà il ruolo di Holding The Central Management store.</span><span class="sxs-lookup"><span data-stu-id="b5077-107">You are asked to select from a list which Front End Server or Front End pool will assume the role of holding the Central Management store.</span></span> <span data-ttu-id="b5077-108">Solo un front end server o un pool Front end può contenere questo ruolo in un determinato momento.</span><span class="sxs-lookup"><span data-stu-id="b5077-108">Only one Front End Server or Front End pool can hold this role at any given time.</span></span> 
  
### <a name="about-the-central-management-server"></a><span data-ttu-id="b5077-109">Informazioni sul server di gestione centrale</span><span class="sxs-lookup"><span data-stu-id="b5077-109">About the Central Management Server</span></span>
<span data-ttu-id="b5077-110">Il server di gestione centrale è un singolo sistema di replica master/multiple, in cui la copia di lettura/scrittura del database è conservata dal front end server che contiene il server di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="b5077-110">The Central Management Server is a single master/multiple replica system, where the read/write copy of the database is held by the Front End Server that contains the Central Management Server.</span></span> <span data-ttu-id="b5077-111">Ogni computer della topologia, incluso il front end server che contiene il server di gestione centrale, dispone di una copia di sola lettura dei dati dell'archivio di gestione centrale nel database di SQL Server, denominata RTCLOCAL per impostazione predefinita, installata nel computer durante l'installazione e la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="b5077-111">Each computer in the topology, including the Front End Server that contains the Central Management Server, has a read-only copy of the Central Management store data in the SQL Server database (named RTCLOCAL by default) installed on the computer during setup and deployment.</span></span> <span data-ttu-id="b5077-112">Il database locale riceve gli aggiornamenti delle repliche tramite l'agente Replicator di replica di Lync Server eseguito come servizio in tutti i computer.</span><span class="sxs-lookup"><span data-stu-id="b5077-112">The local database receives replica updates by way of the Lync Server Replica Replicator Agent that runs as a service on all computers.</span></span> <span data-ttu-id="b5077-113">Il nome del database effettivo sul server di gestione centrale e la replica locale è XDS, costituito dai file XDS. mdf e XDS. ldf.</span><span class="sxs-lookup"><span data-stu-id="b5077-113">The name of the actual database on the Central Management Server and the local replica is XDS, which is made up of the xds.mdf and xds.ldf files.</span></span> <span data-ttu-id="b5077-114">Il percorso del database master è fatto riferimento da un punto di controllo del servizio (SCP) in servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b5077-114">The master database location is referenced by a service control point (SCP) in Active Directory Domain Services.</span></span> <span data-ttu-id="b5077-115">Tutti gli strumenti che utilizzano il server di gestione centrale per la gestione e la configurazione di Lync Server utilizzano l'SCP per individuare l'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="b5077-115">All tools that use the Central Management Server to manage and configure Lync Server use the SCP to locate the Central Management store.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b5077-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b5077-116">See also</span></span>

[<span data-ttu-id="b5077-117">Move-CsManagementServer</span><span class="sxs-lookup"><span data-stu-id="b5077-117">Move-CsManagementServer</span></span>](https://docs.microsoft.com/powershell/module/skype/move-csmanagementserver?view=skype-ps)
