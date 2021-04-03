---
title: Assegnare pacchetti di criteri a utenti e gruppi
author: KarliStites
ms.author: kastites
ms.reviewer: tomkau, saragava, ritikag, jastark
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni sui diversi modi per assegnare pacchetti di criteri a utenti e gruppi in Microsoft Teams.
f1keywords:
- ms.teamsadmincenter.bulkoperations.users.edit
- ms.teamsadmincenter.bulkoperations.edit
ms.openlocfilehash: 0266cb5c34a13df0dac62be2258134e553a357d8
ms.sourcegitcommit: 2bb8556650120b4f7cf509d8ff93d7e4d058829b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574318"
---
# <a name="assign-policy-packages-to-users-and-groups"></a><span data-ttu-id="a8ae8-103">Assegnare pacchetti di criteri a utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="a8ae8-103">Assign policy packages to users and groups</span></span>

<span data-ttu-id="a8ae8-104">Questo articolo illustra i diversi modi per assegnare pacchetti di criteri a utenti e gruppi in Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-104">This article reviews the different ways to assign policy packages to users and groups in Microsoft Teams.</span></span> <span data-ttu-id="a8ae8-105">Prima di leggere, assicurarsi di aver letto [Assegnare criteri in Teams - Guida introduttiva.](policy-assignment-overview.md)</span><span class="sxs-lookup"><span data-stu-id="a8ae8-105">Before reading, be sure you've read [Assign policies in Teams - getting started](policy-assignment-overview.md).</span></span>

## <a name="assign-a-policy-package-to-users"></a><span data-ttu-id="a8ae8-106">Assegnare un pacchetto di criteri agli utenti</span><span class="sxs-lookup"><span data-stu-id="a8ae8-106">Assign a policy package to users</span></span>

