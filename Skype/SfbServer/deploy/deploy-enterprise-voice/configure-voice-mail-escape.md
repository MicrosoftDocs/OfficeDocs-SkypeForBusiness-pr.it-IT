---
title: Configurare l'escape della posta vocale in Skype for business
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
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Riepilogo: informazioni su come configurare la fuga di messaggi vocali in Skype for Business Server tramite Skype for Business Server Management Shell.'
ms.openlocfilehash: c6326360a0e49715feb7e9f9c3c123ec42b9c330
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824926"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Configurare l'escape della posta vocale in Skype for business

**Riepilogo:** Informazioni su come configurare la fuga di messaggi vocali in Skype for Business Server tramite Skype for Business Server Management Shell.

Quando un utente configura lo squillo simultaneo su un telefono cellulare, il chiamante viene in genere instradato alla segreteria telefonica personale dell'utente se il telefono cellulare è disattivato, fuori dalla batteria o fuori portata. Con Skype for Business Server, gli utenti possono scegliere di fare in modo che le chiamate relative alle aziende vengano instradate al sistema di segreteria telefonica aziendale. In particolare, è possibile configurare un timer e, se la chiamata risponde alla segreteria telefonica entro l'intervallo di tempo definito, Skype for Business Server si disconnette dal sistema di segreteria telefonica del gestore (e dalla segreteria telefonica personale dell'utente), mentre gli endpoint restanti dell'utente nel sistema aziendale continuano a squillare. In questo modo, il chiamante viene instradato automaticamente alla segreteria telefonica aziendale dell'utente.

Questa configurazione viene eseguita utilizzando il cmdlet di Skype for Business Server Management Shell, **Set-CsVoicePolicy**, a livello di criteri vocali, con i parametri seguenti.

### <a name="to-configure-voice-mail-escape"></a>Per configurare l'escape per la posta vocale

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015** e quindi su **Skype for Business Server Management Shell**.

2. Specificare i parametri seguenti per **Set-CsVoicePolicy**:

   - **EnableVoicemailEscapeTimer** - Consente di abilitare o disabilitare il timer di escape.

   - **PSTNVoicemailEscapeTimer** - Consente di specificare il valore di timeout in millisecondi. Il valore predefinito è 1500 millisecondi e i valori consentiti sono compresi tra 0 e 8000 millisecondi.

## <a name="example"></a>Esempio

```powershell
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>Vedere anche

[Configurazione di criteri vocali e i record utilizzo PSTN per autorizzare privilegi e caratteristiche di chiamata](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

