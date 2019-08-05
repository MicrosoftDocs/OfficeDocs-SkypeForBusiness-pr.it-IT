---
title: Ottieni cubo
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: c8eeb387-dc1e-44e0-bbf9-a566f8bda551
description: "Riepilogo: informazioni sull'operazione Get Cube, che fa parte dell'API dati per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 970187ce9f95700185ab09bd7aadf9045575b393
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186950"
---
# <a name="get-cube"></a><span data-ttu-id="97aae-104">Ottieni cubo</span><span class="sxs-lookup"><span data-stu-id="97aae-104">Get Cube</span></span>
 
<span data-ttu-id="97aae-105">**Riepilogo:** Informazioni sull'operazione Get Cube, che fa parte dell'API dati per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="97aae-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="97aae-106">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="97aae-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="97aae-107">L'operazione Get Cube fa parte dell'API Data per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="97aae-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="97aae-108">Ottieni cubo</span><span class="sxs-lookup"><span data-stu-id="97aae-108">Get Cube</span></span>

<span data-ttu-id="97aae-109">L'operazione Get CUBE restituisce l'elenco delle dimensioni e delle misure disponibili.</span><span class="sxs-lookup"><span data-stu-id="97aae-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="97aae-110">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="97aae-110">**Method**</span></span>|<span data-ttu-id="97aae-111">**URI di richiesta**</span><span class="sxs-lookup"><span data-stu-id="97aae-111">**Request URI**</span></span>|<span data-ttu-id="97aae-112">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="97aae-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="97aae-113">Ottieni</span><span class="sxs-lookup"><span data-stu-id="97aae-113">GET</span></span>  <br/> |<span data-ttu-id="97aae-114">/QoEDataService/CubeStructure\<portale\>https://</span><span class="sxs-lookup"><span data-stu-id="97aae-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="97aae-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="97aae-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="97aae-116">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="97aae-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="97aae-117">**Richiedi intestazioni** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="97aae-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="97aae-118">**Richiedi corpo** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="97aae-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="97aae-119">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="97aae-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="97aae-120">**Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="97aae-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="97aae-121">**Intestazioni di risposta** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="97aae-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="97aae-122">**Corpo risposta** : di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="97aae-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="97aae-123">Questo esempio Mostra solo i primi due elementi di ogni gruppo di elementi Cube.</span><span class="sxs-lookup"><span data-stu-id="97aae-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
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

 <span data-ttu-id="97aae-124">*Indicatori KPI* -riservati.</span><span class="sxs-lookup"><span data-stu-id="97aae-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="97aae-125">La sezione KPI di un payload di richiesta consente l'esecuzione di operazioni di query per restituire valori per i KPI definiti nel cubo.</span><span class="sxs-lookup"><span data-stu-id="97aae-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="97aae-126">Nel cubo QoE non esistono ancora indicatori KPI.</span><span class="sxs-lookup"><span data-stu-id="97aae-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="97aae-127">*Dimensions* -l'elenco di dimensioni che possono essere usate in filtri e dimensioni sezioni di un payload di richiesta per l'operazione di esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="97aae-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="97aae-128">Per usare una dimensione in un'espressione di filtro, devi specificare un membro della dimensione, che può essere ottenuto usando l'operazione membri della dimensione Get.</span><span class="sxs-lookup"><span data-stu-id="97aae-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="97aae-129">*Misure* : l'elenco delle misurazioni che possono essere usate nella sezione misure di un payload di richiesta per l'operazione di esecuzione della query.</span><span class="sxs-lookup"><span data-stu-id="97aae-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

