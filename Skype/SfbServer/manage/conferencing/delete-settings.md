---
title: Eliminare le impostazioni di configurazione delle riunioni in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ebafb86-13b9-468e-beda-f85f6786da85
description: 'Riepilogo: informazioni su come eliminare le impostazioni di configurazione delle riunioni in Skype for Business Server.'
ms.openlocfilehash: cbf63ba635077dd61599d4bc84a740906b662a6c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991861"
---
# <a name="delete-meeting-configuration-settings-in-skype-for-business-server"></a><span data-ttu-id="74342-103">Eliminare le impostazioni di configurazione delle riunioni in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="74342-103">Delete meeting configuration settings in Skype for Business Server</span></span>
 
<span data-ttu-id="74342-104">**Riepilogo:** Informazioni su come eliminare le impostazioni di configurazione delle riunioni in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="74342-104">**Summary:** Learn how to delete meeting configuration settings in Skype for Business Server.</span></span>
  
<span data-ttu-id="74342-105">Puoi eliminare le impostazioni di configurazione delle riunioni usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="74342-105">You can delete meeting configuration settings by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
<span data-ttu-id="74342-106">È possibile eliminare una configurazione di un sito o di un utente, ma non è possibile eliminare la configurazione globale.</span><span class="sxs-lookup"><span data-stu-id="74342-106">You can delete a site or user configuration, but you cannot delete the global configuration.</span></span> <span data-ttu-id="74342-107">Se si tenta di eliminare la configurazione globale, viene reimpostata automaticamente sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="74342-107">If you attempt to delete the global configuration, it is automatically reset to the default values.</span></span>
  
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="74342-108">Eliminare le impostazioni di configurazione delle riunioni tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="74342-108">Delete meeting configuration settings by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="74342-109">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="74342-109">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="74342-110">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="74342-110">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="74342-111">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **Configurazione riunione**.</span><span class="sxs-lookup"><span data-stu-id="74342-111">In the left navigation bar, click **Conferencing**, and then click **Meeting Configuration**.</span></span>
    
4. <span data-ttu-id="74342-112">Nell'elenco delle configurazioni delle riunioni fare clic sulla configurazione del sito o del pool che si desidera eliminare, fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="74342-112">In the list of meeting configurations, click the site or pool configuration that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-meeting-configuration-settings-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="74342-113">Eliminare le impostazioni di configurazione delle riunioni con Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="74342-113">Delete meeting configuration settings by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="74342-114">Per eliminare le impostazioni della riunione, usare il cmdlet **Remove-CsMeetingConfiguration** .</span><span class="sxs-lookup"><span data-stu-id="74342-114">To delete meeting settings, use the **Remove-CsMeetingConfiguration** cmdlet.</span></span>
  
<span data-ttu-id="74342-115">Il comando seguente rimuove le impostazioni di configurazione delle riunioni applicate al sito Redmond:</span><span class="sxs-lookup"><span data-stu-id="74342-115">The following command removes the meeting configuration settings applied to the Redmond site:</span></span>
  
```PowerShell
Remove-CsMeetingConfiguration -Identity "site:Redmond"
```

<span data-ttu-id="74342-116">Il comando successivo consente di rimuovere tutte le impostazioni di configurazione della riunione applicate all'ambito del sito:</span><span class="sxs-lookup"><span data-stu-id="74342-116">The next command removes all the meeting configuration settings applied to the site scope:</span></span>
  
```PowerShell
Get-CsMeetingConfiguration -Filter "site:*" | Remove-CsMeetingConfiguration
```

<span data-ttu-id="74342-117">Per altre informazioni, incluso un elenco completo dei parametri, vedere [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="74342-117">For more information, including a complete list of parameters, see [Remove-CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csmeetingconfiguration?view=skype-ps).</span></span>
  

