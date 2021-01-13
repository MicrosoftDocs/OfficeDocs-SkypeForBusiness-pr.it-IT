---
title: Abilitare o disabilitare le conferenze telefoniche con accesso esterno in Skype for Business Server
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
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Riepilogo: informazioni su come utilizzare il pannello di controllo o la shell di gestione per abilitare o disabilitare le conferenze telefoniche con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: 99691540306ba0cccf9c63af2e2188e839367bc6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49828126"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="f08cd-103">Abilitare o disabilitare le conferenze telefoniche con accesso esterno in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f08cd-103">Enable or disable dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="f08cd-104">**Riepilogo:** Informazioni su come utilizzare il pannello di controllo o la shell di gestione per abilitare o disabilitare le conferenze telefoniche con accesso esterno in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f08cd-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="f08cd-105">È possibile abilitare le conferenze telefoniche con accesso esterno tramite il pannello di controllo di Skype for Business Server o tramite Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="f08cd-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f08cd-106">Abilitare o disabilitare le conferenze telefoniche con accesso esterno tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f08cd-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f08cd-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="f08cd-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="f08cd-108">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="f08cd-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="f08cd-109">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza** e quindi su **criteri conferenza**.</span><span class="sxs-lookup"><span data-stu-id="f08cd-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="f08cd-110">Nell'elenco dei criteri conferenza selezionare il criterio per il quale abilitare il servizio di conferenza con accesso esterno e quindi fare clic su **Modifica** e su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="f08cd-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="f08cd-p101">Per consentire agli utenti la partecipazione a una riunione mediante accesso esterno, selezionare la casella di controllo **Consenti conferenza telefonica con accesso esterno PSTN**. Per impostazione predefinita, gli utenti possono connettersi alle riunioni utilizzando la rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="f08cd-p101">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box. By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="f08cd-113">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="f08cd-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f08cd-114">Abilitare o disabilitare le conferenze telefoniche con accesso esterno tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="f08cd-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="f08cd-115">Per abilitare o disabilitare le conferenze telefoniche con accesso esterno, utilizzare il cmdlet **Set-CsConferencingPolicy** con il parametro EnableDialInConferencing, come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="f08cd-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```PowerShell
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="f08cd-116">Per ulteriori informazioni, vedere [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="f08cd-116">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

