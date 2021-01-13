---
title: Ottenere impostazioni utente
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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: "Riepilogo: informazioni sull'operazione Get User Settings, che fa parte del servizio impostazioni utente. Il servizio impostazioni utente fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: e2ebf39ba5a7de5d36a8b1ea0441808b6e71f97b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832476"
---
# <a name="get-user-settings"></a>Ottenere impostazioni utente
 
**Riepilogo:** Informazioni sull'operazione Get User Settings, che fa parte del servizio impostazioni utente. Il servizio impostazioni utente fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Ottieni impostazioni utente fa parte del servizio impostazioni utente nell'API del repository per il dashboard qualità chiamata.
  
## <a name="get-user-settings"></a>Ottenere impostazioni utente

Ottenere le impostazioni utente restituisce un elenco di impostazioni per un utente specificato.
  

|**Metodo**|**URI della richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/User/{UserID}/setting  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI**
  
- *efficace*  -facoltativo. Questo parametro si applica solo quando viene utilizzato il valore predefinito dell'ID utente speciale. In altri casi, verrà ignorato. `True` restituisce impostazioni utente effettive e `false` restituisce solo le impostazioni utente (impostazione predefinita).
    
  **Intestazioni richieste** -nessuna intestazione aggiuntiva.
  
  **Corpo richiesta** -nessuno.
  
  **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
  **Codice di stato** -un'operazione completata restituisce il codice di stato 200 (OK).
  
  **Intestazioni di risposta** -Nessun intestazioni aggiuntive.
  
  **Corpo di risposta** -di seguito è riportato un payload di risposta di esempio in JSON.
  
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
