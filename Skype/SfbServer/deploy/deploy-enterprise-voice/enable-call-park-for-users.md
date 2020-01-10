---
title: Abilitare il parcheggio delle chiamate per gli utenti in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Consentire agli utenti di Call Park in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: c3ad2bcf70c7b175ba372ba2834e56209de9f664
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002556"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a><span data-ttu-id="94ac0-103">Abilitare il parcheggio delle chiamate per gli utenti in Skype for business</span><span class="sxs-lookup"><span data-stu-id="94ac0-103">Enable Call Park for users in Skype for Business</span></span>
 
<span data-ttu-id="94ac0-104">Consentire agli utenti di Call Park in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="94ac0-104">Enable users for Call Park in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="94ac0-105">Per impostazione predefinita, il parcheggio delle chiamate è disabilitato per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="94ac0-105">By default, Call Park is disabled for all users.</span></span> <span data-ttu-id="94ac0-106">Gli utenti non possono parcheggiare chiamate o recuperare le chiamate parcheggiate finché non vengono abilitate per il parcheggio delle chiamate in criteri vocali.</span><span class="sxs-lookup"><span data-stu-id="94ac0-106">Users cannot park calls or retrieve parked calls until they are enabled for Call Park in voice policy.</span></span>
  
<span data-ttu-id="94ac0-107">È possibile abilitare il parcheggio di chiamata nell'ambito globale o nell'ambito del sito o nell'ambito dell'utente.</span><span class="sxs-lookup"><span data-stu-id="94ac0-107">You can enable Call Park at the global scope, or at the site scope or user scope.</span></span> <span data-ttu-id="94ac0-108">L'ambito utente ha la precedenza sull'ambito del sito e l'ambito del sito prevale sull'ambito globale.</span><span class="sxs-lookup"><span data-stu-id="94ac0-108">User scope takes precedence over site scope, and site scope takes precedence over global scope.</span></span> <span data-ttu-id="94ac0-109">Se si hanno più criteri vocali, rivedere tutti i criteri per abilitare il parcheggio delle chiamate e non solo i criteri globali.</span><span class="sxs-lookup"><span data-stu-id="94ac0-109">If you have multiple voice policies, review all the policies to enable Call Park, not just the global policy.</span></span>
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a><span data-ttu-id="94ac0-110">Per usare il pannello di controllo di Skype for Business Server per abilitare il parcheggio delle chiamate per gli utenti</span><span class="sxs-lookup"><span data-stu-id="94ac0-110">To Use Skype for Business Server Control Panel to Enable Call Park for Users</span></span>

1. <span data-ttu-id="94ac0-111">Accedere al computer come membro del gruppo **RTCUniversalServerAdmins** oppure come membro del ruolo di amministratore di **CsVoiceAdministrator**, **CsServerAdministrator**o **CsAdministrator** .</span><span class="sxs-lookup"><span data-stu-id="94ac0-111">Log on to the computer as a member of the **RTCUniversalServerAdmins** group, or as a member of the **CsVoiceAdministrator**, **CsServerAdministrator**, or **CsAdministrator** administrative role.</span></span>
    
2. <span data-ttu-id="94ac0-112">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="94ac0-112">Open Skype for Business Server Control Panel.</span></span>
    
3. <span data-ttu-id="94ac0-113">Sulla barra di spostamento sinistra fare clic su **routing vocale**.</span><span class="sxs-lookup"><span data-stu-id="94ac0-113">In the left navigation bar, click **Voice Routing**.</span></span>
    
4. <span data-ttu-id="94ac0-114">Fare clic sulla scheda **criteri vocali** .</span><span class="sxs-lookup"><span data-stu-id="94ac0-114">Click the **Voice Policy** tab.</span></span>
    
5. <span data-ttu-id="94ac0-115">Fare doppio clic su un criterio vocale esistente per aprire la finestra di dialogo **modifica criterio vocale** .</span><span class="sxs-lookup"><span data-stu-id="94ac0-115">Double-click an existing voice policy to open the **Edit Voice Policy** dialog box.</span></span>
    
6. <span data-ttu-id="94ac0-116">In **funzionalità di chiamata**selezionare **Abilita parcheggio chiamate**.</span><span class="sxs-lookup"><span data-stu-id="94ac0-116">Under **Calling features**, select **Enable call park**.</span></span>
    
7. <span data-ttu-id="94ac0-117">Fare clic su **OK** per salvare il criterio vocale</span><span class="sxs-lookup"><span data-stu-id="94ac0-117">Click **OK** to save the voice policy</span></span>
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a><span data-ttu-id="94ac0-118">Per usare i cmdlet per abilitare il parcheggio delle chiamate per gli utenti</span><span class="sxs-lookup"><span data-stu-id="94ac0-118">To Use Cmdlets to Enable Call Park for Users</span></span>

1. <span data-ttu-id="94ac0-119">Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo di amministratore di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.</span><span class="sxs-lookup"><span data-stu-id="94ac0-119">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator administrative role.</span></span>
    
2. <span data-ttu-id="94ac0-120">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="94ac0-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="94ac0-121">Eseguire</span><span class="sxs-lookup"><span data-stu-id="94ac0-121">Run:</span></span>
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    <span data-ttu-id="94ac0-122">Ad esempio, per abilitare Call Park per il criterio vocale globale predefinito:</span><span class="sxs-lookup"><span data-stu-id="94ac0-122">For example, to enable Call Park for the default global voice policy:</span></span>
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a><span data-ttu-id="94ac0-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94ac0-123">See also</span></span>



[<span data-ttu-id="94ac0-124">Creare o modificare un criterio vocale e configurare i record di utilizzo PSTN in Skype for business</span><span class="sxs-lookup"><span data-stu-id="94ac0-124">Create or modify a voice policy and configure PSTN usage records in Skype for Business</span></span>](voice-policy-and-pstn-usage-records.md)

