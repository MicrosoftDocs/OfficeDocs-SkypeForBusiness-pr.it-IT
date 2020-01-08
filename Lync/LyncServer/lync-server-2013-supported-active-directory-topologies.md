---
title: 'Lync Server 2013: Topologie di Active Directory supportate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supported Active Directory topologies
ms:assetid: 0c76b778-7652-4eb0-b161-86f2d4a94ccf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398173(v=OCS.15)
ms:contentKeyID: 48183391
ms.date: 10/02/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3dc15cea3d07dc4e00f1d2a5527c862d90a078c6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977444"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supported-active-directory-topologies-in-lync-server-2013"></a><span data-ttu-id="7b666-102">Topologie di Active Directory supportate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7b666-102">Supported Active Directory topologies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7b666-103">_**Argomento Ultima modifica:** 2014-10-02_</span><span class="sxs-lookup"><span data-stu-id="7b666-103">_**Topic Last Modified:** 2014-10-02_</span></span>

<span data-ttu-id="7b666-104">Lync Server 2013 supporta le stesse topologie dei servizi di dominio Active Directory di Microsoft Lync Server 2010 e Microsoft Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="7b666-104">Lync Server 2013 supports the same Active Directory Domain Services topologies as Microsoft Lync Server 2010 and Microsoft Office Communications Server 2007 R2.</span></span> <span data-ttu-id="7b666-105">Sono supportate le topologie seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b666-105">The following topologies are supported:</span></span>

  - <span data-ttu-id="7b666-106">Singola foresta con un singolo dominio</span><span class="sxs-lookup"><span data-stu-id="7b666-106">Single forest with single domain</span></span>

  - <span data-ttu-id="7b666-107">Singola foresta con un solo albero e più domini</span><span class="sxs-lookup"><span data-stu-id="7b666-107">Single forest with a single tree and multiple domains</span></span>

  - <span data-ttu-id="7b666-108">Foresta singola con più alberi e spazi dei nomi disgiunti</span><span class="sxs-lookup"><span data-stu-id="7b666-108">Single forest with multiple trees and disjoint namespaces</span></span>

  - <span data-ttu-id="7b666-109">Più foreste in una topologia di foresta centrale</span><span class="sxs-lookup"><span data-stu-id="7b666-109">Multiple forests in a central forest topology</span></span>

  - <span data-ttu-id="7b666-110">Più foreste in una topologia di foresta di risorse</span><span class="sxs-lookup"><span data-stu-id="7b666-110">Multiple forests in a resource forest topology</span></span>

  - <span data-ttu-id="7b666-111">Più foreste in una topologia di foresta di risorse di Lync con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7b666-111">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="7b666-112">La figura seguente identifica le icone usate nelle illustrazioni in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="7b666-112">The following figure identifies the icons used in the illustrations in this section.</span></span>

<span data-ttu-id="7b666-113">**Legenda per le illustrazioni relative alle topologie**</span><span class="sxs-lookup"><span data-stu-id="7b666-113">**Key to topology illustrations**</span></span>

<span data-ttu-id="7b666-114">![Chiave per le illustrazioni della topologia](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "")</span><span class="sxs-lookup"><span data-stu-id="7b666-114">![Key to topology illustrations](images/Gg398173.0c3cc89f-6c43-4bc8-b2ec-61d89e391ee9(OCS.15).jpg "Key to topology illustrations")</span></span>

<div>

## <a name="single-forest-single-domain"></a><span data-ttu-id="7b666-115">Singola foresta, singolo dominio</span><span class="sxs-lookup"><span data-stu-id="7b666-115">Single Forest, Single Domain</span></span>

<span data-ttu-id="7b666-116">La topologia di Active Directory più semplice supportata da Lync Server, una singola foresta di domini, è una topologia comune.</span><span class="sxs-lookup"><span data-stu-id="7b666-116">The simplest Active Directory topology supported by Lync Server, a single domain forest, is a common topology.</span></span>

<span data-ttu-id="7b666-117">Nella figura seguente viene illustrata una distribuzione di Lync Server in una singola topologia di Active Directory di dominio.</span><span class="sxs-lookup"><span data-stu-id="7b666-117">The following figure illustrates a Lync Server deployment in a single domain Active Directory topology.</span></span>

