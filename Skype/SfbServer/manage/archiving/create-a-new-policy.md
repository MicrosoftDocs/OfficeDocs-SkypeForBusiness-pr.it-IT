---
title: Creare un nuovo criterio di archiviazione in Skype for Business Server
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
ms.assetid: 50c39731-ba2f-49c2-a571-6dc373f6aaeb
description: 'Riepilogo: informazioni su come creare un nuovo criterio di archiviazione per Skype for Business Server.'
ms.openlocfilehash: fe3a80708d3810a085f1814e6d16ff3cd4c6057c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095420"
---
# <a name="create-a-new-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="3db83-103">Creare un nuovo criterio di archiviazione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="3db83-103">Create a new archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="3db83-104">**Riepilogo:** Informazioni su come creare un nuovo criterio di archiviazione per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3db83-104">**Summary:** Learn how to create a new archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="3db83-105">È possibile creare nuovi criteri di archiviazione utilizzando il Pannello di controllo o Windows PowerShell cmdlet.</span><span class="sxs-lookup"><span data-stu-id="3db83-105">You can create new archiving policies by using the Control Panel or by using Windows PowerShell cmdlets.</span></span>
  
## <a name="create-a-new-archiving-policy-by-using-the-control-panel"></a><span data-ttu-id="3db83-106">Creare un nuovo criterio di archiviazione utilizzando il Pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="3db83-106">Create a new archiving policy by using the Control Panel</span></span>

<span data-ttu-id="3db83-107">Per creare un nuovo criterio di archiviazione utilizzando il Pannello di controllo:</span><span class="sxs-lookup"><span data-stu-id="3db83-107">To create a new archiving policy by using the Control Panel:</span></span>
  
1. <span data-ttu-id="3db83-108">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="3db83-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="3db83-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="3db83-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="3db83-110">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="3db83-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="3db83-111">Fare clic su **Nuovo** e quindi eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3db83-111">Click **New**, and then do one of the following:</span></span> 
    
   - <span data-ttu-id="3db83-112">Per creare un criterio di archiviazione **a** livello di sito, fare clic su Criteri sito e quindi in Selezionare un sito fare clic sul sito a cui applicare il criterio.</span><span class="sxs-lookup"><span data-stu-id="3db83-112">To create a site-level archiving policy, click **Site policy**, and then, in **Select a site**, click the site to which the policy is to be applied.</span></span>
    
   - <span data-ttu-id="3db83-113">Per creare criteri di archiviazione a livello di utente, fare clic su **Criteri utente**.</span><span class="sxs-lookup"><span data-stu-id="3db83-113">To create a user-level archiving policy, click **User policy**.</span></span>
    
5. <span data-ttu-id="3db83-114">In **Nuovi criteri di archiviazione** eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="3db83-114">In **New Archiving Policy**, do the following:</span></span>
    
   - <span data-ttu-id="3db83-115">In **Nome** specificare un nome per i nuovi criteri, ad esempio ContosoEsterni.</span><span class="sxs-lookup"><span data-stu-id="3db83-115">In **Name**, specify a name for the new policy (for example, externalContoso).</span></span>
    
   - <span data-ttu-id="3db83-116">In **Descrizione** immettere informazioni dettagliate sugli scopi dei criteri, ad esempio "Criteri di archiviazione degli utenti esterni per Contoso".</span><span class="sxs-lookup"><span data-stu-id="3db83-116">In **Description**, provide details about what the policy is (for example, External user archiving policy for Contoso).</span></span>
    
   - <span data-ttu-id="3db83-117">Per controllare l'archiviazione delle comunicazioni con gli utenti interni, selezionare o deselezionare la casella di controllo **Archivia comunicazioni interne**.</span><span class="sxs-lookup"><span data-stu-id="3db83-117">To control archiving of communications with internal users, select or clear the **Archive internal communications** check box.</span></span>
    
   - <span data-ttu-id="3db83-118">Per controllare l'archiviazione delle comunicazioni con gli utenti esterni, selezionare o deselezionare la casella di controllo **Archivia comunicazioni esterne**.</span><span class="sxs-lookup"><span data-stu-id="3db83-118">To control archiving of communications with external users, select or clear the **Archive external communications** check box.</span></span>
    
6. <span data-ttu-id="3db83-119">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="3db83-119">Click **Commit**.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="3db83-120">Le impostazioni dei criteri utente sono valide solo per gli utenti e i gruppi di utenti specifici a cui vengono applicati i criteri.</span><span class="sxs-lookup"><span data-stu-id="3db83-120">The settings of a user policy only apply to the specific users and user groups to which you apply the policy.</span></span> <span data-ttu-id="3db83-121">Per informazioni dettagliate, vedere [Apply an archiving policy to users in Skype for Business Server.](apply-a-policy-to-users.md)</span><span class="sxs-lookup"><span data-stu-id="3db83-121">For details, see [Apply an archiving policy to users in Skype for Business Server](apply-a-policy-to-users.md).</span></span> 
  
