---
title: Abilitare parcheggio di chiamata per gli utenti in Skype for Business
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 9430763f-3394-467c-9c6d-426bf761604e
description: Abilitare gli utenti per parcheggio di chiamata in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 87ac29c8f9b6c893149db8fb91561ee4b3cf1166
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843509"
---
# <a name="enable-call-park-for-users-in-skype-for-business"></a>Abilitare parcheggio di chiamata per gli utenti in Skype for Business
 
Abilitare gli utenti per parcheggio di chiamata in Skype for Business Server VoIP aziendale.
  
Per impostazione predefinita, parcheggio di chiamata è disabilitato per tutti gli utenti. Gli utenti non possono parcheggiare le chiamate o recuperare le chiamate parcheggiate finché non vengono abilitate per parcheggio di chiamata nei criteri vocali.
  
È possibile abilitare parcheggio di chiamata nell'ambito globale o nell'ambito del sito o dell'utente. L'ambito utente ha la precedenza rispetto all'ambito a livello di sito, che a sua volta ha la precedenza rispetto all'ambito globale. Se si dispone di più criteri vocali, esaminare tutti i criteri per abilitare parcheggio di chiamata, non solo il criterio globale.
  
### <a name="to-use-skype-for-business-server-control-panel-to-enable-call-park-for-users"></a>Per utilizzare Skype for Business Server pannello di controllo per abilitare il parcheggio di chiamata per gli utenti

1. Accedere al computer come membro del gruppo **RTCUniversalServerAdmins** o come membro del ruolo amministrativo **CsVoiceAdministrator**, **CsServerAdministrator** o **CsAdministrator**.
    
2. Aprire Skype for Business Server Pannello di controllo.
    
3. Sulla barra di spostamento sinistra fare clic su **Routing vocale**.
    
4. Fare clic sulla scheda **Criteri vocali**.
    
5. Fare doppio clic su un criterio esistente per aprire la finestra di dialogo **Modifica criterio vocale**.
    
6. In **Funzionalità di chiamata** selezionare **Abilita parcheggio di chiamata**.
    
7. Fare clic su **OK** per salvare il criterio vocale.
    
### <a name="to-use-cmdlets-to-enable-call-park-for-users"></a>Per utilizzare i cmdlet per abilitare il parcheggio di chiamata per gli utenti

1. Accedere al computer come membro del gruppo RTCUniversalServerAdmins oppure come membro del ruolo amministrativo CsVoiceAdministrator, CsServerAdministrator o CsAdministrator.
    
2. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**
    
3. Eseguire: 
    
   ```powershell
   Set-CsVoicePolicy -Identity <VoicePolicy> -EnableCallPark $true
   ```

    Ad esempio, per abilitare parcheggio di chiamata per il criterio vocale globale predefinito:
    
   ```powershell
   Set-CsVoicePolicy -EnableCallPark $true
   ```

## <a name="see-also"></a>Vedere anche



[Creare o modificare un criterio vocale e configurare i record di utilizzo PSTN in Skype for Business](voice-policy-and-pstn-usage-records.md)

