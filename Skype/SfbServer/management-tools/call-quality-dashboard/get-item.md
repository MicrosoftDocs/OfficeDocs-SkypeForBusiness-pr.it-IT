---
title: Get Item
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: "Riepilogo: informazioni sull'operazione Get Item, che fa parte di Item Service. Item Service fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 3ee8d4f4e64276f7b824bfbdaa06247b27c78988
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60762314"
---
# <a name="get-item"></a>Get Item
 
**Riepilogo:** Informazioni sull'operazione Get Item, che fa parte di Item Service. Item Service fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Item fa parte di Item Service nell'API repository per call quality dashboard.
  
## <a name="get-item"></a>Get Item

Get Item restituisce un elemento specifico nel repository.
  
|**Metodo**|**URI richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** - Nessuno.
  
 **Intestazioni richiesta** - Nessuna intestazione aggiuntiva.
  
 **Corpo della richiesta** - Nessuno.
  
 **Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato:** un'operazione riuscita restituisce il codice di stato 200 (OK). Se non viene trovato un ID elemento specificato, viene restituito il codice di stato 404 (Non trovato).
  
 **Intestazioni di risposta** - Nessuna intestazione aggiuntiva.
  
 **Response Body:** di seguito è riportato un payload di risposta di esempio in JSON.
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 *itemId*  - ID dell'elemento.
  
 *userId*  - ID dell'utente proprietario dell'elemento.
  
 *content*  - Contenuto specifico dell'applicazione.
  
 *type*  - Tipo del contenuto. Questo campo viene impostato dalle applicazioni.
  
 *subItemIds*  - ID degli eventuali elementi secondari. Si tratta di un corto circuito dell'operazione Get Sub-Items per salvare una chiamata. In alternativa, le applicazioni possono ottenere le stesse informazioni utilizzando l'operazione Get Sub-Items.
  

