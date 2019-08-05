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
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: Il cmdlet Exit-CcUpdate esce dalla modalità di manutenzione degli aggiornamenti nel server host Skype for Business Cloud Connector Edition.
ms.openlocfilehash: b3558a81e1d4bc6c833cca157c2b31f2f252b595
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190829"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
Il cmdlet Exit-CcUpdate esce dalla modalità di manutenzione degli aggiornamenti nel server host Skype for Business Cloud Connector Edition. 
  
Questo cmdlet si applica a Skype for Business Cloud Connector Edition 1.4.1, 1.4.2. 
  
```
Exit-CcUpdate
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Il comando seguente inserisce l'appliance in cui viene eseguito di nuovo in modalità di produzione: 
  
```
Exit-CcUpdate
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Se si dispone di appliance inserite in modalità di manutenzione specificando il cmdlet Enter-CcUpdate, il cmdlet Exit-CcUpdate li riporterà in modalità di produzione. 
  
Per altre informazioni su come inserire gli apparecchi in modalità di manutenzione, vedere Invio-CcUpdate.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Exit-CcUpdate non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno 
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Invio-CcUpdate](enter-ccupdate.md)
  

