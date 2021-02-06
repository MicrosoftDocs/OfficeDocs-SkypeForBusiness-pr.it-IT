---
title: Gestire i modelli di team nell'interfaccia di amministrazione
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
description: Informazioni su come gestire i modelli di team nell'interfaccia di amministrazione
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: ef765013541ae740211cc5666da3544f1cd5b528
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125902"
---
# <a name="create-and-manage-teams-templates-in-the-admin-center"></a><span data-ttu-id="c66ea-103">Creare e gestire i modelli di team nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="c66ea-103">Create and manage Teams templates in the admin center</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="c66ea-104">Gestisci i modelli di team che vengono visualizzati agli utenti finali creando criteri per i modelli nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="c66ea-104">Manage the Teams templates that are shown to your end users by creating templates policies in the admin center.</span></span> <span data-ttu-id="c66ea-105">All'interno di ogni criterio modello è possibile specificare i modelli visualizzati o nascosti.</span><span class="sxs-lookup"><span data-stu-id="c66ea-105">Within each template policy, you can designate which templates are shown or hidden.</span></span>
<span data-ttu-id="c66ea-106">Assegnare diversi utenti a criteri di modello diversi, in modo che gli utenti visualizzano solo il sottoinsieme dei modelli di team specificati.</span><span class="sxs-lookup"><span data-stu-id="c66ea-106">Assign different users to different template policies so that your users only view the subset of Teams templates specified.</span></span>

## <a name="create-template-policies-and-assign-available-templates"></a><span data-ttu-id="c66ea-107">Creare criteri modello e assegnare modelli disponibili</span><span class="sxs-lookup"><span data-stu-id="c66ea-107">Create template policies and assign available templates</span></span>

1. <span data-ttu-id="c66ea-108">Accedere all'interfaccia di amministrazione di teams.</span><span class="sxs-lookup"><span data-stu-id="c66ea-108">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="c66ea-109">Espandere i criteri dei modelli di **Teams**  >  .</span><span class="sxs-lookup"><span data-stu-id="c66ea-109">Expand **Teams** > **Templates policies**.</span></span>

3. <span data-ttu-id="c66ea-110">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="c66ea-110">Select **Add**.</span></span>

    ![I criteri modello sono selezionati e Aggiungi evidenziato](media/template-policies-1.png)

1. <span data-ttu-id="c66ea-112">Nella sezione **Impostazioni criteri modelli** completare i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="c66ea-112">In the **Templates Policies Settings** section, complete the following fields:</span></span>

    - <span data-ttu-id="c66ea-113">Nome criterio modelli</span><span class="sxs-lookup"><span data-stu-id="c66ea-113">Templates Policy name</span></span>

    - <span data-ttu-id="c66ea-114">Descrizione breve dei criteri per i modelli</span><span class="sxs-lookup"><span data-stu-id="c66ea-114">Templates Policy short description</span></span>

2. <span data-ttu-id="c66ea-115">Nella tabella **modelli visualizzabili** selezionare i modelli che si desidera nascondere e selezionare **Nascondi**.</span><span class="sxs-lookup"><span data-stu-id="c66ea-115">In the **Viewable Templates** table, select the templates you want to hide and select **Hide**.</span></span>

    ![I modelli selezionati con Nascondi evidenziati](media/template-policies-2.png)

    <span data-ttu-id="c66ea-117">È possibile visualizzare i modelli selezionati per nasconderli nella tabella **modelli nascosti** .</span><span class="sxs-lookup"><span data-stu-id="c66ea-117">You can see the templates you've selected to hide in the **Hidden Templates** table.</span></span>

1. <span data-ttu-id="c66ea-118">Per scoprire alcuni modelli, scorrere fino alla tabella **modelli nascosti** .</span><span class="sxs-lookup"><span data-stu-id="c66ea-118">To unhide certain templates, scroll to the **Hidden templates** table.</span></span>

1. <span data-ttu-id="c66ea-119">Selezionare i modelli da scoprire e quindi selezionare **Mostra**.</span><span class="sxs-lookup"><span data-stu-id="c66ea-119">Select the templates to unhide, and then select **Show**.</span></span>

   ![I modelli selezionati con Nascondi evidenziati](media/template-policies-3.png)

   <span data-ttu-id="c66ea-121">I modelli selezionati verranno visualizzati nella tabella **modelli visualizzabili** .</span><span class="sxs-lookup"><span data-stu-id="c66ea-121">The selected templates will appear in your **Viewable templates** table.</span></span>
3. <span data-ttu-id="c66ea-122">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c66ea-122">Select **Save**.</span></span>

   <span data-ttu-id="c66ea-123">Il nuovo criterio modello viene visualizzato nell'elenco **criteri modelli** .</span><span class="sxs-lookup"><span data-stu-id="c66ea-123">Your new template policy is displayed in the **Templates Policies** list.</span></span>

## <a name="assign-users-to-the-template-policies"></a><span data-ttu-id="c66ea-124">Assegnare utenti ai criteri modello</span><span class="sxs-lookup"><span data-stu-id="c66ea-124">Assign users to the template policies</span></span>

