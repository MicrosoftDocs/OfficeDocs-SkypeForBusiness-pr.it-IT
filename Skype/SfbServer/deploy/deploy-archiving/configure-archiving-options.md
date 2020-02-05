---
title: Configurare le opzioni di archiviazione per Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: "Riepilogo: leggere questo argomento per informazioni su come configurare le opzioni di archiviazione iniziali per Skype for Business Server. È stata inizialmente configurata la configurazione dell'archiviazione quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare configurazioni dopo la distribuzione."
ms.openlocfilehash: f663b310d4c82594976f2f0fc99b8ddd9baf035f
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41769199"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a><span data-ttu-id="2074a-104">Configurare le opzioni di archiviazione per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2074a-104">Configure archiving options for Skype for Business Server</span></span>
 
<span data-ttu-id="2074a-105">**Riepilogo:** Leggere questo argomento per informazioni su come configurare le opzioni di archiviazione iniziali per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2074a-105">**Summary:** Read this topic to learn how to configure initial archiving options for Skype for Business Server.</span></span> <span data-ttu-id="2074a-106">È stata inizialmente configurata la configurazione dell'archiviazione quando si distribuisce l'archiviazione, ma è possibile modificare, aggiungere ed eliminare configurazioni dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2074a-106">You initially set up archiving configurations when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span>
  
<span data-ttu-id="2074a-107">Per configurare le configurazioni di archiviazione iniziali, usare il pannello di controllo di Skype for Business Server per specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2074a-107">To configure initial archiving configurations, you use Skype for Business Server Control Panel to specify the following:</span></span>
  
- <span data-ttu-id="2074a-108">Configurazione a livello globale creata per impostazione predefinita quando si distribuisce Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2074a-108">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="2074a-109">Configurazioni facoltative a livello di sito che specificano la modalità di implementazione dell'archiviazione per un sito specifico</span><span class="sxs-lookup"><span data-stu-id="2074a-109">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="2074a-110">Configurazioni facoltative a livello di pool che specificano la modalità di implementazione dell'archiviazione per un pool specifico</span><span class="sxs-lookup"><span data-stu-id="2074a-110">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="2074a-111">Sarà necessario configurare le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2074a-111">You will need to configure options for the following:</span></span>
  
- <span data-ttu-id="2074a-112">Se abilitare o disabilitare l'archiviazione</span><span class="sxs-lookup"><span data-stu-id="2074a-112">Whether to enable or disable archiving</span></span>
    
- <span data-ttu-id="2074a-113">Se archiviare le sessioni di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="2074a-113">Whether to archive IM sessions</span></span>
    
- <span data-ttu-id="2074a-114">Se archiviare le sessioni di Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="2074a-114">Whether to archive web conferencing sessions</span></span>
    
- <span data-ttu-id="2074a-115">Se bloccare l'attività quando l'archiviazione non è disponibile</span><span class="sxs-lookup"><span data-stu-id="2074a-115">Whether to block activity when archiving is not available</span></span>
    
- <span data-ttu-id="2074a-116">Se usare l'integrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="2074a-116">Whether to use Exchange integration</span></span>
    
- <span data-ttu-id="2074a-117">Come configurare l'eliminazione e l'esportazione dei dati</span><span class="sxs-lookup"><span data-stu-id="2074a-117">How to set up purging and exporting of data</span></span>
    
> [!NOTE]
> <span data-ttu-id="2074a-118">Devi specificare tutte le opzioni appropriate prima di abilitare l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="2074a-118">You should specify all appropriate options before enabling archiving.</span></span> 
  
<span data-ttu-id="2074a-119">Per informazioni dettagliate sull'implementazione delle configurazioni di archiviazione, incluse le opzioni che è possibile specificare e la gerarchia delle configurazioni di archiviazione, vedere [pianificare l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="2074a-119">For details about how archiving configurations are implemented, including which options you can specify and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="2074a-120">Per informazioni dettagliate su come gestire le configurazioni dopo la distribuzione tramite il pannello di controllo o tramite Windows PowerShell, vedere [gestire le opzioni di archiviazione in Skype for Business Server](../../manage/archiving/options.md).</span><span class="sxs-lookup"><span data-stu-id="2074a-120">For details about how to manage configurations after deployment by using the Control Panel or by using Windows PowerShell, see [Manage archiving options in Skype for Business Server](../../manage/archiving/options.md).</span></span>
  
## <a name="configure-global-level-archiving-options"></a><span data-ttu-id="2074a-121">Configurare le opzioni di archiviazione a livello globale</span><span class="sxs-lookup"><span data-stu-id="2074a-121">Configure global level archiving options</span></span>

