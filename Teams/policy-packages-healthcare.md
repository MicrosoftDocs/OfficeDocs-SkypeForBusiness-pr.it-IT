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
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i pacchetti di criteri team per l'organizzazione sanitaria.
ms.openlocfilehash: e7b01935969105abae447ae896480e1faf67fa40
ms.sourcegitcommit: 2aea6ec07149a3054ee4434c8a0bffabf1a16d25
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2020
ms.locfileid: "46578198"
---
# <a name="teams-policy-packages-for-healthcare"></a><span data-ttu-id="25efd-103">Pacchetti di criteri team per l'assistenza sanitaria</span><span class="sxs-lookup"><span data-stu-id="25efd-103">Teams policy packages for healthcare</span></span>

## <a name="overview"></a><span data-ttu-id="25efd-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="25efd-104">Overview</span></span>

<span data-ttu-id="25efd-105">Un [pacchetto di criteri](manage-policy-packages.md) in Microsoft teams è una raccolta di criteri predefiniti e di impostazioni dei criteri che è possibile assegnare agli utenti che hanno ruoli simili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="25efd-105">A [policy package](manage-policy-packages.md) in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="25efd-106">I pacchetti di criteri semplificano la gestione dei criteri e contribuiscono a garantirne la coerenza.</span><span class="sxs-lookup"><span data-stu-id="25efd-106">Policy packages simplify, streamline, and help provide consistency when managing policies.</span></span> <span data-ttu-id="25efd-107">È possibile personalizzare le impostazioni dei criteri nel pacchetto in base alle esigenze degli utenti.</span><span class="sxs-lookup"><span data-stu-id="25efd-107">You can customize the settings of the policies in the package to suit the needs of your users.</span></span> <span data-ttu-id="25efd-108">Quando si modificano le impostazioni dei criteri in un pacchetto di criteri, tutti gli utenti assegnati al pacchetto ottengono le impostazioni aggiornate.</span><span class="sxs-lookup"><span data-stu-id="25efd-108">When you change the settings of policies in a policy package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="25efd-109">Puoi gestire i pacchetti di criteri usando l'interfaccia di amministrazione di Microsoft teams o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="25efd-109">You can manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

<span data-ttu-id="25efd-110">I pacchetti di criteri predefiniscono i criteri per i seguenti elementi, a seconda del pacchetto:</span><span class="sxs-lookup"><span data-stu-id="25efd-110">Policy packages pre-define policies for the following, depending on the package:</span></span>

- <span data-ttu-id="25efd-111">Riunioni</span><span class="sxs-lookup"><span data-stu-id="25efd-111">Meetings</span></span>
- <span data-ttu-id="25efd-112">Eventi live</span><span class="sxs-lookup"><span data-stu-id="25efd-112">Live events</span></span>
- <span data-ttu-id="25efd-113">Chiamate</span><span class="sxs-lookup"><span data-stu-id="25efd-113">Calling</span></span>
- <span data-ttu-id="25efd-114">Messaggistica</span><span class="sxs-lookup"><span data-stu-id="25efd-114">Messaging</span></span>
- <span data-ttu-id="25efd-115">Team</span><span class="sxs-lookup"><span data-stu-id="25efd-115">Teams</span></span>
- <span data-ttu-id="25efd-116">Configurazione dell'app</span><span class="sxs-lookup"><span data-stu-id="25efd-116">App setup</span></span>

<span data-ttu-id="25efd-117">I team attualmente includono i seguenti pacchetti di criteri sanitari.</span><span class="sxs-lookup"><span data-stu-id="25efd-117">Teams currently includes the following healthcare policy packages.</span></span>

