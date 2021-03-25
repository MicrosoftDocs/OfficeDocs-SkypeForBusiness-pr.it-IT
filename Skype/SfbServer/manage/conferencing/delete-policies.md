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
ms.openlocfilehash: 9aadaf82aea7f057cf1969f06d4257992b64a86a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119505"
---
# <a name="delete-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="65244-103">Eliminare i criteri conferenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="65244-103">Delete conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="65244-104">**Riepilogo:** Informazioni su come eliminare i criteri di conferenza in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="65244-104">**Summary:** Learn how to delete conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="65244-105">È possibile eliminare i criteri di conferenza utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="65244-105">You can delete conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="65244-106">Eliminare i criteri conferenza tramite il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="65244-106">Delete conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="65244-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="65244-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="65244-108">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="65244-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="65244-109">Sulla barra di spostamento sinistra fare clic su **Conferenza** e quindi su **Criteri conferenza.**</span><span class="sxs-lookup"><span data-stu-id="65244-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="65244-110">Nell'elenco dei criteri conferenza fare clic sul sito o sui criteri utente che si desidera eliminare, fare clic su **Modifica** e quindi su **Elimina.**</span><span class="sxs-lookup"><span data-stu-id="65244-110">In the list of conferencing policies, click the site or user policy that you want to delete, click **Edit**, and then click **Delete**.</span></span>
    
## <a name="delete-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="65244-111">Eliminare i criteri conferenza tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="65244-111">Delete conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="65244-112">Per eliminare i criteri conferenza, utilizzare il cmdlet **Remove-CsConferencingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="65244-112">To delete conferencing policies, use the **Remove-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="65244-113">Il comando seguente rimuove il criterio di conferenza con identità (Identity) RedmondConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="65244-113">The following command removes the conferencing policy with the Identity RedmondConferencingPolicy:</span></span>
  
```PowerShell
Remove-CsConferencingPolicy -Identity "RedmondConferencingPolicy"
```

<span data-ttu-id="65244-114">Il comando successivo elimina tutti i criteri di conferenza che consentono agli utenti esterni di registrare la conferenza:</span><span class="sxs-lookup"><span data-stu-id="65244-114">The next command deletes any conferencing policies that allow external users to record the conference:</span></span>
  
```PowerShell
Get-CsConferencingPolicy | Where-Object {$_.AllowExternalUsersToRecordMeetings -eq $True} | Remove-CsConferencingPolicy
```

<span data-ttu-id="65244-115">Per ulteriori informazioni, inclusa la sintassi completa e un elenco di parametri, [vedere Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="65244-115">For more information, including complete syntax and a list of parameters, see [Remove-CsConferencingPolicy](/powershell/module/skype/remove-csconferencingpolicy?view=skype-ps).</span></span>
