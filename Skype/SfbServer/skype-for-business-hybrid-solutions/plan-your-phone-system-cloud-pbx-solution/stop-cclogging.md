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
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Il cmdlet Stop-CcLogging smette di generare il log delle chiamate in entrata e in uscita per un appliance di Skype for Business Cloud Connector Edition.
ms.openlocfilehash: dcc62e8ec772912a8275f5321a6c91e28dde8c25
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36190616"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
Il cmdlet Stop-CcLogging smette di generare il log delle chiamate in entrata e in uscita per un appliance di Skype for Business Cloud Connector Edition.
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente interrompe la generazione del log delle chiamate in entrata e in uscita: 
  
```
Stop-CcLogging
```

### <a name="example-2"></a>Esempio 2

L'esempio seguente smette di generare il log delle chiamate in entrata e in uscita e pulisce i file della cache:
  
```
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

[Ricerca-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

