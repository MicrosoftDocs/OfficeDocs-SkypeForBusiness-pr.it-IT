---
title: 'Lync Server 2013: topologie di Active Directory supportate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 46f9236bfbd110ee17811edec2e3e81fc4a0e0f4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524163"
---
# <a name="supported-active-directory-topologies-in-lync-server-2013"></a><span data-ttu-id="d2358-102">Topologie di Active Directory supportate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d2358-102">Supported Active Directory topologies in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d2358-103">_**Ultimo argomento modificato:** 2014-10-02_</span><span class="sxs-lookup"><span data-stu-id="d2358-103">_**Topic Last Modified:** 2014-10-02_</span></span>

<span data-ttu-id="d2358-104">Lync Server 2013 supporta le stesse topologie di servizi di dominio Active Directory di Microsoft Lync Server 2010 e Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="d2358-104">Lync Server 2013 supports the same Active Directory Domain Services topologies as Microsoft Lync Server 2010 and Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="d2358-105">Le topologie supportate sono:</span><span class="sxs-lookup"><span data-stu-id="d2358-105">The following topologies are supported:</span></span>

  - <span data-ttu-id="d2358-106">Foresta singola con singolo dominio</span><span class="sxs-lookup"><span data-stu-id="d2358-106">Single forest with single domain</span></span>

  - <span data-ttu-id="d2358-107">Foresta singola con albero singolo e più domini</span><span class="sxs-lookup"><span data-stu-id="d2358-107">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="d2358-108">Foresta singola con più alberi e spazi dei nomi disgiunti</span><span class="sxs-lookup"><span data-stu-id="d2358-108">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="d2358-109">Più foreste in una topologia di foreste centralizzate</span><span class="sxs-lookup"><span data-stu-id="d2358-109">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="d2358-110">Più foreste in una topologia di foresta di risorse</span><span class="sxs-lookup"><span data-stu-id="d2358-110">Multiple forests in a resource forest topology</span></span>

  - <span data-ttu-id="d2358-111">Più foreste in una topologia di foresta di risorse di Lync con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d2358-111">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="d2358-112">Nella figura seguente vengono identificate le icone utilizzate nelle illustrazioni di questa sezione.</span><span class="sxs-lookup"><span data-stu-id="d2358-112">The following figure identifies the icons used in the illustrations in this section.</span></span>

<span data-ttu-id="d2358-113">**Legenda per le illustrazioni relative alle topologie**</span><span class="sxs-lookup"><span data-stu-id="d2358-113">**Key to topology illustrations**</span></span>

<span data-ttu-id="d2358-114">![Legenda per le illustrazioni relative alle topologie](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Legenda per le illustrazioni relative alle topologie")</span><span class="sxs-lookup"><span data-stu-id="d2358-114">![Key to topology illustrations](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Key to topology illustrations")</span></span>

<div>

## <a name="single-forest-single-domain"></a><span data-ttu-id="d2358-115">Foresta singola, dominio singolo</span><span class="sxs-lookup"><span data-stu-id="d2358-115">Single Forest, Single Domain</span></span>

<span data-ttu-id="d2358-116">La topologia di Active Directory più semplice supportata da Lync Server, una foresta a dominio singolo, è una topologia comune.</span><span class="sxs-lookup"><span data-stu-id="d2358-116">The simplest Active Directory topology supported by Lync Server, a single domain forest, is a common topology.</span></span>

<span data-ttu-id="d2358-117">Nella figura seguente viene illustrata una distribuzione di Lync Server in una topologia di Active Directory a dominio singolo.</span><span class="sxs-lookup"><span data-stu-id="d2358-117">The following figure illustrates a Lync Server deployment in a single domain Active Directory topology.</span></span>

<span data-ttu-id="d2358-118">**Topologia a dominio singolo**</span><span class="sxs-lookup"><span data-stu-id="d2358-118">**Single domain topology**</span></span>

<span data-ttu-id="d2358-119">![Topologia a dominio singolo](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Topologia a dominio singolo")</span><span class="sxs-lookup"><span data-stu-id="d2358-119">![Single domain topology](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Single domain topology")</span></span>

</div>

<div>

## <a name="single-forest-multiple-domains"></a><span data-ttu-id="d2358-120">Foresta singola, più domini</span><span class="sxs-lookup"><span data-stu-id="d2358-120">Single Forest, Multiple Domains</span></span>

