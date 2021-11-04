---
title: Get Cube
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: "Riepilogo: informazioni sull'operazione Get Cube, che fa parte dell'API dati per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: bb5edc6bba4c374600845d18c371332a62a6085e
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60739152"
---
# <a name="get-cube"></a>Get Cube
 
**Riepilogo:** Informazioni sull'operazione Get Cube, che fa parte dell'API dati per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Cube fa parte dell'API dei dati per call quality dashboard.
  
## <a name="get-cube"></a>Get Cube

L'operazione Get Cube restituisce l'elenco delle dimensioni e delle misure disponibili.
  

|**Metodo**|**URI richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|GET  <br/> |https:// \<portal\> /QoEDataService/CubeStructure  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** - Nessuno.
  
 **Intestazioni richiesta** - Nessuna intestazione aggiuntiva.
  
 **Corpo della richiesta** - Nessuno.
  
 **Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato:** un'operazione riuscita restituisce il codice di stato 200 (OK).
  
 **Intestazioni di risposta** - Nessuna intestazione aggiuntiva.
  
 **Response Body:** di seguito è riportato un payload di risposta di esempio in JSON.
  
> [!NOTE]
> In questo esempio vengono mostrati solo i primi due elementi di ogni gruppo di elementi Cube. 
  
```json
{
"Kpis": [{
"FriendlyName": "Poor Trend Month",
"DataModelName": "[KPIValue].Poor Trend Month",
"Description": null
},
{
"FriendlyName": "Poor Rate Trend Month",
"DataModelName": "[KPIValue].Poor Rate Trend Month",
"Description": null
}],
"Dimensions": [{
"Category": "Access Location Pair",
"Attributes": [{
"FriendlyName": "Location Pair",
"DataModelName": "[Access Location Pair].[Location Pair]",
"Description": "Description of Location Pair"
}]
},
{
"Category": "Audio Bandwidth Est",
"Attributes": [{
"FriendlyName": "Metric",
"DataModelName": "[Audio Bandwidth Est].[Metric]",
"Description": "Description of Metric"
}]
}],
"Measurements": [{
"FriendlyName": "Audio Streams Count",
"DataModelName": "[Measures].[Audio Streams Count]",
"Description": "Description of Audio Streams Count"
},
{
"FriendlyName": "Audio Good Streams JPDR Count",
"DataModelName": "[Measures].[Audio Good Streams JPDR Count]",
"Description": "Description of Audio Good Streams JPDR Count"
}]
}
```

 *INDICATORI KPI*  - Riservato. La sezione INDICATORI KPI di un payload di richiesta consente all'operazione Esegui query di restituire valori per gli indicatori KPI definiti nel cubo. Nel cubo QoE non sono ancora presenti indicatori KPI.
  
 *Dimensioni:*  elenco di dimensioni che possono essere utilizzate nelle sezioni Filtri e Dimensioni di un payload di richiesta per l'operazione Esegui query. Per utilizzare una dimensione in un'espressione di filtro, è necessario specificare un membro della dimensione, che può essere ottenuto utilizzando l'operazione Get Dimension Members.
  
 *Misurazioni:*  elenco delle misurazioni che possono essere utilizzate nella sezione Misurazioni di un payload di richiesta per l'operazione Esegui query.
  

