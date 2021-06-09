---
title: Gestire i pacchetti di criteri in Microsoft Teams
author: cichur
ms.author: v-cichur
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
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.policypackages.overview
- seo-marvel-apr2020
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come usare e gestire i pacchetti di criteri in Microsoft Teams per semplificare, semplificare e garantire la coerenza durante la gestione dei criteri per gruppi di utenti.
ms.openlocfilehash: 63900f301a8b3a48a8c17c6278808cd52e2445da
ms.sourcegitcommit: 8ad05b37c0b714adb069bc2503e88366ab75c57d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/07/2021
ms.locfileid: "52810176"
---
# <a name="manage-policy-packages-in-microsoft-teams"></a><span data-ttu-id="c2640-103">Gestire i pacchetti di criteri in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c2640-103">Manage policy packages in Microsoft Teams</span></span>

<span data-ttu-id="c2640-104">Un Pacchetto di criteri in Microsoft Teams è una raccolta di criteri e impostazioni predefiniti da assegnare agli utenti con ruoli simili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c2640-104">A policy package in Microsoft Teams is a collection of predefined policies and policy settings that you can assign to users who have similar roles in your organization.</span></span> <span data-ttu-id="c2640-105">Sono stati creati pacchetti di criteri per semplificare, semplificare e garantire la coerenza durante la gestione dei criteri per gruppi di utenti all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c2640-105">We built policy packages to simplify, streamline, and help provide consistency when managing policies for groups of users across your organization.</span></span>  