<span data-ttu-id="d2358-121">Un'altra topologia di Active Directory supportata da Lync Server è una foresta singola costituita da un dominio radice e da uno o più domini figlio.</span><span class="sxs-lookup"><span data-stu-id="d2358-121">Another Active Directory topology supported by Lync Server is a single forest that consists of a root domain and one or more child domains.</span></span> <span data-ttu-id="d2358-122">In questo tipo di topologia di Active Directory, il dominio in cui si creano gli utenti può essere diverso dal dominio in cui si distribuisce Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d2358-122">In this type of Active Directory topology, the domain where you create users can be different from the domain where you deploy Lync Server.</span></span> <span data-ttu-id="d2358-123">Se però si distribuisce un pool Front End, sarà necessario distribuire tutti i Front End Server del pool in un singolo dominio.</span><span class="sxs-lookup"><span data-stu-id="d2358-123">However, if you deploy a Front End pool, you must deploy all the Front End Servers in the pool within a single domain.</span></span> <span data-ttu-id="d2358-124">Il supporto di Lync Server per i gruppi di amministratori universali di Windows consente l'amministrazione tra domini.</span><span class="sxs-lookup"><span data-stu-id="d2358-124">Lync Server support for Windows universal administrator groups enables cross-domain administration.</span></span>

<span data-ttu-id="d2358-125">Nella figura seguente viene illustrata una distribuzione in una foresta singola con più domini.</span><span class="sxs-lookup"><span data-stu-id="d2358-125">The following figure illustrates a deployment in a single forest with multiple domains.</span></span> <span data-ttu-id="d2358-126">In questa figura viene visualizzata un'icona dell'utente che indica il dominio in cui risiede l'account utente e la freccia punta al dominio in cui risiede il pool di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d2358-126">In this figure, a user icon shows the domain where the user account is homed, and the arrow points to the domain where the Lync Server pool resides.</span></span> <span data-ttu-id="d2358-127">Gli account utente includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2358-127">User accounts include the following:</span></span>

  - <span data-ttu-id="d2358-128">Account utente all'interno dello stesso dominio del pool di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d2358-128">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="d2358-129">Account utente in un dominio diverso dal pool di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d2358-129">User accounts in a different domain from the Lync Server pool</span></span>

  - <span data-ttu-id="d2358-130">Account utente in un dominio figlio del dominio con il pool di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d2358-130">User accounts in a child domain of the domain with the Lync Server pool</span></span>

<span data-ttu-id="d2358-131">**Foresta singola con più domini**</span><span class="sxs-lookup"><span data-stu-id="d2358-131">**Single forest with multiple domains**</span></span>

<span data-ttu-id="d2358-132">![Foresta singola con più domini](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Foresta singola con più domini")</span><span class="sxs-lookup"><span data-stu-id="d2358-132">![Single forest with multiple domains](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Single forest with multiple domains")</span></span>

</div>

<div>

## <a name="single-forest-multiple-trees"></a><span data-ttu-id="d2358-133">Foresta singola, più alberi</span><span class="sxs-lookup"><span data-stu-id="d2358-133">Single Forest, Multiple Trees</span></span>

<span data-ttu-id="d2358-134">Una topologia di foresta a più alberi è costituita da due o più domini che definiscono strutture ad albero indipendenti e spazi dei nomi di Active Directory separati.</span><span class="sxs-lookup"><span data-stu-id="d2358-134">A multiple-tree forest topology consists of two or more domains that define independent tree structures and separate Active Directory namespaces.</span></span>

<span data-ttu-id="d2358-135">Nella figura seguente viene illustrata una foresta singola con più alberi.</span><span class="sxs-lookup"><span data-stu-id="d2358-135">The following figure illustrates a single forest with multiple trees.</span></span> <span data-ttu-id="d2358-136">In questa figura, un'icona dell'utente Visualizza il dominio in cui è ospitato l'account utente, una linea continua che punta a un pool di Lync Server che risiede nello stesso dominio o in un altro, e una linea tratteggiata punta al pool di Lync Server che risiede in un albero diverso.</span><span class="sxs-lookup"><span data-stu-id="d2358-136">In this figure, a user icon shows the domain where the user account is homed, a solid line points to a Lync Server pool that resides in the same or a different domain, and a dashed line points to Lync Server pool that resides in a different tree.</span></span> <span data-ttu-id="d2358-137">Gli account utente includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2358-137">User accounts include the following:</span></span>

  - <span data-ttu-id="d2358-138">Account utente all'interno dello stesso dominio del pool di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d2358-138">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="d2358-139">Account utente in un dominio diverso da (ma lo stesso albero di) il pool di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d2358-139">User accounts in a different domain from (but the same tree as) the Lync Server pool</span></span>

  - <span data-ttu-id="d2358-140">Account utente in un albero diverso dal pool di Lync Server</span><span class="sxs-lookup"><span data-stu-id="d2358-140">User accounts in a different tree from the Lync Server pool</span></span>