## <a name="create-a-new-archiving-policy-by-using-windows-powershell"></a><span data-ttu-id="3db83-122">Creare un nuovo criterio di archiviazione utilizzando Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="3db83-122">Create a new archiving policy by using Windows PowerShell</span></span>

<span data-ttu-id="3db83-123">È inoltre possibile creare nuovi criteri di archiviazione utilizzando Windows PowerShell **cmdlet New-CsArchivingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="3db83-123">You can also create new archiving policies by using the Windows PowerShell **New-CsArchivingPolicy** cmdlet.</span></span> <span data-ttu-id="3db83-124">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [New-CsArchivingPolicy.](/powershell/module/skype/new-csarchivingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="3db83-124">For more information, see the help topic for the [New-CsArchivingPolicy](/powershell/module/skype/new-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
  
### <a name="to-create-a-new-archiving-policy-at-the-site-level"></a><span data-ttu-id="3db83-125">Per creare un nuovo criterio di archiviazione a livello di sito</span><span class="sxs-lookup"><span data-stu-id="3db83-125">To create a new archiving policy at the site level</span></span>

<span data-ttu-id="3db83-126">Questo comando crea nuovi criteri di archiviazione per il sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="3db83-126">This command creates a new archiving policy for the Redmond site:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond"
```

### <a name="to-create-a-new-archiving-policy-at-the-per-user-level"></a><span data-ttu-id="3db83-127">Per creare un nuovo criterio di archiviazione a livello di singolo utente</span><span class="sxs-lookup"><span data-stu-id="3db83-127">To create a new archiving policy at the per-user level</span></span>

<span data-ttu-id="3db83-128">Per creare un nuovo criterio di archiviazione a livello di singolo utente, è sufficiente specificare un'identità univoca durante la creazione del criterio:</span><span class="sxs-lookup"><span data-stu-id="3db83-128">To create a new archiving policy at the per-user level, simply specify a unique Identity when creating the policy:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "RedmondArchivingPolicy"
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-internal-communication-sessions"></a><span data-ttu-id="3db83-129">Per creare un nuovo criterio di archiviazione che consenta l'archiviazione delle sessioni di comunicazione interne</span><span class="sxs-lookup"><span data-stu-id="3db83-129">To create a new archiving policy that enables archiving of internal communication sessions</span></span>

<span data-ttu-id="3db83-130">Dal momento che nei comandi precedenti non sono stati specificati parametri, oltre al parametro Identity obbligatorio, i nuovi criteri useranno i valori predefiniti per ogni proprietà.</span><span class="sxs-lookup"><span data-stu-id="3db83-130">Because no parameters (other than the mandatory Identity parameter) were specified in the preceding commands, the new policies will use the default values for all their properties.</span></span> <span data-ttu-id="3db83-131">Per creare criteri che usano valori di proprietà diversi, includere semplicemente il parametro e il valore di parametro appropriato.</span><span class="sxs-lookup"><span data-stu-id="3db83-131">To create policies that use different property values, simply include the appropriate parameter and parameter value.</span></span> <span data-ttu-id="3db83-132">Ad esempio, il comando seguente crea un criterio di archiviazione che consente l'archiviazione delle sessioni di messaggistica istantanea interne:</span><span class="sxs-lookup"><span data-stu-id="3db83-132">For example, the following command creates an archiving policy that permits archiving of internal instant messaging sessions:</span></span> 
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True
```

### <a name="to-create-a-new-archiving-policy-that-enables-archiving-of-both-internal-and-external-communication-sessions"></a><span data-ttu-id="3db83-133">Per creare un nuovo criterio di archiviazione che consenta l'archiviazione di sessioni di comunicazione sia interne che esterne</span><span class="sxs-lookup"><span data-stu-id="3db83-133">To create a new archiving policy that enables archiving of both internal and external communication sessions</span></span>

<span data-ttu-id="3db83-134">È possibile modificare più valori di proprietà includendo più parametri.</span><span class="sxs-lookup"><span data-stu-id="3db83-134">Multiple property values can be modified by including multiple parameters.</span></span> <span data-ttu-id="3db83-135">Ad esempio, questo comando configura il nuovo criterio per archiviare le sessioni di messaggistica istantanea interne ed esterne:</span><span class="sxs-lookup"><span data-stu-id="3db83-135">For example, this command configures the new policy to archive both internal and external instant messaging sessions:</span></span>
  
```PowerShell
New-CsArchivingPolicy -Identity "site:Redmond" -ArchiveInternal $True -ArchiveExternal $True
```