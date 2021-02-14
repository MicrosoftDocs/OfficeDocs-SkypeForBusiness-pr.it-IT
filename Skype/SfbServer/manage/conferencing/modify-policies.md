---
title: Modificare i criteri di conferenza in Skype for Business Server
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
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Riepilogo: informazioni su come modificare i criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: eafeb56dd9b0c36afffab07830a9efb71bde18fe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828006"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="a12de-103">Modificare i criteri di conferenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a12de-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="a12de-104">**Riepilogo:** Informazioni su come modificare i criteri di conferenza in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a12de-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="a12de-105">È possibile modificare i criteri di conferenza utilizzando il Pannello di controllo di Skype for Business Server o Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="a12de-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="a12de-106">Modificare i criteri di conferenza utilizzando il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="a12de-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="a12de-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="a12de-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="a12de-108">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a12de-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="a12de-109">Sulla barra di spostamento sinistra fare clic su Servizio **di** conferenza e quindi su **Criteri conferenza.**</span><span class="sxs-lookup"><span data-stu-id="a12de-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="a12de-110">Nell'elenco dei criteri per conferenza fare clic sui criteri che si desidera modificare, fare clic su **Modifica** e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="a12de-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="a12de-111">In **Modifica criteri conferenza** modificare qualsiasi impostazione dei criteri ad eccezione del nome, che non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="a12de-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="a12de-112">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="a12de-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="a12de-113">Modificare i criteri di conferenza tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="a12de-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="a12de-114">Per modificare i criteri di conferenza, utilizzare il cmdlet **Set-CsConferencingPolicy.**</span><span class="sxs-lookup"><span data-stu-id="a12de-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="a12de-115">Nell'esempio seguente viene modificato un valore di proprietà del criterio di conferenza SalesConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="a12de-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="a12de-116">Il comando imposta il valore della proprietà AllowConferenceRecording su False:</span><span class="sxs-lookup"><span data-stu-id="a12de-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="a12de-117">Per ulteriori informazioni, inclusa la sintassi completa e un elenco di parametri, [vedere Set-CsConferencingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="a12de-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

