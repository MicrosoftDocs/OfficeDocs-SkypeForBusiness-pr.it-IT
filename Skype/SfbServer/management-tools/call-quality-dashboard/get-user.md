---
title: Get User
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: "Riepilogo: informazioni sull'operazione Get User, che fa parte del servizio utente. Il servizio utente fa parte dell'API repository per il dashboard di qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 31dd511cedc6a9ebe606a2594ca3df0dfae2277c
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58629588"
---
# <a name="get-user"></a>Get User
 
**Riepilogo:** Informazioni sull'operazione Get User, che fa parte del servizio utente. Il servizio utente fa parte dell'API repository per il dashboard di qualità delle chiamate. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Users fa parte del servizio utente nell'API repository per il dashboard qualità delle chiamate.
  
## <a name="get-user"></a>Get User

Get User restituisce un record utente dal repository.
  
|**Metodo**|**URI richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/user/{userId}  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** - Nessuno.
  
 **Intestazioni richiesta** - Nessuna intestazione aggiuntiva.
  
 **Corpo della richiesta** - Nessuno.
  
 **Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato:** un'operazione riuscita restituisce il codice di stato 200 (OK). Se non viene trovato un ID utente specificato, viene restituito il codice di stato 404 (Non trovato).
  
 **Intestazioni di risposta** - Nessuna intestazione aggiuntiva.
  
 **Response Body:** di seguito è riportato un payload di risposta di esempio in JSON.
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userId*  - ID dell'utente.
  
 *loginName*  - Identificazione dell'utente esterno per gli utenti normali. Se Windows'autenticazione viene utilizzata per autenticare gli utenti, potrebbe trattarsi di un FQDN dell'utente.
  
 *defaultItemId*  - ID dell'elemento predefinito per questo utente. L'elemento predefinito è l'elemento più in alto associato all'utente. Tutti gli altri elementi di cui l'utente è proprietario possono essere spostati dall'elemento predefinito.
  
> [!NOTE]
> Specifica il  `defaultItemId` valore dell'operazione Get Item per recuperare i dettagli dell'oggetto Item predefinito.
  

