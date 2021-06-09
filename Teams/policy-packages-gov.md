---
title: Teams di criteri per enti pubblici
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i Teams dei criteri per l'organizzazione governativa.
ms.openlocfilehash: 41ae937323b37948c03128efd565f40c02bbd6a2
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796870"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="e9d46-103">Teams di criteri per enti pubblici</span><span class="sxs-lookup"><span data-stu-id="e9d46-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="e9d46-104">I pacchetti di criteri non sono attualmente disponibili nelle distribuzioni Microsoft 365 Government GCC High o DoD.</span><span class="sxs-lookup"><span data-stu-id="e9d46-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="e9d46-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="e9d46-105">Overview</span></span>

<span data-ttu-id="e9d46-106">Un [Pacchetto di criteri](manage-policy-packages.md) in Microsoft Teams è una raccolta di criteri e impostazioni predefiniti da assegnare agli utenti con ruoli simili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e9d46-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="e9d46-107">I pacchetti di criteri semplificano la gestione dei criteri e contribuiscono a garantirne la coerenza.</span><span class="sxs-lookup"><span data-stu-id="e9d46-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="e9d46-108">È possibile personalizzare le impostazioni dei criteri del pacchetto in base alle esigenze degli utenti.</span><span class="sxs-lookup"><span data-stu-id="e9d46-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="e9d46-109">Quando si modificano le impostazioni dei criteri in un pacchetto di criteri, tutti gli utenti assegnati al pacchetto ottengono le impostazioni aggiornate.</span><span class="sxs-lookup"><span data-stu-id="e9d46-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="e9d46-110">È possibile gestire i pacchetti dei criteri tramite l'interfaccia di amministrazione di Microsoft Teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9d46-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="e9d46-111">I pacchetti di criteri predefiniscono i criteri per gli elementi seguenti, a seconda del pacchetto:</span><span class="sxs-lookup"><span data-stu-id="e9d46-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="e9d46-112">Messaggistica</span><span class="sxs-lookup"><span data-stu-id="e9d46-112">Messaging</span></span>
- <span data-ttu-id="e9d46-113">Riunioni</span><span class="sxs-lookup"><span data-stu-id="e9d46-113">Meetings</span></span>
- <span data-ttu-id="e9d46-114">Chiamate</span><span class="sxs-lookup"><span data-stu-id="e9d46-114">Calling</span></span>
- <span data-ttu-id="e9d46-115">Configurazione delle app</span><span class="sxs-lookup"><span data-stu-id="e9d46-115">App setup</span></span>
- <span data-ttu-id="e9d46-116">Eventi live</span><span class="sxs-lookup"><span data-stu-id="e9d46-116">Live events</span></span>

<span data-ttu-id="e9d46-117">Teams attualmente include i pacchetti di criteri per enti pubblici seguenti.</span><span class="sxs-lookup"><span data-stu-id="e9d46-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="e9d46-118">Nome del pacchetto nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e9d46-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="e9d46-119">Ideale per</span><span class="sxs-lookup"><span data-stu-id="e9d46-119">Best used for</span></span>|<span data-ttu-id="e9d46-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e9d46-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="e9d46-121">Responsabile della sicurezza pubblica</span><span class="sxs-lookup"><span data-stu-id="e9d46-121">Public safety officer</span></span>  |<span data-ttu-id="e9d46-122">Responsabili della sicurezza pubblica nell'organizzazione governativa</span><span class="sxs-lookup"><span data-stu-id="e9d46-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="e9d46-123">Crea un set di criteri e impostazioni dei criteri che si applicano ai responsabili della sicurezza pubblica nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e9d46-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="e9d46-124">Frontline Manager</span><span class="sxs-lookup"><span data-stu-id="e9d46-124">Frontline manager</span></span>  |<span data-ttu-id="e9d46-125">Responsabili in prima linea nell'organizzazione governativa</span><span class="sxs-lookup"><span data-stu-id="e9d46-125">Frontline Managers in your government organization</span></span> |<span data-ttu-id="e9d46-126">Crea un set di criteri e applica tali impostazioni ai responsabili in prima linea dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e9d46-126">Creates a set of policies and applies those settings to Frontline Managers in your organization.</span></span>|
|<span data-ttu-id="e9d46-127">Operaio in prima linea</span><span class="sxs-lookup"><span data-stu-id="e9d46-127">Frontline worker</span></span>  |<span data-ttu-id="e9d46-128">Frontline Workers nell'organizzazione governativa</span><span class="sxs-lookup"><span data-stu-id="e9d46-128">Frontline Workers in your government organization</span></span> |<span data-ttu-id="e9d46-129">Crea un set di criteri e applica tali impostazioni ai Frontline Worker dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e9d46-129">Creates a set of policies and applies those settings to Frontline Workers in your organization.</span></span>|

![Screenshot dei pacchetti di criteri per il settore sanitario](media/policy-packages-gov.png)

<span data-ttu-id="e9d46-131">A ogni singolo criterio viene assegnato il nome del pacchetto di criteri, in modo da poter identificare facilmente i criteri collegati a un determinato pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="e9d46-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="e9d46-132">Ad esempio, quando si assegna il pacchetto di criteri per i funzionari della sicurezza pubblica agli utenti dell'organizzazione, viene creato un criterio denominato PublicSafety_Officer per ogni criterio nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e9d46-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![Screenshot dei criteri nel pacchetto per gli operatori del settore sanitario](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="e9d46-134">Gestire i pacchetti di criteri</span><span class="sxs-lookup"><span data-stu-id="e9d46-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="e9d46-135">Visualizzare</span><span class="sxs-lookup"><span data-stu-id="e9d46-135">View</span></span>

