---
title: Pacchetti di criteri di Teams per il settore sanitario
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
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Informazioni su come usare e gestire i pacchetti di criteri di Teams per l'organizzazione nel settore sanitario.
ms.openlocfilehash: 19c0fee14138b248c4e25d88a9103df4a5618598
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2021
ms.locfileid: "52796810"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="9ba87-103">Pacchetti di criteri di Teams per il settore sanitario</span><span class="sxs-lookup"><span data-stu-id="9ba87-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="9ba87-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="9ba87-104">Overview</span></span>

<span data-ttu-id="9ba87-105">Un [Pacchetto di criteri](manage-policy-packages.md) in Microsoft Teams è una raccolta di criteri e impostazioni predefiniti da assegnare agli utenti con ruoli simili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9ba87-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="9ba87-106">I pacchetti di criteri semplificano la gestione dei criteri e contribuiscono a garantirne la coerenza.</span><span class="sxs-lookup"><span data-stu-id="9ba87-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="9ba87-107">È possibile personalizzare le impostazioni dei criteri del pacchetto in base alle esigenze degli utenti.</span><span class="sxs-lookup"><span data-stu-id="9ba87-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="9ba87-108">Quando si modificano le impostazioni dei criteri in un pacchetto di criteri, tutti gli utenti assegnati al pacchetto ottengono le impostazioni aggiornate.</span><span class="sxs-lookup"><span data-stu-id="9ba87-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="9ba87-109">È possibile gestire i pacchetti dei criteri tramite l'interfaccia di amministrazione di Microsoft Teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9ba87-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="9ba87-110">I pacchetti di criteri predefiniscono i criteri per gli elementi seguenti, a seconda del pacchetto:</span><span class="sxs-lookup"><span data-stu-id="9ba87-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="9ba87-111">Messaggistica</span><span class="sxs-lookup"><span data-stu-id="9ba87-111">Messaging</span></span>
- <span data-ttu-id="9ba87-112">Riunioni</span><span class="sxs-lookup"><span data-stu-id="9ba87-112">Meetings</span></span>
- <span data-ttu-id="9ba87-113">Chiamate</span><span class="sxs-lookup"><span data-stu-id="9ba87-113">Calling</span></span>
- <span data-ttu-id="9ba87-114">Configurazione delle app</span><span class="sxs-lookup"><span data-stu-id="9ba87-114">App setup</span></span>
- <span data-ttu-id="9ba87-115">Eventi live</span><span class="sxs-lookup"><span data-stu-id="9ba87-115">Live events</span></span>

<span data-ttu-id="9ba87-116">Teams attualmente include i pacchetti di criteri per il settore sanitario seguenti.</span><span class="sxs-lookup"><span data-stu-id="9ba87-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="9ba87-117">Nome del pacchetto nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9ba87-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="9ba87-118">Ideale per</span><span class="sxs-lookup"><span data-stu-id="9ba87-118">Best used for</span></span>|<span data-ttu-id="9ba87-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="9ba87-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="9ba87-120">Operatore sanitario</span><span class="sxs-lookup"><span data-stu-id="9ba87-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="9ba87-121">Operatori sanitari in organizzazioni nel settore sanitario</span><span class="sxs-lookup"><span data-stu-id="9ba87-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="9ba87-122">Creare un set e impostazioni di criteri che forniscano agli operatori sanitari, ad esempio infermieri, medici e operatori sociali accesso completo alle chat, alle chiamate, alla gestione dei turni e alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="9ba87-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="9ba87-123">Operatore dell'informazione sanitaria</span><span class="sxs-lookup"><span data-stu-id="9ba87-123">Healthcare information worker</span></span>  |<span data-ttu-id="9ba87-124">Operatori dell'informazione in organizzazioni del settore sanitario</span><span class="sxs-lookup"><span data-stu-id="9ba87-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="9ba87-125">Crea un set di criteri e impostazioni di criteri che forniscono agli operatori dell'informazione, ad esempio personale in ambito IT e finanziario, responsabili della conformità, accesso completo alle chat, alle chiamate e alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="9ba87-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="9ba87-126">Sale per i pazienti nell'organizzazione sanitaria</span><span class="sxs-lookup"><span data-stu-id="9ba87-126">Healthcare patient room</span></span>  |<span data-ttu-id="9ba87-127">Dispositivi per le sale dei pazienti</span><span class="sxs-lookup"><span data-stu-id="9ba87-127">Patient room devices</span></span>|<span data-ttu-id="9ba87-128">Crea un set di criteri e impostazioni di criteri da applicare alle sale dei pazienti nell'organizzazione sanitaria.</span><span class="sxs-lookup"><span data-stu-id="9ba87-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![Screenshot dei pacchetti di criteri per il settore sanitario](media/policy-packages-healthcare.png)

