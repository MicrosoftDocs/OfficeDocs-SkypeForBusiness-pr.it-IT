---
title: Aggiorna elemento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: "Riepilogo: informazioni sull'operazione di aggiornamento degli elementi, che fa parte del servizio elemento. Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 460e6b26375bba28887d170c9827864bfc600138
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816675"
---
# <a name="update-item"></a>Aggiorna elemento
 
**Riepilogo:** Informazioni sull'operazione degli elementi di aggiornamento, che fa parte del servizio elemento. Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Update Item fa parte del servizio Item nell'API del repository per Call Quality dashboard.
  
## <a name="update-item"></a>Aggiorna elemento

Aggiorna elemento aggiorna un elemento specifico nel repository.
  

|**Metodo**|**URI di richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|INSERIRE  <br/> |/QoERepositoryService/repository/Item/{ItemId}\<portale\>https://  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** -None.
  
 **Richiedi intestazioni** -Content-Type: Application/JSON.
  
 **Richiedi Body** -JSON.
  
Esempio di richiesta payload:
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 *contenuto*  Dati formattati JSON da archiviare come nuovo contenuto di un elemento secondario esistente. Tecnicamente, un repository può archiviare qualsiasi contenuto di qualsiasi schema, ma se usato per il dashboard della qualità delle chiamate, dovrebbe essere un report o una query. *digitare*  Specifica sempre "application/json" per il dashboard della qualità delle chiamate.
  
 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** : un'operazione riuscita restituisce il codice di stato 204 (nessun contenuto). Se non viene trovato un ID elemento specificato, viene restituito il codice di stato 404 (non trovato).
  
> [!IMPORTANT]
> "Nessun contenuto" non è uno stato di errore. Significa che una risposta non ha restituito nulla nel corpo (al contrario, 200 OK restituisce il contenuto nel corpo). Indica che l'elemento è stato aggiornato correttamente. 
  
 **Intestazioni di risposta** -nessuna.
  
 **Corpo della risposta** -nessuno.
  

