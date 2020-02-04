---
title: 'Lync Server 2013: Ereditarietà delle autorizzazioni disabilitata nei contenitori di oggetti Computer, User o InetOrgPerson'
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
ms.openlocfilehash: da84454a6e02e02520206b5eb667edfcf4fce849
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755246"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers-in-lync-server-2013"></a><span data-ttu-id="03194-102">Ereditarietà delle autorizzazioni disabilitata nei contenitori di oggetti Computer, User o InetOrgPerson in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="03194-102">Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="03194-103">_**Argomento Ultima modifica:** 2014-12-19_</span><span class="sxs-lookup"><span data-stu-id="03194-103">_**Topic Last Modified:** 2014-12-19_</span></span>

<span data-ttu-id="03194-104">In un servizio di dominio Active Directory bloccato, gli utenti e gli oggetti computer vengono spesso collocati in unità organizzative specifiche con l'ereditarietà delle autorizzazioni disabilitata per proteggere la delega amministrativa e per consentire l'uso di oggetti Criteri di gruppo (GPO) per applicare i criteri di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="03194-104">In a locked-down Active Directory Domain Services, Users and Computer objects are often placed in specific organizational units (OUs) with permissions inheritance disabled to help secure administrative delegation and to enable use of Group Policy objects (GPOs) to enforce security policies.</span></span>

<span data-ttu-id="03194-105">Preparazione del dominio e attivazione del server impostare le voci di controllo di accesso (ACE) richieste da Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="03194-105">Domain preparation and server activation set the access control entries (ACEs) required by Lync Server 2013.</span></span> <span data-ttu-id="03194-106">Quando l'ereditarietà delle autorizzazioni è disabilitata, i gruppi di sicurezza di Lync Server non possono ereditare le voci ACE.</span><span class="sxs-lookup"><span data-stu-id="03194-106">When permissions inheritance is disabled, the Lync Server security groups cannot inherit these ACEs.</span></span> <span data-ttu-id="03194-107">Quando queste autorizzazioni non vengono ereditate, i gruppi di sicurezza di Lync Server non possono accedere alle impostazioni e sorgono i due problemi seguenti:</span><span class="sxs-lookup"><span data-stu-id="03194-107">When these permissions are not inherited, Lync Server security groups cannot access settings, and the following two issues arise:</span></span>

  - <span data-ttu-id="03194-108">Per amministrare utenti, inetOrgPerson e contatti e per gestire i server, i gruppi di sicurezza di Lync Server richiedono gli ACE impostati dalla procedura di preparazione del dominio sui set di proprietà di ogni utente, le comunicazioni in tempo reale (RTC), la ricerca degli utenti RTC e le informazioni pubbliche .</span><span class="sxs-lookup"><span data-stu-id="03194-108">To administer Users, InetOrgPersons, and Contacts, and to operate servers, the Lync Server security groups require ACEs set by the domain preparation procedure on each user’s property sets, real-time communications (RTC), RTC User Search, and Public Information.</span></span> <span data-ttu-id="03194-109">Quando l'ereditarietà delle autorizzazioni è disabilitata, i gruppi di sicurezza non ereditano queste Ace e non possono gestire server o utenti.</span><span class="sxs-lookup"><span data-stu-id="03194-109">When permissions inheritance is disabled, security groups do not inherit these ACEs and cannot manage servers or users.</span></span>

  - <span data-ttu-id="03194-110">Per individuare server e pool, i server che utilizzano Lync Server si basano sulle voci ACE impostate per l'attivazione in oggetti correlati al computer, incluso il contenitore Microsoft e l'oggetto server.</span><span class="sxs-lookup"><span data-stu-id="03194-110">To discover servers and pools, servers running Lync Server rely on ACEs set by activation on computer-related objects, including the Microsoft Container and Server object.</span></span> <span data-ttu-id="03194-111">Quando l'ereditarietà delle autorizzazioni è disabilitata, i gruppi di sicurezza, i server e i pool non ereditano queste voci ACE e non possono sfruttare queste voci ACE.</span><span class="sxs-lookup"><span data-stu-id="03194-111">When permissions inheritance is disabled, security groups, servers, and pools do not inherit these ACEs and cannot take advantage of these ACEs.</span></span>

<span data-ttu-id="03194-112">Per risolvere questi problemi, Lync Server fornisce il cmdlet **Grant-CsOUPermission** .</span><span class="sxs-lookup"><span data-stu-id="03194-112">To address these issues, Lync Server provides the **Grant-CsOuPermission** cmdlet.</span></span> <span data-ttu-id="03194-113">Questo cmdlet imposta le voci ACE di Lync Server necessarie direttamente su un contenitore e le unità organizzative specificati e gli oggetti all'interno del contenitore o dell'unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="03194-113">This cmdlet sets required Lync Server ACEs directly on a specified container and organizational units and the objects within the container or organizational unit.</span></span>

