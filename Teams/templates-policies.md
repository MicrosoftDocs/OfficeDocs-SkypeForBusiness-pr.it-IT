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
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: bcb99538ebd129e02e511c8260dc3bfa101bff9d
ms.sourcegitcommit: 113f587a1c09d42b7394ba1195c32cb054bdf31c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2021
ms.locfileid: "50507969"
---
# <a name="create-and-manage-teams-templates-in-the-admin-center"></a><span data-ttu-id="84121-103">Creare e gestire modelli di Teams nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="84121-103">Create and manage Teams templates in the admin center</span></span>

<span data-ttu-id="84121-104">Gestire i modelli di Teams visualizzati dagli utenti finali creando criteri di modelli nell'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="84121-104">Manage the Teams templates that your end users see by creating templates policies in the admin center.</span></span> <span data-ttu-id="84121-105">All'interno di ogni criterio di modello è possibile specificare quali modelli visualizzare o nascondere.</span><span class="sxs-lookup"><span data-stu-id="84121-105">Within each template policy, you can designate which templates are shown or hidden.</span></span>
<span data-ttu-id="84121-106">Assegnare utenti diversi a criteri di modello diversi in modo che gli utenti visualizzano solo il sottoinsieme di modelli di Teams specificato.</span><span class="sxs-lookup"><span data-stu-id="84121-106">Assign different users to different template policies so that your users only view the subset of Teams templates specified.</span></span>

## <a name="create-template-policies-and-assign-available-templates"></a><span data-ttu-id="84121-107">Creare criteri di modello e assegnare i modelli disponibili</span><span class="sxs-lookup"><span data-stu-id="84121-107">Create template policies and assign available templates</span></span>

1. <span data-ttu-id="84121-108">Accedere all'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="84121-108">Sign in to the Teams admin center.</span></span>

2. <span data-ttu-id="84121-109">Espandere i **criteri dei** modelli di  >  **Teams.**</span><span class="sxs-lookup"><span data-stu-id="84121-109">Expand **Teams** > **Templates policies**.</span></span>

