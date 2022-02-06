---
title: Configurare l'escape della segreteria telefonica in Skype for Business
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
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
ms.custom: null
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Riepilogo: informazioni su come configurare l''escape della casella vocale Skype for Business Server tramite Skype for Business Server Management Shell.'
---

# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Configurare l'escape della segreteria telefonica in Skype for Business

**Riepilogo:** Informazioni su come configurare l'escape della segreteria telefonica Skype for Business Server tramite Skype for Business Server Management Shell.

Quando un utente configura lo squillo simultaneo a un telefono cellulare, un chiamante viene in genere instradato alla segreteria telefonica personale dell'utente se il telefono cellulare è spento, fuori batteria o fuori portata. Con Skype for Business Server , gli utenti possono scegliere di instradare le chiamate correlate all'azienda al sistema di caselle vocali aziendale. In particolare, è possibile configurare un timer e se la segreteria telefonica dell'operatore risponde alla chiamata entro l'intervallo di tempo definito, Skype for Business Server si disconnette dal sistema di caselle vocali dell'operatore (e dalla segreteria telefonica personale dell'utente), mentre gli endpoint rimanenti dell'utente nel sistema aziendale continuano a squillare. In questo modo, il chiamante viene automaticamente instradato alla segreteria telefonica aziendale dell'utente.

Questa configurazione viene eseguita utilizzando il cmdlet Skype for Business Server Management Shell **, Set-CsVoicePolicy**, a livello di criteri vocali, con i parametri seguenti.

### <a name="to-configure-voice-mail-escape"></a>Per configurare l'escape del sistema di caselle vocali

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start****, scegliere** Tutti i programmi, **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell**.

2. Specificare i parametri seguenti per **Set-CsVoicePolicy**:

   - **EnableVoicemailEscapeTimer** - Consente di abilitare o disabilitare il timer di escape.

   - **PSTNVoicemailEscapeTimer** - Consente di specificare il valore di timeout in millisecondi. Il valore predefinito è 1500 millisecondi e i valori consentiti sono compresi tra 0 e 8000 millisecondi.

## <a name="example"></a>Esempio

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>Vedere anche

[Configurazione di criteri vocali e i record utilizzo PSTN per autorizzare privilegi e caratteristiche di chiamata](/previous-versions/office/lync-server-2013/lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges)