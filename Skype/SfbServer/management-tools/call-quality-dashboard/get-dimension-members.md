---
title: Ottenere i membri della dimensione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: "Riepilogo: informazioni sull'operazione get Members Dimension. L'operazione get Members Dimension fa parte dell'API Data per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: c457e7f3b42aaeb11c35180bc4c1ae6ee42b914e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186947"
---
# <a name="get-dimension-members"></a><span data-ttu-id="c09a2-105">Ottenere i membri della dimensione</span><span class="sxs-lookup"><span data-stu-id="c09a2-105">Get Dimension Members</span></span>
 
<span data-ttu-id="c09a2-106">**Riepilogo:** Informazioni sull'operazione get Members Dimension.</span><span class="sxs-lookup"><span data-stu-id="c09a2-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="c09a2-107">L'operazione get Members Dimension fa parte dell'API Data per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="c09a2-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="c09a2-108">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="c09a2-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="c09a2-109">L'operazione get Members Dimension fa parte dell'API Data per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="c09a2-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="c09a2-110">Ottenere i membri della dimensione</span><span class="sxs-lookup"><span data-stu-id="c09a2-110">Get Dimension Members</span></span>

<span data-ttu-id="c09a2-111">L'operazione get Members Dimension restituisce l'elenco dei membri di una dimensione specifica.</span><span class="sxs-lookup"><span data-stu-id="c09a2-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="c09a2-112">È anche possibile filtrare l'elenco dei membri e ottenere un sottoinsieme, per ridurre il costo del bonifico bancario.</span><span class="sxs-lookup"><span data-stu-id="c09a2-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="c09a2-113">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="c09a2-113">**Method**</span></span>|<span data-ttu-id="c09a2-114">**URI di richiesta**</span><span class="sxs-lookup"><span data-stu-id="c09a2-114">**Request URI**</span></span>|<span data-ttu-id="c09a2-115">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="c09a2-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c09a2-116">Inserisci</span><span class="sxs-lookup"><span data-stu-id="c09a2-116">POST</span></span>  <br/> |<span data-ttu-id="c09a2-117">/QoEDataService/DimensionMembers\<portale\>https://</span><span class="sxs-lookup"><span data-stu-id="c09a2-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="c09a2-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="c09a2-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="c09a2-119">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="c09a2-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="c09a2-120">**Richiedi intestazioni** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="c09a2-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c09a2-121">**Richiedi corpo** : contiene il nome della dimensione per cui desideriamo i membri.</span><span class="sxs-lookup"><span data-stu-id="c09a2-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="c09a2-122">Anche il numero massimo di membri restituiti, accanto a puoi specificare alcuni filtri per limitare i membri restituiti.</span><span class="sxs-lookup"><span data-stu-id="c09a2-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
```
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 <span data-ttu-id="c09a2-123">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="c09a2-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="c09a2-124">**Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="c09a2-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="c09a2-125">**Intestazioni di risposta** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="c09a2-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="c09a2-126">**Corpo della risposta** : di seguito è riportato un payload di risposta di esempio in JSON in risposta a una richiesta di "[StartDate]. [Month] "Dimension.</span><span class="sxs-lookup"><span data-stu-id="c09a2-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c09a2-127">L'elenco Mostra solo una piccola parte dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="c09a2-127">The list is only showing a small portion of the list.</span></span> 
  
```
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
