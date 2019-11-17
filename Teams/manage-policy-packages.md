---
title: Gestire i pacchetti di criteri in Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: sekrantz, aaglick
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i pacchetti di criteri in Microsoft teams.
ms.openlocfilehash: ecfc6ae6fb1bb4d9632b8cd04b35dcee6d63359d
ms.sourcegitcommit: 70bf1669442bbb50cb293c86d6a0c80fb3b2b55a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/16/2019
ms.locfileid: "38679828"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="a8977-103">Gestire i pacchetti di criteri in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="a8977-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="a8977-104">Un pacchetto di criteri in Microsoft teams è una raccolta di criteri predefiniti e di impostazioni dei criteri che è possibile assegnare agli utenti che hanno ruoli simili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8977-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="a8977-105">I pacchetti di criteri sono stati creati per semplificare, snellire e garantire la coerenza della gestione dei criteri per i gruppi di utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8977-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="a8977-106">Quando si assegna un pacchetto di criteri agli utenti, i criteri del pacchetto vengono creati e quindi è possibile personalizzare le impostazioni dei criteri nel pacchetto per soddisfare le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8977-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="a8977-107">Che cos'è un pacchetto di criteri?</span><span class="sxs-lookup"><span data-stu-id="a8977-107">What is a policy package?</span></span>

<span data-ttu-id="a8977-108">I pacchetti di criteri consentono di controllare le caratteristiche dei team che si desidera concedere o limitare per set specifici di persone nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8977-108">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="a8977-109">Ogni pacchetto di criteri in teams è progettato intorno a un ruolo utente e include criteri predefiniti e impostazioni dei criteri che supportano le attività di collaborazione e comunicazione tipiche di tale ruolo.</span><span class="sxs-lookup"><span data-stu-id="a8977-109">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="a8977-110">I team attualmente includono i seguenti pacchetti di criteri.</span><span class="sxs-lookup"><span data-stu-id="a8977-110">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="a8977-111">**Nome pacchetto**</span><span class="sxs-lookup"><span data-stu-id="a8977-111">**Package name**</span></span>  |<span data-ttu-id="a8977-112">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a8977-112">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="a8977-113">Pacchetto Education_Teacher</span><span class="sxs-lookup"><span data-stu-id="a8977-113">Education_Teacher package</span></span>     |<span data-ttu-id="a8977-114">Crea un set di criteri e impostazioni dei criteri applicabili agli insegnanti.</span><span class="sxs-lookup"><span data-stu-id="a8977-114">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="a8977-115">Pacchetto Education_PrimaryStudent</span><span class="sxs-lookup"><span data-stu-id="a8977-115">Education_PrimaryStudent package</span></span>    |<span data-ttu-id="a8977-116">Crea un set di criteri e impostazioni dei criteri applicabili agli studenti primari.</span><span class="sxs-lookup"><span data-stu-id="a8977-116">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="a8977-117">Pacchetto Education_SecondaryStudent</span><span class="sxs-lookup"><span data-stu-id="a8977-117">Education_SecondaryStudent package</span></span>    |<span data-ttu-id="a8977-118">Crea un set di criteri e impostazioni dei criteri applicabili agli studenti secondari.</span><span class="sxs-lookup"><span data-stu-id="a8977-118">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="a8977-119">Pacchetto Education_HigherEducationStudent</span><span class="sxs-lookup"><span data-stu-id="a8977-119">Education_HigherEducationStudent package</span></span>    |<span data-ttu-id="a8977-120">Crea un set di criteri e impostazioni dei criteri applicabili agli studenti dell'istruzione superiore.</span><span class="sxs-lookup"><span data-stu-id="a8977-120">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="a8977-121">Pacchetto SmallMediumBusiness_BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="a8977-121">SmallMediumBusiness_BusinessVoice package</span></span>    |<span data-ttu-id="a8977-122">Crea un criterio di configurazione dell'app che include le app per un'esperienza di Business Voice.</span><span class="sxs-lookup"><span data-stu-id="a8977-122">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|

> [!NOTE]
> <span data-ttu-id="a8977-123">Aggiungeremo altri pacchetti di criteri nelle versioni future dei team, quindi controlla le informazioni più aggiornate.</span><span class="sxs-lookup"><span data-stu-id="a8977-123">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="a8977-124">A ogni singolo criterio viene assegnato il nome del pacchetto di criteri in modo da poter identificare facilmente i criteri collegati a un pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="a8977-124">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="a8977-125">Ad esempio, quando si assegna il pacchetto di criteri Education_Teacher agli insegnanti dell'Istituto di istruzione, viene creato un criterio denominato Education_Teacher per ogni criterio nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a8977-125">For example, when you assign the Education_Teacher policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Screenshot del pacchetto dei criteri di Education_Teacher](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="a8977-127">Come usare i pacchetti di criteri</span><span class="sxs-lookup"><span data-stu-id="a8977-127">How to use policy packages</span></span>

<span data-ttu-id="a8977-128">La procedura seguente illustra come usare i pacchetti di criteri nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8977-128">The following outlines how to use policy packages in your organization.</span></span>

