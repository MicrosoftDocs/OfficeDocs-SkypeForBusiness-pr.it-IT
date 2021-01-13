---
title: Get Item
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
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: "Riepilogo: informazioni sull'operazione Get Item, che fa parte del servizio elementi. Il servizio elementi fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 896540c4572fb3991356ce055f01690ed702c6f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832566"
---
# <a name="get-item"></a>Get Item
 
**Riepilogo:** Informazioni sull'operazione Get Item, che fa parte del servizio elementi. Il servizio elementi fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Item fa parte del servizio elementi nell'API del repository per il dashboard qualità chiamata.
  
## <a name="get-item"></a>Get Item

L'elemento Get restituisce un elemento specifico nel repository.
  
|**Metodo**|**URI della richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/Item/{ItemId}  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** -None.
  
 **Intestazioni richieste** -nessuna intestazione aggiuntiva.
  
 **Corpo richiesta** -nessuno.
  
 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** -un'operazione completata restituisce il codice di stato 200 (OK). Se un ID elemento specificato non viene trovato, restituisce il codice di stato 404 (non trovato).
  
 **Intestazioni di risposta** -Nessun intestazioni aggiuntive.
  
 **Corpo di risposta** -di seguito è riportato un payload di risposta di esempio in JSON.
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 *ItemId*  -ID dell'elemento.
  
 *userid*  -ID dell'utente a cui appartiene questo elemento.
  
 *Content*  : contenuto specifico dell'applicazione.
  
 *Type*  : il tipo di contenuto. Questo campo è impostato dalle applicazioni.
  
 *Subitemids*  -ID degli elementi secondari, se presenti. Si tratta di un cortocircuito di Get Sub-Items Operation per salvare una chiamata. Le applicazioni possono, in alternativa, ottenere le stesse informazioni utilizzando l'operazione Get Sub-Items.
  

