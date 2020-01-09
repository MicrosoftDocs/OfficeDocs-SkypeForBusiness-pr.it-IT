---
title: Ottieni impostazione utente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: "Riepilogo: informazioni sull'operazione Get User setting, che fa parte del servizio impostazioni utente. Il servizio impostazioni utente fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 168e61aaebb47cb087e77cbd18e3e6edfd987227
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992643"
---
# <a name="get-user-setting"></a>Ottieni impostazione utente
 
**Riepilogo:** Informazioni sull'operazione Get User setting, che fa parte del servizio impostazioni utente. Il servizio impostazioni utente fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get User Setting fa parte del servizio impostazioni utente nell'API del repository per Call Quality dashboard.
  
## <a name="get-user-setting"></a>Ottieni impostazione utente

Per ottenere l'impostazione utente viene restituita una singola impostazione utente.
  

|**Metodo**|**URI di richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|Ottieni  <br/> |/QoERepositoryService/repository/User/{UserID}/setting/{Key}\<portale\>https://  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** -None.
  
 **Richiedi intestazioni** -nessuna intestazione aggiuntiva.
  
 **Richiedi corpo** -nessuno.
  
 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).
  
 **Intestazioni di risposta** -nessuna intestazione aggiuntiva.
  
 **Corpo risposta** : di seguito è riportato un payload di risposta di esempio in JSON.
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 *userid* -ID dell'utente.
  
 tasto *chiave* dell'impostazione.
  
 *valore-valore* dell'impostazione.
  

