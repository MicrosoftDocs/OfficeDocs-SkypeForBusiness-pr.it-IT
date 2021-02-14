---
title: Eliminare un criterio di archiviazione esistente in Skype for Business Server
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
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 'Riepilogo: informazioni su come eliminare un criterio di archiviazione per Skype for Business Server.'
ms.openlocfilehash: 7d71fd9ca03f743cd51e0161cd1a3b437be43cb2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817616"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a><span data-ttu-id="b18e8-103">Eliminare un criterio di archiviazione esistente in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="b18e8-103">Delete an existing archiving policy in Skype for Business Server</span></span>

<span data-ttu-id="b18e8-104">**Riepilogo:** Informazioni su come eliminare un criterio di archiviazione per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b18e8-104">**Summary:** Learn how to delete an archiving policy for Skype for Business Server.</span></span>
  
<span data-ttu-id="b18e8-105">È possibile eliminare un criterio utente o un criterio sito, ma non il criterio globale.</span><span class="sxs-lookup"><span data-stu-id="b18e8-105">You can delete a user policy or site policy, but not the global policy.</span></span> <span data-ttu-id="b18e8-106">Se si elimina il criterio globale, Skype for Business Server reimposta automaticamente il criterio ai valori predefiniti.</span><span class="sxs-lookup"><span data-stu-id="b18e8-106">If you delete the global policy, Skype for Business Server automatically resets the policy to the default values.</span></span>
  
## <a name="delete-a-policy-by-using-the-control-panel"></a><span data-ttu-id="b18e8-107">Eliminare un criterio tramite il Pannello di controllo</span><span class="sxs-lookup"><span data-stu-id="b18e8-107">Delete a policy by using the Control Panel</span></span>

1. <span data-ttu-id="b18e8-108">Da un account utente assegnato al ruolo CsArchivingAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="b18e8-108">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span> 
    
2. <span data-ttu-id="b18e8-109">Apri una finestra del browser e quindi immetti l'URL di amministratore per aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b18e8-109">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span> 
    
3. <span data-ttu-id="b18e8-110">Nella barra di navigazione di sinistra fare clic su **Monitoraggio e archiviazione**, quindi scegliere **Criteri di archiviazione**.</span><span class="sxs-lookup"><span data-stu-id="b18e8-110">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
4. <span data-ttu-id="b18e8-111">Nell'elenco dei criteri di archiviazione fare clic sul criterio utente o sito che si desidera eliminare, su **Modifica** e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="b18e8-111">In the list of archiving policies, click the user or site policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
5. <span data-ttu-id="b18e8-112">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="b18e8-112">Click **Commit**.</span></span>
    
## <a name="delete-a-policy-by-using-windows-powershell"></a><span data-ttu-id="b18e8-113">Eliminare un criterio tramite Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b18e8-113">Delete a policy by using Windows PowerShell</span></span>

<span data-ttu-id="b18e8-114">È inoltre possibile eliminare i criteri di archiviazione utilizzando il cmdlet **Remove-CsArchivingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="b18e8-114">You can also delete archiving policies by using the **Remove-CsArchivingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="b18e8-115">Ad esempio, il comando seguente elimina il criterio con Identità site:Redmond.</span><span class="sxs-lookup"><span data-stu-id="b18e8-115">For example, the following command deletes the policy with the Identity site:Redmond.</span></span> <span data-ttu-id="b18e8-116">Quando viene eliminato un criterio configurato a livello di sito, gli utenti gestiti in precedenza dal criterio del sito verranno invece regolati automaticamente dal criterio di archiviazione globale:</span><span class="sxs-lookup"><span data-stu-id="b18e8-116">When a policy configured at the site level is deleted, users previously managed by the site policy will automatically be governed by the global archiving policy instead:</span></span>
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

<span data-ttu-id="b18e8-117">Questo comando rimuove tutti i criteri di archiviazione applicati al livello per utente:</span><span class="sxs-lookup"><span data-stu-id="b18e8-117">This command removes all the archiving policies applied to the per-user level:</span></span>
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

<span data-ttu-id="b18e8-118">Questo comando rimuove tutti i criteri di archiviazione in cui è stata disabilitata l'archiviazione interna:</span><span class="sxs-lookup"><span data-stu-id="b18e8-118">This command removes all the archiving policies where internal archiving has been disabled:</span></span>
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

<span data-ttu-id="b18e8-119">Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Remove-CsArchivingPolicy.](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="b18e8-119">For more information, see the help topic for the [Remove-CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet.</span></span>
