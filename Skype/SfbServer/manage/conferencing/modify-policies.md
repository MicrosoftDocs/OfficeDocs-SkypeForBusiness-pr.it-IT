---
title: Modificare i criteri di conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b40ba905-e74a-4456-ac94-65471bc2d66d
description: 'Riepilogo: informazioni su come modificare i criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: 9cfb13436a01439a8d5ea152ca1d8ac543bc0e88
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991811"
---
# <a name="modify-conferencing-policies-in-skype-for-business-server"></a><span data-ttu-id="ca801-103">Modificare i criteri di conferenza in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ca801-103">Modify conferencing policies in Skype for Business Server</span></span>
 
<span data-ttu-id="ca801-104">**Riepilogo:** Informazioni su come modificare i criteri di conferenza in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ca801-104">**Summary:** Learn how to modify conferencing policies in Skype for Business Server.</span></span>
  
<span data-ttu-id="ca801-105">Puoi modificare i criteri di conferenza usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="ca801-105">You can modify conferencing policies by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ca801-106">Modificare i criteri di conferenza tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ca801-106">Modify conferencing policies by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ca801-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="ca801-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="ca801-108">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ca801-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="ca801-109">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="ca801-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="ca801-110">Nell'elenco dei criteri di conferenza fare clic sul criterio che si vuole modificare, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="ca801-110">In the list of conferencing policies, click the policy that you want to change, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="ca801-111">In **modifica criteri di conferenza**modificare le impostazioni dei criteri, ad eccezione del nome del criterio, che non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="ca801-111">In **Edit Conferencing Policy**, modify any of the policy settings, except for the policy name, which cannot be modified.</span></span>
    
6. <span data-ttu-id="ca801-112">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="ca801-112">Click **Commit**.</span></span>
    
## <a name="modify-conferencing-policies-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ca801-113">Modificare i criteri di conferenza tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="ca801-113">Modify conferencing policies by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="ca801-114">Per modificare i criteri di conferenza, usare il cmdlet **Set-CsConferencingPolicy** .</span><span class="sxs-lookup"><span data-stu-id="ca801-114">To modify conferencing policies, use the **Set-CsConferencingPolicy** cmdlet.</span></span>
  
<span data-ttu-id="ca801-115">Nell'esempio seguente viene modificato il valore di una proprietà del criterio di conferenza SalesConferencingPolicy.</span><span class="sxs-lookup"><span data-stu-id="ca801-115">The following example modifies a property value of the conferencing policy SalesConferencingPolicy.</span></span> <span data-ttu-id="ca801-116">Il comando imposta il valore della proprietà AllowConferenceRecording su false:</span><span class="sxs-lookup"><span data-stu-id="ca801-116">The command sets the value of the AllowConferenceRecording property to False:</span></span>
  
```PowerShell
Set-CsConferencingPolicy -Identity SalesConferencingPolicy -AllowConferenceRecording $False
```

<span data-ttu-id="ca801-117">Per altre informazioni, inclusa la sintassi completa e un elenco di parametri, vedere [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="ca801-117">For more information, including complete syntax and a list of parameters, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

