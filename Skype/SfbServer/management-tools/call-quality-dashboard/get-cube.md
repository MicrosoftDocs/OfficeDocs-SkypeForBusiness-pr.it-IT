---
title: Get Cube
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: "Riepilogo: informazioni sull'operazione Get Cube, che fa parte dell'API dati per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 7ae24309ea49d8f7d8d2684c141adb44c5bff2b5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816835"
---
# <a name="get-cube"></a>Get Cube
 
**Riepilogo:** Informazioni sull'operazione Get Cube, che fa parte dell'API dati per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server.
  
L'operazione Get Cube fa parte dell'API Data per il dashboard della qualità delle chiamate.
  
## <a name="get-cube"></a>Get Cube

L'operazione Get CUBE restituisce l'elenco delle dimensioni e delle misure disponibili.
  

|**Metodo**|**URI di richiesta**|**Versione HTTP**|
|:-----|:-----|:-----|
|Ottieni  <br/> |/QoEDataService/CubeStructure\<portale\>https://  <br/> |HTTP/1.1  <br/> |
   
 **Parametri URI** -None.
  
 **Richiedi intestazioni** -nessuna intestazione aggiuntiva.
  
 **Richiedi corpo** -nessuno.
  
 **Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.
  
 **Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).
  
 **Intestazioni di risposta** -nessuna intestazione aggiuntiva.
  
 **Corpo risposta** : di seguito è riportato un payload di risposta di esempio in JSON.
  
> [!NOTE]
> Questo esempio Mostra solo i primi due elementi di ogni gruppo di elementi Cube. 
  
```
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

 *Indicatori KPI* -riservati. La sezione KPI di un payload di richiesta consente l'esecuzione di operazioni di query per restituire valori per i KPI definiti nel cubo. Nel cubo QoE non esistono ancora indicatori KPI.
  
 *Dimensions* -l'elenco di dimensioni che possono essere usate in filtri e dimensioni sezioni di un payload di richiesta per l'operazione di esecuzione della query. Per usare una dimensione in un'espressione di filtro, devi specificare un membro della dimensione, che può essere ottenuto usando l'operazione membri della dimensione Get.
  
 *Misure* : l'elenco delle misurazioni che possono essere usate nella sezione misure di un payload di richiesta per l'operazione di esecuzione della query.
  