<span data-ttu-id="7b666-118">**Topologia a un solo dominio**</span><span class="sxs-lookup"><span data-stu-id="7b666-118">**Single domain topology**</span></span>

<span data-ttu-id="7b666-119">![]Topologia a(images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "dominio") singolo</span><span class="sxs-lookup"><span data-stu-id="7b666-119">![Single domain topology](images/Gg398173.258b3b3f-0558-4a36-a4c2-031be7299668(OCS.15).jpg "Single domain topology")</span></span>

</div>

<div>

## <a name="single-forest-multiple-domains"></a><span data-ttu-id="7b666-120">Singola foresta, più domini</span><span class="sxs-lookup"><span data-stu-id="7b666-120">Single Forest, Multiple Domains</span></span>

<span data-ttu-id="7b666-121">Un'altra topologia di Active Directory supportata da Lync Server è una singola foresta costituita da un dominio radice e uno o più domini figlio.</span><span class="sxs-lookup"><span data-stu-id="7b666-121">Another Active Directory topology supported by Lync Server is a single forest that consists of a root domain and one or more child domains.</span></span> <span data-ttu-id="7b666-122">In questo tipo di topologia di Active Directory, il dominio in cui è possibile creare gli utenti può essere diverso dal dominio in cui si distribuisce Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b666-122">In this type of Active Directory topology, the domain where you create users can be different from the domain where you deploy Lync Server.</span></span> <span data-ttu-id="7b666-123">Tuttavia, se si distribuisce un pool Front-End, è necessario distribuire tutti i server front-end nel pool all'interno di un singolo dominio.</span><span class="sxs-lookup"><span data-stu-id="7b666-123">However, if you deploy a Front End pool, you must deploy all the Front End Servers in the pool within a single domain.</span></span> <span data-ttu-id="7b666-124">Il supporto di Lync Server per i gruppi di amministratori universali di Windows consente l'amministrazione tra domini.</span><span class="sxs-lookup"><span data-stu-id="7b666-124">Lync Server support for Windows universal administrator groups enables cross-domain administration.</span></span>

<span data-ttu-id="7b666-125">Nella figura seguente viene illustrata una distribuzione in una singola foresta con più domini.</span><span class="sxs-lookup"><span data-stu-id="7b666-125">The following figure illustrates a deployment in a single forest with multiple domains.</span></span> <span data-ttu-id="7b666-126">In questa figura l'icona dell'utente Mostra il dominio in cui è stato assegnato l'account utente e la freccia punta sul dominio in cui risiede il pool di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b666-126">In this figure, a user icon shows the domain where the user account is homed, and the arrow points to the domain where the Lync Server pool resides.</span></span> <span data-ttu-id="7b666-127">Gli account utente includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b666-127">User accounts include the following:</span></span>

  - <span data-ttu-id="7b666-128">Account utente nello stesso dominio del pool di Lync Server</span><span class="sxs-lookup"><span data-stu-id="7b666-128">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="7b666-129">Account utente in un dominio diverso dal pool di Lync Server</span><span class="sxs-lookup"><span data-stu-id="7b666-129">User accounts in a different domain from the Lync Server pool</span></span>

  - <span data-ttu-id="7b666-130">Account utente in un dominio figlio del dominio con il pool di Lync Server</span><span class="sxs-lookup"><span data-stu-id="7b666-130">User accounts in a child domain of the domain with the Lync Server pool</span></span>

<span data-ttu-id="7b666-131">**Foresta singola con più domini**</span><span class="sxs-lookup"><span data-stu-id="7b666-131">**Single forest with multiple domains**</span></span>

<span data-ttu-id="7b666-132">![Foresta singola con più domini con]una(images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "sola foresta con più domini")</span><span class="sxs-lookup"><span data-stu-id="7b666-132">![Single forest with multiple domains](images/Gg398173.2b809c72-c3cd-4fad-afe6-8c2dae779750(OCS.15).jpg "Single forest with multiple domains")</span></span>

</div>

<div>