<span data-ttu-id="c66ea-125">Gli utenti assegnati a un criterio saranno in grado di visualizzare solo i modelli visualizzabili all'interno di tale criterio.</span><span class="sxs-lookup"><span data-stu-id="c66ea-125">Users assigned to a policy will only be able to view the viewable templates within that policy.</span></span>

1. <span data-ttu-id="c66ea-126">In **criteri modelli** selezionare un criterio e quindi selezionare **Gestisci utenti**.</span><span class="sxs-lookup"><span data-stu-id="c66ea-126">From **Templates Policies**, select a policy, and then select **Manage users**.</span></span>

2. <span data-ttu-id="c66ea-127">Digitare gli utenti da assegnare a questo criterio.</span><span class="sxs-lookup"><span data-stu-id="c66ea-127">Type the users to assign to this policy.</span></span>

   ![I modelli selezionati con Nascondi evidenziati](media/template-policies-4.png)

3. <span data-ttu-id="c66ea-129">Selezionare **applica**.</span><span class="sxs-lookup"><span data-stu-id="c66ea-129">Select **Apply**.</span></span>

> [!Note]
> <span data-ttu-id="c66ea-130">I nuovi criteri potrebbero richiedere fino a 24 ore per applicare l'effetto agli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="c66ea-130">It might take up to 24 hours for your new policy to take effect for end users.</span></span>

## <a name="size-limits-for-template-policies"></a><span data-ttu-id="c66ea-131">Limiti di dimensione per i criteri modello</span><span class="sxs-lookup"><span data-stu-id="c66ea-131">Size limits for Template policies</span></span>

<span data-ttu-id="c66ea-132">Puoi nascondere un massimo di 100 modelli per ogni criterio.</span><span class="sxs-lookup"><span data-stu-id="c66ea-132">You can hide a max of 100 templates per policy.</span></span> <span data-ttu-id="c66ea-133">Il pulsante **Nascondi** è disabilitato se il criterio indicato contiene già modelli di 100 nascosti.</span><span class="sxs-lookup"><span data-stu-id="c66ea-133">The **Hide** button is disabled if the given policy already has 100 templates hidden.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="c66ea-134">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="c66ea-134">Frequently asked questions</span></span>

<span data-ttu-id="c66ea-135">**D: è possibile assegnare un batch agli utenti ai criteri dei modelli di Team?**</span><span class="sxs-lookup"><span data-stu-id="c66ea-135">**Q: Can I batch assign users to team templates policies?**</span></span>
  
<span data-ttu-id="c66ea-136">A: Sì, sosteniamo l'assegnazione in batch per i criteri di modello in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c66ea-136">A: Yes, we support batch assignment for template policy in PowerShell.</span></span> <span data-ttu-id="c66ea-137">Il tipo di criterio per questa azione è TeamsTemplatePermissionPolicy.</span><span class="sxs-lookup"><span data-stu-id="c66ea-137">The policy type for this action is TeamsTemplatePermissionPolicy.</span></span> [<span data-ttu-id="c66ea-138">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="c66ea-138">Learn more</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)

<span data-ttu-id="c66ea-139">**D: i gruppi possono essere assegnati ai criteri dei modelli di Team?**</span><span class="sxs-lookup"><span data-stu-id="c66ea-139">**Q: Can Groups be assigned to team templates policies?**</span></span>

<span data-ttu-id="c66ea-140">A: attualmente No.</span><span class="sxs-lookup"><span data-stu-id="c66ea-140">A: Currently no.</span></span> <span data-ttu-id="c66ea-141">Questa funzionalità sarà disponibile in futuro.</span><span class="sxs-lookup"><span data-stu-id="c66ea-141">This functionality will be available in the future.</span></span>

<span data-ttu-id="c66ea-142">**D: se viene creato un nuovo modello, il modello verrà incluso nei miei criteri?**</span><span class="sxs-lookup"><span data-stu-id="c66ea-142">**Q: If a new template is created, will the template be included in my policies?**</span></span>

<span data-ttu-id="c66ea-143">A: qualsiasi nuovo modello sarà visibile per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="c66ea-143">A: Any new templates will be visible by default.</span></span> <span data-ttu-id="c66ea-144">È possibile scegliere di nascondere il modello nell'interfaccia di amministrazione nella sezione criteri modelli.</span><span class="sxs-lookup"><span data-stu-id="c66ea-144">You can choose to hide the template in the admin center in the Templates Policies section.</span></span>

<span data-ttu-id="c66ea-145">**D: cosa succede se un modello viene eliminato?**</span><span class="sxs-lookup"><span data-stu-id="c66ea-145">**Q: What happens if a template is deleted?**</span></span>

<span data-ttu-id="c66ea-146">A: i modelli eliminati non saranno più presenti nei criteri per i modelli.</span><span class="sxs-lookup"><span data-stu-id="c66ea-146">A: Any deleted templates will no longer be present in any templates policies.</span></span>

