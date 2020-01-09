---
title: Creare un nuovo criterio di archiviazione in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Riepilogo: informazioni su come creare un nuovo criterio di archiviazione per Skype for Business Server.'
ms.openlocfilehash: 8542c31050cf4ca9383c22b39c83b28309d3ea32
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992733"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="af4e6-103">Creare un nuovo criterio di archiviazione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="af4e6-103">Create a new archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="af4e6-104">**Riepilogo:** Informazioni su come creare un nuovo criterio di archiviazione per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="af4e6-104">**Summary:** Learn how to create a new archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="af4e6-105">È possibile creare nuovi criteri di archiviazione usando il pannello di controllo o usando i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af4e6-105">You can create new archiving policies by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a><span data-ttu-id="af4e6-106">Creare un nuovo criterio di archiviazione tramite il pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="af4e6-106">Create a new archiving policy by using the Control Panel</span></span>

<span data-ttu-id="af4e6-107">Per creare un nuovo criterio di archiviazione tramite il pannello di controllo:</span><span class="sxs-lookup"><span data-stu-id="af4e6-107">To create a new archiving policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="af4e6-108">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="af4e6-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="af4e6-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="af4e6-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="af4e6-110">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="af4e6-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="af4e6-111">Fare clic su **nuovo**e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="af4e6-111">Click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="af4e6-112">Per creare criteri di archiviazione a livello di sito, fare clic su **criteri sito**e quindi, in **selezionare un sito**, fare clic sul sito a cui applicare il criterio.</span><span class="sxs-lookup"><span data-stu-id="af4e6-112">To create a site-level archiving policy, click **Site policy**, and then, in **Select a site**, click the site to which the policy is to be applied.</span></span>
    
   - <span data-ttu-id="af4e6-113">Per creare criteri di archiviazione a livello di utente, fare clic su **criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="af4e6-113">To create a user-level archiving policy, click **User policy**.</span></span>
    
5. <span data-ttu-id="af4e6-114">In **nuovi criteri di archiviazione**eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="af4e6-114">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="af4e6-115">In **nome**specificare un nome per il nuovo criterio, ad esempio ContosoEsterni.</span><span class="sxs-lookup"><span data-stu-id="af4e6-115">In **Name**, specify a name for the new policy (for example, externalContoso).</span></span>
    
   - <span data-ttu-id="af4e6-116">In **Descrizione**specificare i dettagli relativi al criterio, ad esempio criteri di archiviazione degli utenti esterni per contoso.</span><span class="sxs-lookup"><span data-stu-id="af4e6-116">In **Description**, provide details about what the policy is (for example, External user archiving policy for Contoso).</span></span>
    
   - <span data-ttu-id="af4e6-117">Per controllare l'archiviazione delle comunicazioni con gli utenti interni, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne** .</span><span class="sxs-lookup"><span data-stu-id="af4e6-117">To control archiving of communications with internal users, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="af4e6-118">Per controllare l'archiviazione delle comunicazioni con utenti esterni, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne** .</span><span class="sxs-lookup"><span data-stu-id="af4e6-118">To control archiving of communications with external users, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="af4e6-119">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="af4e6-119">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="af4e6-120">Le impostazioni di un criterio utente si applicano solo agli utenti e ai gruppi utente specifici a cui si applicano i criteri.</span><span class="sxs-lookup"><span data-stu-id="af4e6-120">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="af4e6-121">Per informazioni dettagliate, vedere [applicare un criterio di archiviazione agli utenti in Skype for Business Server](apply-a-policy-to-users.md).</span><span class="sxs-lookup"><span data-stu-id="af4e6-121">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a><span data-ttu-id="af4e6-122">Creare un nuovo criterio di archiviazione tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="af4e6-122">Create a new archiving policy by using Windows PowerShell</span></span>

<span data-ttu-id="af4e6-123">Puoi anche creare nuovi criteri di archiviazione usando il cmdlet **New-CsArchivingPolicy** di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="af4e6-123">You can also create new archiving policies by using the Windows PowerShell **New-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="af4e6-124">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="af4e6-124">For more information, see the help topic for the [New-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a><span data-ttu-id="af4e6-125">Per creare un nuovo criterio di archiviazione a livello di sito</span><span class="sxs-lookup"><span data-stu-id="af4e6-125">To create a new archiving policy at the site level</span></span>

<span data-ttu-id="af4e6-126">Questo comando crea un nuovo criterio di archiviazione per il sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="af4e6-126">This command creates a new archiving policy for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a><span data-ttu-id="af4e6-127">Per creare un nuovo criterio di archiviazione a livello per utente</span><span class="sxs-lookup"><span data-stu-id="af4e6-127">To create a new archiving policy at the per-user level</span></span>

<span data-ttu-id="af4e6-128">Per creare un nuovo criterio di archiviazione a livello per utente, è sufficiente specificare un'identità univoca quando si creano i criteri:</span><span class="sxs-lookup"><span data-stu-id="af4e6-128">To create a new archiving policy at the per-user level, simply specify a unique Identity when creating the policy:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a><span data-ttu-id="af4e6-129">Per creare un nuovo criterio di archiviazione che consente l'archiviazione delle sessioni di comunicazione interne</span><span class="sxs-lookup"><span data-stu-id="af4e6-129">To create a new archiving policy that enables archiving of internal communication sessions</span></span>

<span data-ttu-id="af4e6-130">Dato che nei comandi precedenti non sono stati specificati parametri (ad eccezione del parametro di identità obbligatoria), i nuovi criteri utilizzeranno i valori predefiniti per tutte le relative proprietà.</span><span class="sxs-lookup"><span data-stu-id="af4e6-130">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding commands, the new policies will use the default values for all their properties.</span></span> <span data-ttu-id="af4e6-131">Per creare criteri che usano valori di proprietà diversi, includere semplicemente il parametro e il valore del parametro appropriati.</span><span class="sxs-lookup"><span data-stu-id="af4e6-131">To create policies that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="af4e6-132">Ad esempio, il comando seguente crea un criterio di archiviazione che consente l'archiviazione delle sessioni di messaggistica istantanea interne:</span><span class="sxs-lookup"><span data-stu-id="af4e6-132">For example, the following command creates an archiving policy that permits archiving of internal instant messaging sessions:</span></span> 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a><span data-ttu-id="af4e6-133">Per creare un nuovo criterio di archiviazione che consente l'archiviazione di sessioni di comunicazione interne ed esterne</span><span class="sxs-lookup"><span data-stu-id="af4e6-133">To create a new archiving policy that enables archiving of both internal and external communication sessions</span></span>

<span data-ttu-id="af4e6-134">Più valori di proprietà possono essere modificati includendo più parametri.</span><span class="sxs-lookup"><span data-stu-id="af4e6-134">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="af4e6-135">Questo comando, ad esempio, configura il nuovo criterio per l'archiviazione delle sessioni di messaggistica istantanea interne ed esterne:</span><span class="sxs-lookup"><span data-stu-id="af4e6-135">For example, this command configures the new policy to archive both internal and external instant messaging sessions:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```