## <a name="single-forest-multiple-trees"></a><span data-ttu-id="7b666-133">Singola foresta, più alberi</span><span class="sxs-lookup"><span data-stu-id="7b666-133">Single Forest, Multiple Trees</span></span>

<span data-ttu-id="7b666-134">Una topologia di foresta a più alberi è costituita da due o più domini che definiscono strutture ad albero indipendenti e spazi dei nomi Active Directory distinti.</span><span class="sxs-lookup"><span data-stu-id="7b666-134">A multiple-tree forest topology consists of two or more domains that define independent tree structures and separate Active Directory namespaces.</span></span>

<span data-ttu-id="7b666-135">Nella figura seguente viene illustrata una singola foresta con più alberi.</span><span class="sxs-lookup"><span data-stu-id="7b666-135">The following figure illustrates a single forest with multiple trees.</span></span> <span data-ttu-id="7b666-136">In questa figura l'icona di un utente Mostra il dominio in cui è stato assegnato l'account utente, una linea fissa punta a un pool di Lync Server che risiede nello stesso dominio o un altro, e una linea tratteggiata punta al pool di Lync Server che risiede in un albero diverso.</span><span class="sxs-lookup"><span data-stu-id="7b666-136">In this figure, a user icon shows the domain where the user account is homed, a solid line points to a Lync Server pool that resides in the same or a different domain, and a dashed line points to Lync Server pool that resides in a different tree.</span></span> <span data-ttu-id="7b666-137">Gli account utente includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b666-137">User accounts include the following:</span></span>

  - <span data-ttu-id="7b666-138">Account utente nello stesso dominio del pool di Lync Server</span><span class="sxs-lookup"><span data-stu-id="7b666-138">User accounts within the same domain as the Lync Server pool</span></span>

  - <span data-ttu-id="7b666-139">Account utente in un dominio diverso da (ma lo stesso albero) il pool di Lync Server</span><span class="sxs-lookup"><span data-stu-id="7b666-139">User accounts in a different domain from (but the same tree as) the Lync Server pool</span></span>

  - <span data-ttu-id="7b666-140">Account utente in un albero diverso dal pool di Lync Server</span><span class="sxs-lookup"><span data-stu-id="7b666-140">User accounts in a different tree from the Lync Server pool</span></span>

<span data-ttu-id="7b666-141">**Foresta singola con più alberi**</span><span class="sxs-lookup"><span data-stu-id="7b666-141">**Single forest with multiple trees**</span></span>

<span data-ttu-id="7b666-142">![Foresta singola con più]alberi(images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "foresta singola con più alberi")</span><span class="sxs-lookup"><span data-stu-id="7b666-142">![Single forest with multiple trees](images/Gg398173.db30fa49-174a-4974-8695-41dd78e39432(OCS.15).jpg "Single forest with multiple trees")</span></span>

</div>

<div>

## <a name="multiple-forests-central-forest"></a><span data-ttu-id="7b666-143">Più foreste, foresta centrale</span><span class="sxs-lookup"><span data-stu-id="7b666-143">Multiple Forests, Central Forest</span></span>

<span data-ttu-id="7b666-144">Lync Server supporta più foreste configurate in una topologia di foresta centrale.</span><span class="sxs-lookup"><span data-stu-id="7b666-144">Lync Server supports multiple forests that are configured in a central forest topology.</span></span> <span data-ttu-id="7b666-145">Le topologie della foresta centrale usano gli oggetti contatto nella foresta centrale per rappresentare gli utenti nelle altre foreste.</span><span class="sxs-lookup"><span data-stu-id="7b666-145">Central forest topologies use contact objects in the central forest to represent users in the other forests.</span></span> <span data-ttu-id="7b666-146">La foresta centrale ospita anche gli account utente per tutti gli utenti della foresta.</span><span class="sxs-lookup"><span data-stu-id="7b666-146">The central forest also hosts user accounts for any users in this forest.</span></span> <span data-ttu-id="7b666-147">Un prodotto di sincronizzazione della directory, ad esempio Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gestisce il ciclo di vita degli account utente in organizzazione: quando viene creato un nuovo account utente in una delle foreste o un account utente viene eliminato da una foresta, il prodotto di sincronizzazione della directory Sincronizza il contatto corrispondente nella foresta centrale.</span><span class="sxs-lookup"><span data-stu-id="7b666-147">A directory synchronization product, such as Microsoft Identity Integration Server (MIIS), Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts within the organization: When a new user account is created in one of the forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding contact in the central forest.</span></span>

