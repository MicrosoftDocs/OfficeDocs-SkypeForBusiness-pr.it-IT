---
title: Get Users
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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: 'Riepilogo: informazioni sull''operazione Get Users, che fa parte del servizio utente. Il servizio utente fa parte dell''API repository per il dashboard di qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server.'
---

# <a name="get-users"></a>Get Users
 
**Riepilogo:** Informazioni sull'operazione Get Users, che fa parte del servizio utente. Il servizio utente fa parte dell'API repository per il dashboard di qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Users fa parte del servizio utente nell'API repository per il dashboard qualità delle chiamate.
  
## <a name="get-users"></a>Get Users

Get Users restituisce un elenco di utenti nel repository.
  
|**Metodo**|**URI richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |\<portal\>https:///QoERepositoryService/repository/user  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** - Nessuno.
  
 **Intestazioni richiesta** - Nessuna intestazione aggiuntiva.
  
 **Corpo della richiesta** - Nessuno.
  
 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).
  
 **Intestazioni di risposta** - Nessuna intestazione aggiuntiva.
  
 **Response Body** : di seguito è riportato un payload di risposta di esempio in JSON.
  
> [!NOTE]
> Viene restituita una matrice di oggetti User. Per informazioni dettagliate sull'oggetto User, vedere Get User. 
  
```json
[{
"userId": 0,
"loginName": "system",
"defaultItemId": 1652
},
{
"userId": 1,
"loginName": "SAMPLEDOMAIN\\testuser1",
"defaultItemId": 1652
},
{
"userId": 2,
"loginName": "SAMPLEDOMAIN\\testuser2",
"defaultItemId": 1774
}]
```