<div>

## <a name="set-permissions-for-user-inetorgperson-and-contact-objects-after-running-domain-preparation"></a><span data-ttu-id="03194-114">Impostare le autorizzazioni per gli oggetti utente, InetOrgPerson e contatto dopo l'uso della preparazione del dominio</span><span class="sxs-lookup"><span data-stu-id="03194-114">Set Permissions for User, InetOrgPerson, and Contact Objects after Running Domain Preparation</span></span>

<span data-ttu-id="03194-115">In un ambiente Active Directory bloccato in cui l'ereditarietà delle autorizzazioni è disabilitata, la preparazione del dominio non imposta le voci ACE necessarie per i contenitori o le unità organizzative che tengono gli utenti o gli oggetti InetOrgPerson all'interno del dominio.</span><span class="sxs-lookup"><span data-stu-id="03194-115">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or organizational units holding Users or InetOrgPerson objects within the domain.</span></span> <span data-ttu-id="03194-116">In questo caso, è necessario eseguire il cmdlet **Grant-CsOUPermission** in ogni contenitore o ou che contiene oggetti utente o inetOrgPerson per cui l'ereditarietà delle autorizzazioni è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="03194-116">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has User or InetOrgPerson objects for which permissions inheritance is disabled.</span></span> <span data-ttu-id="03194-117">Se si ha una topologia di foresta centrale, è necessario eseguire questa procedura anche per i contenitori o le unità organizzative che contengono oggetti contatto.</span><span class="sxs-lookup"><span data-stu-id="03194-117">If you have a central forest topology, you must also perform this procedure on the containers or OUs that hold contact objects.</span></span> <span data-ttu-id="03194-118">Per informazioni dettagliate sulle topologie della foresta centrale, vedere [topologie di Active Directory supportate in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) nella documentazione relativa alla supportabilità.</span><span class="sxs-lookup"><span data-stu-id="03194-118">For details about central forest topologies, see [Supported Active Directory topologies in Lync Server 2013](lync-server-2013-supported-active-directory-topologies.md) in the Supportability documentation.</span></span> <span data-ttu-id="03194-119">Il parametro ObjectType specifica il tipo di oggetto.</span><span class="sxs-lookup"><span data-stu-id="03194-119">The ObjectType parameter specifies the object type.</span></span> <span data-ttu-id="03194-120">Il parametro OU specifica l'unità organizzativa.</span><span class="sxs-lookup"><span data-stu-id="03194-120">The OU parameter specifies the organizational unit.</span></span>

<span data-ttu-id="03194-121">Questo cmdlet aggiunge le voci ACE necessarie direttamente ai contenitori o alle unità organizzative specificate e agli oggetti utente o InetOrgPerson all'interno del contenitore.</span><span class="sxs-lookup"><span data-stu-id="03194-121">This cmdlet adds the required ACEs directly on the specified containers or OUs and the User or InetOrgPerson objects within the container.</span></span> <span data-ttu-id="03194-122">Se l'unità organizzativa in cui viene eseguito il comando include unità organizzative figlio con oggetti utente o InetOrgPerson, le autorizzazioni non verranno applicate in tali.</span><span class="sxs-lookup"><span data-stu-id="03194-122">If the OU on which this command is executed has child OUs with User or InetOrgPerson objects, the permissions will not be applied on those.</span></span> <span data-ttu-id="03194-123">Sarà necessario eseguire il comando su ogni unità organizzativa figlio individualmente.</span><span class="sxs-lookup"><span data-stu-id="03194-123">You will need to run the command on each child OU individually.</span></span> <span data-ttu-id="03194-124">Si tratta di uno scenario comune con le distribuzioni di hosting di Lync, ad esempio i tenant di OU = OCS, DC = CONTOSO, DC = LOCAL e Child OU = Tenant1, OU = OCS tenant, DC = CONTOSO, DC = LOCAL.</span><span class="sxs-lookup"><span data-stu-id="03194-124">This is a common scenario with Lync Hosting Deployments e.g. Parent OU=OCS Tenants, DC=CONTOSO,DC=LOCAL and child OU=Tenant1, OU=OCS Tenants ,DC=CONTOSO,DC=LOCAL.</span></span>

<span data-ttu-id="03194-125">Per eseguire questo cmdlet sono necessari diritti utente equivalenti all'appartenenza al gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="03194-125">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="03194-126">Se le voci ACE dell'utente autenticato sono state rimosse anche nell'ambiente bloccato, è necessario concedere l'account ACEs di accesso in lettura per i contenitori o le unità organizzative del dominio radice della foresta, come descritto in [autorizzazioni utente autenticate vengono rimosse in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) o usare un account membro del gruppo amministratori organizzazione.</span><span class="sxs-lookup"><span data-stu-id="03194-126">If the authenticated user ACEs have also been removed in the locked-down environment, you must grant this account read-access ACEs on the relevant containers or OUs in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="03194-127">**Per impostare le voci ACE obbligatorie per gli oggetti utente, InetOrgPerson e contatto**</span><span class="sxs-lookup"><span data-stu-id="03194-127">**To set required ACEs for User, InetOrgPerson, and Contact objects**</span></span>

