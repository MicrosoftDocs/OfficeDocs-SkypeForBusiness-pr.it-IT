---
title: Test delle autorizzazioni di amministratore in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Come verificare le autorizzazioni di amministratore in Skype for Business Server
ms.openlocfilehash: 97db574803b575d484240e7339d56603ae5432da
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817187"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="2e1c2-103">Test delle autorizzazioni di amministratore in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2e1c2-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="2e1c2-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="2e1c2-104">Verification schedule</span></span>|<span data-ttu-id="2e1c2-105">Dopo la distribuzione iniziale di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="2e1c2-106">Se necessario, se sorgono problemi relativi alle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="2e1c2-107">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="2e1c2-107">Testing tool</span></span>|<span data-ttu-id="2e1c2-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="2e1c2-108">Windows PowerShell</span></span>|
|<span data-ttu-id="2e1c2-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="2e1c2-109">Permissions required</span></span>|<span data-ttu-id="2e1c2-110">Quando si esegue localmente usando Skype for Business Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="2e1c2-111">Quando si esegue usando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che disponga delle autorizzazioni per eseguire il cmdlet Test-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="2e1c2-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono usare questo cmdlet, eseguire il comando seguente dal prompt di Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2e1c2-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="2e1c2-113">Get-CsAdminRole \| Where-Object {$ _. Cmdlet-confronta "Test-CsOUPermission"}</span><span class="sxs-lookup"><span data-stu-id="2e1c2-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="2e1c2-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="2e1c2-114">Description</span></span>

<span data-ttu-id="2e1c2-115">Quando si installa Skype for Business Server, una delle attività eseguite dal programma di installazione offre al gruppo RTCUniversalUserAdmins le autorizzazioni di Active Directory necessarie per gestire utenti, computer, contatti, contatti delle applicazioni e InetOrg persone.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="2e1c2-116">Se è stata disabilitata l'ereditarietà delle autorizzazioni in Active Directory, il programma di installazione non sarà in grado di assegnare tali autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="2e1c2-117">Di conseguenza, i membri del gruppo RTCUniversalUserAdmins non saranno in grado di gestire le entità di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="2e1c2-118">Tali privilegi di gestione saranno disponibili solo per gli amministratori di dominio.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="2e1c2-119">Il cmdlet Test-CsOUPermission verifica che le autorizzazioni necessarie per la gestione di utenti, computer e altri oggetti vengano impostate in un contenitore di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="2e1c2-120">Se tali autorizzazioni non sono impostate, è possibile risolvere il problema eseguendo il [cmdlet Grant-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission).</span><span class="sxs-lookup"><span data-stu-id="2e1c2-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="2e1c2-121">Tieni presente che Grant-CsOUPermission può assegnare le autorizzazioni solo ai membri del gruppo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="2e1c2-122">Non è possibile usare questo cmdlet per concedere le autorizzazioni a un utente o un gruppo arbitrario.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="2e1c2-123">Se si vuole che un utente o un gruppo diverso disponga delle autorizzazioni di gestione degli utenti, è necessario aggiungere l'utente (o il gruppo) al gruppo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="2e1c2-124">Eseguire il test</span><span class="sxs-lookup"><span data-stu-id="2e1c2-124">Running the test</span></span>

<span data-ttu-id="2e1c2-125">Per verificare che le autorizzazioni di gestione siano impostate in un contenitore, eseguire il cmdlet Test-CsOUPermission seguito dal nome distinto del contenitore e dal tipo di autorizzazioni da verificare.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="2e1c2-126">Questo comando, ad esempio, controlla se le autorizzazioni utente sono impostate nell'ou ou = Redmond, DC = litwareinc, DC = com:</span><span class="sxs-lookup"><span data-stu-id="2e1c2-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="2e1c2-127">Per verificare più autorizzazioni con un solo comando, racchiudere ogni tipo di autorizzazione racchiuso tra virgolette, quindi separare i tipi usando le virgole.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="2e1c2-128">Questo comando, ad esempio, verifica le autorizzazioni utente, computer e contatto:</span><span class="sxs-lookup"><span data-stu-id="2e1c2-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="2e1c2-129">Per altre informazioni, vedere l' [argomento della Guida relativo al cmdlet Test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span><span class="sxs-lookup"><span data-stu-id="2e1c2-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="2e1c2-130">Determinare l'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="2e1c2-130">Determining success or failure</span></span>

<span data-ttu-id="2e1c2-131">Se le autorizzazioni necessarie sono già state impostate, Test-CsOUPermission restituirà una risposta di una sola parola:</span><span class="sxs-lookup"><span data-stu-id="2e1c2-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="2e1c2-132">True</span><span class="sxs-lookup"><span data-stu-id="2e1c2-132">True</span></span>

<span data-ttu-id="2e1c2-133">Se le autorizzazioni necessarie non sono impostate, Test-CsOUPermission restituirà il valore false.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="2e1c2-134">Potrebbe essere necessario cercare un momento per trovare questo valore.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="2e1c2-135">Verrà in genere incorporato all'interno di diversi avvisi di accompagnamento.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="2e1c2-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="2e1c2-136">For example:</span></span>

<span data-ttu-id="2e1c2-137">AVVISO: voce di controllo di accesso (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; consentire ReadProperty ContainerInherit Discendenti bf967aba-0de6-11D0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="2e1c2-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="2e1c2-138">AVVISO: le voci di controllo di accesso (ACE) nell'oggetto "OU = NorthAmerica, DC = atl-cs-001\DC = litwareinc, DC = com" non sono pronte.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="2e1c2-139">False</span><span class="sxs-lookup"><span data-stu-id="2e1c2-139">False</span></span> 

<span data-ttu-id="2e1c2-140">AVVISO: l'elaborazione "Test-CsOUPermission" è stata completata con gli avvisi.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="2e1c2-141">gli avvisi "2" sono stati registrati durante l'esecuzione.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="2e1c2-142">AVVISO: i risultati dettagliati possono essere trovati in "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span><span class="sxs-lookup"><span data-stu-id="2e1c2-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="2e1c2-143">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="2e1c2-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="2e1c2-144">Se Test-CsOUPermission ha esito negativo, in genere significa che l'autorizzazione specificata non è stata assegnata al gruppo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="2e1c2-145">È possibile risolvere il problema e assegnare le autorizzazioni necessarie usando il cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="2e1c2-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="2e1c2-146">Ad esempio, questo comando fornisce le autorizzazioni di UO per utenti, contatti e InetOrgPerson al gruppo RTCUniversalUserAdmins:</span><span class="sxs-lookup"><span data-stu-id="2e1c2-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="2e1c2-147">Per altre informazioni, vedere l' [argomento della Guida relativo al cmdlet Test-CsOUPermission](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span><span class="sxs-lookup"><span data-stu-id="2e1c2-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/en-us/powershell/module/skype/test-csoupermission).</span></span>
