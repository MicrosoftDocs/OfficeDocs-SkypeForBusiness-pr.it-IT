---
title: Pacchetti di criteri team per l'assistenza sanitaria
author: lanachin
ms.author: v-lanac
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
description: Informazioni su come usare e gestire i pacchetti di criteri team per l'organizzazione sanitaria.
ms.openlocfilehash: 6c14cc82a7e2e16780eb50c04064955aad4e4eb7
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790648"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="c4a37-103">Pacchetti di criteri team per l'assistenza sanitaria</span><span class="sxs-lookup"><span data-stu-id="c4a37-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="c4a37-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="c4a37-104">Overview</span></span>

<span data-ttu-id="c4a37-105">Un [pacchetto di criteri](manage-policy-packages.md) in Microsoft teams è una raccolta di criteri predefiniti e di impostazioni dei criteri che è possibile assegnare agli utenti che hanno ruoli simili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c4a37-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="c4a37-106">I pacchetti di criteri semplificano la gestione dei criteri e contribuiscono a garantirne la coerenza.</span><span class="sxs-lookup"><span data-stu-id="c4a37-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="c4a37-107">È possibile personalizzare le impostazioni dei criteri nel pacchetto in base alle esigenze degli utenti.</span><span class="sxs-lookup"><span data-stu-id="c4a37-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="c4a37-108">Quando si modificano le impostazioni dei criteri in un pacchetto di criteri, tutti gli utenti assegnati al pacchetto ottengono le impostazioni aggiornate.</span><span class="sxs-lookup"><span data-stu-id="c4a37-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="c4a37-109">Puoi gestire i pacchetti di criteri usando l'interfaccia di amministrazione di Microsoft teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c4a37-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Ht2o]

<span data-ttu-id="c4a37-110">I pacchetti di criteri predefiniscono i criteri per i seguenti elementi, a seconda del pacchetto:</span><span class="sxs-lookup"><span data-stu-id="c4a37-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="c4a37-111">Messaggistica</span><span class="sxs-lookup"><span data-stu-id="c4a37-111">Messaging</span></span>
- <span data-ttu-id="c4a37-112">Riunioni</span><span class="sxs-lookup"><span data-stu-id="c4a37-112">Meetings</span></span>
- <span data-ttu-id="c4a37-113">Chiamate</span><span class="sxs-lookup"><span data-stu-id="c4a37-113">Calling</span></span>
- <span data-ttu-id="c4a37-114">Configurazione dell'app</span><span class="sxs-lookup"><span data-stu-id="c4a37-114">App setup</span></span>
- <span data-ttu-id="c4a37-115">Eventi live</span><span class="sxs-lookup"><span data-stu-id="c4a37-115">Live events</span></span>

<span data-ttu-id="c4a37-116">I team attualmente includono i seguenti pacchetti di criteri sanitari.</span><span class="sxs-lookup"><span data-stu-id="c4a37-116">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="c4a37-117">Nome pacchetto nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c4a37-117">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="c4a37-118">Ideale per</span><span class="sxs-lookup"><span data-stu-id="c4a37-118">Best used for</span></span>|<span data-ttu-id="c4a37-119">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c4a37-119">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="c4a37-120">Lavoratore clinico sanitario</span><span class="sxs-lookup"><span data-stu-id="c4a37-120">Healthcare clinical worker</span></span>  |<span data-ttu-id="c4a37-121">Operatori clinici nell'organizzazione sanitaria</span><span class="sxs-lookup"><span data-stu-id="c4a37-121">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="c4a37-122">Crea un set di criteri e impostazioni dei criteri che conferiscono agli operatori clinici, ad esempio infermieri registrati, addebiti infermieri, medici e assistenti sociali, l'accesso completo alla chat, alle chiamate, alla gestione del turno e alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="c4a37-122">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="c4a37-123">Information Worker sanitari</span><span class="sxs-lookup"><span data-stu-id="c4a37-123">Healthcare information worker</span></span>  |<span data-ttu-id="c4a37-124">Information Worker nell'organizzazione sanitaria</span><span class="sxs-lookup"><span data-stu-id="c4a37-124">Information workers in your healthcare organization</span></span> |<span data-ttu-id="c4a37-125">Crea un set di criteri e impostazioni dei criteri che forniscono agli Information Worker come personale IT, personale informatico, personale finanziario e responsabili della conformità, accesso completo alla chat, alle chiamate e alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="c4a37-125">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="c4a37-126">Sala paziente sanitaria</span><span class="sxs-lookup"><span data-stu-id="c4a37-126">Healthcare patient room</span></span>  |<span data-ttu-id="c4a37-127">Dispositivi per la sala paziente</span><span class="sxs-lookup"><span data-stu-id="c4a37-127">Patient room devices</span></span>|<span data-ttu-id="c4a37-128">Crea un set di criteri e impostazioni dei criteri applicabili alle sale del paziente nell'organizzazione sanitaria.</span><span class="sxs-lookup"><span data-stu-id="c4a37-128">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![Screenshot dei pacchetti di criteri sanitari](media/policy-packages-healthcare.png)

