---
title: Mascherare i numeri di telefono nelle Microsoft Teams riunioni
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
ms.localizationpriority: medium
search.appverid: MET150
description: Informazioni su come mascherare i numeri di telefono nelle Microsoft Teams riunioni
ms.openlocfilehash: f9e7fd76f0b9afa9776e554cbde87a0b302c7011
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/30/2021
ms.locfileid: "58733765"
---
# <a name="mask-phone-numbers-in-microsoft-teams-meetings"></a>Mascherare i numeri di telefono nelle Microsoft Teams riunioni

Per una maggior privacy, i numeri di telefono dei partecipanti che a una riunione di Teams tramite audioconferenza vengono visualizzati completamente ai partecipanti interni. I numeri vengono mascherati dai partecipanti esterni all'organizzazione. Questa impostazione è l'impostazione predefinita per tutte le organizzazioni. Il numero mascherato viene visualizzato come illustrato nell'immagine seguente:

![un esempio di numero di telefono mascherato.](media/hiddenPhoneNum.png)

Per casi d'uso specifici del settore, gli amministratori hanno la possibilità di scegliere come vengono visualizzati i numeri di telefono dei partecipanti ai servizi di audioconferenza nelle riunioni organizzate nel tenant. Gli amministratori possono scegliere tra tre opzioni:

- Telefono i numeri vengono mascherati solo da partecipanti esterni. I partecipanti che appartengono al tenant dell'organizzatore della riunione continuano a visualizzare il numero di telefono completo.
- Telefono i numeri sono mascherati da tutti i partecipanti alla riunione, ad eccezione dell'organizzatore.
- Telefono i numeri vengono smascherati, che li rende visibili a tutti i partecipanti alla riunione.

Questa impostazione viene applicata a tutte le superfici della riunione in cui sono esposti i numeri di telefono.

## <a name="use-microsoft-powershell-to-set-phone-number-masking"></a>Usare Microsoft PowerShell per impostare il mascheramento dei numeri di telefono

Per modificare l'impostazione di mascheramento PSTN (Public Switched Telephone Network), impostare il parametro del **`MaskPstnNumbersType`** cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) su una delle opzioni disponibili.

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