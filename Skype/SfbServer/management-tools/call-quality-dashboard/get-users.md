---
title: Get Users
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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: "Riepilogo: informazioni sull'operazione Get Users, che fa parte del servizio utente. Il servizio utente fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: a830663fc97d8fda727d1ebb008d97407796cc7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832426"
---
# <a name="get-users"></a>Get Users
 
**Riepilogo:** Informazioni sull'operazione Get Users, che fa parte del servizio utente. Il servizio utente fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Users fa parte del servizio utente nell'API del repository per il dashboard qualità chiamata.
  
## <a name="get-users"></a>Get Users

Ottenere gli utenti restituisce un elenco di utenti nel repository.
  
|**Metodo**|**URI della richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/User  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** -None.
  
 **Intestazioni richieste** -nessuna intestazione aggiuntiva.
  
 **Corpo richiesta** -nessuno.
  
 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** -un'operazione completata restituisce il codice di stato 200 (OK).
  
 **Intestazioni di risposta** -Nessun intestazioni aggiuntive.
  
 **Corpo di risposta** -di seguito è riportato un payload di risposta di esempio in JSON.
  
> [!NOTE]
> Viene restituita una matrice di oggetti User. Per informazioni dettagliate sull'oggetto utente, vedere Get User. 
  
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


