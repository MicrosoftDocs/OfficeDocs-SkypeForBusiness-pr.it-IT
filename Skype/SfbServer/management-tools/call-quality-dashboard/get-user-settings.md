---
title: Ottenere le impostazioni utente
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
ms.openlocfilehash: 8d1bb1da9e9a186cbc10f0c8ba36275348bb7267
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186893"
---
# <a name="get-user-settings"></a>Ottenere le impostazioni utente
 
**Riepilogo:** Informazioni sull'operazione Ottieni impostazioni utente, che fa parte del servizio impostazioni utente. Il servizio impostazioni utente fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Ottieni impostazioni utente fa parte del servizio impostazioni utente nell'API del repository per il dashboard qualità chiamata.
  
## <a name="get-user-settings"></a>Ottenere le impostazioni utente

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
  
```
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
