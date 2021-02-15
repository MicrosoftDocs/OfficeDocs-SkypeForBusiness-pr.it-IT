---
title: Get Cube
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
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: "Riepilogo: informazioni sull'operazione Get Cube, che fa parte dell'API dei dati per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: a3527f21bc1751c23bba088ae06c3e6702cb8c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832626"
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
  
 **Intestazioni risposta** - Nessuna intestazione aggiuntiva.
  
 **Contenuto della risposta:** di seguito è riportato un payload di risposta di esempio in JSON.
  
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

 *INDICATORI KPI*  - Riservato. La sezione KPI di un payload di richiesta consente all'operazione Esegui query di restituire i valori per gli indicatori KPI definiti nel cubo. Nel cubo QoE non sono ancora presenti indicatori KPI.
  
 *Dimensioni:*  elenco di dimensioni che possono essere utilizzate nelle sezioni Filtri e Dimensioni di un payload di richiesta per l'operazione Esegui query. Per utilizzare una dimensione in un'espressione di filtro, è necessario specificare un membro di dimensione, che può essere ottenuto utilizzando l'operazione Get Dimension Members.
  
 *Misurazioni-*  Elenco di misurazioni che possono essere utilizzate nella sezione Misurazioni di un payload di richiesta per l'operazione Esegui query.
  

