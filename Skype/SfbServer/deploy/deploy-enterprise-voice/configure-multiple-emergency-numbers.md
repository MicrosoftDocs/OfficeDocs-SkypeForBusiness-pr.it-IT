---
title: Configurare più numeri di emergenza in Skype for Business
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Leggere questo argomento per informazioni su come configurare più numeri di emergenza in Skype for Business Server.
ms.openlocfilehash: d79a57e64d52bfc6b0f1d8ee9a9bd9c3c1509658
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60833912"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Configurare più numeri di emergenza in Skype for Business

Leggere questo argomento per informazioni su come configurare più numeri di emergenza in Skype for Business Server.

Skype for Business Server ora supporta più numeri di emergenza per un client. Più numeri di emergenza è una nuova funzionalità introdotta nell'aggiornamento cumulativo di giugno 2016. Prima di configurare l'ambiente per supportare più numeri di emergenza, leggere Pianificare più numeri di emergenza [in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).

> [!NOTE]
> Se non è stato ancora eseguito l'aggiornamento all'aggiornamento cumulativo di novembre 2016, vedere [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). Con l'aggiornamento cumulativo di novembre 2016, il numero di numeri di emergenza di supporto aumenta da 5 a 100.

## <a name="configure-multiple-emergency-numbers"></a>Configurare più numeri di emergenza

Per configurare più numeri di emergenza, utilizzare il cmdlet New-CsEmergencyNumber e quindi specificare il parametro EmergencyNumbers con i cmdlet [New-CsLocationPolicy](/powershell/module/skype/new-cslocationpolicy?view=skype-ps) e [Set-CsLocationPolicy.](/powershell/module/skype/set-cslocationpolicy?view=skype-ps) Per una descrizione completa di tutti i parametri dei criteri percorso, ad esempio l'utilizzo PSTN e la posizione necessaria, [vedere Set-CsLocationPolicy.](/powershell/module/skype/set-cslocationpolicy?view=skype-ps)

Il comando seguente crea un nuovo numero di emergenza con la stringa di composizione 911 utilizzando il cmdlet New-CsEmergency:

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

Il comando successivo associa il numero al criterio percorso specificato specificando il parametro EmergencyNumbers nel cmdlet Set-CsLocationPolicy:

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

Nell'esempio seguente viene creato un numero di emergenza con una maschera di composizione singola, 112:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

Il comando successivo crea un numero di emergenza con più maschere di composizione:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

Nell'esempio seguente vengono aggiunti più numeri di emergenza con più maschere di composizione e quindi i numeri di emergenza vengono associati al criterio percorso specificato:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

L'esempio seguente configura più numeri di emergenza per i provider di servizi sanitari che utilizzano sia 911 che 450:

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

L'esempio seguente configura più numeri di emergenza per la città di Londra:

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

L'esempio seguente configura più numeri di emergenza per l'India:

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

Nell'esempio seguente viene rimossa una voce esistente con dial string 911 e dial mask 112 e 999:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```