<span data-ttu-id="7b666-148">Una foresta centrale presenta i vantaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7b666-148">A central forest has the following advantages:</span></span>

  - <span data-ttu-id="7b666-149">I server che esegue Lync Server vengono centralizzati in una singola foresta.</span><span class="sxs-lookup"><span data-stu-id="7b666-149">Servers running Lync Server are centralized within a single forest.</span></span>

  - <span data-ttu-id="7b666-150">Gli utenti possono cercare e comunicare con altri utenti in qualsiasi foresta.</span><span class="sxs-lookup"><span data-stu-id="7b666-150">Users can search for and communicate with other users in any forest.</span></span>

  - <span data-ttu-id="7b666-151">Gli utenti possono visualizzare la presenza di altri utenti in qualsiasi foresta.</span><span class="sxs-lookup"><span data-stu-id="7b666-151">Users can view presence of other users in any forest.</span></span>

  - <span data-ttu-id="7b666-152">Il prodotto di sincronizzazione della directory automatizza l'aggiunta e l'eliminazione degli oggetti contatto nella foresta centrale quando gli account utente vengono creati o rimossi.</span><span class="sxs-lookup"><span data-stu-id="7b666-152">The directory synchronization product automates the addition and deletion of contact objects in the central forest as user accounts are created or removed.</span></span>

<span data-ttu-id="7b666-153">Nella figura seguente viene illustrata una topologia di foresta centrale.</span><span class="sxs-lookup"><span data-stu-id="7b666-153">The following figure illustrates a central forest topology.</span></span> <span data-ttu-id="7b666-154">In questa figura esistono relazioni di trust bidirezionali tra il dominio che ospita Lync Server, che si trova nella foresta centrale e ogni dominio solo utente, che si trova in una foresta separata.</span><span class="sxs-lookup"><span data-stu-id="7b666-154">In this figure, there are two-way trust relationships between the domain that hosts Lync Server, which is in the central forest, and each user-only domain, which is in a separate forest.</span></span> <span data-ttu-id="7b666-155">Non è necessario estendere lo schema nelle foreste utente separate.</span><span class="sxs-lookup"><span data-stu-id="7b666-155">The schema in the separate user forests does not need to be extended.</span></span>

<span data-ttu-id="7b666-156">**Topologia a foresta centralizzata**</span><span class="sxs-lookup"><span data-stu-id="7b666-156">**Central forest topology**</span></span>

<span data-ttu-id="7b666-157">Topologia della(images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "foresta centrale") della ![topologia foresta centrale]</span><span class="sxs-lookup"><span data-stu-id="7b666-157">![Central forest topology](images/Gg398173.7feb049a-453b-4134-9128-873b83ee1755(OCS.15).jpg "Central forest topology")</span></span>

</div>

<div>

## <a name="multiple-forests-resource-forest"></a><span data-ttu-id="7b666-158">Più foreste, foresta delle risorse</span><span class="sxs-lookup"><span data-stu-id="7b666-158">Multiple Forests, Resource Forest</span></span>

