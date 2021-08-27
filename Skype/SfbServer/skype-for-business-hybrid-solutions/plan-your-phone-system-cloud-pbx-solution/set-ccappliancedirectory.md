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
ms.localizationpriority: medium
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: Il cmdlet Set-CcApplianceDirectory consente di impostare la directory di lavoro nel server Skype for Business Cloud Connector Edition host. Tutti i file di distribuzione vengono archiviati in questa directory.
ms.openlocfilehash: 0f64fbb52cd12020104e98051564379d1fbc4985
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58617668"
---
# <a name="set-ccappliancedirectory"></a>Set-CcApplianceDirectory
 
Il cmdlet Set-CcApplianceDirectory consente di impostare la directory di lavoro nel server Skype for Business Cloud Connector Edition host. Tutti i file di distribuzione vengono archiviati in questa directory.
  
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
  