3. <span data-ttu-id="84121-110">Selezionare **Aggiungi**.</span><span class="sxs-lookup"><span data-stu-id="84121-110">Select **Add**.</span></span>

    ![I criteri di modello sono selezionati e l'opzione Aggiungi è evidenziata](media/template-policies-1.png)

1. <span data-ttu-id="84121-112">Nella sezione **Impostazioni criteri modello** completare i campi seguenti:</span><span class="sxs-lookup"><span data-stu-id="84121-112">In the **Templates Policies Settings** section, complete the following fields:</span></span>

    - <span data-ttu-id="84121-113">Nome criterio modelli</span><span class="sxs-lookup"><span data-stu-id="84121-113">Templates Policy name</span></span>

    - <span data-ttu-id="84121-114">Descrizione breve dei criteri dei modelli</span><span class="sxs-lookup"><span data-stu-id="84121-114">Templates Policy short description</span></span>

2. <span data-ttu-id="84121-115">Nella tabella **Modelli visualizzabili** selezionare i modelli da nascondere e **quindi** Nascondi.</span><span class="sxs-lookup"><span data-stu-id="84121-115">In the **Viewable Templates** table, select the templates you want to hide and select **Hide**.</span></span>

    ![Modelli selezionati con Nascondi evidenziato](media/template-policies-2.png)

    <span data-ttu-id="84121-117">È possibile vedere i modelli selezionati per nasconderli nella **tabella Modelli** nascosti.</span><span class="sxs-lookup"><span data-stu-id="84121-117">You can see the templates you've selected to hide in the **Hidden Templates** table.</span></span>

1. <span data-ttu-id="84121-118">Per scoprire alcuni modelli, scorrere fino alla **tabella Dei modelli** nascosti.</span><span class="sxs-lookup"><span data-stu-id="84121-118">To unhide certain templates, scroll to the **Hidden templates** table.</span></span>

1. <span data-ttu-id="84121-119">Selezionare i modelli da scoprire e quindi **selezionare Mostra.**</span><span class="sxs-lookup"><span data-stu-id="84121-119">Select the templates to unhide, and then select **Show**.</span></span>

   ![I modelli selezionati che non sono nascosti](media/template-policies-3.png)

   <span data-ttu-id="84121-121">I modelli selezionati verranno visualizzati nella **tabella dei modelli visualizzabili.**</span><span class="sxs-lookup"><span data-stu-id="84121-121">The selected templates will appear in your **Viewable templates** table.</span></span>
3. <span data-ttu-id="84121-122">Selezionare **Salva**.</span><span class="sxs-lookup"><span data-stu-id="84121-122">Select **Save**.</span></span>

   <span data-ttu-id="84121-123">Il nuovo criterio modello viene visualizzato **nell'elenco Criteri** modelli.</span><span class="sxs-lookup"><span data-stu-id="84121-123">Your new template policy is displayed in the **Templates Policies** list.</span></span>

## <a name="assign-users-to-the-template-policies"></a><span data-ttu-id="84121-124">Assegnare utenti ai criteri di modello</span><span class="sxs-lookup"><span data-stu-id="84121-124">Assign users to the template policies</span></span>

<span data-ttu-id="84121-125">Gli utenti assegnati a un criterio potranno solo visualizzare i modelli visualizzabili all'interno di tale criterio.</span><span class="sxs-lookup"><span data-stu-id="84121-125">Users assigned to a policy will only be able to view the viewable templates within that policy.</span></span>

1. <span data-ttu-id="84121-126">In **Criteri modelli** selezionare un criterio e quindi Selezionare Gestisci **utenti.**</span><span class="sxs-lookup"><span data-stu-id="84121-126">From **Templates Policies**, select a policy, and then select **Manage users**.</span></span>

2. <span data-ttu-id="84121-127">Digitare gli utenti da assegnare al criterio.</span><span class="sxs-lookup"><span data-stu-id="84121-127">Type the users to assign to this policy.</span></span>

   ![assegnare utenti a un criterio modello](media/template-policies-4.png)

3. <span data-ttu-id="84121-129">Selezionare **Applica.**</span><span class="sxs-lookup"><span data-stu-id="84121-129">Select **Apply**.</span></span>

> [!Note]
> <span data-ttu-id="84121-130">L'applicazione del nuovo criterio per gli utenti finali può richiedere fino a 24 ore.</span><span class="sxs-lookup"><span data-stu-id="84121-130">It might take up to 24 hours for your new policy to take effect for end users.</span></span>

## <a name="size-limits-for-template-policies"></a><span data-ttu-id="84121-131">Limiti di dimensioni per i criteri di modello</span><span class="sxs-lookup"><span data-stu-id="84121-131">Size limits for Template policies</span></span>

<span data-ttu-id="84121-132">È possibile nascondere un massimo di 100 modelli per criterio.</span><span class="sxs-lookup"><span data-stu-id="84121-132">You can hide a max of 100 templates per policy.</span></span> <span data-ttu-id="84121-133">Il **pulsante** Nascondi è disabilitato se il criterio specificato contiene già 100 modelli nascosti.</span><span class="sxs-lookup"><span data-stu-id="84121-133">The **Hide** button is disabled if the given policy already has 100 templates hidden.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="84121-134">Domande frequenti</span><span class="sxs-lookup"><span data-stu-id="84121-134">Frequently asked questions</span></span>

<span data-ttu-id="84121-135">**D: È possibile assegnare gli utenti in batch ai criteri dei modelli del team?**</span><span class="sxs-lookup"><span data-stu-id="84121-135">**Q: Can I batch assign users to team templates policies?**</span></span>
  
<span data-ttu-id="84121-136">A: Sì, sono supportate le assegnazioni batch per i criteri di modello in PowerShell.</span><span class="sxs-lookup"><span data-stu-id="84121-136">A: Yes, we support batch assignment for template policy in PowerShell.</span></span> <span data-ttu-id="84121-137">Il tipo di criterio per questa azione è TeamsTemplatePermissionPolicy.</span><span class="sxs-lookup"><span data-stu-id="84121-137">The policy type for this action is TeamsTemplatePermissionPolicy.</span></span> [<span data-ttu-id="84121-138">Ulteriori informazioni</span><span class="sxs-lookup"><span data-stu-id="84121-138">Learn more</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)

<span data-ttu-id="84121-139">**D: I gruppi possono essere assegnati ai criteri dei modelli del team?**</span><span class="sxs-lookup"><span data-stu-id="84121-139">**Q: Can Groups be assigned to team templates policies?**</span></span>

<span data-ttu-id="84121-140">A: Attualmente no.</span><span class="sxs-lookup"><span data-stu-id="84121-140">A: Currently no.</span></span> <span data-ttu-id="84121-141">Questa funzionalità sarà disponibile in futuro.</span><span class="sxs-lookup"><span data-stu-id="84121-141">This functionality will be available in the future.</span></span>

<span data-ttu-id="84121-142">**D: Se viene creato un nuovo modello, verrà incluso nei criteri?**</span><span class="sxs-lookup"><span data-stu-id="84121-142">**Q: If a new template is created, will the template be included in my policies?**</span></span>

<span data-ttu-id="84121-143">A: Tutti i nuovi modelli saranno visibili per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="84121-143">A: Any new templates will be visible by default.</span></span> <span data-ttu-id="84121-144">È possibile scegliere di nascondere il modello nell'interfaccia di amministrazione nella sezione Criteri modelli.</span><span class="sxs-lookup"><span data-stu-id="84121-144">You can choose to hide the template in the admin center in the Templates Policies section.</span></span>

<span data-ttu-id="84121-145">**D: Cosa succede se un modello viene eliminato?**</span><span class="sxs-lookup"><span data-stu-id="84121-145">**Q: What happens if a template is deleted?**</span></span>

<span data-ttu-id="84121-146">A: I modelli eliminati non saranno più presenti nei criteri dei modelli.</span><span class="sxs-lookup"><span data-stu-id="84121-146">A: Any deleted templates will no longer be present in any templates policies.</span></span>

<span data-ttu-id="84121-147">**D: È possibile assegnare più utenti a un criterio di modello nell'interfaccia di amministrazione di Teams?**</span><span class="sxs-lookup"><span data-stu-id="84121-147">**Q: Can I assign multiple users to a template policy in the Teams Admin Center?**</span></span>

<span data-ttu-id="84121-148">A: Sì.</span><span class="sxs-lookup"><span data-stu-id="84121-148">A: Yes.</span></span>

1. <span data-ttu-id="84121-149">Nell'interfaccia di amministrazione passare a **Utenti.**</span><span class="sxs-lookup"><span data-stu-id="84121-149">In the Admin center, go to **Users**.</span></span>
1. <span data-ttu-id="84121-150">Nella tabella dell'elenco Utenti selezionare gli utenti da assegnare a un determinato criterio di modello.</span><span class="sxs-lookup"><span data-stu-id="84121-150">In the Users list table, select the users you want to assign to a certain templates policy.</span></span>
1. <span data-ttu-id="84121-151">Selezionare Modifica impostazioni e modificare il campo Criteri modelli.</span><span class="sxs-lookup"><span data-stu-id="84121-151">Select Edit settings, and change the Templates policies field.</span></span>
1. <span data-ttu-id="84121-152">Selezionare Applica.</span><span class="sxs-lookup"><span data-stu-id="84121-152">Select apply.</span></span>
   <span data-ttu-id="84121-153">Altre informazioni [sull'assegnazione di criteri agli utenti in Microsoft Teams - Microsoft Teams \| Microsoft Docs.](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users)</span><span class="sxs-lookup"><span data-stu-id="84121-153">Learn more [Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-batch-of-users).</span></span>

<span data-ttu-id="84121-154">**D: Come si visualizzano tutti gli utenti assegnati a un criterio specifico?**</span><span class="sxs-lookup"><span data-stu-id="84121-154">**Q: How do I view all users assigned to a specific policy?**</span></span>

<span data-ttu-id="84121-155">A: Nell'interfaccia di amministrazione:</span><span class="sxs-lookup"><span data-stu-id="84121-155">A: In the Admin center:</span></span>

1. <span data-ttu-id="84121-156">Passare alla **sezione** Utenti.</span><span class="sxs-lookup"><span data-stu-id="84121-156">Go to the **Users** section.</span></span>
2. <span data-ttu-id="84121-157">Selezionare il filtro nella tabella dell'elenco Utenti e filtrare in base ai criteri del modello di teams.</span><span class="sxs-lookup"><span data-stu-id="84121-157">Select the filter in the Users list table and filter for the teams template policy.</span></span>
3. <span data-ttu-id="84121-158">Selezionare **Applica.**</span><span class="sxs-lookup"><span data-stu-id="84121-158">Select **Apply**.</span></span>

![Criteri del modello selezionati e visualizzazione degli utenti](media/template-policies-5.png)

<span data-ttu-id="84121-160">**D: È possibile gestire i criteri dei modelli con PowerShell?**</span><span class="sxs-lookup"><span data-stu-id="84121-160">**Q: Can I manage templates policies via PowerShell?**</span></span>

<span data-ttu-id="84121-161">A: No, la gestione dei modelli in PowerShell non è supportata.</span><span class="sxs-lookup"><span data-stu-id="84121-161">A: No, managing templates in PowerShell isn't supported.</span></span>

<span data-ttu-id="84121-162">**D: I criteri dei modelli sono applicabili all'EDU?**</span><span class="sxs-lookup"><span data-stu-id="84121-162">**Q: Are templates policies applicable to EDU?**</span></span>

<span data-ttu-id="84121-163">A: No, i criteri di modello per l'du non sono supportati.</span><span class="sxs-lookup"><span data-stu-id="84121-163">A: No, template policies for EDU isn't supported.</span></span>

## <a name="related-topics"></a><span data-ttu-id="84121-164">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="84121-164">Related topics</span></span>

- [<span data-ttu-id="84121-165">Introduzione ai modelli di team nell'interfaccia di amministrazione</span><span class="sxs-lookup"><span data-stu-id="84121-165">Get started with team templates in the admin center</span></span>](https://docs.microsoft.com/MicrosoftTeams/get-started-with-teams-templates-in-the-admin-console)

- [<span data-ttu-id="84121-166">Creare un modello di team personalizzato</span><span class="sxs-lookup"><span data-stu-id="84121-166">Create a custom team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-a-team-template)

- [<span data-ttu-id="84121-167">Creare un modello da un team esistente</span><span class="sxs-lookup"><span data-stu-id="84121-167">Create a template from an existing team</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-team)

- [<span data-ttu-id="84121-168">Creare un modello di team da un modello di team esistente</span><span class="sxs-lookup"><span data-stu-id="84121-168">Create a team template from an existing team template</span></span>](https://docs.microsoft.com/MicrosoftTeams/create-template-from-existing-template)

- [<span data-ttu-id="84121-169">Assegnare criteri agli utenti in Microsoft Teams - Microsoft Teams \| Microsoft Docs</span><span class="sxs-lookup"><span data-stu-id="84121-169">Assign policies to your users in Microsoft Teams - Microsoft Teams \| Microsoft Docs</span></span>](https://docs.microsoft.com/microsoftteams/assign-policies)

- [<span data-ttu-id="84121-170">Assegnare utenti a un criterio in batch</span><span class="sxs-lookup"><span data-stu-id="84121-170">Batch assign users to a policy</span></span>](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps)