<span data-ttu-id="d2358-141">**Foresta singola con più alberi**</span><span class="sxs-lookup"><span data-stu-id="d2358-141">**Single forest with multiple trees**</span></span>

<span data-ttu-id="d2358-142">![Foresta singola con più alberi](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Foresta singola con più alberi")</span><span class="sxs-lookup"><span data-stu-id="d2358-142">![Single forest with multiple trees](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Single forest with multiple trees")</span></span>

</div>

<div>

## <a name="multiple-forests-central-forest"></a><span data-ttu-id="d2358-143">Più foreste, foresta centralizzata</span><span class="sxs-lookup"><span data-stu-id="d2358-143">Multiple Forests, Central Forest</span></span>

<span data-ttu-id="d2358-144">Lync Server supporta più insiemi di strutture configurati in una topologia a foresta centralizzata.</span><span class="sxs-lookup"><span data-stu-id="d2358-144">Lync Server supports multiple forests that are configured in a central forest topology.</span></span> <span data-ttu-id="d2358-145">Le topologie della foresta centrale utilizzano gli oggetti contatto nella foresta centrale per rappresentare gli utenti nelle altre foreste.</span><span class="sxs-lookup"><span data-stu-id="d2358-145">Central forest topologies use contact objects in the central forest to represent users in the other forests.</span></span> <span data-ttu-id="d2358-146">La foresta centrale ospita anche account utente per tutti gli utenti della foresta.</span><span class="sxs-lookup"><span data-stu-id="d2358-146">The central forest also hosts user accounts for any users in this forest.</span></span> <span data-ttu-id="d2358-147">Un prodotto di sincronizzazione della directory, ad esempio Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gestisce il ciclo di vita degli account utente all'interno dell'organizzazione: quando viene creato un nuovo account utente in uno dei boschi o un account utente viene eliminato da una foresta, il prodotto di sincronizzazione della directory Sincronizza il contatto corrispondente nella foresta centrale.</span><span class="sxs-lookup"><span data-stu-id="d2358-147">A directory synchronization product, such as Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts within the organization: When a new user account is created in one of the forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding contact in the central forest.</span></span>

<span data-ttu-id="d2358-148">Una foresta centralizzata presenta i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="d2358-148">A central forest has the following advantages:</span></span>

  - <span data-ttu-id="d2358-149">I server che eseguono Lync Server sono centralizzati all'interno di una singola foresta.</span><span class="sxs-lookup"><span data-stu-id="d2358-149">Servers running Lync Server are centralized within a single forest.</span></span>

  - <span data-ttu-id="d2358-150">Gli utenti possono cercare altri utenti e comunicare con loro in qualsiasi foresta.</span><span class="sxs-lookup"><span data-stu-id="d2358-150">Users can search for and communicate with other users in any forest.</span></span>

  - <span data-ttu-id="d2358-151">Gli utenti possono visualizzare la presenza di altri utenti in qualsiasi foresta.</span><span class="sxs-lookup"><span data-stu-id="d2358-151">Users can view presence of other users in any forest.</span></span>

  - <span data-ttu-id="d2358-152">Il prodotto di sincronizzazione della directory automatizza l'aggiunta e l'eliminazione di oggetti contatto nella foresta centralizzata durante la creazione o la rimozione di account utente.</span><span class="sxs-lookup"><span data-stu-id="d2358-152">The directory synchronization product automates the addition and deletion of contact objects in the central forest as user accounts are created or removed.</span></span>

