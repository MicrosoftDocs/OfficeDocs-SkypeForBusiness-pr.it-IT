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
description: Il cmdlet Switch-CcVersion disconnette l'appliance in uso e passa a un'appliance appena distribuita o di backup.
ms.openlocfilehash: 31dbb841caae51de0accedf081fa576ec378044b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824150"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
Il cmdlet Switch-CcVersion disconnette l'appliance in uso e passa a un'appliance appena distribuita o di backup. 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente svuota i servizi dell'appliance corrente in uso e quindi passa a un'appliance appena distribuita o di backup:
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a>Esempio 2

L'esempio seguente svuota i servizi dell'appliance corrente e arresta i servizi con forza se lo svuotamento dei servizi non riesce. Il comando passa quindi a un dispositivo appena distribuito o di backup:
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Switch-CcVersion svuota i servizi Cloud Connector in Mediation Server e Edge Server. Tutte le chiamate in uso verranno completate, ma l'accessorio rifiuterà tutte le nuove chiamate. Dopo lo svuotamento, il cmdlet disconnette l'appliance corrente dalle reti aziendali e Internet, disattiva tutte le macchine virtuali appartenenti all'appliance e quindi connette l'appliance di backup alle reti aziendali e Internet.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| Force <br/> | Facoltativo <br/> |System.Management.Automation.SwitchParameter  <br/> | Arresta i servizi con forza se lo svuotamento dei servizi non riesce. <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

Nessuno
  

