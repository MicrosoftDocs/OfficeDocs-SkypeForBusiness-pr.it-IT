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
description: "Riepilogo: informazioni sull'operazione Get User setting, che fa parte del servizio impostazioni utente. Il servizio impostazioni utente fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 82632f5de7ae215d6f34d9f0b39e500fb713a1be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832486"
---
# <a name="get-user-setting"></a>Ottenere impostazione utente
 
**Riepilogo:** Informazioni sull'operazione Get User setting, che fa parte del servizio impostazioni utente. Il servizio impostazioni utente fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get User Setting fa parte del servizio impostazioni utente nell'API del repository per il dashboard qualità chiamata.
  
## <a name="get-user-setting"></a>Ottenere impostazione utente

Ottenere l'impostazione utente restituisce una singola impostazione utente.
  

|**Metodo**|**URI della richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/User/{UserID}/setting/{Key}  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** -None.
  
 **Intestazioni richieste** -nessuna intestazione aggiuntiva.
  
 **Corpo richiesta** -nessuno.
  
 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** -un'operazione completata restituisce il codice di stato 200 (OK).
  
 **Intestazioni di risposta** -Nessun intestazioni aggiuntive.
  
 **Corpo di risposta** -di seguito è riportato un payload di risposta di esempio in JSON.
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userid*  -ID dell'utente.
  
 tasto *chiave* dell'impostazione.
  
 *valore-valore*  dell'impostazione.
  

