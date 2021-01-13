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
description: "Riepilogo: informazioni su come ottenere l'operazione utente, che fa parte del servizio utente. Il servizio utente fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: dd2bb5e46ddbe3e65faf441a11e39cbc5429e473
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832416"
---
# <a name="get-user"></a>Get User
 
**Riepilogo:** Informazioni sull'operazione Get utente, che fa parte del servizio utente. Il servizio utente fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Users fa parte del servizio utente nell'API del repository per il dashboard qualità chiamata.
  
## <a name="get-user"></a>Get User

Get utente restituisce un record utente dall'archivio.
  
|**Metodo**|**URI della richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoERepositoryService/repository/User/{UserID}  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** -None.
  
 **Intestazioni richieste** -nessuna intestazione aggiuntiva.
  
 **Corpo richiesta** -nessuno.
  
 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** -un'operazione completata restituisce il codice di stato 200 (OK). Se un ID utente specificato non viene trovato, restituisce il codice di stato 404 (non trovato).
  
 **Intestazioni di risposta** -Nessun intestazioni aggiuntive.
  
 **Corpo di risposta** -di seguito è riportato un payload di risposta di esempio in JSON.
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userid*  -ID dell'utente.
  
 *LoginName*  -identificazione utente esterno per utenti normali. Se viene utilizzata l'autenticazione di Windows per l'autenticazione degli utenti, può trattarsi di un nome di dominio completo dell'utente.
  
 *defaultItemId*  -ID dell'elemento predefinito per questo utente. L'elemento predefinito è l'elemento più in alto associato all'utente. Tutti gli altri elementi posseduti dall'utente possono essere spostati dall'elemento predefinito.
  
> [!NOTE]
> Specificare il  `defaultItemId` valore per ottenere l'operazione sugli elementi per recuperare i dettagli dell'elemento predefinito.
  

