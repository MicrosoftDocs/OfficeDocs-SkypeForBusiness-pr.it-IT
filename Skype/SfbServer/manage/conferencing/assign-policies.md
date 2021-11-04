---
title: Assegnare criteri di conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Riepilogo: informazioni su come assegnare criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: e63e59f806bcef14a50f75924527aa0f8733799b
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60767834"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Assegnare criteri di conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni su come assegnare criteri di conferenza in Skype for Business Server.
  
È possibile assegnare criteri di conferenza agli utenti utilizzando Skype for Business Server Management Shell e il cmdlet **Grant-CsConferencingPolicy.**
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Assegnare criteri di conferenza tramite Skype for Business Server Management Shell

Nell'esempio seguente, il criterio SalesConferencingPolicy viene assegnato all'utente con identità "Ken Myer":
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

Nell'esempio successivo, il criterio di conferenza FinanceConferencingPolicy viene assegnato a tutti gli utenti che dispongono di account nell'unità organizzativa Finance. Per assegnare lo stesso criterio a tutti gli utenti di una determinata unità organizzativa (OU), viene utilizzato il cmdlet Get-CsUser per recuperare tutti gli account di tale unità. Dopo il recupero degli account utente, tali informazioni vengono quindi reindirizzate al cmdlet Grant-CsConferencingPolicy, che assegna il criterio FinanceConferencingPolicy a ogni utente della raccolta:
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Per ulteriori informazioni, inclusa la sintassi completa e un elenco di parametri, vedere [Grant-CsConferencingPolicy](/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).
