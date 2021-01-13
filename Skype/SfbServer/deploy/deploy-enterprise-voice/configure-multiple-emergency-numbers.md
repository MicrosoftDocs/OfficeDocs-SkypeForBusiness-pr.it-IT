---
title: Configurare più numeri di emergenza in Skype for business
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 2e869df0-5fdb-4e70-bd81-cb012556eb1a
description: Leggere questo argomento per informazioni su come configurare più numeri di emergenza in Skype for Business Server.
ms.openlocfilehash: fe53e914eb0c406a4f7013df2f6ec106fa781f56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49804106"
---
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a>Configurare più numeri di emergenza in Skype for business

Leggere questo argomento per informazioni su come configurare più numeri di emergenza in Skype for Business Server.

Skype for Business Server ora supporta più numeri di emergenza per un client. Numeri di emergenza multipli è una nuova funzionalità introdotta nell'aggiornamento cumulativo di giugno 2016. Prima di configurare l'ambiente per il supporto di più numeri di emergenza, leggere [piano per più numeri di emergenza in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).

> [!NOTE]
> Se non è stato ancora aggiornato all'aggiornamento cumulativo del 2016 novembre, vedere Updates [to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015). Con l'aggiornamento cumulativo di novembre 2016, il numero di numeri di emergenza di supporto aumenta da 5 a 100.

## <a name="configure-multiple-emergency-numbers"></a>Configurare più numeri di emergenza

Per configurare più numeri di emergenza, è possibile utilizzare il cmdlet New-CsEmergencyNumber e quindi specificare il parametro EmergencyNumbers con i cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) e [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) . Per una descrizione completa di tutti i parametri dei criteri di percorso, ad esempio l'utilizzo e la posizione PSTN richiesti, vedere [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).

Il comando seguente crea un nuovo numero di emergenza con la stringa di chiamata 911 utilizzando il cmdlet New-CsEmergency:

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

Il comando successivo associa il numero al criterio percorso specificato specificando il parametro EmergencyNumbers nel cmdlet Set-CsLocationPolicy:

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

Nell'esempio riportato di seguito viene creato un numero di emergenza con una singola maschera di chiamata, 112:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

Il comando seguente consente di creare un numero di emergenza con più maschere di chiamata:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

Nell'esempio seguente vengono aggiunti più numeri di emergenza con più maschere di chiamata e quindi i numeri di emergenza vengono associati ai criteri percorso specificati:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

Nell'esempio seguente vengono configurati più numeri di emergenza per i provider di servizi di assistenza sanitaria che utilizzano sia 911 che 450:

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

Nell'esempio riportato di seguito viene rimossa una voce esistente con Dial String 911 e dial Masks 112 e 999:

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
