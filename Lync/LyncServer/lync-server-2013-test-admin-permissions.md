---
title: 'Lync Server 2013: verificare le autorizzazioni di amministrazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Test admin permissions
ms:assetid: 5dda3efd-0f84-4848-819e-87b1551066b1
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn767945(v=OCS.15)
ms:contentKeyID: 63969607
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4543501d668b61bbb90073c80c4e85373341d93
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41746476"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="test-admin-permissions-in-lync-server-2013"></a><span data-ttu-id="fad38-102">Verificare le autorizzazioni di amministratore in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fad38-102">Test admin permissions in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fad38-103">_**Argomento Ultima modifica:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="fad38-103">_**Topic Last Modified:** 2014-08-18_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="fad38-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="fad38-104">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="fad38-105">Dopo la distribuzione iniziale di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fad38-105">After initial Lync Server deployment.</span></span> <span data-ttu-id="fad38-106">Se necessario, se sorgono problemi relativi alle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="fad38-106">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="fad38-107">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="fad38-107">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="fad38-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fad38-108">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="fad38-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="fad38-109">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="fad38-110">Quando si esegue localmente tramite Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="fad38-110">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="fad38-111">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="fad38-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="fad38-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="fad38-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="fad38-113">Descrizione</span><span class="sxs-lookup"><span data-stu-id="fad38-113">Description</span></span>

<span data-ttu-id="fad38-114">Quando si installa Lync Server 2013 1 delle attività eseguite dal programma di installazione, il gruppo RTCUniversalUserAdmins offre le autorizzazioni di Active Directory necessarie per gestire utenti, computer, contatti, contatti delle applicazioni e persone InetOrg.</span><span class="sxs-lookup"><span data-stu-id="fad38-114">When you install Lync Server 2013 one of the tasks that were performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="fad38-115">Se l'ereditarietà delle autorizzazioni disabilitata nella configurazione di Active Directory non sarà in grado di assegnare tali autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="fad38-115">If you have disabled permission inheritance in Active Directory setup won't be able to assign those permissions.</span></span> <span data-ttu-id="fad38-116">Di conseguenza, i membri del gruppo RTCUniversalUserAdmins non saranno in grado di gestire le entità di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fad38-116">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Lync Server entities.</span></span> <span data-ttu-id="fad38-117">Tali privilegi di gestione saranno disponibili solo per gli amministratori di dominio.</span><span class="sxs-lookup"><span data-stu-id="fad38-117">Those management privileges will only be available to domain administrators.</span></span>

<span data-ttu-id="fad38-118">Il cmdlet Test-CsOUPermission verifica che le autorizzazioni necessarie necessarie per gestire utenti, computer e altri oggetti vengano impostate in un contenitore di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="fad38-118">The Test-CsOUPermission cmdlet verifies that the required permissions that are needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="fad38-119">Se tali autorizzazioni non sono impostate, è possibile risolvere il problema eseguendo il cmdlet [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) .</span><span class="sxs-lookup"><span data-stu-id="fad38-119">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) cmdlet.</span></span>

<span data-ttu-id="fad38-120">Tieni presente che Grant-CsOUPermission può assegnare le autorizzazioni solo ai membri del gruppo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="fad38-120">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="fad38-121">Non è possibile usare questo cmdlet per concedere le autorizzazioni a un utente o un gruppo arbitrario.</span><span class="sxs-lookup"><span data-stu-id="fad38-121">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="fad38-122">Se si vuole che un utente o un gruppo diverso disponga delle autorizzazioni di gestione degli utenti, è necessario aggiungere l'utente (o il gruppo) al gruppo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="fad38-122">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span>

