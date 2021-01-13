---
title: Criteri archiviazione
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.MonArchPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9b69f1fa-8f3b-450e-aa89-91fd462f198d
description: "È possibile utilizzare i criteri di archiviazione per abilitare e disabilitare l'archiviazione per gli utenti ospitati in Skype for Business Server. In ogni criterio di archiviazione, è possibile abilitare o disabilitare l'archiviazione per uno o entrambi gli elementi seguenti:"
ms.openlocfilehash: 19bc0612208e719b7a963bf4c7f0dc6a9cc69537
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49826946"
---
# <a name="archiving-policy"></a><span data-ttu-id="f1145-104">Criteri archiviazione</span><span class="sxs-lookup"><span data-stu-id="f1145-104">Archiving Policy</span></span>
 
<span data-ttu-id="f1145-105">È possibile utilizzare i criteri di archiviazione per abilitare e disabilitare l'archiviazione per gli utenti ospitati in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f1145-105">You use Archiving policies to enable and disable archiving for users homed on Skype for Business Server.</span></span> <span data-ttu-id="f1145-106">In ogni criterio di archiviazione, è possibile abilitare o disabilitare l'archiviazione per uno o entrambi gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1145-106">In each Archiving policy, you can enable or disable archiving for either or both of the following:</span></span>
  
- <span data-ttu-id="f1145-107">Comunicazioni interne</span><span class="sxs-lookup"><span data-stu-id="f1145-107">Internal communications</span></span>
    
- <span data-ttu-id="f1145-108">Comunicazioni esterne (comunicazioni che includono almeno un utente esterno alla rete interna)</span><span class="sxs-lookup"><span data-stu-id="f1145-108">External communications (communications that include at least one user outside your internal network)</span></span>
    
<span data-ttu-id="f1145-109">I criteri di archiviazione includono il criterio globale e, facoltativamente, uno o più criteri di archiviazione per sito e utente:</span><span class="sxs-lookup"><span data-stu-id="f1145-109">Archiving policies include the global policy, and, optionally, one or more site and user Archiving policies:</span></span>
  
- <span data-ttu-id="f1145-110">**Criteri globali** Il criterio globale viene creato per impostazione predefinita in tutte le distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="f1145-110">**Global policy** The global policy is created by default in all deployments.</span></span> <span data-ttu-id="f1145-111">È possibile modificare il criterio globale, ma non eliminarlo.</span><span class="sxs-lookup"><span data-stu-id="f1145-111">You can edit the global policy, but you cannot delete this policy.</span></span> <span data-ttu-id="f1145-112">Se si tenta di eliminarlo, tutte le opzioni verranno ripristinate ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="f1145-112">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="f1145-113">**Criteri sito (facoltativo)** È possibile specificare uno o più criteri di archiviazione dei siti, ognuno dei quali può essere configurato per abilitare e disabilitare l'archiviazione delle comunicazioni interne o esterne per un singolo sito.</span><span class="sxs-lookup"><span data-stu-id="f1145-113">**Site policy (optional)** You can specify one or more site Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a single site.</span></span> <span data-ttu-id="f1145-114">Un criterio sito ha la precedenza sui criteri globali, ma solo per i siti specificati nei criteri del sito di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f1145-114">A site policy overrides the global policy, but only for the sites specified in your Archiving site policies.</span></span> <span data-ttu-id="f1145-115">È possibile modificare o eliminare i criteri sito.</span><span class="sxs-lookup"><span data-stu-id="f1145-115">You can edit or delete site policies.</span></span>
    
- <span data-ttu-id="f1145-116">**Criteri utente (facoltativo)** È possibile specificare uno o più criteri di archiviazione degli utenti, ognuno dei quali può essere configurato per abilitare e disabilitare l'archiviazione delle comunicazioni interne o esterne per un utente o un gruppo di utenti specifico.</span><span class="sxs-lookup"><span data-stu-id="f1145-116">**User policy (optional)** You can specify one or more user Archiving policies, each of which you can configure to enable and disable archiving of internal or external communications for a specific user or user group.</span></span> <span data-ttu-id="f1145-117">Un criterio utente ha la precedenza sui criteri globali e sui criteri sito, ma solo per gli utenti e i gruppi di utenti a cui si assegnano i criteri di archiviazione a livello di utente.</span><span class="sxs-lookup"><span data-stu-id="f1145-117">A user policy overrides the global policy and site policies, but only for the users and user groups to whom you assign user-level Archiving policies.</span></span> <span data-ttu-id="f1145-118">È possibile modificare o eliminare i criteri utente.</span><span class="sxs-lookup"><span data-stu-id="f1145-118">You can edit or delete user policies.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f1145-119">I criteri di archiviazione sono validi solo per gli utenti ospitati in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f1145-119">Archiving policies apply only to users homed on Skype for Business Server.</span></span> <span data-ttu-id="f1145-120">Se si utilizza l'integrazione di Exchange per archiviare i dati di archiviazione in Microsoft Exchange, i criteri di Exchange 2013 controllano l'archiviazione per gli utenti ospitati in Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="f1145-120">If you use Exchange integration to store archiving data in Microsoft Exchange, then Exchange 2013 policies control archiving for users homed on Exchange 2013.</span></span> <span data-ttu-id="f1145-121">Per abilitare l'archiviazione per tali utenti, è necessario che la cassetta postale dell'utente venga inserita In-Place blocco.</span><span class="sxs-lookup"><span data-stu-id="f1145-121">To enable archiving for those users, the user's mailbox must be placed on In-Place Hold.</span></span> 
  
