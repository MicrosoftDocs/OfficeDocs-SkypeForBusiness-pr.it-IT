---
title: Configurare i criteri di archiviazione per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8e48087-d4f0-4fe1-9e7e-f2b3e07f815f
description: 'Riepilogo: leggere questo argomento per informazioni su come configurare i criteri di archiviazione iniziali per gli utenti di Skype for Business Server.'
ms.openlocfilehash: 9d4fc7bd27440688f981ac9d05b1e47750ad7867
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190499"
---
# <a name="configure-archiving-policies-for-skype-for-business-server"></a><span data-ttu-id="4fb04-103">Configurare i criteri di archiviazione per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4fb04-103">Configure archiving policies for Skype for Business Server</span></span>
 
<span data-ttu-id="4fb04-104">**Riepilogo:** Leggere questo argomento per informazioni su come configurare i criteri di archiviazione iniziali per gli utenti di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4fb04-104">**Summary:** Read this topic to learn how to configure initial archiving policies for Skype for Business Server users.</span></span>
  
<span data-ttu-id="4fb04-105">In Skype for Business Server si usano i criteri per abilitare e disabilitare l'archiviazione per comunicazioni interne e comunicazioni esterne per gli utenti residenti in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4fb04-105">In Skype for Business Server, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Skype for Business Server.</span></span> <span data-ttu-id="4fb04-106">Sono inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="4fb04-106">This includes the following:</span></span>
  
- <span data-ttu-id="4fb04-107">Un criterio globale creato per impostazione predefinita quando si distribuisce Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4fb04-107">A global policy that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="4fb04-108">Criteri facoltativi a livello di sito che specificano la modalità di implementazione dell'archiviazione per un sito specifico</span><span class="sxs-lookup"><span data-stu-id="4fb04-108">Optional site-level policies that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="4fb04-109">Criteri facoltativi a livello utente che specificano la modalità di implementazione dell'archiviazione per utenti specifici</span><span class="sxs-lookup"><span data-stu-id="4fb04-109">Optional user-level policies that specify how archiving is implemented for specific users</span></span>
    
<span data-ttu-id="4fb04-110">I criteri di archiviazione sono stati inizialmente impostati quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare criteri dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="4fb04-110">You initially set up archiving policies when you deploy archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="4fb04-111">Nel pannello di controllo di Skype for Business Server è possibile usare la pagina **criteri di archiviazione** del gruppo **archiviazione e monitoraggio** per gestire i criteri a livello globale, del sito e degli utenti.</span><span class="sxs-lookup"><span data-stu-id="4fb04-111">In Skype for Business Server Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global, site, and user levels.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4fb04-112">Per controllare l'implementazione dell'archiviazione, è necessario specificare le opzioni, ad esempio l'archiviazione di messaggi istantanei o di conferenza, l'uso delle opzioni di modalità critiche ed eliminazione.</span><span class="sxs-lookup"><span data-stu-id="4fb04-112">To control the implementation of archiving, you must specify options, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="4fb04-113">Per impostazione predefinita, nessuna opzione è abilitata nella configurazione di archiviazione globale o in qualsiasi configurazione di archiviazione di siti o pool.</span><span class="sxs-lookup"><span data-stu-id="4fb04-113">By default no options are enabled in the global archiving configuration or any site or pool archiving configuration.</span></span> <span data-ttu-id="4fb04-114">Devi specificare tutte le opzioni appropriate prima di abilitare l'archiviazione per comunicazioni interne o esterne.</span><span class="sxs-lookup"><span data-stu-id="4fb04-114">You should specify all appropriate options before enabling archiving for internal or external communications.</span></span> <span data-ttu-id="4fb04-115">Per informazioni dettagliate, vedere [configurare le opzioni di archiviazione per Skype for Business Server](configure-archiving-options.md).</span><span class="sxs-lookup"><span data-stu-id="4fb04-115">For details, see [Configure archiving options for Skype for Business Server](configure-archiving-options.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4fb04-116">Se si Abilita l'integrazione di Microsoft Exchange per la distribuzione, i criteri di blocco sul posto di Exchange controllano se l'archiviazione è abilitata per gli utenti ospitati in Exchange e le cassette postali vengono messe sul posto.</span><span class="sxs-lookup"><span data-stu-id="4fb04-116">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange and have their mailboxes put on In-Place Hold.</span></span> 
  
