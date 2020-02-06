---
title: Gestire le opzioni di archiviazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 50399f26-58a3-4ce2-8229-32a8cafc7733
description: 'Riepilogo: informazioni su come configurare le opzioni di archiviazione per Skype for Business Server.'
ms.openlocfilehash: af5c8f90cd49f556e1e787e5f550b54da1976c45
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818898"
---
# <a name="manage-archiving-options-in-skype-for-business-server"></a><span data-ttu-id="43a6a-103">Gestire le opzioni di archiviazione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="43a6a-103">Manage archiving options in Skype for Business Server</span></span>

<span data-ttu-id="43a6a-104">**Riepilogo:** Informazioni su come configurare le opzioni di archiviazione per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="43a6a-104">**Summary:** Learn how to configure archiving options for Skype for Business Server.</span></span>
  
<span data-ttu-id="43a6a-105">L'archiviazione viene inizialmente configurata in fase di distribuzione, ma è possibile modificare, aggiungere ed eliminare configurazioni dopo la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="43a6a-105">You initially configure archiving at deployment, but you can change, add, and delete configurations after deployment.</span></span> <span data-ttu-id="43a6a-106">Le opzioni di archiviazione determinano se:</span><span class="sxs-lookup"><span data-stu-id="43a6a-106">Archiving options determine whether to:</span></span> 
  
- <span data-ttu-id="43a6a-107">Abilitare o disabilitare l'archiviazione</span><span class="sxs-lookup"><span data-stu-id="43a6a-107">Enable or disable archiving</span></span>
    
- <span data-ttu-id="43a6a-108">Archivia sessioni di messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="43a6a-108">Archive IM sessions</span></span>
    
- <span data-ttu-id="43a6a-109">Sessioni di Web Conferencing di archiviazione</span><span class="sxs-lookup"><span data-stu-id="43a6a-109">Archive web conferencing sessions</span></span>
    
- <span data-ttu-id="43a6a-110">Bloccare l'attività quando l'archiviazione non è disponibile</span><span class="sxs-lookup"><span data-stu-id="43a6a-110">Block activity when archiving is not available</span></span>
    
- <span data-ttu-id="43a6a-111">Usare l'integrazione di Exchange</span><span class="sxs-lookup"><span data-stu-id="43a6a-111">Use Exchange integration</span></span>
    
- <span data-ttu-id="43a6a-112">Configurare l'eliminazione e l'esportazione dei dati</span><span class="sxs-lookup"><span data-stu-id="43a6a-112">Set up purging and exporting of data</span></span>
    
<span data-ttu-id="43a6a-113">È possibile specificare le opzioni di configurazione ai livelli seguenti:</span><span class="sxs-lookup"><span data-stu-id="43a6a-113">You can specify configuration options at the following levels:</span></span>
  
- <span data-ttu-id="43a6a-114">Configurazione a livello globale creata per impostazione predefinita quando si distribuisce Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="43a6a-114">Global-level configuration that is created by default when you deploy Skype for Business Server</span></span>
    
- <span data-ttu-id="43a6a-115">Configurazioni facoltative a livello di sito che specificano la modalità di implementazione dell'archiviazione per un sito specifico</span><span class="sxs-lookup"><span data-stu-id="43a6a-115">Optional site-level configurations that specify how archiving is implemented for a specific site</span></span>
    
- <span data-ttu-id="43a6a-116">Configurazioni facoltative a livello di pool che specificano la modalità di implementazione dell'archiviazione per un pool specifico</span><span class="sxs-lookup"><span data-stu-id="43a6a-116">Optional pool-level configurations that specify how archiving is implemented for a specific pool</span></span>
    
