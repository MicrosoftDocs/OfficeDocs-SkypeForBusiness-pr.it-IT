---
title: Ottieni elementi secondari
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: "Riepilogo: informazioni sull'operazione Get Sub-Items, che fa parte del servizio Item. Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 75fc4fcd331925c224d8dfb72c681d25e3485eb6
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992653"
---
# <a name="get-sub-items"></a>Ottieni elementi secondari
 
**Riepilogo:** Informazioni sull'operazione Get Sub-Items, che fa parte del servizio Item. Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Sub-Items fa parte del servizio Item nell'API del repository per Call Quality dashboard.
  
## <a name="get-sub-items"></a>Ottieni elementi secondari

Get Sub-Items restituisce gli elementi secondari di un elemento specifico.
  

|**Metodo**|**URI di richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|Ottieni  <br/> |/QoERepositoryService/repository/Item/{ItemId}/SubItem\<portale\>https://  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** -None.
  
 **Richiedi intestazioni** -nessuna intestazione aggiuntiva.
  
 **Richiedi corpo** -nessuno.
  
 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK). Se non viene trovato un ID utente specificato, viene restituito il codice di stato 404 (non trovato).
  
 **Intestazioni di risposta** -nessuna intestazione aggiuntiva.
  
 **Corpo risposta** : di seguito è riportato un payload di risposta di esempio in JSON.
  
> [!NOTE]
> Viene restituita una matrice di oggetto Item. 
  
```json
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

L'oggetto Item restituito dall'operazione elementi secondari contiene solo i tre campi seguenti. 
  
 ID *ItemId* dell'elemento.
  
 *userid* -ID dell'utente proprietario di questo elemento.
  
 *tipo* : il tipo di contenuto. Questo campo è impostato dalle applicazioni.
  
> [!NOTE]
>  `Content`e `subItems` i campi non sono inclusi nella risposta per ridurre la quantità di dati trasmessi tramite la rete.
  

