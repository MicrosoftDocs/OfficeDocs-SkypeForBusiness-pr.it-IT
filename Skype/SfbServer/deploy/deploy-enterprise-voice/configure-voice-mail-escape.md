---
title: Configurare l'escape della segreteria telefonica in Skype for business
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
ms.assetid: a1d19e6c-82ff-4768-8ae5-da981368ce40
description: 'Riepilogo: informazioni su come configurare la modalità di escape della segreteria telefonica in Skype for Business Server tramite Skype for Business Server Management Shell.'
ms.openlocfilehash: c9a858ead9261944c162cb10fda63840f8de86d3
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233792"
---
# <a name="configure-voice-mail-escape-in-skype-for-business"></a>Configurare l'escape della segreteria telefonica in Skype for business

**Riepilogo:** Informazioni su come configurare la modalità di escape della segreteria telefonica in Skype for Business Server tramite Skype for Business Server Management Shell.

Quando un utente configura lo squillo simultaneo su un telefono cellulare, il chiamante viene in genere instradato alla segreteria telefonica personale dell'utente se il telefono cellulare è disattivato, non è più alimentato dalla batteria o fuori portata. Con Skype for Business Server, gli utenti possono scegliere di avere chiamate correlate alle aziende instradate al sistema di segreteria telefonica aziendale. In particolare, è possibile configurare un timer e, se la chiamata viene risolta dalla segreteria telefonica del vettore entro l'intervallo di tempo definito, Skype for Business Server si disconnette dal sistema di segreteria telefonica del gestore (e dalla segreteria telefonica personale dell'utente), mentre l'utente gli endpoint rimanenti nel sistema aziendale continuano a squillare. In questo modo, il chiamante viene indirizzato automaticamente alla segreteria telefonica aziendale dell'utente.

Questa configurazione viene eseguita usando il cmdlet di Skype for Business Server Management Shell, **Set-CsVoicePolicy**, a livello di criteri vocali, con i parametri seguenti.

### <a name="to-configure-voice-mail-escape"></a>Per configurare l'escape della segreteria telefonica

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

2. Specificare i parametri seguenti per **Set-CsVoicePolicy**:

   - **EnableVoicemailEscapeTimer** -Abilita o Disabilita il timer di escape.

   - **PSTNVoicemailEscapeTimer** -specifica il valore di timeout in millisecondi. Il valore predefinito è 1500 millisecondi e il valore può variare da 0 millisecondi a 8000 millisecondi.

## <a name="example"></a>Esempio

```
Set-CsVoicePolicy UserVoicePolicy -EnableVoiceMailEscapeTimer $true - PSTNVoicemailEscapeTimer 2000
Set-CsVoicePolicy -Identity site:SitePolicy -EnableVoiceMailEscapeTimer $true -PSTNVoicemailEscapeTimer 1500
```

## <a name="see-also"></a>Vedere anche

[Configurazione dei criteri vocali e dei record di utilizzo PSTN per autorizzare le funzionalità e i privilegi di chiamata](https://technet.microsoft.com/library/63f22010-a3d7-4cbd-86e8-6fc0e13c2b84.aspx)

