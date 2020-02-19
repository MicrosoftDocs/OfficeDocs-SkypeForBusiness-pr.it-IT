---
title: "Lync Server 2013: l'ereditarietà delle autorizzazioni è disabilitata in computer, utenti o contenitori InetOrgPerson"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers
ms:assetid: c472ad21-a93d-4fcb-a3d9-60a2134a87fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412970(v=OCS.15)
ms:contentKeyID: 48185348
ms.date: 12/19/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c67bda331532a11904b3edec469bceaa7e4f15b
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42139989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="32b1a-102">L'ereditarietà delle autorizzazioni è disabilitata su computer, utenti o contenitori InetOrgPerson in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32b1a-102">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32b1a-103">_**Ultimo argomento modificato:** 2014-12-19_</span><span class="sxs-lookup"><span data-stu-id="32b1a-103">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="32b1a-104">In un servizio di dominio Active Directory bloccato, gli utenti e gli oggetti computer vengono spesso inseriti in unità organizzative specifiche con l'ereditarietà delle autorizzazioni disabilitata per proteggere la delega amministrativa e per abilitare l'utilizzo di oggetti Criteri di gruppo (GPO) per applicare i criteri di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="32b1a-104">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="32b1a-105">Preparazione del dominio e attivazione del server impostare le voci di controllo di accesso (ACE) richieste da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="32b1a-105">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="32b1a-106">Quando l'ereditarietà delle autorizzazioni è disabilitata, i gruppi di sicurezza di Lync Server non possono ereditare tali ACE.</span><span class="sxs-lookup"><span data-stu-id="32b1a-106">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="32b1a-107">Quando queste autorizzazioni non vengono ereditate, i gruppi di sicurezza di Lync Server non possono accedere alle impostazioni e si verificano i due problemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="32b1a-107">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="32b1a-108">Per amministrare utenti, inetOrgPerson e contatti e per gestire i server, i gruppi di sicurezza di Lync Server richiedono gli ACE impostati dalla procedura di preparazione del dominio sui set di proprietà di ogni utente, l'RTC (Real-Time Communications), la ricerca degli utenti RTC e le informazioni pubbliche. .</span><span class="sxs-lookup"><span data-stu-id="32b1a-108">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="32b1a-109">Quando l'ereditarietà delle autorizzazioni è disabilitata, i gruppi di sicurezza non ereditano tali voci di controllo di accesso e non possono gestire né i server né gli utenti.</span><span class="sxs-lookup"><span data-stu-id="32b1a-109">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="32b1a-110">Per individuare i server e i pool, i server che eseguono Lync Server si basano sulle voci ACE impostate per l'attivazione su oggetti correlati al computer, tra cui il contenitore Microsoft e l'oggetto server.</span><span class="sxs-lookup"><span data-stu-id="32b1a-110">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="32b1a-111">Quando l'ereditarietà delle autorizzazioni è disabilitata, i gruppi di sicurezza, i server e i pool non ereditano tali voci di controllo di accesso e non possono usufruirne.</span><span class="sxs-lookup"><span data-stu-id="32b1a-111">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="32b1a-112">Per risolvere questi problemi, Lync Server fornisce il cmdlet **Grant-CsOUPermission** .</span><span class="sxs-lookup"><span data-stu-id="32b1a-112">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="32b1a-113">Questo cmdlet imposta gli ACE di Lync Server necessari direttamente su un contenitore e unità organizzativa specificati e gli oggetti all'interno del contenitore o dell'unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="32b1a-113">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="32b1a-114">Impostazione delle autorizzazioni per gli oggetti User, InetOrgPerson e Contact dopo l'esecuzione della preparazione del dominio</span><span class="sxs-lookup"><span data-stu-id="32b1a-114">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="32b1a-115">In un ambiente Active Directory bloccato in cui è disabilitata l'ereditarietà delle autorizzazioni, durante la preparazione del dominio non vengono impostate le voci di controllo di accesso necessarie nei contenitori o nelle unità organizzative che includono oggetti User o InetOrgPerson all'interno del dominio.</span><span class="sxs-lookup"><span data-stu-id="32b1a-115">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="32b1a-116">In questa situazione, è necessario eseguire il cmdlet **Grant-CsOuPermission** in ogni contenitore o unità organizzativa con oggetti User o InetOrgPerson per cui è disabilitata l'ereditarietà delle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="32b1a-116">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="32b1a-117">Nel caso di una topologia a foresta centralizzata, è necessario eseguire questa procedura anche nei contenitori o nelle unità organizzative che contengono oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="32b1a-117">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="32b1a-118">Per informazioni dettagliate sulle topologie di foreste centrali, vedere [supported Active Directory Topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="32b1a-118">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="32b1a-119">Il parametro ObjectType specifica il tipo di oggetto.</span><span class="sxs-lookup"><span data-stu-id="32b1a-119">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="32b1a-120">Il parametro OU specifica l'unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="32b1a-120">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="32b1a-121">Questo cmdlet consente di aggiungere le voci di controllo di accesso necessarie direttamente nei contenitori o nelle unità organizzative specificati e negli oggetti User o InetOrgPerson all'interno di tali contenitori.</span><span class="sxs-lookup"><span data-stu-id="32b1a-121">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="32b1a-122">Se nell'unità organizzativa in cui viene eseguito il comando sono presenti le unità organizzative figlio con gli oggetti User o InetOrgPerson, le autorizzazioni non verranno applicate a tali utenti.</span><span class="sxs-lookup"><span data-stu-id="32b1a-122">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="32b1a-123">Sarà necessario eseguire il comando su ogni unità organizzativa figlio individualmente.</span><span class="sxs-lookup"><span data-stu-id="32b1a-123">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="32b1a-124">Si tratta di uno scenario comune con le distribuzioni di hosting di Lync, ad esempio, i tenant di OU = OCS, DC = CONTOSO, DC = LOCAL e Child OU = Tenant1, OU = OCS Tenants, DC = CONTOSO, DC = LOCAL.</span><span class="sxs-lookup"><span data-stu-id="32b1a-124">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="32b1a-125">Per eseguire questo cmdlet, è necessario disporre di diritti utente equivalenti all'appartenenza al gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="32b1a-125">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="32b1a-126">Se anche gli ACE degli utenti autenticati sono stati rimossi nell'ambiente bloccato, è necessario concedere a questo account le voci ACE di accesso in lettura nei contenitori o le unità organizzative rilevanti nel dominio radice della foresta, come descritto in [autorizzazioni utente autenticate sono state rimosse in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) oppure utilizzare un account membro del gruppo Enterprise Admins.</span><span class="sxs-lookup"><span data-stu-id="32b1a-126">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="32b1a-127">**Per impostare le voci di controllo di accesso necessarie per gli oggetti User, InetOrgPerson e Contact**</span><span class="sxs-lookup"><span data-stu-id="32b1a-127">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="32b1a-128">Accedere a un computer appartenente al dominio con un account membro del gruppo Domain Admins o che disponga di diritti utente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="32b1a-128">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="32b1a-129">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="32b1a-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="32b1a-130">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="32b1a-130">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="32b1a-131">Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="32b1a-131">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="32b1a-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="32b1a-132">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="32b1a-133">Nel file di registro, cercare il risultato dell'esecuzione di \*\* \<esito positivo\> \*\* alla fine di ogni attività per verificare che le autorizzazioni siano state impostate e quindi chiudere la finestra del registro.</span><span class="sxs-lookup"><span data-stu-id="32b1a-133">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="32b1a-134">In alternativa, è possibile eseguire il comando seguente per determinare se le autorizzazioni sono state impostate:</span><span class="sxs-lookup"><span data-stu-id="32b1a-134">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="32b1a-135">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="32b1a-135">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="32b1a-136">Impostazione delle autorizzazioni per oggetti Computer dopo l'esecuzione della preparazione del dominio</span><span class="sxs-lookup"><span data-stu-id="32b1a-136">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="32b1a-137">In un ambiente Active Directory bloccato in cui è disabilitata l'ereditarietà delle autorizzazioni, durante la preparazione del dominio non vengono impostate le voci di controllo di accesso necessarie nei contenitori o nelle unità organizzative che includono oggetti Computer all'interno del dominio.</span><span class="sxs-lookup"><span data-stu-id="32b1a-137">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="32b1a-138">In questo caso, è necessario eseguire il cmdlet **Grant-CsOUPermission** in ogni contenitore o unità organizzativa che dispone di computer che eseguono Lync Server in cui l'ereditarietà delle autorizzazioni è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="32b1a-138">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="32b1a-139">Il parametro ObjectType specifica il tipo di oggetto.</span><span class="sxs-lookup"><span data-stu-id="32b1a-139">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="32b1a-140">Questa procedura consente di aggiungere le voci di controllo di accesso necessarie direttamente nei contenitori specificati.</span><span class="sxs-lookup"><span data-stu-id="32b1a-140">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="32b1a-141">Per eseguire questo cmdlet, è necessario disporre di diritti utente equivalenti all'appartenenza al gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="32b1a-141">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="32b1a-142">Se anche gli ACE degli utenti autenticati sono stati rimossi, è necessario concedere questo account alle voci ACE di accesso in lettura nei contenitori rilevanti nel dominio radice della foresta, come descritto in [autorizzazioni utente autenticate sono state rimosse in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) oppure utilizzare un account membro del gruppo Enterprise Admins.</span><span class="sxs-lookup"><span data-stu-id="32b1a-142">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="32b1a-143">**Per impostare le voci di controllo di accesso necessarie per gli oggetti computer**</span><span class="sxs-lookup"><span data-stu-id="32b1a-143">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="32b1a-144">Accedere al computer del dominio con un account membro del gruppo Domain Admins o che disponga di diritti utente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="32b1a-144">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="32b1a-145">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="32b1a-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="32b1a-146">Eseguire: </span><span class="sxs-lookup"><span data-stu-id="32b1a-146">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="32b1a-147">Se non si specifica il parametro Domain, per impostazione predefinita verrà utilizzato il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="32b1a-147">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="32b1a-148">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="32b1a-148">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="32b1a-149">Nel file di registro di esempio C\\:\\logs OUPermissions. XML, è necessario cercare il risultato dell'esecuzione di \*\* \<esito positivo\> \*\* alla fine di ogni attività e verificare che non vi siano errori e quindi chiudere il registro.</span><span class="sxs-lookup"><span data-stu-id="32b1a-149">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="32b1a-150">È possibile eseguire il cmdlet seguente per verificare le autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="32b1a-150">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="32b1a-151">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="32b1a-151">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="32b1a-152">Se si esegue la preparazione del dominio nel dominio radice della foresta in un ambiente Active Directory bloccato, tenere presente che Lync Server richiede l'accesso ai contenitori dello schema e della configurazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="32b1a-152">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="32b1a-153">Se l'autorizzazione utente autenticata predefinita è stata rimossa dallo schema o dai contenitori di configurazione&nbsp;in servizi di dominio Active Directory, solo i membri del gruppo Schema Admins (per il contenitore dello schema) o del gruppo Enterprise Admins (per il contenitore di configurazione) sono autorizzati ad accedere al contenitore specificato.</span><span class="sxs-lookup"><span data-stu-id="32b1a-153">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="32b1a-154">Poiché Setup. exe, i cmdlet di Lync Server Management Shell e il pannello di controllo di Lync Server richiedono l'accesso a questi contenitori, l'installazione e l'installazione degli strumenti di amministrazione avranno esito negativo a meno che l'utente che esegue l'installazione disponga di diritti utente equivalenti allo schema. Appartenenza ai gruppi Admins e Enterprise Admins.</span><span class="sxs-lookup"><span data-stu-id="32b1a-154">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="32b1a-155">Per risolvere questo problema, sarà necessario concedere al gruppo RTCUniversalGlobalWriteGroup l'accesso in lettura e scrittura ai contenitori dello schema e della configurazione.</span><span class="sxs-lookup"><span data-stu-id="32b1a-155">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

