---
title: Criteri di archiviazione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
ROBOTS: NOINDEX, NOFOLLOW
description: "Si usano i criteri di archiviazione per abilitare e disabilitare l'archiviazione per gli utenti ospitati in Skype for Business Server. Nei criteri di archiviazione è possibile abilitare o disabilitare la funzionalità per uno o entrambi i tipi di comunicazione seguenti:"
ms.openlocfilehash: cbd15a7ea1f183a90d30fac8f44fae46edc1610e
ms.sourcegitcommit: b1229ed5dc25a04e56aa02aab8ad3d4209559d8f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41795055"
---
# <a name="archiving-policy"></a><span data-ttu-id="2f998-104">Criteri di archiviazione</span><span class="sxs-lookup"><span data-stu-id="2f998-104">Archiving Policy</span></span>
 
<span data-ttu-id="2f998-105">Si usano i criteri di archiviazione per abilitare e disabilitare l'archiviazione per gli utenti ospitati in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2f998-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="2f998-106">Nei criteri di archiviazione è possibile abilitare o disabilitare la funzionalità per uno o entrambi i tipi di comunicazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="2f998-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="2f998-107">Comunicazioni interne</span><span class="sxs-lookup"><span data-stu-id="2f998-107">Internal communications</span></span>
    
- <span data-ttu-id="2f998-108">Comunicazioni esterne (comunicazioni che includono almeno un utente esterno alla rete interna)</span><span class="sxs-lookup"><span data-stu-id="2f998-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="2f998-109">I criteri di archiviazione includono il criterio globale e, facoltativamente, uno o più criteri di archiviazione per sito e utente:</span><span class="sxs-lookup"><span data-stu-id="2f998-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="2f998-110">**Criteri globali** Il criterio globale viene creato per impostazione predefinita in tutte le distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="2f998-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="2f998-111">È possibile modificare il criterio globale, ma non eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="2f998-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="2f998-112">Se si tenta di eliminarlo, tutte le opzioni verranno ripristinate ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="2f998-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="2f998-113">**Criteri sito (facoltativo)** Puoi specificare uno o più criteri di archiviazione del sito, ognuno dei quali puoi configurare per abilitare e disabilitare l'archiviazione delle comunicazioni interne o esterne per un singolo sito.</span><span class="sxs-lookup"><span data-stu-id="2f998-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="2f998-114">Un criterio sito ha la precedenza sui criteri globali, ma solo per il sito specificato nei criteri di archiviazione del sito.</span><span class="sxs-lookup"><span data-stu-id="2f998-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="2f998-115">È possibile modificare o eliminare i criteri sito.</span><span class="sxs-lookup"><span data-stu-id="2f998-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="2f998-116">**Criteri utente (facoltativo)** Puoi specificare uno o più criteri di archiviazione degli utenti, ognuno dei quali puoi configurare per abilitare e disabilitare l'archiviazione delle comunicazioni interne o esterne per un utente o un gruppo di utenti specifico.</span><span class="sxs-lookup"><span data-stu-id="2f998-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="2f998-117">Un criterio utente ha la precedenza sui criteri globali e i criteri sito, ma solo per gli utenti e i gruppi di utenti a cui si assegnano i criteri di archiviazione a livello utente.</span><span class="sxs-lookup"><span data-stu-id="2f998-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="2f998-118">È possibile modificare o eliminare i criteri utente.</span><span class="sxs-lookup"><span data-stu-id="2f998-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="2f998-119">I criteri di archiviazione si applicano solo agli utenti residenti in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2f998-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="2f998-120">Se si usa l'integrazione di Exchange per archiviare i dati di archiviazione in Microsoft Exchange, i criteri di Exchange controllano l'archiviazione per gli utenti ospitati in Exchange.</span><span class="sxs-lookup"><span data-stu-id="2f998-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange policies control archiving for users homed on Exchange.</span></span> <span data-ttu-id="2f998-121">Per abilitare l'archiviazione per tali utenti, la cassetta postale dell'utente deve essere posizionata sul blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="2f998-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="2f998-p107">Nella pagina **Criteri di archiviazione** sono elencati tutti i criteri di archiviazione configurati per la distribuzione. Sono inoltre mostrati il nome del criterio, l'ambito (globale, sito o utente) e quali opzioni di archiviazione sono abilitate per ogni criterio di archiviazione. Nella pagina **Criteri di archiviazione** sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2f998-p107">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy. From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="2f998-125">**Nuovo** È possibile aggiungere uno o più dei seguenti criteri di archiviazione facoltativi:</span><span class="sxs-lookup"><span data-stu-id="2f998-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="2f998-126">Criteri sito</span><span class="sxs-lookup"><span data-stu-id="2f998-126">Site policy</span></span>
    
  - <span data-ttu-id="2f998-127">Criteri utente</span><span class="sxs-lookup"><span data-stu-id="2f998-127">User policy</span></span>
    
- <span data-ttu-id="2f998-128">**Modifica** È possibile modificare le opzioni di uno dei criteri di archiviazione elencati nella pagina.</span><span class="sxs-lookup"><span data-stu-id="2f998-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="2f998-129">Usando questa opzione è possibile eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2f998-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="2f998-130">**Mostra dettagli** Questa opzione consente di aprire una finestra di dialogo in cui è possibile modificare le opzioni di archiviazione per un criterio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="2f998-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="2f998-131">**Seleziona tutto** Questa opzione consente di selezionare tutti i criteri di archiviazione nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="2f998-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="2f998-132">**Elimina** Questa opzione consente di eliminare tutti i criteri di archiviazione selezionati.</span><span class="sxs-lookup"><span data-stu-id="2f998-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="2f998-133">**Azione** Puoi usare questa opzione per abilitare o disabilitare rapidamente l'archiviazione delle comunicazioni interne o esterne in qualsiasi criterio elencato nella pagina, invece di modificare i criteri.</span><span class="sxs-lookup"><span data-stu-id="2f998-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="2f998-134">Le opzioni disponibili in **Azione** dipendono dall'opzione attualmente specificata nel criterio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="2f998-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="2f998-135">Tutte le opzioni sono disponibili, ad eccezione di quella attualmente applicata per il criterio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="2f998-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="2f998-136">Tra le opzioni disponibili sono incluse le seguenti:</span><span class="sxs-lookup"><span data-stu-id="2f998-136">Options include the following:</span></span>
    
  - <span data-ttu-id="2f998-137">**Abilita archiviazione di comunicazioni interne**</span><span class="sxs-lookup"><span data-stu-id="2f998-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="2f998-138">**Disabilita archiviazione di comunicazioni interne**</span><span class="sxs-lookup"><span data-stu-id="2f998-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="2f998-139">**Abilita archiviazione di comunicazioni esterne**</span><span class="sxs-lookup"><span data-stu-id="2f998-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="2f998-140">**Disabilita archiviazione di comunicazioni esterne**</span><span class="sxs-lookup"><span data-stu-id="2f998-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="2f998-141">**Aggiornare** È possibile aggiornare la pagina dei **criteri di archiviazione** per verificare lo stato delle opzioni di tutti i criteri di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="2f998-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="2f998-142">Per informazioni dettagliate sulla funzionalità e le funzionalità di archiviazione, inclusa l'integrazione di Exchange, vedere [pianificare l'archiviazione in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [distribuire l'archiviazione per Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)e [gestire l'archiviazione in Skype for Business Server](../../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="2f998-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

