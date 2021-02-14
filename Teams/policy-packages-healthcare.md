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
description: Informazioni su come usare e gestire i pacchetti di criteri di Teams per l'organizzazione sanitaria.
ms.openlocfilehash: af6f5923d5c97fc03c77585ba94292264aacc027
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812856"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="98837-103">Pacchetti di criteri di Teams per il settore sanitario</span><span class="sxs-lookup"><span data-stu-id="98837-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="98837-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="98837-104">Overview</span></span>

<span data-ttu-id="98837-105">Un [pacchetto di](manage-policy-packages.md) criteri in Microsoft Teams è una raccolta di criteri e impostazioni dei criteri predefiniti che è possibile assegnare agli utenti con ruoli simili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="98837-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="98837-106">I pacchetti di criteri semplificano la gestione dei criteri e contribuiscono a garantirne la coerenza.</span><span class="sxs-lookup"><span data-stu-id="98837-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="98837-107">È possibile personalizzare le impostazioni dei criteri nel pacchetto in base alle esigenze degli utenti.</span><span class="sxs-lookup"><span data-stu-id="98837-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="98837-108">Quando si modificano le impostazioni dei criteri in un pacchetto di criteri, tutti gli utenti assegnati al pacchetto ottengono le impostazioni aggiornate.</span><span class="sxs-lookup"><span data-stu-id="98837-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="98837-109">Puoi gestire i pacchetti dei criteri utilizzando l'interfaccia di amministrazione di Microsoft Teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="98837-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="98837-110">Criteri predefiniti per i pacchetti di criteri per i seguenti, a seconda del pacchetto:</span><span class="sxs-lookup"><span data-stu-id="98837-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="98837-111">Messaggistica</span><span class="sxs-lookup"><span data-stu-id="98837-111">Messaging</span></span>
- <span data-ttu-id="98837-112">Riunioni</span><span class="sxs-lookup"><span data-stu-id="98837-112">Meetings</span></span>
- <span data-ttu-id="98837-113">Chiamate</span><span class="sxs-lookup"><span data-stu-id="98837-113">Calling</span></span>
- <span data-ttu-id="98837-114">Configurazione dell'app</span><span class="sxs-lookup"><span data-stu-id="98837-114">App setup</span></span>
- <span data-ttu-id="98837-115">Eventi live</span><span class="sxs-lookup"><span data-stu-id="98837-115">Live events</span></span>

<span data-ttu-id="98837-116">Teams attualmente include i pacchetti di criteri sanitari seguenti.</span><span class="sxs-lookup"><span data-stu-id="98837-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="98837-117">Nome del pacchetto nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="98837-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="98837-118">Ideale per</span><span class="sxs-lookup"><span data-stu-id="98837-118">Best used for</span></span>|<span data-ttu-id="98837-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="98837-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="98837-120">Operatore medico</span><span class="sxs-lookup"><span data-stu-id="98837-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="98837-121">Operatori clinici nell'organizzazione sanitaria</span><span class="sxs-lookup"><span data-stu-id="98837-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="98837-122">Crea un set di criteri e impostazioni dei criteri che conferiranno a operatori clinici come infermieri specializzati, infermieri con addebito, medici e social worker l'accesso completo a chat, chiamate, gestione dei turni e riunioni.</span><span class="sxs-lookup"><span data-stu-id="98837-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="98837-123">Information Worker sanitario</span><span class="sxs-lookup"><span data-stu-id="98837-123">Healthcare information worker</span></span>  |<span data-ttu-id="98837-124">Information worker nell'organizzazione sanitaria</span><span class="sxs-lookup"><span data-stu-id="98837-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="98837-125">Crea un set di criteri e impostazioni dei criteri che forniscono a information worker come personale IT, personale informatico, personale finanziario e responsabili della conformità, accesso completo a chat, chiamate e riunioni.</span><span class="sxs-lookup"><span data-stu-id="98837-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="98837-126">Sala pazienti sanitaria</span><span class="sxs-lookup"><span data-stu-id="98837-126">Healthcare patient room</span></span>  |<span data-ttu-id="98837-127">Dispositivi per la sala pazienti</span><span class="sxs-lookup"><span data-stu-id="98837-127">Patient room devices</span></span>|<span data-ttu-id="98837-128">Crea un set di criteri e impostazioni dei criteri che si applicano alle sale pazienti dell'organizzazione sanitaria.</span><span class="sxs-lookup"><span data-stu-id="98837-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![Screenshot dei pacchetti di criteri sanitari](media/policy-packages-healthcare.png)

