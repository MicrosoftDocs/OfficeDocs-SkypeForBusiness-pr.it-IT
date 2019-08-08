---
title: Configurare le impostazioni di Call Park in Skype for business
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
ms.assetid: 3bed9d09-8363-4fff-a220-f0f6d3a81241
description: Modificare le impostazioni di Call Park in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: df7334734784a773abd1df66a7544c3141a9aec9
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233939"
---
# <a name="configure-call-park-settings-in-skype-for-business"></a>Configurare le impostazioni di Call Park in Skype for business

Modificare le impostazioni di Call Park in Skype for Business Server VoIP aziendale.

Se non si vogliono usare le impostazioni predefinite di Call Park, è possibile personalizzarle. Quando si installa l'applicazione Call Park, le impostazioni globali sono configurate per impostazione predefinita. È possibile modificare le impostazioni globali ed è anche possibile specificare impostazioni specifiche del sito. Usa il cmdlet **New-CsCpsConfiguration** per creare nuove impostazioni specifiche del sito. Usare il cmdlet **Set-CsCpsConfiguration** per modificare le impostazioni esistenti.

> [!NOTE]
> È consigliabile configurare almeno l'opzione **OnTimeoutURI** per la destinazione di fallback da usare quando si verifica un timeout per una chiamata parcheggiata e la risponderia non riesce.

USA cmdlet **New-CsCpsConfiguration** o il cmdlet **Set-CsCpsConfiguration** per configurare una delle impostazioni seguenti:


| **Questa opzione:**                     | **Specifica questo:**                                                                                                                                                                                                                                                                                                                   |
|:-------------------------------------|:--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **CallPickupTimeoutThreshold** <br/> | La quantità di tempo che trascorre dopo il parcheggio di una chiamata prima che ritorni al telefono in cui è stata risolta la chiamata.  <br/> Il valore deve essere immesso nel formato HH: mm: SS per specificare le ore, i minuti e i secondi. Il valore minimo è di 10 secondi e il valore massimo è di 10 minuti. Il valore predefinito è 00:01:30.  <br/> |
| **EnableMusicOnHold** <br/>          | Se la musica viene riprodotta per un chiamante mentre viene parcheggiata una chiamata.  <br/> I valori sono true o false. Il valore predefinito è true.  <br/>                                                                                                                                                                                                                 |
| **MaxCallPickupAttempts** <br/>      | Il numero di squilli di una chiamata parcheggiata torna al telefono che risponde prima che venga inoltrato all'URI (Uniform Resource Identifier) di fallback specificato per **OnTimeoutURI**. Il valore predefinito è 1.  <br/>                                                                                                                         |
| **OnTimeoutURI** <br/>               | Indirizzo SIP dell'utente o del gruppo di risposte a cui viene instradata una chiamata parcheggiata senza risposta quando viene superato **MaxCallPickupAttempts** . <br/> Value deve essere un URI SIP che inizia con la stringa SIP:. Ad esempio, sip:bob@contoso.com. L'impostazione predefinita non è l'indirizzo di inoltro.  <br/>                                                   |

### <a name="to-configure-call-park-settings"></a>Per configurare le impostazioni di Call Park

1. Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.

2. Eseguire

   ```
   New-CsCpsConfiguration -Identity site:<sitename to apply settings> [-CallPickupTimeoutThreshold <hh:mm:ss>] -[EnableMusicOnHold <$true | $false>] [-MaxCallPickupAttempts <number of rings>] [-OnTimeoutURI sip:<sip URI for routing unanswered call>]
   ```

   > [!TIP]
   > Usa il cmdlet **Get-CsSite** per identificare il sito. Per informazioni dettagliate, vedi documentazione di Skype for Business Server Management Shell.

    Ad esempio:

   ```
   New-CsCpsConfiguration -Identity site:Redmond1 -CallPickupTimeoutThreshold 00:01:00 -EnableMusicOnHold $false -MaxCallPickupAttempts 2 -OnTimeoutURI sip:bob@contoso.com
   ```

## <a name="see-also"></a>Vedere anche

[Personalizzare la musica di Call Park in attesa in Skype for business 2015](customize-call-park-music-on-hold.md)

[New-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/new-cscpsconfiguration?view=skype-ps)

[Set-CsCpsConfiguration](https://docs.microsoft.com/powershell/module/skype/set-cscpsconfiguration?view=skype-ps)

[Get-CsSite](https://docs.microsoft.com/powershell/module/skype/get-cssite?view=skype-ps)
