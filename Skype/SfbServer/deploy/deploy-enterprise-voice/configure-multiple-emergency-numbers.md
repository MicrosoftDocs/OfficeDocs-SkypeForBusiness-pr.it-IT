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
# <a name="configure-multiple-emergency-numbers-in-skype-for-business"></a><span data-ttu-id="1bc6f-103">Configurare più numeri di emergenza in Skype for business</span><span class="sxs-lookup"><span data-stu-id="1bc6f-103">Configure multiple emergency numbers in Skype for Business</span></span>

<span data-ttu-id="1bc6f-104">Leggere questo argomento per informazioni su come configurare più numeri di emergenza in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-104">Read this topic to learn how to configure multiple emergency numbers in Skype for Business Server.</span></span>

<span data-ttu-id="1bc6f-105">Skype for Business Server ora supporta più numeri di emergenza per un client.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-105">Skype for Business Server now supports multiple emergency numbers for a client.</span></span> <span data-ttu-id="1bc6f-106">Numeri di emergenza multipli è una nuova funzionalità introdotta nell'aggiornamento cumulativo di giugno 2016.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-106">Multiple emergency numbers is a new feature introduced in the June 2016 Cumulative Update.</span></span> <span data-ttu-id="1bc6f-107">Prima di configurare l'ambiente per il supporto di più numeri di emergenza, leggere [piano per più numeri di emergenza in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="1bc6f-107">Before you configure your environment to support multiple emergency numbers, be sure to read [Plan for multiple emergency numbers in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/multiple-emergency-numbers.md).</span></span>

> [!NOTE]
> <span data-ttu-id="1bc6f-108">Se non è stato ancora aggiornato all'aggiornamento cumulativo del 2016 novembre, vedere Updates [to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span><span class="sxs-lookup"><span data-stu-id="1bc6f-108">If you have not yet upgraded to the November 2016 Cumulative Update, see [Updates to Skype for Business Server 2015](https://support.microsoft.com/help/3061064/updates-for-skype-for-business-server-2015).</span></span> <span data-ttu-id="1bc6f-109">Con l'aggiornamento cumulativo di novembre 2016, il numero di numeri di emergenza di supporto aumenta da 5 a 100.</span><span class="sxs-lookup"><span data-stu-id="1bc6f-109">With the November 2016 Cumulative Update, the number of support emergency numbers increases from 5 to 100.</span></span>

## <a name="configure-multiple-emergency-numbers"></a><span data-ttu-id="1bc6f-110">Configurare più numeri di emergenza</span><span class="sxs-lookup"><span data-stu-id="1bc6f-110">Configure multiple emergency numbers</span></span>

<span data-ttu-id="1bc6f-111">Per configurare più numeri di emergenza, è possibile utilizzare il cmdlet New-CsEmergencyNumber e quindi specificare il parametro EmergencyNumbers con i cmdlet [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) e [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="1bc6f-111">To configure multiple emergency numbers, you use the New-CsEmergencyNumber cmdlet, and then you specify the EmergencyNumbers parameter with the [New-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/new-cslocationpolicy?view=skype-ps) and [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps) cmdlets.</span></span> <span data-ttu-id="1bc6f-112">Per una descrizione completa di tutti i parametri dei criteri di percorso, ad esempio l'utilizzo e la posizione PSTN richiesti, vedere [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="1bc6f-112">For a complete description of all the location policy parameters, such as PSTN usage and Location required, see [Set-CsLocationPolicy](https://docs.microsoft.com/powershell/module/skype/set-cslocationpolicy?view=skype-ps).</span></span>

<span data-ttu-id="1bc6f-113">Il comando seguente crea un nuovo numero di emergenza con la stringa di chiamata 911 utilizzando il cmdlet New-CsEmergency:</span><span class="sxs-lookup"><span data-stu-id="1bc6f-113">The following command creates a new emergency number with dial string 911 by using the New-CsEmergency cmdlet:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
```

<span data-ttu-id="1bc6f-114">Il comando successivo associa il numero al criterio percorso specificato specificando il parametro EmergencyNumbers nel cmdlet Set-CsLocationPolicy:</span><span class="sxs-lookup"><span data-stu-id="1bc6f-114">The next command associates the number with the specified location policy by specifying the EmergencyNumbers parameter in the Set-CsLocationPolicy cmdlet:</span></span>

```powershell
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a}
```

<span data-ttu-id="1bc6f-115">Nell'esempio riportato di seguito viene creato un numero di emergenza con una singola maschera di chiamata, 112:</span><span class="sxs-lookup"><span data-stu-id="1bc6f-115">In the next example, an emergency number is created with a single dial mask, 112:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112
```

<span data-ttu-id="1bc6f-116">Il comando seguente consente di creare un numero di emergenza con più maschere di chiamata:</span><span class="sxs-lookup"><span data-stu-id="1bc6f-116">The next command creates an emergency number with multiple dial masks:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
```

<span data-ttu-id="1bc6f-117">Nell'esempio seguente vengono aggiunti più numeri di emergenza con più maschere di chiamata e quindi i numeri di emergenza vengono associati ai criteri percorso specificati:</span><span class="sxs-lookup"><span data-stu-id="1bc6f-117">The next example adds multiple emergency numbers with multiple dial masks, and then associates the emergency numbers with the specified location policy:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> $b = New-CsEmergencyNumber -DialString 500 -DialMask 501;502
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="1bc6f-118">Nell'esempio seguente vengono configurati più numeri di emergenza per i provider di servizi di assistenza sanitaria che utilizzano sia 911 che 450:</span><span class="sxs-lookup"><span data-stu-id="1bc6f-118">The next example configures multiple emergency numbers for health care providers that use both 911 and 450:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911
> $b = New-CsEmergencyNumber -DialString 450
> Set-CsLocationPolicy -Identity US-Hospital -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="1bc6f-119">Nell'esempio seguente vengono configurati più numeri di emergenza per la città di Londra:</span><span class="sxs-lookup"><span data-stu-id="1bc6f-119">The next example configures multiple emergency numbers for the city of London:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 999 -DialMask 144
> $b = New-CsEmergencyNumber -DialString 112 -DialMask 911;117;118
> Set-CsLocationPolicy -Identity London -EmergencyNumbers @{add=$a,$b}
```

<span data-ttu-id="1bc6f-120">Nell'esempio seguente vengono configurati più numeri di emergenza per l'India:</span><span class="sxs-lookup"><span data-stu-id="1bc6f-120">The next example configures multiple emergency numbers for India:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 100 -DialMask 911
> $b = New-CsEmergencyNumber -DialString 101
> $c = New-CsEmergencyNumber -DialString 102
> Set-CsLocationPolicy -Identity India -EmergencyNumbers @{add=$a,$b,$c}
```

<span data-ttu-id="1bc6f-121">Nell'esempio riportato di seguito viene rimossa una voce esistente con Dial String 911 e dial Masks 112 e 999:</span><span class="sxs-lookup"><span data-stu-id="1bc6f-121">The next example removes an existing entry with Dial string 911 and Dial masks 112 and 999:</span></span>

```powershell
> $a = New-CsEmergencyNumber -DialString 911 -DialMask 112;999
> Set-CsLocationPolicy -Identity <id> -EmergencyNumbers @{remove=$a}
```