<span data-ttu-id="c4a37-130">A ogni singolo criterio viene assegnato il nome del pacchetto di criteri in modo da poter identificare facilmente i criteri collegati a un pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="c4a37-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="c4a37-131">Ad esempio, quando si assegna il pacchetto di criteri di lavoro clinico sanitario ai clinici dell'organizzazione, viene creato un criterio denominato Healthcare_ClinicalWorker per ogni criterio nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="c4a37-131">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![Screenshot dei criteri nel pacchetto Worker clinico per l'assistenza sanitaria](media/policy-packages-healthcare-clinical-worker.png)

## <a name="get-started-with-policy-packages"></a><span data-ttu-id="c4a37-133">Introduzione ai pacchetti di criteri</span><span class="sxs-lookup"><span data-stu-id="c4a37-133">Get started with policy packages</span></span>

<span data-ttu-id="c4a37-134">Per iniziare a usare i pacchetti di criteri per l'assistenza sanitaria, nell'hub di amministrazione Microsoft, selezionare **nozioni di base sull'assistenza sanitaria** e quindi selezionare **Assegna impostazioni criteri per ruolo** .</span><span class="sxs-lookup"><span data-stu-id="c4a37-134">To get you started with Healthcare policy packages, on the Microsoft Admin Center onboarding hub, select **Healthcare basics** , and then select **Assign policy settings by role** .</span></span> <span data-ttu-id="c4a37-135">Quando si è pronti per iniziare, decidere i pacchetti di criteri a cui si vuole assegnare gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c4a37-135">Once you’re ready to get started, decide which policy packages you'd like to assign individuals in your organization to.</span></span>

