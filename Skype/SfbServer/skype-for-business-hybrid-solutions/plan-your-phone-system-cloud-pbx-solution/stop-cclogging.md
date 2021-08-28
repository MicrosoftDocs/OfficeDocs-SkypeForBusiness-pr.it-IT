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
ms.localizationpriority: medium
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: Il cmdlet Stop-CcLogging interrompe la generazione del registro delle chiamate in ingresso e in uscita per un Skype for Business Cloud Connector Edition appliance.
ms.openlocfilehash: cfa07602f8465ce3c931010f835f52acc44e2ee2
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58580341"
---
# <a name="stop-cclogging"></a>Stop-CcLogging
 
Il cmdlet Stop-CcLogging interrompe la generazione del registro delle chiamate in ingresso e in uscita per un Skype for Business Cloud Connector Edition appliance.
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene interrotta la generazione del registro chiamate in ingresso e in uscita: 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a>Esempio 2

Nell'esempio seguente viene interrotta la generazione del registro chiamate in ingresso e in uscita e vengono puliti i file della cache:
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Stop-CcLogging interrompe la registrazione delle chiamate in ingresso e in uscita su un dispositivo. Per impostazione predefinita, la registrazione verrà interrotta automaticamente dopo quattro ore.
  
## <a name="parameters"></a>Parametri
<a name="DetailedDescription"> </a>

|**Parametro**|**Obbligatorio**|**Tipo**|**Descrizione**|
|:-----|:-----|:-----|:-----|
| RemoveCache <br/> | Facoltativo <br/> | System.Management.Automation.SwitchParameter <br/> |Rimuove i file della cache di registrazione.  <br/> |
   
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Stop-CcLogging non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Search-CcLog](search-cclog.md)
  
[Start-CcLogging](start-cclogging.md)
  

