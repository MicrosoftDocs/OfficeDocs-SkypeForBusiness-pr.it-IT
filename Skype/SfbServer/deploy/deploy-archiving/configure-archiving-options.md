---
title: Configurare le opzioni di archiviazione per Skype for Business Server
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
ms.assetid: 2f534697-ac7f-45b7-8cdc-ba67f052223b
description: "Riepilogo: leggere questo argomento per informazioni su come configurare le opzioni di archiviazione iniziale per Skype for Business Server. Le configurazioni di archiviazione vengono inizialmente impostate durante la distribuzione dell'archiviazione, ma è possibile modificarle, aggiungerle ed eliminarle dopo la distribuzione."
ms.openlocfilehash: 0a4803b821ee082a548b9f429b9596fd8019500f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815536"
---
# <a name="configure-archiving-options-for-skype-for-business-server"></a><span data-ttu-id="e3e9b-104">Configurare le opzioni di archiviazione per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e3e9b-104">Configure archiving options for Skype for Business Server</span></span>
 
<span data-ttu-id="e3e9b-105">**Riepilogo:** Leggere questo argomento per informazioni su come configurare le opzioni di archiviazione iniziale per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-105">**Summary:** Read this topic to learn how to configure initial archiving options for Skype for Business Server.</span></span> <span data-ttu-id="e3e9b-106">Le configurazioni di archiviazione vengono inizialmente impostate durante la distribuzione dell'archiviazione, ma è possibile modificarle, aggiungerle ed eliminarle dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-106">You initially set up archiving configurations when you deploy archiving, but you can change, add, and delete configurations after deployment.</span></span>
  
<span data-ttu-id="e3e9b-107">Per configurare le configurazioni di archiviazione iniziali, utilizzare il Pannello di controllo di Skype for Business Server per specificare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="e3e9b-107">To configure initial archiving configurations, you use Skype for Business Server Control Panel to specify the following:</span></span>
  
- <span data-ttu-id="e3e9b-108">Configurazione a livello globale creata per impostazione predefinita quando si distribuisce Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e3e9b-108">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="e3e9b-109">Configurazioni facoltative a livello di sito che specificano la modalità di implementazione dell'archiviazione per un sito specifico</span><span class="sxs-lookup"><span data-stu-id="e3e9b-109">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="e3e9b-110">Configurazioni facoltative a livello di pool che specificano la modalità di implementazione dell'archiviazione per un pool specifico</span><span class="sxs-lookup"><span data-stu-id="e3e9b-110">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="e3e9b-111">Sarà necessario configurare le opzioni per gli elementi seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3e9b-111">You will need to configure options for the following:</span></span>
  
- <span data-ttu-id="e3e9b-112">Se abilitare o disabilitare l'archiviazione</span><span class="sxs-lookup"><span data-stu-id="e3e9b-112">Whether to enable or disable archiving</span></span>
    
- <span data-ttu-id="e3e9b-113">Se archiviare le sessioni di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="e3e9b-113">Whether to archive IM sessions</span></span>
    
- <span data-ttu-id="e3e9b-114">Se archiviare le sessioni di Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="e3e9b-114">Whether to archive web conferencing sessions</span></span>
    
- <span data-ttu-id="e3e9b-115">Se bloccare l'attività quando l'archiviazione non è disponibile</span><span class="sxs-lookup"><span data-stu-id="e3e9b-115">Whether to block activity when archiving is not available</span></span>
    
- <span data-ttu-id="e3e9b-116">Se utilizzare l'integrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="e3e9b-116">Whether to use Exchange integration</span></span>
    
- <span data-ttu-id="e3e9b-117">Come configurare l'eliminazione e l'esportazione dei dati</span><span class="sxs-lookup"><span data-stu-id="e3e9b-117">How to set up purging and exporting of data</span></span>
    
> [!NOTE]
> <span data-ttu-id="e3e9b-118">È consigliabile specificare tutte le opzioni appropriate prima di abilitare l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-118">You should specify all appropriate options before enabling archiving.</span></span> 
  
