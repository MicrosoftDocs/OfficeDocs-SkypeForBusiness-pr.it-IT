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
description: Il cmdlet Exit-CcUpdate esce dalla modalità di manutenzione degli aggiornamenti nel server host Skype for Business Cloud Connector Edition server host.
ms.openlocfilehash: d55004f071caa67492d5368e36007d9c3c307b90aabbc33d79d1feeb4aa37356
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54288838"
---
# <a name="exit-ccupdate"></a>Exit-CcUpdate
 
Il cmdlet Exit-CcUpdate esce dalla modalità di manutenzione degli aggiornamenti nel server host Skype for Business Cloud Connector Edition server host. 
  
Questo cmdlet si applica Skype for Business Cloud Connector Edition 1.4.1, 1.4.2. 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Con il comando seguente l'appliance su cui viene eseguito torna in modalità di produzione: 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Se si dispone di appliance che sono state messe in modalità di manutenzione specificando il cmdlet Enter-CcUpdate, il cmdlet Exit-CcUpdate tornerà in modalità di produzione. 
  
Per ulteriori informazioni sull'inserimento delle appliance in modalità manutenzione, vedere Enter-CcUpdate.
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Exit-CcUpdate non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno 
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Enter-CcUpdate](enter-ccupdate.md)
  

