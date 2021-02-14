---
title: Test delle autorizzazioni di amministratore in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Come testare le autorizzazioni di amministratore in Skype for Business Server
ms.openlocfilehash: 27ae50cca0018985ad59dbc4487dd3630cb5cf87
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800096"
---
# <a name="testing-admin-permissions-in-skype-for-business-server"></a><span data-ttu-id="0af28-103">Test delle autorizzazioni di amministratore in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0af28-103">Testing admin permissions in Skype for Business Server</span></span>

| | |
|--|--|
|<span data-ttu-id="0af28-104">Pianificazione della verifica</span><span class="sxs-lookup"><span data-stu-id="0af28-104">Verification schedule</span></span>|<span data-ttu-id="0af28-105">Dopo la distribuzione iniziale di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0af28-105">After initial Skype for Business Server deployment.</span></span> <span data-ttu-id="0af28-106">Se necessario, in caso di problemi relativi alle autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0af28-106">As needed if permission-related issues arise.</span></span>|
|<span data-ttu-id="0af28-107">Strumento di test</span><span class="sxs-lookup"><span data-stu-id="0af28-107">Testing tool</span></span>|<span data-ttu-id="0af28-108">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0af28-108">Windows PowerShell</span></span>|
|<span data-ttu-id="0af28-109">Autorizzazioni necessarie</span><span class="sxs-lookup"><span data-stu-id="0af28-109">Permissions required</span></span>|<span data-ttu-id="0af28-110">Quando vengono eseguiti localmente tramite Skype for Business Server Management Shell, gli utenti devono essere membri del gruppo di sicurezza RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="0af28-110">When run locally using the Skype for Business Server Management Shell, users must be members of the RTCUniversalServerAdmins security group.</span></span><br><br/><span data-ttu-id="0af28-111">Quando viene eseguito utilizzando un'istanza remota di Windows PowerShell, agli utenti deve essere assegnato un ruolo RBAC che dispone dell'autorizzazione per eseguire il cmdlet Test-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="0af28-111">When run using a remote instance of Windows PowerShell, users must be assigned an RBAC role that has permission to run the Test-CsOUPermission cmdlet.</span></span> <span data-ttu-id="0af28-112">Per visualizzare un elenco di tutti i ruoli RBAC che possono utilizzare questo cmdlet, eseguire il comando seguente dal prompt Windows PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="0af28-112">To see a list of all RBAC roles that can use this cmdlet, run the following command from the Windows PowerShell prompt:</span></span><br/><br/><span data-ttu-id="0af28-113">Get-CsAdminRole Where-Object \| {$_. Cmdlet -match "Test-CsOUPermission"}</span><span class="sxs-lookup"><span data-stu-id="0af28-113">Get-CsAdminRole \| Where-Object {$_.Cmdlets -match "Test-CsOUPermission"}</span></span>|
|||

## <a name="description"></a><span data-ttu-id="0af28-114">Descrizione</span><span class="sxs-lookup"><span data-stu-id="0af28-114">Description</span></span>

<span data-ttu-id="0af28-115">Quando si installa Skype for Business Server, una delle attività eseguite dal programma di installazione assegna al gruppo RTCUniversalUserAdmins le autorizzazioni di Active Directory necessarie per gestire utenti, computer, contatti, contatti dell'applicazione e persone InetOrg.</span><span class="sxs-lookup"><span data-stu-id="0af28-115">When you install Skype for Business Server, one of the tasks that was performed by the Setup program gives the RTCUniversalUserAdmins group the Active Directory permissions that are needed to manage users, computers, contacts, application contacts, and InetOrg persons.</span></span> <span data-ttu-id="0af28-116">Se l'ereditarietà delle autorizzazioni è stata disabilitata in Active Directory, il programma di installazione non sarà in grado di assegnare tali autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0af28-116">If you have disabled permission inheritance in Active Directory, setup won't be able to assign those permissions.</span></span> <span data-ttu-id="0af28-117">Di conseguenza, i membri del gruppo RTCUniversalUserAdmins non saranno in grado di gestire le entità di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0af28-117">As a result, members of the RTCUniversalUserAdmins group won't be able to manage Skype for Business Server entities.</span></span> <span data-ttu-id="0af28-118">Tali privilegi di gestione saranno disponibili solo per gli amministratori di dominio.</span><span class="sxs-lookup"><span data-stu-id="0af28-118">Those management privileges will only be available to domain administrators.</span></span> 

