---
title: Configurazione dei criteri di archiviazione per Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Riepilogo: leggere questo argomento per informazioni su come configurare i criteri di archiviazione iniziali per gli utenti di Skype for Business Server.'
ms.openlocfilehash: ab737305561aa20c873bbce6e0f075d17fedd0d6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820856"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a><span data-ttu-id="64391-103">Configurazione dei criteri di archiviazione per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="64391-103">Configure archiving policies for Skype for Business Server</span></span>
 
<span data-ttu-id="64391-104">**Riepilogo:** Leggere questo argomento per informazioni su come configurare i criteri di archiviazione iniziali per gli utenti di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="64391-104">**Summary:** Read this topic to learn how to configure initial archiving policies for Skype for Business Server users.</span></span>
  
<span data-ttu-id="64391-105">In Skype for Business Server, è possibile utilizzare i criteri per abilitare e disabilitare l'archiviazione delle comunicazioni interne e delle comunicazioni esterne per gli utenti che si trovano in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="64391-105">In Skype for Business Server, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="64391-106">Sono incluse le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="64391-106">This includes the following:</span></span>
  
- <span data-ttu-id="64391-107">Un criterio globale creato per impostazione predefinita quando si distribuisce Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="64391-107">A global policy that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="64391-108">Criteri facoltativi a livello di sito che specificano la modalità di implementazione dell'archiviazione per un sito specifico</span><span class="sxs-lookup"><span data-stu-id="64391-108">Optional site-level policies that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="64391-109">Criteri facoltativi a livello di utente che specificano la modalità di implementazione dell'archiviazione per utenti specifici</span><span class="sxs-lookup"><span data-stu-id="64391-109">Optional user-level policies that specify how archiving is implemented for specific users</span></span>
    
<span data-ttu-id="64391-110">Inizialmente sono stati configurati i criteri di archiviazione quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare criteri dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="64391-110">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="64391-111">Nel pannello di controllo di Skype for Business Server, è possibile utilizzare la pagina **criteri di archiviazione** del gruppo di **archiviazione e monitoraggio** per gestire i criteri a livello globale, di sito e di utente.</span><span class="sxs-lookup"><span data-stu-id="64391-111">In Skype for Business Server Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global, site, and user levels.</span></span>
  
> [!NOTE]
> <span data-ttu-id="64391-112">Per controllare l'implementazione dell'archiviazione, è necessario specificare le opzioni, ad esempio se archiviare la messaggistica istantanea o le conferenze, l'utilizzo della modalità critica e le opzioni di eliminazione.</span><span class="sxs-lookup"><span data-stu-id="64391-112">To control the implementation of archiving, you must specify options, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="64391-113">Per impostazione predefinita, nessuna opzione è abilitata nella configurazione di archiviazione globale o in qualsiasi configurazione di archiviazione del sito o del pool.</span><span class="sxs-lookup"><span data-stu-id="64391-113">By default no options are enabled in the global archiving configuration or any site or pool archiving configuration.</span></span> <span data-ttu-id="64391-114">Prima di abilitare l'archiviazione per le comunicazioni interne o esterne, è necessario specificare tutte le opzioni appropriate.</span><span class="sxs-lookup"><span data-stu-id="64391-114">You should specify all appropriate options before enabling archiving for internal or external communications.</span></span> <span data-ttu-id="64391-115">Per ulteriori informazioni, vedere [configurare le opzioni di archiviazione per Skype for Business Server](configure-archiving-options.md).</span><span class="sxs-lookup"><span data-stu-id="64391-115">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="64391-116">Se si Abilita l'integrazione di Microsoft Exchange per la distribuzione, i criteri di Exchange In-Place conservazione determinano se l'archiviazione è abilitata per gli utenti ospitati in Exchange e le cassette postali vengono inserite In-Place blocco.</span><span class="sxs-lookup"><span data-stu-id="64391-116">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> 
  
