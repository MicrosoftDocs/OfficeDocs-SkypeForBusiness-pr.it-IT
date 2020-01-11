---
title: Configurare più numeri di emergenza in Skype for business
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Leggere questo argomento per informazioni su come configurare più numeri di emergenza in Skype for Business Server.
ms.openlocfilehash: a0a16536799024085afcce07d6a2a9a0e4c899e1
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41001316"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Configurare più numeri di emergenza in Skype for business

Leggere questo argomento per informazioni su come configurare più numeri di emergenza in Skype for Business Server.

Skype for Business Server ora supporta più numeri di emergenza per un client. Più numeri di emergenza è una nuova funzionalità introdotta nell'aggiornamento cumulativo di giugno 2016. Prima di configurare l'ambiente in modo da supportare più numeri di emergenza, leggere [piano per più numeri di emergenza in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).

> [!NOTE]
> Se l'aggiornamento cumulativo di novembre 2016 non è stato ancora aggiornato, vedere [aggiornamenti di Skype for Business Server 2015](https://support.microsoft.com/en-us/help/3061064/updates-for-skype-for-business-server-2015). Con l'aggiornamento cumulativo di novembre 2016, il numero di numeri di emergenza del supporto aumenta da 5 a 100. 

## <a name="configure-multiple-emergency-numbers"></a>Configurare numeri di emergenza multipli

Per configurare più numeri di emergenza, usare il cmdlet New-CsEmergencyNumber e quindi specificare il parametro EmergencyNumbers con i cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) e [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) . Per una descrizione completa di tutti i parametri dei criteri di posizione, ad esempio l'utilizzo e la posizione PSTN necessari, vedere [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).

Il comando seguente crea un nuovo numero di emergenza con Dial String 911 usando il cmdlet New-CsEmergency:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 
```

Il comando successivo associa il numero con il criterio di posizione specificato specificando il parametro EmergencyNumbers nel cmdlet Set-CsLocationPolicy:

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a} 
```

Nell'esempio successivo viene creato un numero di emergenza con una singola maschera di chiamata, 112:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112 
```

Il comando successivo crea un numero di emergenza con più maschere di chiamata:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
```

L'esempio seguente aggiunge più numeri di emergenza con più maschere di chiamata e quindi associa i numeri di emergenza con i criteri di posizione specificati:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999 
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b} 
```

Nell'esempio seguente vengono configurati più numeri di emergenza per i provider di servizi sanitari che usano sia 911 che 450: 

```powershell
> $a = New-CsEmergencyNumber -DialString 911 
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

Nell'esempio seguente vengono configurati più numeri di emergenza per la città di Londra:

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

Nell'esempio seguente vengono configurati più numeri di emergenza per l'India:

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101 
> $c = New-CsEmergencyNumber -DialString 102 
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

Nell'esempio successivo viene rimossa una voce esistente con Dial String 911 e maschere di chiamata 112 e 999:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a} 
```


