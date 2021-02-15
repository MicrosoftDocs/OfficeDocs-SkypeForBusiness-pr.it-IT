---
title: Get Sub-Items
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: "Riepilogo: informazioni sull'operazione Get Sub-Items, che fa parte di Item Service. Item Service fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: defb0b898c5101513cbb4f6da4382a8bb43bce6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832506"
---
# <a name="get-sub-items"></a>Get Sub-Items
 
**Riepilogo:** Informazioni sull'operazione Get Sub-Items, che fa parte di Item Service. Item Service fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Sub-Items fa parte di Item Service nell'API repository per call quality dashboard.
  
## <a name="get-sub-items"></a>Get Sub-Items

Ottiene Sub-Items gli elementi secondari di un elemento specifico.
  

|**Metodo**|**URI richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/item/{itemId}/subitem  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** - Nessuno.
  
 **Intestazioni richiesta** - Nessuna intestazione aggiuntiva.
  
 **Corpo della richiesta** - Nessuno.
  
 **Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato:** un'operazione riuscita restituisce il codice di stato 200 (OK). Se non viene trovato un ID utente specificato, viene restituito il codice di stato 404 (Non trovato).
  
 **Intestazioni risposta** - Nessuna intestazione aggiuntiva.
  
 **Contenuto della risposta:** di seguito è riportato un payload di risposta di esempio in JSON.
  
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
  
 *type*  - Tipo di contenuto. Questo campo viene impostato dalle applicazioni.
  
> [!NOTE]
>  `Content` e i campi non sono inclusi nella risposta per ridurre la quantità di dati `subItems` trasmessi in rete.
  

