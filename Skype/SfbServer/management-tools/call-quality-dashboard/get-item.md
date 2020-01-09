---
title: Ottieni elemento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: "Riepilogo: informazioni sull'operazione Get Item, che fa parte del servizio Item. Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 208ad3d1852ab58b7fcd0d01eeb440097328f733
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992673"
---
# <a name="get-item"></a>Ottieni elemento
 
**Riepilogo:** Informazioni sull'operazione Get Item, che fa parte del servizio Item. Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Item fa parte del servizio Item nell'API del repository per Call Quality dashboard.
  
## <a name="get-item"></a>Ottieni elemento

Get Item restituisce un elemento specifico nel repository.
  
|**Metodo**|**URI di richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|Ottieni  <br/> |/QoERepositoryService/repository/Item/{ItemId}\<portale\>https://  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** -None.
  
 **Richiedi intestazioni** -nessuna intestazione aggiuntiva.
  
 **Richiedi corpo** -nessuno.
  
 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK). Se non viene trovato un ID elemento specificato, viene restituito il codice di stato 404 (non trovato).
  
 **Intestazioni di risposta** -nessuna intestazione aggiuntiva.
  
 **Corpo risposta** : di seguito è riportato un payload di risposta di esempio in JSON.
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 ID *ItemId* dell'elemento.
  
 *userid* -ID dell'utente proprietario di questo elemento.
  
 *contenuto* : contenuto specifico dell'applicazione.
  
 *tipo* : il tipo di contenuto. Questo campo è impostato dalle applicazioni.
  
 *Subitemids* -gli ID degli elementi secondari, se presenti. Si tratta di un cortocircuito dell'operazione Get Sub-Items per salvare una chiamata. Le applicazioni possono ottenere in alternativa le stesse informazioni utilizzando l'operazione Get Sub-Items.
  

