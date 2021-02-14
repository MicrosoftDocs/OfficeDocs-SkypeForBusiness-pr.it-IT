---
title: Configurazione archiviazione
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
- ms.lync.lscp.MonArchSettingMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9c2fd164-a9b8-40e6-a1c4-423a7fe34aba
description: "Le configurazioni di archiviazione consentono di controllare le opzioni di archiviazione per la distribuzione di Skype for Business Server, inclusa l'abilitazione e la disabilitazione delle opzioni seguenti:"
ms.openlocfilehash: 96a01579f43833017978fc6067b5a86f9e9951aa
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827006"
---
# <a name="archiving-configuration"></a><span data-ttu-id="e8ad9-103">Configurazione archiviazione</span><span class="sxs-lookup"><span data-stu-id="e8ad9-103">Archiving Configuration</span></span>
 
<span data-ttu-id="e8ad9-104">Le configurazioni di archiviazione consentono di controllare le opzioni di archiviazione per la distribuzione di Skype for Business Server, inclusa l'abilitazione e la disabilitazione delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8ad9-104">You use Archiving configurations to control archiving options for your Skype for Business Server deployment, including enabling and disabling the following options:</span></span>
  
- <span data-ttu-id="e8ad9-105">Blocco delle sessioni di messaggistica istantanea o conferenza se l'archiviazione non riesce</span><span class="sxs-lookup"><span data-stu-id="e8ad9-105">Blocking of instant messaging (IM) or conferencing sessions if archiving fails</span></span>
    
- <span data-ttu-id="e8ad9-106">Integrazione con l'archiviazione di Exchange 2013, per gli utenti ospitati in Exchange 2013</span><span class="sxs-lookup"><span data-stu-id="e8ad9-106">Integration with Exchange 2013 storage, for users homed on Exchange 2013</span></span>
    
- <span data-ttu-id="e8ad9-107">Eliminazione dei dati archiviati</span><span class="sxs-lookup"><span data-stu-id="e8ad9-107">Purging of archived data</span></span>
    
<span data-ttu-id="e8ad9-108">Le configurazioni di archiviazione includono la configurazione globale e, facoltativamente, una o più configurazioni di archiviazione per siti e pool:</span><span class="sxs-lookup"><span data-stu-id="e8ad9-108">Archiving configurations include the global configuration and, optionally, one or more site and pool Archiving configurations:</span></span>
  
- <span data-ttu-id="e8ad9-109">**Configurazione globale** La configurazione globale viene creata per impostazione predefinita in tutte le distribuzioni di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-109">**Global configuration** The global configuration is created by default in all Skype for Business Server deployments.</span></span> <span data-ttu-id="e8ad9-110">La configurazione globale viene modificata, ma non è possibile eliminarla.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-110">You edit the global configuration, but you cannot delete this Archiving configuration.</span></span> <span data-ttu-id="e8ad9-111">Se si tenta di eliminarlo, tutte le opzioni verranno ripristinate ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-111">If you try to delete it, all options are reset to the defaults.</span></span>
    
- <span data-ttu-id="e8ad9-112">**Configurazione del sito (facoltativo)** È possibile specificare una o più configurazioni di archiviazione del sito, ognuna delle quali può essere configurata per controllare le opzioni di archiviazione per un sito specifico.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-112">**Site configuration (optional)** You can specify one or more site Archiving configurations, each of which you can configure to control archiving options for a specific site.</span></span> <span data-ttu-id="e8ad9-113">Una configurazione di sito ha la precedenza sulla configurazione globale, ma solo per i siti specificati nelle configurazioni del sito di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-113">A site configuration overrides the global configuration, but only for the sites specified in the Archiving site configurations.</span></span> <span data-ttu-id="e8ad9-114">È possibile modificare o eliminare le configurazioni dei siti.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-114">You can edit or delete site configurations.</span></span>
    
- <span data-ttu-id="e8ad9-115">**Configurazione pool (facoltativo)** È possibile specificare una o più configurazioni di archiviazione del pool per controllare le opzioni di archiviazione per un pool specifico.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-115">**Pool configuration (optional)** You can specify one or more pool Archiving configuration, to control archiving options for a specific pool.</span></span> <span data-ttu-id="e8ad9-116">La configurazione di un pool sostituisce la configurazione globale e la configurazione del sito, ma solo per i pool specificati nelle configurazioni dei pool di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-116">A pool configuration overrides the global configuration and site configuration, but only for the pools specified in Archiving pool configurations.</span></span> <span data-ttu-id="e8ad9-117">È possibile modificare o eliminare le configurazioni del pool.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-117">You can edit or delete pool configurations.</span></span>
    
> [!NOTE]
> <span data-ttu-id="e8ad9-118">Le configurazioni di archiviazione si applicano agli utenti ospitati in Skype for Business Server e, se si utilizza Exchange per archiviare i dati di archiviazione in Microsoft Exchange, agli utenti ospitati in Exchange 2013, ma sono implementati in modo leggermente diverso per gli utenti ospitati in Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-118">Archiving configurations apply to users homed on Skype for Business Server and, if you use Exchange to store archiving data in Microsoft Exchange, to users homed on Exchange 2013 but are implemented slightly differently for users homed on Exchange 2013.</span></span> <span data-ttu-id="e8ad9-119">Le differenze sono descritte nella sezione successiva.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-119">The differences are described in the next section.</span></span> 
  
