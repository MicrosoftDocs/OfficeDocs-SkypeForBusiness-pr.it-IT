---
title: Ottenere impostazione utente
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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: "Riepilogo: informazioni sull'operazione Get User Setting, che fa parte del servizio di Impostazioni utente. Il servizio di Impostazioni utente fa parte dell'API repository per il dashboard qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 5ea18a5ae5307bbf392796f95f7dcce8393371bdb8ddcfc192cb32d819494aa3
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298156"
---
# <a name="get-user-setting"></a>Ottenere impostazione utente
 
**Riepilogo:** Informazioni sull'operazione Ottieni impostazione utente, che fa parte del servizio Impostazioni utente. Il servizio di Impostazioni utente fa parte dell'API repository per il dashboard qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get User Setting fa parte del servizio di Impostazioni utente nell'API repository per il dashboard qualità delle chiamate.
  
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
  

