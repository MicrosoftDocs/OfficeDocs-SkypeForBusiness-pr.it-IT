---
title: Ottenere gli antenati degli elementi
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: "Riepilogo: informazioni sull'operazione Ottieni antenati elemento, che fa parte del servizio elemento. Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 77fb5f46ada278bcb172a51620317182fe5d61b0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186941"
---
# <a name="get-item-ancestors"></a>Ottenere gli antenati degli elementi
 
**Riepilogo:** Informazioni sull'operazione Ottieni antenati elemento, che fa parte del servizio elemento. Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Ottieni antenati elemento fa parte del servizio elemento nell'API del repository per Call Quality dashboard.
  
## <a name="get-item-ancestors"></a>Ottenere gli antenati degli elementi

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
  
```
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
  

