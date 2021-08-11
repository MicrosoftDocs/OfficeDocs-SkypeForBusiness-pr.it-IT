---
title: Set-CcApplianceDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/21/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: Il cmdlet Set-CcApplianceDirectory imposta la directory di lavoro nel server host Skype for Business Cloud Connector Edition. Tutti i file di distribuzione vengono archiviati in questa directory.
ms.openlocfilehash: 8ca6b8b8e175058e5f19c86a9dd1c6e0cf8a43ab6ef7a439eee4e09b5430f6a2
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54306597"
---
# <a name="set-ccappliancedirectory"></a>Set-CcApplianceDirectory
 
Il cmdlet Set-CcApplianceDirectory imposta la directory di lavoro nel server host Skype for Business Cloud Connector Edition. Tutti i file di distribuzione vengono archiviati in questa directory.
  
```powershell
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente la directory di lavoro nel server host viene impostata su c:\cloudconnector\applianceroot:
  
```powershell
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a>Parametri
<a name="Examples"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| Percorso <br/> | Obbligatorio <br/> |System.String  <br/> | Specifica il percorso in cui vengono archiviati tutti i file di distribuzione. <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Set-CcApplianceDirectory non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

Nessuno
  

