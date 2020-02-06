---
title: Eliminare i criteri di conferenza in Skype for Business Server
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
ms.assetid: 497e6ca0-7a49-4f3e-9804-14414cf87b57
description: 'Riepilogo: informazioni su come eliminare i criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: 3fe5b8c2bb12f48cb6e904df2fe43c6c8a01e3f6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818597"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="45812-103">Eliminare i criteri di conferenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="45812-103">Delete conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="45812-104">**Riepilogo:** Informazioni su come eliminare i criteri di conferenza in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="45812-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="45812-105">Puoi eliminare i criteri di conferenza usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="45812-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="45812-106">Eliminare i criteri di conferenza tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="45812-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="45812-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="45812-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="45812-108">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="45812-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="45812-109">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="45812-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="45812-110">Nell'elenco dei criteri di conferenza fare clic sul sito o sui criteri utente da eliminare, fare clic su **modifica**e quindi su **Elimina**.</span><span class="sxs-lookup"><span data-stu-id="45812-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="45812-111">Eliminare i criteri di conferenza tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="45812-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="45812-112">Per eliminare i criteri di conferenza, usare il cmdlet **Remove-CsConferencingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="45812-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="45812-113">Il comando seguente rimuove i criteri di conferenza con Identity RedmondConferencingPolicy:</span><span class="sxs-lookup"><span data-stu-id="45812-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="45812-114">Il comando successivo Elimina i criteri di conferenza che consentono agli utenti esterni di registrare la conferenza:</span><span class="sxs-lookup"><span data-stu-id="45812-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="45812-115">Per altre informazioni, inclusa la sintassi completa e un elenco di parametri, vedere [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="45812-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
  

