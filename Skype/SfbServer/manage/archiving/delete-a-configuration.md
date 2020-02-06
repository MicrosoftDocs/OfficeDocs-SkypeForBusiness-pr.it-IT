---
title: Eliminare una configurazione di archiviazione in Skype for Business Server
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
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 'Riepilogo: informazioni su come eliminare una configurazione di archiviazione in Skype for Business Server.'
ms.openlocfilehash: 82415e2cac7293d991280c3fcee6e64d684f5c26
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818938"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a><span data-ttu-id="8031f-103">Eliminare una configurazione di archiviazione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8031f-103">Delete an archiving configuration in Skype for Business Server</span></span>

<span data-ttu-id="8031f-104">**Riepilogo:** Informazioni su come eliminare una configurazione di archiviazione in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8031f-104">**Summary:** Learn how to delete an archiving configuration in Skype for Business Server.</span></span>
  
<span data-ttu-id="8031f-105">È possibile eliminare una configurazione del sito o una configurazione del pool, ma non è possibile eliminare la configurazione globale.</span><span class="sxs-lookup"><span data-stu-id="8031f-105">You can delete a site configuration or pool configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="8031f-106">Se elimini la configurazione globale, viene reimpostata automaticamente sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="8031f-106">If you delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a><span data-ttu-id="8031f-107">Eliminare una configurazione di archiviazione tramite il pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="8031f-107">Delete an archiving configuration by using the Control Panel</span></span>

<span data-ttu-id="8031f-108">Per eliminare una configurazione di archiviazione tramite il pannello di controllo:</span><span class="sxs-lookup"><span data-stu-id="8031f-108">To delete an archiving configuration by using the Control Panel:</span></span>
  
1. <span data-ttu-id="8031f-109">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="8031f-109">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="8031f-110">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8031f-110">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="8031f-111">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**e quindi su **Configurazione archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="8031f-111">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Configuration**.</span></span>
    
4. <span data-ttu-id="8031f-112">Nell'elenco delle configurazioni di archiviazione fare clic sulla configurazione del sito o del pool che si desidera eliminare, fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="8031f-112">In the list of archiving configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="8031f-113">È anche possibile fare clic sulla configurazione globale, ma scegliere questa opzione solo se si vuole reimpostare la configurazione globale sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="8031f-113">You can also click the Global configuration, but choose this option only if you want to reset the Global configuration to the default values.</span></span> 
  
5. <span data-ttu-id="8031f-114">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8031f-114">Click **Commit**.</span></span>
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a><span data-ttu-id="8031f-115">Eliminare una configurazione di archiviazione tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8031f-115">Delete an archiving configuration by using Windows PowerShell</span></span>

<span data-ttu-id="8031f-116">Puoi anche eliminare una configurazione di archiviazione usando il cmdlet **Remove-CsArchivingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="8031f-116">You can also delete an archiving configuration by using the **Remove-CsArchivingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="8031f-117">Ad esempio, il comando seguente rimuove le impostazioni di configurazione dell'archiviazione applicate al sito Redmond.</span><span class="sxs-lookup"><span data-stu-id="8031f-117">For example, the following command removes the archiving configuration settings applied to the Redmond site.</span></span> <span data-ttu-id="8031f-118">Quando un criterio configurato nell'ambito del sito viene eliminato, gli utenti gestiti in precedenza dal criterio del sito verranno regolati automaticamente dal criterio di archiviazione globale:</span><span class="sxs-lookup"><span data-stu-id="8031f-118">When a policy configured at the site scope is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="8031f-119">Il comando seguente rimuove tutte le impostazioni di configurazione dell'archiviazione applicate all'ambito del servizio:</span><span class="sxs-lookup"><span data-stu-id="8031f-119">The following command removes all the archiving configuration settings applied to the service scope:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

<span data-ttu-id="8031f-120">Il comando successivo consente di rimuovere tutte le impostazioni di configurazione dell'archiviazione in cui è stato disabilitato l'archiviazione di Exchange:</span><span class="sxs-lookup"><span data-stu-id="8031f-120">The next command removes all the archiving configuration settings where Exchange archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

<span data-ttu-id="8031f-121">Puoi anche usare il cmdlet **Remove-CsArchivingConfiguration** per reimpostare le impostazioni globali su valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="8031f-121">You can also use the **Remove-CsArchivingConfiguration** cmdlet to reset the global settings to default values.</span></span> <span data-ttu-id="8031f-122">Ad esempio, supponiamo di aver abilitato l'archiviazione delle sessioni di messaggistica istantanea a livello globale; con il comando seguente viene reimpostato il valore per l'impostazione predefinita None, che disattiverà l'archiviazione a livello globale:</span><span class="sxs-lookup"><span data-stu-id="8031f-122">For example, suppose you have enabled IM session archiving at the global level; the following command will reset the value to the default of None, which will disable archiving at the global level:</span></span>
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

<span data-ttu-id="8031f-123">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="8031f-123">For more information, see the help topic for the [Remove-CsArchivingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet.</span></span>
