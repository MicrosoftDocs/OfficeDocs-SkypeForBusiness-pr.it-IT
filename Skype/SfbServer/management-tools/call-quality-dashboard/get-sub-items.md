---
title: Get Sub-Items
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: "Riepilogo: informazioni sull'operazione Get Sub-Items, che fa parte di Item Service. Item Service fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: a1e439b9bfdfddf7009babbeb39a8175adc2a569
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851910"
---
# <a name="get-sub-items"></a>Get Sub-Items
 
**Riepilogo:** Informazioni sull'operazione Get Sub-Items, che fa parte di Item Service. Item Service fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Sub-Items fa parte di Item Service nell'API repository per il dashboard qualità delle chiamate.
  
## <a name="get-sub-items"></a>Get Sub-Items

Ottenere Sub-Items restituisce gli elementi secondari di un elemento specifico.
  

|**Metodo**|**URI richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}/subitem  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** - Nessuno.
  
 **Intestazioni richiesta** - Nessuna intestazione aggiuntiva.
  
 **Corpo della richiesta** - Nessuno.
  
 **Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato:** un'operazione riuscita restituisce il codice di stato 200 (OK). Se non viene trovato un ID utente specificato, viene restituito il codice di stato 404 (Non trovato).
  
 **Intestazioni di risposta** - Nessuna intestazione aggiuntiva.
  
 **Response Body:** di seguito è riportato un payload di risposta di esempio in JSON.
  
> [!NOTE]
> Viene restituita una matrice di oggetti Item. 
  
```json
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

L'oggetto Item restituito Sub-Items'operazione contiene solo i tre campi seguenti. 
  
 *itemId*  - ID dell'elemento.
  
 *userId*  - ID dell'utente proprietario dell'elemento.
  
 *type*  - Tipo del contenuto. Questo campo viene impostato dalle applicazioni.
  
> [!NOTE]
>  `Content` e i campi non sono inclusi nella risposta per ridurre la quantità di `subItems` dati trasmessi in rete.
  