<span data-ttu-id="c4a37-136">Selezionare **Visualizza dettagli criteri** per altre informazioni sui criteri specifici in un pacchetto e le rispettive impostazioni.</span><span class="sxs-lookup"><span data-stu-id="c4a37-136">Select **View policy details** to learn more about the specific policies in a package and their respective settings.</span></span> <span data-ttu-id="c4a37-137">Questi dati [possono essere personalizzati](manage-policy-packages.md#customize-policies-in-a-policy-package) dopo l'assegnazione nell'interfaccia di amministrazione di teams.</span><span class="sxs-lookup"><span data-stu-id="c4a37-137">These [can be customized](manage-policy-packages.md#customize-policies-in-a-policy-package) after assignment in the Teams Admin Center.</span></span>

<span data-ttu-id="c4a37-138">Scegliere uno o più pacchetti da assegnare e quindi fare clic su **Avanti** .</span><span class="sxs-lookup"><span data-stu-id="c4a37-138">Choose one or multiple packages to assign and then click **Next** .</span></span> <span data-ttu-id="c4a37-139">Puoi cercare e aggiungere persone al pacchetto di criteri più adatto per il loro ruolo.</span><span class="sxs-lookup"><span data-stu-id="c4a37-139">You can search for and add people to the policy package best suited for their role.</span></span> <span data-ttu-id="c4a37-140">Un singolo utente non può essere assegnato contemporaneamente a più di un pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="c4a37-140">An individual can't be assigned to more than one policy package at one time.</span></span>

<span data-ttu-id="c4a37-141">Dopo aver aggiunto persone al pacchetto di criteri corretto, **fine** completa le selezioni.</span><span class="sxs-lookup"><span data-stu-id="c4a37-141">Once you’ve added people to the right policy package, **Finish** finalizes your selections.</span></span> <span data-ttu-id="c4a37-142">Puoi continuare a personalizzare e gestire i pacchetti di criteri nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="c4a37-142">You can continue to customize and manage policy packages in the Microsoft Teams admin center.</span></span>

## <a name="manage-policy-packages"></a><span data-ttu-id="c4a37-143">Gestire i pacchetti di criteri</span><span class="sxs-lookup"><span data-stu-id="c4a37-143">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="c4a37-144">Visualizzazione</span><span class="sxs-lookup"><span data-stu-id="c4a37-144">View</span></span>

<span data-ttu-id="c4a37-145">Visualizzare le impostazioni di ogni criterio in un pacchetto di criteri prima di assegnare un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="c4a37-145">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="c4a37-146">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare **pacchetti di criteri** , selezionare il nome del pacchetto e quindi selezionare il nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="c4a37-146">In the left navigation of the Microsoft Teams admin center, select **Policy packages** , select the package name, and then select the policy name.</span></span>

<span data-ttu-id="c4a37-147">Decidere se i valori predefiniti sono appropriati per l'organizzazione o se è necessario personalizzarli per essere più restrittivi o indulgenti in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c4a37-147">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="c4a37-148">Personalizza</span><span class="sxs-lookup"><span data-stu-id="c4a37-148">Customize</span></span>

<span data-ttu-id="c4a37-149">Personalizzare le impostazioni dei criteri nel pacchetto dei criteri, se necessario, in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c4a37-149">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="c4a37-150">Tutte le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti a cui è stato assegnato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="c4a37-150">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="c4a37-151">Per modificare le impostazioni di un criterio in un pacchetto di criteri, nell'interfaccia di amministrazione di Microsoft teams selezionare il pacchetto di criteri, selezionare il nome del criterio che si vuole modificare e quindi selezionare **modifica** .</span><span class="sxs-lookup"><span data-stu-id="c4a37-151">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit** .</span></span>

<span data-ttu-id="c4a37-152">Tieni presente che puoi anche modificare le impostazioni dei criteri in un pacchetto dopo l'assegnazione del pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="c4a37-152">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="c4a37-153">Per altre informazioni, vedere [personalizzare i criteri in un pacchetto di criteri](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="c4a37-153">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="c4a37-154">Assegnare</span><span class="sxs-lookup"><span data-stu-id="c4a37-154">Assign</span></span>

<span data-ttu-id="c4a37-155">Assegnare il pacchetto di criteri agli utenti.</span><span class="sxs-lookup"><span data-stu-id="c4a37-155">Assign the policy package to users.</span></span> <span data-ttu-id="c4a37-156">Per assegnare un pacchetto di criteri a uno o più utenti, fare clic su **Gestisci utenti** .</span><span class="sxs-lookup"><span data-stu-id="c4a37-156">To assign a policy package to one or multiple users, click **Manage users** .</span></span> <span data-ttu-id="c4a37-157">È anche possibile [usare PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) per assegnare un pacchetto di criteri ai batch di grandi dimensioni degli utenti.</span><span class="sxs-lookup"><span data-stu-id="c4a37-157">You can also [use PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) to assign a policy package to large batches of users.</span></span> 

<span data-ttu-id="c4a37-158">Per istruzioni su come assegnare un pacchetto di criteri usando l'interfaccia di amministrazione di Microsoft teams o PowerShell, vedere [assegnare un pacchetto di criteri](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="c4a37-158">For steps on how to assign a policy package using the Microsoft Teams admin center or PowerShell, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![Screenshot che illustra come assegnare un pacchetto di criteri nell'interfaccia di amministrazione](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="c4a37-160">Se un utente ha un criterio assegnato e in seguito si assegna un criterio diverso, l'assegnazione più recente avrà la priorità.</span><span class="sxs-lookup"><span data-stu-id="c4a37-160">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c4a37-161">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c4a37-161">Related topics</span></span>

[<span data-ttu-id="c4a37-162">Gestire i pacchetti di criteri in Teams</span><span class="sxs-lookup"><span data-stu-id="c4a37-162">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="c4a37-163">Assegnare criteri agli utenti in teams</span><span class="sxs-lookup"><span data-stu-id="c4a37-163">Assign policies to your users in Teams</span></span>](assign-policies.md)
