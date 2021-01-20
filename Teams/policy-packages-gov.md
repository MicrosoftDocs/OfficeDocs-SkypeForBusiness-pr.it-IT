---
title: Pacchetti di criteri per le squadre per enti pubblici
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
description: Informazioni su come usare e gestire i pacchetti di criteri per le squadre per l'organizzazione pubblica.
ms.openlocfilehash: 2841fbf523f49c5784045cc6cf960e846b45aa9b
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909080"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="e2210-103">Pacchetti di criteri per le squadre per enti pubblici</span><span class="sxs-lookup"><span data-stu-id="e2210-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="e2210-104">I pacchetti di criteri non sono attualmente disponibili nelle distribuzioni governative GCC High o DoD di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e2210-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="e2210-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="e2210-105">Overview</span></span>

<span data-ttu-id="e2210-106">Un [pacchetto di criteri](manage-policy-packages.md) in Microsoft teams è una raccolta di criteri predefiniti e di impostazioni dei criteri che è possibile assegnare agli utenti che hanno ruoli simili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e2210-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="e2210-107">I pacchetti di criteri semplificano la gestione dei criteri e contribuiscono a garantirne la coerenza.</span><span class="sxs-lookup"><span data-stu-id="e2210-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="e2210-108">È possibile personalizzare le impostazioni dei criteri nel pacchetto in base alle esigenze degli utenti.</span><span class="sxs-lookup"><span data-stu-id="e2210-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="e2210-109">Quando si modificano le impostazioni dei criteri in un pacchetto di criteri, tutti gli utenti assegnati al pacchetto ottengono le impostazioni aggiornate.</span><span class="sxs-lookup"><span data-stu-id="e2210-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="e2210-110">Puoi gestire i pacchetti di criteri usando l'interfaccia di amministrazione di Microsoft teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e2210-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="e2210-111">I pacchetti di criteri predefiniscono i criteri per i seguenti elementi, a seconda del pacchetto:</span><span class="sxs-lookup"><span data-stu-id="e2210-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="e2210-112">Messaggistica</span><span class="sxs-lookup"><span data-stu-id="e2210-112">Messaging</span></span>
- <span data-ttu-id="e2210-113">Riunioni</span><span class="sxs-lookup"><span data-stu-id="e2210-113">Meetings</span></span>
- <span data-ttu-id="e2210-114">Chiamate</span><span class="sxs-lookup"><span data-stu-id="e2210-114">Calling</span></span>
- <span data-ttu-id="e2210-115">Configurazione dell'app</span><span class="sxs-lookup"><span data-stu-id="e2210-115">App setup</span></span>
- <span data-ttu-id="e2210-116">Eventi live</span><span class="sxs-lookup"><span data-stu-id="e2210-116">Live events</span></span>

<span data-ttu-id="e2210-117">I team attualmente includono i pacchetti di criteri seguenti per il governo.</span><span class="sxs-lookup"><span data-stu-id="e2210-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="e2210-118">Nome pacchetto nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e2210-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="e2210-119">Ideale per</span><span class="sxs-lookup"><span data-stu-id="e2210-119">Best used for</span></span>|<span data-ttu-id="e2210-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="e2210-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="e2210-121">Addetto alla sicurezza pubblica</span><span class="sxs-lookup"><span data-stu-id="e2210-121">Public safety officer</span></span>  |<span data-ttu-id="e2210-122">Responsabili della sicurezza pubblica nella propria organizzazione governativa</span><span class="sxs-lookup"><span data-stu-id="e2210-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="e2210-123">Crea un set di criteri e impostazioni dei criteri applicabili agli addetti alla sicurezza pubblica dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e2210-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="e2210-124">Frontline Manager</span><span class="sxs-lookup"><span data-stu-id="e2210-124">Frontline manager</span></span>  |<span data-ttu-id="e2210-125">Responsabili di Frontline nell'organizzazione governativa</span><span class="sxs-lookup"><span data-stu-id="e2210-125">Frontline Managers in your government organization</span></span> |<span data-ttu-id="e2210-126">Crea un set di criteri e applica tali impostazioni ai responsabili di Frontline nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e2210-126">Creates a set of policies and applies those settings to Frontline Managers in your organization.</span></span>|
|<span data-ttu-id="e2210-127">Lavoratore Frontline</span><span class="sxs-lookup"><span data-stu-id="e2210-127">Frontline worker</span></span>  |<span data-ttu-id="e2210-128">Lavoratori in prima linea nella tua organizzazione governativa</span><span class="sxs-lookup"><span data-stu-id="e2210-128">Frontline Workers in your government organization</span></span> |<span data-ttu-id="e2210-129">Crea un set di criteri e applica tali impostazioni agli operatori Frontline dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e2210-129">Creates a set of policies and applies those settings to Frontline Workers in your organization.</span></span>|

![Screenshot dei pacchetti di criteri sanitari](media/policy-packages-gov.png)

<span data-ttu-id="e2210-131">A ogni singolo criterio viene assegnato il nome del pacchetto di criteri in modo da poter identificare facilmente i criteri collegati a un pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="e2210-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="e2210-132">Ad esempio, quando si assegna il pacchetto di criteri per gli agenti di sicurezza pubblica agli utenti dell'organizzazione, viene creato un criterio denominato PublicSafety_Officer per ogni criterio nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e2210-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![Screenshot dei criteri nel pacchetto Worker clinico per l'assistenza sanitaria](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="e2210-134">Gestire i pacchetti di criteri</span><span class="sxs-lookup"><span data-stu-id="e2210-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="e2210-135">Visualizzare</span><span class="sxs-lookup"><span data-stu-id="e2210-135">View</span></span>