<span data-ttu-id="c2640-106">È possibile usare i [pacchetti di criteri inclusi in Teams](#policy-packages-included-in-teams) o creare pacchetti di criteri [personalizzati.](#custom-policy-packages)</span><span class="sxs-lookup"><span data-stu-id="c2640-106">You can use the [policy packages included in Teams](#policy-packages-included-in-teams) or [create your own custom policy packages](#custom-policy-packages).</span></span>

:::image type="content" source="media/policy-packages-admin-center.png" alt-text="Screenshot della pagina Pacchetti di criteri nell'interfaccia di amministrazione":::

<span data-ttu-id="c2640-108">È possibile personalizzare le impostazioni dei criteri in un pacchetto di criteri in base alle esigenze degli utenti.</span><span class="sxs-lookup"><span data-stu-id="c2640-108">You can customize the settings of the policies in a policy package to suit the needs of your users.</span></span> <span data-ttu-id="c2640-109">Quando si modificano le impostazioni dei criteri in un pacchetto, tutti gli utenti assegnati al pacchetto ottengono le impostazioni aggiornate.</span><span class="sxs-lookup"><span data-stu-id="c2640-109">When you change the settings of policies in a package, all users who are assigned to that package get the updated settings.</span></span> <span data-ttu-id="c2640-110">Per gestire i pacchetti di criteri, usare l'interfaccia Microsoft Teams di amministrazione o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c2640-110">You manage policy packages by using the Microsoft Teams admin center or PowerShell.</span></span>

> [!NOTE]
> <span data-ttu-id="c2640-111">Ogni utente richiederà il componente aggiuntivo Advanced Communications per ricevere un'assegnazione di pacchetti di criteri personalizzati.</span><span class="sxs-lookup"><span data-stu-id="c2640-111">Each user will require the Advanced Communications add-on in order to receive a custom policy package assignment.</span></span> <span data-ttu-id="c2640-112">Per altre informazioni, vedere [Componente aggiuntivo Comunicazioni avanzate per Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span><span class="sxs-lookup"><span data-stu-id="c2640-112">For more information, see [Advanced Communications add-on for Microsoft Teams](/microsoftteams/teams-add-on-licensing/advanced-communications).</span></span>

## <a name="what-is-a-policy-package"></a><span data-ttu-id="c2640-113">Che cos'è un pacchetto di criteri?</span><span class="sxs-lookup"><span data-stu-id="c2640-113">What is a policy package?</span></span>

<span data-ttu-id="c2640-114">I pacchetti di criteri consentono di controllare Teams funzionalità che si vogliono consentire o limitare per set specifici di persone all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c2640-114">Policy packages let you control Teams features that you want to allow or restrict for specific sets of people across your organization.</span></span> <span data-ttu-id="c2640-115">Ogni pacchetto di criteri in Teams è progettato in base a un ruolo utente e include criteri predefiniti e impostazioni dei criteri che supportano le attività di collaborazione e comunicazione tipiche per quel ruolo.</span><span class="sxs-lookup"><span data-stu-id="c2640-115">Each policy package in Teams is designed around a user role and includes predefined policies and policy settings that support the collaboration and communication activities that are typical for that role.</span></span>

<span data-ttu-id="c2640-116">I pacchetti di criteri supportano i Teams seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2640-116">Policy packages support the following Teams policy types:</span></span>

- <span data-ttu-id="c2640-117">Criteri di messaggistica</span><span class="sxs-lookup"><span data-stu-id="c2640-117">Messaging policy</span></span>
- <span data-ttu-id="c2640-118">Criterio di riunione</span><span class="sxs-lookup"><span data-stu-id="c2640-118">Meeting policy</span></span>
- <span data-ttu-id="c2640-119">Criteri di configurazione delle app</span><span class="sxs-lookup"><span data-stu-id="c2640-119">App setup policy</span></span>
- <span data-ttu-id="c2640-120">Criteri di chiamata</span><span class="sxs-lookup"><span data-stu-id="c2640-120">Calling policy</span></span>
- <span data-ttu-id="c2640-121">Criteri per gli eventi live</span><span class="sxs-lookup"><span data-stu-id="c2640-121">Live events policy</span></span>

## <a name="policy-packages-included-in-teams"></a><span data-ttu-id="c2640-122">Pacchetti di criteri inclusi in Teams</span><span class="sxs-lookup"><span data-stu-id="c2640-122">Policy packages included in Teams</span></span>

<span data-ttu-id="c2640-123">Teams attualmente include i pacchetti di criteri seguenti.</span><span class="sxs-lookup"><span data-stu-id="c2640-123">Teams currently includes the following policy packages.</span></span>

| <span data-ttu-id="c2640-124">Nome pacchetto</span><span class="sxs-lookup"><span data-stu-id="c2640-124">Package name</span></span> | <span data-ttu-id="c2640-125">Descrizione</span><span class="sxs-lookup"><span data-stu-id="c2640-125">Description</span></span> |
|---------|---------|
|<span data-ttu-id="c2640-126">Istruzione (studente di istruzione superiore)</span><span class="sxs-lookup"><span data-stu-id="c2640-126">Education (Higher education student)</span></span>    |<span data-ttu-id="c2640-127">Crea un set di criteri e impostazioni dei criteri che si applicano agli studenti dell'istruzione superiore.</span><span class="sxs-lookup"><span data-stu-id="c2640-127">Creates a set of policies and policy settings that apply to higher education students.</span></span>|
|<span data-ttu-id="c2640-128">Istruzione (studente della scuola primaria)</span><span class="sxs-lookup"><span data-stu-id="c2640-128">Education (Primary school student)</span></span>   |<span data-ttu-id="c2640-129">Crea un set di criteri e impostazioni dei criteri che si applicano agli studenti primari.</span><span class="sxs-lookup"><span data-stu-id="c2640-129">Creates a set of policies and policy settings that apply to primary students.</span></span>|
|<span data-ttu-id="c2640-130">Istruzione (studente di scuola secondaria)</span><span class="sxs-lookup"><span data-stu-id="c2640-130">Education (Secondary school student)</span></span>    |<span data-ttu-id="c2640-131">Crea un set di criteri e impostazioni dei criteri che si applicano agli studenti secondari.</span><span class="sxs-lookup"><span data-stu-id="c2640-131">Creates a set of policies and policy settings that apply to secondary students.</span></span>         |
|<span data-ttu-id="c2640-132">Istruzione (docente)</span><span class="sxs-lookup"><span data-stu-id="c2640-132">Education (Teacher)</span></span>    |<span data-ttu-id="c2640-133">Crea un set di criteri e impostazioni dei criteri che si applicano ai docenti.</span><span class="sxs-lookup"><span data-stu-id="c2640-133">Creates a set of policies and policy settings that apply to teachers.</span></span>      |
|<span data-ttu-id="c2640-134">Istruzione (docente della scuola primaria che usa l'apprendimento remoto)</span><span class="sxs-lookup"><span data-stu-id="c2640-134">Education (Primary school teacher using remote learning)</span></span>    |<span data-ttu-id="c2640-135">Crea una serie di criteri che si applicano agli insegnanti delle scuole elementari per massimizzare la sicurezza e la collaborazione degli studenti quando si adotta l'apprendimento a distanza.</span><span class="sxs-lookup"><span data-stu-id="c2640-135">Creates a set of policies that apply to primary teachers to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="c2640-136">Istruzione (studente della scuola primaria che usa l'apprendimento remoto)</span><span class="sxs-lookup"><span data-stu-id="c2640-136">Education (Primary school student using remote learning)</span></span>    |<span data-ttu-id="c2640-137">Crea una serie di criteri che si applicano agli studenti delle scuole elementari per massimizzare la sicurezza e la collaborazione degli studenti quando si adotta l'apprendimento a distanza.</span><span class="sxs-lookup"><span data-stu-id="c2640-137">Creates a set of policies that apply to primary students to maximize student safety and collaboration when using remote learning.</span></span>      |
|<span data-ttu-id="c2640-138">Frontline Manager</span><span class="sxs-lookup"><span data-stu-id="c2640-138">Frontline manager</span></span> |<span data-ttu-id="c2640-139">Crea un set di criteri e applica tali impostazioni ai responsabili in prima linea dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c2640-139">Creates a set of policies and applies those settings to Frontline managers in your organization.</span></span> |
|<span data-ttu-id="c2640-140">Operaio in prima linea</span><span class="sxs-lookup"><span data-stu-id="c2640-140">Frontline worker</span></span> |<span data-ttu-id="c2640-141">Crea un set di criteri e applica tali impostazioni ai lavoratori frontline dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c2640-141">Creates a set of policies and applies those settings to Frontline workers in your organization.</span></span> |
|<span data-ttu-id="c2640-142">Operatore sanitario</span><span class="sxs-lookup"><span data-stu-id="c2640-142">Healthcare clinical worker</span></span>  |<span data-ttu-id="c2640-143">Creare un set e impostazioni di criteri che forniscano agli operatori sanitari, ad esempio infermieri, medici e operatori sociali accesso completo alle chat, alle chiamate, alla gestione dei turni e alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="c2640-143">Creates a set of policies and policy settings that give clinical workers such as registered nurses, charge nurses, physicians, and social workers full access to chat, calling, shift management, and meetings.</span></span> |
|<span data-ttu-id="c2640-144">Operatore dell'informazione sanitaria</span><span class="sxs-lookup"><span data-stu-id="c2640-144">Healthcare information worker</span></span>  |<span data-ttu-id="c2640-145">Crea un set di criteri e impostazioni di criteri che forniscono agli operatori dell'informazione, ad esempio personale in ambito IT e finanziario, responsabili della conformità, accesso completo alle chat, alle chiamate e alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="c2640-145">Creates a set of policies and policy settings that give information workers such as IT personnel, informatics staff, finance personnel, and compliance officers, full access to chat, calling, and meetings.</span></span>|
|<span data-ttu-id="c2640-146">Sale per i pazienti nell'organizzazione sanitaria</span><span class="sxs-lookup"><span data-stu-id="c2640-146">Healthcare patient room</span></span>  |<span data-ttu-id="c2640-147">Crea un set di criteri e impostazioni di criteri da applicare alle sale dei pazienti nell'organizzazione sanitaria.</span><span class="sxs-lookup"><span data-stu-id="c2640-147">Creates a set of policies and policy settings that apply to patient rooms in your healthcare organization.</span></span>|
|<span data-ttu-id="c2640-148">Utente small e medium business (Business Voice)</span><span class="sxs-lookup"><span data-stu-id="c2640-148">Small and medium business user (Business Voice)</span></span> |<span data-ttu-id="c2640-149">Crea un criterio di configurazione dell'app che include le app per un'esperienza vocale aziendale.</span><span class="sxs-lookup"><span data-stu-id="c2640-149">Creates an app setup policy that includes the apps for a business voice experience.</span></span>|
|<span data-ttu-id="c2640-150">Utente di piccole e medie imprese (senza Voce aziendale)</span><span class="sxs-lookup"><span data-stu-id="c2640-150">Small and medium business user (without Business Voice)</span></span> |<span data-ttu-id="c2640-151">Crea un criterio di configurazione dell'app pertinente per un utente di piccole e medie Teams utenti (esperienza vocale non aziendale).</span><span class="sxs-lookup"><span data-stu-id="c2640-151">Creates an app setup policy relevant for a small and medium sized business Teams users (non-Business Voice experience).</span></span>
|<span data-ttu-id="c2640-152">Responsabile della sicurezza pubblica</span><span class="sxs-lookup"><span data-stu-id="c2640-152">Public safety officer</span></span>   |<span data-ttu-id="c2640-153">Crea un set di criteri e impostazioni dei criteri che si applicano ai responsabili della sicurezza pubblica nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c2640-153">Creates a set of policies and policy settings that apply to public safety officers in your organization.</span></span>|

> [!NOTE]
> <span data-ttu-id="c2640-154">Nelle versioni future di Teams verranno aggiunti altri pacchetti di criteri, quindi controllare di nuovo le informazioni più aggiornate.</span><span class="sxs-lookup"><span data-stu-id="c2640-154">We'll be adding more policy packages in future releases of Teams, so check back for the most up-to-date information.</span></span>  

<span data-ttu-id="c2640-155">A ogni singolo criterio viene assegnato il nome del pacchetto di criteri, in modo da poter identificare facilmente i criteri collegati a un determinato pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="c2640-155">Each individual policy is given the name of the policy package so you can easily identify the policies that are linked to a policy package.</span></span>
<span data-ttu-id="c2640-156">Ad esempio, quando si assegna il pacchetto di criteri Education (Teacher) agli insegnanti dell'istituto di istruzione, viene creato un criterio denominato Education_Teacher per ogni criterio nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="c2640-156">For example, when you assign the Education (Teacher) policy package to teachers in your school, a policy that's named Education_Teacher is created for each policy in the package.</span></span>

![Screenshot del pacchetto di criteri Education (Teacher)](media/policy-packages-education_teacher.png)

## <a name="custom-policy-packages"></a><span data-ttu-id="c2640-158">Pacchetti di criteri personalizzati</span><span class="sxs-lookup"><span data-stu-id="c2640-158">Custom policy packages</span></span>

<span data-ttu-id="c2640-159">**I pacchetti di criteri personalizzati non sono ancora disponibili per Government Community Cloud (GCC)**</span><span class="sxs-lookup"><span data-stu-id="c2640-159">**Custom policy packages is not yet available for the Government Community Cloud (GCC)**</span></span>

<span data-ttu-id="c2640-160">I pacchetti di criteri personalizzati consentono di raggruppare il proprio set di criteri per gli utenti con ruoli simili nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c2640-160">Custom policy packages let you bundle your own set of policies for users with similar roles in you organization.</span></span> <span data-ttu-id="c2640-161">Creare pacchetti di criteri personalizzati aggiungendo i tipi di criteri e i criteri necessari.</span><span class="sxs-lookup"><span data-stu-id="c2640-161">Create your own policy packages by adding the policy types and policies that you need.</span></span>

<span data-ttu-id="c2640-162">Per creare un nuovo pacchetto di criteri personalizzato:</span><span class="sxs-lookup"><span data-stu-id="c2640-162">To create a new custom policy package:</span></span>

1. <span data-ttu-id="c2640-163">Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione selezionare **Pacchetti di** criteri e quindi fare clic su **Aggiungi.**</span><span class="sxs-lookup"><span data-stu-id="c2640-163">In the left navigation of the Microsoft Teams admin center,  select **Policy packages**, and then click **Add**.</span></span>

    :::image type="content" source="media/policy-packages-add.png" alt-text="Screenshot del pulsante Aggiungi nella pagina Pacchetti criteri nell'interfaccia di amministrazione":::

2. <span data-ttu-id="c2640-165">Immettere un nome e una descrizione per il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="c2640-165">Enter a name and description for your package.</span></span>

    :::image type="content" source="media/policy-packages-add-custom.png" alt-text="Screenshot dell'aggiunta di un nuovo pacchetto di criteri personalizzato":::

3. <span data-ttu-id="c2640-167">Selezionare i tipi di criteri e i nomi dei criteri da includere nel pacchetto.</span><span class="sxs-lookup"><span data-stu-id="c2640-167">Select the policy types and policy names to include in the package.</span></span>

4. <span data-ttu-id="c2640-168">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c2640-168">Click **Save**.</span></span>

## <a name="how-to-use-policy-packages"></a><span data-ttu-id="c2640-169">Come usare i pacchetti di criteri</span><span class="sxs-lookup"><span data-stu-id="c2640-169">How to use policy packages</span></span>

<span data-ttu-id="c2640-170">Di seguito viene descritto come usare i pacchetti di criteri nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c2640-170">The following outlines how to use policy packages in your organization.</span></span>

![Panoramica dell'uso dei pacchetti di criteri](media/manage-policy-packages-overview.png)

- <span data-ttu-id="c2640-172">**[Visualizza:](#view-the-settings-of-a-policy-in-a-policy-package)** visualizzare i criteri in un pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="c2640-172">**[View](#view-the-settings-of-a-policy-in-a-policy-package)**: View the policies in a policy package.</span></span> <span data-ttu-id="c2640-173">Quindi, visualizzare le impostazioni di ogni criterio in un pacchetto prima di assegnare il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="c2640-173">Then, view the settings of each policy in a package before you assign the package.</span></span> <span data-ttu-id="c2640-174">Assicurarsi di aver compreso ogni impostazione.</span><span class="sxs-lookup"><span data-stu-id="c2640-174">Make sure that you understand each setting.</span></span> <span data-ttu-id="c2640-175">Decidere se i valori predefiniti sono appropriati per l'organizzazione o se è necessario modificarli in modo che siano più restrittivi o meno in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c2640-175">Decide whether the predefined values are appropriate for your organization or whether you need to change them to be more restrictive or lenient based on your organization's needs.</span></span>

    <span data-ttu-id="c2640-176">Se un criterio viene eliminato, è comunque possibile visualizzare le impostazioni, ma non modificarle.</span><span class="sxs-lookup"><span data-stu-id="c2640-176">If a policy is deleted, you can still view the settings but you won't be able to change any settings.</span></span> <span data-ttu-id="c2640-177">I criteri eliminati vengono ri-creati con le impostazioni predefinite quando si assegna il pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="c2640-177">A deleted policy is re-created with the predefined settings when you assign the policy package.</span></span>

- <span data-ttu-id="c2640-178">**[Personalizza](#customize-policies-in-a-policy-package)**: personalizzare le impostazioni dei criteri nel pacchetto di criteri in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c2640-178">**[Customize](#customize-policies-in-a-policy-package)**: Customize the settings of policies in the policy package to fit the needs of your organization.</span></span>

- <span data-ttu-id="c2640-179">**[Assegna:](#assign-a-policy-package)** assegnare il pacchetto di criteri agli utenti.</span><span class="sxs-lookup"><span data-stu-id="c2640-179">**[Assign](#assign-a-policy-package)**: Assign the policy package to users.</span></span>  

> [!NOTE]
> <span data-ttu-id="c2640-180">È anche possibile modificare le impostazioni dei criteri in un pacchetto di criteri dopo aver assegnato un pacchetto.</span><span class="sxs-lookup"><span data-stu-id="c2640-180">You can also change the settings of policies in a policy package after you assign a package.</span></span> <span data-ttu-id="c2640-181">Le modifiche apportate alle impostazioni dei criteri vengono applicate automaticamente agli utenti ai quali è assegnato il pacchetto.</span><span class="sxs-lookup"><span data-stu-id="c2640-181">Any changes you make to policy settings are automatically applied to users who are assigned the package.</span></span>

<span data-ttu-id="c2640-182">Ecco i passaggi per visualizzare, assegnare e personalizzare i pacchetti di criteri nell'Microsoft Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="c2640-182">Here are the steps for how to view, assign, and customize policy packages in the Microsoft Teams admin center.</span></span>

### <a name="view-the-settings-of-a-policy-in-a-policy-package"></a><span data-ttu-id="c2640-183">Visualizzare le impostazioni di un criterio in un pacchetto di criteri</span><span class="sxs-lookup"><span data-stu-id="c2640-183">View the settings of a policy in a policy package</span></span>

1. <span data-ttu-id="c2640-184">Nel riquadro di spostamento sinistro dell Microsoft Teams di amministrazione selezionare Pacchetti di criteri **e** quindi selezionare un pacchetto di criteri facendo clic a sinistra del nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="c2640-184">In the left navigation of the Microsoft Teams admin center, select **Policy packages**, and then select a policy package by clicking to the left of the package name.</span></span>

2. <span data-ttu-id="c2640-185">Fare clic sul criterio da visualizzare.</span><span class="sxs-lookup"><span data-stu-id="c2640-185">Click the policy you want to view.</span></span>

### <a name="customize-policies-in-a-policy-package"></a><span data-ttu-id="c2640-186">Personalizzare i criteri in un pacchetto di criteri</span><span class="sxs-lookup"><span data-stu-id="c2640-186">Customize policies in a policy package</span></span>

<span data-ttu-id="c2640-187">È possibile modificare le impostazioni  di un criterio tramite la pagina Pacchetti criteri o passando direttamente alla pagina dei criteri nell'Microsoft Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="c2640-187">You can edit the settings of a policy through the **Policy packages** page or by going directly to the policy page in the Microsoft Teams admin center.</span></span>

1. <span data-ttu-id="c2640-188">Nel riquadro di spostamento sinistro dell'interfaccia Microsoft Teams di amministrazione eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2640-188">In the left navigation of the Microsoft Teams admin center, do one of the following:</span></span>
    - <span data-ttu-id="c2640-189">Fare **clic su Pacchetti** criteri e quindi selezionare il pacchetto di criteri facendo clic a sinistra del nome del pacchetto.</span><span class="sxs-lookup"><span data-stu-id="c2640-189">Click **Policy packages**, and then select the policy package by clicking to the left of the package name.</span></span>
    - <span data-ttu-id="c2640-190">Fare clic sul tipo di criterio.</span><span class="sxs-lookup"><span data-stu-id="c2640-190">Click the policy type.</span></span>  <span data-ttu-id="c2640-191">Ad esempio, fare clic su **Criteri di messaggistica.**</span><span class="sxs-lookup"><span data-stu-id="c2640-191">For example, click **Messaging policies**.</span></span>

2. <span data-ttu-id="c2640-192">Selezionare il criterio da modificare.</span><span class="sxs-lookup"><span data-stu-id="c2640-192">Select the policy you want to edit.</span></span> <span data-ttu-id="c2640-193">I criteri collegati a un pacchetto di criteri hanno lo stesso nome del pacchetto di criteri.</span><span class="sxs-lookup"><span data-stu-id="c2640-193">Policies that are linked to a policy package have the same name as the policy package.</span></span>

3. <span data-ttu-id="c2640-194">Apportare le modifiche desiderate e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="c2640-194">Make the changes that you want, and then click **Save**.</span></span>

### <a name="assign-a-policy-package"></a><span data-ttu-id="c2640-195">Assegnare un pacchetto di criteri</span><span class="sxs-lookup"><span data-stu-id="c2640-195">Assign a policy package</span></span>

<span data-ttu-id="c2640-196">È possibile assegnare un pacchetto di criteri a un singolo utente, a un gruppo o a un batch di utenti.</span><span class="sxs-lookup"><span data-stu-id="c2640-196">You can assign a policy package to an individual user, a group, or a batch of users.</span></span> <span data-ttu-id="c2640-197">Per altre informazioni su come assegnare pacchetti di criteri, vedere [Assegnare pacchetti di criteri a utenti e gruppi.](assign-policy-packages.md)</span><span class="sxs-lookup"><span data-stu-id="c2640-197">For more information on how to assign policy packages, see [Assign policy packages to users and groups](assign-policy-packages.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="c2640-198">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c2640-198">Related topics</span></span>

- [<span data-ttu-id="c2640-199">Assegnare pacchetti di criteri</span><span class="sxs-lookup"><span data-stu-id="c2640-199">Assign policy packages</span></span>](assign-policy-packages.md)
- [<span data-ttu-id="c2640-200">Teams dei criteri per gli amministratori di EDU</span><span class="sxs-lookup"><span data-stu-id="c2640-200">Teams policy packages for EDU admins</span></span>](policy-packages-edu.md)
- [<span data-ttu-id="c2640-201">Pacchetti di criteri di Teams per il settore sanitario</span><span class="sxs-lookup"><span data-stu-id="c2640-201">Teams policy packages for healthcare</span></span>](policy-packages-healthcare.md)
- [<span data-ttu-id="c2640-202">Teams di criteri per enti pubblici</span><span class="sxs-lookup"><span data-stu-id="c2640-202">Teams policy packages for government</span></span>](policy-packages-gov.md)