<span data-ttu-id="e9d46-136">Visualizzare le impostazioni di ogni criterio in un pacchetto di criteri prima di assegnare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e9d46-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="e9d46-137">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams selezionare **Pacchetti di criteri**, selezionare il nome del pacchetto e quindi selezionare il nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="e9d46-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="e9d46-138">Stabilire se i valori predefiniti sono appropriati per la propria organizzazione o se è necessario personalizzarli in modo da renderli più restrittivi o permissivi.</span><span class="sxs-lookup"><span data-stu-id="e9d46-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="e9d46-139">Personalizzare</span><span class="sxs-lookup"><span data-stu-id="e9d46-139">Customize</span></span>

<span data-ttu-id="e9d46-140">Personalizzare le impostazioni dei criteri nel pacchetto di criteri come necessario per soddisfare le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e9d46-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="e9d46-141">Le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti ai quali è assegnato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e9d46-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="e9d46-142">Per modificare le impostazioni di un criterio in un pacchetto di criteri, nell'interfaccia di amministrazione di Microsoft Teams selezionare il pacchetto di criteri, selezionare il nome del criterio da modificare e quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e9d46-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="e9d46-143">È possibile modificare le impostazioni dei criteri in un pacchetto anche dopo l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="e9d46-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="e9d46-144">Per altre informazioni, vedere [Personalizzare i criteri in un pacchetto di criteri](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="e9d46-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="e9d46-145">Assegnare</span><span class="sxs-lookup"><span data-stu-id="e9d46-145">Assign</span></span>

<span data-ttu-id="e9d46-p106">Assegnare il pacchetto di criteri agli utenti. Se a un utente è assegnato un criterio e successivamente gli si assegna un criterio diverso, avrà priorità l'assegnazione più recente.</span><span class="sxs-lookup"><span data-stu-id="e9d46-p106">Assign the policy package to users. If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

> [!NOTE]
> <span data-ttu-id="e9d46-148">Ogni utente richiederà il componente aggiuntivo Advanced Communications per ricevere un'assegnazione di pacchetti di criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="e9d46-148">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="e9d46-149">Per altre informazioni, vedere [Componente aggiuntivo Comunicazioni avanzate per Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span><span class="sxs-lookup"><span data-stu-id="e9d46-149">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="e9d46-150">Assegnare un pacchetto di criteri a uno o più utenti</span><span class="sxs-lookup"><span data-stu-id="e9d46-150">Assign a policy package to one or several users</span></span>

<span data-ttu-id="e9d46-151">Per assegnare un pacchetto di criteri a uno o più utenti, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Pacchetti di criteri** e quindi selezionare **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="e9d46-151">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![Screenshot che mostra come assegnare un pacchetto di criteri nell'interfaccia di amministrazione](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="e9d46-153">Per altre informazioni, vedere [Assegnare un pacchetto di criteri](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="e9d46-153">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="e9d46-154">Se a un utente è assegnato un criterio e successivamente gli si assegna un criterio diverso, avrà priorità l'assegnazione più recente.</span><span class="sxs-lookup"><span data-stu-id="e9d46-154">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="e9d46-155">Assegnare un pacchetto di criteri a un gruppo</span><span class="sxs-lookup"><span data-stu-id="e9d46-155">Assign a policy package to a group</span></span>

<span data-ttu-id="e9d46-156">**Questa funzionalità è in anteprima privata**</span><span class="sxs-lookup"><span data-stu-id="e9d46-156">**This feature is in private preview**</span></span>

<span data-ttu-id="e9d46-157">L'assegnazione di pacchetti di criteri ai gruppi consente di assegnare più criteri a un gruppo di utenti, ad esempio un gruppo di sicurezza o una lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e9d46-157">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="e9d46-158">L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza.</span><span class="sxs-lookup"><span data-stu-id="e9d46-158">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="e9d46-159">Quando vengono aggiunti o rimossi membri da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="e9d46-159">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="e9d46-160">Questo metodo è consigliato per gruppi composti da un massimo di 50.000 utenti, ma funziona anche con i gruppi più grandi.</span><span class="sxs-lookup"><span data-stu-id="e9d46-160">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="e9d46-161">Per altre informazioni, vedere [Assegnare un pacchetto di criteri a un gruppo](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="e9d46-161">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="e9d46-162">Assegnare un pacchetto di criteri a un set di utenti di grandi dimensioni (batch)</span><span class="sxs-lookup"><span data-stu-id="e9d46-162">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="e9d46-163">Usare l'assegnazione pacchetti di criteri per batch per assegnare un pacchetto di criteri a grandi set di utenti per volta.</span><span class="sxs-lookup"><span data-stu-id="e9d46-163">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="e9d46-164">Per inviare un batch di utenti e il pacchetto di criteri da assegnare, usare il cmdlet [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="e9d46-164">You use the [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="e9d46-165">Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch.</span><span class="sxs-lookup"><span data-stu-id="e9d46-165">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="e9d46-166">Un batch può contenere fino a 5.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="e9d46-166">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="e9d46-167">È possibile specificare gli utenti in base all'ID oggetto, all'UPN, all'indirizzo SIP o all'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e9d46-167">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="e9d46-168">Per altre informazioni, vedere [Assegnare un pacchetto di criteri a un batch di utenti](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="e9d46-168">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e9d46-169">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e9d46-169">Related topics</span></span>

[<span data-ttu-id="e9d46-170">Gestire i pacchetti di criteri in Teams</span><span class="sxs-lookup"><span data-stu-id="e9d46-170">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="e9d46-171">Assegnare pacchetti di criteri a utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="e9d46-171">Assign policy packages to users and groups</span></span>](assign-policy-packages.md)