<span data-ttu-id="98837-130">A ogni singolo criterio viene assegnato il nome del pacchetto di criteri, in modo da poter identificare facilmente i criteri collegati a un pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="98837-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="98837-131">Ad esempio, quando si assegna il pacchetto di criteri per operatori clinici sanitari a un medico dell'organizzazione, viene creato un criterio denominato Healthcare_ClinicalWorker per ogni criterio nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="98837-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![Screenshot dei criteri nel pacchetto di operatori clinici sanitari](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="98837-133">Introduzione ai pacchetti di criteri</span><span class="sxs-lookup"><span data-stu-id="98837-133">Get started with policy packages</span></span>

<span data-ttu-id="98837-134">Per iniziare a usare i pacchetti di criteri sanitari, nell'hub di onboarding dell'interfaccia di amministrazione Microsoft selezionare **Sanità** e quindi Assegnare le impostazioni dei criteri in base **al ruolo.**</span><span class="sxs-lookup"><span data-stu-id="98837-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare**, and then select **Assign policy settings by role**.</span></span> <span data-ttu-id="98837-135">Quando sei pronto per iniziare, decidi a quali pacchetti di criteri vuoi assegnare i singoli utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="98837-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="98837-136">Selezionare **Visualizza dettagli sui criteri** per altre informazioni sui criteri specifici in un pacchetto e sulle relative impostazioni.</span><span class="sxs-lookup"><span data-stu-id="98837-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="98837-137">Possono [essere personalizzate dopo l'attività](manage-policy-packages.md#customize-policies-in-a-policy-package) nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="98837-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="98837-138">Scegli uno o più pacchetti da assegnare e quindi fai clic su **Avanti.**</span><span class="sxs-lookup"><span data-stu-id="98837-138">Choose one or multiple packages to assign and then click **Next**.</span></span> <span data-ttu-id="98837-139">È possibile cercare e aggiungere persone al pacchetto di criteri più adatto per il loro ruolo.</span><span class="sxs-lookup"><span data-stu-id="98837-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="98837-140">Non è possibile assegnare una persona a più di un pacchetto di criteri contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="98837-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="98837-141">Dopo aver aggiunto persone al pacchetto di criteri giusto, **completare** le selezioni.</span><span class="sxs-lookup"><span data-stu-id="98837-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="98837-142">Puoi continuare a personalizzare e gestire i pacchetti di criteri nell'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="98837-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="98837-143">Gestire i pacchetti di criteri</span><span class="sxs-lookup"><span data-stu-id="98837-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="98837-144">Visualizzare</span><span class="sxs-lookup"><span data-stu-id="98837-144">View</span></span>

<span data-ttu-id="98837-145">Visualizzare le impostazioni di ogni criterio in un pacchetto di criteri prima di assegnare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="98837-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="98837-146">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai a Pacchetti **criteri,** seleziona il nome del pacchetto e quindi seleziona il nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="98837-146">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="98837-147">Stabilire se i valori predefiniti sono appropriati per la propria organizzazione o se è necessario personalizzarli in modo da renderli più restrittivi o permissivi.</span><span class="sxs-lookup"><span data-stu-id="98837-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="98837-148">Personalizzare</span><span class="sxs-lookup"><span data-stu-id="98837-148">Customize</span></span>

<span data-ttu-id="98837-149">Personalizzare le impostazioni dei criteri nel pacchetto di criteri come necessario per soddisfare le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="98837-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="98837-150">Le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti ai quali è assegnato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="98837-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="98837-151">Per modificare le impostazioni di un criterio in un pacchetto di criteri, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams vai a Pacchetti **criteri,** seleziona il pacchetto di criteri, seleziona il nome del criterio che vuoi modificare e quindi seleziona **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="98837-151">To edit the settings of a policy in a policy package, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="98837-152">È possibile modificare le impostazioni dei criteri in un pacchetto anche dopo l'assegnazione.</span><span class="sxs-lookup"><span data-stu-id="98837-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="98837-153">Per altre informazioni, vedere [Personalizzare i criteri in un pacchetto di criteri](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="98837-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span>

### <a name="assign"></a><span data-ttu-id="98837-154">Assegnare</span><span class="sxs-lookup"><span data-stu-id="98837-154">Assign</span></span>

<span data-ttu-id="98837-155">Assegnare il pacchetto di criteri agli utenti.</span><span class="sxs-lookup"><span data-stu-id="98837-155">Assign the policy package to users.</span></span> <span data-ttu-id="98837-156">Se a un utente è assegnato un criterio e successivamente gli si assegna un criterio diverso, avrà priorità l'assegnazione più recente.</span><span class="sxs-lookup"><span data-stu-id="98837-156">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-one-or-several-users"></a><span data-ttu-id="98837-157">Assegnare un pacchetto di criteri a uno o più utenti</span><span class="sxs-lookup"><span data-stu-id="98837-157">Assign a policy package to one or several users</span></span>

<span data-ttu-id="98837-158">Per assegnare un pacchetto di criteri a uno o più utenti, nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Pacchetti di criteri** e quindi selezionare **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="98837-158">To assign a policy package to one or multiple users, in the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select **Manage users**.</span></span>  

![Screenshot che mostra come assegnare un pacchetto di criteri nell'interfaccia di amministrazione](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="98837-160">Per altre informazioni, vedere [Assegnare un pacchetto di criteri](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="98837-160">To learn more, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

<span data-ttu-id="98837-161">Se a un utente è assegnato un criterio e successivamente gli si assegna un criterio diverso, avrà priorità l'assegnazione più recente.</span><span class="sxs-lookup"><span data-stu-id="98837-161">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

#### <a name="assign-a-policy-package-to-a-group"></a><span data-ttu-id="98837-162">Assegnare un pacchetto di criteri a un gruppo</span><span class="sxs-lookup"><span data-stu-id="98837-162">Assign a policy package to a group</span></span>

<span data-ttu-id="98837-163">**Questa funzionalità è in anteprima privata**</span><span class="sxs-lookup"><span data-stu-id="98837-163">**This feature is in private preview**</span></span>

<span data-ttu-id="98837-164">L'assegnazione di pacchetti di criteri ai gruppi consente di assegnare più criteri a un gruppo di utenti, ad esempio un gruppo di sicurezza o una lista di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="98837-164">Policy package assignment to groups let you assign multiple policies to a group of users, such as a security group or distribution list.</span></span> <span data-ttu-id="98837-165">L'assegnazione dei criteri viene propagata ai membri del gruppo in base alle regole di precedenza.</span><span class="sxs-lookup"><span data-stu-id="98837-165">The policy assignment is propagated to members of the group according to precedence rules.</span></span> <span data-ttu-id="98837-166">Quando vengono aggiunti o rimossi membri da un gruppo, le assegnazioni dei criteri ereditate vengono aggiornate di conseguenza.</span><span class="sxs-lookup"><span data-stu-id="98837-166">As members are added to or removed from a group, their inherited policy assignments are updated accordingly.</span></span> <span data-ttu-id="98837-167">Questo metodo è consigliato per gruppi composti da un massimo di 50.000 utenti, ma funziona anche con i gruppi più grandi.</span><span class="sxs-lookup"><span data-stu-id="98837-167">This method is recommended for groups of up to 50,000 users but will also work with larger groups.</span></span>

<span data-ttu-id="98837-168">Per altre informazioni, vedere [Assegnare un pacchetto di criteri a un gruppo](assign-policies.md#assign-a-policy-package-to-a-group).</span><span class="sxs-lookup"><span data-stu-id="98837-168">To learn more, see [Assign a policy package to a group](assign-policies.md#assign-a-policy-package-to-a-group).</span></span>

#### <a name="assign-a-policy-package-to-a-large-set-batch-of-users"></a><span data-ttu-id="98837-169">Assegnare un pacchetto di criteri a un set di utenti di grandi dimensioni (batch)</span><span class="sxs-lookup"><span data-stu-id="98837-169">Assign a policy package to a large set (batch) of users</span></span>

<span data-ttu-id="98837-170">Usare l'assegnazione pacchetti di criteri per batch per assegnare un pacchetto di criteri a grandi set di utenti per volta.</span><span class="sxs-lookup"><span data-stu-id="98837-170">Use batch policy package assignment to assign a policy package to large sets of users at a time.</span></span> <span data-ttu-id="98837-171">Per inviare un batch di utenti e il pacchetto di criteri da assegnare, usare il cmdlet [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation).</span><span class="sxs-lookup"><span data-stu-id="98837-171">You use the [New-CsBatchPolicyPackageAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) cmdlet to submit a batch of users and the policy package that you want to assign.</span></span> <span data-ttu-id="98837-172">Le assegnazioni vengono elaborate come operazione in background e viene generato un ID operazione per ogni batch.</span><span class="sxs-lookup"><span data-stu-id="98837-172">The assignments are processed as a background operation and an operation ID is generated for each batch.</span></span>

<span data-ttu-id="98837-173">Un batch può contenere fino a 5.000 utenti.</span><span class="sxs-lookup"><span data-stu-id="98837-173">A batch can contain up to 5,000 users.</span></span> <span data-ttu-id="98837-174">È possibile specificare gli utenti in base all'ID oggetto, all'UPN, all'indirizzo SIP o all'indirizzo di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="98837-174">You can specify users by their object Id, UPN, SIP address, or email address.</span></span> <span data-ttu-id="98837-175">Per altre informazioni, vedere [Assegnare un pacchetto di criteri a un batch di utenti](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="98837-175">To learn more, see [Assign a policy package to a batch of users](assign-policies.md#assign-a-policy-package-to-a-batch-of-users).</span></span>

## <a name="related-topics"></a><span data-ttu-id="98837-176">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="98837-176">Related topics</span></span>

[<span data-ttu-id="98837-177">Gestire i pacchetti di criteri in Teams</span><span class="sxs-lookup"><span data-stu-id="98837-177">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="98837-178">Assegnare i criteri agli utenti in Teams</span><span class="sxs-lookup"><span data-stu-id="98837-178">Assign policies to your users in Teams</span></span>](assign-policies.md)