|<span data-ttu-id="25efd-118">Nome pacchetto nell'interfaccia di amministrazione di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="25efd-118">Package name in the Microsoft Teams admin center</span></span>|<span data-ttu-id="25efd-119">Ideale per</span><span class="sxs-lookup"><span data-stu-id="25efd-119">Best used for</span></span>|<span data-ttu-id="25efd-120">Descrizione</span><span class="sxs-lookup"><span data-stu-id="25efd-120">Description</span></span> |
|---------|---------|---------|
|<span data-ttu-id="25efd-121">Lavoratore clinico sanitario</span><span class="sxs-lookup"><span data-stu-id="25efd-121">Healthcare clinical worker</span></span>  |<span data-ttu-id="25efd-122">Operatori clinici nell'organizzazione sanitaria</span><span class="sxs-lookup"><span data-stu-id="25efd-122">Clinical workers in your healthcare organization</span></span>  |<span data-ttu-id="25efd-123">Crea un set di criteri e impostazioni dei criteri che conferiscono agli operatori clinici, ad esempio infermieri registrati, addebiti infermieri, medici e assistenti sociali, l'accesso completo alla chat, alle chiamate, alla gestione del turno e alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="25efd-123">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="25efd-124">Information Worker sanitari</span><span class="sxs-lookup"><span data-stu-id="25efd-124">Healthcare information worker</span></span>  |<span data-ttu-id="25efd-125">Information Worker nell'organizzazione sanitaria</span><span class="sxs-lookup"><span data-stu-id="25efd-125">Information workers in your healthcare organization</span></span> |<span data-ttu-id="25efd-126">Crea un set di criteri e impostazioni dei criteri che forniscono agli Information Worker come personale IT, personale informatico, personale finanziario e responsabili della conformità, accesso completo alla chat, alle chiamate e alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="25efd-126">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="25efd-127">Sala paziente sanitaria</span><span class="sxs-lookup"><span data-stu-id="25efd-127">Healthcare patient room</span></span>  |<span data-ttu-id="25efd-128">Dispositivi per la sala paziente</span><span class="sxs-lookup"><span data-stu-id="25efd-128">Patient room devices</span></span>|<span data-ttu-id="25efd-129">Crea un set di criteri e impostazioni dei criteri applicabili alle sale del paziente nell'organizzazione sanitaria.</span><span class="sxs-lookup"><span data-stu-id="25efd-129">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|

![Screenshot dei pacchetti di criteri sanitari](media/policy-packages-healthcare.png)

<span data-ttu-id="25efd-131">A ogni singolo criterio viene assegnato il nome del pacchetto di criteri in modo da poter identificare facilmente i criteri collegati a un pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="25efd-131">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span> <span data-ttu-id="25efd-132">Ad esempio, quando si assegna il pacchetto di criteri di lavoro clinico sanitario ai clinici dell'organizzazione, viene creato un criterio denominato Healthcare_ClinicalWorker per ogni criterio nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="25efd-132">For example, when you assign the Healthcare clinical worker policy package to clinicians in your organization, a policy named Healthcare_ClinicalWorker is created for each policy in the package.</span></span>

