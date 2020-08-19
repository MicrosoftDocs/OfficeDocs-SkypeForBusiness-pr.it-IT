---
title: Pacchetti di criteri per le squadre per enti pubblici
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
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i pacchetti di criteri per le squadre per l'organizzazione pubblica.
ms.openlocfilehash: 738197a82303c1149ebc89a8e3ad7c6b37df90eb
ms.sourcegitcommit: bd13aecbb25c14e17d1b64343df6d80c90b2aa45
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2020
ms.locfileid: "46804028"
---
# <a name="teams-policy-packages-for-government"></a><span data-ttu-id="ae0a7-103">Pacchetti di criteri per le squadre per enti pubblici</span><span class="sxs-lookup"><span data-stu-id="ae0a7-103">Teams policy packages for government</span></span>

> [!NOTE]
> <span data-ttu-id="ae0a7-104">I pacchetti di criteri non sono attualmente disponibili nelle distribuzioni governative GCC High o DoD di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-104">Policy packages are currently not available in Microsoft 365 Government GCC High or DoD deployments.</span></span>

## <a name="overview"></a><span data-ttu-id="ae0a7-105">Panoramica</span><span class="sxs-lookup"><span data-stu-id="ae0a7-105">Overview</span></span>

<span data-ttu-id="ae0a7-106">Un [pacchetto di criteri](manage-policy-packages.md) in Microsoft teams è una raccolta di criteri predefiniti e di impostazioni dei criteri che è possibile assegnare agli utenti che hanno ruoli simili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-106">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="ae0a7-107">I pacchetti di criteri semplificano la gestione dei criteri e contribuiscono a garantirne la coerenza.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-107">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="ae0a7-108">È possibile personalizzare le impostazioni dei criteri nel pacchetto in base alle esigenze degli utenti.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-108">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="ae0a7-109">Quando si modificano le impostazioni dei criteri in un pacchetto di criteri, tutti gli utenti assegnati al pacchetto ottengono le impostazioni aggiornate.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-109">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="ae0a7-110">Puoi gestire i pacchetti di criteri usando l'interfaccia di amministrazione di Microsoft teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-110">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="ae0a7-111">I pacchetti di criteri predefiniscono i criteri per i seguenti elementi, a seconda del pacchetto:</span><span class="sxs-lookup"><span data-stu-id="ae0a7-111">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="ae0a7-112">Messaggistica</span><span class="sxs-lookup"><span data-stu-id="ae0a7-112">Messaging</span></span>
- <span data-ttu-id="ae0a7-113">Riunioni</span><span class="sxs-lookup"><span data-stu-id="ae0a7-113">Meetings</span></span>
- <span data-ttu-id="ae0a7-114">Chiamate</span><span class="sxs-lookup"><span data-stu-id="ae0a7-114">Calling</span></span>
- <span data-ttu-id="ae0a7-115">Configurazione dell'app</span><span class="sxs-lookup"><span data-stu-id="ae0a7-115">App setup</span></span>
- <span data-ttu-id="ae0a7-116">Eventi live</span><span class="sxs-lookup"><span data-stu-id="ae0a7-116">Live events</span></span>

<span data-ttu-id="ae0a7-117">I team attualmente includono i pacchetti di criteri seguenti per il governo.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-117">Teams currently includes the following policy packages for government.</span></span>

|<span data-ttu-id="ae0a7-118">Nome pacchetto nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ae0a7-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="ae0a7-119">Ideale per</span><span class="sxs-lookup"><span data-stu-id="ae0a7-119">Best used for</span></span>|<span data-ttu-id="ae0a7-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="ae0a7-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="ae0a7-121">Addetto alla sicurezza pubblica</span><span class="sxs-lookup"><span data-stu-id="ae0a7-121">Public safety officer</span></span>  |<span data-ttu-id="ae0a7-122">Responsabili della sicurezza pubblica nella propria organizzazione governativa</span><span class="sxs-lookup"><span data-stu-id="ae0a7-122">Public safety officers in your government organization</span></span>  |<span data-ttu-id="ae0a7-123">Crea un set di criteri e impostazioni dei criteri applicabili agli addetti alla sicurezza pubblica dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-123">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span> |
|<span data-ttu-id="ae0a7-124">Gestione i FIRSTLINE</span><span class="sxs-lookup"><span data-stu-id="ae0a7-124">Firstline manager</span></span>  |<span data-ttu-id="ae0a7-125">Responsabili di i FIRSTLINE nella propria organizzazione pubblica</span><span class="sxs-lookup"><span data-stu-id="ae0a7-125">Firstline Managers in your government organization</span></span> |<span data-ttu-id="ae0a7-126">Crea un set di criteri e applica tali impostazioni ai responsabili di I FIRSTLINE dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-126">Creates a set of policies and applies those settings to Firstline Managers in your organization.</span></span>|
|<span data-ttu-id="ae0a7-127">Lavoratore i FIRSTLINE</span><span class="sxs-lookup"><span data-stu-id="ae0a7-127">Firstline worker</span></span>  |<span data-ttu-id="ae0a7-128">I FIRSTLINE lavoratori dell'organizzazione governativa</span><span class="sxs-lookup"><span data-stu-id="ae0a7-128">Firstline Workers in your government organization</span></span> |<span data-ttu-id="ae0a7-129">Crea un set di criteri e applica tali impostazioni agli operatori I FIRSTLINE dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-129">Creates a set of policies and applies those settings to Firstline Workers in your organization.</span></span>|

