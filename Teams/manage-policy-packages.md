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
f1.keywords: ms.teamsadmincenter.policypackages.overview
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i pacchetti di criteri in Microsoft teams.
ms.openlocfilehash: d73cd22cc0a98cd772ba3823fffa3649602010bc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41772748"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="8dd29-103">Gestire i pacchetti di criteri in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8dd29-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="8dd29-104">Un pacchetto di criteri in Microsoft teams è una raccolta di criteri predefiniti e di impostazioni dei criteri che è possibile assegnare agli utenti che hanno ruoli simili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8dd29-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="8dd29-105">I pacchetti di criteri sono stati creati per semplificare, snellire e garantire la coerenza della gestione dei criteri per i gruppi di utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8dd29-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="8dd29-106">Quando si assegna un pacchetto di criteri agli utenti, i criteri del pacchetto vengono creati e quindi è possibile personalizzare le impostazioni dei criteri nel pacchetto per soddisfare le esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8dd29-106">When you assign a policy package to users, the policies in the package are created and you can then customize the settings of the policies in the package to meet your organization's needs.</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="8dd29-107">Che cos'è un pacchetto di criteri?</span><span class="sxs-lookup"><span data-stu-id="8dd29-107">What is a policy package?</span></span>

<span data-ttu-id="8dd29-108">I pacchetti di criteri consentono di controllare le caratteristiche dei team che si desidera concedere o limitare per set specifici di persone nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8dd29-108">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="8dd29-109">Ogni pacchetto di criteri in teams è progettato intorno a un ruolo utente e include criteri predefiniti e impostazioni dei criteri che supportano le attività di collaborazione e comunicazione tipiche di tale ruolo.</span><span class="sxs-lookup"><span data-stu-id="8dd29-109">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="8dd29-110">I team attualmente includono i seguenti pacchetti di criteri.</span><span class="sxs-lookup"><span data-stu-id="8dd29-110">Teams currently includes the following policy packages.</span></span>

|<span data-ttu-id="8dd29-111">**Nome pacchetto**</span><span class="sxs-lookup"><span data-stu-id="8dd29-111">**Package name**</span></span>  |<span data-ttu-id="8dd29-112">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="8dd29-112">**Description**</span></span> |
|---------|---------|
|<span data-ttu-id="8dd29-113">Istruzione (studente di istruzione superiore)</span><span class="sxs-lookup"><span data-stu-id="8dd29-113">Education (Higher education student)</span></span>    |<span data-ttu-id="8dd29-114">Crea un set di criteri e impostazioni dei criteri applicabili agli studenti dell'istruzione superiore.</span><span class="sxs-lookup"><span data-stu-id="8dd29-114">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="8dd29-115">Istruzione (studente di scuola elementare)</span><span class="sxs-lookup"><span data-stu-id="8dd29-115">Education (Primary school student)</span></span>   |<span data-ttu-id="8dd29-116">Crea un set di criteri e impostazioni dei criteri applicabili agli studenti primari.</span><span class="sxs-lookup"><span data-stu-id="8dd29-116">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="8dd29-117">Istruzione (studente di scuola secondaria)</span><span class="sxs-lookup"><span data-stu-id="8dd29-117">Education (Secondary school student)</span></span>    |<span data-ttu-id="8dd29-118">Crea un set di criteri e impostazioni dei criteri applicabili agli studenti secondari.</span><span class="sxs-lookup"><span data-stu-id="8dd29-118">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="8dd29-119">Istruzione (insegnante)</span><span class="sxs-lookup"><span data-stu-id="8dd29-119">Education (Teacher)</span></span>    |<span data-ttu-id="8dd29-120">Crea un set di criteri e impostazioni dei criteri applicabili agli insegnanti.</span><span class="sxs-lookup"><span data-stu-id="8dd29-120">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="8dd29-121">Business Voice</span><span class="sxs-lookup"><span data-stu-id="8dd29-121">Business voice</span></span> |<span data-ttu-id="8dd29-122">Crea un criterio di configurazione dell'app che include le app per un'esperienza di Business Voice.</span><span class="sxs-lookup"><span data-stu-id="8dd29-122">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="8dd29-123">Addetto alla sicurezza pubblica</span><span class="sxs-lookup"><span data-stu-id="8dd29-123">Public safety officer</span></span>   |<span data-ttu-id="8dd29-124">Crea un set di criteri e impostazioni dei criteri applicabili agli addetti alla sicurezza pubblica dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8dd29-124">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|
|<span data-ttu-id="8dd29-125">Sanità (lavoratore clinico)</span><span class="sxs-lookup"><span data-stu-id="8dd29-125">Healthcare (Clinical worker)</span></span>  |<span data-ttu-id="8dd29-126">Crea un set di criteri e impostazioni dei criteri che conferiscono agli operatori clinici, ad esempio infermieri registrati, addebiti infermieri, medici e assistenti sociali, l'accesso completo alla chat, alle chiamate, alla gestione del turno e alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="8dd29-126">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="8dd29-127">Assistenza sanitaria (Information Worker)</span><span class="sxs-lookup"><span data-stu-id="8dd29-127">Healthcare (Information worker)</span></span>  |<span data-ttu-id="8dd29-128">Crea un set di criteri e impostazioni dei criteri che forniscono agli Information Worker come personale IT, personale informatico, personale finanziario e responsabili della conformità, accesso completo alla chat, alle chiamate e alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="8dd29-128">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|