<span data-ttu-id="d2358-153">Nella figura seguente viene illustrata una topologia a foresta centralizzata.</span><span class="sxs-lookup"><span data-stu-id="d2358-153">The following figure illustrates a central forest topology.</span></span> <span data-ttu-id="d2358-154">In questa figura, esistono relazioni di trust bidirezionali tra il dominio che ospita Lync Server, che si trova nella foresta centrale, e ogni dominio solo utente, che si trova in una foresta separata.</span><span class="sxs-lookup"><span data-stu-id="d2358-154">In this figure, there are two-way trust relationships between the domain that hosts Lync Server, which is in the central forest, and each user-only domain, which is in a separate forest.</span></span> <span data-ttu-id="d2358-155">Non è necessario estendere lo schema nelle foreste degli utenti separate.</span><span class="sxs-lookup"><span data-stu-id="d2358-155">The schema in the separate user forests does not need to be extended.</span></span>

<span data-ttu-id="d2358-156">**Topologia a foresta centralizzata**</span><span class="sxs-lookup"><span data-stu-id="d2358-156">**Central forest topology**</span></span>

<span data-ttu-id="d2358-157">![Topologia a foresta centralizzata](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Topologia a foresta centralizzata")</span><span class="sxs-lookup"><span data-stu-id="d2358-157">![Central forest topology](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Central forest topology")</span></span>

</div>

<div>

## <a name="multiple-forests-resource-forest"></a><span data-ttu-id="d2358-158">Più foreste, foresta delle risorse</span><span class="sxs-lookup"><span data-stu-id="d2358-158">Multiple Forests, Resource Forest</span></span>

<span data-ttu-id="d2358-159">In una topologia con foresta di risorse, una foresta è dedicata all'esecuzione di applicazioni server, ad esempio Microsoft Exchange Server e Lync Server.</span><span class="sxs-lookup"><span data-stu-id="d2358-159">In a resource forest topology, one forest is dedicated to running server applications, such as Microsoft Exchange Server and Lync Server.</span></span> <span data-ttu-id="d2358-160">La foresta delle risorse ospita le applicazioni server e una rappresentazione sincronizzata dell'oggetto utente attivo, ma non contiene alcun account utente abilitato per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d2358-160">The resource forest hosts the server applications and a synchronized representation of the active user object, but it does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="d2358-161">La foresta delle risorse funge da ambiente dei servizi condivisi per le altre foreste in cui risiedono gli oggetti utente.</span><span class="sxs-lookup"><span data-stu-id="d2358-161">The resource forest acts as a shared services environment for the other forests where user objects reside.</span></span> <span data-ttu-id="d2358-162">Le foreste degli utenti presentano una relazione di trust a livello di foresta con la foresta delle risorse.</span><span class="sxs-lookup"><span data-stu-id="d2358-162">The user forests have a forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="d2358-163">Quando si distribuisce Lync Server in questo tipo di topologia, è possibile creare un oggetto utente disabilitato nella foresta di risorse per ogni account utente nelle foreste di utenti.</span><span class="sxs-lookup"><span data-stu-id="d2358-163">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="d2358-164">Se Microsoft Exchange è già distribuito nella foresta di risorse, potrebbero esistere già gli account utente disabilitati.</span><span class="sxs-lookup"><span data-stu-id="d2358-164">If Microsoft Exchange is already deployed in the resource forest, the disabled user accounts might already exist.</span></span> <span data-ttu-id="d2358-165">Un prodotto di sincronizzazione della directory, come MIIS, Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gestisce il ciclo di vita degli account utente.</span><span class="sxs-lookup"><span data-stu-id="d2358-165">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="d2358-166">Quando un nuovo account utente viene creato in una delle foreste degli utenti o un account utente viene eliminato da una foresta, il prodotto di sincronizzazione della directory sincronizza la rappresentazione dell'utente corrispondente nella foresta delle risorse.</span><span class="sxs-lookup"><span data-stu-id="d2358-166">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span>

<span data-ttu-id="d2358-p108">Questa topologia può essere utilizzata per fornire un'infrastruttura condivisa per i servizi in organizzazioni che gestiscono più foreste o per separare l'amministrazione degli oggetti di Active Directory da un'altra amministrazione. Si tratta della scelta più frequente da parte delle società che hanno la necessità di isolare l'amministrazione di Active Directory per motivi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="d2358-p108">This topology can be used to provide a shared infrastructure for services in organizations that manage multiple forests or to separate the administration of Active Directory objects from other administration. Companies that need to isolate Active Directory administration for security reasons often choose this topology.</span></span>

<span data-ttu-id="d2358-169">Questa topologia offre il vantaggio di limitare la necessità di estendere lo schema di Active Directory a una singola foresta, ovvero la foresta delle risorse.</span><span class="sxs-lookup"><span data-stu-id="d2358-169">This topology provides the benefit of limiting the need to extend the Active Directory schema to a single forest (that is, the resource forest).</span></span>