![Screenshot dei pacchetti di criteri sanitari](media/policy-packages-gov.png)

<span data-ttu-id="ae0a7-131">A ogni singolo criterio viene assegnato il nome del pacchetto di criteri in modo da poter identificare facilmente i criteri collegati a un pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="ae0a7-132">Ad esempio, quando si assegna il pacchetto di criteri per gli agenti di sicurezza pubblica agli utenti dell'organizzazione, viene creato un criterio denominato PublicSafety_Officer per ogni criterio nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-132">For example, when you assign the Public safety officer policy package to users in your organization, a policy named PublicSafety_Officer is created for each policy in the package.</span></span>

![Screenshot dei criteri nel pacchetto Worker clinico per l'assistenza sanitaria](media/policy-packages-public-safety-officer.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="ae0a7-134">Gestire i pacchetti di criteri</span><span class="sxs-lookup"><span data-stu-id="ae0a7-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="ae0a7-135">Visualizzazione</span><span class="sxs-lookup"><span data-stu-id="ae0a7-135">View</span></span>

<span data-ttu-id="ae0a7-136">Visualizzare le impostazioni di ogni criterio in un pacchetto di criteri prima di assegnare un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="ae0a7-137">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare **pacchetti di criteri**, selezionare il nome del pacchetto e quindi selezionare il nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="ae0a7-138">Decidere se i valori predefiniti sono appropriati per l'organizzazione o se è necessario personalizzarli per essere più restrittivi o indulgenti in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="ae0a7-139">Personalizza</span><span class="sxs-lookup"><span data-stu-id="ae0a7-139">Customize</span></span>

<span data-ttu-id="ae0a7-140">Personalizzare le impostazioni dei criteri nel pacchetto dei criteri, se necessario, in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="ae0a7-141">Tutte le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti a cui è stato assegnato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="ae0a7-142">Per modificare le impostazioni di un criterio in un pacchetto di criteri, nell'interfaccia di amministrazione di Microsoft teams selezionare il pacchetto di criteri, selezionare il nome del criterio che si vuole modificare e quindi selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="ae0a7-143">Tieni presente che puoi anche modificare le impostazioni dei criteri in un pacchetto dopo l'assegnazione del pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="ae0a7-144">Per altre informazioni, vedere [personalizzare i criteri in un pacchetto di criteri](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="ae0a7-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="ae0a7-145">Assegnare</span><span class="sxs-lookup"><span data-stu-id="ae0a7-145">Assign</span></span>

<span data-ttu-id="ae0a7-146">Assegnare il pacchetto di criteri agli utenti.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-146">Assign the policy package to users.</span></span> <span data-ttu-id="ae0a7-147">Per assegnare un pacchetto di criteri a uno o più utenti, fare clic su **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-147">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="ae0a7-148">È anche possibile [usare PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) per assegnare un pacchetto di criteri ai batch di grandi dimensioni degli utenti.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-148">You can also [use PowerShell](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicypackageassignmentoperation) to assign a policy package to large batches of users.</span></span> 

<span data-ttu-id="ae0a7-149">Per istruzioni su come assegnare un pacchetto di criteri usando l'interfaccia di amministrazione di Microsoft teams o PowerShell, vedere [assegnare un pacchetto di criteri](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="ae0a7-149">For steps on how to assign a policy package using the Microsoft Teams admin center or PowerShell, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![Screenshot che illustra come assegnare un pacchetto di criteri nell'interfaccia di amministrazione](media/policy-packages-gov-assign.png)

<span data-ttu-id="ae0a7-151">Se un utente ha un criterio assegnato e in seguito si assegna un criterio diverso, l'assegnazione più recente avrà la priorità.</span><span class="sxs-lookup"><span data-stu-id="ae0a7-151">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ae0a7-152">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="ae0a7-152">Related topics</span></span>

[<span data-ttu-id="ae0a7-153">Gestire i pacchetti di criteri in Teams</span><span class="sxs-lookup"><span data-stu-id="ae0a7-153">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="ae0a7-154">Assegnare criteri agli utenti in teams</span><span class="sxs-lookup"><span data-stu-id="ae0a7-154">Assign policies to your users in Teams</span></span>](assign-policies.md) 
