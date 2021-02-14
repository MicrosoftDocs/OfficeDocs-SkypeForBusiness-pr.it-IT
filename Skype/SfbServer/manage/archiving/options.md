---
title: Gestire le opzioni di archiviazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Riepilogo: informazioni su come configurare le opzioni di archiviazione per Skype for Business Server.'
ms.openlocfilehash: ee0145ac0896e1bbb8d18c6a51116f2ddd75ee05
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817536"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a><span data-ttu-id="c0c17-103">Gestire le opzioni di archiviazione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c0c17-103">Manage archiving options in Skype for Business Server</span></span>

<span data-ttu-id="c0c17-104">**Riepilogo:** Informazioni su come configurare le opzioni di archiviazione per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c0c17-104">**Summary:** Learn how to configure archiving options for Skype for Business Server.</span></span>
  
<span data-ttu-id="c0c17-105">L'archiviazione viene configurata inizialmente durante la distribuzione, ma è possibile modificare, aggiungere ed eliminare configurazioni dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="c0c17-105">You initially configure archiving at deployment, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="c0c17-106">Le opzioni di archiviazione determinano se:</span><span class="sxs-lookup"><span data-stu-id="c0c17-106">Archiving options determine whether to:</span></span> 
  
- <span data-ttu-id="c0c17-107">Abilitare o disabilitare l'archiviazione</span><span class="sxs-lookup"><span data-stu-id="c0c17-107">Enable or disable archiving</span></span>
    
- <span data-ttu-id="c0c17-108">Archivia sessioni di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="c0c17-108">Archive IM sessions</span></span>
    
- <span data-ttu-id="c0c17-109">Archiviare le sessioni di Web Conferencing</span><span class="sxs-lookup"><span data-stu-id="c0c17-109">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="c0c17-110">Bloccare l'attività quando l'archiviazione non è disponibile</span><span class="sxs-lookup"><span data-stu-id="c0c17-110">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="c0c17-111">Utilizzare l'integrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="c0c17-111">Use Exchange integration</span></span>
    
- <span data-ttu-id="c0c17-112">Configurare l'eliminazione e l'esportazione dei dati</span><span class="sxs-lookup"><span data-stu-id="c0c17-112">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="c0c17-113">È possibile specificare le opzioni di configurazione ai livelli seguenti:</span><span class="sxs-lookup"><span data-stu-id="c0c17-113">You can specify configuration options at the following levels:</span></span>
  
- <span data-ttu-id="c0c17-114">Configurazione a livello globale creata per impostazione predefinita quando si distribuisce Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c0c17-114">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="c0c17-115">Configurazioni facoltative a livello di sito che specificano la modalità di implementazione dell'archiviazione per un sito specifico</span><span class="sxs-lookup"><span data-stu-id="c0c17-115">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="c0c17-116">Configurazioni facoltative a livello di pool che specificano la modalità di implementazione dell'archiviazione per un pool specifico</span><span class="sxs-lookup"><span data-stu-id="c0c17-116">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="c0c17-117">È possibile eliminare una configurazione di sito o pool, ma non è possibile eliminare la configurazione globale.</span><span class="sxs-lookup"><span data-stu-id="c0c17-117">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="c0c17-118">Se si elimina la configurazione globale, viene reimpostata automaticamente sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="c0c17-118">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="c0c17-119">Per informazioni dettagliate sull'implementazione delle configurazioni di archiviazione e sulla gerarchia delle configurazioni di archiviazione, vedere [Pianificare l'archiviazione in Skype for Business Server.](../../plan-your-deployment/archiving/archiving.md)</span><span class="sxs-lookup"><span data-stu-id="c0c17-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="c0c17-120">Configurare le opzioni di archiviazione tramite il Pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="c0c17-120">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="c0c17-121">È possibile configurare le opzioni di archiviazione utilizzando il Pannello di controllo nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="c0c17-121">You can configure archiving options by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="c0c17-122">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="c0c17-122">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="c0c17-123">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c0c17-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="c0c17-124">Sulla barra di spostamento sinistra fare clic su **Configurazione archiviazione.**</span><span class="sxs-lookup"><span data-stu-id="c0c17-124">In the left navigation bar, click **Archiving Configuration**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="c0c17-125">Configurare le opzioni di archiviazione tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0c17-125">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="c0c17-126">È inoltre possibile configurare le opzioni di archiviazione utilizzando Windows PowerShell cmdlet elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="c0c17-126">You can also configure archiving options by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="c0c17-127">Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri disponibili, vedere [Skype for Business Server Management Shell.](../management-shell.md)</span><span class="sxs-lookup"><span data-stu-id="c0c17-127">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="c0c17-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="c0c17-128">**Cmdlet**</span></span>|<span data-ttu-id="c0c17-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="c0c17-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c0c17-130">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c0c17-130">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="c0c17-131">Restituisce informazioni sulle impostazioni di configurazione dell'archiviazione nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c0c17-131">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="c0c17-132">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c0c17-132">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="c0c17-133">Crea un nuovo set di impostazioni di messaggistica istantanea, che può essere utilizzato per abilitare o disabilitare il salvataggio automatico delle sessioni di messaggistica istantanea e per bloccare i messaggi istantanei che non possono essere archiviati.</span><span class="sxs-lookup"><span data-stu-id="c0c17-133">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="c0c17-134">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c0c17-134">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="c0c17-135">Rimuove la raccolta specificata di impostazioni di archiviazione utilizzate per abilitare o disabilitare il salvataggio automatico delle sessioni di messaggistica istantanea e per bloccare facoltativamente i messaggi istantanei che non possono essere archiviati.</span><span class="sxs-lookup"><span data-stu-id="c0c17-135">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="c0c17-136">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="c0c17-136">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="c0c17-137">Modifica una raccolta esistente di opzioni di configurazione dell'archiviazione di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="c0c17-137">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
