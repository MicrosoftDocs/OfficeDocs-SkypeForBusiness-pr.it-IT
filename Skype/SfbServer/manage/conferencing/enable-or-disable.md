---
title: Abilitare o disabilitare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1f7cf91-8434-42ec-b09d-7d9d01e0b357
description: 'Riepilogo: informazioni su come usare il pannello di controllo o la shell di gestione per abilitare o disabilitare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: 6723c3501b226d11977ad176a804210540f1a2bc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194524"
---
# <a name="enable-or-disable-dial-in-conferencing-in-skype-for-business-server"></a><span data-ttu-id="5be74-103">Abilitare o disabilitare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5be74-103">Enable or disable dial-in conferencing in Skype for Business Server</span></span>
 
<span data-ttu-id="5be74-104">**Riepilogo:** Informazioni su come usare il pannello di controllo o Management Shell per abilitare o disabilitare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5be74-104">**Summary:** Learn how to use Control Panel or Management Shell to enable or disable dial-in conferencing in Skype for Business Server.</span></span>
  
<span data-ttu-id="5be74-105">Puoi abilitare i servizi di conferenza telefonica con accesso esterno usando il pannello di controllo di Skype for Business Server o usando Skype for Business Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="5be74-105">You can enable dial-in conferencing by using Skype for Business Server Control Panel or by using Skype for Business Server Management Shell.</span></span>
  
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="5be74-106">Abilitare o disabilitare i servizi di conferenza telefonica con accesso esterno tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="5be74-106">Enable or disable dial-in conferencing by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="5be74-107">Da un account utente assegnato al ruolo CsUserAdministrator o CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="5be74-107">From a user account that is assigned to the CsUserAdministrator role or the CsAdministrator role, log on to any computer in your internal deployment.</span></span>
    
2.  <span data-ttu-id="5be74-108">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5be74-108">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="5be74-109">Sulla barra di spostamento sinistra fare clic su servizi di **conferenza**e quindi su **criteri di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="5be74-109">In the left navigation bar, click **Conferencing**, and then click **Conferencing Policy**.</span></span>
    
4. <span data-ttu-id="5be74-110">Nell'elenco dei criteri di conferenza selezionare i criteri per cui si desidera abilitare i servizi di conferenza telefonica con accesso esterno, fare clic su **modifica**e quindi su **Mostra dettagli**.</span><span class="sxs-lookup"><span data-stu-id="5be74-110">In the list of conferencing policies, select the policy for which you want to enable dial-in conferencing, click **Edit**, and then click **Show details**.</span></span> 
    
5. <span data-ttu-id="5be74-111">Per consentire agli utenti di partecipare a una riunione effettuando la chiamata, selezionare la casella di controllo **Abilita conferenza telefonica con accesso esterno PSTN** .</span><span class="sxs-lookup"><span data-stu-id="5be74-111">To allow users to join meeting by dialing in, check the **Enable PSTN dial-in conferencing** check box.</span></span> <span data-ttu-id="5be74-112">Per impostazione predefinita, gli utenti possono eseguire la chiamata alle riunioni tramite la rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="5be74-112">By default, users can dial in to meetings by using the public switched telephone network (PSTN).</span></span>
    
6. <span data-ttu-id="5be74-113">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="5be74-113">Click **Commit**.</span></span> 
    
## <a name="enable-or-disable-dial-in-conferencing-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="5be74-114">Abilitare o disabilitare i servizi di conferenza telefonica con accesso esterno usando Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="5be74-114">Enable or disable dial-in conferencing by using Skype for Business Server Management Shell</span></span>

<span data-ttu-id="5be74-115">Per abilitare o disabilitare i servizi di conferenza telefonica con accesso esterno, usare il cmdlet **Set-CsConferencingPolicy** con il parametro EnableDialInConferencing come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5be74-115">To enable or disable dial-in conferencing, use the **Set-CsConferencingPolicy** cmdlet with the EnableDialInConferencing parameter as follows:</span></span>
  
```
Set-CsConferencingPolicy  [-EnableDialInConferencing <$true | $false>] 
```

<span data-ttu-id="5be74-116">Per altre informazioni, vedere [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="5be74-116">For more information, see [Set-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csconferencingpolicy?view=skype-ps).</span></span>
  