<span data-ttu-id="fad38-123">Per altre informazioni sulle autorizzazioni dell'unità organizzativa, vedere l'articolo [autorizzazioni l'ereditarietà è disabilitata in computer, utenti o contenitori InetOrgPerson in Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span><span class="sxs-lookup"><span data-stu-id="fad38-123">For more information on OU permissions, see the article [Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="fad38-124">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="fad38-124">Running the test</span></span>

<span data-ttu-id="fad38-125">Per verificare che le autorizzazioni di gestione siano impostate in un contenitore, eseguire il cmdlet Test-CsOUPermission seguito dal nome distinto del contenitore e dal tipo di autorizzazioni da verificare.</span><span class="sxs-lookup"><span data-stu-id="fad38-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="fad38-126">Questo comando, ad esempio, controlla se le autorizzazioni utente sono impostate nell'ou ou = Redmond, DC = litwareinc, DC = com:</span><span class="sxs-lookup"><span data-stu-id="fad38-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

<span data-ttu-id="fad38-127">Per verificare più autorizzazioni con un solo comando, racchiudere ogni tipo di autorizzazione racchiuso tra virgolette, quindi separare i tipi usando le virgole.</span><span class="sxs-lookup"><span data-stu-id="fad38-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="fad38-128">Questo comando, ad esempio, verifica le autorizzazioni utente, computer e contatto:</span><span class="sxs-lookup"><span data-stu-id="fad38-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

<span data-ttu-id="fad38-129">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) .</span><span class="sxs-lookup"><span data-stu-id="fad38-129">For more information, see the help topic for the [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="fad38-130">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="fad38-130">Determining success or failure</span></span>

<span data-ttu-id="fad38-131">Se sono già state impostate le autorizzazioni necessarie, Test-CsOUPermission restituirà una risposta di una sola parola:</span><span class="sxs-lookup"><span data-stu-id="fad38-131">If the required permissions have already been set then Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="fad38-132">True</span><span class="sxs-lookup"><span data-stu-id="fad38-132">True</span></span>

<span data-ttu-id="fad38-133">Se non sono impostate le autorizzazioni necessarie, Test-CsOUPermission restituirà il valore false.</span><span class="sxs-lookup"><span data-stu-id="fad38-133">If the required permissions are not set then Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="fad38-134">Potrebbe essere necessario cercare un momento per trovare questo valore.</span><span class="sxs-lookup"><span data-stu-id="fad38-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="fad38-135">Verrà in genere incorporato all'interno di diversi avvisi di accompagnamento.</span><span class="sxs-lookup"><span data-stu-id="fad38-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="fad38-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="fad38-136">For example:</span></span>

<span data-ttu-id="fad38-137">AVVISO: voce di controllo di accesso (ACE) atl-cs\\-001 RTCUniversalUserReadOnlyGroup; consentire ReadProperty ContainerInherit Discendenti bf967aba-0de6-11D0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="fad38-137">WARNING: access control entry (ACE) atl-cs-001\\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span>

<span data-ttu-id="fad38-138">AVVISO: le voci di controllo di accesso (ACE) nell'oggetto "OU = NorthAmerica, DC = atl-cs-\\001 DC = LITWAREINC, DC = com" non sono pronte.</span><span class="sxs-lookup"><span data-stu-id="fad38-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\\DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="fad38-139">False</span><span class="sxs-lookup"><span data-stu-id="fad38-139">False</span></span>

<span data-ttu-id="fad38-140">AVVISO: l'elaborazione "Test-CsOUPermission" è stata completata con gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="fad38-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="fad38-141">gli avvisi "2" sono stati registrati durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="fad38-141">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="fad38-142">AVVISO: i risultati dettagliati sono disponibili in "C\\:\\Users\\admin\\\\AppData\\local Temp Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de. html".</span><span class="sxs-lookup"><span data-stu-id="fad38-142">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="fad38-143">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="fad38-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="fad38-144">Se Test-CsOUPermission non riesce, che in genere significa che l'autorizzazione specificata non è stata assegnata al gruppo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="fad38-144">If Test-CsOUPermission fails that will usually mean that the specified permission has not been assign to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="fad38-145">È possibile risolvere il problema e assegnare le autorizzazioni necessarie usando il cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="fad38-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="fad38-146">Ad esempio, questo comando fornisce le autorizzazioni di UO per utenti, contatti e InetOrgPerson al gruppo RTCUniversalUserAdmins:</span><span class="sxs-lookup"><span data-stu-id="fad38-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

<span data-ttu-id="fad38-147">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="fad38-147">For more information, see the help topic for the Grant-CsOUPermission cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

