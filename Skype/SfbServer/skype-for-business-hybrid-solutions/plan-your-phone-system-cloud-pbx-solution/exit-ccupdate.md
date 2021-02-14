---
title: Exit-CcUpdate
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
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: Il cmdlet Exit-CcUpdate esce dalla modalità di manutenzione degli aggiornamenti nel server host Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 315d6b7dccb6708901128bf8faa29a60f712e833
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801766"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
Il cmdlet Exit-CcUpdate esce dalla modalità di manutenzione degli aggiornamenti nel server host Skype for Business Cloud Connector Edition. 
  
Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2. 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a>Parametri

None
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Con il comando seguente l'applicazione in cui viene eseguita torna in modalità di produzione: 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Se si dispone di appliance che sono state messe in modalità manutenzione specificando il cmdlet Enter-CcUpdate, il cmdlet Exit-CcUpdate li inservirà di nuovo in modalità di produzione. 
  
Per ulteriori informazioni sull'utilizzo delle appliance in modalità manutenzione, vedere Enter-CcUpdate.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Exit-CcUpdate non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

None 
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

