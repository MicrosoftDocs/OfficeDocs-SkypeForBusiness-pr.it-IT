---
title: Get Item Ancestors
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
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: "Riepilogo: informazioni sull'operazione Get Item Predecessors, che fa parte di Item Service. Item Service fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 59fcd10f620b32151346e8732e67ae6151a258ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832576"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="7a7a9-105">Get Item Ancestors</span><span class="sxs-lookup"><span data-stu-id="7a7a9-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="7a7a9-106">**Riepilogo:** Informazioni sull'operazione Get Item Predecessors, che fa parte di Item Service.</span><span class="sxs-lookup"><span data-stu-id="7a7a9-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="7a7a9-107">Item Service fa parte dell'API repository per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="7a7a9-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="7a7a9-108">Call Quality Dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7a7a9-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="7a7a9-109">L'operazione Get Item Predecessors fa parte di Item Service nell'API repository per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="7a7a9-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="7a7a9-110">Get Item Ancestors</span><span class="sxs-lookup"><span data-stu-id="7a7a9-110">Get Item Ancestors</span></span>

<span data-ttu-id="7a7a9-111">Get Item Predecessors restituisce un predecessore di elementi specifici dal repository.</span><span class="sxs-lookup"><span data-stu-id="7a7a9-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="7a7a9-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="7a7a9-112">**Method**</span></span>|<span data-ttu-id="7a7a9-113">**URI richiesta**</span><span class="sxs-lookup"><span data-stu-id="7a7a9-113">**Request URI**</span></span>|<span data-ttu-id="7a7a9-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="7a7a9-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7a7a9-115">GET</span><span class="sxs-lookup"><span data-stu-id="7a7a9-115">GET</span></span>  <br/> |<span data-ttu-id="7a7a9-116">https:// \<portal\> /QoERepositoryService/repository/itemAncestors/{itemId}</span><span class="sxs-lookup"><span data-stu-id="7a7a9-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="7a7a9-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="7a7a9-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="7a7a9-118">**Parametri URI** - Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7a7a9-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="7a7a9-119">**Intestazioni richiesta** - Nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="7a7a9-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7a7a9-120">**Corpo della richiesta** - Nessuno.</span><span class="sxs-lookup"><span data-stu-id="7a7a9-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="7a7a9-121">**Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="7a7a9-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="7a7a9-122">**Codice di stato:** un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="7a7a9-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="7a7a9-123">Se non viene trovato un ID utente specificato, viene restituito il codice di stato 404 (Non trovato).</span><span class="sxs-lookup"><span data-stu-id="7a7a9-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="7a7a9-124">**Intestazioni risposta** - Nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="7a7a9-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="7a7a9-125">**Contenuto della risposta:** di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="7a7a9-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
[{
"item1": 1653,
"item2": 0,
"item3": "Audio Streams Monthly Trend"
},
{
"item1": 1652,
"item2": 1,
"item3": "All Audio Streams"
}]
```

 <span data-ttu-id="7a7a9-126">*Item1*  - ID dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="7a7a9-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="7a7a9-127">*Item2*  - Profondità è la distanza dall'elemento.</span><span class="sxs-lookup"><span data-stu-id="7a7a9-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="7a7a9-128">0 è l'elemento padre immediato.</span><span class="sxs-lookup"><span data-stu-id="7a7a9-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="7a7a9-129">*Item3*  - Titolo dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="7a7a9-129">*Item3*  - Title of the item.</span></span>
  

