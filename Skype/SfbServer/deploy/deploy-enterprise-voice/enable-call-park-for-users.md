---
title: Abilitare il parcheggio delle chiamate per gli utenti in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Consentire agli utenti di Call Park in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 6642af2a7af698a1127ff2a9bb4e45df73d18c50
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767279"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Abilitare il parcheggio delle chiamate per gli utenti in Skype for business
 
Consentire agli utenti di Call Park in Skype for Business Server VoIP aziendale.
  
Per impostazione predefinita, il parcheggio delle chiamate è disabilitato per tutti gli utenti. Gli utenti non possono parcheggiare chiamate o recuperare le chiamate parcheggiate finché non vengono abilitate per il parcheggio delle chiamate in criteri vocali.
  
È possibile abilitare il parcheggio di chiamata nell'ambito globale o nell'ambito del sito o nell'ambito dell'utente. L'ambito utente ha la precedenza sull'ambito del sito e l'ambito del sito prevale sull'ambito globale. Se si hanno più criteri vocali, rivedere tutti i criteri per abilitare il parcheggio delle chiamate e non solo i criteri globali.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>Per usare il pannello di controllo di Skype for Business Server per abilitare il parcheggio delle chiamate per gli utenti

1. Accedere al computer come membro del gruppo **RTCUniversalServerAdmins** oppure come membro del ruolo di amministratore di **CsVoiceAdministrator**, **CsServerAdministrator**o **CsAdministrator** .
    
2. Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **routing vocale**.
    
4. Fare clic sulla scheda **criteri vocali** .
    
5. Fare doppio clic su un criterio vocale esistente per aprire la finestra di dialogo **modifica criterio vocale** .
    
6. In **funzionalità di chiamata**selezionare **Abilita parcheggio chiamate**.
    
7. Fare clic su **OK** per salvare il criterio vocale
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Per usare i cmdlet per abilitare il parcheggio delle chiamate per gli utenti

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo di amministratore di CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.
    
3. Eseguire
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    Ad esempio, per abilitare Call Park per il criterio vocale globale predefinito:
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>Vedere anche



[Creare o modificare un criterio vocale e configurare i record di utilizzo PSTN in Skype for business](voice-policy-and-pstn-usage-records.md)

