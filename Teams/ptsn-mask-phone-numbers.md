---
title: Mascherare i numeri di telefono nelle riunioni di Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Informazioni su come mascherare i numeri di telefono nelle riunioni di Microsoft Teams
ms.openlocfilehash: 5a59ef07873660e79d6c8bc69b7e92095a2fac1a
ms.sourcegitcommit: 4d76837f9481ca2cda437afdf11de5eaf7a57d99
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/11/2021
ms.locfileid: "50726782"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Mascherare i numeri di telefono nelle riunioni di Microsoft Teams

Per una maggior privacy, i numeri di telefono dei partecipanti che a una riunione di Teams con l'audioconferenza vengono visualizzati completamente ai partecipanti interni. I numeri vengono mascherati dai partecipanti esterni all'organizzazione. Questa impostazione è l'impostazione predefinita per tutte le organizzazioni. Il numero mascherato viene visualizzato come illustrato nell'immagine seguente:

![esempio di numero di telefono mascherato](media/hiddenPhoneNum.png)

Per specifici casi d'uso del settore, gli amministratori possono scegliere come visualizzare i numeri di telefono dei partecipanti ai servizi di audioconferenza nelle riunioni organizzate nel tenant. Gli amministratori possono scegliere tra tre opzioni:

- I numeri di telefono sono mascherati solo da partecipanti esterni. I partecipanti che appartengono al tenant dell'organizzatore della riunione continuano a visualizzare il numero di telefono completo.
- I numeri di telefono sono mascherati da tutti i partecipanti alla riunione, ad eccezione dell'organizzatore.
- I numeri di telefono vengono smascherati, quindi sono visibili a tutti i partecipanti alla riunione.

Questa impostazione viene applicata a tutte le superfici della riunione in cui sono esposti i numeri di telefono.

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Usare Microsoft PowerShell per impostare il mascheramento dei numeri di telefono

Per modificare l'impostazione di mascheramento PSTN (Public Switched Telephone Network), impostare il parametro del **`MaskPstnNumbersType`** cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://docs.microsoft.com/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) su una delle opzioni disponibili.

Per mascherare i numeri di telefono solo da partecipanti esterni, eseguire il comando seguente:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

Per mascherare i numeri di telefono di tutti i partecipanti alla riunione (ad eccezione dell'organizzatore), eseguire il comando seguente:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

Per disabilitare il mascheramento dei numeri di telefono, eseguire il comando seguente:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```
