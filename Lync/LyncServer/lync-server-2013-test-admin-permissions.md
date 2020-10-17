---
title: 'Lync Server 2013: testare le autorizzazioni di amministratore'
description: 'Lync Server 2013: testare le autorizzazioni di amministratore.'
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
ms.openlocfilehash: 07e15be288ed31afe9303d91ce3e623d19822428
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48568522"
---
# <a name="test-admin-permissions-in-lync-server-2013"></a><span data-ttu-id="73c32-103">Verificare le autorizzazioni di amministratore in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="73c32-103">Test admin permissions in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73c32-104">_**Ultimo argomento modificato:** 2014-08-18_</span><span class="sxs-lookup"><span data-stu-id="73c32-104">_**Topic Last Modified:** 2014-08-18_</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="73c32-105">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="73c32-105">Verification schedule</span></span></p></td>
<td><p><span data-ttu-id="73c32-106">Dopo la distribuzione iniziale di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="73c32-106">After initial Lync Server deployment.</span></span> <span data-ttu-id="73c32-107">Se necessario, se si verificano problemi relativi alle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="73c32-107">As needed if permission-related issues arise.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="73c32-108">Strumento di testing</span><span class="sxs-lookup"><span data-stu-id="73c32-108">Testing tool</span></span></p></td>
<td><p><span data-ttu-id="73c32-109">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="73c32-109">Windows PowerShell</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="73c32-110">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="73c32-110">Permissions required</span></span></p></td>
<td><p><span data-ttu-id="73c32-111">Quando si esegue localmente utilizzando Lync Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="73c32-111">When run locally using the Lync Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span></p>
<p><span data-ttu-id="73c32-112">Quando si esegue l'utilizzo di un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga dell'autorizzazione per eseguire il cmdlet Test-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="73c32-112">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="73c32-113">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando riportato di seguito dal prompt dei comandi di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="73c32-113">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span></p>
<pre><code>Get-CsAdminRole | Where-Object {$_.Cmdlets -match &quot;Test-CsOUPermission&quot;}</code></pre></td>
</tr>
</tbody>
</table>


<div>

## <a name="description"></a><span data-ttu-id="73c32-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="73c32-114">Description</span></span>

<span data-ttu-id="73c32-115">Quando si installa Lync Server 2013 1 delle attività eseguite dal programma di installazione, vengono fornite al gruppo RTCUniversalUserAdmins le autorizzazioni di Active Directory necessarie per la gestione di utenti, computer, contatti, contatti di applicazioni e persone di InetOrg.</span><span class="sxs-lookup"><span data-stu-id="73c32-115">When you install Lync Server 2013 one of the tasks that were performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="73c32-116">Se l'ereditarietà delle autorizzazioni disabilitata nel programma di installazione di Active Directory non è in grado di assegnare tali autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="73c32-116">If you have disabled permission inheritance in Active Directory setup won't be able to assign those permissions.</span></span> <span data-ttu-id="73c32-117">Di conseguenza, i membri del gruppo RTCUniversalUserAdmins non saranno in grado di gestire le entità di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="73c32-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Lync Server entities.</span></span> <span data-ttu-id="73c32-118">Tali privilegi di gestione saranno disponibili solo per gli amministratori di dominio.</span><span class="sxs-lookup"><span data-stu-id="73c32-118">Those management privileges will only be available to domain administrators.</span></span>

<span data-ttu-id="73c32-119">Il cmdlet Test-CsOUPermission verifica che le autorizzazioni necessarie per la gestione degli utenti, dei computer e di altri oggetti siano impostate su un contenitore di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="73c32-119">The Test-CsOUPermission cmdlet verifies that the required permissions that are needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="73c32-120">Se tali autorizzazioni non sono impostate, è possibile risolvere il problema eseguendo il cmdlet [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) .</span><span class="sxs-lookup"><span data-stu-id="73c32-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission) cmdlet.</span></span>

<span data-ttu-id="73c32-121">Si noti che Grant-CsOUPermission possibile assegnare autorizzazioni solo ai membri del gruppo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="73c32-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="73c32-122">Non è possibile utilizzare questo cmdlet per concedere le autorizzazioni a un utente o un gruppo arbitrario.</span><span class="sxs-lookup"><span data-stu-id="73c32-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="73c32-123">Se si desidera che un utente o un gruppo diverso disponga delle autorizzazioni per la gestione degli utenti, è necessario aggiungere tale utente (o gruppo) al gruppo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="73c32-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span>

<span data-ttu-id="73c32-124">Per ulteriori informazioni sulle autorizzazioni di unità organizzativa, vedere l'articolo [autorizzazioni l'ereditarietà è disabilitata su computer, utenti o contenitori InetOrgPerson in Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span><span class="sxs-lookup"><span data-stu-id="73c32-124">For more information on OU permissions, see the article [Permissions inheritance Is disabled on computers, users, or InetOrgPerson containers in Lync Server 2013](lync-server-2013-permissions-inheritance-is-disabled-on-computers-users-or-inetorgperson-containers.md).</span></span>

</div>

<div>

## <a name="running-the-test"></a><span data-ttu-id="73c32-125">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="73c32-125">Running the test</span></span>

