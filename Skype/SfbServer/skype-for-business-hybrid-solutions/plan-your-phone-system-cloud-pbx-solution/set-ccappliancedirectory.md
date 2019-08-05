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
localization_priority: Normal
ms.assetid: 6da93ddb-ca99-4b5d-9b33-3d70659730b2
description: Il cmdlet Set-CcApplianceDirectory imposta la directory di lavoro nel server host di Skype for Business Cloud Connector Edition. Tutti i file di distribuzione sono archiviati in questa directory.
ms.openlocfilehash: 56a13da740b0c23adee7e05ddbcc1bbc82f0f1cc
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190649"
---
# <a name="set-ccappliancedirectory"></a>Set-CcApplianceDirectory
 
Il cmdlet Set-CcApplianceDirectory imposta la directory di lavoro nel server host di Skype for Business Cloud Connector Edition. Tutti i file di distribuzione sono archiviati in questa directory.
  
```
Set-CcApplianceDirectory[[-Path] <string>]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente imposta la directory di lavoro nel server host su c:\cloudconnector\applianceroot:
  
```
Set-CcApplianceDirectory -Path "c:\cloudconnector\applianceroot"
```

## <a name="parameters"></a>Parametri
<a name="Examples"> </a>

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| Percorso <br/> | Obbligatorio <br/> |System.String  <br/> | Specifica il percorso in cui sono archiviati tutti i file di distribuzione. <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Set-CcApplianceDirectory non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

Nessuno
  

