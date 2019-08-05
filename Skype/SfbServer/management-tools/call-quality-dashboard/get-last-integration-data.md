---
title: Ottenere gli ultimi dati di integrazione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: e7967dd9-0d6a-4a80-8b59-b8fc2e5615f8
description: "Riepilogo: informazioni su come ottenere l'ultima operazione di integrazione dei dati, che fa parte dell'API dati per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: d110bdc1fe88a9fe7f77abe7f7b9ed47a3324eb0
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186917"
---
# <a name="get-last-integration-data"></a><span data-ttu-id="da05c-104">Ottenere gli ultimi dati di integrazione</span><span class="sxs-lookup"><span data-stu-id="da05c-104">Get Last Integration Data</span></span>
 
<span data-ttu-id="da05c-105">**Riepilogo:** Informazioni sull'operazione Get last Integration data, che fa parte dell'API dati per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="da05c-105">**Summary:** Learn about the Get Last Integration Data operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="da05c-106">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="da05c-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="da05c-107">L'operazione Get last Integration data fa parte dell'API Data per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="da05c-107">The Get Last Integration Data operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-last-integration-data"></a><span data-ttu-id="da05c-108">Ottenere gli ultimi dati di integrazione</span><span class="sxs-lookup"><span data-stu-id="da05c-108">Get Last Integration Data</span></span>

<span data-ttu-id="da05c-109">Ottenere l'ultima operazione di integrazione dei dati restituisce l'elenco degli ultimi 5 successo/errore dell'archiviazione e dell'elaborazione dei cubi.</span><span class="sxs-lookup"><span data-stu-id="da05c-109">Get Last Integration Data operation returns the list of last 5 success/failure of archiving and cube processing.</span></span>
  
<span data-ttu-id="da05c-110">Questa caratteristica è disabilitata per impostazione predefinita e deve essere abilitata configurando l'API dati.</span><span class="sxs-lookup"><span data-stu-id="da05c-110">This feature is disabled by default and it needs to be enabled by configuring the Data API.</span></span>
  

|<span data-ttu-id="da05c-111">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="da05c-111">**Method**</span></span>|<span data-ttu-id="da05c-112">**URI di richiesta**</span><span class="sxs-lookup"><span data-stu-id="da05c-112">**Request URI**</span></span>|<span data-ttu-id="da05c-113">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="da05c-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="da05c-114">Ottieni</span><span class="sxs-lookup"><span data-stu-id="da05c-114">GET</span></span>  <br/> |<span data-ttu-id="da05c-115">/QoEDataService/IntegrationLog/status\<portale\>https://</span><span class="sxs-lookup"><span data-stu-id="da05c-115">https://\<portal\>/QoEDataService/IntegrationLog/Status</span></span>  <br/> |<span data-ttu-id="da05c-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="da05c-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="da05c-117">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="da05c-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="da05c-118">**Richiedi intestazioni** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="da05c-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="da05c-119">**Richiedi corpo** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="da05c-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="da05c-120">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="da05c-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="da05c-121">**Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="da05c-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="da05c-122">**Intestazioni di risposta** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="da05c-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="da05c-123">**Corpo risposta** : di seguito è riportato un esempio di stato del log.</span><span class="sxs-lookup"><span data-stu-id="da05c-123">**Response Body** - Below is a sample log status.</span></span>
  
```
{
"LastSuccessIntegrations": ["01/18/2015 10:30:13",
"01/18/2015 10:28:29",
"01/17/2015 15:15:17",
"01/17/2015 15:00:17",
"01/17/2015 14:45:13"],
"LastSuccessCubeProcessings": ["01/17/2015 15:16:40",
"01/17/2015 15:01:41",
"01/17/2015 14:47:19",
"01/17/2015 14:31:40",
"01/17/2015 14:17:01"],
"LastFailedIntegrations":  ,
"LastFailedCubeProcessings": ["01/18/2015 10:30:58",
"01/18/2015 10:29:28",
"01/17/2015 10:02:20",
"01/15/2015 20:01:56",
"01/15/2015 19:45:50"],
"LastDataIntegrationStart": null,
"LastCubeProcessingStart": "01/18/2015 10:30:16"
}
```