<span data-ttu-id="73c32-126">Per verificare che le autorizzazioni di gestione siano impostate su un contenitore, eseguire il cmdlet Test-CsOUPermission seguito dal nome distinto del contenitore e dal tipo di autorizzazioni che si sta verificando.</span><span class="sxs-lookup"><span data-stu-id="73c32-126">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="73c32-127">Ad esempio, questo comando consente di controllare se le autorizzazioni utente sono impostate nell'unità organizzativa OU = Redmond, DC = litwareinc, DC = com:</span><span class="sxs-lookup"><span data-stu-id="73c32-127">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"

<span data-ttu-id="73c32-128">Per verificare più autorizzazioni utilizzando un singolo comando, racchiudere ogni tipo di autorizzazione racchiuso tra virgolette, quindi separare i tipi utilizzando le virgole.</span><span class="sxs-lookup"><span data-stu-id="73c32-128">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="73c32-129">Ad esempio, questo comando consente di verificare le autorizzazioni utente, computer e contatti:</span><span class="sxs-lookup"><span data-stu-id="73c32-129">For example, this one command verifies user, computer, and contact permissions:</span></span>

    Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"

<span data-ttu-id="73c32-130">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) .</span><span class="sxs-lookup"><span data-stu-id="73c32-130">For more information, see the help topic for the [Test-CsOUPermission](https://docs.microsoft.com/powershell/module/skype/Test-CsOUPermission) cmdlet.</span></span>

</div>

<div>

## <a name="determining-success-or-failure"></a><span data-ttu-id="73c32-131">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="73c32-131">Determining success or failure</span></span>

<span data-ttu-id="73c32-132">Se le autorizzazioni necessarie sono già state impostate, Test-CsOUPermission restituirà una risposta a una sola parola:</span><span class="sxs-lookup"><span data-stu-id="73c32-132">If the required permissions have already been set then Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="73c32-133">Vero</span><span class="sxs-lookup"><span data-stu-id="73c32-133">True</span></span>

<span data-ttu-id="73c32-134">Se le autorizzazioni necessarie non sono impostate, Test-CsOUPermission restituirà il valore false.</span><span class="sxs-lookup"><span data-stu-id="73c32-134">If the required permissions are not set then Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="73c32-135">Potrebbe essere necessario cercare un momento per trovare questo valore.</span><span class="sxs-lookup"><span data-stu-id="73c32-135">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="73c32-136">In genere viene incorporato all'interno di diversi avvisi di accompagnamento.</span><span class="sxs-lookup"><span data-stu-id="73c32-136">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="73c32-137">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="73c32-137">For example:</span></span>

<span data-ttu-id="73c32-138">AVVISO: voce di controllo di accesso (ACE) atl-cs-001 \\ RTCUniversalUserReadOnlyGroup; Consenti; ReadProperty ContainerInherit Discendenti bf967aba-0de6-11D0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="73c32-138">WARNING: access control entry (ACE) atl-cs-001\\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span>

<span data-ttu-id="73c32-139">AVVISO: le voci di controllo di accesso (ACE) dell'oggetto "OU = NorthAmerica, DC = atl-cs-001 \\ DC = litwareinc, DC = com" non sono pronte.</span><span class="sxs-lookup"><span data-stu-id="73c32-139">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\\DC=litwareinc,DC=com" are not ready.</span></span>

<span data-ttu-id="73c32-140">False</span><span class="sxs-lookup"><span data-stu-id="73c32-140">False</span></span>

<span data-ttu-id="73c32-141">AVVISO: l'elaborazione di "Test-CsOUPermission" è stata completata con gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="73c32-141">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="73c32-142">gli avvisi "2" sono stati registrati durante la fase di esecuzione.</span><span class="sxs-lookup"><span data-stu-id="73c32-142">"2" warnings were recorded during this run.</span></span>

<span data-ttu-id="73c32-143">AVVISO: i risultati dettagliati sono disponibili in "C: \\ Users \\ admin \\ AppData \\ Local \\ temp \\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span><span class="sxs-lookup"><span data-stu-id="73c32-143">WARNING: Detailed results can be found at "C:\\Users\\Admin\\AppData\\Local\\Temp\\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span>

</div>

<div>

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="73c32-144">Motivi per cui il test potrebbe non avere avuto esito positivo</span><span class="sxs-lookup"><span data-stu-id="73c32-144">Reasons why the test might have failed</span></span>

<span data-ttu-id="73c32-145">Se Test-CsOUPermission ha esito negativo che in genere significa che l'autorizzazione specificata non è stata assegnata al gruppo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="73c32-145">If Test-CsOUPermission fails that will usually mean that the specified permission has not been assign to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="73c32-146">È possibile risolvere il problema e assegnare le autorizzazioni necessarie utilizzando il cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="73c32-146">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="73c32-147">Ad esempio, questo comando fornisce le autorizzazioni di unità organizzativa per utenti, contatti e InetOrgPerson al gruppo RTCUniversalUserAdmins:</span><span class="sxs-lookup"><span data-stu-id="73c32-147">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

    Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"

<span data-ttu-id="73c32-148">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="73c32-148">For more information, see the help topic for the Grant-CsOUPermission cmdlet.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

