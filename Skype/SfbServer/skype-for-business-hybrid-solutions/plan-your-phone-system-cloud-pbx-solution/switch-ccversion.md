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
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: Il cmdlet Switch-CcVersion disconnette l'appliance in uso e passa a un'appliance appena distribuita o di backup.
ms.openlocfilehash: e63c5ea6d74e979f7fc9fe5a4c5eae97a0689e1e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190604"
---
# <a name="switch-ccversion"></a>Switch-CcVersion
 
Il cmdlet Switch-CcVersion disconnette l'appliance in uso e passa a un'appliance appena distribuita o di backup. 
  
```
Switch-CcVersion [-Force]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente svuota i servizi dell'appliance corrente in uso e quindi passa a un'appliance appena distribuita o di backup:
  
```
Switch-CcVersion
```

### <a name="example-2"></a>Esempio 2

L'esempio seguente svuota i servizi dell'appliance corrente e arresta i servizi con forza se lo svuotamento dei servizi non riesce. Il comando passa quindi a un dispositivo appena distribuito o di backup:
  
```
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
  