<span data-ttu-id="0af28-119">Il Test-CsOUPermission cmdlet verifica che le autorizzazioni necessarie per gestire utenti, computer e altri oggetti siano impostate su un contenitore di Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0af28-119">The Test-CsOUPermission cmdlet verifies that the required permissions needed to manage users, computers, and other objects are set on an Active Directory container.</span></span> <span data-ttu-id="0af28-120">Se tali autorizzazioni non sono impostate, è possibile risolvere il problema eseguendo il [cmdlet Grant-CsOUPermission.](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission)</span><span class="sxs-lookup"><span data-stu-id="0af28-120">If those permissions are not set, you can resolve this problem by running the [Grant-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/Grant-CsOUPermission).</span></span> 

<span data-ttu-id="0af28-121">Tenere presente Grant-CsOUPermission assegnare autorizzazioni solo ai membri del gruppo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="0af28-121">Note that Grant-CsOUPermission can only assign permissions to members of the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="0af28-122">Non è possibile utilizzare questo cmdlet per concedere autorizzazioni a un utente o a un gruppo arbitrario.</span><span class="sxs-lookup"><span data-stu-id="0af28-122">You can’t use this cmdlet to grant permissions to an arbitrary user or group.</span></span> <span data-ttu-id="0af28-123">Se si desidera che un utente o un gruppo diverso abbia le autorizzazioni di gestione degli utenti, è necessario aggiungere tale utente (o gruppo) al gruppo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="0af28-123">If you want a different user or group to have user management permissions, you should add that user (or group) to the RTCUniversalUserAdmins group.</span></span> 


## <a name="running-the-test"></a><span data-ttu-id="0af28-124">Esecuzione del test</span><span class="sxs-lookup"><span data-stu-id="0af28-124">Running the test</span></span>

<span data-ttu-id="0af28-125">Per verificare che le autorizzazioni di gestione siano impostate in un contenitore, eseguire il cmdlet Test-CsOUPermission seguito dal nome distinto del contenitore e dal tipo di autorizzazioni che si sta verificando.</span><span class="sxs-lookup"><span data-stu-id="0af28-125">To verify that management permissions are set on a container, run the Test-CsOUPermission cmdlet followed by the distinguished name of the container and by the type of permissions that you are verifying.</span></span> <span data-ttu-id="0af28-126">Ad esempio, questo comando controlla se le autorizzazioni utente sono impostate sull'unità organizzativa ou=Redmond,dc=litwareinc,dc=com:</span><span class="sxs-lookup"><span data-stu-id="0af28-126">For example, this command checks whether user permissions are set on the OU ou=Redmond,dc=litwareinc,dc=com:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user"`

<span data-ttu-id="0af28-127">Per verificare più autorizzazioni utilizzando un singolo comando, racchiudere ogni tipo di autorizzazione racchiuso tra virgolette, quindi separare tali tipi utilizzando le virgole.</span><span class="sxs-lookup"><span data-stu-id="0af28-127">To verify multiple permissions by using a single command, enclose each permission type enclosed in quotation marks, then separate those types by using commas.</span></span> <span data-ttu-id="0af28-128">Ad esempio, questo comando verifica le autorizzazioni utente, computer e contatto:</span><span class="sxs-lookup"><span data-stu-id="0af28-128">For example, this one command verifies user, computer, and contact permissions:</span></span>

`Test-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "computer", "contact"`

