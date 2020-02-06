---
title: Run Query
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
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: "Riepilogo: informazioni sull'operazione Esegui query, che fa parte dell'API dati per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 4e520921496a1650af12b342fd5a0244fe9eb7a5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816685"
---
# <a name="run-query"></a><span data-ttu-id="97b2a-104">Run Query</span><span class="sxs-lookup"><span data-stu-id="97b2a-104">Run Query</span></span>

<span data-ttu-id="97b2a-105">**Riepilogo:** Informazioni sull'operazione Esegui query, che fa parte dell'API dati per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="97b2a-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="97b2a-106">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="97b2a-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="97b2a-107">L'operazione Esegui query fa parte dell'API dati per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="97b2a-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="97b2a-108">Run Query</span><span class="sxs-lookup"><span data-stu-id="97b2a-108">Run Query</span></span>

<span data-ttu-id="97b2a-109">L'operazione Esegui query offre la possibilità di eseguire una query sul cubo in base a dimensioni, misure e filtri specificati e restituire i dati.</span><span class="sxs-lookup"><span data-stu-id="97b2a-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="97b2a-110">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="97b2a-110">**Method**</span></span>|<span data-ttu-id="97b2a-111">**URI di richiesta**</span><span class="sxs-lookup"><span data-stu-id="97b2a-111">**Request URI**</span></span>|<span data-ttu-id="97b2a-112">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="97b2a-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="97b2a-113">Inserisci</span><span class="sxs-lookup"><span data-stu-id="97b2a-113">POST</span></span>  <br/> |<span data-ttu-id="97b2a-114">/QoEDataService/RunQuery\<portale\>https://</span><span class="sxs-lookup"><span data-stu-id="97b2a-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="97b2a-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="97b2a-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="97b2a-116">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="97b2a-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="97b2a-117">**Richiedi intestazioni** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="97b2a-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="97b2a-118">**Richiedi corpo** : Ecco un payload di richiesta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="97b2a-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="97b2a-119">Contiene dimensioni, filtri e misure necessarie per una query.</span><span class="sxs-lookup"><span data-stu-id="97b2a-119">It contains dimensions, filters, and measurement required for a query.</span></span>

```json
{
"Filters": [{
"DataModelName": "[StartDate].[Month]",
"Caption": "July 2013",
"Value": "[2015-03-01T00:00:00]",
"Operand": 0,
"UnionGroup": ""
}],
"Dimensions": [{
"DataModelName": "[StartDate].[Month]"
}],
"Measurements": [{
"DataModelName": "[Measures].[Audio Good Streams Count]"
},
{
"DataModelName": "[Measures].[Audio UnClassified Streams Count]"
},
{
"DataModelName": "[Measures].[Audio Poor Streams Count]"
},
{
"DataModelName": "[Measures].[AudioPoorPercentage]"
}],
"Trend": {
"EnableTrend": true,
"SpanCount": 7,
"TrendDate": "2015-3",
"Type": 0
}
}
```

 <span data-ttu-id="97b2a-120">*Filtri* : un elenco di espressioni di filtro da applicare in modo che il set di dati risultante rifletta solo il sottoinsieme dei dati di interesse.</span><span class="sxs-lookup"><span data-stu-id="97b2a-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="97b2a-121">*Dimensions* : un elenco di dimensioni che verranno usate per l'aggregazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="97b2a-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="97b2a-122">È richiesta almeno una dimensione, ma possono essere specificate più dimensioni per ottenere un livello aggiuntivo di aggregazioni secondarie.</span><span class="sxs-lookup"><span data-stu-id="97b2a-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="97b2a-123">*Misure* : un elenco di misurazioni, note anche come fact, che sono le metriche desiderate da aggregare in base alle dimensioni specificate.</span><span class="sxs-lookup"><span data-stu-id="97b2a-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="97b2a-124">*Trend* -istruzioni aggiuntive per il controllo per personalizzare i dati dei risultati.</span><span class="sxs-lookup"><span data-stu-id="97b2a-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="97b2a-125">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="97b2a-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="97b2a-126">**Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="97b2a-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="97b2a-127">**Intestazioni di risposta** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="97b2a-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="97b2a-128">**Corpo risposta** : di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="97b2a-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="97b2a-129">Contiene una tabella dati che contiene i dati, inoltre conterrà un meta dati, che mostra il tempo di esecuzione della query e se i dati vengono o meno dalla cache.</span><span class="sxs-lookup"><span data-stu-id="97b2a-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

```json
{
"ExecutionTime": "00:00:00.2102630",
"DataResult": [["September 2014",
        1792,
        34,
        78,
        4.171],
        ["October 2014",
        37017,
        1731,
        3305,
        8.197],
        ["November 2014",
        79184,
        3033,
        5556,
        6.557],
        ["December 2014",
        122253,
        4050,
        5444,
        4.263],
        ["January 2015",
        31246,
        1069,
        1342,
        4.118]],
"ResultIsFromCache": false,
"ErrorType": 0
}
```

 <span data-ttu-id="97b2a-130">*Tempo di esecuzione* : il tempo totale impiegato per il server per la restituzione dei dati.</span><span class="sxs-lookup"><span data-stu-id="97b2a-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="97b2a-131">Questo può o non può coinvolgere la cache.</span><span class="sxs-lookup"><span data-stu-id="97b2a-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="97b2a-132">*Risultato dei dati* : il risultato della query.</span><span class="sxs-lookup"><span data-stu-id="97b2a-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="97b2a-133">Si tratta di una matrice bidimensionale contenente tutte le permutazioni dei membri delle dimensioni e di ogni elemento contenente i nomi dei membri delle dimensioni e i valori aggregati delle misure specificate.</span><span class="sxs-lookup"><span data-stu-id="97b2a-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="97b2a-134">Il *risultato è dalla cache* -per la diagnostica.</span><span class="sxs-lookup"><span data-stu-id="97b2a-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="97b2a-135">Indica se il risultato proviene dalla cache o dal cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="97b2a-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
