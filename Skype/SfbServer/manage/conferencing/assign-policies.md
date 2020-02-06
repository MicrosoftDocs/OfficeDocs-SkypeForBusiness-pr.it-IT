---
title: Assegnare criteri di conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Riepilogo: informazioni su come assegnare criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: c5dfb9c2aa186bf199a066c82e3687aade564905
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818658"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Assegnare criteri di conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni su come assegnare criteri di conferenza in Skype for Business Server.
  
Puoi assegnare criteri di conferenza agli utenti usando Skype for Business Server Management Shell e il cmdlet **Grant-CsConferencingPolicy** .
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Assegnare criteri di conferenza tramite Skype for Business Server Management Shell

Nell'esempio seguente, il criterio SalesConferencingPolicy viene assegnato all'utente con l'identità "Ken":
  
```PowerShell
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

Nell'esempio seguente, il criterio di conferenza FinanceConferencingPolicy viene assegnato a tutti gli utenti che hanno account nell'unità organizzativa Finance. Per assegnare lo stesso criterio a tutti gli utenti di una determinata unità organizzativa, viene usato il cmdlet Get-CsUser per recuperare tutti gli account in tale OU. Dopo aver recuperato gli account utente, le informazioni vengono quindi inviate tramite pipe al cmdlet Grant-CsConferencingPolicy, che assegna i criteri FinanceConferencingPolicy a ogni utente della raccolta:
  
```PowerShell
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Per altre informazioni, inclusa la sintassi completa e un elenco di parametri, vedere [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).
  