<span data-ttu-id="2074a-122">Quando si aggiunge l'archiviazione alla topologia e si pubblica la topologia, Skype for Business Server crea una configurazione globale per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="2074a-122">When you add archiving to your topology and publish the topology, Skype for Business Server creates a global configuration for archiving.</span></span> <span data-ttu-id="2074a-123">Per impostazione predefinita, le opzioni di archiviazione non sono abilitate nella configurazione globale.</span><span class="sxs-lookup"><span data-stu-id="2074a-123">By default, no archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="2074a-124">La configurazione globale Controlla quali opzioni sono abilitate per l'intera distribuzione, a meno che non vengano configurate configurazioni del sito o del pool, che eseguono l'override della configurazione globale.</span><span class="sxs-lookup"><span data-stu-id="2074a-124">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>
  
<span data-ttu-id="2074a-125">Per configurare le opzioni di archiviazione a livello globale:</span><span class="sxs-lookup"><span data-stu-id="2074a-125">To configure archiving options at the global level:</span></span>
  
1. <span data-ttu-id="2074a-126">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="2074a-126">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2074a-127">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2074a-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="2074a-128">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="2074a-128">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="2074a-129">Nella pagina **Configurazione archiviazione** fare clic su **globale**, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="2074a-129">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="2074a-130">In **Modifica impostazioni di archiviazione-globale**, nell'elenco a discesa **Impostazioni archiviazione** Selezionare una delle opzioni di archiviazione seguenti:</span><span class="sxs-lookup"><span data-stu-id="2074a-130">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="2074a-131">**Disabilita archiviazione**</span><span class="sxs-lookup"><span data-stu-id="2074a-131">**Disable archiving**</span></span>
    
   - <span data-ttu-id="2074a-132">**Archivia sessioni di messaggistica istantanea**</span><span class="sxs-lookup"><span data-stu-id="2074a-132">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="2074a-133">**Archivia sessioni di messaggistica istantanea e Web Conferencing**</span><span class="sxs-lookup"><span data-stu-id="2074a-133">**Archive IM and web conferencing sessions**</span></span>
    
6. <span data-ttu-id="2074a-134">Anche nell' **impostazione modifica archiviazione-pagina globale** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2074a-134">Also on the **Edit Archiving Setting - Global** page, do the following:</span></span>
    
   - <span data-ttu-id="2074a-135">Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca messaggistica istantanea o servizi di conferenza Web se l'archiviazione non riesce** .</span><span class="sxs-lookup"><span data-stu-id="2074a-135">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="2074a-136">Per usare Microsoft Exchange Server per archiviare i dati di archiviazione, fare clic sulla casella di controllo **integrazione di Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="2074a-136">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="2074a-137">Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita l'eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2074a-137">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="2074a-138">Per specificare l'eliminazione dopo un determinato numero di giorni, fare clic su **Elimina dati di archiviazione esportati e archivia dati archiviati dopo la durata massima (giorni)** e quindi specificare il numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="2074a-138">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="2074a-139">Per limitare l'eliminazione all'archiviazione dei dati esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.</span><span class="sxs-lookup"><span data-stu-id="2074a-139">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="2074a-140">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="2074a-140">Click **Commit**.</span></span>
    
## <a name="configure-site-level-archiving-options"></a><span data-ttu-id="2074a-141">Configurare le opzioni di archiviazione a livello di sito</span><span class="sxs-lookup"><span data-stu-id="2074a-141">Configure site level archiving options</span></span>

<span data-ttu-id="2074a-142">È possibile specificare le opzioni di archiviazione per un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="2074a-142">You can specify archiving options for a specific site.</span></span> <span data-ttu-id="2074a-143">Una configurazione del sito sostituisce la configurazione globale, ma solo per il sito specificato nella configurazione del sito.</span><span class="sxs-lookup"><span data-stu-id="2074a-143">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> 
  
1. <span data-ttu-id="2074a-144">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="2074a-144">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2074a-145">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2074a-145">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="2074a-146">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="2074a-146">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="2074a-147">Nella pagina **Configurazione archiviazione** fare clic su **nuovo**e quindi su **configurazione sito**.</span><span class="sxs-lookup"><span data-stu-id="2074a-147">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>
    
5. <span data-ttu-id="2074a-148">In **Seleziona un sito**selezionare il sito da configurare per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="2074a-148">In **Select a Site**, select the site to be configured for archiving.</span></span>
    
