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
description: Il Switch-CcVersion disconnette l'applicazione in esecuzione e passa a un'appliance appena distribuita o di backup.
ms.openlocfilehash: 31dbb841caae51de0accedf081fa576ec378044b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824150"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
Il Switch-CcVersion disconnette l'applicazione in esecuzione e passa a un'appliance appena distribuita o di backup. 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente vengono scaricati i servizi dell'applicazione in esecuzione corrente e quindi si passa a un'appliance appena distribuita o di backup:
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a>Esempio 2

Nell'esempio seguente vengono scaricati i servizi dell'applicazione in esecuzione corrente e i servizi vengono arrestati forzatamente in caso di errore di svuotamento dei servizi. Il comando passa quindi a un'appliance appena distribuita o di backup:
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il Switch-CcVersion cmdlet svuota i servizi del connettore cloud nel Mediation Server e nel server perimetrale. Tutte le chiamate in esecuzione verranno completate, ma l'applicazione rifiuterà tutte le nuove chiamate. Dopo lo svuotamento, il cmdlet disconnette l'applicazione in esecuzione dalle reti aziendali e Internet, disattiva tutte le macchine virtuali appartenenti all'appliance e quindi connette l'appliance di backup alle reti aziendali e Internet.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| Force <br/> | Facoltativo <br/> |System.Management.Automation.SwitchParameter  <br/> | Arresta forzatamente i servizi in caso di errore di svuotamento dei servizi. <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

None
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

None
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

Nessuno
  

