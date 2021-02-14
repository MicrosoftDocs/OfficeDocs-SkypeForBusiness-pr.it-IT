---
title: Run Query
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
ms.assetid: 45a77f7e-b137-462b-9146-3a0f43d8e0c7
description: "Riepilogo: informazioni sull'operazione Esegui query, che fa parte dell'API dati per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: bff24ca5a4d651ba276b4b0d795afabce3c6d0dd
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803116"
---
# <a name="run-query"></a><span data-ttu-id="76a06-104">Run Query</span><span class="sxs-lookup"><span data-stu-id="76a06-104">Run Query</span></span>

<span data-ttu-id="76a06-105">**Riepilogo:** Informazioni sull'operazione Esegui query, che fa parte dell'API dati per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="76a06-105">**Summary:** Learn about the Run Query operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="76a06-106">Call Quality Dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="76a06-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>

<span data-ttu-id="76a06-107">L'operazione Esegui query fa parte dell'API dati per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="76a06-107">The Run Query operation is part of the Data API for Call Quality Dashboard.</span></span>

## <a name="run-query"></a><span data-ttu-id="76a06-108">Run Query</span><span class="sxs-lookup"><span data-stu-id="76a06-108">Run Query</span></span>

<span data-ttu-id="76a06-109">L'operazione Esegui query consente di eseguire una query sul cubo in base a dimensioni, misure e filtri specificati e di restituire i dati.</span><span class="sxs-lookup"><span data-stu-id="76a06-109">Run Query operation provides the ability to run a query on the cube based on specified dimensions, measurements, and filters and return back the data.</span></span>


|<span data-ttu-id="76a06-110">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="76a06-110">**Method**</span></span>|<span data-ttu-id="76a06-111">**URI richiesta**</span><span class="sxs-lookup"><span data-stu-id="76a06-111">**Request URI**</span></span>|<span data-ttu-id="76a06-112">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="76a06-112">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="76a06-113">POST</span><span class="sxs-lookup"><span data-stu-id="76a06-113">POST</span></span>  <br/> |<span data-ttu-id="76a06-114">https:// \<portal\> /QoEDataService/RunQuery</span><span class="sxs-lookup"><span data-stu-id="76a06-114">https://\<portal\>/QoEDataService/RunQuery</span></span>  <br/> |<span data-ttu-id="76a06-115">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="76a06-115">HTTP/1.1</span></span>  <br/> |

 <span data-ttu-id="76a06-116">**Parametri URI** - Nessuno.</span><span class="sxs-lookup"><span data-stu-id="76a06-116">**URI Parameters** - None.</span></span>

 <span data-ttu-id="76a06-117">**Intestazioni richiesta** - Nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="76a06-117">**Request Headers** - No additional headers.</span></span>

 <span data-ttu-id="76a06-118">**Corpo della richiesta:** ecco un payload di richiesta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="76a06-118">**Request Body** - Here is a sample request payload in JSON.</span></span> <span data-ttu-id="76a06-119">Contiene dimensioni, filtri e misurazioni necessari per una query.</span><span class="sxs-lookup"><span data-stu-id="76a06-119">It contains dimensions, filters, and measurement required for a query.</span></span>

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

 <span data-ttu-id="76a06-120">*Filtri*  - Elenco di espressioni di filtro da applicare in modo che il set di dati risultante rifletta solo il sottoinsieme di dati di interesse.</span><span class="sxs-lookup"><span data-stu-id="76a06-120">*Filters*  - A list of filter expressions to be applied such that the resulting data set will reflect only the subset of the data that are of interest.</span></span>

 <span data-ttu-id="76a06-121">*Dimensioni*  : elenco di dimensioni che verranno utilizzate per l'aggregazione dei dati.</span><span class="sxs-lookup"><span data-stu-id="76a06-121">*Dimensions*  - A list of dimensions that will be used for aggregating the data.</span></span> <span data-ttu-id="76a06-122">È necessaria almeno una dimensione, ma è possibile specificarne più per ottenere un livello aggiuntivo di aggregazioni secondarie.</span><span class="sxs-lookup"><span data-stu-id="76a06-122">At least one dimension is required but multiple dimensions may be specified to obtain additional level of sub-aggregations.</span></span>

 <span data-ttu-id="76a06-123">*Misurazioni:*  un elenco di misurazioni, note anche come fatti, che sono le metriche desiderate da aggregare in base alle dimensioni specificate.</span><span class="sxs-lookup"><span data-stu-id="76a06-123">*Measurements*  - A list of measurements, also known as facts, that are the desired metrics to be aggregated based on the dimensions you specified.</span></span>

 <span data-ttu-id="76a06-124">*Tendenza:*  istruzioni di controllo aggiuntive per personalizzare i dati dei risultati.</span><span class="sxs-lookup"><span data-stu-id="76a06-124">*Trend*  - Additional control instructions to customize the result data.</span></span>

 <span data-ttu-id="76a06-125">**Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="76a06-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>

 <span data-ttu-id="76a06-126">**Codice di stato:** un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="76a06-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>

 <span data-ttu-id="76a06-127">**Intestazioni risposta** - Nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="76a06-127">**Response Headers** - No additional headers.</span></span>

 <span data-ttu-id="76a06-128">**Contenuto della risposta:** di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="76a06-128">**Response Body** - Below is a sample response payload in JSON.</span></span> <span data-ttu-id="76a06-129">Contiene una tabella di dati che contiene i dati, inoltre conterrà un metadato, che mostra il tempo di esecuzione della query e se i dati sono o meno dalla cache.</span><span class="sxs-lookup"><span data-stu-id="76a06-129">It contains a data table which contains the data, also it will contain a meta data, which shows query execution time and whether or not the data is from the cache.</span></span>

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

 <span data-ttu-id="76a06-130">*Tempo di esecuzione-*  Tempo totale impiegato dal server per restituire i dati.</span><span class="sxs-lookup"><span data-stu-id="76a06-130">*Execution Time*  - The total time it took for the server to return the data.</span></span> <span data-ttu-id="76a06-131">Questa operazione può interessare o meno la cache.</span><span class="sxs-lookup"><span data-stu-id="76a06-131">This may or may not involve cache.</span></span>

 <span data-ttu-id="76a06-132">*Risultato dati*  - Risultato della query.</span><span class="sxs-lookup"><span data-stu-id="76a06-132">*Data Result*  - The result of the query.</span></span> <span data-ttu-id="76a06-133">Si tratta di una matrice bidimensionale contenente tutte le permutazioni dei membri delle dimensioni e ogni elemento contenente i nomi dei membri delle dimensioni, nonché i valori aggregati delle misure specificate.</span><span class="sxs-lookup"><span data-stu-id="76a06-133">It is a two-dimensional array containing all permutations of the dimensions' members, and each element containing the dimensions' member names as well as the aggregated values of the specified Measurements.</span></span>

 <span data-ttu-id="76a06-134">*Risultato dalla cache-*  Per la diagnostica.</span><span class="sxs-lookup"><span data-stu-id="76a06-134">*Result is From Cache*  - For diagnostics.</span></span> <span data-ttu-id="76a06-135">Indica se il risultato deriva dalla cache o dal cubo QoE.</span><span class="sxs-lookup"><span data-stu-id="76a06-135">Indicates whether the result came from the cache or from the QoE Cube.</span></span>
