---
title: Ottieni impostazioni utente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: "Riepilogo: informazioni sull'operazione Ottieni impostazioni utente, che fa parte del servizio impostazioni utente. Il servizio impostazioni utente fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 42934496b8b65132a67d4012d81d7b8997859726
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992633"
---
# <a name="get-user-settings"></a>Ottieni impostazioni utente
 
**Riepilogo:** Informazioni sull'operazione Ottieni impostazioni utente, che fa parte del servizio impostazioni utente. Il servizio impostazioni utente fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Ottieni impostazioni utente fa parte del servizio impostazioni utente nell'API del repository per il dashboard qualità chiamata.
  
## <a name="get-user-settings"></a>Ottieni impostazioni utente

Ottieni impostazioni utente restituisce un elenco di impostazioni per un utente specificato.
  

|**Metodo**|**URI di richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|Ottieni  <br/> |/QoERepositoryService/repository/User/{UserID}/setting\<portale\>https://  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI**
  
- *effettivi* -facoltativo. Questo parametro si applica solo quando viene usato l'ID utente speciale default. In altri casi verrà ignorato. `True`Restituisce le impostazioni utente effettive e `false` restituisce solo le impostazioni utente (impostazione predefinita).
    
  **Richiedi intestazioni** -nessuna intestazione aggiuntiva.
  
  **Richiedi corpo** -nessuno.
  
  **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
  **Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).
  
  **Intestazioni di risposta** -nessuna intestazione aggiuntiva.
  
  **Corpo risposta** : di seguito è riportato un payload di risposta di esempio in JSON.
  
```json
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```
