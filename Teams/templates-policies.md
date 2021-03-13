---
title: Gestire i modelli di Teams nell'interfaccia di amministrazione
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: yinchang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come gestire i modelli di Teams nell'interfaccia di amministrazione
ms.openlocfilehash: b32be22dc7a57e65c6ec8d901ae6e7b004ce4b6c
ms.sourcegitcommit: 3db994f3d26b05071d84b2004892a2ca2ff26d25
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/13/2021
ms.locfileid: "50765829"
---
# <a name="manage-teams-templates-in-the-admin-center"></a><span data-ttu-id="f2925-103">Gestire i modelli di Teams nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="f2925-103">Manage Teams templates in the admin center</span></span>

<span data-ttu-id="f2925-104">Gestire i modelli di Teams visualizzati dagli utenti finali creando criteri di modelli nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="f2925-104">Manage the Teams templates that your end users see by creating templates policies in the admin center.</span></span> <span data-ttu-id="f2925-105">All'interno di ogni criterio di modello è possibile specificare i modelli da visualizzare o nascondere.</span><span class="sxs-lookup"><span data-stu-id="f2925-105">Within each template policy, you can designate which templates are shown or hidden.</span></span>
<span data-ttu-id="f2925-106">Assegnare utenti diversi a criteri di modello diversi in modo che gli utenti visualizzano solo il sottoinsieme di modelli di Teams specificato.</span><span class="sxs-lookup"><span data-stu-id="f2925-106">Assign different users to different template policies so that your users view only the subset of Teams templates specified.</span></span>

<span data-ttu-id="f2925-107">Questo breve video illustra come gestire i criteri dei modelli.</span><span class="sxs-lookup"><span data-stu-id="f2925-107">Watch this short video to learn how to manage template policies.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWyXL9]

## <a name="create-template-policies-and-assign-available-templates"></a><span data-ttu-id="f2925-108">Creare criteri di modello e assegnare i modelli disponibili</span><span class="sxs-lookup"><span data-stu-id="f2925-108">Create template policies and assign available templates</span></span>

1. <span data-ttu-id="f2925-109">Accedere all'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="f2925-109">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="f2925-110">Espandere Criteri **di Modelli** di  >  **Teams**.</span><span class="sxs-lookup"><span data-stu-id="f2925-110">Expand **Teams** > **Templates policies**.</span></span>