<span data-ttu-id="64391-117">Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, inclusa la gerarchia per i criteri globali, del sito e degli utenti, vedere [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="64391-117">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="64391-118">Per informazioni dettagliate su come gestire i criteri dopo la distribuzione, vedere [gestire i criteri di archiviazione in Skype for Business Server](../../manage/archiving/policies.md).</span><span class="sxs-lookup"><span data-stu-id="64391-118">For details about how to manage policies after deployment, see [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).</span></span>
  
## <a name="global-policy"></a><span data-ttu-id="64391-119">Criterio globale</span><span class="sxs-lookup"><span data-stu-id="64391-119">Global policy</span></span>

<span data-ttu-id="64391-120">Quando si distribuisce i Front End Server, in Skype for Business Server viene creato un criterio globale per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="64391-120">When you deploy your Front End Servers, Skype for Business Server creates a global policy for archiving.</span></span> <span data-ttu-id="64391-121">Per impostazione predefinita, l'archiviazione è disabilitata nei criteri globali.</span><span class="sxs-lookup"><span data-stu-id="64391-121">By default, archiving is disabled in the global policy.</span></span> <span data-ttu-id="64391-122">Il criterio globale determina se l'archiviazione è abilitata per le comunicazioni interne ed esterne per l'intera distribuzione, a meno che non si configurano i criteri di sito o utente, che sostituiscono il criterio globale, o se si utilizza l'integrazione di Microsoft Exchange per alcuni o tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="64391-122">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="64391-123">Se si utilizza l'integrazione di Microsoft Exchange, il criterio globale non si applica a tutti gli utenti ospitati in Exchange e le cassette postali vengono inserite In-Place blocco.</span><span class="sxs-lookup"><span data-stu-id="64391-123">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange and have the mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a><span data-ttu-id="64391-124">Configurazione dei criteri globali per l'archiviazione dei database di archiviazione di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="64391-124">Configure the global policy for archiving for Skype for Business Server archiving databases</span></span>

1. <span data-ttu-id="64391-125">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="64391-125">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="64391-126">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="64391-126">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="64391-127">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="64391-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="64391-128">Nella pagina **Criteri di archiviazione** fare clic su **Globale**, **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="64391-128">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="64391-129">In **Modifica Criteri di archiviazione - Globale** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="64391-129">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="64391-130">In **Nome**, se non si vuole usare il nome predefinito Globale, specificare un nuovo nome per i criteri globali.</span><span class="sxs-lookup"><span data-stu-id="64391-130">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span> 
    
   - <span data-ttu-id="64391-131">In **Descrizione** fornire informazioni sui criteri, ad esempio i criteri globali per  *divisionname*  .</span><span class="sxs-lookup"><span data-stu-id="64391-131">In **Description**, provide information about what the policy is (for example, Global policy for  *divisionName*  .</span></span>
    
   - <span data-ttu-id="64391-132">Per controllare l'archiviazione delle comunicazioni interne per tutti i siti e gli utenti non controllati in modo specifico tramite criteri utente o sito, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne**.</span><span class="sxs-lookup"><span data-stu-id="64391-132">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="64391-133">Per controllare l'archiviazione delle comunicazioni esterne per tutti i siti e gli utenti non controllati in modo specifico tramite criteri utente o di sito, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne**.</span><span class="sxs-lookup"><span data-stu-id="64391-133">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="64391-134">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="64391-134">Click **Commit**.</span></span>
    
## <a name="site-policies"></a><span data-ttu-id="64391-135">Criteri sito</span><span class="sxs-lookup"><span data-stu-id="64391-135">Site policies</span></span>

<span data-ttu-id="64391-136">È possibile abilitare o disabilitare l'archiviazione per siti specifici creando un criterio di archiviazione per ognuno di questi siti.</span><span class="sxs-lookup"><span data-stu-id="64391-136">You can enable or disable archiving for specific sites by creating an archiving policy for each of those sites.</span></span> <span data-ttu-id="64391-137">Un criterio sito ha la precedenza sui criteri globali, ma i criteri degli utenti eseguono l'override dei criteri sito.</span><span class="sxs-lookup"><span data-stu-id="64391-137">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="64391-138">I criteri di archiviazione si applicano solo se non si utilizza l'integrazione di Microsoft Exchange o, se si utilizza l'integrazione di Microsoft Exchange, ma alcuni utenti non sono ospitati in Exchange e le relative cassette postali vengono inserite In-Place.</span><span class="sxs-lookup"><span data-stu-id="64391-138">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="create-an-archiving-policy-for-a-site"></a><span data-ttu-id="64391-139">Creare un criterio di archiviazione per un sito</span><span class="sxs-lookup"><span data-stu-id="64391-139">Create an archiving policy for a site</span></span>

1. <span data-ttu-id="64391-140">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="64391-140">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="64391-141">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="64391-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="64391-142">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="64391-142">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="64391-143">Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, inclusa la gerarchia per i criteri globali, del sito e degli utenti, vedere [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="64391-143">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
    
4. <span data-ttu-id="64391-144">Fare clic su **Nuovo** e quindi su **Criteri sito**.</span><span class="sxs-lookup"><span data-stu-id="64391-144">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="64391-145">In **Seleziona un sito** fare clic sul sito a cui devono essere applicati i criteri.</span><span class="sxs-lookup"><span data-stu-id="64391-145">In **Select a site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="64391-146">In **Crea nuovi criteri di archiviazione** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="64391-146">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="64391-147">In **nome** specificare il nome del criterio sito.</span><span class="sxs-lookup"><span data-stu-id="64391-147">In **Name**, specify the name for the site policy.</span></span> 
    
   - <span data-ttu-id="64391-148">In **Descrizione** fornire informazioni sui criteri di sito, ad esempio criteri sito per Redmond.</span><span class="sxs-lookup"><span data-stu-id="64391-148">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
   - <span data-ttu-id="64391-149">Per controllare l'archiviazione delle comunicazioni interne per il sito specificato, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .</span><span class="sxs-lookup"><span data-stu-id="64391-149">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="64391-150">Per controllare l'archiviazione delle comunicazioni esterne per il sito specificato, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .</span><span class="sxs-lookup"><span data-stu-id="64391-150">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>
    
7. <span data-ttu-id="64391-151">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="64391-151">Click **Commit**.</span></span>
    
## <a name="user-policies"></a><span data-ttu-id="64391-152">Criteri utente</span><span class="sxs-lookup"><span data-stu-id="64391-152">User policies</span></span>

<span data-ttu-id="64391-153">È possibile abilitare o disabilitare l'archiviazione per utenti specifici mediante la creazione e la configurazione di un criterio di archiviazione per gli utenti e quindi l'applicazione del criterio a utenti o gruppi utente specifici.</span><span class="sxs-lookup"><span data-stu-id="64391-153">You can enable or disable archiving for specific users by creating and configuring an archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="64391-154">I criteri utente sostituiscono eventuali criteri globali o sito.</span><span class="sxs-lookup"><span data-stu-id="64391-154">User policies override any global policy or site policies.</span></span> <span data-ttu-id="64391-155">I criteri di archiviazione si applicano solo se non si utilizza l'integrazione di Microsoft Exchange o, se si utilizza l'integrazione di Microsoft Exchange, ma alcuni utenti non sono ospitati in Exchange e le relative cassette postali vengono inserite In-Place.</span><span class="sxs-lookup"><span data-stu-id="64391-155">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a><span data-ttu-id="64391-156">Configurare un criterio di archiviazione per gli utenti ospitati in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="64391-156">Configure an archiving policy for users homed on Skype for Business Server</span></span>

1. <span data-ttu-id="64391-157">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="64391-157">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="64391-158">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="64391-158">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="64391-159">Nella barra di spostamento sinistra fare clic su **Monitoraggio e archiviazione** e quindi su **Criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="64391-159">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="64391-160">Fare clic su **Nuovo** e quindi su **Criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="64391-160">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="64391-161">In **Nuovi criteri di archiviazione** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="64391-161">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="64391-162">In **Nome** specificare un nome per i criteri utente.</span><span class="sxs-lookup"><span data-stu-id="64391-162">In **Name**, specify the name for the user policy.</span></span> 
    
   - <span data-ttu-id="64391-163">In **Descrizione** immettere informazioni sugli scopi dei criteri utente, ad esempio "Criteri utente per il reparto legale".</span><span class="sxs-lookup"><span data-stu-id="64391-163">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
   - <span data-ttu-id="64391-164">Per controllare l'archiviazione delle comunicazioni interne per i criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne**.</span><span class="sxs-lookup"><span data-stu-id="64391-164">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="64391-165">Per controllare l'archiviazione delle comunicazioni esterne per i criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne**.</span><span class="sxs-lookup"><span data-stu-id="64391-165">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="64391-166">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="64391-166">Click **Commit**.</span></span>
    
<span data-ttu-id="64391-167">I criteri utente si applicano solo agli utenti a cui vengono assegnati.</span><span class="sxs-lookup"><span data-stu-id="64391-167">A user policy applies only to users to whom you assign the policy.</span></span>
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a><span data-ttu-id="64391-168">Applicare un criterio di archiviazione di Skype for Business Server a un utente</span><span class="sxs-lookup"><span data-stu-id="64391-168">Apply a Skype for Business Server archiving policy to a user</span></span>

1. <span data-ttu-id="64391-169">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="64391-169">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="64391-170">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="64391-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="64391-171">Sulla barra di spostamento sinistra fare clic su **Utenti** e quindi cercare l'account utente che si desidera configurare.</span><span class="sxs-lookup"><span data-stu-id="64391-171">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="64391-172">Nella tabella dei risultati di ricerca fare clic sull'account utente, fare clic su **Modifica** e quindi fare clic su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="64391-172">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="64391-173">In **modifica utente di Skype for Business Server** in **criteri di archiviazione**, selezionare i criteri utente di archiviazione che si desidera applicare.</span><span class="sxs-lookup"><span data-stu-id="64391-173">In **Edit Skype for Business Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="64391-174">Le **\<Automatic\>** impostazioni applicano le impostazioni di installazione predefinite del server.</span><span class="sxs-lookup"><span data-stu-id="64391-174">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="64391-175">Queste impostazioni vengono applicate automaticamente dal server.</span><span class="sxs-lookup"><span data-stu-id="64391-175">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="64391-176">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="64391-176">Click **Commit**.</span></span>
    

