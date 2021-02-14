---
title: Eliminare i criteri conferenza in Skype for Business Server
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
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Riepilogo: informazioni su come eliminare i criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: eedb0b3676f0cc046e6096dca2cb1ec5ced5d6ec
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828196"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="7e840-103">Eliminare i criteri conferenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7e840-103">Delete conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="7e840-104">**Riepilogo:** Informazioni su come eliminare i criteri di conferenza in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7e840-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="7e840-105">È possibile eliminare i criteri di conferenza utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="7e840-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="7e840-106">Eliminare i criteri di conferenza tramite il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7e840-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="7e840-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="7e840-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="7e840-108">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7e840-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="7e840-109">Sulla barra di spostamento sinistra fare clic su Servizio **di** conferenza e quindi su **Criteri conferenza.**</span><span class="sxs-lookup"><span data-stu-id="7e840-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="7e840-110">Nell'elenco dei criteri conferenza fare clic sul sito o sui criteri utente che si desidera eliminare, fare clic su Modifica **e** quindi su **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="7e840-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="7e840-111">Eliminare i criteri conferenza tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="7e840-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="7e840-112">Per eliminare i criteri conferenza, utilizzare il cmdlet **Remove-CsConferencingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="7e840-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="7e840-113">Il comando seguente rimuove il criterio di conferenza con identità (Identity) RedmondConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="7e840-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="7e840-114">Il comando successivo elimina tutti i criteri di conferenza che consentono agli utenti esterni di registrare la conferenza:</span><span class="sxs-lookup"><span data-stu-id="7e840-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="7e840-115">Per ulteriori informazioni, inclusa la sintassi completa e un elenco di parametri, [vedere Remove-CsConferencingPolicy.](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="7e840-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
  

