---
title: Update Item
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: "Riepilogo: informazioni sull'operazione di aggiornamento degli elementi, che fa parte del servizio elementi. Il servizio elementi fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 78da2fa414b4ba266f9e6aba4feac5ff73150062
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803086"
---
# <a name="update-item"></a>Update Item
 
**Riepilogo:** Informazioni sull'operazione di aggiornamento degli elementi, che fa parte del servizio elementi. Il servizio elementi fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione di aggiornamento degli elementi fa parte del servizio elementi nell'API del repository per il dashboard qualità chiamata.
  
## <a name="update-item"></a>Update Item

Update Item aggiorna un elemento specifico nel repository.
  

|**Metodo**|**URI della richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|PUT  <br/> |https:// \<portal\> /QoERepositoryService/repository/Item/{ItemId}  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** -None.
  
 **Intestazioni richieste** -Content-Type: Application/JSON.
  
 **Richiesta corpo** -JSON.
  
Payload di richiesta di esempio:
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *contenuto*  I dati formattati JSON devono essere archiviati come nuovo contenuto di un elemento secondario esistente. Tecnicamente, un archivio è in grado di archiviare qualsiasi contenuto di qualsiasi schema, ma se utilizzato per il dashboard per la qualità delle chiamate, dovrebbe essere un report o una query. *tipo*  di  Specificare sempre "application/json" per il dashboard per la qualità delle chiamate.
  
 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** -un'operazione completata restituisce il codice di stato 204 (nessun contenuto). Se un ID elemento specificato non viene trovato, restituisce il codice di stato 404 (non trovato).
  
> [!IMPORTANT]
> "Nessun contenuto" non è uno stato di errore. Significa che una risposta non ha restituito nulla nel corpo (al contrario, 200 OK restituisce il contenuto nel corpo). Indica che l'elemento è stato aggiornato correttamente. 
  
 **Intestazioni di risposta** -None.
  
 **Corpo di risposta** -nessuno.
  