1.  <span data-ttu-id="03194-128">Accedere a un computer collegato al dominio con un account membro del gruppo Domain Admins o con diritti utente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="03194-128">Log on to a computer joined to the domain with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="03194-129">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="03194-129">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="03194-130">Eseguire</span><span class="sxs-lookup"><span data-stu-id="03194-130">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <User | Computer | InetOrgPerson | Contact | AppContact | Device> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="03194-131">Se non specifichi il parametro Domain, il valore predefinito è il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="03194-131">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="03194-132">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="03194-132">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net"

4.  <span data-ttu-id="03194-133">Nel file di log cercare il risultato dell'esecuzione di \*\* \<successo\> \*\* alla fine di ogni attività per verificare che le autorizzazioni siano state impostate e quindi chiudere la finestra del log.</span><span class="sxs-lookup"><span data-stu-id="03194-133">In the log file, look for **\<Success\>** Execution Result at the end of each task to verify that the permissions were set, and then close the log window.</span></span> <span data-ttu-id="03194-134">In alternativa, è possibile eseguire il comando seguente per determinare se sono state impostate le autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="03194-134">Or, you can run the following command to determine whether the permissions were set:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>] [-Report <fully qualified path and name of file to create>]
    
    <span data-ttu-id="03194-135">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="03194-135">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "User" -OU "cn=Redmond,dc=contoso,dc=net" -Domain "contoso.net" -Report "C:\Log\OUPermissionsTest.html"

</div>

<div>

## <a name="set-permissions-for-computer-objects-after-running-domain-preparation"></a><span data-ttu-id="03194-136">Impostare le autorizzazioni per gli oggetti computer dopo aver eseguito la preparazione del dominio</span><span class="sxs-lookup"><span data-stu-id="03194-136">Set Permissions for Computer Objects after Running Domain Preparation</span></span>

<span data-ttu-id="03194-137">In un ambiente Active Directory bloccato in cui l'ereditarietà delle autorizzazioni è disabilitata, la preparazione del dominio non imposta le voci ACE necessarie per i contenitori o le unità organizzative che contengono oggetti computer all'interno del dominio.</span><span class="sxs-lookup"><span data-stu-id="03194-137">In a locked-down Active Directory environment where permissions inheritance is disabled, domain preparation does not set the necessary ACEs on the containers or OUs that hold Computer objects within the domain.</span></span> <span data-ttu-id="03194-138">In questo caso, è necessario eseguire il cmdlet **Grant-CsOUPermission** in ogni contenitore o ou che include computer che eseguono Lync Server in cui l'ereditarietà delle autorizzazioni è disabilitata.</span><span class="sxs-lookup"><span data-stu-id="03194-138">In this situation, you must run the **Grant-CsOuPermission** cmdlet on each container or OU that has computers running Lync Server where permissions inheritance is disabled.</span></span> <span data-ttu-id="03194-139">Il parametro ObjectType specifica il tipo di oggetto.</span><span class="sxs-lookup"><span data-stu-id="03194-139">The ObjectType parameter specifies the object type.</span></span>

<span data-ttu-id="03194-140">Questa procedura aggiunge le voci ACE necessarie direttamente nei contenitori specificati.</span><span class="sxs-lookup"><span data-stu-id="03194-140">This procedure adds the required ACEs directly on the specified containers.</span></span>

<span data-ttu-id="03194-141">Per eseguire questo cmdlet sono necessari diritti utente equivalenti all'appartenenza al gruppo Domain Admins.</span><span class="sxs-lookup"><span data-stu-id="03194-141">You need user rights equivalent to Domain Admins group membership to run this cmdlet.</span></span> <span data-ttu-id="03194-142">Se sono state rimosse anche le voci ACE dell'utente autenticato, è necessario concedere a questo account le voci ACE di accesso in lettura nei contenitori rilevanti nel dominio radice della foresta, come descritto in [autorizzazioni utente autenticate vengono rimosse in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) o usare un account membro del gruppo amministratori organizzazione.</span><span class="sxs-lookup"><span data-stu-id="03194-142">If the authenticated user ACEs have also been removed, you must grant this account read-access ACEs on the relevant containers in the forest root domain as described in [Authenticated user permissions are removed in Lync Server 2013](lync-server-2013-authenticated-user-permissions-are-removed.md) or use an account that is a member of the Enterprise Admins group.</span></span>

