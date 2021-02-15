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
description: "Riepilogo: informazioni sull'operazione Ottieni impostazioni utente, che fa parte del servizio impostazioni utente. Il servizio impostazioni utente fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: e2ebf39ba5a7de5d36a8b1ea0441808b6e71f97b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832476"
---
# <a name="get-user-settings"></a>Ottenere impostazioni utente
 
**Riepilogo:** Informazioni sull'operazione Ottieni impostazioni utente, che fa parte del servizio impostazioni utente. Il servizio impostazioni utente fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get User Settings fa parte del servizio impostazioni utente nell'API repository per call quality dashboard.
  
## <a name="get-user-settings"></a>Ottenere impostazioni utente

Ottieni impostazioni utente restituisce un elenco di impostazioni per un utente specificato.
  

|**Metodo**|**URI richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI**
  
- *effective*  - Facoltativo. Questo parametro si applica solo quando viene utilizzato l'ID utente speciale predefinito. In altri casi, verrà ignorato. `True` restituisce le impostazioni utente effettive `false` e restituisce solo le impostazioni utente (impostazione predefinita).
    
  **Intestazioni richiesta** - Nessuna intestazione aggiuntiva.
  
  **Corpo della richiesta** - Nessuno.
  
  **Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
  **Codice di stato:** un'operazione riuscita restituisce il codice di stato 200 (OK).
  
  **Intestazioni risposta** - Nessuna intestazione aggiuntiva.
  
  **Contenuto della risposta:** di seguito è riportato un payload di risposta di esempio in JSON.
  
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
