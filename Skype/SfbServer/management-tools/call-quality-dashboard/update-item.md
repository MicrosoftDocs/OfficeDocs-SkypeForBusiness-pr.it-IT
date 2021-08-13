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
description: "Riepilogo: informazioni sull'operazione Update Item, che fa parte di Item Service. Item Service fa parte dell'API repository per il dashboard di qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: ad615e5b6c6187a51293e86bcf3b1e2ee20c820f8c8c7a48b013d95befd03d87
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54340802"
---
# <a name="update-item"></a>Update Item
 
**Riepilogo:** Informazioni sull'operazione Update Item, che fa parte di Item Service. Item Service fa parte dell'API repository per il dashboard di qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'operazione Update Item fa parte di Item Service nell'API repository per call quality dashboard.
  
## <a name="update-item"></a>Update Item

Update Item aggiorna un elemento specifico nel repository.
  

|**Metodo**|**URI richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|PUT  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** - Nessuno.
  
 **Request Headers** -Content-Type: application/json.
  
 **Request Body** - JSON.
  
Payload di richiesta di esempio:
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *contenuto*  Dati in formato JSON da archiviare come nuovo contenuto di un elemento secondario esistente. Tecnicamente, un repository può archiviare qualsiasi contenuto di qualsiasi schema, ma quando viene utilizzato per call quality dashboard, deve essere un report o una query. *type*  Specifica sempre "application/json" per Call Quality Dashboard.
  
 **Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato:** un'operazione riuscita restituisce il codice di stato 204 (Nessun contenuto). Se non viene trovato un ID elemento specificato, viene restituito il codice di stato 404 (Non trovato).
  
> [!IMPORTANT]
> "Nessun contenuto" non è uno stato di errore. Significa che una risposta non ha restituito nulla nel corpo (al contrario, 200 OK restituisce il contenuto in Body). Indica che l'elemento è stato aggiornato correttamente. 
  
 **Intestazioni risposta** - Nessuna.
  
 **Corpo risposta** - Nessuno.
  

