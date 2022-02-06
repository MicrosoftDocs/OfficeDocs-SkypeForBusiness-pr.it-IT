---
title: Ottenere impostazioni utente
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: 'Riepilogo: informazioni sull''operazione Get User Impostazioni, che fa parte del servizio di Impostazioni utente. Il servizio di Impostazioni utente fa parte dell''API repository per il dashboard qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server.'
---

# <a name="get-user-settings"></a>Ottenere impostazioni utente
 
**Riepilogo:** Informazioni sull'operazione Get User Impostazioni, che fa parte del servizio di Impostazioni utente. Il servizio di Impostazioni utente fa parte dell'API repository per il dashboard qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get User Impostazioni fa parte del servizio di Impostazioni utente nell'API repository per il dashboard qualità delle chiamate.
  
## <a name="get-user-settings"></a>Ottenere impostazioni utente

Get User Impostazioni restituisce un elenco di impostazioni per un utente specificato.
  

|**Metodo**|**URI richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |\<portal\>https:///QoERepositoryService/repository/user/{userId}/setting  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI**
  
- *effective*  - Facoltativo. Questo parametro si applica solo quando viene utilizzato l'ID utente speciale predefinito. In altri casi, verrà ignorato. `True` restituisce le impostazioni utente effettive e `false` restituisce solo le impostazioni utente (impostazione predefinita).
    
  **Intestazioni richiesta** - Nessuna intestazione aggiuntiva.
  
  **Corpo della richiesta** - Nessuno.
  
  **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
  **Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).
  
  **Intestazioni di risposta** - Nessuna intestazione aggiuntiva.
  
  **Response Body** : di seguito è riportato un payload di risposta di esempio in JSON.
  
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
