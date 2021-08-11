---
title: Get Item Ancestors
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
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: "Riepilogo: informazioni sull'operazione Get Item Ancestors, che fa parte di Item Service. Item Service fa parte dell'API repository per il dashboard di qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: bb756e35ff835d889ef8d8c8f613529ab7d6a5c08de339fe7892779921367997
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54278654"
---
# <a name="get-item-ancestors"></a>Get Item Ancestors
 
**Riepilogo:** Informazioni sull'operazione Get Item Ancestors, che fa parte di Item Service. Item Service fa parte dell'API repository per il dashboard di qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Item Ancestors fa parte di Item Service nell'API repository per il dashboard qualità delle chiamate.
  
## <a name="get-item-ancestors"></a>Get Item Ancestors

Get Item Ancestors restituisce un predecessore di elementi specifici dal repository.
  

|**Metodo**|**URI richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/itemAncestors/{itemId}  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** - Nessuno.
  
 **Intestazioni richiesta** - Nessuna intestazione aggiuntiva.
  
 **Corpo della richiesta** - Nessuno.
  
 **Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato:** un'operazione riuscita restituisce il codice di stato 200 (OK). Se non viene trovato un ID utente specificato, viene restituito il codice di stato 404 (Non trovato).
  
 **Intestazioni di risposta** - Nessuna intestazione aggiuntiva.
  
 **Response Body:** di seguito è riportato un payload di risposta di esempio in JSON.
  
```json
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 *Item1*  - ID dell'elemento.
  
 *Item2*  - Depth è la distanza dall'oggetto Item. 0 è l'elemento padre immediato.
  
 *Item3*  - Titolo dell'elemento.
  

