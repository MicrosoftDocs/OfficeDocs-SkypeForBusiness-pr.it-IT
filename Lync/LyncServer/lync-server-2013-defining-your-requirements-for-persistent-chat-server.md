---
title: 'Lync Server 2013: definizione dei requisiti per il server Chat persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15beb7728525fa3e4bb6b75dfc46fb46335d1063
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42154678"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="b33e5-102">Definizione dei requisiti dell'organizzazione per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b33e5-102">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b33e5-103">_**Ultimo argomento modificato:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="b33e5-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="b33e5-104">Prima di distribuire il server Chat persistente per l'organizzazione, è essenziale prendere in considerazione le seguenti domande chiave per ottimizzare la distribuzione:</span><span class="sxs-lookup"><span data-stu-id="b33e5-104">Before you deploy Persistent Chat Server for your organization, it’s essential to consider the following key questions to optimize your deployment:</span></span>

  - <span data-ttu-id="b33e5-105">Chi (profilo utente) deve essere abilitato per il server Chat persistente?</span><span class="sxs-lookup"><span data-stu-id="b33e5-105">Who (user profile) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="b33e5-106">Il server Chat persistente è abilitato da un criterio che può essere impostato a livello globale, sito, pool o utente.</span><span class="sxs-lookup"><span data-stu-id="b33e5-106">Persistent Chat Server is enabled by a policy that can be set at a Global, Site, Pool or User level.</span></span>

  - <span data-ttu-id="b33e5-107">Quanti utenti (scala) devono essere abilitati per il server Chat persistente?</span><span class="sxs-lookup"><span data-stu-id="b33e5-107">How many users (scale) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="b33e5-108">Il server Chat persistente supporta gli utenti con provisioning 150.000 (abilitati dai criteri) e un massimo di 80.000 utenti simultanei che utilizzano il server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b33e5-108">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users using Persistent Chat Server.</span></span> <span data-ttu-id="b33e5-109">Un singolo server Chat persistente può supportare gli utenti connessi a 20.000 e un singolo pool di server Chat persistente può avere fino a 4 server attivi per un totale di 80.000 utenti connessi contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="b33e5-109">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>

  - <span data-ttu-id="b33e5-110">Si sta eseguendo la migrazione da una versione precedente di Group Chat Server o si sta distribuendo il server Chat persistente per la prima volta?</span><span class="sxs-lookup"><span data-stu-id="b33e5-110">Are you migrating from a previous version of Group Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>

  - <span data-ttu-id="b33e5-111">Ci sono requisiti di conformità da rispettare?</span><span class="sxs-lookup"><span data-stu-id="b33e5-111">Are there compliance requirements?</span></span> <span data-ttu-id="b33e5-112">Il server Chat persistente supporta la conformità.</span><span class="sxs-lookup"><span data-stu-id="b33e5-112">Persistent Chat Server supports compliance.</span></span> <span data-ttu-id="b33e5-113">Il servizio di conformità viene eseguito nella collocazione sul server front end server Persistent Chat, invece del requisito di un computer separato nelle distribuzioni precedenti di Group Chat Server.</span><span class="sxs-lookup"><span data-stu-id="b33e5-113">The compliance service runs collocated on the Persistent Chat Server Front End Server, as opposed to the requirement for a separate computer in previous Group Chat Server deployments.</span></span> <span data-ttu-id="b33e5-114">La conformità è facoltativa e, se scelta, richiede un database di conformità che deve essere configurato per l'archiviazione di dati ed eventi di conformità.</span><span class="sxs-lookup"><span data-stu-id="b33e5-114">Compliance is optional, and if chosen, requires a compliance database that must be configured to store compliance data and events.</span></span> <span data-ttu-id="b33e5-115">È possibile che si desideri configurare anche un adattatore per estrarre i dati dal database di conformità e convertirli in un altro formato, ad esempio file XML o archivi di Exchange ospitati.</span><span class="sxs-lookup"><span data-stu-id="b33e5-115">You may want to also configure an adapter to take the data from the compliance database and convert to another format (such as XML files or Exchange-hosted archives).</span></span>

  - <span data-ttu-id="b33e5-p104">In che modo si vogliono controllare ambiti, limiti etici e accesso? È possibile definire **Categorie** per definire i limiti e scegliere gli utenti a cui è consentito trovarsi nelle chat create in ognuna di queste categorie.</span><span class="sxs-lookup"><span data-stu-id="b33e5-p104">How do you want to control scopes, ethical boundaries, and access? You can define **Categories** to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>

  - <span data-ttu-id="b33e5-p105">In che modo si vuole controllare chi può creare chat? È possibile configurare **Creatori**, appropriati a seconda della categoria, che possono creare chat. I creatori possono impostare altri membri come **Responsabili di chat room** per la gestione ordinaria delle chat (aggiunta o rimozione di membri), in base all'ambito dei **Membri consentiti/Membri non consentiti** configurati dalla categoria.</span><span class="sxs-lookup"><span data-stu-id="b33e5-p105">How do you want to control who can create rooms? You can configure **Creators**, appropriate to your categories, who can create rooms. Creators can assign other members as **Chat Room Managers** for ongoing management of the rooms (adding or removing additional members), according to the scope for **AllowedMembers/DeniedMembers** configured by the category.</span></span>

  - <span data-ttu-id="b33e5-121">In che modo si vogliono creare le chat?</span><span class="sxs-lookup"><span data-stu-id="b33e5-121">How do you want to create rooms?</span></span> <span data-ttu-id="b33e5-122">Il server Chat persistente offre una funzionalità basata sul Web per la creazione e la gestione della sala.</span><span class="sxs-lookup"><span data-stu-id="b33e5-122">Persistent Chat Server provides a web-based feature for room creation and management.</span></span> <span data-ttu-id="b33e5-123">Questa operazione può essere avviata dal client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b33e5-123">This can be launched from the Lync 2013 client.</span></span> <span data-ttu-id="b33e5-124">È possibile scegliere di definire una soluzione personalizzata, utilizzando il Software Development Kit (SDK) di Persistent Chat Server, che implementa i flussi di lavoro e i requisiti aziendali e configura il server Chat persistente per indirizzare gli utenti alla soluzione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="b33e5-124">You can choose to define a custom solution (by using the Persistent Chat Server Software Development Kit (SDK)) that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>

  - <span data-ttu-id="b33e5-125">Di che tipo di componenti aggiuntivi si vuole effettuare il provisioning?</span><span class="sxs-lookup"><span data-stu-id="b33e5-125">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="b33e5-126">I **componenti** aggiuntivi consentono di migliorare l'esperienza in sala utilizzando il riquadro Extensibility nel client Lync 2013 per fornire un contesto pertinente per la sala.</span><span class="sxs-lookup"><span data-stu-id="b33e5-126">**Add-ins** enhance the in-room experience by leveraging the extensibility pane in the Lync 2013 client to provide context that is relevant to the room.</span></span> <span data-ttu-id="b33e5-127">È possibile scegliere i componenti aggiuntivi generici che si ritengono più utili, ad esempio il sito Web aziendale, i documenti di collaborazione interni e così via.</span><span class="sxs-lookup"><span data-stu-id="b33e5-127">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="b33e5-128">I responsabili di chat room, se vogliono, possono scegliere uno dei componenti aggiuntivi registrati e associarlo alla propria chat.</span><span class="sxs-lookup"><span data-stu-id="b33e5-128">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span>

  - <span data-ttu-id="b33e5-129">Quali sono i requisiti di disponibilità elevata e di ripristino di emergenza?</span><span class="sxs-lookup"><span data-stu-id="b33e5-129">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="b33e5-130">Il server Chat persistente supporta il mirroring di SQL Server e il clustering di SQL Server per la disponibilità elevata e supporta fino a 8 Server (4 attivi e 4 in standby) in un pool esteso con il log shipping di SQL Server per il ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="b33e5-130">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability and supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping for disaster recovery.</span></span>

  - <span data-ttu-id="b33e5-131">Ci sono requisiti normativi da rispettare?</span><span class="sxs-lookup"><span data-stu-id="b33e5-131">Are there regulatory requirements?</span></span> <span data-ttu-id="b33e5-132">Se l'azienda si trova in un paese/area geografica in cui i dati devono essere conservati all'interno del paese, potrebbe essere necessario distribuire più pool di server di chat persistente, ognuno locale a una specifica geografia.</span><span class="sxs-lookup"><span data-stu-id="b33e5-132">If your company is in a country/region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="b33e5-133">Una sala, una categoria o un componente aggiuntivo non si estende su pool, bensì appartiene a un solo pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b33e5-133">A room, category, or add-in does not span pools—it belongs to only one Persistent Chat Server pool.</span></span> <span data-ttu-id="b33e5-134">È possibile gestire il set di categorie, i componenti aggiuntivi e le sale per ogni pool di server Chat persistente.</span><span class="sxs-lookup"><span data-stu-id="b33e5-134">You can manage the set of categories, add-ins and rooms for each Persistent Chat Server pool.</span></span> <span data-ttu-id="b33e5-135">Gli utenti possono essere configurati in modo che possano accedere alle chat room di uno o più pool utilizzando l'ambito di appartenenza di categoria AllowedMembers o della sala, a seconda di come si progettano le categorie.</span><span class="sxs-lookup"><span data-stu-id="b33e5-135">Users can be configured to have access to rooms in one or more pools using the category AllowedMembers scope or Room’s membership scope, depending on how you design your categories.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="b33e5-136">Se si dispone di più pool di server di chat persistente, non è possibile aumentare la scalabilità (sono ancora disponibili solo 80.000 utenti connessi contemporaneamente in tutti i pool di server Chat persistente).</span><span class="sxs-lookup"><span data-stu-id="b33e5-136">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrently connected users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="b33e5-137">Il motivo principale del supporto di più pool di server di chat persistente è il supporto di problemi normativi.</span><span class="sxs-lookup"><span data-stu-id="b33e5-137">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