<span data-ttu-id="d2358-170">Nella figura seguente viene illustrata la topologia con foresta delle risorse.</span><span class="sxs-lookup"><span data-stu-id="d2358-170">The following diagram illustrates a resource forest topology.</span></span>

<span data-ttu-id="d2358-171">**Topologia della foresta di risorse**</span><span class="sxs-lookup"><span data-stu-id="d2358-171">**Resource forest topology**</span></span>

<span data-ttu-id="d2358-172">![Topologia della foresta di risorse di Active Directory](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Topologia della foresta di risorse di Active Directory")</span><span class="sxs-lookup"><span data-stu-id="d2358-172">![Active Directory Resource Forest Topology](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory Resource Forest Topology")</span></span>

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a><span data-ttu-id="d2358-173">Più foreste in una topologia di foresta di risorse di Lync con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="d2358-173">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="d2358-174">In questa topologia, una o più foreste si trovano in locale e sono dedicate all'hosting degli account utente di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d2358-174">In this topology, one or more forests are located on-premises and are dedicated to hosting Active Directory user accounts.</span></span> <span data-ttu-id="d2358-175">La foresta di risorse si trova fuori sede ed è gestita da un provider di hosting di terze parti.</span><span class="sxs-lookup"><span data-stu-id="d2358-175">The resource forest is located off-premises and is maintained by a third-party hosting provider.</span></span> <span data-ttu-id="d2358-176">La foresta di risorse contiene solo la distribuzione di Lync Server e una replica sincronizzata degli account utente dalla foresta degli account utente locali.</span><span class="sxs-lookup"><span data-stu-id="d2358-176">The resource forest contains only the Lync Server deployment and a synchronized replication of the user accounts from the on-premises user accounts forest(s).</span></span> <span data-ttu-id="d2358-177">Non contiene account utente abilitati per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="d2358-177">It does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="d2358-178">Exchange è distribuito in una foresta di account utente locale integrata insieme a Exchange Online (ibrido) oppure i servizi di posta elettronica per gli account utente locali sono forniti esclusivamente da Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="d2358-178">Exchange is deployed either in the on-premises user account forest(s) integrated along with Exchange Online (Hybrid), or email services for the on-premises user accounts are provided exclusively by Exchange Online.</span></span>

<span data-ttu-id="d2358-179">La foresta di risorse funge da ambiente di servizi condivisi per le foreste di Active Directory locali in cui risiedono gli oggetti utente.</span><span class="sxs-lookup"><span data-stu-id="d2358-179">The resource forest acts as a shared services environment for the on-premises Active Directory forest(s) where user objects reside.</span></span> <span data-ttu-id="d2358-180">Le foreste degli account utente dispongono di una relazione di trust a livello di foresta unidirezionale con la foresta di risorse.</span><span class="sxs-lookup"><span data-stu-id="d2358-180">The user account forest(s) have a one way forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="d2358-181">Quando si distribuisce Lync Server in questo tipo di topologia, è possibile creare un oggetto utente disabilitato nella foresta di risorse per ogni account utente nelle foreste di utenti.</span><span class="sxs-lookup"><span data-stu-id="d2358-181">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="d2358-182">Un prodotto di sincronizzazione della directory, come MIIS, Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gestisce il ciclo di vita degli account utente.</span><span class="sxs-lookup"><span data-stu-id="d2358-182">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="d2358-183">Quando un nuovo account utente viene creato in una delle foreste degli utenti o un account utente viene eliminato da una foresta, il prodotto di sincronizzazione della directory sincronizza la rappresentazione dell'utente corrispondente nella foresta delle risorse.</span><span class="sxs-lookup"><span data-stu-id="d2358-183">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span> <span data-ttu-id="d2358-184">Per ulteriori informazioni sulla configurazione di una distribuzione a più foreste, vedere [Deploying Lync in a multi-Forest Architecture (Partner Hosted Lync with Exchange Hybrid)](https://go.microsoft.com/fwlink/p/?linkid=513216).</span><span class="sxs-lookup"><span data-stu-id="d2358-184">For more information about configuring a multi-forest deployment, see [Deploying Lync in a Multi-Forest Architecture (Partner Hosted Lync with Exchange Hybrid)](https://go.microsoft.com/fwlink/p/?linkid=513216).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