> [!NOTE]
> <span data-ttu-id="8dd29-129">Aggiungeremo altri pacchetti di criteri nelle versioni future dei team, quindi controlla le informazioni più aggiornate.</span><span class="sxs-lookup"><span data-stu-id="8dd29-129">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="8dd29-130">A ogni singolo criterio viene assegnato il nome del pacchetto di criteri in modo da poter identificare facilmente i criteri collegati a un pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="8dd29-130">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="8dd29-131">Ad esempio, quando si assegna il pacchetto di criteri Education (Teacher) agli insegnanti dell'Istituto di istruzione, viene creato un criterio denominato Education_Teacher per ogni criterio nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8dd29-131">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Screenshot del pacchetto di criteri Education (Teacher)](media/policy-packages-education_teacher.png)

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="8dd29-133">Come usare i pacchetti di criteri</span><span class="sxs-lookup"><span data-stu-id="8dd29-133">How to use policy packages</span></span>

<span data-ttu-id="8dd29-134">La procedura seguente illustra come usare i pacchetti di criteri nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8dd29-134">The following outlines how to use policy packages in your organization.</span></span>

![Panoramica sull'uso dei pacchetti di criteri](media/manage-policy-packages-overview.png)

- <span data-ttu-id="8dd29-136">**[Visualizzazione](#view-the-settings-of-a-policy-in-a-policy-package)**: visualizzare le impostazioni di ogni criterio in un pacchetto di criteri prima di assegnare un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8dd29-136">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the settings of each policy in a policy package before you assign a package.</span></span> <span data-ttu-id="8dd29-137">Verificare di aver compreso ogni impostazione e quindi decidere se i valori predefiniti sono appropriati per l'organizzazione o se è necessario modificarli per essere più restrittivi o indulgenti in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8dd29-137">Make sure that you understand each setting and then decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="8dd29-138">Se un criterio viene eliminato, è comunque possibile visualizzarne le impostazioni, ma non si potranno modificare le impostazioni.</span><span class="sxs-lookup"><span data-stu-id="8dd29-138">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="8dd29-139">I criteri eliminati vengono ricreati con le impostazioni predefinite quando si assegna il pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="8dd29-139">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="8dd29-140">**[Assegna](#assign-a-policy-package)**: assegna il pacchetto di criteri agli utenti.</span><span class="sxs-lookup"><span data-stu-id="8dd29-140">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span> <span data-ttu-id="8dd29-141">Tenere presente che i criteri in un pacchetto di criteri non vengono creati finché non si assegna il pacchetto, dopodiché è possibile modificare le impostazioni dei singoli criteri nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8dd29-141">Remember that policies in a policy package aren't created until you assign the package, after which you can change the settings of individual policies in the package.</span></span>  

- <span data-ttu-id="8dd29-142">**[Personalizza](#customize-policies-in-a-policy-package)**: personalizzare le impostazioni dei criteri nel pacchetto dei criteri per adattarle alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8dd29-142">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span> <span data-ttu-id="8dd29-143">Tutte le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti a cui è stato assegnato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8dd29-143">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="8dd29-144">Ecco i passaggi per visualizzare, assegnare e personalizzare i pacchetti di criteri nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="8dd29-144">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="8dd29-145">Visualizzare le impostazioni di un criterio in un pacchetto di criteri</span><span class="sxs-lookup"><span data-stu-id="8dd29-145">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="8dd29-146">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams fare clic su **pacchetti di criteri**e quindi selezionare un pacchetto di criteri facendo clic a sinistra del nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8dd29-146">In the left navigation of the Microsoft Teams admin center, click **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="8dd29-147">Fare clic sul criterio che si vuole visualizzare.</span><span class="sxs-lookup"><span data-stu-id="8dd29-147">Click the policy you want to view.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="8dd29-148">Assegnare un pacchetto di criteri</span><span class="sxs-lookup"><span data-stu-id="8dd29-148">Assign a policy package</span></span>

#### <a name="assign-a-policy-package-to-one-user"></a><span data-ttu-id="8dd29-149">Assegnare un pacchetto di criteri a un utente</span><span class="sxs-lookup"><span data-stu-id="8dd29-149">Assign a policy package to one user</span></span>

1. <span data-ttu-id="8dd29-150">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **utenti**e quindi fai clic sull'utente.</span><span class="sxs-lookup"><span data-stu-id="8dd29-150">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="8dd29-151">Nella pagina dell'utente fare clic su **criteri**e quindi fare clic su **modifica**accanto a **pacchetto criteri**.</span><span class="sxs-lookup"><span data-stu-id="8dd29-151">On the user's page, click **Policies**, and then next to **Policy package**, click **Edit**.</span></span>
3. <span data-ttu-id="8dd29-152">Nel riquadro **Assegna criteri del pacchetto** selezionare il pacchetto da assegnare e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8dd29-152">In the **Assign policy package** pane, select the package you want to assign, and then click **Save**.</span></span>

#### <a name="assign-a-policy-package-to-multiple-users"></a><span data-ttu-id="8dd29-153">Assegnare un pacchetto di criteri a più utenti</span><span class="sxs-lookup"><span data-stu-id="8dd29-153">Assign a policy package to multiple users</span></span>

1. <span data-ttu-id="8dd29-154">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams, passa a **pacchetti di criteri**e quindi seleziona il pacchetto di criteri da assegnare facendo clic a sinistra del nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8dd29-154">In the left navigation of the Microsoft Teams admin center, go to **Policy packages**, and then select the policy package you want to assign by clicking to the left of the package name.</span></span>
2. <span data-ttu-id="8dd29-155">Fare clic su **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="8dd29-155">Click **Manage users**.</span></span>
3. <span data-ttu-id="8dd29-156">Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o per nome utente, selezionare il nome e quindi fare clic su **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="8dd29-156">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then click **Add**.</span></span> <span data-ttu-id="8dd29-157">Ripetere questo passaggio per ogni utente che si vuole aggiungere.</span><span class="sxs-lookup"><span data-stu-id="8dd29-157">Repeat this step for each user that you want to add.</span></span>
4. <span data-ttu-id="8dd29-158">Al termine dell'aggiunta di utenti, fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8dd29-158">When you're finished adding users, click **Save**.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="8dd29-159">Personalizzare i criteri in un pacchetto di criteri</span><span class="sxs-lookup"><span data-stu-id="8dd29-159">Customize policies in a policy package</span></span>

<span data-ttu-id="8dd29-160">È possibile modificare le impostazioni di un criterio tramite la pagina **pacchetti di criteri** o accedendo direttamente alla pagina dei criteri nell'interfaccia di amministrazione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="8dd29-160">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="8dd29-161">Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft teams eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8dd29-161">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="8dd29-162">Fare clic su **pacchetti di criteri**e quindi selezionare il pacchetto di criteri facendo clic a sinistra del nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="8dd29-162">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="8dd29-163">Fare clic sul tipo di criterio.</span><span class="sxs-lookup"><span data-stu-id="8dd29-163">Click the policy type.</span></span>  <span data-ttu-id="8dd29-164">Ad esempio, fare clic su **criteri di messaggistica**.</span><span class="sxs-lookup"><span data-stu-id="8dd29-164">For example, click **Messaging policies**.</span></span>
2. <span data-ttu-id="8dd29-165">Fare clic sul criterio che si vuole modificare.</span><span class="sxs-lookup"><span data-stu-id="8dd29-165">Click the policy you want to edit.</span></span> <span data-ttu-id="8dd29-166">I criteri collegati a un pacchetto di criteri hanno lo stesso nome del pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="8dd29-166">Policies that are linked to a policy package have the same name as the policy package.</span></span>
3. <span data-ttu-id="8dd29-167">Apportare le modifiche desiderate e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8dd29-167">Make the changes that you want, and then click **Save**.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="8dd29-168">Risoluzione dei problemi</span><span class="sxs-lookup"><span data-stu-id="8dd29-168">Troubleshooting</span></span>

<span data-ttu-id="8dd29-169">**Viene visualizzato un messaggio di errore quando si assegna un pacchetto di criteri**</span><span class="sxs-lookup"><span data-stu-id="8dd29-169">**You receive an error when you assign a policy package**</span></span>

<span data-ttu-id="8dd29-170">Questo problema può verificarsi se uno o più criteri del pacchetto non sono stati creati o applicati correttamente.</span><span class="sxs-lookup"><span data-stu-id="8dd29-170">This may occur if one or more policies in the package weren't created or applied successfully.</span></span> <span data-ttu-id="8dd29-171">Riassegnare il pacchetto di criteri agli utenti.</span><span class="sxs-lookup"><span data-stu-id="8dd29-171">Reassign the policy package to your users.</span></span> <span data-ttu-id="8dd29-172">Il tentativo di riprovare l'operazione in genere risolve questo problema.</span><span class="sxs-lookup"><span data-stu-id="8dd29-172">Retrying the operation typically fixes this issue.</span></span>

## <a name="related-topics"></a><span data-ttu-id="8dd29-173">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8dd29-173">Related topics</span></span>

[<span data-ttu-id="8dd29-174">Pacchetti di criteri di Microsoft Teams per l'istruzione per amministratori</span><span class="sxs-lookup"><span data-stu-id="8dd29-174">Microsoft Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