<span data-ttu-id="4fb04-117">Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, ad esempio la gerarchia per i criteri globali, per il sito e per gli utenti, vedere [pianificare l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="4fb04-117">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="4fb04-118">Per informazioni dettagliate su come gestire i criteri dopo la distribuzione, vedere [gestire i criteri di archiviazione in Skype for Business Server](../../manage/archiving/policies.md).</span><span class="sxs-lookup"><span data-stu-id="4fb04-118">For details about how to manage policies after deployment, see [Manage archiving policies in Skype for Business Server](../../manage/archiving/policies.md).</span></span>
  
## <a name="global-policy"></a><span data-ttu-id="4fb04-119">Criterio globale</span><span class="sxs-lookup"><span data-stu-id="4fb04-119">Global policy</span></span>

<span data-ttu-id="4fb04-120">Quando si distribuiscono i server front-end, Skype for Business Server crea un criterio globale per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="4fb04-120">When you deploy your Front End Servers, Skype for Business Server creates a global policy for archiving.</span></span> <span data-ttu-id="4fb04-121">Per impostazione predefinita, l'archiviazione è disabilitata nel criterio globale.</span><span class="sxs-lookup"><span data-stu-id="4fb04-121">By default, archiving is disabled in the global policy.</span></span> <span data-ttu-id="4fb04-122">Il criterio globale controlla se l'archiviazione è abilitata per le comunicazioni interne ed esterne per l'intera distribuzione, a meno che non vengano configurati i criteri del sito o degli utenti, che eseguono l'override del criterio globale o se si usa l'integrazione di Microsoft Exchange per alcuni o tutti Gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4fb04-122">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="4fb04-123">Se si usa l'integrazione di Microsoft Exchange, il criterio globale non si applica agli utenti ospitati in Exchange e hanno inserito le cassette postali sul posto.</span><span class="sxs-lookup"><span data-stu-id="4fb04-123">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange and have the mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-the-global-policy-for-archiving-for-skype-for-business-server-archiving-databases"></a><span data-ttu-id="4fb04-124">Configurare i criteri globali per l'archiviazione per i database di archiviazione di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4fb04-124">Configure the global policy for archiving for Skype for Business Server archiving databases</span></span>

1. <span data-ttu-id="4fb04-125">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="4fb04-125">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4fb04-126">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4fb04-126">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="4fb04-127">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="4fb04-127">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="4fb04-128">Nella pagina **criteri di archiviazione** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="4fb04-128">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="4fb04-129">In **modifica criteri di archiviazione-globale**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4fb04-129">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
   - <span data-ttu-id="4fb04-130">In **nome**, se non si vuole usare il nome predefinito globale, specificare un nuovo nome per il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="4fb04-130">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span> 
    
   - <span data-ttu-id="4fb04-131">In **Descrizione**, fornisci informazioni sui criteri, ad esempio i criteri globali per divisioname \*\* .</span><span class="sxs-lookup"><span data-stu-id="4fb04-131">In **Description**, provide information about what the policy is (for example, Global policy for  *divisionName*  .</span></span>
    
   - <span data-ttu-id="4fb04-132">Per controllare l'archiviazione delle comunicazioni interne per tutti i siti e gli utenti non controllati in modo specifico tramite criteri del sito o criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .</span><span class="sxs-lookup"><span data-stu-id="4fb04-132">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="4fb04-133">Per controllare l'archiviazione delle comunicazioni esterne per tutti i siti e gli utenti non controllati in modo specifico tramite criteri del sito o criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .</span><span class="sxs-lookup"><span data-stu-id="4fb04-133">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="4fb04-134">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="4fb04-134">Click **Commit**.</span></span>
    
## <a name="site-policies"></a><span data-ttu-id="4fb04-135">Criteri sito</span><span class="sxs-lookup"><span data-stu-id="4fb04-135">Site policies</span></span>

<span data-ttu-id="4fb04-136">È possibile abilitare o disabilitare l'archiviazione per siti specifici creando un criterio di archiviazione per ognuno di questi siti.</span><span class="sxs-lookup"><span data-stu-id="4fb04-136">You can enable or disable archiving for specific sites by creating an archiving policy for each of those sites.</span></span> <span data-ttu-id="4fb04-137">Un criterio di sito sostituisce il criterio globale, ma i criteri utente sostituiscono i criteri del sito.</span><span class="sxs-lookup"><span data-stu-id="4fb04-137">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="4fb04-138">I criteri di archiviazione si applicano solo se non si usa l'integrazione di Microsoft Exchange o, se si usa l'integrazione di Microsoft Exchange, ma alcuni utenti non sono ospitati in Exchange e le cassette postali vengono inserite in un blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="4fb04-138">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="create-an-archiving-policy-for-a-site"></a><span data-ttu-id="4fb04-139">Creare un criterio di archiviazione per un sito</span><span class="sxs-lookup"><span data-stu-id="4fb04-139">Create an archiving policy for a site</span></span>

1. <span data-ttu-id="4fb04-140">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="4fb04-140">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4fb04-141">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4fb04-141">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="4fb04-142">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="4fb04-142">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="4fb04-143">Per informazioni dettagliate sul funzionamento dei criteri di archiviazione, ad esempio la gerarchia per i criteri globali, per il sito e per gli utenti, vedere [pianificare l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="4fb04-143">For details about how archiving policies work, including the hierarchy for global, site, and user policies, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
    
4. <span data-ttu-id="4fb04-144">Fare clic su **Nuovo** e quindi su **Criteri sito**.</span><span class="sxs-lookup"><span data-stu-id="4fb04-144">Click **New**, and then click **Site policy**.</span></span>
    
5. <span data-ttu-id="4fb04-145">In **Seleziona un sito**fare clic sul sito a cui applicare il criterio.</span><span class="sxs-lookup"><span data-stu-id="4fb04-145">In **Select a site**, click the site to which the policy is to be applied.</span></span>
    
6. <span data-ttu-id="4fb04-146">In **nuovi criteri di archiviazione**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4fb04-146">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="4fb04-147">In **nome**specificare il nome per il criterio del sito.</span><span class="sxs-lookup"><span data-stu-id="4fb04-147">In **Name**, specify the name for the site policy.</span></span> 
    
   - <span data-ttu-id="4fb04-148">In **Descrizione**immettere informazioni sui criteri del sito, ad esempio i criteri del sito per Redmond.</span><span class="sxs-lookup"><span data-stu-id="4fb04-148">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
   - <span data-ttu-id="4fb04-149">Per controllare l'archiviazione delle comunicazioni interne per il sito specificato, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .</span><span class="sxs-lookup"><span data-stu-id="4fb04-149">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="4fb04-150">Per controllare l'archiviazione delle comunicazioni esterne per il sito specificato, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .</span><span class="sxs-lookup"><span data-stu-id="4fb04-150">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>
    
7. <span data-ttu-id="4fb04-151">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="4fb04-151">Click **Commit**.</span></span>
    
## <a name="user-policies"></a><span data-ttu-id="4fb04-152">Criteri per gli utenti</span><span class="sxs-lookup"><span data-stu-id="4fb04-152">User policies</span></span>

<span data-ttu-id="4fb04-153">È possibile abilitare o disabilitare l'archiviazione per utenti specifici creando e configurando un criterio di archiviazione per gli utenti e quindi applicando il criterio a utenti o gruppi utente specifici.</span><span class="sxs-lookup"><span data-stu-id="4fb04-153">You can enable or disable archiving for specific users by creating and configuring an archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="4fb04-154">I criteri utente eseguono l'override di qualsiasi criterio globale o dei criteri del sito.</span><span class="sxs-lookup"><span data-stu-id="4fb04-154">User policies override any global policy or site policies.</span></span> <span data-ttu-id="4fb04-155">I criteri di archiviazione si applicano solo se non si usa l'integrazione di Microsoft Exchange o, se si usa l'integrazione di Microsoft Exchange, ma alcuni utenti non sono ospitati in Exchange e le cassette postali vengono inserite in un blocco sul posto.</span><span class="sxs-lookup"><span data-stu-id="4fb04-155">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange and have their mailboxes put on In-Place Hold.</span></span>
  
### <a name="configure-an-archiving-policy-for-users-homed-on-skype-for-business-server"></a><span data-ttu-id="4fb04-156">Configurare un criterio di archiviazione per gli utenti ospitati in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="4fb04-156">Configure an archiving policy for users homed on Skype for Business Server</span></span>

1. <span data-ttu-id="4fb04-157">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="4fb04-157">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4fb04-158">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4fb04-158">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="4fb04-159">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="4fb04-159">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="4fb04-160">Fare clic su **Nuovo** e quindi su **Criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="4fb04-160">Click **New**, and then click **User policy**.</span></span>
    
5. <span data-ttu-id="4fb04-161">In **nuovi criteri di archiviazione**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="4fb04-161">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="4fb04-162">In **nome**specificare il nome per il criterio utente.</span><span class="sxs-lookup"><span data-stu-id="4fb04-162">In **Name**, specify the name for the user policy.</span></span> 
    
   - <span data-ttu-id="4fb04-163">In **Descrizione**, fornisci informazioni sui criteri utente (ad esempio, criteri utente per il reparto legale).</span><span class="sxs-lookup"><span data-stu-id="4fb04-163">In **Description**, provide information about what the user policy is (for example, user policy for legal department).</span></span>
    
   - <span data-ttu-id="4fb04-164">Per controllare l'archiviazione delle comunicazioni interne per i criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .</span><span class="sxs-lookup"><span data-stu-id="4fb04-164">To control archiving of internal communications for the user policy, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="4fb04-165">Per controllare l'archiviazione delle comunicazioni esterne per i criteri utente, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .</span><span class="sxs-lookup"><span data-stu-id="4fb04-165">To control archiving of external communications for the user policy, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="4fb04-166">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="4fb04-166">Click **Commit**.</span></span>
    
<span data-ttu-id="4fb04-167">Un criterio utente si applica solo agli utenti a cui si assegnano i criteri.</span><span class="sxs-lookup"><span data-stu-id="4fb04-167">A user policy applies only to users to whom you assign the policy.</span></span>
### <a name="apply-a-skype-for-business-server-archiving-policy-to-a-user"></a><span data-ttu-id="4fb04-168">Applicare un criterio di archiviazione di Skype for Business Server a un utente</span><span class="sxs-lookup"><span data-stu-id="4fb04-168">Apply a Skype for Business Server archiving policy to a user</span></span>

1. <span data-ttu-id="4fb04-169">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="4fb04-169">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="4fb04-170">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4fb04-170">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="4fb04-171">Nella barra di spostamento sinistra fare clic su **utenti**e quindi cercare l'account utente che si vuole configurare.</span><span class="sxs-lookup"><span data-stu-id="4fb04-171">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>
    
4. <span data-ttu-id="4fb04-172">Nella tabella in cui sono elencati i risultati della ricerca fare clic sull'account utente, su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="4fb04-172">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="4fb04-173">In **modifica utenti di Skype for Business Server** in **criteri di archiviazione**Selezionare i criteri utente di archiviazione che si desidera applicare.</span><span class="sxs-lookup"><span data-stu-id="4fb04-173">In **Edit Skype for Business Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4fb04-174">Le \*\* \<impostazioni\> automatiche\*\* applicano le impostazioni di installazione del server predefinite.</span><span class="sxs-lookup"><span data-stu-id="4fb04-174">The **\<Automatic\>** settings apply the default server installation settings.</span></span> <span data-ttu-id="4fb04-175">Queste impostazioni vengono applicate automaticamente dal server.</span><span class="sxs-lookup"><span data-stu-id="4fb04-175">These settings are applied automatically by the server.</span></span>
  
6. <span data-ttu-id="4fb04-176">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="4fb04-176">Click **Commit**.</span></span>
    