<span data-ttu-id="7b666-159">In una topologia di foresta di risorse, una foresta è dedicata all'uso di applicazioni server, come Microsoft Exchange Server e Lync Server.</span><span class="sxs-lookup"><span data-stu-id="7b666-159">In a resource forest topology, one forest is dedicated to running server applications, such as Microsoft Exchange Server and Lync Server.</span></span> <span data-ttu-id="7b666-160">La foresta di risorse ospita le applicazioni server e una rappresentazione sincronizzata dell'oggetto utente attivo, ma non contiene account utente abilitati per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="7b666-160">The resource forest hosts the server applications and a synchronized representation of the active user object, but it does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="7b666-161">La foresta di risorse funge da ambiente di servizi condivisi per gli altri insiemi di strutture in cui risiedono gli oggetti utente.</span><span class="sxs-lookup"><span data-stu-id="7b666-161">The resource forest acts as a shared services environment for the other forests where user objects reside.</span></span> <span data-ttu-id="7b666-162">Le foreste degli utenti hanno una relazione di trust a livello di foresta con la foresta di risorse.</span><span class="sxs-lookup"><span data-stu-id="7b666-162">The user forests have a forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="7b666-163">Quando si distribuisce Lync Server in questo tipo di topologia, è possibile creare un oggetto utente disabilitato nella foresta di risorse per ogni account utente nelle foreste degli utenti.</span><span class="sxs-lookup"><span data-stu-id="7b666-163">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="7b666-164">Se Microsoft Exchange è già distribuito nella foresta delle risorse, gli account utente disabilitati potrebbero già esistere.</span><span class="sxs-lookup"><span data-stu-id="7b666-164">If Microsoft Exchange is already deployed in the resource forest, the disabled user accounts might already exist.</span></span> <span data-ttu-id="7b666-165">Un prodotto di sincronizzazione della directory, ad esempio MIIS, Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gestisce il ciclo di vita degli account utente.</span><span class="sxs-lookup"><span data-stu-id="7b666-165">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="7b666-166">Quando viene creato un nuovo account utente in una delle foreste degli utenti o un account utente viene eliminato da una foresta, il prodotto di sincronizzazione della directory Sincronizza la corrispondente rappresentazione dell'utente nella foresta di risorse.</span><span class="sxs-lookup"><span data-stu-id="7b666-166">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span>

<span data-ttu-id="7b666-167">Questa topologia può essere usata per specificare un'infrastruttura condivisa per i servizi in organizzazioni che gestiscono più foreste o per separare l'amministrazione degli oggetti di Active Directory da un'altra amministrazione.</span><span class="sxs-lookup"><span data-stu-id="7b666-167">This topology can be used to provide a shared infrastructure for services in organizations that manage multiple forests or to separate the administration of Active Directory objects from other administration.</span></span> <span data-ttu-id="7b666-168">Le aziende che devono isolare l'amministrazione di Active Directory per motivi di sicurezza spesso scelgono questa topologia.</span><span class="sxs-lookup"><span data-stu-id="7b666-168">Companies that need to isolate Active Directory administration for security reasons often choose this topology.</span></span>

<span data-ttu-id="7b666-169">Questa topologia offre il vantaggio di limitare la necessità di estendere lo schema di Active Directory a una singola foresta, ossia alla foresta di risorse.</span><span class="sxs-lookup"><span data-stu-id="7b666-169">This topology provides the benefit of limiting the need to extend the Active Directory schema to a single forest (that is, the resource forest).</span></span>

<span data-ttu-id="7b666-170">Il diagramma seguente illustra una topologia di foresta di risorse.</span><span class="sxs-lookup"><span data-stu-id="7b666-170">The following diagram illustrates a resource forest topology.</span></span>

<span data-ttu-id="7b666-171">**Topologia della foresta di risorse**</span><span class="sxs-lookup"><span data-stu-id="7b666-171">**Resource forest topology**</span></span>

<span data-ttu-id="7b666-172">Topologia della(images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "foresta della risorsa Active") directory della foresta di ![Active Directory]</span><span class="sxs-lookup"><span data-stu-id="7b666-172">![Active Directory Resource Forest Topology](images/Gg398173.54ab82f1-e9e5-40f0-a54e-86e340b65c2a(OCS.15).jpg "Active Directory Resource Forest Topology")</span></span>

</div>

<div>

## <a name="multiple-forests-in-a-lync-resource-forest-topology-with-exchange-online"></a><span data-ttu-id="7b666-173">Più foreste in una topologia di foresta di risorse di Lync con Exchange Online</span><span class="sxs-lookup"><span data-stu-id="7b666-173">Multiple forests in a Lync resource forest topology with Exchange Online</span></span>

