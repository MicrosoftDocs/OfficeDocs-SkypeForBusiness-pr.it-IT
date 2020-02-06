---
title: Enter-CcUpdate
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
ms.date: 3/31/2017
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 330367f2-22b0-43e3-b8fb-3e0d2e3b330e
description: Il cmdlet Enter-CcUpdate prepara il server host di Skype for Business Cloud Connector Edition per il processo di aggiornamento inserendolo in modalità di manutenzione. L'appliance arresta immediatamente tutti i servizi, terminando qualsiasi chiamata in corso e rifiutando le nuove chiamate.
ms.openlocfilehash: 25d2fbc56bd4de6a08985de18c178d5a8f993492
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802176"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate

Il cmdlet Enter-CcUpdate prepara il server host di Skype for Business Cloud Connector Edition per il processo di aggiornamento inserendolo in modalità di manutenzione. L'appliance arresta immediatamente tutti i servizi, terminando qualsiasi chiamata in corso e rifiutando le nuove chiamate.
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente prepara l'appliance per il processo di aggiornamento immettendo la modalità di manutenzione:
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Enter-CcUpdate arresta immediatamente tutti i servizi che terminano le chiamate in corso e l'appliance respinge le nuove chiamate, che vengono trasferite ad altri apparecchi di produzione. È necessario assicurarsi che gli apparecchi di produzione rimanenti abbiano una capacità sufficiente per gestire le chiamate dall'appliance che si sta preparando per l'aggiornamento.
  
La modalità di manutenzione è utile se l'accessorio è abilitato per l'aggiornamento automatico, ad esempio, e Microsoft rilascia un hotfix critico. La modalità di manutenzione è utile anche se si decide di disattivare gli aggiornamenti automatici, ma si eseguono aggiornamenti manuali su base coerente.
  
Dopo l'installazione degli aggiornamenti, l'appliance può essere riportata in modalità di produzione eseguendo il cmdlet Exit-CcUpdate.
  
> [!NOTE]
> Se si decide di aggiornare manualmente un dispositivo Cloud Connector, è necessario aggiornarlo entro 60 giorni dopo che Microsoft rilascia la versione successiva. Microsoft supporta la versione rilasciata in precedenza di Cloud Connector per 60 giorni dopo il rilascio della nuova versione 
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuno. Il cmdlet Enter-CCUpdate non accetta l'input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno 
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