<span data-ttu-id="a8ae8-107">Un pacchetto di criteri in Teams è una raccolta di criteri e impostazioni dei criteri predefiniti che è possibile assegnare agli utenti con ruoli uguali o simili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-107">A policy package in Teams is a collection of predefined policies and policy settings that you can assign to users who have the same or similar roles in your organization.</span></span> <span data-ttu-id="a8ae8-108">Ogni pacchetto di criteri è progettato in base a un ruolo utente e include criteri predefiniti e impostazioni dei criteri che supportano le attività tipiche del ruolo.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-108">Each policy package is designed around a user role and includes predefined policies and policy settings that support activities typical for that role.</span></span> <span data-ttu-id="a8ae8-109">Alcuni esempi di pacchetti di criteri sono il pacchetto Education (Teacher) e il pacchetto Healthcare (Clinical Worker).</span><span class="sxs-lookup"><span data-stu-id="a8ae8-109">Some examples of policy packages are the Education (Teacher) package and Healthcare (Clinical worker) package.</span></span> <span data-ttu-id="a8ae8-110">Per altre informazioni, vedere [Gestire i pacchetti di criteri in Teams.](manage-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="a8ae8-110">To learn more, see [Manage policy packages in Teams](manage-policy-packages.md).</span></span>

### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="a8ae8-111">Assegnare un pacchetto di criteri a un utente</span><span class="sxs-lookup"><span data-stu-id="a8ae8-111">Assign a policy package to one user</span></span>

1. <span data-ttu-id="a8ae8-112">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi selezionare l'utente.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-112">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then select the user.</span></span>
2. <span data-ttu-id="a8ae8-113">Nella pagina dell'utente selezionare **Criteri** e quindi accanto a Pacchetto **criteri** selezionare **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="a8ae8-113">On the user's page, select **Policies**, and then next to **Policy package**, select **Edit**.</span></span>
3. <span data-ttu-id="a8ae8-114">Nel riquadro **Assegna pacchetto di** criteri selezionare il pacchetto da assegnare e quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-114">In the **Assign policy package** pane, select the package you want to assign, and then select **Save**.</span></span>

![Screenshot dell'interfaccia di amministrazione di Teams per l'assegnazione di pacchetti di criteri a un utente](media/assign-policypackages-user.png)

### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="a8ae8-116">Assegnare un pacchetto di criteri a più utenti</span><span class="sxs-lookup"><span data-stu-id="a8ae8-116">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="a8ae8-117">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a Pacchetti criteri **e** quindi selezionare il pacchetto di criteri da assegnare facendo clic a sinistra del nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-117">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="a8ae8-118">Scegliere **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-118">Select **Manage users**.</span></span>
3. <span data-ttu-id="a8ae8-119">Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-119">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="a8ae8-120">Ripetere questa operazione per ogni utente da aggiungere.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-120">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="a8ae8-121">Dopo aver aggiunto gli utenti, selezionare **Salva.**</span><span class="sxs-lookup"><span data-stu-id="a8ae8-121">When you're finished adding users, select **Save**.</span></span>

![Screenshot dell'interfaccia di amministrazione di Teams per l'assegnazione di pacchetti di criteri a più utenti](media/assign-policypackages-multipleusers.png)

## <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="a8ae8-123">Assegnare un pacchetto di criteri a un gruppo</span><span class="sxs-lookup"><span data-stu-id="a8ae8-123">Assign a policy package to a group</span></span>

<span data-ttu-id="a8ae8-124">L'assegnazione di pacchetti di criteri ai gruppi consente di assegnare più criteri a un gruppo di utenti, ad esempio un gruppo di sicurezza o una lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-124">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="a8ae8-125">L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-125">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="a8ae8-126">Quando vengono aggiunti o rimossi membri da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-126">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span>

<span data-ttu-id="a8ae8-127">L'assegnazione di pacchetti di criteri ai gruppi è consigliata per gruppi con un massimo di 50.000 utenti, ma funziona anche con gruppi più grandi.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-127">Policy package assignment to groups is recommended for groups of up to 50,000 users, but it will also work with larger groups.</span></span>

<span data-ttu-id="a8ae8-128">Quando si assegna il pacchetto di criteri, questo viene immediatamente assegnato al gruppo.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-128">When you assign the policy package, it's immediately assigned to the group.</span></span> <span data-ttu-id="a8ae8-129">Tuttavia, la propagazione dell'assegnazione dei criteri ai membri del gruppo viene eseguita come operazione in background e può richiedere del tempo, a seconda delle dimensioni del gruppo.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-129">However, the propagation of the policy assignment to members of the group is performed as a background operation and might take some time, depending on the size of the group.</span></span> <span data-ttu-id="a8ae8-130">Lo stesso vale quando un criterio non è assegnato a un gruppo o quando i membri vengono aggiunti o rimossi da un gruppo.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-130">The same is true when a policy is unassigned from a group, or when members are added to or removed from a group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a8ae8-131">Prima di iniziare, è importante comprendere[(](assign-policies-users-and-groups.md#precedence-rules)regole di precedenza ) e ([classificazione assegnazione gruppo](assign-policies-users-and-groups.md#group-assignment-ranking)).</span><span class="sxs-lookup"><span data-stu-id="a8ae8-131">Before you get started, it's important to understand ([precedence rules](assign-policies-users-and-groups.md#precedence-rules)) and ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)).</span></span> <span data-ttu-id="a8ae8-132">Leggere e comprendere i concetti descritti in[(](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)Informazioni necessarie sull'assegnazione dei criteri ai gruppi ) più indietro in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-132">Make sure you read and understand the concepts in ([What you need to know about policy assignment to groups](assign-policies-users-and-groups.md#what-you-need-to-know-about-policy-assignment-to-groups)) earlier in this article.</span></span>

### <a name="assign-a-policy-package-to-a-group-of-users-in-the-admin-center"></a><span data-ttu-id="a8ae8-133">Assegnare un pacchetto di criteri a un gruppo di utenti nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="a8ae8-133">Assign a policy package to a group of users in the admin center</span></span>

1. <span data-ttu-id="a8ae8-134">Passare all'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-134">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="a8ae8-135">Nel riquadro di spostamento sinistro passare alla pagina del pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-135">In the left navigation, go to the policy package page.</span></span>
3. <span data-ttu-id="a8ae8-136">Selezionare la scheda Assegnazione criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-136">Select the Group policy assignment tab.</span></span>
4. <span data-ttu-id="a8ae8-137">Selezionare **Aggiungi gruppo** e quindi nel riquadro Assegna un pacchetto di criteri al gruppo eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a8ae8-137">Select **Add group**, and then in the Assign a policy package to group pane, do the following:</span></span>

    <span data-ttu-id="a8ae8-138">a.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-138">a.</span></span> <span data-ttu-id="a8ae8-139">Cercare e aggiungere il gruppo a cui si vuole assegnare il pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-139">Search for and add the group you want to assign the policy package to.</span></span>

    <span data-ttu-id="a8ae8-140">b.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-140">b.</span></span> <span data-ttu-id="a8ae8-141">Selezionare un pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-141">Select a policy package.</span></span>

    <span data-ttu-id="a8ae8-142">c.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-142">c.</span></span> <span data-ttu-id="a8ae8-143">Impostare la classificazione per ogni tipo di criterio.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-143">Set the ranking for each policy type.</span></span>

    <span data-ttu-id="a8ae8-144">d.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-144">d.</span></span> <span data-ttu-id="a8ae8-145">Selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-145">Select **Apply**.</span></span>

![mostra l'assegnazione di Criteri di gruppo](media/group-pkg-assignment.png)

5. <span data-ttu-id="a8ae8-147">Per gestire la classificazione per un tipo di criterio specifico, passare alla pagina dei criteri specifica.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-147">To manage ranking for a specific policy type, navigate to the specific policy page.</span></span>
6. <span data-ttu-id="a8ae8-148">Per riassegnare un pacchetto di criteri a un gruppo, rimuovere prima l'assegnazione dei criteri di gruppo.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-148">To reassign a policy package to a group, first remove the group policy assignment.</span></span> <span data-ttu-id="a8ae8-149">Seguire quindi i passaggi precedenti per assegnare il pacchetto di criteri a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-149">Then, follow the steps above to assign the policy package to a group.</span></span>

### <a name="work-with-powershell"></a><span data-ttu-id="a8ae8-150">Usare PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8ae8-150">Work with PowerShell</span></span>

#### <a name="get-the-teams-powershell-module"></a><span data-ttu-id="a8ae8-151">Ottenere il modulo di PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="a8ae8-151">Get the Teams PowerShell module</span></span>

<span data-ttu-id="a8ae8-152">Per istruzioni dettagliate, vedere Installare [PowerShell di Teams.](teams-powershell-install.md)</span><span class="sxs-lookup"><span data-stu-id="a8ae8-152">For step-by-step guidance, see [Install Teams PowerShell](teams-powershell-install.md).</span></span>

#### <a name="assign-a-policy-package-to-a-group-of-users"></a><span data-ttu-id="a8ae8-153">Assegnare un pacchetto di criteri a un gruppo di utenti</span><span class="sxs-lookup"><span data-stu-id="a8ae8-153">Assign a policy package to a group of users</span></span>

<span data-ttu-id="a8ae8-154">Usare il cmdlet [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) per assegnare un pacchetto di criteri a un gruppo.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-154">Use the [Grant-CsGroupPolicyPackageAssignment](https://docs.microsoft.com/powershell/module/teams/grant-csgrouppolicypackageassignment) cmdlet to assign a policy package to a group.</span></span> <span data-ttu-id="a8ae8-155">È possibile specificare un gruppo usando l'ID oggetto, l'indirizzo SIP o l'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-155">You can specify a group by using the object ID, SIP address, or email address.</span></span> <span data-ttu-id="a8ae8-156">Quando si assegna il pacchetto di criteri, specificare una ( classificazione[assegnazione gruppo](assign-policies-users-and-groups.md#group-assignment-ranking)) per ogni tipo di criterio nel pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-156">When you assign the policy package, specify a ([group assignment ranking](assign-policies-users-and-groups.md#group-assignment-ranking)) for each policy type in the policy package.</span></span>

<span data-ttu-id="a8ae8-157">In questo esempio il pacchetto di criteri Education_Teacher viene assegnato a un gruppo con una classificazione delle assegnazioni 1 per TeamsAppSetupPolicy e TeamsMeetingBroadcastPolicy e una classificazione 2 per TeamsMeetingPolicy.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-157">In this example, we assign the Education_Teacher policy package to a group with an assignment ranking of 1 for TeamsAppSetupPolicy and TeamsMeetingBroadcastPolicy and a ranking of 2 for TeamsMeetingPolicy.</span></span>

```powershell
Grant-CsGroupPolicyPackageAssignment -GroupId "dae90bb4-120f-4a3e-a15d-30f142e79f69" -PackageName "Education_Teacher" -PolicyRankings "TeamsAppSetupPolicy, 1", "TeamsMeetingBroadcastPolicy, 1", "TeamsMeetingPolicy, 2"
```

## <a name="assign-a-policy-package-to-a-batch-of-users"></a><span data-ttu-id="a8ae8-158">Assegnare un pacchetto di criteri a un batch di utenti</span><span class="sxs-lookup"><span data-stu-id="a8ae8-158">Assign a policy package to a batch of users</span></span>

<span data-ttu-id="a8ae8-159">Con l'assegnazione di pacchetti di criteri batch, è possibile assegnare un pacchetto di criteri a set di utenti di grandi dimensioni alla volta senza dover usare uno script.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-159">With batch policy package assignment, you can assign a policy package to large sets of users at a time without having to use a script.</span></span> <span data-ttu-id="a8ae8-160">Usare il cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) per inviare un batch di utenti e il pacchetto di criteri da assegnare.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-160">You use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="a8ae8-161">Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-161">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span> <span data-ttu-id="a8ae8-162">È quindi possibile usare il cmdlet [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) per tenere traccia dello stato e dello stato delle assegnazioni in un batch.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-162">You can then use the [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation) cmdlet to track the progress and status of the assignments in a batch.</span></span>

<span data-ttu-id="a8ae8-163">Specificare gli utenti in base all'ID oggetto o all'indirizzo SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="a8ae8-163">Specify users by their object ID or Session Initiation Protocol (SIP) address.</span></span> <span data-ttu-id="a8ae8-164">L'indirizzo SIP di un utente spesso ha lo stesso valore del nome dell'entità utente (UPN) o dell'indirizzo di posta elettronica, ma non è obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-164">A user's SIP address often has the same value as the User Principal Name (UPN) or email address, but this isn't required.</span></span> <span data-ttu-id="a8ae8-165">Se un utente viene specificato usando l'UPN o la posta elettronica, ma ha un valore diverso dall'indirizzo SIP, l'assegnazione dei criteri non riuscirà per l'utente.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-165">If a user is specified using their UPN or email, but it has a different value than their SIP address, then policy assignment will fail for the user.</span></span> <span data-ttu-id="a8ae8-166">Se un batch include utenti duplicati, i duplicati verranno rimossi dal batch prima dell'elaborazione e lo stato verrà fornito solo per gli utenti univoci rimanenti nel batch.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-166">If a batch includes duplicate users, the duplicates will be removed from the batch before processing and status will only be provided for the unique users remaining in the batch.</span></span>

<span data-ttu-id="a8ae8-167">Un batch contiene fino a 5.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-167">A batch contains up to 5,000 users.</span></span> <span data-ttu-id="a8ae8-168">Per risultati ottimali, non inviare più di pochi batch alla volta.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-168">For best results, don't submit more than a few batches at a time.</span></span> <span data-ttu-id="a8ae8-169">Consentire ai batch di completare l'elaborazione prima di inviare altri batch.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-169">Allow batches to complete processing before submitting more batches.</span></span>

### <a name="use-the-teams-powershell-module"></a><span data-ttu-id="a8ae8-170">Usare il modulo di PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="a8ae8-170">Use the Teams PowerShell module</span></span>

<span data-ttu-id="a8ae8-171">Eseguire le operazioni seguenti per installare il [modulo di PowerShell](https://www.powershellgallery.com/packages/MicrosoftTeams) di Microsoft Teams (se non è già stato fatto).</span><span class="sxs-lookup"><span data-stu-id="a8ae8-171">Run the following to install the [Microsoft Teams PowerShell module](https://www.powershellgallery.com/packages/MicrosoftTeams) (if you haven't already).</span></span> <span data-ttu-id="a8ae8-172">Assicurarsi di installare la versione 1.0.5 o successiva.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-172">Make sure you install version 1.0.5 or later.</span></span>

```powershell
Install-Module -Name MicrosoftTeams
```

<span data-ttu-id="a8ae8-173">Eseguire le operazioni seguenti per connettersi a Teams e avviare una sessione.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-173">Run the following to connect to Teams and start a session.</span></span>

```powershell
Connect-MicrosoftTeams
```

<span data-ttu-id="a8ae8-174">Quando richiesto, accedere con le credenziali di amministratore.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-174">When you're prompted, sign in using your admin credentials.</span></span>

### <a name="assign-policy-packages-to-a-batch-of-users"></a><span data-ttu-id="a8ae8-175">Assegnare pacchetti di criteri a un batch di utenti</span><span class="sxs-lookup"><span data-stu-id="a8ae8-175">Assign policy packages to a batch of users</span></span>

<span data-ttu-id="a8ae8-176">In questo esempio viene utilizzato il cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) per assegnare il pacchetto di criteri di Education_PrimaryStudent a un batch di utenti.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-176">In this example, we use the [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation) cmdlet to assign the Education_PrimaryStudent policy package to a batch of users.</span></span>

```powershell
New-CsBatchPolicyPackageAssignmentOperation -Identity 1bc0b35f-095a-4a37-a24c-c4b6049816ab,user1@econtoso.com,user2@contoso.com -PackageName Education_PrimaryStudent
```

### <a name="see-the-status-of-a-batch-assignment"></a><span data-ttu-id="a8ae8-177">Visualizzare lo stato di un'assegnazione batch</span><span class="sxs-lookup"><span data-stu-id="a8ae8-177">See the status of a batch assignment</span></span>

<span data-ttu-id="a8ae8-178">Eseguire quanto segue per ottenere lo stato di un'assegnazione batch, dove OperationId è l'ID operazione restituito dal ```New-CsBatchPolicyAssignmentOperation``` cmdlet per un determinato batch.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-178">Run the following to get the status of a batch assignment, where OperationId is the operation ID that's returned by the ```New-CsBatchPolicyAssignmentOperation``` cmdlet for a given batch.</span></span>

```powershell
$Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | fl
```

<span data-ttu-id="a8ae8-179">Se l'output indica che si è verificato un errore, eseguire le operazioni seguenti per ottenere altre informazioni sugli errori presenti nella ```UserState``` proprietà.</span><span class="sxs-lookup"><span data-stu-id="a8ae8-179">If the output shows that an error occurred, run the following to get more information about errors, which are in the ```UserState``` property.</span></span>

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId f985e013-0826-40bb-8c94-e5f367076044 | Select -ExpandProperty UserState
```

<span data-ttu-id="a8ae8-180">Per altre informazioni, vedere [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="a8ae8-180">To learn more, see [Get-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/get-csbatchpolicyassignmentoperation).</span></span>

## <a name="related-topics"></a><span data-ttu-id="a8ae8-181">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a8ae8-181">Related topics</span></span>

- [<span data-ttu-id="a8ae8-182">Gestire Teams con i criteri</span><span class="sxs-lookup"><span data-stu-id="a8ae8-182">Manage Teams with policies</span></span>](manage-teams-with-policies.md)
- [<span data-ttu-id="a8ae8-183">Gestire i pacchetti di criteri in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8ae8-183">Manage policy packages in Microsoft Teams</span></span>](manage-policy-packages.md)
- [<span data-ttu-id="a8ae8-184">Panoramica di Teams PowerShell</span><span class="sxs-lookup"><span data-stu-id="a8ae8-184">Teams PowerShell Overview</span></span>](teams-powershell-overview.md)
- [<span data-ttu-id="a8ae8-185">Assegnare criteri in Teams - Guida introduttiva</span><span class="sxs-lookup"><span data-stu-id="a8ae8-185">Assign policies in Teams - getting started</span></span>](policy-assignment-overview.md)