<span data-ttu-id="7b666-174">In questa topologia, uno o più insiemi di strutture si trovano in locale e sono dedicati all'hosting degli account utente di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="7b666-174">In this topology, one or more forests are located on-premises and are dedicated to hosting Active Directory user accounts.</span></span> <span data-ttu-id="7b666-175">La foresta delle risorse si trova fuori sede e viene gestita da un provider di hosting di terze parti.</span><span class="sxs-lookup"><span data-stu-id="7b666-175">The resource forest is located off-premises and is maintained by a third-party hosting provider.</span></span> <span data-ttu-id="7b666-176">La foresta di risorse contiene solo la distribuzione di Lync Server e una replica sincronizzata degli account utente dagli insiemi di strutture degli account utente locali.</span><span class="sxs-lookup"><span data-stu-id="7b666-176">The resource forest contains only the Lync Server deployment and a synchronized replication of the user accounts from the on-premises user accounts forest(s).</span></span> <span data-ttu-id="7b666-177">Non contiene account utente abilitati per l'accesso.</span><span class="sxs-lookup"><span data-stu-id="7b666-177">It does not contain logon-enabled user accounts.</span></span> <span data-ttu-id="7b666-178">Exchange viene distribuito nella foresta di account utente locale integrata insieme a Exchange Online (Hybrid) o i servizi di posta elettronica per gli account utente locali vengono forniti esclusivamente da Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="7b666-178">Exchange is deployed either in the on-premises user account forest(s) integrated along with Exchange Online (Hybrid), or email services for the on-premises user accounts are provided exclusively by Exchange Online.</span></span>

<span data-ttu-id="7b666-179">La foresta di risorse funge da ambiente di servizi condivisi per gli insiemi di strutture Active Directory locali in cui risiedono gli oggetti utente.</span><span class="sxs-lookup"><span data-stu-id="7b666-179">The resource forest acts as a shared services environment for the on-premises Active Directory forest(s) where user objects reside.</span></span> <span data-ttu-id="7b666-180">Le foreste dell'account utente hanno una relazione di trust a livello di foresta unidirezionale con la foresta di risorse.</span><span class="sxs-lookup"><span data-stu-id="7b666-180">The user account forest(s) have a one way forest-level trust relationship with the resource forest.</span></span> <span data-ttu-id="7b666-181">Quando si distribuisce Lync Server in questo tipo di topologia, è possibile creare un oggetto utente disabilitato nella foresta di risorse per ogni account utente nelle foreste degli utenti.</span><span class="sxs-lookup"><span data-stu-id="7b666-181">When you deploy Lync Server in this type of topology, you create one disabled user object in the resource forest for every user account in the user forests.</span></span> <span data-ttu-id="7b666-182">Un prodotto di sincronizzazione della directory, ad esempio MIIS, Microsoft Forefront Identity Manager (FIM) 2010 o Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), gestisce il ciclo di vita degli account utente.</span><span class="sxs-lookup"><span data-stu-id="7b666-182">A directory synchronization product, such as MIIS, Microsoft Forefront Identity Manager (FIM) 2010, or Microsoft Identity Lifecycle Manager (ILM) 2007 Feature Pack 1 (FP1), manages the life cycle of user accounts.</span></span> <span data-ttu-id="7b666-183">Quando viene creato un nuovo account utente in una delle foreste degli utenti o un account utente viene eliminato da una foresta, il prodotto di sincronizzazione della directory Sincronizza la corrispondente rappresentazione dell'utente nella foresta di risorse.</span><span class="sxs-lookup"><span data-stu-id="7b666-183">When a new user account is created in one of the user forests or a user account is deleted from a forest, the directory synchronization product synchronizes the corresponding user representation in the resource forest.</span></span> <span data-ttu-id="7b666-184">Per altre informazioni sulla configurazione di una distribuzione con più insiemi di strutture, vedere [distribuzione di Lync in un'architettura con più insiemi di strutture (partner Lync ospitata con Exchange Hybrid)](http://go.microsoft.com/fwlink/p/?linkid=513216).</span><span class="sxs-lookup"><span data-stu-id="7b666-184">For more information about configuring a multi-forest deployment, see [Deploying Lync in a Multi-Forest Architecture (Partner Hosted Lync with Exchange Hybrid)](http://go.microsoft.com/fwlink/p/?linkid=513216).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