3. <span data-ttu-id="f2925-111">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="f2925-111">Select **Add**.</span></span>

    ![I criteri del modello sono selezionati e l'opzione Aggiungi è evidenziata](media/template-policies-1.png)

1. <span data-ttu-id="f2925-113">Nella sezione **Impostazioni criteri modelli** compilare i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f2925-113">In the **Templates Policies Settings** section, complete the following fields:</span></span>

    - <span data-ttu-id="f2925-114">Nome dei criteri dei modelli</span><span class="sxs-lookup"><span data-stu-id="f2925-114">Templates Policy name</span></span>

    - <span data-ttu-id="f2925-115">Breve descrizione dei criteri dei modelli</span><span class="sxs-lookup"><span data-stu-id="f2925-115">Templates Policy short description</span></span>

2. <span data-ttu-id="f2925-116">Nella tabella **Modelli visualizzabili** selezionare i modelli da nascondere e scegliere **Nascondi.**</span><span class="sxs-lookup"><span data-stu-id="f2925-116">In the **Viewable Templates** table, select the templates you want to hide and select **Hide**.</span></span>

    ![Modelli selezionati con nascondi evidenziato](media/template-policies-2.png)

    <span data-ttu-id="f2925-118">È possibile visualizzare i modelli selezionati per nasconderli nella **tabella Modelli** nascosti.</span><span class="sxs-lookup"><span data-stu-id="f2925-118">You can see the templates you've selected to hide in the **Hidden Templates** table.</span></span>

1. <span data-ttu-id="f2925-119">Per scoprire alcuni modelli, scorrere fino alla **tabella Modelli nascosti.**</span><span class="sxs-lookup"><span data-stu-id="f2925-119">To unhide certain templates, scroll to the **Hidden templates** table.</span></span>

1. <span data-ttu-id="f2925-120">Selezionare i modelli da scoprire e quindi selezionare **Mostra.**</span><span class="sxs-lookup"><span data-stu-id="f2925-120">Select the templates to unhide, and then select **Show**.</span></span>

   ![Modelli selezionati non nascosti](media/template-policies-3.png)

   <span data-ttu-id="f2925-122">I modelli selezionati verranno visualizzati nella **tabella Modelli visualizzabili.**</span><span class="sxs-lookup"><span data-stu-id="f2925-122">The selected templates will appear in your **Viewable templates** table.</span></span>
3. <span data-ttu-id="f2925-123">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f2925-123">Select **Save**.</span></span>

   <span data-ttu-id="f2925-124">I nuovi criteri di modello vengono visualizzati **nell'elenco Criteri** modelli.</span><span class="sxs-lookup"><span data-stu-id="f2925-124">Your new template policy is displayed in the **Templates Policies** list.</span></span>

## <a name="assign-users-to-the-template-policies"></a><span data-ttu-id="f2925-125">Assegnare utenti ai criteri di modello</span><span class="sxs-lookup"><span data-stu-id="f2925-125">Assign users to the template policies</span></span>

<span data-ttu-id="f2925-126">Gli utenti assegnati a un criterio potranno visualizzare solo i modelli visualizzabili all'interno di tale criterio.</span><span class="sxs-lookup"><span data-stu-id="f2925-126">Users assigned to a policy will only be able to view the viewable templates within that policy.</span></span>

1. <span data-ttu-id="f2925-127">In **Criteri modelli** selezionare un criterio e quindi selezionare Gestisci **utenti.**</span><span class="sxs-lookup"><span data-stu-id="f2925-127">From **Templates Policies**, select a policy, and then select **Manage users**.</span></span>

2. <span data-ttu-id="f2925-128">Digitare gli utenti da assegnare a questo criterio.</span><span class="sxs-lookup"><span data-stu-id="f2925-128">Type the users to assign to this policy.</span></span>

   ![assegnare utenti a un criterio di modello](media/template-policies-4.png)

3. <span data-ttu-id="f2925-130">Selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="f2925-130">Select **Apply**.</span></span>

> [!Note]
> <span data-ttu-id="f2925-131">L'applicazione del nuovo criterio per gli utenti finali potrebbe richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="f2925-131">It might take up to 24 hours for your new policy to take effect for end users.</span></span>

## <a name="size-limits-for-template-policies"></a><span data-ttu-id="f2925-132">Limiti delle dimensioni per i criteri di modello</span><span class="sxs-lookup"><span data-stu-id="f2925-132">Size limits for Template policies</span></span>

<span data-ttu-id="f2925-133">È possibile nascondere un massimo di 100 modelli per criterio.</span><span class="sxs-lookup"><span data-stu-id="f2925-133">You can hide a max of 100 templates per policy.</span></span> <span data-ttu-id="f2925-134">Il **pulsante** Nascondi è disabilitato se il criterio specificato contiene già 100 modelli nascosti.</span><span class="sxs-lookup"><span data-stu-id="f2925-134">The **Hide** button is disabled if the given policy already has 100 templates hidden.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="f2925-135">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="f2925-135">Frequently asked questions</span></span>

<span data-ttu-id="f2925-136">**D: È possibile assegnare utenti in batch ai criteri dei modelli di team?**</span><span class="sxs-lookup"><span data-stu-id="f2925-136">**Q: Can I batch assign users to team templates policies?**</span></span>
  
<span data-ttu-id="f2925-137">A: Sì, l'assegnazione in batch per i criteri di modello è in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f2925-137">A: Yes, we support batch assignment for template policy in PowerShell.</span></span> <span data-ttu-id="f2925-138">Il tipo di criterio per questa azione è TeamsTemplatePermissionPolicy.</span><span class="sxs-lookup"><span data-stu-id="f2925-138">The policy type for this action is TeamsTemplatePermissionPolicy.</span></span> [<span data-ttu-id="f2925-139">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="f2925-139">Learn more</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)

<span data-ttu-id="f2925-140">**D: I gruppi possono essere assegnati ai criteri dei modelli di team?**</span><span class="sxs-lookup"><span data-stu-id="f2925-140">**Q: Can Groups be assigned to team templates policies?**</span></span>

<span data-ttu-id="f2925-141">A: Attualmente no.</span><span class="sxs-lookup"><span data-stu-id="f2925-141">A: Currently no.</span></span> <span data-ttu-id="f2925-142">Questa funzionalità sarà disponibile in futuro.</span><span class="sxs-lookup"><span data-stu-id="f2925-142">This functionality will be available in the future.</span></span>

<span data-ttu-id="f2925-143">**D: Se viene creato un nuovo modello, il modello verrà incluso nei criteri?**</span><span class="sxs-lookup"><span data-stu-id="f2925-143">**Q: If a new template is created, will the template be included in my policies?**</span></span>

<span data-ttu-id="f2925-144">A: Tutti i nuovi modelli saranno visibili per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f2925-144">A: Any new templates will be visible by default.</span></span> <span data-ttu-id="f2925-145">È possibile scegliere di nascondere il modello nell'interfaccia di amministrazione nella sezione Criteri modelli.</span><span class="sxs-lookup"><span data-stu-id="f2925-145">You can choose to hide the template in the admin center in the Templates Policies section.</span></span>

<span data-ttu-id="f2925-146">**D: Cosa succede se un modello viene eliminato?**</span><span class="sxs-lookup"><span data-stu-id="f2925-146">**Q: What happens if a template is deleted?**</span></span>

<span data-ttu-id="f2925-147">A: Tutti i modelli eliminati non saranno più presenti nei criteri dei modelli.</span><span class="sxs-lookup"><span data-stu-id="f2925-147">A: Any deleted templates will no longer be present in any templates policies.</span></span>

<span data-ttu-id="f2925-148">**D: È possibile assegnare più utenti a un criterio di modello nell'interfaccia di amministrazione di Teams?**</span><span class="sxs-lookup"><span data-stu-id="f2925-148">**Q: Can I assign multiple users to a template policy in the Teams Admin Center?**</span></span>

<span data-ttu-id="f2925-149">A: Sì.</span><span class="sxs-lookup"><span data-stu-id="f2925-149">A: Yes.</span></span>

1. <span data-ttu-id="f2925-150">Nell'interfaccia di amministrazione passare a **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="f2925-150">In the Admin center, go to **Users**.</span></span>
1. <span data-ttu-id="f2925-151">Nella tabella elenco Utenti selezionare gli utenti da assegnare a un determinato criterio di modelli.</span><span class="sxs-lookup"><span data-stu-id="f2925-151">In the Users list table, select the users you want to assign to a certain templates policy.</span></span>
1. <span data-ttu-id="f2925-152">Selezionare Modifica impostazioni e modificare il campo Criteri modelli.</span><span class="sxs-lookup"><span data-stu-id="f2925-152">Select Edit settings, and change the Templates policies field.</span></span>
1. <span data-ttu-id="f2925-153">Selezionare Applica.</span><span class="sxs-lookup"><span data-stu-id="f2925-153">Select apply.</span></span>
   <span data-ttu-id="f2925-154">Altre informazioni [Su come assegnare criteri agli utenti in Microsoft Teams - Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="f2925-154">Learn more [Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).</span></span>

<span data-ttu-id="f2925-155">**D: Come si visualizzano tutti gli utenti assegnati a un criterio specifico?**</span><span class="sxs-lookup"><span data-stu-id="f2925-155">**Q: How do I view all users assigned to a specific policy?**</span></span>

<span data-ttu-id="f2925-156">A: Nell'interfaccia di amministrazione:</span><span class="sxs-lookup"><span data-stu-id="f2925-156">A: In the Admin center:</span></span>

1. <span data-ttu-id="f2925-157">Passare alla **sezione** Utenti.</span><span class="sxs-lookup"><span data-stu-id="f2925-157">Go to the **Users** section.</span></span>
2. <span data-ttu-id="f2925-158">Selezionare il filtro nella tabella Elenco utenti e filtrare per i criteri del modello teams.</span><span class="sxs-lookup"><span data-stu-id="f2925-158">Select the filter in the Users list table and filter for the teams template policy.</span></span>
3. <span data-ttu-id="f2925-159">Selezionare **Applica**.</span><span class="sxs-lookup"><span data-stu-id="f2925-159">Select **Apply**.</span></span>

![I criteri di modello selezionati e visualizzano gli utenti](media/template-policies-5.png)

<span data-ttu-id="f2925-161">**D: È possibile gestire i criteri dei modelli tramite PowerShell?**</span><span class="sxs-lookup"><span data-stu-id="f2925-161">**Q: Can I manage templates policies via PowerShell?**</span></span>

<span data-ttu-id="f2925-162">A: No, la gestione dei modelli in PowerShell non è supportata.</span><span class="sxs-lookup"><span data-stu-id="f2925-162">A: No, managing templates in PowerShell isn't supported.</span></span>

<span data-ttu-id="f2925-163">**D: I criteri dei modelli sono applicabili all'EDU?**</span><span class="sxs-lookup"><span data-stu-id="f2925-163">**Q: Are templates policies applicable to EDU?**</span></span>

<span data-ttu-id="f2925-164">A: No, i criteri dei modelli per EDU non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="f2925-164">A: No, template policies for EDU isn't supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f2925-165">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f2925-165">Related topics</span></span>

- [<span data-ttu-id="f2925-166">Introduzione ai modelli di team nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="f2925-166">Get started with team templates in the admin center</span></span>](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [<span data-ttu-id="f2925-167">Creare un modello di team personalizzato</span><span class="sxs-lookup"><span data-stu-id="f2925-167">Create a custom team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [<span data-ttu-id="f2925-168">Creare un modello da un team esistente</span><span class="sxs-lookup"><span data-stu-id="f2925-168">Create a template from an existing team</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [<span data-ttu-id="f2925-169">Creare un modello di team da un modello di team esistente</span><span class="sxs-lookup"><span data-stu-id="f2925-169">Create a team template from an existing team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [<span data-ttu-id="f2925-170">Assegnare criteri agli utenti in Microsoft Teams - Microsoft Teams \| Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="f2925-170">Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs</span></span>](https://docs.microsoft.com/microsoftteams/assign-policies)

- [<span data-ttu-id="f2925-171">Assegnare utenti a un criterio in batch</span><span class="sxs-lookup"><span data-stu-id="f2925-171">Batch assign users to a policy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation)
