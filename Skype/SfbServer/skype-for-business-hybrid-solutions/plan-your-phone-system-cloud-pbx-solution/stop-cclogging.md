---
title: Stop-CcLogging
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
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Il cmdlet Stop-CcLogging smette di generare il log delle chiamate in entrata e in uscita per un appliance di Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 8a012e9b1a94c3698cc61da4326eb0ccbb27bca2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824160"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
Il cmdlet Stop-CcLogging smette di generare il log delle chiamate in entrata e in uscita per un appliance di Skype for Business Cloud Connector Edition.
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente interrompe la generazione del log delle chiamate in entrata e in uscita: 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a>Esempio 2

L'esempio seguente smette di generare il log delle chiamate in entrata e in uscita e pulisce i file della cache:
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Stop-CcLogging interrompe la registrazione delle chiamate in entrata e in uscita in un dispositivo. Per impostazione predefinita, la registrazione si arresta automaticamente dopo quattro ore.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Richiesto**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | Facoltativo <br/> | System.Management.Automation.SwitchParameter <br/> |Rimuove i file della cache di registrazione.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Stop-CcLogging non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

