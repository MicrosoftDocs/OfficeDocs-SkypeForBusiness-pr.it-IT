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
description: Il cmdlet Enter-CcUpdate prepara il server host Skype for Business Cloud Connector Edition per il processo di aggiornamento mettendolo in modalità manutenzione. L'appliance arresta immediatamente tutti i servizi, terminando le chiamate in corso e rifiutando eventuali nuove chiamate.
ms.openlocfilehash: 75be5933e31f3966ab36f9957b78cd89c21a4a31df23b5761000a6e96cd9806e
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54303649"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate

Il cmdlet Enter-CcUpdate prepara il server host Skype for Business Cloud Connector Edition per il processo di aggiornamento mettendolo in modalità manutenzione. L'appliance arresta immediatamente tutti i servizi, terminando le chiamate in corso e rifiutando eventuali nuove chiamate.
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a>Parametri

Nessuno
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

L'esempio seguente prepara l'appliance per il processo di aggiornamento attivando la modalità di manutenzione:
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Enter-CcUpdate arresterà immediatamente tutti i servizi che terminano le chiamate in corso e l'appliance rifiuterà le nuove chiamate, trasferite ad altre appliance di produzione. È necessario verificare che le altre appliance di produzione siano in grado di gestire le chiamate dall'appliance che si sta preparando per l'aggiornamento.
  
La modalità di manutenzione è utile, ad esempio, se nel dispositivo è abilitato l'aggiornamento automatico e Microsoft rilascia un hotfix critico. La modalità manutenzione è utile anche se decidi di disattivare gli aggiornamenti automatici, ma esegui gli aggiornamenti manuali in modo coerente.
  
Dopo aver installato gli aggiornamenti, è possibile tornare alla modalità di produzione eseguendo il cmdlet Exit-CcUpdate.
  
> [!NOTE]
> Se si decide di aggiornare manualmente un'appliance Cloud Connector, è necessario aggiornarla entro 60 giorni dal rilascio della versione successiva da parte di Microsoft. Microsoft supporta la versione rilasciata in precedenza di Cloud Connector per 60 giorni dopo il rilascio della nuova versione 
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Enter-CCUpdate non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

Nessuno 
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

