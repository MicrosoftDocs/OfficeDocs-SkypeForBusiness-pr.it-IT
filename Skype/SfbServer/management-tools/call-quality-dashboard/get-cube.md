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
description: "Riepilogo: informazioni sull'operazione Get Cube, che fa parte dell'API dei dati per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: a3527f21bc1751c23bba088ae06c3e6702cb8c8e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832626"
---
# <a name="get-cube"></a><span data-ttu-id="80f25-104">Get Cube</span><span class="sxs-lookup"><span data-stu-id="80f25-104">Get Cube</span></span>
 
<span data-ttu-id="80f25-105">**Riepilogo:** Informazioni sull'operazione Get Cube, che fa parte dell'API Data per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="80f25-105">**Summary:** Learn about the Get Cube operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="80f25-106">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="80f25-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="80f25-107">L'operazione Get Cube fa parte dell'API Data per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="80f25-107">The Get Cube operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-cube"></a><span data-ttu-id="80f25-108">Get Cube</span><span class="sxs-lookup"><span data-stu-id="80f25-108">Get Cube</span></span>

<span data-ttu-id="80f25-109">Get Cube Operation restituisce l'elenco delle dimensioni e delle misure disponibili.</span><span class="sxs-lookup"><span data-stu-id="80f25-109">Get Cube operation returns the list of available dimensions and measurements.</span></span>
  

|<span data-ttu-id="80f25-110">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="80f25-110">**Method**</span></span>|<span data-ttu-id="80f25-111">**URI della richiesta**</span><span class="sxs-lookup"><span data-stu-id="80f25-111">**Request URI**</span></span>|<span data-ttu-id="80f25-112">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="80f25-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="80f25-113">GET</span><span class="sxs-lookup"><span data-stu-id="80f25-113">GET</span></span>  <br/> |<span data-ttu-id="80f25-114">https:// \<portal\> /QoEDataService/CubeStructure</span><span class="sxs-lookup"><span data-stu-id="80f25-114">https://\<portal\>/QoEDataService/CubeStructure</span></span>  <br/> |<span data-ttu-id="80f25-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="80f25-115">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="80f25-116">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="80f25-116">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="80f25-117">**Intestazioni richieste** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="80f25-117">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="80f25-118">**Corpo richiesta** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="80f25-118">**Request Body** - None.</span></span>
  
 <span data-ttu-id="80f25-119">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="80f25-119">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="80f25-120">**Codice di stato** -un'operazione completata restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="80f25-120">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="80f25-121">**Intestazioni di risposta** -Nessun intestazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="80f25-121">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="80f25-122">**Corpo di risposta** -di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="80f25-122">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="80f25-123">In questo esempio vengono visualizzati solo i primi due elementi di ogni gruppo di elementi Cube.</span><span class="sxs-lookup"><span data-stu-id="80f25-123">This sample is only showing first two elements of each groups of Cube elements.</span></span> 
  
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

 <span data-ttu-id="80f25-124">*Indicatori KPI*  -riservati.</span><span class="sxs-lookup"><span data-stu-id="80f25-124">*KPIs*  - Reserved.</span></span> <span data-ttu-id="80f25-125">La sezione KPI di un payload di richiesta consente di eseguire l'operazione di query per restituire i valori degli indicatori KPI definiti nel cubo.</span><span class="sxs-lookup"><span data-stu-id="80f25-125">The KPIs section of a request payload allows Run Query operation to return values for the KPIs defined in the cube.</span></span> <span data-ttu-id="80f25-126">Non esistono ancora indicatori KPI nel cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="80f25-126">No KPIs exist in the QoE Cube yet.</span></span>
  
 <span data-ttu-id="80f25-127">*Dimensions*  : l'elenco delle dimensioni che può essere utilizzato nelle sezioni filtri e dimensioni di un payload di richieste per l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="80f25-127">*Dimensions*  - The list of dimensions that may be used in Filters and Dimensions sections of a request payload for Run Query operation.</span></span> <span data-ttu-id="80f25-128">Per utilizzare una dimensione in un'espressione di filtro, è necessario specificare un membro di dimensione, che può essere ottenuto utilizzando l'operazione dei membri della dimensione Get.</span><span class="sxs-lookup"><span data-stu-id="80f25-128">To use a dimension in a filter expression, you need to specify a dimension member, which can be obtained using Get Dimension Members operation.</span></span>
  
 <span data-ttu-id="80f25-129">*Misurazioni*  : l'elenco delle misurazioni che possono essere utilizzate nella sezione misurazioni di un payload di richiesta per l'esecuzione di query.</span><span class="sxs-lookup"><span data-stu-id="80f25-129">*Measurements*  - The list of measurements that may be used in Measurements section of a request payload for Run Query operation.</span></span>
  

