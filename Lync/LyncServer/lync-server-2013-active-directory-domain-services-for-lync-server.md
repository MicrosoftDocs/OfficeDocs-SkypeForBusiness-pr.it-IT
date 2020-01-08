---
title: 'Lync Server 2013: Servizi di dominio Active Directory per Lync Server'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9a7dd0a5d5c6d8323abab3a8abfbc5f1025379e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977340"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="8aea2-102">Servizi di dominio Active Directory per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8aea2-102">Active Directory Domain Services for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8aea2-103">_**Argomento Ultima modifica:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="8aea2-103">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="8aea2-104">Active Directory Domain Services funziona come servizio directory per le reti Windows Server 2003, Windows Server 2008, Windows Server 2012 e Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="8aea2-104">Active Directory Domain Services functions as the directory service for Windows Server 2003, Windows Server 2008, Windows Server 2012, and Windows Server 2012 R2 networks.</span></span> <span data-ttu-id="8aea2-105">Servizi di dominio Active Directory funge anche da fondamento per cui è stata creata l'infrastruttura di sicurezza di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8aea2-105">Active Directory Domain Services also serves as the foundation on which the Microsoft Lync Server 2013 security infrastructure is built.</span></span> <span data-ttu-id="8aea2-106">Lo scopo di questa sezione è descrivere in che modo Lync Server 2013 USA i servizi di dominio Active Directory per creare un ambiente affidabile per la messaggistica istantanea, le conferenze Web, i contenuti multimediali e la voce.</span><span class="sxs-lookup"><span data-stu-id="8aea2-106">The purpose of this section is to describe how Lync Server 2013 uses Active Directory Domain Services to create a trustworthy environment for IM, Web conferencing, media, and voice.</span></span> <span data-ttu-id="8aea2-107">Per informazioni dettagliate sulle estensioni di Lync Server per i servizi di dominio Active Directory e sulla preparazione dell'ambiente per i servizi di dominio Active Directory, vedere [preparazione di servizi di dominio Active Directory per Lync server 2013](lync-server-2013-preparing-active-directory-domain-services.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8aea2-107">For details about Lync Server extensions to Active Directory Domain Services and about preparing your environment for Active Directory Domain Services, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span> <span data-ttu-id="8aea2-108">Per informazioni dettagliate sul ruolo dei servizi di dominio Active Directory nelle reti Windows Server, vedere la documentazione relativa alla versione del sistema operativo in uso.</span><span class="sxs-lookup"><span data-stu-id="8aea2-108">For details about the role of Active Directory Domain Services in Windows Server networks, see the documentation for the version of the operating system you are using.</span></span>

<span data-ttu-id="8aea2-109">Lync Server 2013 USA i servizi di dominio Active Directory per archiviare:</span><span class="sxs-lookup"><span data-stu-id="8aea2-109">Lync Server 2013 uses Active Directory Domain Services to store:</span></span>

  - <span data-ttu-id="8aea2-110">Impostazioni globali che richiedono tutti i server in cui è in uso Lync Server 2013 in una foresta.</span><span class="sxs-lookup"><span data-stu-id="8aea2-110">Global settings that all servers running Lync Server 2013 in a forest require.</span></span>

  - <span data-ttu-id="8aea2-111">Informazioni sul servizio che identificano i ruoli di tutti i server in cui è in uso Lync Server 2013 in una foresta.</span><span class="sxs-lookup"><span data-stu-id="8aea2-111">Service information that identifies the roles of all servers running Lync Server 2013 in a forest.</span></span>

  - <span data-ttu-id="8aea2-112">Alcune impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="8aea2-112">Some user settings.</span></span>

<div>

## <a name="active-directory-infrastructure"></a><span data-ttu-id="8aea2-113">Infrastruttura di Active Directory</span><span class="sxs-lookup"><span data-stu-id="8aea2-113">Active Directory Infrastructure</span></span>

