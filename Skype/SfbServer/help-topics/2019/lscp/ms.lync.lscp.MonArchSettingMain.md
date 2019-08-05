---
title: Configurazione archiviazione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
ROBOTS: NOINDEX, NOFOLLOW
description: "Puoi usare le configurazioni di archiviazione per controllare le opzioni di archiviazione per la distribuzione di Skype for Business Server, incluso l'abilitazione e la disabilitazione delle opzioni seguenti:"
ms.openlocfilehash: 8c585d2a5816f2d29b3f468fd48fa82c36254d5f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192146"
---
# <a name="archiving-configuration"></a><span data-ttu-id="1fa2e-103">Configurazione archiviazione</span><span class="sxs-lookup"><span data-stu-id="1fa2e-103">Archiving Configuration</span></span>
 
<span data-ttu-id="1fa2e-104">Puoi usare le configurazioni di archiviazione per controllare le opzioni di archiviazione per la distribuzione di Skype for Business Server, incluso l'abilitazione e la disabilitazione delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1fa2e-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="1fa2e-105">Blocco delle sessioni di messaggistica istantanea o Web Conferencing se l'archiviazione non riesce</span><span class="sxs-lookup"><span data-stu-id="1fa2e-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="1fa2e-106">Integrazione con lo spazio di archiviazione di Exchange per utenti ospitati in Exchange</span><span class="sxs-lookup"><span data-stu-id="1fa2e-106">Integration with Exchange storage, for users homed on Exchange</span></span>
    
- <span data-ttu-id="1fa2e-107">Eliminazione dei dati archiviati</span><span class="sxs-lookup"><span data-stu-id="1fa2e-107">Purging of archived data</span></span>
    
<span data-ttu-id="1fa2e-108">Le configurazioni di archiviazione includono la configurazione globale e, facoltativamente, una o più configurazioni di archiviazione per sito e pool:</span><span class="sxs-lookup"><span data-stu-id="1fa2e-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="1fa2e-109">**Configurazione globale** La configurazione globale viene creata per impostazione predefinita in tutte le distribuzioni di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="1fa2e-110">È possibile modificare la configurazione globale, ma non eliminare la configurazione di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="1fa2e-111">Se si tenta di eliminarla, tutte le opzioni verranno ripristinate ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="1fa2e-112">**Configurazione sito (facoltativa)** È possibile specificare una o più configurazioni di archiviazione del sito, ognuna delle quali può essere configurata per controllare le opzioni di archiviazione per un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="1fa2e-113">Una configurazione di sito ha la priorità rispetto alla configurazione globale, ma solo per i siti specificati nelle configurazioni sito di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="1fa2e-114">È possibile modificare o eliminare le configurazioni sito.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="1fa2e-115">**Configurazione del pool (facoltativo)** Puoi specificare una o più configurazioni di archiviazione del pool per controllare le opzioni di archiviazione per un pool specifico.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="1fa2e-116">Una configurazione pool ha la priorità rispetto alla configurazione globale e alla configurazione sito, ma solo per i pool specificati nelle configurazioni pool di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="1fa2e-117">È possibile modificare o eliminare le configurazioni pool.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1fa2e-118">Le configurazioni di archiviazione si applicano agli utenti ospitati in Skype for Business Server e, se si usa Exchange per archiviare i dati di archiviazione in Microsoft Exchange, agli utenti ospitati in Exchange, ma vengono implementati in modo leggermente diverso per gli utenti ospitati in Exchange.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange but are implemented slightly differently for users homed on Exchange.</span></span> <span data-ttu-id="1fa2e-119">Le differenze sono descritte nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="1fa2e-p105">Nella pagina **Configurazione archiviazione** sono elencati tutti i criteri di archiviazione configurati per la distribuzione. Sono inoltre mostrati il nome del criterio, l'ambito (globale, sito o pool) e quali opzioni di archiviazione sono abilitate per ogni configurazione di archiviazione. Nella pagina **Configurazione archiviazione** sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1fa2e-p105">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment. It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration. From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="1fa2e-123">**Nuovo** È possibile aggiungere una o più delle configurazioni di archiviazione facoltative seguenti.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="1fa2e-124">Configurazione sito</span><span class="sxs-lookup"><span data-stu-id="1fa2e-124">Site configuration</span></span>
    
  - <span data-ttu-id="1fa2e-125">Configurazione pool</span><span class="sxs-lookup"><span data-stu-id="1fa2e-125">Pool configuration</span></span>
    
- <span data-ttu-id="1fa2e-126">**Modifica** È possibile modificare le opzioni di tutte le configurazioni di archiviazione elencate nella pagina.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="1fa2e-127">Usando questa voce, è possibile scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1fa2e-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="1fa2e-128">**Mostra dettagli** Questa opzione apre una finestra di dialogo in cui è possibile modificare le opzioni di archiviazione per la configurazione di archiviazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="1fa2e-129">È possibile mostrare i dettagli solo per una configurazione di archiviazione alla volta.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="1fa2e-130">**Seleziona tutto** Questa opzione consente di selezionare tutte le configurazioni di archiviazione nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="1fa2e-131">**Eliminare** Questa opzione Elimina tutte le configurazioni di archiviazione selezionate.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="1fa2e-132">**Azione** Puoi usare questa opzione per abilitare o disabilitare rapidamente l'archiviazione delle sessioni di messaggistica istantanea o delle sessioni di conferenza Web in qualsiasi configurazione elencata nella pagina, invece di modificare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="1fa2e-133">Le opzioni disponibili in **Azione** dipendono dall'opzione attualmente specificata nella configurazione di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="1fa2e-134">Tutte le opzioni sono disponibili, a eccezione di quella attualmente applicata per la configurazione di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="1fa2e-135">Tra le opzioni disponibili sono incluse le seguenti:</span><span class="sxs-lookup"><span data-stu-id="1fa2e-135">Options include the following:</span></span>
    
  - <span data-ttu-id="1fa2e-136">**Archivia sessioni di messaggistica istantanea**</span><span class="sxs-lookup"><span data-stu-id="1fa2e-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="1fa2e-137">**Archivia sessioni di messaggistica istantanea e Web Conferencing**</span><span class="sxs-lookup"><span data-stu-id="1fa2e-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="1fa2e-138">**Disabilita archiviazione**</span><span class="sxs-lookup"><span data-stu-id="1fa2e-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="1fa2e-139">**Aggiornare** È possibile aggiornare la pagina di **configurazione dell'archiviazione** per verificare lo stato delle opzioni di tutte le configurazioni di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="1fa2e-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="1fa2e-140">Per informazioni dettagliate sulla funzionalità e le funzionalità di archiviazione, inclusa l'integrazione di Exchange, vedere [pianificare l'archiviazione in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [distribuire l'archiviazione per Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md)e [gestire l'archiviazione in Skype for business Server](../../../manage/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="1fa2e-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server](../../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server](../../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server](../../../manage/archiving/archiving.md).</span></span>

