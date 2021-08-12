---
title: Configurare le impostazioni del parcheggio di chiamata in Skype for Business
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
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Modificare le impostazioni del parcheggio di chiamata in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 09888fd0d22ce182688a2fbd0456ce7e5cc6564e1b33ebb1b957ebb0f23b02df
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54294903"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a>Configurare le impostazioni del parcheggio di chiamata in Skype for Business

Modificare le impostazioni del parcheggio di chiamata in Skype for Business Server VoIP aziendale.

Se non si desidera utilizzare le impostazioni predefinite del parcheggio di chiamata, è possibile personalizzarle. Quando si installa l'applicazione Parcheggio di chiamata, le impostazioni globali vengono configurate per impostazione predefinita. È possibile modificarle, nonché specificare impostazioni specifiche del sito. Usare il cmdlet **New-CsCpsConfiguration** per creare nuove impostazioni specifiche del sito. Usare il cmdlet **Set-CsCpsConfiguration** per modificare le impostazioni esistenti.

> [!NOTE]
> È consigliabile configurare come minimo l'opzione **OnTimeoutURI** per la destinazione di fallback da utilizzare quando si verifica il timeout di una chiamata parcheggiata e la richiamata ha esito negativo.

Usare il cmdlet **New-CsCpsConfiguration** o il cmdlet **Set-CsCpsConfiguration** per configurare una delle impostazioni seguenti:


| **Opzione:**                     | **Descrizione:**                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **CallPickupTimeoutThreshold** <br/> | Specifica quanto tempo deve trascorrere dopo che una chiamata è stata parcheggiata prima che squilli sul telefono da cui è stata effettuata la risposta.  <br/> Il valore deve essere immesso nel formato hh:mm:ss per specificare le ore, i minuti e i secondi. Il valore minimo è 10 secondi e il valore massimo è 10 minuti. Il valore predefinito è 00:01:30.  <br/> |
| **EnableMusicOnHold** <br/>          | Specifica se viene riprodotto un brano musicale per il chiamante mentre una chiamata è parcheggiata.  <br/> I valori consentiti sono True o False. Il valore predefinito è True.  <br/>                                                                                                                                                                                                                 |
| **MaxCallPickupAttempts** <br/>      | Specifica per una chiamata parcheggiata il numero di squilli sul telefono da cui è stata effettuata la risposta prima che la chiamata venga inoltrata all'URI (Uniform Resource Identifier) di fallback indicato per **OnTimeoutURI**. Il valore predefinito è 1.<br/>                                                                                                                         |
| **OnTimeoutURI** <br/>               | Specifica l'indirizzo SIP dell'utente o del Response Group a cui viene instradata una chiamata parcheggiata senza risposta quando viene superato il valore specificato per **MaxCallPickupAttempts**. <br/> Il valore deve essere un URI SIP che inizia con la stringa sip:, ad esempio sip:bob@contoso.com. Per impostazione predefinita, non viene specificato un indirizzo di inoltro.<br/>                                                   |

### <a name="to-configure-call-park-settings"></a>Per configurare le impostazioni del parcheggio di chiamata

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi fare clic su **Skype for Business Server Management Shell.**

2. Eseguire: 

   ```powershell
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > Utilizzare il cmdlet **Get-CsSite** per identificare il sito. Per informazioni dettagliate, vedere Skype for Business Server Management Shell.

    Ad esempio:

   ```powershell
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>Vedere anche

[Personalizzare la musica del parcheggio di chiamata in attesa inSkype for Business 2015](customize-call-park-music-on-hold.md)

[New-CsCpsConfiguration](/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[Set-CsCpsConfiguration](/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[Get-CsSite](/powershell/module/skype/get-cssite?view=skype-ps)