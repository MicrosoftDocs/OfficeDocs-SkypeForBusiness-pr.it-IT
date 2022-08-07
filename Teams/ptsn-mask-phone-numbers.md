---
title: Mascherare i numeri di telefono nelle riunioni di Microsoft Teams
author: heidip
ms.author: MicrosoftHeidi
manager: serdars
ms.reviewer: moakram
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come mascherare i numeri di telefono nelle riunioni di Microsoft Teams
ms.openlocfilehash: e1ef25f12bdf92bc58739284af2a624257169403
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270821"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Mascherare i numeri di telefono nelle riunioni di Microsoft Teams

Per una maggiore privacy, i numeri di telefono dei partecipanti che accedono a una riunione di Teams tramite audioconferenza vengono visualizzati completamente ai partecipanti interni. I numeri vengono mascherati dai partecipanti esterni all'organizzazione. Questa è l'impostazione predefinita per tutte le organizzazioni. Il numero mascherato viene visualizzato come illustrato nell'immagine seguente:

![un esempio di numero di telefono mascherato.](media/hiddenPhoneNum.png)

Per specifici casi di utilizzo di settore, gli amministratori hanno la possibilità di scegliere come visualizzare i numeri di telefono dei partecipanti ai servizi di audioconferenza nelle riunioni organizzate nel proprio tenant. Gli amministratori possono scegliere tra tre opzioni:

- I numeri di telefono vengono mascherati solo dai partecipanti esterni. I partecipanti che appartengono al tenant dell'organizzatore della riunione vedono ancora il numero di telefono completo.
- I numeri di telefono vengono mascherati da tutti i partecipanti alla riunione tranne l'organizzatore.
- I numeri di telefono vengono smascherati, rendendoli visibili a tutti i partecipanti alla riunione.

Questa impostazione viene applicata a tutte le superfici della riunione in cui vengono esposti i numeri di telefono.

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Usare Microsoft PowerShell per impostare il mascheramento dei numeri di telefono

Per modificare l'impostazione di mascheramento PSTN (Public Switched Telephone Network), imposta il **`MaskPstnNumbersType`** parametro del cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) su una delle opzioni disponibili.

Per mascherare i numeri di telefono solo dei partecipanti esterni, eseguire il comando seguente:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForExternalUsers"
```

Per mascherare i numeri di telefono di tutti i partecipanti alla riunione (eccetto l'organizzatore), eseguire il comando seguente:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "MaskedForAllUsers"
```

Per disabilitare il filtro dei numeri di telefono, eseguire il comando seguente:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -MaskPstnNumbersType "NoMasking"
```
