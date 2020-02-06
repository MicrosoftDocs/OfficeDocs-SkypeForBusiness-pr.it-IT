---
title: Ottieni predecessori elemento
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
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: "Riepilogo: informazioni sull'operazione Ottieni antenati elemento, che fa parte del servizio elemento. Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 7beaffbb670f664ec7181482dbceb120a8b7d9e8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816805"
---
# <a name="get-item-ancestors"></a>Ottieni predecessori elemento
 
**Riepilogo:** Informazioni sull'operazione Ottieni antenati elemento, che fa parte del servizio elemento. Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Ottieni antenati elemento fa parte del servizio elemento nell'API del repository per Call Quality dashboard.
  
## <a name="get-item-ancestors"></a>Ottieni predecessori elemento

Ottenere gli antenati degli elementi restituisce un elemento specifico antenati dal repository.
  

|**Metodo**|**URI di richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|Ottieni  <br/> |/QoERepositoryService/repository/itemAncestors/{ItemId}\<portale\>https://  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** -None.
  
 **Richiedi intestazioni** -nessuna intestazione aggiuntiva.
  
 **Richiedi corpo** -nessuno.
  
 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK). Se non viene trovato un ID utente specificato, viene restituito il codice di stato 404 (non trovato).
  
 **Intestazioni di risposta** -nessuna intestazione aggiuntiva.
  
 **Corpo risposta** : di seguito è riportato un payload di risposta di esempio in JSON.
  
```json
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 *Item1* -ID dell'elemento.
  
 *Item2* -Depth è la distanza dall'elemento. 0 è l'elemento padre immediato.
  
 *Item3* -titolo dell'elemento.
  