6. <span data-ttu-id="2074a-149">In **nuova impostazione archiviazione**, nella casella di riepilogo a discesa **Impostazioni archiviazione** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2074a-149">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="2074a-150">Per abilitare l'archiviazione solo per le sessioni di messaggistica istantanea (IM), fare clic su **Archivia sessioni**istantanee.</span><span class="sxs-lookup"><span data-stu-id="2074a-150">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="2074a-151">Per abilitare l'archiviazione sia per le sessioni di messaggistica istantanea che per le conferenze, fare clic su **Archivia messaggistica istantanea e sessioni di conferenza Web**.</span><span class="sxs-lookup"><span data-stu-id="2074a-151">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="2074a-152">Per disabilitare l'archiviazione per il criterio, fare clic su **Disattiva archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="2074a-152">To disable archiving for the policy, click **Disable archiving**.</span></span>
    
7. <span data-ttu-id="2074a-153">Anche in **nuove impostazioni di archiviazione**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2074a-153">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="2074a-154">Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca messaggistica istantanea o servizi di conferenza Web se l'archiviazione non riesce** .</span><span class="sxs-lookup"><span data-stu-id="2074a-154">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="2074a-155">Per usare Microsoft Exchange Server per archiviare i dati di archiviazione, fare clic sulla casella di controllo **integrazione di Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="2074a-155">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="2074a-156">Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita l'eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2074a-156">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="2074a-157">Per specificare l'eliminazione dopo un determinato numero di giorni, fare clic su **Elimina dati di archiviazione esportati e archivia dati archiviati dopo la durata massima (giorni)** e quindi specificare il numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="2074a-157">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="2074a-158">Per limitare l'eliminazione all'archiviazione dei dati esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.</span><span class="sxs-lookup"><span data-stu-id="2074a-158">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="2074a-159">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="2074a-159">Click **Commit**.</span></span>
    
## <a name="configure-pool-level-archiving-options"></a><span data-ttu-id="2074a-160">Configurare le opzioni di archiviazione a livello di pool</span><span class="sxs-lookup"><span data-stu-id="2074a-160">Configure pool level archiving options</span></span>

<span data-ttu-id="2074a-161">È possibile specificare le opzioni di archiviazione per un pool specifico.</span><span class="sxs-lookup"><span data-stu-id="2074a-161">You can specify archiving options for a specific pool.</span></span> <span data-ttu-id="2074a-162">La configurazione del pool sostituisce la configurazione globale e la configurazione del sito, ma solo per il pool specificato nella configurazione del pool.</span><span class="sxs-lookup"><span data-stu-id="2074a-162">A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>
  
1. <span data-ttu-id="2074a-163">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="2074a-163">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="2074a-164">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2074a-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="2074a-165">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="2074a-165">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="2074a-166">Nella pagina **Configurazione archiviazione** fare clic su **nuovo**e quindi su **Configurazione pool**.</span><span class="sxs-lookup"><span data-stu-id="2074a-166">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>
    
5. <span data-ttu-id="2074a-167">In **Seleziona un servizio**selezionare il pool da configurare per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="2074a-167">In **Select a Service**, select the pool to be configured for archiving.</span></span>
    
6. <span data-ttu-id="2074a-168">In **nuova impostazione archiviazione**selezionare una delle opzioni di archiviazione seguenti nell'elenco a discesa **Impostazioni archiviazione** :</span><span class="sxs-lookup"><span data-stu-id="2074a-168">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="2074a-169">**Disabilita archiviazione**</span><span class="sxs-lookup"><span data-stu-id="2074a-169">**Disable archiving**</span></span>
    
   - <span data-ttu-id="2074a-170">**Archivia sessioni di messaggistica istantanea**</span><span class="sxs-lookup"><span data-stu-id="2074a-170">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="2074a-171">**Archivia sessioni di messaggistica istantanea e Web Conferencing**</span><span class="sxs-lookup"><span data-stu-id="2074a-171">**Archive IM and web conferencing sessions**</span></span>
    
7. <span data-ttu-id="2074a-172">Anche nella pagina **nuova impostazione archiviazione** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2074a-172">Also in **New Archiving Setting** page, do the following:</span></span>
    
   - <span data-ttu-id="2074a-173">Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca messaggistica istantanea o servizi di conferenza Web se l'archiviazione non riesce** .</span><span class="sxs-lookup"><span data-stu-id="2074a-173">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="2074a-174">Per usare Microsoft Exchange Server per archiviare i dati di archiviazione, fare clic sulla casella di controllo **integrazione di Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="2074a-174">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="2074a-175">Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita l'eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2074a-175">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="2074a-176">Per specificare l'eliminazione dopo un determinato numero di giorni, fare clic su **Elimina dati di archiviazione esportati e archivia dati archiviati dopo la durata massima (giorni)** e quindi specificare il numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="2074a-176">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="2074a-177">Per limitare l'eliminazione all'archiviazione dei dati esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.</span><span class="sxs-lookup"><span data-stu-id="2074a-177">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="2074a-178">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="2074a-178">Click **Commit**.</span></span>
    