<span data-ttu-id="e8ad9-120">Nella **pagina Configurazione archiviazione** sono elencati i criteri di archiviazione configurati per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-120">The **Archiving Configuration** page lists each Archiving policy that is configured for your deployment.</span></span> <span data-ttu-id="e8ad9-121">Vengono inoltre visualizzati il nome del criterio, l'ambito (globale, sito o pool) e le opzioni di archiviazione abilitate per ogni configurazione di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-121">It also shows the policy name, scope (global, site, or pool), and which archiving options are enabled for each Archiving configuration.</span></span> <span data-ttu-id="e8ad9-122">Nella pagina **Configurazione archiviazione** sono disponibili le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8ad9-122">From the **Archiving Configuration** page, you have the following options:</span></span>
- <span data-ttu-id="e8ad9-123">**Nuovo** È possibile aggiungere una o più delle seguenti configurazioni di archiviazione facoltative.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-123">**New** You can add one or more of each of the following optional Archiving configurations.</span></span>
    
  - <span data-ttu-id="e8ad9-124">Configurazione del sito</span><span class="sxs-lookup"><span data-stu-id="e8ad9-124">Site configuration</span></span>
    
  - <span data-ttu-id="e8ad9-125">Configurazione pool</span><span class="sxs-lookup"><span data-stu-id="e8ad9-125">Pool configuration</span></span>
    
- <span data-ttu-id="e8ad9-126">**Modifica** È possibile modificare le opzioni di qualsiasi configurazione di archiviazione elencata nella pagina.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-126">**Edit** You can change the options of any of the Archiving configurations listed on the page.</span></span> <span data-ttu-id="e8ad9-127">Usando questa voce, è possibile scegliere tra le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8ad9-127">Using this option, you can do the following:</span></span>
    
  - <span data-ttu-id="e8ad9-128">**Mostra dettagli** Questa opzione consente di aprire una finestra di dialogo in cui è possibile modificare le opzioni di archiviazione per la configurazione di archiviazione selezionata.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-128">**Show details** This option opens a dialog box in which you can change the archiving options for the selected Archiving configuration.</span></span> <span data-ttu-id="e8ad9-129">È possibile visualizzare solo i dettagli per una configurazione di archiviazione alla volta.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-129">You can only show details for one Archiving configuration at a time.</span></span>
    
  - <span data-ttu-id="e8ad9-130">**Seleziona tutto** Questa opzione consente di selezionare tutte le configurazioni di archiviazione nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-130">**Select all** This option selects all Archiving configurations in the list.</span></span>
    
  - <span data-ttu-id="e8ad9-131">**Elimina** Questa opzione consente di eliminare tutte le configurazioni di archiviazione selezionate.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-131">**Delete** This option deletes all selected Archiving configurations.</span></span>
    
- <span data-ttu-id="e8ad9-132">**Azione** È possibile utilizzare questa opzione per abilitare o disabilitare rapidamente l'archiviazione di sessioni di messaggistica istantanea o di conferenze Web in qualsiasi configurazione elencata nella pagina, anziché modificare la configurazione.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-132">**Action** You can use this option to quickly enable or disable archiving of IM sessions or web conferencing sessions in any configuration listed on the page, instead of editing the configuration.</span></span> <span data-ttu-id="e8ad9-133">Le opzioni disponibili in **Azione** dipendono dall'opzione attualmente specificata nella configurazione di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-133">The options available under **Action** depend on what option is currently specified in the Archiving configuration.</span></span> <span data-ttu-id="e8ad9-134">Sono disponibili tutte le opzioni, ad eccezione dell'opzione attualmente in vigore per la configurazione di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-134">All options are available, except the option currently in effect for the Archiving configuration.</span></span> <span data-ttu-id="e8ad9-135">Tra le opzioni sono incluse le seguenti:</span><span class="sxs-lookup"><span data-stu-id="e8ad9-135">Options include the following:</span></span>
    
  - <span data-ttu-id="e8ad9-136">**Archivia sessioni di messaggistica istantanea**</span><span class="sxs-lookup"><span data-stu-id="e8ad9-136">**Archive IM sessions**</span></span>
    
  - <span data-ttu-id="e8ad9-137">**Archivia sessioni di messaggistica istantanea e Web Conferencing**</span><span class="sxs-lookup"><span data-stu-id="e8ad9-137">**Archive IM and web conferencing sessions**</span></span>
    
  - <span data-ttu-id="e8ad9-138">**Disabilita archiviazione**</span><span class="sxs-lookup"><span data-stu-id="e8ad9-138">**Disable archiving**</span></span>
    
- <span data-ttu-id="e8ad9-139">**Aggiorna** È possibile aggiornare la pagina **Configurazione archiviazione** per verificare lo stato delle opzioni di tutte le configurazioni di archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e8ad9-139">**Refresh** You can refresh the **Archiving Configuration** page to verify the status of the options of all Archiving configurations.</span></span>
    
<span data-ttu-id="e8ad9-140">Per informazioni dettagliate sulle funzionalità di archiviazione, inclusa l'integrazione di Exchange, vedere Pianificare l'archiviazione [in Skype for Business Server 2015,](../../plan-your-deployment/archiving/archiving.md)Distribuire l'archiviazione per Skype for Business Server [2015](../../deploy/deploy-archiving/deploy-archiving.md)e Gestire l'archiviazione [in Skype for Business Server 2015.](../../manage/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="e8ad9-140">For details about the Archiving feature and capabilities, including Exchange integration, see [Plan for archiving in Skype for Business Server 2015](../../plan-your-deployment/archiving/archiving.md), [Deploy archiving for Skype for Business Server 2015](../../deploy/deploy-archiving/deploy-archiving.md), and [Manage archiving in Skype for Business Server 2015](../../manage/archiving/archiving.md).</span></span>