![Panoramica sull'uso dei pacchetti di criteri](media/manage-policy-packages-overview.png)

- <span data-ttu-id="a8977-130">**[Visualizzazione](#view-the-settings-of-a-policy-in-a-policy-package)**: visualizzare le impostazioni di ogni criterio in un pacchetto di criteri prima di assegnare un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a8977-130">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="a8977-131">Verificare di aver compreso ogni impostazione e quindi decidere se i valori predefiniti sono appropriati per l'organizzazione o se è necessario modificarli per essere più restrittivi o indulgenti in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8977-131">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="a8977-132">Se un criterio viene eliminato, è comunque possibile visualizzarne le impostazioni, ma non si potranno modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="a8977-132">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="a8977-133">I criteri eliminati vengono ricreati con le impostazioni predefinite quando si assegna il pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="a8977-133">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="a8977-134">**[Assegna](#assign-a-policy-package)**: assegna il pacchetto di criteri agli utenti.</span><span class="sxs-lookup"><span data-stu-id="a8977-134">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="a8977-135">Tenere presente che i criteri in un pacchetto di criteri non vengono creati finché non si assegna il pacchetto, dopodiché è possibile modificare le impostazioni dei singoli criteri nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a8977-135">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="a8977-136">**[Personalizza](#customize-policies-in-a-policy-package)**: personalizzare le impostazioni dei criteri nel pacchetto dei criteri per adattarle alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a8977-136">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="a8977-137">Tutte le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti a cui è stato assegnato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a8977-137">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="a8977-138">Ecco i passaggi per visualizzare, assegnare e personalizzare i pacchetti di criteri nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="a8977-138">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="a8977-139">Visualizzare le impostazioni di un criterio in un pacchetto di criteri</span><span class="sxs-lookup"><span data-stu-id="a8977-139">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="a8977-140">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams fare clic su **pacchetti di criteri**e quindi selezionare un pacchetto di criteri facendo clic a sinistra del nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a8977-140">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="a8977-141">Fare clic sul criterio che si vuole visualizzare.</span><span class="sxs-lookup"><span data-stu-id="a8977-141">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="a8977-142">Assegnare un pacchetto di criteri</span><span class="sxs-lookup"><span data-stu-id="a8977-142">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="a8977-143">Assegnare un pacchetto di criteri a un utente</span><span class="sxs-lookup"><span data-stu-id="a8977-143">Assign a policy package to one user</span></span>

1. <span data-ttu-id="a8977-144">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **utenti**e quindi fai clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="a8977-144">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="a8977-145">Nella pagina dell'utente fare clic su **criteri**e quindi fare clic su **modifica**accanto a **pacchetto criteri**.</span><span class="sxs-lookup"><span data-stu-id="a8977-145">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="a8977-146">Nel riquadro **Assegna criteri del pacchetto** selezionare il pacchetto da assegnare e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a8977-146">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="a8977-147">Assegnare un pacchetto di criteri a più utenti</span><span class="sxs-lookup"><span data-stu-id="a8977-147">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="a8977-148">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **pacchetti di criteri**e quindi seleziona il pacchetto di criteri da assegnare facendo clic a sinistra del nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a8977-148">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="a8977-149">Fare clic su **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="a8977-149">Click **Manage users**.</span></span>
3. <span data-ttu-id="a8977-150">Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o per nome utente, selezionare il nome e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="a8977-150">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="a8977-151">Ripetere questo passaggio per ogni utente che si vuole aggiungere.</span><span class="sxs-lookup"><span data-stu-id="a8977-151">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="a8977-152">Al termine dell'aggiunta di utenti, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a8977-152">When you're finished adding users, click **Save**.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="a8977-153">Personalizzare i criteri in un pacchetto di criteri</span><span class="sxs-lookup"><span data-stu-id="a8977-153">Customize policies in a policy package</span></span>

<span data-ttu-id="a8977-154">È possibile modificare le impostazioni di un criterio tramite la pagina **pacchetti di criteri** o accedendo direttamente alla pagina dei criteri nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="a8977-154">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="a8977-155">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a8977-155">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="a8977-156">Fare clic su **pacchetti di criteri**e quindi selezionare il pacchetto di criteri facendo clic a sinistra del nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="a8977-156">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="a8977-157">Fare clic sul tipo di criterio.</span><span class="sxs-lookup"><span data-stu-id="a8977-157">Click the policy type.</span></span>  <span data-ttu-id="a8977-158">Ad esempio, fare clic su **criteri di messaggistica**.</span><span class="sxs-lookup"><span data-stu-id="a8977-158">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="a8977-159">Fare clic sul criterio che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="a8977-159">Click the policy you want to edit.</span></span> <span data-ttu-id="a8977-160">I criteri collegati a un pacchetto di criteri hanno lo stesso nome del pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="a8977-160">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="a8977-161">Apportare le modifiche desiderate e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="a8977-161">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="a8977-162">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="a8977-162">Troubleshooting</span></span>

<span data-ttu-id="a8977-163">**Viene visualizzato un messaggio di errore quando si assegna un pacchetto di criteri**</span><span class="sxs-lookup"><span data-stu-id="a8977-163">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="a8977-164">Questo problema può verificarsi se uno o più criteri del pacchetto non sono stati creati o applicati correttamente.</span><span class="sxs-lookup"><span data-stu-id="a8977-164">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="a8977-165">Riassegnare il pacchetto di criteri agli utenti.</span><span class="sxs-lookup"><span data-stu-id="a8977-165">Reassign the policy package to your users.</span></span> <span data-ttu-id="a8977-166">Il tentativo di riprovare l'operazione in genere risolve questo problema.</span><span class="sxs-lookup"><span data-stu-id="a8977-166">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="a8977-167">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="a8977-167">Related topics</span></span>

[<span data-ttu-id="a8977-168">Pacchetti dei criteri di Microsoft teams per gli amministratori EDU</span><span class="sxs-lookup"><span data-stu-id="a8977-168">Microsoft Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