<span data-ttu-id="0af28-129">Per ulteriori informazioni, vedere [l'argomento della Guida relativo Test-CsOUPermission cmdlet.](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)</span><span class="sxs-lookup"><span data-stu-id="0af28-129">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).</span></span>

## <a name="determining-success-or-failure"></a><span data-ttu-id="0af28-130">Determinazione dell'esito positivo o negativo</span><span class="sxs-lookup"><span data-stu-id="0af28-130">Determining success or failure</span></span>

<span data-ttu-id="0af28-131">Se le autorizzazioni necessarie sono già state impostate, Test-CsOUPermission restituirà una risposta di una sola parola:</span><span class="sxs-lookup"><span data-stu-id="0af28-131">If the required permissions have already been set, Test-CsOUPermission will return a one-word response:</span></span>

<span data-ttu-id="0af28-132">Vero</span><span class="sxs-lookup"><span data-stu-id="0af28-132">True</span></span>

<span data-ttu-id="0af28-133">Se le autorizzazioni necessarie non sono impostate, Test-CsOUPermission restituirà il valore False.</span><span class="sxs-lookup"><span data-stu-id="0af28-133">If the required permissions are not set, Test-CsOUPermission will return the value False.</span></span> <span data-ttu-id="0af28-134">Potrebbe essere necessario cercare un momento per trovare questo valore.</span><span class="sxs-lookup"><span data-stu-id="0af28-134">You might have to search for a moment to find this value.</span></span> <span data-ttu-id="0af28-135">In genere, viene incorporato all'interno di diversi avvisi.</span><span class="sxs-lookup"><span data-stu-id="0af28-135">It will typically be embedded inside several accompanying warnings.</span></span> <span data-ttu-id="0af28-136">Ad esempio:</span><span class="sxs-lookup"><span data-stu-id="0af28-136">For example:</span></span>

<span data-ttu-id="0af28-137">AVVISO: voce di controllo di accesso (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Discendenti; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span><span class="sxs-lookup"><span data-stu-id="0af28-137">WARNING: access control entry (ACE) atl-cs-001\RTCUniversalUserReadOnlyGroup; allow; ReadProperty; ContainerInherit; Descendents; bf967aba-0de6-11d0-00aa003049e2; d819615a-3b9b-4738-b47e-f1bd8ee3aea4</span></span> 

<span data-ttu-id="0af28-138">AVVISO: le voci di controllo di accesso (ACE) sull'oggetto "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" non sono pronte.</span><span class="sxs-lookup"><span data-stu-id="0af28-138">WARNING: The access control entries (ACEs) on the object "OU=NorthAmerica,DC=atl-cs-001\DC=litwareinc,DC=com" are not ready.</span></span> 

<span data-ttu-id="0af28-139">Falso</span><span class="sxs-lookup"><span data-stu-id="0af28-139">False</span></span> 

<span data-ttu-id="0af28-140">AVVISO: l'elaborazione "Test-CsOUPermission" è stata completata con avvisi.</span><span class="sxs-lookup"><span data-stu-id="0af28-140">WARNING: "Test-CsOUPermission" processing has completed with warnings.</span></span> <span data-ttu-id="0af28-141">Durante l'esecuzione sono stati registrati avvisi "2".</span><span class="sxs-lookup"><span data-stu-id="0af28-141">"2" warnings were recorded during this run.</span></span> 

<span data-ttu-id="0af28-142">AVVISO: risultati dettagliati sono disponibili in "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span><span class="sxs-lookup"><span data-stu-id="0af28-142">WARNING: Detailed results can be found at "C:\Users\Admin\AppData\Local\Temp\Test-CsOUPermission-5d7a89af-f854-4a9c-87e3-69e37e58de.html".</span></span> 

## <a name="reasons-why-the-test-might-have-failed"></a><span data-ttu-id="0af28-143">Motivi per cui il test potrebbe non essere riuscito</span><span class="sxs-lookup"><span data-stu-id="0af28-143">Reasons why the test might have failed</span></span>

<span data-ttu-id="0af28-144">Se Test-CsOUPermission ha esito negativo, in genere l'autorizzazione specificata non è stata assegnata al gruppo RTCUniversalUserAdmins.</span><span class="sxs-lookup"><span data-stu-id="0af28-144">If Test-CsOUPermission fails, it usually means that the specified permission has not been assigned to the RTCUniversalUserAdmins group.</span></span> <span data-ttu-id="0af28-145">È possibile risolvere il problema e assegnare le autorizzazioni necessarie utilizzando il cmdlet Grant-CsOUPermission.</span><span class="sxs-lookup"><span data-stu-id="0af28-145">You can resolve this problem, and assign the required permissions, by using the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="0af28-146">Ad esempio, questo comando assegna le autorizzazioni ou per utenti, contatti e inetOrgPersons al gruppo RTCUniversalUserAdmins:</span><span class="sxs-lookup"><span data-stu-id="0af28-146">For example, this command gives OU permissions for users, contacts, and inetOrgPersons to the RTCUniversalUserAdmins group:</span></span>

`Grant-CsOUPermission -OU "ou=Redmond,dc=litwareinc,dc=com" -ObjectType "user", "contact", "inetOrgPerson"`

<span data-ttu-id="0af28-147">Per ulteriori informazioni, vedere [l'argomento della Guida relativo Test-CsOUPermission cmdlet.](https://docs.microsoft.com/powershell/module/skype/test-csoupermission)</span><span class="sxs-lookup"><span data-stu-id="0af28-147">For more information, see the [help topic for the Test-CsOUPermission cmdlet](https://docs.microsoft.com/powershell/module/skype/test-csoupermission).</span></span>
