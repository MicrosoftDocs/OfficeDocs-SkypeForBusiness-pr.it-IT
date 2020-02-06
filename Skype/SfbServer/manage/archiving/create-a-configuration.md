---
title: Creare una configurazione di archiviazione in Skype for Business Server
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
ms.assetid: dc574afa-0b7d-404f-99b3-c812430b7c70
description: 'Riepilogo: informazioni su come creare una configurazione di archiviazione per Skype for Business Server.'
ms.openlocfilehash: bc7319f2de8398dd3d9e9a79948d1af6eaeb98bc
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818958"
---
# <a name="create-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="e7de0-103">Creare una configurazione di archiviazione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e7de0-103">Create an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="e7de0-104">**Riepilogo:** Informazioni su come creare una configurazione di archiviazione per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e7de0-104">**Summary:** Learn how to create an archiving configuration for Skype for Business Server.</span></span>
  
## <a name="configure-archiving-options-by-using-the-control-panel"></a><span data-ttu-id="e7de0-105">Configurare le opzioni di archiviazione tramite il pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="e7de0-105">Configure archiving options by using the Control Panel</span></span>

<span data-ttu-id="e7de0-106">Per configurare le opzioni di archiviazione per un sito o un pool specifico:</span><span class="sxs-lookup"><span data-stu-id="e7de0-106">To configure archiving options for a specific site or pool:</span></span> 
  
1. <span data-ttu-id="e7de0-107">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="e7de0-107">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="e7de0-108">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e7de0-108">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="e7de0-109">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="e7de0-109">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="e7de0-110">Nella pagina **Configurazione archiviazione** fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7de0-110">On the **Archiving Configuration** page, click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="e7de0-111">Per creare una configurazione di archiviazione del sito, fare clic su **configurazione sito**e quindi selezionare il sito da configurare per l'archiviazione in **selezionare un sito**.</span><span class="sxs-lookup"><span data-stu-id="e7de0-111">To create a site archiving configuration, click **Site Configuration**, and then in **Select a site**, select the site to be configured for archiving.</span></span>
    
   - <span data-ttu-id="e7de0-112">Per creare una configurazione di archiviazione del pool, fare clic su **Configurazione pool**e quindi in **selezionare un pool**Selezionare il pool da configurare per l'archiviazione.</span><span class="sxs-lookup"><span data-stu-id="e7de0-112">To create a pool archiving configuration, click **Pool Configuration**, and then in **Select a pool**, select the pool to be configured for archiving.</span></span>
    
5. <span data-ttu-id="e7de0-113">In **nuova impostazione archiviazione**, nella casella di riepilogo a discesa **Impostazioni archiviazione** eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7de0-113">In **New Archiving Setting**, in the **Archiving setting** drop-down list box, do one of the following:</span></span>
    
   - <span data-ttu-id="e7de0-114">Per abilitare l'archiviazione solo per le sessioni di messaggistica istantanea (IM), fare clic su **Archivia sessioni**istantanee.</span><span class="sxs-lookup"><span data-stu-id="e7de0-114">To enable archiving only for instant messaging (IM) sessions, click **Archive IM sessions**.</span></span>
    
   - <span data-ttu-id="e7de0-115">Per abilitare l'archiviazione sia per le sessioni di messaggistica istantanea che per le conferenze Web, fare clic su **Archivia messaggistica istantanea e sessioni di conferenza Web**.</span><span class="sxs-lookup"><span data-stu-id="e7de0-115">To enable archiving for both IM sessions and web conferences, click **Archive IM and web conferencing sessions**.</span></span>
    
   - <span data-ttu-id="e7de0-116">Per disabilitare l'archiviazione per questa configurazione, fare clic su **Disattiva archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="e7de0-116">To disable archiving for this configuration, click **Disable archiving**.</span></span>
    