<span data-ttu-id="43a6a-117">È possibile eliminare una configurazione del sito o una configurazione del pool, ma non è possibile eliminare la configurazione globale.</span><span class="sxs-lookup"><span data-stu-id="43a6a-117">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="43a6a-118">Se elimini la configurazione globale, viene reimpostata automaticamente sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="43a6a-118">If you delete the global configuration, it is automatically reset to the default values.</span></span> <span data-ttu-id="43a6a-119">Per informazioni dettagliate sull'implementazione delle configurazioni di archiviazione e sulla gerarchia delle configurazioni di archiviazione, vedere [pianificare l'archiviazione in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span><span class="sxs-lookup"><span data-stu-id="43a6a-119">For details about how archiving configurations are implemented and the hierarchy of archiving configurations, see [Plan for archiving in Skype for Business Server](../../plan-your-deployment/archiving/archiving.md).</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="43a6a-120">Configurare le opzioni di archiviazione tramite il pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="43a6a-120">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="43a6a-121">È possibile configurare le opzioni di archiviazione usando il pannello di controllo come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="43a6a-121">You can configure archiving options by using the Control Panel as follows:</span></span>
  
1. <span data-ttu-id="43a6a-122">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="43a6a-122">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="43a6a-123">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="43a6a-123">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="43a6a-124">Sulla barra di spostamento sinistra fare clic su **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="43a6a-124">In the left navigation bar, click **Archiving Configuration**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="43a6a-125">Configurare le opzioni di archiviazione tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="43a6a-125">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="43a6a-126">È anche possibile configurare le opzioni di archiviazione usando i cmdlet di Windows PowerShell elencati nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="43a6a-126">You can also configure archiving options by using the Windows PowerShell cmdlets listed in the following table.</span></span> <span data-ttu-id="43a6a-127">Per informazioni dettagliate sulla sintassi, inclusi tutti i parametri disponibili, Vedi [Skype for Business Server Management Shell](../management-shell.md).</span><span class="sxs-lookup"><span data-stu-id="43a6a-127">For details about syntax, including all available parameters, see [Skype for Business Server Management Shell](../management-shell.md).</span></span>
  

|<span data-ttu-id="43a6a-128">**Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="43a6a-128">**Cmdlet**</span></span>|<span data-ttu-id="43a6a-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="43a6a-129">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="43a6a-130">Get-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="43a6a-130">Get-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="43a6a-131">Restituisce informazioni sulle impostazioni di configurazione dell'archiviazione nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="43a6a-131">Returns information about the archiving configuration settings in your organization.</span></span>  <br/> |
|<span data-ttu-id="43a6a-132">New-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="43a6a-132">New-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="43a6a-133">Crea un nuovo set di impostazioni di messaggistica istantanea, che può essere usato per abilitare o disabilitare il salvataggio automatico delle sessioni di messaggistica istantanea e per bloccare i messaggi istantanei che non possono essere archiviati.</span><span class="sxs-lookup"><span data-stu-id="43a6a-133">Creates a new set of instant messaging (IM) settings, which can be used to enable or disable the automatic saving of IM sessions, and to block any instant messages that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="43a6a-134">Remove-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="43a6a-134">Remove-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="43a6a-135">Rimuove la raccolta specificata di impostazioni di archiviazione usate per abilitare o disabilitare il salvataggio automatico delle sessioni di messaggistica istantanea e per bloccare facoltativamente qualsiasi messaggio istantaneo che non può essere archiviato.</span><span class="sxs-lookup"><span data-stu-id="43a6a-135">Removes the specified collection of archiving settings that are used to enable or disable the automatic saving of instant messaging (IM) sessions, and to optionally block any instant message that cannot be archived.</span></span>  <br/> |
|<span data-ttu-id="43a6a-136">Set-CsArchivingConfiguration</span><span class="sxs-lookup"><span data-stu-id="43a6a-136">Set-CsArchivingConfiguration</span></span>  <br/> |<span data-ttu-id="43a6a-137">Modifica una raccolta esistente di opzioni di configurazione dell'archiviazione di messaggistica istantanea (IM).</span><span class="sxs-lookup"><span data-stu-id="43a6a-137">Modifies an existing collection of instant messaging (IM) archiving configuration options.</span></span>  <br/> |
