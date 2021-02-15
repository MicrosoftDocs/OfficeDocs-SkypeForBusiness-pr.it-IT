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
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: "Riepilogo: informazioni sull'operazione Get User, che fa parte del servizio utente. Il servizio utente fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: dd2bb5e46ddbe3e65faf441a11e39cbc5429e473
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832416"
---
# <a name="get-user"></a>Get User
 
**Riepilogo:** Informazioni sull'operazione Get User, che fa parte del servizio utente. Il servizio utente fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Users fa parte del servizio utente nell'API repository per call quality dashboard.
  
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
  
 **Intestazioni risposta** - Nessuna intestazione aggiuntiva.
  
 **Contenuto della risposta:** di seguito è riportato un payload di risposta di esempio in JSON.
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userId*  - ID dell'utente.
  
 *loginName*  - Identificazione utente esterna per gli utenti normali. Se per l'autenticazione degli utenti viene utilizzata l'autenticazione di Windows, può trattarsi di un FQDN dell'utente.
  
 *defaultItemId*  - ID dell'elemento predefinito per questo utente. L'elemento predefinito è l'elemento più in alto associato all'utente. Tutti gli altri elementi di cui l'utente è proprietario possono essere spostati dall'elemento predefinito.
  
> [!NOTE]
> Specifica il  `defaultItemId` valore dell'operazione Get Item per recuperare i dettagli dell'elemento predefinito.
  

