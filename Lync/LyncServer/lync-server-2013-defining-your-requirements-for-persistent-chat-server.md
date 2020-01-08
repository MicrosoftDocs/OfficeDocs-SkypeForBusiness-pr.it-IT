---
title: "Lync Server 2013: Definizione dei requisiti dell'organizzazione per il server Chat persistente"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for Persistent Chat Server
ms:assetid: 568674fb-c08a-4170-ac38-e2f8428c69e0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398372(v=OCS.15)
ms:contentKeyID: 48184166
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68f9195a91a4f8334933d1fce7ffd3a5dceb564c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984810"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-organizations-requirements-for-persistent-chat-server-in-lync-server-2013"></a><span data-ttu-id="dfa93-102">Definizione dei requisiti dell'organizzazione per il server Chat persistente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="dfa93-102">Defining your organization's requirements for Persistent Chat Server in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dfa93-103">_**Argomento Ultima modifica:** 2014-01-15_</span><span class="sxs-lookup"><span data-stu-id="dfa93-103">_**Topic Last Modified:** 2014-01-15_</span></span>

<span data-ttu-id="dfa93-104">Prima di distribuire il server di chat persistente per l'organizzazione, è essenziale prendere in considerazione le domande chiave seguenti per ottimizzare la distribuzione:</span><span class="sxs-lookup"><span data-stu-id="dfa93-104">Before you deploy Persistent Chat Server for your organization, it’s essential to consider the following key questions to optimize your deployment:</span></span>

  - <span data-ttu-id="dfa93-105">Chi (profilo utente) deve essere abilitato per il server di chat persistente?</span><span class="sxs-lookup"><span data-stu-id="dfa93-105">Who (user profile) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="dfa93-106">Il server di chat persistente è abilitato da un criterio che può essere impostato a livello globale, del sito, del pool o dell'utente.</span><span class="sxs-lookup"><span data-stu-id="dfa93-106">Persistent Chat Server is enabled by a policy that can be set at a Global, Site, Pool or User level.</span></span>

  - <span data-ttu-id="dfa93-107">Il numero di utenti (scala) deve essere abilitato per il server di chat persistente?</span><span class="sxs-lookup"><span data-stu-id="dfa93-107">How many users (scale) should be enabled for Persistent Chat Server?</span></span> <span data-ttu-id="dfa93-108">Il server di chat persistente supporta gli utenti con provisioning di 150.000 (abilitati per criterio) e un massimo di 80.000 utenti simultanei che usano il server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="dfa93-108">Persistent Chat Server supports 150,000 provisioned users (enabled by policy), and a maximum of 80,000 concurrent users using Persistent Chat Server.</span></span> <span data-ttu-id="dfa93-109">Un singolo server di chat persistente può supportare gli utenti connessi di 20.000 e un singolo pool di server di chat persistente può avere fino a 4 server attivi per un totale di 80.000 utenti connessi contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="dfa93-109">A single Persistent Chat Server can support 20,000 connected users, and a single Persistent Chat Server pool can have up to 4 active servers for a total of 80,000 concurrently connected users.</span></span>

  - <span data-ttu-id="dfa93-110">Si esegue la migrazione da una versione precedente di Group Chat Server o si sta distribuendo il server di chat persistente per la prima volta?</span><span class="sxs-lookup"><span data-stu-id="dfa93-110">Are you migrating from a previous version of Group Chat Server, or are you deploying Persistent Chat Server for the first time?</span></span>

  - <span data-ttu-id="dfa93-111">Esistono requisiti di conformità?</span><span class="sxs-lookup"><span data-stu-id="dfa93-111">Are there compliance requirements?</span></span> <span data-ttu-id="dfa93-112">Il server di chat persistente supporta la conformità.</span><span class="sxs-lookup"><span data-stu-id="dfa93-112">Persistent Chat Server supports compliance.</span></span> <span data-ttu-id="dfa93-113">Il servizio di conformità viene eseguito in una collocazione nel server front end del server di chat persistente, in contrapposizione al requisito di un computer separato nelle distribuzioni precedenti di Group Chat Server.</span><span class="sxs-lookup"><span data-stu-id="dfa93-113">The compliance service runs collocated on the Persistent Chat Server Front End Server, as opposed to the requirement for a separate computer in previous Group Chat Server deployments.</span></span> <span data-ttu-id="dfa93-114">La conformità è facoltativa e, se scelta, richiede un database di conformità che deve essere configurato per archiviare i dati e gli eventi di conformità.</span><span class="sxs-lookup"><span data-stu-id="dfa93-114">Compliance is optional, and if chosen, requires a compliance database that must be configured to store compliance data and events.</span></span> <span data-ttu-id="dfa93-115">Potrebbe essere necessario configurare un adapter anche per prendere i dati dal database di conformità e convertirli in un altro formato, ad esempio i file XML o gli archivi ospitati in Exchange.</span><span class="sxs-lookup"><span data-stu-id="dfa93-115">You may want to also configure an adapter to take the data from the compliance database and convert to another format (such as XML files or Exchange-hosted archives).</span></span>

  - <span data-ttu-id="dfa93-116">Come si vogliono controllare gli ambiti, i confini etici e l'accesso?</span><span class="sxs-lookup"><span data-stu-id="dfa93-116">How do you want to control scopes, ethical boundaries, and access?</span></span> <span data-ttu-id="dfa93-117">Puoi definire **categorie** per separare questi limiti e scegliere chi può essere nelle sale create in ognuna di queste categorie.</span><span class="sxs-lookup"><span data-stu-id="dfa93-117">You can define **Categories** to segregate these boundaries, and choose who is allowed to be in rooms that are created in each of these categories.</span></span>

  - <span data-ttu-id="dfa93-118">Come si vuole controllare chi può creare sale?</span><span class="sxs-lookup"><span data-stu-id="dfa93-118">How do you want to control who can create rooms?</span></span> <span data-ttu-id="dfa93-119">Puoi configurare gli **autori**, appropriati alle categorie, che possono creare sale.</span><span class="sxs-lookup"><span data-stu-id="dfa93-119">You can configure **Creators**, appropriate to your categories, who can create rooms.</span></span> <span data-ttu-id="dfa93-120">Gli autori possono assegnare ad altri membri i **responsabili delle chat room** per la gestione continua delle sale (aggiunta o rimozione di membri aggiuntivi), in base all'ambito per **AllowedMembers/DeniedMembers** configurato dalla categoria.</span><span class="sxs-lookup"><span data-stu-id="dfa93-120">Creators can assign other members as **Chat Room Managers** for ongoing management of the rooms (adding or removing additional members), according to the scope for **AllowedMembers/DeniedMembers** configured by the category.</span></span>

  - <span data-ttu-id="dfa93-121">Come si vogliono creare le sale?</span><span class="sxs-lookup"><span data-stu-id="dfa93-121">How do you want to create rooms?</span></span> <span data-ttu-id="dfa93-122">Persistent Chat Server offre una funzionalità basata sul Web per la creazione e la gestione della sala.</span><span class="sxs-lookup"><span data-stu-id="dfa93-122">Persistent Chat Server provides a web-based feature for room creation and management.</span></span> <span data-ttu-id="dfa93-123">Questa operazione può essere avviata dal client Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="dfa93-123">This can be launched from the Lync 2013 client.</span></span> <span data-ttu-id="dfa93-124">Puoi scegliere di definire una soluzione personalizzata (usando il Software Development Kit (SDK) Persistent Chat Server) che implementa i tuoi requisiti e flussi di lavoro e configura il server di chat persistente per indirizzare gli utenti alla tua soluzione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="dfa93-124">You can choose to define a custom solution (by using the Persistent Chat Server Software Development Kit (SDK)) that implements your business requirements and workflows, and configures Persistent Chat Server to direct users to your custom solution.</span></span>

  - <span data-ttu-id="dfa93-125">Quali tipi di componenti aggiuntivi si desidera eseguire il provisioning?</span><span class="sxs-lookup"><span data-stu-id="dfa93-125">What kind of add-ins do you want to provision?</span></span> <span data-ttu-id="dfa93-126">I **componenti** aggiuntivi migliorano l'esperienza in camera sfruttando il riquadro estensibilità nel client Lync 2013 per offrire un contesto rilevante per la sala.</span><span class="sxs-lookup"><span data-stu-id="dfa93-126">**Add-ins** enhance the in-room experience by leveraging the extensibility pane in the Lync 2013 client to provide context that is relevant to the room.</span></span> <span data-ttu-id="dfa93-127">È possibile scegliere quali componenti aggiuntivi generali potrebbero essere più utili, ad esempio il sito Web aziendale, i documenti di collaborazione interni e così via.</span><span class="sxs-lookup"><span data-stu-id="dfa93-127">You can choose what general add-ins might be most useful (for example, your company website, internal collaboration documents, and so on).</span></span> <span data-ttu-id="dfa93-128">I responsabili della chat room possono scegliere uno dei componenti aggiuntivi registrati e associarli alle rispettive sale, se necessario.</span><span class="sxs-lookup"><span data-stu-id="dfa93-128">Chat room managers can choose one of the registered add-ins and associate it with their rooms, if desired.</span></span>

  - <span data-ttu-id="dfa93-129">Quali sono i requisiti per l'elevata disponibilità e il ripristino di emergenza?</span><span class="sxs-lookup"><span data-stu-id="dfa93-129">What kind of high availability and disaster recovery requirements do you have?</span></span> <span data-ttu-id="dfa93-130">Il server di chat persistente supporta il mirroring di SQL Server e il clustering di SQL Server per l'elevata disponibilità e supporta fino a 8 Server (4 attiva e 4 in standby) in un pool allungato con SQL Server log shipping per il ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="dfa93-130">Persistent Chat Server supports SQL Server mirroring and SQL Server clustering for high availability and supports up to 8 servers (4 active and 4 standby) in a stretched pool with SQL Server log shipping for disaster recovery.</span></span>

  - <span data-ttu-id="dfa93-131">Esistono requisiti normativi?</span><span class="sxs-lookup"><span data-stu-id="dfa93-131">Are there regulatory requirements?</span></span> <span data-ttu-id="dfa93-132">Se l'azienda si trova in un paese/area geografica in cui devono essere conservati i dati all'interno del paese, potrebbe essere necessario distribuire più pool di server di chat permanenti, ognuno locale in uno specifico percorso geografico.</span><span class="sxs-lookup"><span data-stu-id="dfa93-132">If your company is in a country/region where data needs to be kept within the country, you may need to deploy multiple Persistent Chat Server pools, each local to a specific geography.</span></span> <span data-ttu-id="dfa93-133">Una sala, una categoria o un componente aggiuntivo non si estende ai pool, ma appartiene solo a un pool di server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="dfa93-133">A room, category, or add-in does not span pools—it belongs to only one Persistent Chat Server pool.</span></span> <span data-ttu-id="dfa93-134">È possibile gestire il set di categorie, componenti aggiuntivi e sale per ogni pool di server di chat persistente.</span><span class="sxs-lookup"><span data-stu-id="dfa93-134">You can manage the set of categories, add-ins and rooms for each Persistent Chat Server pool.</span></span> <span data-ttu-id="dfa93-135">Gli utenti possono essere configurati per avere accesso alle sale in uno o più pool usando l'ambito di categoria AllowedMembers o l'ambito di appartenenza della sala, a seconda di come si progettano le categorie.</span><span class="sxs-lookup"><span data-stu-id="dfa93-135">Users can be configured to have access to rooms in one or more pools using the category AllowedMembers scope or Room’s membership scope, depending on how you design your categories.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="dfa93-136">La presenza di più pool di server di chat persistenti non offre più scala (è comunque possibile avere solo 80.000 utenti connessi contemporaneamente in tutti i pool di server di chat persistenti).</span><span class="sxs-lookup"><span data-stu-id="dfa93-136">Having multiple Persistent Chat Server pools does not give you more scale (you can still have only 80,000 concurrently connected users across all your Persistent Chat Server pools).</span></span> <span data-ttu-id="dfa93-137">Il motivo principale per il supporto di più pool di server di chat persistenti consiste nel supportare i problemi normativi.</span><span class="sxs-lookup"><span data-stu-id="dfa93-137">The primary reason for supporting multiple Persistent Chat Server pools is to support regulatory concerns.</span></span>

    
    </div>

</div>

<span> </span>

</div>

</div>

</div>