<span data-ttu-id="c66ea-147">**D: è possibile assegnare più utenti a un criterio modello nell'interfaccia di amministrazione di Teams?**</span><span class="sxs-lookup"><span data-stu-id="c66ea-147">**Q: Can I assign multiple users to a template policy in the Teams Admin Center?**</span></span>

<span data-ttu-id="c66ea-148">A: Sì.</span><span class="sxs-lookup"><span data-stu-id="c66ea-148">A: Yes.</span></span>

1. <span data-ttu-id="c66ea-149">Nell'interfaccia di amministrazione accedere a **utenti**.</span><span class="sxs-lookup"><span data-stu-id="c66ea-149">In the Admin center, go to **Users**.</span></span>
1. <span data-ttu-id="c66ea-150">Nella tabella elenco utenti selezionare gli utenti che si desidera assegnare a determinati criteri dei modelli.</span><span class="sxs-lookup"><span data-stu-id="c66ea-150">In the Users list table, select the users you want to assign to a certain templates policy.</span></span>
1. <span data-ttu-id="c66ea-151">Selezionare Modifica impostazioni e modificare il campo criteri modelli.</span><span class="sxs-lookup"><span data-stu-id="c66ea-151">Select Edit settings, and change the Templates policies field.</span></span>
1. <span data-ttu-id="c66ea-152">Selezionare Applica.</span><span class="sxs-lookup"><span data-stu-id="c66ea-152">Select apply.</span></span>
   <span data-ttu-id="c66ea-153">Altre informazioni [assegnare criteri agli utenti in Microsoft teams-Microsoft teams Microsoft \| docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).</span><span class="sxs-lookup"><span data-stu-id="c66ea-153">Learn more [Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).</span></span>

<span data-ttu-id="c66ea-154">**D: come si visualizzano tutti gli utenti assegnati a un criterio specifico?**</span><span class="sxs-lookup"><span data-stu-id="c66ea-154">**Q: How do I view all users assigned to a specific policy?**</span></span>

<span data-ttu-id="c66ea-155">A: nell'interfaccia di amministrazione:</span><span class="sxs-lookup"><span data-stu-id="c66ea-155">A: In the Admin center:</span></span>

1. <span data-ttu-id="c66ea-156">Accedere alla sezione **utenti** .</span><span class="sxs-lookup"><span data-stu-id="c66ea-156">Go to the **Users** section.</span></span>
2. <span data-ttu-id="c66ea-157">Selezionare il filtro nella tabella elenco utenti e filtrare per i criteri del modello teams.</span><span class="sxs-lookup"><span data-stu-id="c66ea-157">Select the filter in the Users list table and filter for the teams template policy.</span></span>
3. <span data-ttu-id="c66ea-158">Selezionare **applica**.</span><span class="sxs-lookup"><span data-stu-id="c66ea-158">Select **Apply**.</span></span>

![I modelli selezionati con Nascondi evidenziati](media/template-policies-5.png)

<span data-ttu-id="c66ea-160">**D: è possibile gestire I criteri dei modelli tramite PowerShell?**</span><span class="sxs-lookup"><span data-stu-id="c66ea-160">**Q: Can I manage templates policies via PowerShell?**</span></span>

<span data-ttu-id="c66ea-161">A: No, non è supportato.</span><span class="sxs-lookup"><span data-stu-id="c66ea-161">A: No, this isn't supported.</span></span>

<span data-ttu-id="c66ea-162">**D: i criteri per i modelli sono applicabili a EDU?**</span><span class="sxs-lookup"><span data-stu-id="c66ea-162">**Q: Are templates policies applicable to EDU?**</span></span>

<span data-ttu-id="c66ea-163">A: No, non è supportato.</span><span class="sxs-lookup"><span data-stu-id="c66ea-163">A: No, this isn't supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c66ea-164">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c66ea-164">Related topics</span></span>

- [<span data-ttu-id="c66ea-165">Introduzione ai modelli di team nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="c66ea-165">Get started with team templates in the admin center</span></span>](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [<span data-ttu-id="c66ea-166">Creare un modello di team personalizzato</span><span class="sxs-lookup"><span data-stu-id="c66ea-166">Create a custom team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [<span data-ttu-id="c66ea-167">Creare un modello da un team esistente</span><span class="sxs-lookup"><span data-stu-id="c66ea-167">Create a template from an existing team</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [<span data-ttu-id="c66ea-168">Creare un modello di team da un modello di Team esistente</span><span class="sxs-lookup"><span data-stu-id="c66ea-168">Create a team template from an existing team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [<span data-ttu-id="c66ea-169">Assegnare criteri agli utenti in Microsoft teams-Microsoft teams Microsoft \| docs</span><span class="sxs-lookup"><span data-stu-id="c66ea-169">Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs</span></span>](https://docs.microsoft.com/microsoftteams/assign-policies)

- [<span data-ttu-id="c66ea-170">TeamsTemplatePermissionPolicy</span><span class="sxs-lookup"><span data-stu-id="c66ea-170">TeamsTemplatePermissionPolicy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)