<span data-ttu-id="e2210-136">Visualizzare le impostazioni di ogni criterio in un pacchetto di criteri prima di assegnare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e2210-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="e2210-137">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams selezionare **Pacchetti di criteri**, selezionare il nome del pacchetto e quindi selezionare il nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="e2210-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="e2210-138">Stabilire se i valori predefiniti sono appropriati per la propria organizzazione o se è necessario personalizzarli in modo da renderli più restrittivi o permissivi.</span><span class="sxs-lookup"><span data-stu-id="e2210-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="e2210-139">Personalizzare</span><span class="sxs-lookup"><span data-stu-id="e2210-139">Customize</span></span>

<span data-ttu-id="e2210-140">Personalizzare le impostazioni dei criteri nel pacchetto di criteri come necessario per soddisfare le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="e2210-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="e2210-141">Le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti ai quali è assegnato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="e2210-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="e2210-142">Per modificare le impostazioni di un criterio in un pacchetto di criteri, nell'interfaccia di amministrazione di Microsoft Teams selezionare il pacchetto di criteri, selezionare il nome del criterio da modificare e quindi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e2210-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="e2210-143">È possibile modificare le impostazioni dei criteri in un pacchetto anche dopo l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="e2210-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="e2210-144">Per altre informazioni, vedere [Personalizzare i criteri in un pacchetto di criteri](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="e2210-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="e2210-145">Assegnare</span><span class="sxs-lookup"><span data-stu-id="e2210-145">Assign</span></span>

<span data-ttu-id="e2210-146">Assegnare il pacchetto di criteri agli utenti.</span><span class="sxs-lookup"><span data-stu-id="e2210-146">Assign the policy package to users.</span></span> <span data-ttu-id="e2210-147">Se a un utente è assegnato un criterio e successivamente gli si assegna un criterio diverso, avrà priorità l'assegnazione più recente.</span><span class="sxs-lookup"><span data-stu-id="e2210-147">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="e2210-148">Assegnare un pacchetto di criteri a uno o più utenti</span><span class="sxs-lookup"><span data-stu-id="e2210-148">Assign a policy package to one or several users</span></span>

<span data-ttu-id="e2210-149">Per assegnare un pacchetto di criteri a uno o più utenti, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Pacchetti di criteri** e quindi selezionare **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="e2210-149">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![Screenshot che mostra come assegnare un pacchetto di criteri nell'interfaccia di amministrazione](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="e2210-151">Per altre informazioni, vedere [Assegnare un pacchetto di criteri](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="e2210-151">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="e2210-152">Se a un utente è assegnato un criterio e successivamente gli si assegna un criterio diverso, avrà priorità l'assegnazione più recente.</span><span class="sxs-lookup"><span data-stu-id="e2210-152">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="e2210-153">Assegnare un pacchetto di criteri a un gruppo</span><span class="sxs-lookup"><span data-stu-id="e2210-153">Assign a policy package to a group</span></span>

<span data-ttu-id="e2210-154">**Questa funzionalità è in anteprima privata**</span><span class="sxs-lookup"><span data-stu-id="e2210-154">**This feature is in private preview**</span></span>

<span data-ttu-id="e2210-155">L'assegnazione di pacchetti di criteri ai gruppi consente di assegnare più criteri a un gruppo di utenti, ad esempio un gruppo di sicurezza o una lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e2210-155">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="e2210-156">L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza.</span><span class="sxs-lookup"><span data-stu-id="e2210-156">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="e2210-157">Quando vengono aggiunti o rimossi membri da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="e2210-157">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="e2210-158">Questo metodo è consigliato per gruppi composti da un massimo di 50.000 utenti, ma funziona anche con i gruppi più grandi.</span><span class="sxs-lookup"><span data-stu-id="e2210-158">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="e2210-159">Per altre informazioni, vedere [Assegnare un pacchetto di criteri a un gruppo](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="e2210-159">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="e2210-160">Assegnare un pacchetto di criteri a un set di utenti di grandi dimensioni (batch)</span><span class="sxs-lookup"><span data-stu-id="e2210-160">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="e2210-161">Usare l'assegnazione pacchetti di criteri per batch per assegnare un pacchetto di criteri a grandi set di utenti per volta.</span><span class="sxs-lookup"><span data-stu-id="e2210-161">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="e2210-162">Per inviare un batch di utenti e il pacchetto di criteri da assegnare, usare il cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="e2210-162">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="e2210-163">Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch.</span><span class="sxs-lookup"><span data-stu-id="e2210-163">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="e2210-164">Un batch può contenere fino a 5.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="e2210-164">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="e2210-165">È possibile specificare gli utenti in base all'ID oggetto, all'UPN, all'indirizzo SIP o all'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e2210-165">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="e2210-166">Per altre informazioni, vedere [Assegnare un pacchetto di criteri a un batch di utenti](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="e2210-166">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e2210-167">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e2210-167">Related topics</span></span>

[<span data-ttu-id="e2210-168">Gestire i pacchetti di criteri in Teams</span><span class="sxs-lookup"><span data-stu-id="e2210-168">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="e2210-169">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="e2210-169">Assign policies to your users in Teams</span></span>](assign-policies.md) 