6. <span data-ttu-id="e7de0-117">Anche in **nuove impostazioni di archiviazione**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7de0-117">Also in **New Archiving Setting**, do the following:</span></span>
    
   - <span data-ttu-id="e7de0-118">Per bloccare l'attività quando l'archiviazione non è disponibile, selezionare la casella di controllo **Blocca messaggistica istantanea o servizi di conferenza Web se l'archiviazione non riesce** .</span><span class="sxs-lookup"><span data-stu-id="e7de0-118">To block activity when archiving is not available, select the **Block instant messaging (IM) or web conferencing sessions if archiving fails** check box.</span></span>
    
   - <span data-ttu-id="e7de0-119">Per usare Microsoft Exchange Server per archiviare i dati di archiviazione, fare clic sulla casella di controllo **integrazione di Microsoft Exchange** .</span><span class="sxs-lookup"><span data-stu-id="e7de0-119">To use Microsoft Exchange Server to store archiving data, click the **Microsoft Exchange integration** check box.</span></span>
    
   - <span data-ttu-id="e7de0-120">Per abilitare l'eliminazione dei dati, selezionare la casella di controllo **Abilita l'eliminazione dei dati di archiviazione** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e7de0-120">To enable data purging, select the **Enable purging of archiving data** check box, and then do one of the following:</span></span>
    
     - <span data-ttu-id="e7de0-121">Per specificare l'eliminazione dopo un determinato numero di giorni, fare clic su **Elimina dati di archiviazione esportati e archivia dati archiviati dopo la durata massima (giorni)** e quindi specificare il numero di giorni.</span><span class="sxs-lookup"><span data-stu-id="e7de0-121">To specify purging after a specific number of days, click **Purge exported archiving data and stored archiving data after maximum duration (days)**, and then specify the number of days.</span></span>
    
     - <span data-ttu-id="e7de0-122">Per limitare l'eliminazione all'archiviazione dei dati esportati, fare clic su **Elimina solo i dati di archiviazione esportati**.</span><span class="sxs-lookup"><span data-stu-id="e7de0-122">To limit purging to archiving data that has been exported, click **Purge exported archiving data only**.</span></span>
    
7. <span data-ttu-id="e7de0-123">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="e7de0-123">Click **Commit**.</span></span>
    
## <a name="configure-archiving-options-by-using-windows-powershell"></a><span data-ttu-id="e7de0-124">Configurare le opzioni di archiviazione tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e7de0-124">Configure archiving options by using Windows PowerShell</span></span>

<span data-ttu-id="e7de0-125">È anche possibile configurare le opzioni di archiviazione per un sito o un pool specifico usando il cmdlet **New-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="e7de0-125">You can also configure archiving options for a specific site or pool by using the **New-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="e7de0-126">Il comando seguente crea una nuova raccolta di impostazioni di configurazione dell'archiviazione per il sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="e7de0-126">The following command creates a new collection of archiving configuration settings for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="e7de0-127">Poiché non sono stati specificati parametri (ad eccezione del parametro di identità obbligatorio) nel comando precedente, la nuova raccolta di impostazioni di configurazione utilizzerà i valori predefiniti per tutte le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="e7de0-127">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding command, the new collection of configuration settings will use the default values for all its properties.</span></span> 
  
<span data-ttu-id="e7de0-128">Per creare impostazioni che usano valori di proprietà diversi, includere semplicemente il parametro e il valore del parametro appropriati.</span><span class="sxs-lookup"><span data-stu-id="e7de0-128">To create settings that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="e7de0-129">L'esempio seguente crea una raccolta di impostazioni di configurazione dell'archiviazione che, per impostazione predefinita, consentono l'archiviazione solo delle sessioni di messaggistica istantanea:</span><span class="sxs-lookup"><span data-stu-id="e7de0-129">The following example creates a collection of archiving configuration settings that, by default, allow archiving of instant messaging sessions only:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly"
```

<span data-ttu-id="e7de0-130">Più valori di proprietà possono essere modificati includendo più parametri.</span><span class="sxs-lookup"><span data-stu-id="e7de0-130">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="e7de0-131">Ad esempio, questo comando Configura le nuove impostazioni per l'archiviazione delle sessioni di messaggistica istantanea e per bloccare la messaggistica istantanea del servizio archiviazione non disponibile:</span><span class="sxs-lookup"><span data-stu-id="e7de0-131">For example, this command configures the new settings to archive instant messaging sessions and to block instant messaging of the archiving service is not available:</span></span>
  
```PowerShell
New-CsArchivingConfiguration -Identity "site:Redmond" -EnableArchiving "ImOnly" -BlockOnArchiveFailure $True
```

<span data-ttu-id="e7de0-132">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="e7de0-132">For more information, see the help topic for the [New-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/new-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
