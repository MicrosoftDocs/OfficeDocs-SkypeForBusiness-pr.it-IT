---
title: Get Dimension Members
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
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: "Riepilogo: informazioni sull'operazione get Members Dimension. L'operazione get Members Dimension fa parte dell'API Data per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 40e5ac8b95c24c3a8cb759da99f7d7aeaa391576
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888815"
---
# <a name="get-dimension-members"></a>Get Dimension Members
 
**Riepilogo:** Informazioni sull'operazione get Members Dimension. L'operazione get Members Dimension fa parte dell'API Data per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione get Members Dimension fa parte dell'API Data per il dashboard della qualità delle chiamate.
  
## <a name="get-dimension-members"></a>Get Dimension Members

L'operazione get Members Dimension restituisce l'elenco dei membri di una dimensione specifica. È anche possibile filtrare l'elenco dei membri e ottenere un sottoinsieme, per ridurre il costo del bonifico bancario.
  

|**Metodo**|**URI di richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|Inserisci  <br/> |/QoEDataService/DimensionMembers\<portale\>https://  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** -None.
  
 **Richiedi intestazioni** -nessuna intestazione aggiuntiva.
  
 **Richiedi corpo** : contiene il nome della dimensione per cui desideriamo i membri. Anche il numero massimo di membri restituiti, accanto a puoi specificare alcuni filtri per limitare i membri restituiti.
  
```json
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).
  
 **Intestazioni di risposta** -nessuna intestazione aggiuntiva.
  
 **Corpo della risposta** : di seguito è riportato un payload di risposta di esempio in JSON in risposta a una richiesta di "[StartDate]. [Month] "Dimension.
  
> [!NOTE]
> L'elenco Mostra solo una piccola parte dell'elenco. 
  
```json
{
"MembersCount": 493,
"Members": [["[1990-01-01T00:00:00]",
"January 1990"],
["[1990-02-01T00:00:00]",
"February 1990"],
["[1990-03-01T00:00:00]",
"March 1990"],
 
    ...
    
["[2030-10-01T00:00:00]",
"October 2030"],
["[2030-11-01T00:00:00]",
"November 2030"],
["[2030-12-01T00:00:00]",
"December 2030"],
["[2031-01-01T00:00:00]",
"January 2031"]]
}
```
