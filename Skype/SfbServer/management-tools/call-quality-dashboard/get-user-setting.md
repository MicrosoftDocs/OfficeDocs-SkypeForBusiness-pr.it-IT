---
title: Ottenere impostazione utente
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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: "Riepilogo: informazioni sull'operazione Get User Setting, che fa parte del servizio Impostazioni utente. Il servizio di Impostazioni utente fa parte dell'API repository per il dashboard qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 2be81d09c45a93c967af2556ba7ed8fbca9ce0f9
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774626"
---
# <a name="get-user-setting"></a>Ottenere impostazione utente
 
**Riepilogo:** Informazioni sull'operazione Ottieni impostazione utente, che fa parte del servizio Impostazioni utente. Il servizio di Impostazioni utente fa parte dell'API repository per il dashboard qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'operazione Ottieni impostazione utente fa parte del servizio di Impostazioni utente nell'API repository per il dashboard qualità delle chiamate.
  
## <a name="get-user-setting"></a>Ottenere impostazione utente

Get User Setting restituisce un'impostazione utente singola.
  

|**Metodo**|**URI richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** - Nessuno.
  
 **Intestazioni richiesta** - Nessuna intestazione aggiuntiva.
  
 **Corpo della richiesta** - Nessuno.
  
 **Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato:** un'operazione riuscita restituisce il codice di stato 200 (OK).
  
 **Intestazioni di risposta** - Nessuna intestazione aggiuntiva.
  
 **Response Body:** di seguito è riportato un payload di risposta di esempio in JSON.
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userId*  - ID dell'utente.
  
 *key*  - Chiave dell'impostazione.
  
 *value*  - Valore dell'impostazione.
  

