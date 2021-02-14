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
description: Il cmdlet Enter-CcUpdate prepara il server host Skype for Business Cloud Connector Edition per il processo di aggiornamento attivando la modalità di manutenzione. L'applicazione arresta immediatamente tutti i servizi, terminando le chiamate in corso e rifiutando eventuali nuove chiamate.
ms.openlocfilehash: 25d2fbc56bd4de6a08985de18c178d5a8f993492
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802176"
---
# <a name="enter-ccupdate"></a>Enter-CcUpdate

Il cmdlet Enter-CcUpdate prepara il server host Skype for Business Cloud Connector Edition per il processo di aggiornamento attivando la modalità di manutenzione. L'applicazione arresta immediatamente tutti i servizi, terminando le chiamate in corso e rifiutando eventuali nuove chiamate.
  
```powershell
Enter-CcUpdate
```

## <a name="parameters"></a>Parametri

None
  
## <a name="examples"></a>Esempi
<a name="Examples"> </a>

### <a name="example-1"></a>Esempio 1

Nell'esempio seguente viene preparato l'applicazione per il processo di aggiornamento attivando la modalità di manutenzione:
  
```powershell
Enter-CcUpdate 
```

## <a name="detailed-description"></a>Descrizione dettagliata
<a name="DetailedDescription"> </a>

Il cmdlet Enter-CcUpdate arresta immediatamente tutti i servizi che terminano le chiamate in corso e l'applicazione rifiuterà le nuove chiamate, trasferite ad altre appliance di produzione. È necessario verificare che gli appliance di produzione rimanenti siano in grado di gestire le chiamate dall'appliance che si sta preparando per l'aggiornamento.
  
La modalità manutenzione è utile, ad esempio, se l'applicazione dispone dell'aggiornamento automatico abilitato e Microsoft rilascia un hotfix critico. La modalità manutenzione è utile anche se decidi di disattivare gli aggiornamenti automatici, ma esegui gli aggiornamenti manuali su base coerente.
  
Dopo aver installato gli aggiornamenti, il dispositivo può essere riportato in modalità di produzione eseguendo il cmdlet Exit-CcUpdate.
  
> [!NOTE]
> Se si decide di aggiornare manualmente un'applicazione Cloud Connector, è necessario aggiornarla entro 60 giorni dal rilascio della versione successiva da parte di Microsoft. Microsoft supporta la versione rilasciata in precedenza di Cloud Connector per 60 giorni dopo il rilascio della nuova versione 
  
## <a name="input-types"></a>Tipi di input
<a name="InputTypes"> </a>

Nessuna. Il cmdlet Enter-CCUpdate non accetta input da pipeline.
  
## <a name="return-types"></a>Tipi restituiti
<a name="ReturnTypes"> </a>

None 
  
## <a name="see-also"></a>Vedere anche
<a name="ReturnTypes"> </a>

[Exit-CcUpdate](exit-ccupdate.md)
  

