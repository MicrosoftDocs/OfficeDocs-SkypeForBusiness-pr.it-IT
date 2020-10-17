---
title: 'Lync Server 2013: Servizi di dominio Active Directory per Lync Server'
description: 'Lync Server 2013: Servizi di dominio Active Directory per Lync Server.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Active Directory Domain Services for Lync Server 2013
ms:assetid: 5483afd5-d8af-4825-ae95-a82dbe941dbf
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn481129(v=OCS.15)
ms:contentKeyID: 59893871
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 50c7460daa312daf5fb857f51fe1acb78972447c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571072"
---
# <a name="active-directory-domain-services-for-lync-server-2013"></a><span data-ttu-id="06ffa-103">Servizi di dominio Active Directory per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="06ffa-103">Active Directory Domain Services for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="06ffa-104">_**Ultimo argomento modificato:** 2013-11-13_</span><span class="sxs-lookup"><span data-stu-id="06ffa-104">_**Topic Last Modified:** 2013-11-13_</span></span>

<span data-ttu-id="06ffa-105">Servizi di dominio Active Directory funge da servizio directory per le reti Windows Server 2003, Windows Server 2008, Windows Server 2012 e Windows Server 2012 R2.</span><span class="sxs-lookup"><span data-stu-id="06ffa-105">Active Directory Domain Services functions as the directory service for Windows Server 2003, Windows Server 2008, Windows Server 2012, and Windows Server 2012 R2 networks.</span></span> <span data-ttu-id="06ffa-106">Servizi di dominio Active Directory funge anche da fondamento su cui è stata creata l'infrastruttura di sicurezza di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="06ffa-106">Active Directory Domain Services also serves as the foundation on which the Microsoft Lync Server 2013 security infrastructure is built.</span></span> <span data-ttu-id="06ffa-107">Lo scopo di questa sezione è descrivere come Lync Server 2013 utilizza servizi di dominio Active Directory per creare un ambiente affidabile per messaggistica istantanea, Web Conferencing, multimediale e vocale.</span><span class="sxs-lookup"><span data-stu-id="06ffa-107">The purpose of this section is to describe how Lync Server 2013 uses Active Directory Domain Services to create a trustworthy environment for IM, Web conferencing, media, and voice.</span></span> <span data-ttu-id="06ffa-108">Per informazioni dettagliate sulle estensioni di Lync Server per i servizi di dominio Active Directory e sulla preparazione dell'ambiente per i servizi di dominio Active Directory, vedere [preparazione di servizi di dominio Active Directory per Lync server 2013](lync-server-2013-preparing-active-directory-domain-services.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="06ffa-108">For details about Lync Server extensions to Active Directory Domain Services and about preparing your environment for Active Directory Domain Services, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span> <span data-ttu-id="06ffa-109">Per informazioni dettagliate sul ruolo di Servizi di dominio Active Directory nelle reti Windows Server, vedere la documentazione per la versione del sistema operativo in uso.</span><span class="sxs-lookup"><span data-stu-id="06ffa-109">For details about the role of Active Directory Domain Services in Windows Server networks, see the documentation for the version of the operating system you are using.</span></span>

<span data-ttu-id="06ffa-110">Lync Server 2013 utilizza servizi di dominio Active Directory per archiviare:</span><span class="sxs-lookup"><span data-stu-id="06ffa-110">Lync Server 2013 uses Active Directory Domain Services to store:</span></span>

  - <span data-ttu-id="06ffa-111">Impostazioni globali che richiedono tutti i server che eseguono Lync Server 2013 in una foresta.</span><span class="sxs-lookup"><span data-stu-id="06ffa-111">Global settings that all servers running Lync Server 2013 in a forest require.</span></span>

  - <span data-ttu-id="06ffa-112">Informazioni sui servizi che identificano i ruoli di tutti i server che eseguono Lync Server 2013 in una foresta.</span><span class="sxs-lookup"><span data-stu-id="06ffa-112">Service information that identifies the roles of all servers running Lync Server 2013 in a forest.</span></span>

  - <span data-ttu-id="06ffa-113">Alcune impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="06ffa-113">Some user settings.</span></span>

<div>

## <a name="active-directory-infrastructure"></a><span data-ttu-id="06ffa-114">Infrastruttura di Active Directory</span><span class="sxs-lookup"><span data-stu-id="06ffa-114">Active Directory Infrastructure</span></span>

<span data-ttu-id="06ffa-115">I requisiti di infrastruttura per Active Directory includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="06ffa-115">Infrastructure requirements for Active Directory include the following:</span></span>

  - <span data-ttu-id="06ffa-116">Requisiti del sistema operativo per i controller di dominio</span><span class="sxs-lookup"><span data-stu-id="06ffa-116">Operating system requirements for domain controllers</span></span>

  - <span data-ttu-id="06ffa-117">Requisiti per il livello funzionale di foresta e dominio</span><span class="sxs-lookup"><span data-stu-id="06ffa-117">Domain and forest functional level requirements</span></span>

  - <span data-ttu-id="06ffa-118">Requisiti di dominio per il catalogo globale</span><span class="sxs-lookup"><span data-stu-id="06ffa-118">Global catalog domain requirements</span></span>

<span data-ttu-id="06ffa-119">Per informazioni dettagliate, vedere [Active Directory Infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="06ffa-119">For details, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="active-directory-domain-services-preparation"></a><span data-ttu-id="06ffa-120">Preparativi per Servizi di dominio Active Directory</span><span class="sxs-lookup"><span data-stu-id="06ffa-120">Active Directory Domain Services Preparation</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="06ffa-121">È consigliabile distribuire le impostazioni globali nel contenitore della configurazione anziché nel contenitore di sistema.</span><span class="sxs-lookup"><span data-stu-id="06ffa-121">We recommend that you deploy global settings to the Configuration container instead of the System container.</span></span> <span data-ttu-id="06ffa-122">Ciò non consente miglioramenti della sicurezza, ma può consentire miglioramenti della scalabilità per alcune topologie di Servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="06ffa-122">This does not enhance security, but can result in scalability improvements for some Active Directory Domain Services topologies.</span></span> <span data-ttu-id="06ffa-123">Se si esegue la migrazione da Microsoft Office Communications Server 2007 ed è stato utilizzato il contenitore di sistema ma si intende utilizzare il contenitore di configurazione, è necessario spostare le impostazioni nel contenitore di sistema prima di eseguire qualsiasi preparazione all'aggiornamento.</span><span class="sxs-lookup"><span data-stu-id="06ffa-123">If you are migrating from Microsoft Office Communications Server 2007 and have used the System container but plan to use the Configuration container, you MUST move the settings in the System container BEFORE you do any upgrade preparations.</span></span> <span data-ttu-id="06ffa-124">Per eseguire la migrazione delle impostazioni del contenitore di sistema nel contenitore di configurazione, vedere Office Communications Server 2007 Global Settings Migration Tool at <A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A> .</span><span class="sxs-lookup"><span data-stu-id="06ffa-124">To migrate your System container settings to the Configuration container, see Office Communications Server 2007 Global Settings Migration Tool at <A href="https://go.microsoft.com/fwlink/p/?linkid=145236">https://go.microsoft.com/fwlink/p/?LinkId=145236</A>.</span></span>



</div>

<span data-ttu-id="06ffa-125">Quando si distribuisce Lync Server 2013, il primo passaggio consiste nel preparare i servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="06ffa-125">When deploying Lync Server 2013, the first step is to prepare Active Directory Domain Services.</span></span> <span data-ttu-id="06ffa-126">La preparazione di servizi di dominio Active Directory per Lync Server 2013 è costituita dai tre passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="06ffa-126">Preparing Active Directory Domain Services for Lync Server 2013 consists of the following three steps:</span></span>

  - <span data-ttu-id="06ffa-127">**Prepara schema**.</span><span class="sxs-lookup"><span data-stu-id="06ffa-127">**Prepare Schema**.</span></span> <span data-ttu-id="06ffa-128">Questa attività consente di estendere lo schema in servizi di dominio Active Directory per includere classi e attributi specifici di Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="06ffa-128">This task extends the schema in Active Directory Domain Services to include classes and attributes specific to Lync Server 2013.</span></span> <span data-ttu-id="06ffa-129">Per informazioni dettagliate sulla preparazione dello schema, vedere [running Active Directory schema preparation in Lync Server 2013](lync-server-2013-running-schema-preparation.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="06ffa-129">For details about preparing the schema, see [Running Active Directory schema preparation in Lync Server 2013](lync-server-2013-running-schema-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="06ffa-130">Per ulteriori informazioni, vedere [migrazione da Office Communications Server 2007 R2 a Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="06ffa-130">For more information, see [Migration from Office Communications Server 2007 R2 to Lync Server 2013](migration-from-office-communications-server-2007-r2-to-lync-server-2013.md).</span></span>

  - <span data-ttu-id="06ffa-131">**Preparare la foresta**.</span><span class="sxs-lookup"><span data-stu-id="06ffa-131">**Prepare Forest**.</span></span> <span data-ttu-id="06ffa-132">Questa attività consente di creare le impostazioni globali e gli oggetti nel dominio radice della foresta, insieme ai gruppi amministrativi e di servizi universali che regolano l'accesso a queste impostazioni e oggetti.</span><span class="sxs-lookup"><span data-stu-id="06ffa-132">This task creates global settings and objects in the forest root domain, along with the universal service and administrative groups that govern access to these settings and objects.</span></span> <span data-ttu-id="06ffa-133">Per informazioni dettagliate sulla preparazione della foresta, vedere [Running Forest Preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="06ffa-133">For details about preparing the forest, see [Running forest preparation for Lync Server 2013](lync-server-2013-running-forest-preparation.md) in the Deployment documentation.</span></span>

  - <span data-ttu-id="06ffa-134">**Prepara dominio**.</span><span class="sxs-lookup"><span data-stu-id="06ffa-134">**Prepare Domain**.</span></span> <span data-ttu-id="06ffa-135">Questa attività consente di aggiungere le voci di controllo di accesso (ACE, Access Control Entry) necessarie ai gruppi universali che concedono le autorizzazioni per ospitare e gestire gli utenti nel dominio.</span><span class="sxs-lookup"><span data-stu-id="06ffa-135">This task adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain.</span></span> <span data-ttu-id="06ffa-136">Questa attività deve essere completata in tutti i domini in cui si desidera distribuire i server che eseguono Lync Server 2013 e tutti i domini in cui risiedono gli utenti di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06ffa-136">This task must be completed in all domains where you want to deploy servers running Lync Server 2013 and any domains where your Lync Server users reside.</span></span> <span data-ttu-id="06ffa-137">Per informazioni dettagliate sulla preparazione del dominio, vedere [Running domain preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="06ffa-137">For details about preparing the domain, see [Running domain preparation for Lync Server 2013](lync-server-2013-running-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="06ffa-138">Per una panoramica del processo completo per la preparazione di Active Directory e dei diritti e delle autorizzazioni necessari per eseguire ogni passaggio, vedere [Active Directory Infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="06ffa-138">For an overview of the complete process for preparing Active Directory and the rights and permissions required to perform each step, see [Active Directory infrastructure requirements for Lync Server 2013](lync-server-2013-active-directory-infrastructure-requirements.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="universal-groups"></a><span data-ttu-id="06ffa-139">Gruppi universali</span><span class="sxs-lookup"><span data-stu-id="06ffa-139">Universal Groups</span></span>

<span data-ttu-id="06ffa-140">Durante la preparazione della foresta, Lync Server 2013 crea vari gruppi universali all'interno dei servizi di dominio Active Directory che dispongono dell'autorizzazione per l'accesso e la gestione delle impostazioni e dei servizi globali.</span><span class="sxs-lookup"><span data-stu-id="06ffa-140">During preparation of the forest, Lync Server 2013 creates various universal groups within Active Directory Domain Services that have permission to access and manage global settings and services.</span></span> <span data-ttu-id="06ffa-141">Questi gruppi universali includono:</span><span class="sxs-lookup"><span data-stu-id="06ffa-141">These universal groups include:</span></span>

  - <span data-ttu-id="06ffa-142">**Gruppi amministrativi**.</span><span class="sxs-lookup"><span data-stu-id="06ffa-142">**Administrative groups**.</span></span> <span data-ttu-id="06ffa-143">Questi gruppi definiscono i ruoli di amministratore fondamentali per una rete di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06ffa-143">These groups define the fundamental administrator roles for a Lync Server network.</span></span> <span data-ttu-id="06ffa-144">Durante la preparazione della foresta, questi gruppi di amministratori vengono aggiunti ai gruppi di infrastruttura di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06ffa-144">During forest preparation, these administrator groups are added to Lync Server infrastructure groups.</span></span>

  - <span data-ttu-id="06ffa-145">**Gruppi di servizi**.</span><span class="sxs-lookup"><span data-stu-id="06ffa-145">**Service groups**.</span></span> <span data-ttu-id="06ffa-146">Questi gruppi sono account di servizio necessari per accedere ai diversi servizi forniti da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06ffa-146">These groups are service accounts that are required to access various services provided by Lync Server.</span></span>

  - <span data-ttu-id="06ffa-147">**Gruppi di infrastrutture**.</span><span class="sxs-lookup"><span data-stu-id="06ffa-147">**Infrastructure groups**.</span></span> <span data-ttu-id="06ffa-148">Questi gruppi forniscono l'autorizzazione per accedere a aree specifiche dell'infrastruttura di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06ffa-148">These groups provide permission to access specific areas of the Lync Server infrastructure.</span></span> <span data-ttu-id="06ffa-149">Fungono da componenti dei gruppi amministrativi ed è consigliabile non modificarli o aggiungervi direttamente utenti.</span><span class="sxs-lookup"><span data-stu-id="06ffa-149">They function as components of administrative groups, and you should not modify them or add users to them directly.</span></span> <span data-ttu-id="06ffa-150">Durante la preparazione della foresta, i gruppi di servizi e di amministrazione specifici vengono aggiunti ai gruppi di infrastruttura corretti.</span><span class="sxs-lookup"><span data-stu-id="06ffa-150">During forest preparation, specific service and administration groups are added to the appropriate infrastructure groups.</span></span>

<span data-ttu-id="06ffa-151">Per informazioni dettagliate sugli specifici gruppi universali creati durante la preparazione di Active Directory per Lync Server, nonché i gruppi di servizi e di amministrazione che vengono aggiunti ai gruppi di infrastruttura, vedere [changes made by Forest preparation in Lync server 2013](lync-server-2013-changes-made-by-forest-preparation.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="06ffa-151">For details about the specific universal groups created when preparing AD for Lync Server, as well as the service and administration groups that get added to the infrastructure groups, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="06ffa-152">Lync Server 2013 supporta i gruppi universali in Windows Server 2012 per i server che eseguono Lync Server 2013, nonché i sistemi operativi Windows Server 2003 per i controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="06ffa-152">Lync Server 2013 supports the universal groups in the Windows Server 2012 for servers running Lync Server 2013, as well as Windows Server 2003 operating systems for domain controllers.</span></span> <span data-ttu-id="06ffa-153">Ai membri dei gruppi universali, che possono includere altri gruppi e account di qualsiasi dominio della foresta o dell'albero di dominio, è possibile assegnare autorizzazioni in qualsiasi dominio della foresta o dell'albero di dominio.</span><span class="sxs-lookup"><span data-stu-id="06ffa-153">Members of universal groups can include other groups and accounts from any domain in the domain tree or forest and can be assigned permissions in any domain in the domain tree or forest.</span></span> <span data-ttu-id="06ffa-154">Il supporto di gruppo universale, Unito alla delega dell'amministratore, semplifica la gestione di una distribuzione di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06ffa-154">Universal group support, combined with administrator delegation, simplifies the management of a Lync Server deployment.</span></span> <span data-ttu-id="06ffa-155">Non è più necessario, ad esempio, aggiungere un dominio a un altro per consentire a un amministratore di gestirli entrambi.</span><span class="sxs-lookup"><span data-stu-id="06ffa-155">For example, it is not necessary to add one domain to another to enable an administrator to manage both.</span></span>



</div>

</div>

<div>

## <a name="role-based-access-control"></a><span data-ttu-id="06ffa-156">Controllo di accesso basato sui ruoli</span><span class="sxs-lookup"><span data-stu-id="06ffa-156">Role-Based Access Control</span></span>

<span data-ttu-id="06ffa-157">Oltre alla creazione di gruppi di amministrazione e di servizio universali e all'aggiunta di gruppi di servizi e di amministrazione ai gruppi universali, la preparazione della foresta crea anche Role-Based gruppi di controllo di accesso (RBAC).</span><span class="sxs-lookup"><span data-stu-id="06ffa-157">In addition to creating universal service and administration groups and adding service and administration groups to the appropriate universal groups, forest preparation also creates Role-Based Access Control (RBAC) groups.</span></span> <span data-ttu-id="06ffa-158">Per informazioni dettagliate sui gruppi RBAC specifici creati dalla preparazione della foresta, vedere [changes made by Forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="06ffa-158">For details about the specific RBAC groups created by forest preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) in the Deployment documentation.</span></span> <span data-ttu-id="06ffa-159">Per ulteriori informazioni sui gruppi RBAC, vedere [controllo di accesso basato sui ruoli (RBAC) per Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span><span class="sxs-lookup"><span data-stu-id="06ffa-159">For more information about RBAC groups, see [Role-based access control (RBAC) for Lync Server 2013](lync-server-2013-role-based-access-control-rbac.md).</span></span>

</div>

<div>

## <a name="access-control-entries-aces-and-inheritance"></a><span data-ttu-id="06ffa-160">Voci di controllo di accesso ed ereditarietà</span><span class="sxs-lookup"><span data-stu-id="06ffa-160">Access Control Entries (ACEs) and Inheritance</span></span>

<span data-ttu-id="06ffa-161">Il processo di preparazione della foresta prevede la creazione sia di voci di controllo di accesso pubbliche che private e l'aggiunta delle voci di controllo di accesso per i gruppi universali creati.</span><span class="sxs-lookup"><span data-stu-id="06ffa-161">Forest preparation creates both private and public ACEs and, adding ACEs for the universal groups it creates.</span></span> <span data-ttu-id="06ffa-162">Crea voci ACE private specifiche nel contenitore delle impostazioni globali utilizzato da Lync Server.</span><span class="sxs-lookup"><span data-stu-id="06ffa-162">It creates specific private ACEs on the global settings container used by Lync Server.</span></span> <span data-ttu-id="06ffa-163">Questo contenitore viene utilizzato solo da Lync Server e si trova nel contenitore di configurazione o nel contenitore di sistema nel dominio radice, a seconda della posizione in cui vengono archiviate le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="06ffa-163">This container is used only by Lync Server and is located either in the Configuration container or the System container in the root domain, depending on where you store global settings.</span></span>

<span data-ttu-id="06ffa-p114">Questa operazione comporta l'aggiunta delle voci di controllo di accesso necessarie ai gruppi universali che concedono autorizzazioni per ospitare e gestire gli utenti nell'ambito del dominio. Con la preparazione del dominio vengono create voci di controllo di accesso nella radice del dominio e tre contenitori predefiniti per utenti, computer e controller di dominio.</span><span class="sxs-lookup"><span data-stu-id="06ffa-p114">The domain preparation step adds the necessary access control entries (ACEs) to universal groups that grant permissions to host and manage users within the domain. Domain preparation creates ACEs on the domain root and three built-in containers: User, Computers, and Domain Controllers.</span></span>

<span data-ttu-id="06ffa-166">Per informazioni dettagliate sulle voci di accesso pubbliche create e aggiunte dalla preparazione della foresta e dalla preparazione del dominio, vedere [changes made by Forest preparation in Lync server 2013](lync-server-2013-changes-made-by-forest-preparation.md) e [changes made by domain preparation in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="06ffa-166">For details about the public ACEs created and added by forest preparation and domain preparation, see [Changes made by forest preparation in Lync Server 2013](lync-server-2013-changes-made-by-forest-preparation.md) and [Changes made by domain preparation in Lync Server 2013](lync-server-2013-changes-made-by-domain-preparation.md) in the Deployment documentation.</span></span>

<span data-ttu-id="06ffa-167">Le organizzazioni scelgono spesso di bloccare Servizi di dominio Active Directory per ridurre i rischi per la sicurezza.</span><span class="sxs-lookup"><span data-stu-id="06ffa-167">Organizations often lock down Active Directory Domain Services (AD DS) to help mitigate security risks.</span></span> <span data-ttu-id="06ffa-168">Tuttavia, un ambiente Active Directory bloccato può limitare le autorizzazioni richieste da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="06ffa-168">However, a locked-down Active Directory environment can limit the permissions that Lync Server 2013 requires.</span></span> <span data-ttu-id="06ffa-169">Ciò può includere la rimozione delle voci di controllo di accesso dai contenitori e dalle unità organizzative, nonché la disabilitazione dell'ereditarietà delle autorizzazioni negli oggetti User, Contact, InetOrgPerson o Computer.</span><span class="sxs-lookup"><span data-stu-id="06ffa-169">This can include removal of ACEs from containers and OUs and disabling of permissions inheritance on User, Contact, InetOrgPerson, or Computer objects.</span></span> <span data-ttu-id="06ffa-170">In un ambiente Active Directory bloccato, le autorizzazioni devono essere impostate manualmente nei contenitori e nelle unità organizzative per cui sono necessarie.</span><span class="sxs-lookup"><span data-stu-id="06ffa-170">In a locked down Active Directory environment, permissions must be set manually on containers and OUs that require them.</span></span> <span data-ttu-id="06ffa-171">Per ulteriori informazioni, vedere [preparazione di servizi di dominio Active Directory bloccati in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="06ffa-171">For details, see [Preparing a locked-down Active Directory Domain Services in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="server-information"></a><span data-ttu-id="06ffa-172">Informazioni sui server</span><span class="sxs-lookup"><span data-stu-id="06ffa-172">Server Information</span></span>

<span data-ttu-id="06ffa-173">Durante l'attivazione, Lync Server 2013 pubblica le informazioni sui server nelle tre posizioni seguenti in servizi di dominio Active Directory:</span><span class="sxs-lookup"><span data-stu-id="06ffa-173">During activation, Lync Server 2013 publishes server information to the three following locations in Active Directory Domain Services:</span></span>

  - <span data-ttu-id="06ffa-174">Un punto di connessione del servizio (SCP, Service Connection Point) su ogni oggetto computer di Active Directory corrispondente a un computer fisico in cui è installato Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="06ffa-174">A service connection point (SCP) on each Active Directory computer object corresponding to a physical computer on which Lync Server 2013 is installed.</span></span>

  - <span data-ttu-id="06ffa-175">Oggetti server creati nel contenitore della classe **msRTCSIP-Pools**.</span><span class="sxs-lookup"><span data-stu-id="06ffa-175">Server objects created in the container of the **msRTCSIP-Pools** class.</span></span>

  - <span data-ttu-id="06ffa-176">Server attendibili specificati in Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="06ffa-176">Trusted servers specified in Topology Builder.</span></span>

</div>

<div>

## <a name="service-connection-points"></a><span data-ttu-id="06ffa-177">Punti di connessione del servizio</span><span class="sxs-lookup"><span data-stu-id="06ffa-177">Service Connection Points</span></span>

<span data-ttu-id="06ffa-178">Ogni oggetto Lync Server 2013 in servizi di dominio Active Directory ha un SCP denominato RTC Services, che a sua volta contiene una serie di attributi che identificano ogni computer e specificano i servizi forniti.</span><span class="sxs-lookup"><span data-stu-id="06ffa-178">Each Lync Server 2013 object in Active Directory Domain Services has an SCP called RTC Services, which in turn contains a number of attributes that identify each computer and specify the services that it provides.</span></span> <span data-ttu-id="06ffa-179">*serviceDNSName*, *serviceDNSNameType*, *serviceClassname* e *serviceBindingInformation* sono alcuni degli attributi SCP più importanti.</span><span class="sxs-lookup"><span data-stu-id="06ffa-179">Among the more important SCP attributes are *serviceDNSName*, *serviceDNSNameType*, *serviceClassname*, and *serviceBindingInformation*.</span></span> <span data-ttu-id="06ffa-180">Le applicazioni di terze parti per la gestione delle risorse possono recuperare le informazioni sui server in una distribuzione eseguendo una query a fronte di questi e altri attributi SCP.</span><span class="sxs-lookup"><span data-stu-id="06ffa-180">Third-party asset management applications can retrieve server information across a deployment by querying against these and other SCP attributes.</span></span>

</div>

<div>

## <a name="active-directory-server-objects"></a><span data-ttu-id="06ffa-181">Oggetti server Active Directory</span><span class="sxs-lookup"><span data-stu-id="06ffa-181">Active Directory Server Objects</span></span>

<span data-ttu-id="06ffa-182">Ogni ruolo del server Lync Server 2013 dispone di un oggetto Active Directory corrispondente i cui attributi definiscono i servizi forniti da tale ruolo.</span><span class="sxs-lookup"><span data-stu-id="06ffa-182">Each Lync Server 2013 server role has a corresponding Active Directory object whose attributes define the services provided by that role.</span></span> <span data-ttu-id="06ffa-183">Inoltre, quando un server Standard Edition viene attivato o quando viene creato un pool Enterprise Edition, Lync Server 2013 crea un nuovo oggetto **msRTCSIP-Pool** nel contenitore **msRTCSIP-** pools.</span><span class="sxs-lookup"><span data-stu-id="06ffa-183">Also, when a Standard Edition server is activated, or when an Enterprise Edition pool is created, Lync Server 2013 creates a new **msRTCSIP-Pool** object in the **msRTCSIP-Pools** container.</span></span> <span data-ttu-id="06ffa-184">La classe **msRTCSIP-Pool** specifica il nome di dominio completo (FQDN) del pool, insieme all'associazione tra i componenti front-end e back-end del pool.</span><span class="sxs-lookup"><span data-stu-id="06ffa-184">The **msRTCSIP-Pool** class specifies the fully qualified domain name (FQDN) of the pool, along with the association between the front-end and back-end components of the pool.</span></span> <span data-ttu-id="06ffa-185">Un server Standard Edition viene considerato un pool logico i cui componenti front-end e back-end sono collocati in un solo computer.</span><span class="sxs-lookup"><span data-stu-id="06ffa-185">(A Standard Edition server is regarded as a logical pool whose front and back ends are collocated on a single computer.)</span></span>

</div>

<div>

## <a name="trusted-servers"></a><span data-ttu-id="06ffa-186">Server trusted</span><span class="sxs-lookup"><span data-stu-id="06ffa-186">Trusted Servers</span></span>

<span data-ttu-id="06ffa-187">In Lync Server 2013, i server attendibili sono quelli specificati durante l'esecuzione di generatore di topologie e la pubblicazione della topologia.</span><span class="sxs-lookup"><span data-stu-id="06ffa-187">In Lync Server 2013, trusted servers are the ones specified when you run Topology Builder and publish your topology.</span></span> <span data-ttu-id="06ffa-188">La topologia pubblicata, incluse tutte le informazioni del server, viene archiviata nell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="06ffa-188">The published topology, including all the server information, is stored in the Central Management store.</span></span> <span data-ttu-id="06ffa-189">Solo i server definiti nell'archivio di gestione centrale sono trusted.</span><span class="sxs-lookup"><span data-stu-id="06ffa-189">Only servers defined in the Central Management store are trusted.</span></span> <span data-ttu-id="06ffa-190">In Lync Server 2013, un server attendibile è in grado di soddisfare i seguenti criteri:</span><span class="sxs-lookup"><span data-stu-id="06ffa-190">In Lync Server 2013, a trusted server is one that meets the following criteria:</span></span>

  - <span data-ttu-id="06ffa-191">Il nome FQDN del server compare nella topologia archiviata nell'archivio di gestione centrale.</span><span class="sxs-lookup"><span data-stu-id="06ffa-191">The FQDN of the server occurs in the topology stored in Central Management store.</span></span>

  - <span data-ttu-id="06ffa-192">Il server presenta un certificato valido da un'autorità di certificazione attendibile.</span><span class="sxs-lookup"><span data-stu-id="06ffa-192">The server presents a valid certificate from a trusted CA.</span></span> <span data-ttu-id="06ffa-193">Per informazioni dettagliate, vedere [Certificate Infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06ffa-193">For details, see [Certificate infrastructure requirements for Lync Server 2013](lync-server-2013-certificate-infrastructure-requirements.md).</span></span>

<span data-ttu-id="06ffa-p120">Se uno di questi criteri non risulta soddisfatto, il server non è trusted e la connessione viene rifiutata. Questo duplice requisito impedisce un possibile, anche se improbabile, attacco in cui un server non autorizzato tenta di prendere il controllo del nome FQDN di un server valido.</span><span class="sxs-lookup"><span data-stu-id="06ffa-p120">If either of these criteria is missing, the server is not trusted and connection with it is refused. This double requirement prevents a possible, if unlikely, attack in which a rogue server attempts to take over a valid server’s FQDN.</span></span>

<span data-ttu-id="06ffa-196">Inoltre, per consentire alle distribuzioni di Microsoft Office Communications Server 2007 R2 e Microsoft Office Communications Server 2007 di comunicare con i server di Lync Server 2013, Lync Server 2013 crea contenitori durante la preparazione della foresta per la conservazione degli elenchi di server attendibili per le versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="06ffa-196">Additionally, to enable Microsoft Office Communications Server 2007 R2 and Microsoft Office Communications Server 2007 deployments to communicate with Lync Server 2013 servers, Lync Server 2013 creates containers during forest preparation for holding lists of trusted servers for previous releases.</span></span> <span data-ttu-id="06ffa-197">Nella tabella seguente vengono descritti i contenitori creati per abilitare la compatibilità con le distribuzioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="06ffa-197">The following table describes the containers created to enable compatibility with previous deployments.</span></span>

### <a name="trusted-server-lists-and-their-active-directory-containers-for-compatibility-with-previous-releases"></a><span data-ttu-id="06ffa-198">Elenchi di server trusted e contenitori Active Directory corrispondenti per la compatibilità con le versioni precedenti</span><span class="sxs-lookup"><span data-stu-id="06ffa-198">Trusted Server Lists and Their Active Directory Containers for Compatibility with Previous Releases</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="06ffa-199">Elenco di server trusted</span><span class="sxs-lookup"><span data-stu-id="06ffa-199">Trusted server list</span></span></th>
<th><span data-ttu-id="06ffa-200">Contenitore di Active Directory</span><span class="sxs-lookup"><span data-stu-id="06ffa-200">Active Directory container</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="06ffa-201">Server Standard Edtion e Front End Server del pool Enterprise</span><span class="sxs-lookup"><span data-stu-id="06ffa-201">Standard Edition servers and Enterprise pool Front End Servers</span></span></p></td>
<td><p><span data-ttu-id="06ffa-202">RTC Service/Global Settings</span><span class="sxs-lookup"><span data-stu-id="06ffa-202">RTC Service/Global Settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06ffa-203">Conferencing Server</span><span class="sxs-lookup"><span data-stu-id="06ffa-203">Conferencing Servers</span></span></p></td>
<td><p><span data-ttu-id="06ffa-204">RTC Service/Trusted MCUs</span><span class="sxs-lookup"><span data-stu-id="06ffa-204">RTC Service/Trusted MCUs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06ffa-205">Web Components Server</span><span class="sxs-lookup"><span data-stu-id="06ffa-205">Web Components Servers</span></span></p></td>
<td><p><span data-ttu-id="06ffa-206">RTC Service/TrustedWebComponentsServers</span><span class="sxs-lookup"><span data-stu-id="06ffa-206">RTC Service/TrustedWebComponentsServers</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="06ffa-207">Mediation Server e Communicator Web Access Server, server applicazioni, funzione di registrazione con QoE, servizio A/V Conferencing (anche server SIP di terze parti)</span><span class="sxs-lookup"><span data-stu-id="06ffa-207">Mediation Servers and Communicator Web Access Servers, Application Server, Registrar with QoE, A/V Conferencing Service (also 3rd-party SIP servers)</span></span></p></td>
<td><p><span data-ttu-id="06ffa-208">RTC Service/Trusted Services</span><span class="sxs-lookup"><span data-stu-id="06ffa-208">RTC Service/Trusted Services</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="06ffa-209">Server proxy</span><span class="sxs-lookup"><span data-stu-id="06ffa-209">Proxy Servers</span></span></p></td>
<td><p><span data-ttu-id="06ffa-210">Lync Server 2013 non supporta la compatibilità con le versioni precedenti per i server proxy</span><span class="sxs-lookup"><span data-stu-id="06ffa-210">Lync Server 2013 does not support backward compatibility for proxy servers</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="06ffa-211">Per supportare i server attendibili delle versioni precedenti, è necessario eseguire lo strumento Analizzatore procedure consigliate.</span><span class="sxs-lookup"><span data-stu-id="06ffa-211">To support trusted servers of previous releases, you must run the best practices analyzer tool.</span></span> <span data-ttu-id="06ffa-212">Per informazioni dettagliate sull'esecuzione dell'Analizzatore procedure consigliate, vedere [https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633) .</span><span class="sxs-lookup"><span data-stu-id="06ffa-212">For details about running the best practices analyzer, see [https://go.microsoft.com/fwlink/p/?LinkId=330633](https://go.microsoft.com/fwlink/p/?linkid=330633).</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

