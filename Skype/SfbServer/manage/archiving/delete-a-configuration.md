---
title: Eliminare una configurazione di archiviazione in Skype for Business Server
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
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Riepilogo: informazioni su come eliminare una configurazione di archiviazione in Skype for Business Server.'
ms.openlocfilehash: 43913485ce18660b6c7fa7ce747ceeaaebd49923
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095410"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="a2845-103">Eliminare una configurazione di archiviazione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a2845-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="a2845-104">**Riepilogo:** Informazioni su come eliminare una configurazione di archiviazione in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a2845-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="a2845-105">È possibile eliminare una configurazione di sito o di pool, ma non è possibile eliminare la configurazione globale.</span><span class="sxs-lookup"><span data-stu-id="a2845-105">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="a2845-106">Se si elimina la configurazione globale, viene reimpostata automaticamente sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a2845-106">If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="a2845-107">Eliminare una configurazione di archiviazione tramite il Pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="a2845-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="a2845-108">Per eliminare una configurazione di archiviazione tramite il Pannello di controllo:</span><span class="sxs-lookup"><span data-stu-id="a2845-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="a2845-109">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="a2845-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="a2845-110">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a2845-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="a2845-111">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="a2845-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="a2845-112">Nell'elenco delle configurazioni di archiviazione fare clic sulla configurazione di sito o di pool che si desidera eliminare, fare clic su **Modifica** e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="a2845-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="a2845-113">È anche possibile fare clic sulla configurazione globale, ma scegliere questa opzione solo se si desidera ripristinare i valori predefiniti della configurazione globale.</span><span class="sxs-lookup"><span data-stu-id="a2845-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="a2845-114">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="a2845-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="a2845-115">Eliminare una configurazione di archiviazione tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="a2845-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="a2845-116">È inoltre possibile eliminare una configurazione di archiviazione utilizzando il cmdlet **Remove-CsArchivingConfiguration.**</span><span class="sxs-lookup"><span data-stu-id="a2845-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="a2845-117">Ad esempio, il comando seguente rimuove le impostazioni di configurazione di archiviazione applicate al sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="a2845-117">For example, the following command removes the archiving configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="a2845-118">Quando viene eliminato un criterio configurato nell'ambito del sito, gli utenti gestiti in precedenza dal criterio del sito verranno invece regolati automaticamente dal criterio di archiviazione globale:</span><span class="sxs-lookup"><span data-stu-id="a2845-118">When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="a2845-119">Il comando seguente rimuove tutte le impostazioni di configurazione dell'archiviazione applicate all'ambito del servizio:</span><span class="sxs-lookup"><span data-stu-id="a2845-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="a2845-120">Il comando successivo rimuove tutte le impostazioni di configurazione dell'archiviazione in cui l'archiviazione di Exchange è stata disabilitata:</span><span class="sxs-lookup"><span data-stu-id="a2845-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="a2845-121">È inoltre possibile utilizzare il cmdlet **Remove-CsArchivingConfiguration** per reimpostare le impostazioni globali ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="a2845-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="a2845-122">Si supponga, ad esempio, di aver abilitato l'archiviazione delle sessioni di messaggistica istantanea a livello globale. il comando seguente reimposta il valore predefinito none, disabilitando l'archiviazione a livello globale:</span><span class="sxs-lookup"><span data-stu-id="a2845-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="a2845-123">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsArchivingConfiguration.](/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a2845-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>