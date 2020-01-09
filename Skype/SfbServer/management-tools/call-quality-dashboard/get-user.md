---
title: Ottieni utente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: "Riepilogo: informazioni sull'operazione Get User, che fa parte del servizio utente. Il servizio utente fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 09dcbbaeaae98ed7b01f3d710cfda23aa5fa986f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992623"
---
# <a name="get-user"></a>Ottieni utente
 
**Riepilogo:** Informazioni sull'operazione Get User, che fa parte del servizio utente. Il servizio utente fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Users fa parte del servizio utente nell'API del repository per il dashboard della qualità delle chiamate.
  
## <a name="get-user"></a>Ottieni utente

Get User restituisce un record utente dal repository.
  
|**Metodo**|**URI di richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|Ottieni  <br/> |/QoERepositoryService/repository/User/{UserID}\<portale\>https://  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** -None.
  
 **Richiedi intestazioni** -nessuna intestazione aggiuntiva.
  
 **Richiedi corpo** -nessuno.
  
 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK). Se non viene trovato un ID utente specificato, viene restituito il codice di stato 404 (non trovato).
  
 **Intestazioni di risposta** -nessuna intestazione aggiuntiva.
  
 **Corpo risposta** : di seguito è riportato un payload di risposta di esempio in JSON.
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 *userid* -ID dell'utente.
  
 *LoginName* -Identificativo utente esterno per utenti regolari. Se l'autenticazione di Windows viene usata per l'autenticazione degli utenti, può trattarsi di un nome di dominio completo dell'utente.
  
 *defaultItemId* -ID dell'elemento predefinito per l'utente. L'elemento predefinito è l'elemento in primo piano associato all'utente. Tutti gli altri elementi posseduti dall'utente possono essere spostati dall'elemento predefinito.
  
> [!NOTE]
> Fornisci il `defaultItemId` valore per ottenere l'operazione Item per recuperare i dettagli dell'elemento predefinito.
  