<span data-ttu-id="9ba87-130">A ogni singolo criterio viene assegnato il nome del pacchetto di criteri, in modo da poter identificare facilmente i criteri collegati a un determinato pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="9ba87-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="9ba87-131">Ad esempio, quando si assegna il pacchetto di criteri per gli operatori sanitari nell'organizzazione, viene creato un criterio denominato Healthcare_ClinicalWorker per ogni criterio presente nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="9ba87-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![Screenshot dei criteri nel pacchetto per gli operatori del settore sanitario](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="9ba87-133">Introduzione ai pacchetti di criteri</span><span class="sxs-lookup"><span data-stu-id="9ba87-133">Get started with policy packages</span></span>

<span data-ttu-id="9ba87-134">Per un'introduzione ai pacchetti di criteri del settore sanitario, nell'hub di onboarding dell'interfaccia di amministrazione Microsoft selezionare **Assistenza sanitaria** poi **Assegna le impostazioni dei criteri in base al ruolo**.</span><span class="sxs-lookup"><span data-stu-id="9ba87-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare**, and then select **Assign policy settings by role**.</span></span> <span data-ttu-id="9ba87-135">Quando si è pronti per iniziare, decidere a quali pacchetti di criteri si desidera assegnare gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9ba87-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="9ba87-136">Selezionare **Visualizza dettagli dei criteri** per altre informazioni sui criteri specifici in un pacchetto e sulle relative impostazioni.</span><span class="sxs-lookup"><span data-stu-id="9ba87-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="9ba87-137">Tali impostazioni [possono essere personalizzate](manage-policy-packages.md#customize-policies-in-a-policy-package) dopo l'assegnazione nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="9ba87-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="9ba87-138">Scegliere uno o più pacchetti da assegnare poi fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9ba87-138">Choose one or multiple packages to assign and then click **Next**.</span></span> <span data-ttu-id="9ba87-139">È possibile cercare e aggiungere utenti al pacchetto di criteri in base al loro ruolo.</span><span class="sxs-lookup"><span data-stu-id="9ba87-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="9ba87-140">Non è possibile assegnare un utente a più pacchetti di criteri contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="9ba87-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="9ba87-141">Dopo aver aggiunto gli utenti al pacchetto di criteri appropriato, fare clic **Fine** per salvare le selezioni.</span><span class="sxs-lookup"><span data-stu-id="9ba87-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="9ba87-142">È possibile continuare a personalizzare e gestire i pacchetti dei criteri nell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9ba87-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="9ba87-143">Gestire i pacchetti di criteri</span><span class="sxs-lookup"><span data-stu-id="9ba87-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="9ba87-144">Visualizzare</span><span class="sxs-lookup"><span data-stu-id="9ba87-144">View</span></span>

<span data-ttu-id="9ba87-145">Visualizzare le impostazioni di ogni criterio in un pacchetto di criteri prima di assegnare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="9ba87-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="9ba87-146">Nel riquadro di spostamento a sinistra dell'interfaccia di amministrazione di Microsoft Teams passare a **Pacchetti di criteri**, selezionare il nome del pacchetto poi selezionare il nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="9ba87-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="9ba87-147">Stabilire se i valori predefiniti sono appropriati per la propria organizzazione o se è necessario personalizzarli in modo da renderli più restrittivi o permissivi.</span><span class="sxs-lookup"><span data-stu-id="9ba87-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="9ba87-148">Personalizzare</span><span class="sxs-lookup"><span data-stu-id="9ba87-148">Customize</span></span>

<span data-ttu-id="9ba87-149">Personalizzare le impostazioni dei criteri nel pacchetto di criteri come necessario per soddisfare le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9ba87-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="9ba87-150">Le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti ai quali è assegnato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="9ba87-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="9ba87-151">Per modificare le impostazioni di un criterio in un pacchetto di criteri, nel riquadro di spostamento a sinistra nell'interfaccia di amministrazione di Microsoft Teams passare a **Pacchetto di criteri** e selezionare il nome del criterio che si desidera modificare poi selezionare **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="9ba87-151">To edit the settings of a policy in a policy package, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="9ba87-152">È possibile modificare le impostazioni dei criteri in un pacchetto anche dopo l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="9ba87-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="9ba87-153">Per altre informazioni, vedere [Personalizzare i criteri in un pacchetto di criteri](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="9ba87-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span>

### <a name="assign"></a><span data-ttu-id="9ba87-154">Assegnare</span><span class="sxs-lookup"><span data-stu-id="9ba87-154">Assign</span></span>

<span data-ttu-id="9ba87-p110">Assegnare il pacchetto di criteri agli utenti. Se a un utente è assegnato un criterio e successivamente gli si assegna un criterio diverso, avrà priorità l'assegnazione più recente.</span><span class="sxs-lookup"><span data-stu-id="9ba87-p110">Assign the policy package to users. If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

> [!NOTE]
> <span data-ttu-id="9ba87-157">Ogni utente richiederà il componente aggiuntivo Advanced Communications per ricevere un'assegnazione di pacchetti di criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="9ba87-157">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="9ba87-158">Per altre informazioni, vedere [Componente aggiuntivo Comunicazioni avanzate per Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span><span class="sxs-lookup"><span data-stu-id="9ba87-158">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="9ba87-159">Assegnare un pacchetto di criteri a uno o più utenti</span><span class="sxs-lookup"><span data-stu-id="9ba87-159">Assign a policy package to one or several users</span></span>

<span data-ttu-id="9ba87-160">Per assegnare un pacchetto di criteri a uno o più utenti, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Pacchetti di criteri** e quindi selezionare **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="9ba87-160">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![Screenshot che mostra come assegnare un pacchetto di criteri nell'interfaccia di amministrazione](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="9ba87-162">Per altre informazioni, vedere [Assegnare un pacchetto di criteri](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="9ba87-162">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="9ba87-163">Se a un utente è assegnato un criterio e successivamente gli si assegna un criterio diverso, avrà priorità l'assegnazione più recente.</span><span class="sxs-lookup"><span data-stu-id="9ba87-163">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="9ba87-164">Assegnare un pacchetto di criteri a un gruppo</span><span class="sxs-lookup"><span data-stu-id="9ba87-164">Assign a policy package to a group</span></span>

<span data-ttu-id="9ba87-165">**Questa funzionalità è in anteprima privata**</span><span class="sxs-lookup"><span data-stu-id="9ba87-165">**This feature is in private preview**</span></span>

<span data-ttu-id="9ba87-166">L'assegnazione di pacchetti di criteri ai gruppi consente di assegnare più criteri a un gruppo di utenti, ad esempio un gruppo di sicurezza o una lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9ba87-166">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="9ba87-167">L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza.</span><span class="sxs-lookup"><span data-stu-id="9ba87-167">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="9ba87-168">Quando vengono aggiunti o rimossi membri da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="9ba87-168">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="9ba87-169">Questo metodo è consigliato per gruppi composti da un massimo di 50.000 utenti, ma funziona anche con i gruppi più grandi.</span><span class="sxs-lookup"><span data-stu-id="9ba87-169">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="9ba87-170">Per altre informazioni, vedere [Assegnare un pacchetto di criteri a un gruppo](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="9ba87-170">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="9ba87-171">Assegnare un pacchetto di criteri a un set di utenti di grandi dimensioni (batch)</span><span class="sxs-lookup"><span data-stu-id="9ba87-171">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="9ba87-172">Usare l'assegnazione pacchetti di criteri per batch per assegnare un pacchetto di criteri a grandi set di utenti per volta.</span><span class="sxs-lookup"><span data-stu-id="9ba87-172">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="9ba87-173">Per inviare un batch di utenti e il pacchetto di criteri da assegnare, usare il cmdlet [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="9ba87-173">You use the [New-CsBatchPolicyPackageAssignmentOperation](/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="9ba87-174">Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch.</span><span class="sxs-lookup"><span data-stu-id="9ba87-174">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="9ba87-175">Un batch può contenere fino a 5.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="9ba87-175">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="9ba87-176">È possibile specificare gli utenti in base all'ID oggetto, all'UPN, all'indirizzo SIP o all'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="9ba87-176">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="9ba87-177">Per altre informazioni, vedere [Assegnare un pacchetto di criteri a un batch di utenti](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="9ba87-177">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="9ba87-178">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9ba87-178">Related topics</span></span>

[<span data-ttu-id="9ba87-179">Gestire i pacchetti di criteri in Teams</span><span class="sxs-lookup"><span data-stu-id="9ba87-179">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="9ba87-180">Assegnare pacchetti di criteri a utenti e gruppi</span><span class="sxs-lookup"><span data-stu-id="9ba87-180">Assign policy packages to users and groups</span></span>](assign-policy-packages.md)