<span data-ttu-id="e3e9b-119">Per informazioni dettagliate sull'implementazione delle configurazioni di archiviazione, incluse le opzioni che è possibile specificare e la gerarchia delle configurazioni di archiviazione, vedere Pianificare l'archiviazione [in Skype for Business Server.](../../plan-your-deployment/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="e3e9b-119">For details about how archiving configurations are implemented, including which options you can specify and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span> <span data-ttu-id="e3e9b-120">Per informazioni dettagliate su come gestire le configurazioni dopo la distribuzione tramite il Pannello di controllo o tramite Windows PowerShell, vedere Gestire le opzioni di archiviazione [in Skype for Business Server.](../../manage/archiving/options.md)</span><span class="sxs-lookup"><span data-stu-id="e3e9b-120">For details about how to manage configurations after deployment by using the Control Panel or by using Windows PowerShell, see [Manage archiving options in Skype for Business Server](../../manage/archiving/options.md).</span></span>
  
## <a name="configure-global-level-archiving-options"></a><span data-ttu-id="e3e9b-121">Configurare le opzioni di archiviazione a livello globale</span><span class="sxs-lookup"><span data-stu-id="e3e9b-121">Configure global level archiving options</span></span>

<span data-ttu-id="e3e9b-122">Quando si aggiunge l'archiviazione alla topologia e si pubblica la topologia, Skype for Business Server crea una configurazione globale per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-122">When you add archiving to your topology and publish the topology, Skype for Business Server creates a global configuration for archiving.</span></span> <span data-ttu-id="e3e9b-123">Per impostazione predefinita, nella configurazione globale non è abilitata alcuna opzione di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-123">By default, no archiving options are enabled in the global configuration.</span></span> <span data-ttu-id="e3e9b-124">La configurazione globale controlla le opzioni abilitate per l'intera distribuzione, a meno che non si impostino configurazioni a livello di sito o di pool, le quali hanno la priorità sulla configurazione globale.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-124">The global configuration controls which options are enabled for your entire deployment, unless you set up site or pool configurations, which override the global configuration.</span></span>
  
<span data-ttu-id="e3e9b-125">Per configurare le opzioni di archiviazione a livello globale:</span><span class="sxs-lookup"><span data-stu-id="e3e9b-125">To configure archiving options at the global level:</span></span>
  
1. <span data-ttu-id="e3e9b-126">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-126">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e3e9b-127">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-127">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e3e9b-128">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-128">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="e3e9b-129">Nella pagina **Configurazione archiviazione** fare clic su **Globale**, su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-129">On the **Archiving Configuration** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="e3e9b-130">In **Modifica Impostazione di archiviazione - Globale** selezionare una delle opzioni di archiviazione seguenti nell'elenco a discesa **Impostazione di archiviazione**:</span><span class="sxs-lookup"><span data-stu-id="e3e9b-130">In **Edit Archiving Setting - Global**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="e3e9b-131">**Disabilita archiviazione**</span><span class="sxs-lookup"><span data-stu-id="e3e9b-131">**Disable archiving**</span></span>
    
   - <span data-ttu-id="e3e9b-132">**Archivia sessioni di messaggistica istantanea**</span><span class="sxs-lookup"><span data-stu-id="e3e9b-132">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="e3e9b-133">**Archivia sessioni di messaggistica istantanea e Web Conferencing**</span><span class="sxs-lookup"><span data-stu-id="e3e9b-133">**Archive IM and web conferencing sessions**</span></span>
    
6. <span data-ttu-id="e3e9b-134">Nella pagina **Modifica impostazione di archiviazione - Globale** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3e9b-134">Also on the **Edit Archiving Setting - Global** page, do the following:</span></span>
    
   - <span data-ttu-id="e3e9b-135">Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca sessioni di messaggistica istantanea o Web Conferencing se l'archiviazione non riesce**.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-135">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="e3e9b-136">Per utilizzare il Microsoft Exchange Server per archiviare i dati di archiviazione, selezionare la casella di controllo **integrazione di Microsoft Exchange.**</span><span class="sxs-lookup"><span data-stu-id="e3e9b-136">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="e3e9b-137">Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3e9b-137">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="e3e9b-138">Per specificare l'eliminazione dopo un numero specifico di giorni, fare clic su **Elimina dati di archiviazione esportati e archiviati dopo durata massima (giorni)** e quindi specificare il numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-138">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="e3e9b-139">Per limitare l'eliminazione ai dati di archiviazione esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-139">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="e3e9b-140">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-140">Click **Commit**.</span></span>
    
## <a name="configure-site-level-archiving-options"></a><span data-ttu-id="e3e9b-141">Configurare le opzioni di archiviazione a livello di sito</span><span class="sxs-lookup"><span data-stu-id="e3e9b-141">Configure site level archiving options</span></span>

<span data-ttu-id="e3e9b-142">È possibile specificare le opzioni di archiviazione per un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-142">You can specify archiving options for a specific site.</span></span> <span data-ttu-id="e3e9b-143">Una configurazione di sito ha la priorità rispetto alla configurazione globale, ma solo per il sito specificato.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-143">A site configuration overrides the global configuration, but only for the site specified in the site configuration.</span></span> 
  
1. <span data-ttu-id="e3e9b-144">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-144">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e3e9b-145">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-145">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e3e9b-146">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-146">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="e3e9b-147">Nella pagina **Configurazione archiviazione** fare clic su **Nuovo** e quindi su **Configurazione sito**.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-147">On the **Archiving Configuration** page, click **New**, and then click **Site Configuration**.</span></span>
    
5. <span data-ttu-id="e3e9b-148">In **Seleziona un sito** selezionare il sito da configurare per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-148">In **Select a Site**, select the site to be configured for archiving.</span></span>
    
6. <span data-ttu-id="e3e9b-149">In **Nuova impostazione di archiviazione** eseguire una delle operazioni seguenti nella casella di riepilogo a discesa **Impostazione di archiviazione**:</span><span class="sxs-lookup"><span data-stu-id="e3e9b-149">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="e3e9b-150">Per abilitare l'archiviazione solo per le sessioni di messaggistica istantanea, fare clic su **Archivia sessioni di messaggistica istantanea**.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-150">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="e3e9b-151">Per abilitare l'archiviazione per le conferenze e le sessioni di messaggistica istantanea, fare clic su **Archivia sessioni di messaggistica istantanea e Web Conferencing**.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-151">To enable archiving for both IM sessions and conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="e3e9b-152">Per disabilitare l'archiviazione dei criteri, fare clic su **Disabilita archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-152">To disable archiving for the policy, click **Disable archiving**.</span></span>
    
7. <span data-ttu-id="e3e9b-153">Sempre in **Nuova impostazione di archiviazione** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3e9b-153">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="e3e9b-154">Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca sessioni di messaggistica istantanea o Web Conferencing se l'archiviazione non riesce**.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-154">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="e3e9b-155">Per utilizzare il Microsoft Exchange Server per archiviare i dati di archiviazione, selezionare la casella di controllo **integrazione di Microsoft Exchange.**</span><span class="sxs-lookup"><span data-stu-id="e3e9b-155">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="e3e9b-156">Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3e9b-156">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="e3e9b-157">Per specificare l'eliminazione dopo un numero specifico di giorni, fare clic su **Elimina dati di archiviazione esportati e archiviati dopo durata massima (giorni)** e quindi specificare il numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-157">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="e3e9b-158">Per limitare l'eliminazione ai dati di archiviazione esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-158">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="e3e9b-159">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-159">Click **Commit**.</span></span>
    
## <a name="configure-pool-level-archiving-options"></a><span data-ttu-id="e3e9b-160">Configurare le opzioni di archiviazione a livello di pool</span><span class="sxs-lookup"><span data-stu-id="e3e9b-160">Configure pool level archiving options</span></span>

<span data-ttu-id="e3e9b-161">È possibile specificare le opzioni di archiviazione per un pool specifico.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-161">You can specify archiving options for a specific pool.</span></span> <span data-ttu-id="e3e9b-162">La configurazione di un pool ha la priorità sulla configurazione globale e sulla configurazione del sito, ma solo per il pool specificato nella relativa configurazione.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-162">A pool configuration overrides the global configuration and site configuration, but only for the pool specified in the pool configuration.</span></span>
  
1. <span data-ttu-id="e3e9b-163">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-163">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2. <span data-ttu-id="e3e9b-164">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-164">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e3e9b-165">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-165">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="e3e9b-166">Nella pagina **Configurazione archiviazione** fare clic su **Nuovo** e quindi su **Configurazione pool**.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-166">On the **Archiving Configuration** page, click **New**, and then click **Pool Configuration**.</span></span>
    
5. <span data-ttu-id="e3e9b-167">In **Seleziona un servizio** selezionare il pool da configurare per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-167">In **Select a Service**, select the pool to be configured for archiving.</span></span>
    
6. <span data-ttu-id="e3e9b-168">In **Nuova impostazione di archiviazione** selezionare una delle opzioni di archiviazione seguenti nell'elenco a discesa **Impostazione di archiviazione**:</span><span class="sxs-lookup"><span data-stu-id="e3e9b-168">In **New Archiving Setting**, in the **Archiving setting** drop-down list, select one of the following archiving options:</span></span>
    
   - <span data-ttu-id="e3e9b-169">**Disabilita archiviazione**</span><span class="sxs-lookup"><span data-stu-id="e3e9b-169">**Disable archiving**</span></span>
    
   - <span data-ttu-id="e3e9b-170">**Archivia sessioni di messaggistica istantanea**</span><span class="sxs-lookup"><span data-stu-id="e3e9b-170">**Archive IM sessions**</span></span>
    
   - <span data-ttu-id="e3e9b-171">**Archivia sessioni di messaggistica istantanea e Web Conferencing**</span><span class="sxs-lookup"><span data-stu-id="e3e9b-171">**Archive IM and web conferencing sessions**</span></span>
    
7. <span data-ttu-id="e3e9b-172">Sempre nella pagina **Nuova impostazione di archiviazione** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3e9b-172">Also in **New Archiving Setting** page, do the following:</span></span>
    
   - <span data-ttu-id="e3e9b-173">Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca sessioni di messaggistica istantanea o Web Conferencing se l'archiviazione non riesce**.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-173">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="e3e9b-174">Per utilizzare il Microsoft Exchange Server per archiviare i dati di archiviazione, selezionare la casella di controllo **integrazione di Microsoft Exchange.**</span><span class="sxs-lookup"><span data-stu-id="e3e9b-174">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="e3e9b-175">Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e3e9b-175">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
   - <span data-ttu-id="e3e9b-176">Per specificare l'eliminazione dopo un numero specifico di giorni, fare clic su **Elimina dati di archiviazione esportati e archiviati dopo durata massima (giorni)** e quindi specificare il numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-176">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
   - <span data-ttu-id="e3e9b-177">Per limitare l'eliminazione ai dati di archiviazione esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-177">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
8. <span data-ttu-id="e3e9b-178">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="e3e9b-178">Click **Commit**.</span></span>
    

