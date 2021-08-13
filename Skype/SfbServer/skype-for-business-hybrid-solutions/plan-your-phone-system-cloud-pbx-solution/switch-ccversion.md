---
title: Switch-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: Il cmdlet Switch-CcVersion disconnette l'appliance in esecuzione e passa a un'appliance appena distribuita o di backup.
ms.openlocfilehash: 1558f34d2388dc75bf4398ba15fc09cd36c439e2d70a39588ee697bc0ef04341
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54320039"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
Il cmdlet Switch-CcVersion disconnette l'appliance in esecuzione e passa a un'appliance appena distribuita o di backup. 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente vengono svuotati i servizi dell'appliance in esecuzione corrente e quindi si passa a un'appliance appena distribuita o di backup:
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a>Esempio 2

Nell'esempio seguente vengono svuotati i servizi dell'appliance in esecuzione corrente e i servizi vengono arrestati forzatamente se l'svuotamento dei servizi ha esito negativo. Il comando passa quindi a un'appliance appena distribuita o di backup:
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Switch-CcVersion svuota i servizi del connettore cloud nel Mediation Server e nel server perimetrale. Tutte le chiamate in esecuzione verranno completate, ma l'appliance rifiuterà tutte le nuove chiamate. Dopo l'svuotamento, il cmdlet disconnette l'appliance in esecuzione dalle reti aziendali e Internet, spegne tutte le macchine virtuali appartenenti all'appliance e quindi connette l'appliance di backup alle reti aziendali e Internet.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| Force <br/> | Facoltativo <br/> |System.Management.Automation.SwitchParameter  <br/> | Arresta i servizi forzatamente se l'svuotamento dei servizi ha esito negativo. <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

Nessuno
  

