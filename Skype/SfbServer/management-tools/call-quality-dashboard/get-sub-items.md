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
description: "Riepilogo: informazioni sull'operazione Get Sub-Items, che fa parte del servizio elementi. Il servizio elementi fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: defb0b898c5101513cbb4f6da4382a8bb43bce6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832506"
---
# <a name="get-sub-items"></a>Get Sub-Items
 
**Riepilogo:** Informazioni sull'operazione Get Sub-Items, che fa parte del servizio elementi. Il servizio elementi fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Sub-Items fa parte del servizio elementi nell'API del repository per il dashboard qualità chiamata.
  
## <a name="get-sub-items"></a>Get Sub-Items

Get Sub-Items restituisce gli elementi secondari di un elemento specifico.
  

|**Metodo**|**URI della richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/Item/{ItemId}/SubItem  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** -None.
  
 **Intestazioni richieste** -nessuna intestazione aggiuntiva.
  
 **Corpo richiesta** -nessuno.
  
 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** -un'operazione completata restituisce il codice di stato 200 (OK). Se un ID utente specificato non viene trovato, restituisce il codice di stato 404 (non trovato).
  
 **Intestazioni di risposta** -Nessun intestazioni aggiuntive.
  
 **Corpo di risposta** -di seguito è riportato un payload di risposta di esempio in JSON.
  
> [!NOTE]
> Viene restituita una matrice di oggetto Item. 
  
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

L'oggetto Item restituito dall'operazione Sub-Items contiene solo i tre campi seguenti. 
  
 *ItemId*  -ID dell'elemento.
  
 *userid*  -ID dell'utente a cui appartiene questo elemento.
  
 *Type*  : il tipo di contenuto. Questo campo è impostato dalle applicazioni.
  
> [!NOTE]
>  `Content` e `subItems` i campi non sono inclusi nella risposta per ridurre la quantità di dati trasmessi sulla rete.
  

