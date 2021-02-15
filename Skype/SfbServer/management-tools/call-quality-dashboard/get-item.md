---
title: Get Item
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
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: "Riepilogo: informazioni sull'operazione Get Item, che fa parte di Item Service. Item Service fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 896540c4572fb3991356ce055f01690ed702c6f2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832566"
---
# <a name="get-item"></a><span data-ttu-id="d2c8d-105">Get Item</span><span class="sxs-lookup"><span data-stu-id="d2c8d-105">Get Item</span></span>
 
<span data-ttu-id="d2c8d-106">**Riepilogo:** Informazioni sull'operazione Get Item, che fa parte di Item Service.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="d2c8d-107">Item Service fa parte dell'API repository per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="d2c8d-108">Call Quality Dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="d2c8d-109">L'operazione Get Item fa parte di Item Service nell'API repository per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="d2c8d-110">Get Item</span><span class="sxs-lookup"><span data-stu-id="d2c8d-110">Get Item</span></span>

<span data-ttu-id="d2c8d-111">Get Item restituisce un elemento specifico nel repository.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="d2c8d-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="d2c8d-112">**Method**</span></span>|<span data-ttu-id="d2c8d-113">**URI richiesta**</span><span class="sxs-lookup"><span data-stu-id="d2c8d-113">**Request URI**</span></span>|<span data-ttu-id="d2c8d-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="d2c8d-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d2c8d-115">GET</span><span class="sxs-lookup"><span data-stu-id="d2c8d-115">GET</span></span>  <br/> |<span data-ttu-id="d2c8d-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="d2c8d-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="d2c8d-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="d2c8d-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="d2c8d-118">**Parametri URI** - Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="d2c8d-119">**Intestazioni richiesta** - Nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d2c8d-120">**Corpo della richiesta** - Nessuno.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="d2c8d-121">**Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="d2c8d-122">**Codice di stato:** un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="d2c8d-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="d2c8d-123">Se non viene trovato un ID elemento specificato, viene restituito il codice di stato 404 (Non trovato).</span><span class="sxs-lookup"><span data-stu-id="d2c8d-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="d2c8d-124">**Intestazioni risposta** - Nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d2c8d-125">**Contenuto della risposta:** di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="d2c8d-126">*itemId*  - ID dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="d2c8d-127">*userId*  - ID dell'utente proprietario dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="d2c8d-128">*content*  - Contenuto specifico dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="d2c8d-129">*type*  - Tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-129">*type*  - The type of the content.</span></span> <span data-ttu-id="d2c8d-130">Questo campo viene impostato dalle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="d2c8d-131">*subItemIds*  - ID degli eventuali elementi secondari.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="d2c8d-132">Si tratta di un corto circuito dell'operazione Get Sub-Items salvare una chiamata.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="d2c8d-133">In alternativa, le applicazioni possono ottenere le stesse informazioni utilizzando l'Sub-Items get.</span><span class="sxs-lookup"><span data-stu-id="d2c8d-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

