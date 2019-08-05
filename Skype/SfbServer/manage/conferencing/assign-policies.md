---
title: Assegnare criteri di conferenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f384d19b-0950-4ec6-9d93-2c5958b83e71
description: 'Riepilogo: informazioni su come assegnare criteri di conferenza in Skype for Business Server.'
ms.openlocfilehash: acd74262b51000a3f4af5668fb3c9271a8c0978d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191273"
---
# <a name="assign-conferencing-policies-in-skype-for-business-server"></a>Assegnare criteri di conferenza in Skype for Business Server
 
**Riepilogo:** Informazioni su come assegnare criteri di conferenza in Skype for Business Server.
  
Puoi assegnare criteri di conferenza agli utenti usando Skype for Business Server Management Shell e il cmdlet **Grant-CsConferencingPolicy** .
  
## <a name="assign-conferencing-policies-by-using-skype-for-business-server-management-shell"></a>Assegnare criteri di conferenza tramite Skype for Business Server Management Shell

Nell'esempio seguente, il criterio SalesConferencingPolicy viene assegnato all'utente con l'identità "Ken":
  
```
Grant-CsConferencingPolicy -identity "Ken Myer" -PolicyName SalesConferencingPolicy
```

Nell'esempio seguente, il criterio di conferenza FinanceConferencingPolicy viene assegnato a tutti gli utenti che hanno account nell'unità organizzativa Finance. Per assegnare lo stesso criterio a tutti gli utenti di una determinata unità organizzativa, viene usato il cmdlet Get-CsUser per recuperare tutti gli account in tale OU. Dopo aver recuperato gli account utente, le informazioni vengono quindi inviate tramite pipe al cmdlet Grant-CsConferencingPolicy, che assegna i criteri FinanceConferencingPolicy a ogni utente della raccolta:
  
```
Get-CsUser -OU "ou=Finance,dc=litwareinc,dc=com" | Grant-CsConferencingPolicy -PolicyName FinanceConferencingPolicy
```

Per altre informazioni, inclusa la sintassi completa e un elenco di parametri, vedere [Grant-CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csconferencingpolicy?view=skype-ps).
  