<span data-ttu-id="03194-143">**Per impostare le voci ACE obbligatorie per gli oggetti computer**</span><span class="sxs-lookup"><span data-stu-id="03194-143">**To set required ACEs for computer objects**</span></span>

1.  <span data-ttu-id="03194-144">Accedere al computer del dominio con un account membro del gruppo Domain Admins o con diritti utente equivalenti.</span><span class="sxs-lookup"><span data-stu-id="03194-144">Log on to the domain computer with an account that is a member of the Domain Admins group or that has equivalent user rights.</span></span>

2.  <span data-ttu-id="03194-145">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="03194-145">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="03194-146">Eseguire</span><span class="sxs-lookup"><span data-stu-id="03194-146">Run:</span></span>
    
        Grant-CsOuPermission -ObjectType <Computer> 
        -OU <DN name for the computer OU container relative to the domain root container DN> 
        [-Domain <Domain FQDN>][-Report <fully qualified path and name of output report>]
    
    <span data-ttu-id="03194-147">Se non specifichi il parametro Domain, il valore predefinito è il dominio locale.</span><span class="sxs-lookup"><span data-stu-id="03194-147">If you do not specify the Domain parameter, the default value is the local domain.</span></span>
    
    <span data-ttu-id="03194-148">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="03194-148">For example:</span></span>
    
        Grant-CsOuPermission -ObjectType "Computer" -OU "ou=Lync Servers,dc=litwareinc,dc=com" -Report "C:\Logs\OUPermissions.xml"

4.  <span data-ttu-id="03194-149">Nel file di log di esempio C\\:\\logs OUPermissions. XML, si cercherà il risultato dell'esecuzione di \*\* \<successo\> \*\* alla fine di ogni attività e verificare che non ci siano errori e quindi chiudere il log.</span><span class="sxs-lookup"><span data-stu-id="03194-149">In the example log file C:\\Logs\\OUPermissions.xml, you would look for **\<Success\>** Execution Result at the end of each task and verify that there are no errors, and then close the log.</span></span> <span data-ttu-id="03194-150">Puoi eseguire il cmdlet seguente per testare le autorizzazioni:</span><span class="sxs-lookup"><span data-stu-id="03194-150">You can run the following cmdlet to test permissions:</span></span>
    
        Test-CsOuPermission -ObjectType <type of object> 
        -OU <DN name for the OU container relative to the domain root container DN> [-Domain <Domain FQDN>]
    
    <span data-ttu-id="03194-151">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="03194-151">For example:</span></span>
    
        Test-CsOuPermission -ObjectType "user","contact" -OU "cn=Bellevue,dc=contoso,dc=net" -Domain "contoso.net"
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="03194-152">Se si esegue la preparazione del dominio nel dominio radice della foresta in un ambiente Active Directory bloccato, tenere presente che Lync Server richiede l'accesso ai contenitori dello schema e della configurazione di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="03194-152">If you run domain preparation on the forest root domain in a locked-down Active Directory environment, be aware that Lync Server requires access to the Active Directory Schema and Configuration containers.</span></span><BR><span data-ttu-id="03194-153">Se l'autorizzazione utente autenticata predefinita viene rimossa dallo schema o dai contenitori di configurazione in&nbsp;servizi di dominio Active Directory, solo i membri del gruppo amministratori schema (per il contenitore dello schema) o del gruppo amministratori organizzazione (per il contenitore di configurazione) possono accedere al contenitore indicato.</span><span class="sxs-lookup"><span data-stu-id="03194-153">If the default authenticated user permission is removed from the Schema or the Configuration containers in AD&nbsp;DS, only members of the Schema Admins group (for Schema container) or Enterprise Admins group (for Configuration container) are permitted to access the given container.</span></span> <span data-ttu-id="03194-154">Poiché Setup. exe, i cmdlet di Lync Server Management Shell e il pannello di controllo di Lync Server richiedono l'accesso a questi contenitori, la configurazione e l'installazione degli strumenti di amministrazione avranno esito negativo, a meno che l'utente che ha eseguito l'installazione abbia diritti utente equivalenti a schema Membri del gruppo amministratori e amministratori aziendali.</span><span class="sxs-lookup"><span data-stu-id="03194-154">Because Setup.exe, Lync Server Management Shell cmdlets, and Lync Server Control Panel require access to these containers, Setup and installation of the administrative tools will fail unless the user running the installation has user rights equivalent to Schema Admins and Enterprise Admins group membership.</span></span><BR><span data-ttu-id="03194-155">Per risolvere il problema, è necessario concedere l'accesso in lettura e scrittura del gruppo RTCUniversalGlobalWriteGroup ai contenitori schema e configurazione.</span><span class="sxs-lookup"><span data-stu-id="03194-155">To remedy this situation, you must grant RTCUniversalGlobalWriteGroup group Read, Write access to the Schema and Configuration containers.</span></span>

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

