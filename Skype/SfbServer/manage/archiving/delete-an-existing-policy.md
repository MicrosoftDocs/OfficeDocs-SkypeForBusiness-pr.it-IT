---
title: Eliminare un criterio di archiviazione esistente in Skype for Business Server
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
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Riepilogo: informazioni su come eliminare un criterio di archiviazione per Skype for Business Server.'
ms.openlocfilehash: 8e2a2c21f6d137fcdb87e69c041cf08143092be1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818928"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="b7752-103">Eliminare un criterio di archiviazione esistente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b7752-103">Delete an existing archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="b7752-104">**Riepilogo:** Informazioni su come eliminare un criterio di archiviazione per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7752-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="b7752-105">Puoi eliminare un criterio utente o un criterio del sito, ma non il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="b7752-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="b7752-106">Se elimini il criterio globale, Skype for Business Server Reimposta automaticamente i criteri sui valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="b7752-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="b7752-107">Eliminare un criterio tramite il pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="b7752-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="b7752-108">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="b7752-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="b7752-109">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b7752-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="b7752-110">Sulla barra di spostamento sinistra fare clic su **monitoraggio e archiviazione**, quindi fare clic su **criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="b7752-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="b7752-111">Nell'elenco dei criteri di archiviazione fare clic sul criterio dell'utente o del sito che si desidera eliminare, fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="b7752-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="b7752-112">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="b7752-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="b7752-113">Eliminare un criterio tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b7752-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="b7752-114">È anche possibile eliminare i criteri di archiviazione usando il cmdlet **Remove-CsArchivingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="b7752-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="b7752-115">Ad esempio, il comando seguente elimina il criterio con il sito Identity: Redmond.</span><span class="sxs-lookup"><span data-stu-id="b7752-115">For example, the following command deletes the policy with the Identity site:Redmond.</span></span> <span data-ttu-id="b7752-116">Quando un criterio configurato a livello di sito viene eliminato, gli utenti gestiti in precedenza dal criterio del sito verranno automaticamente regolati dal criterio di archiviazione globale:</span><span class="sxs-lookup"><span data-stu-id="b7752-116">When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="b7752-117">Questo comando rimuove tutti i criteri di archiviazione applicati al livello per utente:</span><span class="sxs-lookup"><span data-stu-id="b7752-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="b7752-118">Questo comando rimuove tutti i criteri di archiviazione in cui l'archiviazione interna è stata disattivata:</span><span class="sxs-lookup"><span data-stu-id="b7752-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="b7752-119">Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="b7752-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
