---
title: Abilitare il parcheggio di chiamata per gli utenti in Skype for business
ms.reviewer: ''
ms.author: v-cichur
author: cichur
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
description: Abilitare gli utenti per il parcheggio di chiamata in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: e9bbc42f5940af0cfc94ab83eae981dd023c9fcd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830956"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Abilitare il parcheggio di chiamata per gli utenti in Skype for business
 
Abilitare gli utenti per il parcheggio di chiamata in Skype for Business Server VoIP aziendale.
  
Per impostazione predefinita, il parcheggio di chiamata è disabilitato per tutti gli utenti. Gli utenti non possono parcheggiare le chiamate o recuperare le chiamate parcheggiate finché non sono abilitate per il parcheggio di chiamata nel criterio vocale.
  
È possibile abilitare il parcheggio di chiamata nell'ambito globale o nell'ambito del sito o nell'ambito dell'utente. L'ambito utente ha la precedenza rispetto all'ambito a livello di sito, che a sua volta ha la precedenza rispetto all'ambito globale. Se si dispone di più criteri vocali, esaminare tutti i criteri per abilitare il parcheggio di chiamata, non solo il criterio globale.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>Per utilizzare il pannello di controllo di Skype for Business Server per abilitare il parcheggio di chiamata per gli utenti

1. Accedere al computer come membro del gruppo **RTCUniversalServerAdmins** o come membro del ruolo amministrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Aprire il pannello di controllo di Skype for Business Server.
    
3. Sulla barra di spostamento sinistra fare clic su **Routing vocale**.
    
4. Fare clic sulla scheda **Criteri vocali**.
    
5. Fare doppio clic su un criterio esistente per aprire la finestra di dialogo **Modifica criterio vocale**.
    
6. In **Funzionalità di chiamata** selezionare **Abilita parcheggio di chiamata**.
    
7. Fare clic su **OK** per salvare il criterio vocale.
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Per utilizzare i cmdlet per abilitare il parcheggio di chiamata per gli utenti

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo amministrativo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.
    
3. Eseguire: 
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    Ad esempio, per abilitare il parcheggio di chiamata per il criterio vocale globale predefinito:
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>Vedere anche



[Creare o modificare criteri vocali e configurare i record di utilizzo PSTN in Skype for business](voice-policy-and-pstn-usage-records.md)