![Screenshot dei criteri nel pacchetto Worker clinico per l'assistenza sanitaria](media/policy-packages-healthcare-clinical-worker.png)

## <a name="manage-policy-packages"></a><span data-ttu-id="25efd-134">Gestire i pacchetti di criteri</span><span class="sxs-lookup"><span data-stu-id="25efd-134">Manage policy packages</span></span>

### <a name="view"></a><span data-ttu-id="25efd-135">Visualizzazione</span><span class="sxs-lookup"><span data-stu-id="25efd-135">View</span></span>

<span data-ttu-id="25efd-136">Visualizzare le impostazioni di ogni criterio in un pacchetto di criteri prima di assegnare un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="25efd-136">View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="25efd-137">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams selezionare **pacchetti di criteri**, selezionare il nome del pacchetto e quindi selezionare il nome del criterio.</span><span class="sxs-lookup"><span data-stu-id="25efd-137">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, select the package name, and then select the policy name.</span></span>

<span data-ttu-id="25efd-138">Decidere se i valori predefiniti sono appropriati per l'organizzazione o se è necessario personalizzarli per essere più restrittivi o indulgenti in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="25efd-138">Decide whether the predefined values are appropriate for your organization or whether you need to customize them to be more restrictive or lenient based on your organization's needs.</span></span>

### <a name="customize"></a><span data-ttu-id="25efd-139">Personalizza</span><span class="sxs-lookup"><span data-stu-id="25efd-139">Customize</span></span>

<span data-ttu-id="25efd-140">Personalizzare le impostazioni dei criteri nel pacchetto dei criteri, se necessario, in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="25efd-140">Customize the settings of policies in the policy package, as needed, to fit the needs of your organization.</span></span> <span data-ttu-id="25efd-141">Tutte le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti a cui è stato assegnato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="25efd-141">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span> <span data-ttu-id="25efd-142">Per modificare le impostazioni di un criterio in un pacchetto di criteri, nell'interfaccia di amministrazione di Microsoft teams selezionare il pacchetto di criteri, selezionare il nome del criterio che si vuole modificare e quindi selezionare **modifica**.</span><span class="sxs-lookup"><span data-stu-id="25efd-142">To edit the settings of a policy in a policy package, in the Microsoft Teams admin center, select the policy package, select the name of the policy you want to edit, and then select **Edit**.</span></span>

<span data-ttu-id="25efd-143">Tieni presente che puoi anche modificare le impostazioni dei criteri in un pacchetto dopo l'assegnazione del pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="25efd-143">Keep in mind that you can also change the settings of policies in a package after you assign the policy package.</span></span> <span data-ttu-id="25efd-144">Per altre informazioni, vedere [personalizzare i criteri in un pacchetto di criteri](manage-policy-packages.md#customize-policies-in-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="25efd-144">To learn more, see [Customize policies in a policy package](manage-policy-packages.md#customize-policies-in-a-policy-package).</span></span> 

### <a name="assign"></a><span data-ttu-id="25efd-145">Assegnare</span><span class="sxs-lookup"><span data-stu-id="25efd-145">Assign</span></span>

<span data-ttu-id="25efd-146">Assegnare il pacchetto di criteri agli utenti.</span><span class="sxs-lookup"><span data-stu-id="25efd-146">Assign the policy package to users.</span></span> <span data-ttu-id="25efd-147">Per assegnare un pacchetto di criteri a uno o più utenti, fare clic su **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="25efd-147">To assign a policy package to one or multiple users, click **Manage users**.</span></span> <span data-ttu-id="25efd-148">È anche possibile usare PowerShell per assegnare un pacchetto di criteri ai batch di grandi dimensioni degli utenti.</span><span class="sxs-lookup"><span data-stu-id="25efd-148">You can also use PowerShell to assign a policy package to large batches of users.</span></span> <span data-ttu-id="25efd-149">Per istruzioni su come assegnare un pacchetto di criteri, vedere [assegnare un pacchetto di criteri](manage-policy-packages.md#assign-a-policy-package).</span><span class="sxs-lookup"><span data-stu-id="25efd-149">For steps on how to assign a policy package, see [Assign a policy package](manage-policy-packages.md#assign-a-policy-package).</span></span>

![Screenshot che illustra come assegnare un pacchetto di criteri nell'interfaccia di amministrazione](media/policy-packages-healthcare-assign.png)

<span data-ttu-id="25efd-151">Se un utente ha un criterio assegnato e in seguito si assegna un criterio diverso, l'assegnazione più recente avrà la priorità.</span><span class="sxs-lookup"><span data-stu-id="25efd-151">If a user has a policy assigned, and then later you assign a different policy, the most recent assignment will take priority.</span></span>

## <a name="related-topics"></a><span data-ttu-id="25efd-152">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="25efd-152">Related topics</span></span>

[<span data-ttu-id="25efd-153">Gestire i pacchetti di criteri in Teams</span><span class="sxs-lookup"><span data-stu-id="25efd-153">Manage policy packages in Teams</span></span>](manage-policy-packages.md)

[<span data-ttu-id="25efd-154">Assegnare criteri agli utenti in teams</span><span class="sxs-lookup"><span data-stu-id="25efd-154">Assign policies to your users in Teams</span></span>](assign-policies.md)