<span data-ttu-id="8aea2-114">I requisiti di infrastruttura per Active Directory includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="8aea2-114">Infrastructure requirements for Active Directory include the following:</span></span>

  - <span data-ttu-id="8aea2-115">Requisiti del sistema operativo per i controller di dominio</span><span class="sxs-lookup"><span data-stu-id="8aea2-115">Operating system requirements for domain controllers</span></span>

  - <span data-ttu-id="8aea2-116">Requisiti del livello di funzionalità Domain e Forest</span><span class="sxs-lookup"><span data-stu-id="8aea2-116">Domain and forest functional level requirements</span></span>

  - <span data-ttu-id="8aea2-117">Requisiti del dominio catalogo globale</span><span class="sxs-lookup"><span data-stu-id="8aea2-117">Global catalog domain requirements</span></span>

<span data-ttu-id="8aea2-118">Per informazioni dettagliate, vedere [requisiti per l'infrastruttura di Active Directory per Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8aea2-118">For details, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a><span data-ttu-id="8aea2-119">Preparazione dei servizi di dominio Active Directory</span><span class="sxs-lookup"><span data-stu-id="8aea2-119">Active Directory Domain Services Preparation</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8aea2-120">È consigliabile distribuire le impostazioni globali nel contenitore di configurazione anziché nel contenitore di sistema.</span><span class="sxs-lookup"><span data-stu-id="8aea2-120">We recommend that you deploy global settings to the Configuration container instead of the System container.</span></span> <span data-ttu-id="8aea2-121">Questo non migliora la sicurezza, ma può determinare miglioramenti della scalabilità per alcune topologie di servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8aea2-121">This does not enhance security, but can result in scalability improvements for some Active Directory Domain Services topologies.</span></span> <span data-ttu-id="8aea2-122">Se si esegue la migrazione da Microsoft Office Communications Server 2007 e si usa il contenitore di sistema ma si prevede di usare il contenitore di configurazione, è necessario trasferire le impostazioni nel contenitore di sistema prima di eseguire qualsiasi preparazione per l'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="8aea2-122">If you are migrating from Microsoft Office Communications Server 2007 and have used the System container but plan to use the Configuration container, you MUST move the settings in the System container BEFORE you do any upgrade preparations.</span></span> <span data-ttu-id="8aea2-123">Per eseguire la migrazione delle impostazioni del contenitore di sistema nel contenitore di configurazione, vedere lo strumento di migrazione delle <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>impostazioni globali di Office Communications Server 2007.</span><span class="sxs-lookup"><span data-stu-id="8aea2-123">To migrate your System container settings to the Configuration container, see Office Communications Server 2007 Global Settings Migration Tool at <A href="http://go.microsoft.com/fwlink/p/?linkid=145236">http://go.microsoft.com/fwlink/p/?LinkId=145236</A>.</span></span>



</div>

<span data-ttu-id="8aea2-124">Quando si distribuisce Lync Server 2013, il primo passaggio consiste nel preparare i servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8aea2-124">When deploying Lync Server 2013, the first step is to prepare Active Directory Domain Services.</span></span> <span data-ttu-id="8aea2-125">La preparazione dei servizi di dominio Active Directory per Lync Server 2013 è costituita dai tre passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="8aea2-125">Preparing Active Directory Domain Services for Lync Server 2013 consists of the following three steps:</span></span>

  - <span data-ttu-id="8aea2-126">**Preparare lo schema**.</span><span class="sxs-lookup"><span data-stu-id="8aea2-126">**Prepare Schema**.</span></span> <span data-ttu-id="8aea2-127">Questa attività estende lo schema in servizi di dominio Active Directory per includere classi e attributi specifici di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8aea2-127">This task extends the schema in Active Directory Domain Services to include classes and attributes specific to Lync Server 2013.</span></span> <span data-ttu-id="8aea2-128">Per informazioni dettagliate sulla preparazione dello schema, vedere [eseguire la preparazione dello schema di Active Directory in Lync Server 2013](lync-server-2013-running-schema-preparation.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8aea2-128">For details about preparing the schema, see [Running Active Directory schema preparation in Lync Server 2013](lync-server-2013-running-schema-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="8aea2-129">Per altre informazioni, vedere [migrazione da Office Communications Server 2007 R2 a Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="8aea2-129">For more information, see [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span></span>

  - <span data-ttu-id="8aea2-130">**Preparare Forest**.</span><span class="sxs-lookup"><span data-stu-id="8aea2-130">**Prepare Forest**.</span></span> <span data-ttu-id="8aea2-131">Questa attività crea impostazioni globali e oggetti nel dominio radice della foresta, insieme al servizio universale e ai gruppi amministrativi che regolano l'accesso a queste impostazioni e agli oggetti.</span><span class="sxs-lookup"><span data-stu-id="8aea2-131">This task creates global settings and objects in the forest root domain, along with the universal service and administrative groups that govern access to these settings and objects.</span></span> <span data-ttu-id="8aea2-132">Per informazioni dettagliate sulla preparazione della foresta, vedere [eseguire la preparazione della foresta per Lync Server 2013](lync-server-2013-running-forest-preparation.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8aea2-132">For details about preparing the forest, see [Running forest preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="8aea2-133">**Preparare il dominio**.</span><span class="sxs-lookup"><span data-stu-id="8aea2-133">**Prepare Domain**.</span></span> <span data-ttu-id="8aea2-134">Questa attività aggiunge le necessarie voci di controllo di accesso (ACE) ai gruppi universali che assegnano le autorizzazioni per ospitare e gestire gli utenti all'interno del dominio.</span><span class="sxs-lookup"><span data-stu-id="8aea2-134">This task adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="8aea2-135">Questa attività deve essere completata in tutti i domini in cui si vogliono distribuire server che utilizzano Lync Server 2013 e tutti i domini in cui risiedono gli utenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8aea2-135">This task must be completed in all domains where you want to deploy servers running Lync Server 2013 and any domains where your Lync Server users reside.</span></span> <span data-ttu-id="8aea2-136">Per informazioni dettagliate sulla preparazione del dominio, vedere [eseguire la preparazione del dominio per Lync Server 2013](lync-server-2013-running-domain-preparation.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8aea2-136">For details about preparing the domain, see [Running domain preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="8aea2-137">Per una panoramica del processo completo per la preparazione di Active Directory e i diritti e le autorizzazioni necessarie per eseguire ogni passaggio, vedere [requisiti dell'infrastruttura Active Directory per Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8aea2-137">For an overview of the complete process for preparing Active Directory and the rights and permissions required to perform each step, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="universal-groups"></a><span data-ttu-id="8aea2-138">Gruppi universali</span><span class="sxs-lookup"><span data-stu-id="8aea2-138">Universal Groups</span></span>

<span data-ttu-id="8aea2-139">Durante la preparazione della foresta, Lync Server 2013 crea diversi gruppi universali all'interno di servizi di dominio Active Directory con l'autorizzazione per accedere e gestire le impostazioni e i servizi globali.</span><span class="sxs-lookup"><span data-stu-id="8aea2-139">During preparation of the forest, Lync Server 2013 creates various universal groups within Active Directory Domain Services that have permission to access and manage global settings and services.</span></span> <span data-ttu-id="8aea2-140">Questi gruppi universali includono:</span><span class="sxs-lookup"><span data-stu-id="8aea2-140">These universal groups include:</span></span>

  - <span data-ttu-id="8aea2-141">**Gruppi amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="8aea2-141">**Administrative groups**.</span></span> <span data-ttu-id="8aea2-142">Questi gruppi definiscono i ruoli di amministratore fondamentali per una rete Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8aea2-142">These groups define the fundamental administrator roles for a Lync Server network.</span></span> <span data-ttu-id="8aea2-143">Durante la preparazione della foresta, questi gruppi di amministratori vengono aggiunti ai gruppi di infrastruttura di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8aea2-143">During forest preparation, these administrator groups are added to Lync Server infrastructure groups.</span></span>

  - <span data-ttu-id="8aea2-144">**Gruppi di servizi**.</span><span class="sxs-lookup"><span data-stu-id="8aea2-144">**Service groups**.</span></span> <span data-ttu-id="8aea2-145">Questi gruppi sono account di servizio necessari per accedere a vari servizi forniti da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8aea2-145">These groups are service accounts that are required to access various services provided by Lync Server.</span></span>

  - <span data-ttu-id="8aea2-146">**Gruppi di infrastrutture**.</span><span class="sxs-lookup"><span data-stu-id="8aea2-146">**Infrastructure groups**.</span></span> <span data-ttu-id="8aea2-147">Questi gruppi consentono di accedere ad aree specifiche dell'infrastruttura di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8aea2-147">These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="8aea2-148">Funzionano come componenti di gruppi amministrativi e non devono essere modificati o aggiunti direttamente agli utenti.</span><span class="sxs-lookup"><span data-stu-id="8aea2-148">They function as components of administrative groups, and you should not modify them or add users to them directly.</span></span> <span data-ttu-id="8aea2-149">Durante la preparazione della foresta, i gruppi di servizi e di amministrazione specifici vengono aggiunti ai gruppi di infrastruttura appropriati.</span><span class="sxs-lookup"><span data-stu-id="8aea2-149">During forest preparation, specific service and administration groups are added to the appropriate infrastructure groups.</span></span>

<span data-ttu-id="8aea2-150">Per informazioni dettagliate sui gruppi universali specifici creati durante la preparazione di Active Directory per Lync Server, nonché i gruppi di servizi e di amministrazione aggiunti ai gruppi di infrastruttura, vedere [modifiche apportate dalla preparazione della foresta in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8aea2-150">For details about the specific universal groups created when preparing AD for Lync Server, as well as the service and administration groups that get added to the infrastructure groups, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8aea2-151">Lync Server 2013 supporta i gruppi universali di Windows Server 2012 per i server che utilizzano Lync Server 2013 e i sistemi operativi Windows Server 2003 per i controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="8aea2-151">Lync Server 2013 supports the universal groups in the Windows Server 2012 for servers running Lync Server 2013, as well as Windows Server 2003 operating systems for domain controllers.</span></span> <span data-ttu-id="8aea2-152">I membri dei gruppi universali possono includere altri gruppi e account da qualsiasi dominio nell'albero di dominio o nella foresta e possono essere assegnate autorizzazioni in qualsiasi dominio nell'albero o nella foresta del dominio.</span><span class="sxs-lookup"><span data-stu-id="8aea2-152">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="8aea2-153">Il supporto del gruppo universale, combinato con la delega dell'amministratore, semplifica la gestione di una distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8aea2-153">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="8aea2-154">Ad esempio, non è necessario aggiungere un dominio a un altro per consentire a un amministratore di gestire entrambe le proprie esigenze.</span><span class="sxs-lookup"><span data-stu-id="8aea2-154">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>



</div>

</div>

<div>

## <a name="role-based-access-control"></a><span data-ttu-id="8aea2-155">Controllo dell'accesso basato sui ruoli</span><span class="sxs-lookup"><span data-stu-id="8aea2-155">Role-Based Access Control</span></span>

<span data-ttu-id="8aea2-156">Oltre a creare gruppi di servizi e di amministrazione universali e ad aggiungere gruppi di servizi e di amministrazione ai gruppi universali appropriati, la preparazione della foresta crea anche gruppi di controllo di accesso basati sui ruoli.</span><span class="sxs-lookup"><span data-stu-id="8aea2-156">In addition to creating universal service and administration groups and adding service and administration groups to the appropriate universal groups, forest preparation also creates Role-Based Access Control (RBAC) groups.</span></span> <span data-ttu-id="8aea2-157">Per informazioni dettagliate sui gruppi RBAC specifici creati dalla preparazione della foresta, vedere le [modifiche apportate dalla preparazione della foresta in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8aea2-157">For details about the specific RBAC groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="8aea2-158">Per altre informazioni sui gruppi RBAC, vedere [controllo di accesso basato sui ruoli (RBAC) per Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="8aea2-158">For more information about RBAC groups, see [Role-based access control (RBAC) for Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span></span>

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a><span data-ttu-id="8aea2-159">Voci di controllo di accesso (ACE) ed ereditarietà</span><span class="sxs-lookup"><span data-stu-id="8aea2-159">Access Control Entries (ACEs) and Inheritance</span></span>

<span data-ttu-id="8aea2-160">La preparazione della foresta crea sia gli assi privati che quelli pubblici e, aggiungendo le voci ACE per i gruppi universali creati.</span><span class="sxs-lookup"><span data-stu-id="8aea2-160">Forest preparation creates both private and public ACEs and, adding ACEs for the universal groups it creates.</span></span> <span data-ttu-id="8aea2-161">Crea Ace private specifiche nel contenitore di impostazioni globali usato da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8aea2-161">It creates specific private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="8aea2-162">Questo contenitore viene usato solo da Lync Server e si trova nel contenitore di configurazione o nel contenitore di sistema nel dominio radice, a seconda di dove si archiviano le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="8aea2-162">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span>

<span data-ttu-id="8aea2-163">Il passaggio preparazione del dominio aggiunge le voci di controllo di accesso (ACE) necessarie ai gruppi universali che assegnano le autorizzazioni per ospitare e gestire gli utenti all'interno del dominio.</span><span class="sxs-lookup"><span data-stu-id="8aea2-163">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="8aea2-164">La preparazione del dominio crea ACE nella radice del dominio e tre contenitori predefiniti: User, computer e Domain controller.</span><span class="sxs-lookup"><span data-stu-id="8aea2-164">Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="8aea2-165">Per informazioni dettagliate sulle voci ACE pubbliche create e aggiunte dalla preparazione della foresta e dalla preparazione del dominio, vedere [modifiche apportate dalla preparazione della foresta in Lync server 2013](lync-server-2013-changes-made-by-forest-preparation.md) e [modifiche apportate dalla preparazione del dominio in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8aea2-165">For details about the public ACEs created and added by forest preparation and domain preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) and [Changes made by domain preparation in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="8aea2-166">Le organizzazioni spesso bloccano i servizi di dominio Active Directory (AD DS) per ridurre i rischi per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="8aea2-166">Organizations often lock down Active Directory Domain Services (AD DS) to help mitigate security risks.</span></span> <span data-ttu-id="8aea2-167">Tuttavia, un ambiente Active Directory bloccato può limitare le autorizzazioni necessarie per Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8aea2-167">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="8aea2-168">Questa operazione può includere la rimozione di Ace da contenitori e unità organizzative e la disabilitazione dell'ereditarietà delle autorizzazioni per gli oggetti utente, contatto, InetOrgPerson o computer.</span><span class="sxs-lookup"><span data-stu-id="8aea2-168">This can include removal of ACEs from containers and OUs and disabling of permissions inheritance on User, Contact, InetOrgPerson, or Computer objects.</span></span> <span data-ttu-id="8aea2-169">In un ambiente Active Directory bloccato è necessario impostare manualmente le autorizzazioni sui contenitori e le UO che le richiedono.</span><span class="sxs-lookup"><span data-stu-id="8aea2-169">In a locked down Active Directory environment, permissions must be set manually on containers and OUs that require them.</span></span> <span data-ttu-id="8aea2-170">Per informazioni dettagliate, vedere [preparazione di servizi di dominio Active Directory bloccati in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="8aea2-170">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="server-information"></a><span data-ttu-id="8aea2-171">Informazioni sul server</span><span class="sxs-lookup"><span data-stu-id="8aea2-171">Server Information</span></span>

<span data-ttu-id="8aea2-172">Durante l'attivazione, Lync Server 2013 pubblica le informazioni sul server nei tre percorsi seguenti in servizi di dominio Active Directory:</span><span class="sxs-lookup"><span data-stu-id="8aea2-172">During activation, Lync Server 2013 publishes server information to the three following locations in Active Directory Domain Services:</span></span>

  - <span data-ttu-id="8aea2-173">Un punto di connessione del servizio (SCP) in ogni oggetto computer di Active Directory corrispondente a un computer fisico in cui è installato Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8aea2-173">A service connection point (SCP) on each Active Directory computer object corresponding to a physical computer on which Lync Server 2013 is installed.</span></span>

  - <span data-ttu-id="8aea2-174">Oggetti server creati nel contenitore della classe **msRTCSIP-Pools** .</span><span class="sxs-lookup"><span data-stu-id="8aea2-174">Server objects created in the container of the **msRTCSIP-Pools** class.</span></span>

  - <span data-ttu-id="8aea2-175">Server attendibili specificati in Generatore di topologia.</span><span class="sxs-lookup"><span data-stu-id="8aea2-175">Trusted servers specified in Topology Builder.</span></span>

</div>

<div>

## <a name="service-connection-points"></a><span data-ttu-id="8aea2-176">Punti di connessione del servizio</span><span class="sxs-lookup"><span data-stu-id="8aea2-176">Service Connection Points</span></span>

<span data-ttu-id="8aea2-177">Ogni oggetto Lync Server 2013 in servizi di dominio Active Directory include un SCP denominato RTC Services, che a sua volta contiene un numero di attributi che identificano ogni computer e specificano i servizi forniti.</span><span class="sxs-lookup"><span data-stu-id="8aea2-177">Each Lync Server 2013 object in Active Directory Domain Services has an SCP called RTC Services, which in turn contains a number of attributes that identify each computer and specify the services that it provides.</span></span> <span data-ttu-id="8aea2-178">Tra gli attributi SCP più importanti ci sono *serviceDNSName*, *serviceDNSNameType*, *serviceClassName*e *serviceBindingInformation*.</span><span class="sxs-lookup"><span data-stu-id="8aea2-178">Among the more important SCP attributes are *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*, and *serviceBindingInformation*.</span></span> <span data-ttu-id="8aea2-179">Le applicazioni di Asset Management di terze parti possono recuperare le informazioni sul server in una distribuzione eseguendo una query su questi e altri attributi SCP.</span><span class="sxs-lookup"><span data-stu-id="8aea2-179">Third-party asset management applications can retrieve server information across a deployment by querying against these and other SCP attributes.</span></span>

</div>

<div>

## <a name="active-directory-server-objects"></a><span data-ttu-id="8aea2-180">Oggetti server di Active Directory</span><span class="sxs-lookup"><span data-stu-id="8aea2-180">Active Directory Server Objects</span></span>

<span data-ttu-id="8aea2-181">Ogni ruolo del server di Lync Server 2013 include un oggetto Active Directory corrispondente i cui attributi definiscono i servizi forniti da tale ruolo.</span><span class="sxs-lookup"><span data-stu-id="8aea2-181">Each Lync Server 2013 server role has a corresponding Active Directory object whose attributes define the services provided by that role.</span></span> <span data-ttu-id="8aea2-182">Inoltre, quando viene attivato un server Standard Edition o quando viene creato un pool Enterprise Edition, Lync Server 2013 crea un nuovo oggetto **msRTCSIP-Pool** nel contenitore **msRTCSIP-** pools.</span><span class="sxs-lookup"><span data-stu-id="8aea2-182">Also, when a Standard Edition server is activated, or when an Enterprise Edition pool is created, Lync Server 2013 creates a new **msRTCSIP-Pool** object in the **msRTCSIP-Pools** container.</span></span> <span data-ttu-id="8aea2-183">La classe **msRTCSIP-Pool** specifica il nome di dominio completo (FQDN) del pool, insieme all'associazione tra i componenti front-end e back-end del pool.</span><span class="sxs-lookup"><span data-stu-id="8aea2-183">The **msRTCSIP-Pool** class specifies the fully qualified domain name (FQDN) of the pool, along with the association between the front-end and back-end components of the pool.</span></span> <span data-ttu-id="8aea2-184">Un server Standard Edition viene considerato come un pool logico di cui le estremità anteriore e posteriore sono collocate in un singolo computer.</span><span class="sxs-lookup"><span data-stu-id="8aea2-184">(A Standard Edition server is regarded as a logical pool whose front and back ends are collocated on a single computer.)</span></span>

</div>

<div>

## <a name="trusted-servers"></a><span data-ttu-id="8aea2-185">Server attendibili</span><span class="sxs-lookup"><span data-stu-id="8aea2-185">Trusted Servers</span></span>

<span data-ttu-id="8aea2-186">In Lync Server 2013 i server attendibili sono quelli specificati quando si esegue Generatore di topologie e si pubblica la topologia.</span><span class="sxs-lookup"><span data-stu-id="8aea2-186">In Lync Server 2013, trusted servers are the ones specified when you run Topology Builder and publish your topology.</span></span> <span data-ttu-id="8aea2-187">La topologia pubblicata, incluse tutte le informazioni sul server, è archiviata in Central Management store.</span><span class="sxs-lookup"><span data-stu-id="8aea2-187">The published topology, including all the server information, is stored in the Central Management store.</span></span> <span data-ttu-id="8aea2-188">Solo i server definiti nell'Central Management store sono attendibili.</span><span class="sxs-lookup"><span data-stu-id="8aea2-188">Only servers defined in the Central Management store are trusted.</span></span> <span data-ttu-id="8aea2-189">In Lync Server 2013 un server attendibile è quello che soddisfa i criteri seguenti:</span><span class="sxs-lookup"><span data-stu-id="8aea2-189">In Lync Server 2013, a trusted server is one that meets the following criteria:</span></span>

  - <span data-ttu-id="8aea2-190">Il nome di dominio completo del server si trova nella topologia archiviata in Central Management store.</span><span class="sxs-lookup"><span data-stu-id="8aea2-190">The FQDN of the server occurs in the topology stored in Central Management store.</span></span>

  - <span data-ttu-id="8aea2-191">Il server presenta un certificato valido da una CA attendibile.</span><span class="sxs-lookup"><span data-stu-id="8aea2-191">The server presents a valid certificate from a trusted CA.</span></span> <span data-ttu-id="8aea2-192">Per informazioni dettagliate, vedere [requisiti per l'infrastruttura dei certificati per Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8aea2-192">For details, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span></span>

<span data-ttu-id="8aea2-193">Se uno di questi criteri non è presente, il server non è attendibile e la connessione viene rifiutata.</span><span class="sxs-lookup"><span data-stu-id="8aea2-193">If either of these criteria is missing, the server is not trusted and connection with it is refused.</span></span> <span data-ttu-id="8aea2-194">Questo doppio requisito impedisce un attacco possibile, se improbabile, in cui un server Rogue tenti di assumere il nome di dominio completo del server valido.</span><span class="sxs-lookup"><span data-stu-id="8aea2-194">This double requirement prevents a possible, if unlikely, attack in which a rogue server attempts to take over a valid server’s FQDN.</span></span>

<span data-ttu-id="8aea2-195">Inoltre, per consentire alle distribuzioni di Microsoft Office Communications Server 2007 R2 e Microsoft Office Communications Server 2007 di comunicare con i server di Lync Server 2013, Lync Server 2013 crea contenitori durante la preparazione della foresta per la partecipazione a elenchi di server attendibili per le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="8aea2-195">Additionally, to enable Microsoft Office Communications Server 2007 R2 and Microsoft Office Communications Server 2007 deployments to communicate with Lync Server 2013 servers, Lync Server 2013 creates containers during forest preparation for holding lists of trusted servers for previous releases.</span></span> <span data-ttu-id="8aea2-196">La tabella seguente descrive i contenitori creati per consentire la compatibilità con le distribuzioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="8aea2-196">The following table describes the containers created to enable compatibility with previous deployments.</span></span>

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a><span data-ttu-id="8aea2-197">Elenchi di server attendibili e relativi contenitori di Active Directory per la compatibilità con le versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="8aea2-197">Trusted Server Lists and Their Active Directory Containers for Compatibility with Previous Releases</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="8aea2-198">Elenco di server attendibili</span><span class="sxs-lookup"><span data-stu-id="8aea2-198">Trusted server list</span></span></th>
<th><span data-ttu-id="8aea2-199">Contenitore di Active Directory</span><span class="sxs-lookup"><span data-stu-id="8aea2-199">Active Directory container</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="8aea2-200">Server Standard Edition e server front-end del pool Enterprise</span><span class="sxs-lookup"><span data-stu-id="8aea2-200">Standard Edition servers and Enterprise pool Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="8aea2-201">RTC Service/impostazioni globali</span><span class="sxs-lookup"><span data-stu-id="8aea2-201">RTC Service/Global Settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8aea2-202">Server di conferenza</span><span class="sxs-lookup"><span data-stu-id="8aea2-202">Conferencing Servers</span></span></p></td>
<td><p><span data-ttu-id="8aea2-203">RTC Service/trusted MCU</span><span class="sxs-lookup"><span data-stu-id="8aea2-203">RTC Service/Trusted MCUs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8aea2-204">Server Web Components</span><span class="sxs-lookup"><span data-stu-id="8aea2-204">Web Components Servers</span></span></p></td>
<td><p><span data-ttu-id="8aea2-205">RTC Service/TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="8aea2-205">RTC Service/TrustedWebComponentsServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="8aea2-206">Mediation Server e server Communicator Web Access, server applicazioni, registrar con QoE, servizio di conferenza A/V (anche server SIP di terze parti)</span><span class="sxs-lookup"><span data-stu-id="8aea2-206">Mediation Servers and Communicator Web Access Servers, Application Server, Registrar with QoE, A/V Conferencing Service (also 3rd-party SIP servers)</span></span></p></td>
<td><p><span data-ttu-id="8aea2-207">Servizio RTC/servizi attendibili</span><span class="sxs-lookup"><span data-stu-id="8aea2-207">RTC Service/Trusted Services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="8aea2-208">Server proxy</span><span class="sxs-lookup"><span data-stu-id="8aea2-208">Proxy Servers</span></span></p></td>
<td><p><span data-ttu-id="8aea2-209">Lync Server 2013 non supporta la compatibilità con le versioni precedenti per i server proxy</span><span class="sxs-lookup"><span data-stu-id="8aea2-209">Lync Server 2013 does not support backward compatibility for proxy servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="8aea2-210">Per supportare i server attendibili delle versioni precedenti, è necessario eseguire lo strumento Analizzatore procedure consigliate.</span><span class="sxs-lookup"><span data-stu-id="8aea2-210">To support trusted servers of previous releases, you must run the best practices analyzer tool.</span></span> <span data-ttu-id="8aea2-211">Per informazioni dettagliate sull'uso dell'Analizzatore procedure consigliate, vedere [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633).</span><span class="sxs-lookup"><span data-stu-id="8aea2-211">For details about running the best practices analyzer, see [http://go.microsoft.com/fwlink/p/?LinkId=330633](http://go.microsoft.com/fwlink/p/?linkid=330633).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