<span data-ttu-id="f1145-122">La pagina **criteri di archiviazione** elenca tutti i criteri di archiviazione configurati per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f1145-122">The **Archiving Policy** page lists each Archiving policy that is configured for your deployment.</span></span> <span data-ttu-id="f1145-123">Vengono inoltre visualizzati il nome del criterio, l'ambito (globale, sito o utente) e quali opzioni di archiviazione sono abilitate per ogni criterio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f1145-123">It also shows the policy name, scope (global, site, or user), and which archiving options are enabled for each Archiving policy.</span></span> <span data-ttu-id="f1145-124">Nella pagina **criteri di archiviazione** sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1145-124">From the **Archiving Policy** page, you have the following options:</span></span>
- <span data-ttu-id="f1145-125">**Nuovo** È possibile aggiungere uno o più dei seguenti criteri di archiviazione facoltativi:</span><span class="sxs-lookup"><span data-stu-id="f1145-125">**New** You can add one or more of each of the following optional Archiving policies:</span></span>
    
  - <span data-ttu-id="f1145-126">Criterio sito</span><span class="sxs-lookup"><span data-stu-id="f1145-126">Site policy</span></span>
    
  - <span data-ttu-id="f1145-127">Criteri utente</span><span class="sxs-lookup"><span data-stu-id="f1145-127">User policy</span></span>
    
- <span data-ttu-id="f1145-128">**Modifica** È possibile modificare le opzioni di tutti i criteri di archiviazione elencati nella pagina.</span><span class="sxs-lookup"><span data-stu-id="f1145-128">**Edit** You can change the options of any of the Archiving policies listed on the page.</span></span> <span data-ttu-id="f1145-129">Usando questa voce, è possibile scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1145-129">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="f1145-130">**Mostra dettagli** Questa opzione consente di aprire una finestra di dialogo in cui è possibile modificare le opzioni di archiviazione per un criterio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f1145-130">**Show details** This option opens a dialog box in which you can change the archiving options for an Archiving policy.</span></span>
    
  - <span data-ttu-id="f1145-131">**Seleziona tutto** Questa opzione consente di selezionare tutti i criteri di archiviazione nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="f1145-131">**Select all** This option selects all Archiving policies in the list.</span></span>
    
  - <span data-ttu-id="f1145-132">**Eliminare** Questa opzione consente di eliminare tutti i criteri di archiviazione selezionati.</span><span class="sxs-lookup"><span data-stu-id="f1145-132">**Delete** This option deletes all selected Archiving policies.</span></span>
    
- <span data-ttu-id="f1145-133">**Azione** È possibile utilizzare questa opzione per abilitare o disabilitare rapidamente l'archiviazione delle comunicazioni interne o esterne in qualsiasi criterio elencato nella pagina, anziché modificare il criterio.</span><span class="sxs-lookup"><span data-stu-id="f1145-133">**Action** You can use this option to quickly enable or disable archiving of internal or external communications in any policy listed on the page, instead of editing the policy.</span></span> <span data-ttu-id="f1145-134">Le opzioni disponibili in **azione** dipendono dall'opzione attualmente specificata nei criteri di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f1145-134">The options available under **Action** depend on what option is currently specified in the Archiving policy.</span></span> <span data-ttu-id="f1145-135">Tutte le opzioni sono disponibili, ad eccezione dell'opzione attualmente attiva per il criterio di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f1145-135">All options are available, except the option currently in effect for the Archiving policy.</span></span> <span data-ttu-id="f1145-136">Tra le opzioni sono incluse le seguenti:</span><span class="sxs-lookup"><span data-stu-id="f1145-136">Options include the following:</span></span>
    
  - <span data-ttu-id="f1145-137">**Abilitare l'archiviazione delle comunicazioni interne**</span><span class="sxs-lookup"><span data-stu-id="f1145-137">**Enable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="f1145-138">**Disabilitare l'archiviazione delle comunicazioni interne**</span><span class="sxs-lookup"><span data-stu-id="f1145-138">**Disable Archiving of internal communications**</span></span>
    
  - <span data-ttu-id="f1145-139">**Abilitare l'archiviazione delle comunicazioni esterne**</span><span class="sxs-lookup"><span data-stu-id="f1145-139">**Enable Archiving of external communications**</span></span>
    
  - <span data-ttu-id="f1145-140">**Disabilitare l'archiviazione delle comunicazioni esterne**</span><span class="sxs-lookup"><span data-stu-id="f1145-140">**Disable Archiving of external communications**</span></span>
    
- <span data-ttu-id="f1145-141">**Aggiorna** È possibile aggiornare la pagina **criteri di archiviazione** per verificare lo stato delle opzioni di tutti i criteri di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="f1145-141">**Refresh** You can refresh the **Archiving Policy** page to verify the status of the options of all Archiving policies.</span></span>
    
<span data-ttu-id="f1145-142">Per informazioni dettagliate sulla funzionalità e sulle funzionalità di archiviazione, inclusa l'integrazione di Exchange, vedere [Plan for archiving in Skype for Business server 2015](../../plan-your-deployment/archiving/archiving.md), [deploy Archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md)e [Manage Archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="f1145-142">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

