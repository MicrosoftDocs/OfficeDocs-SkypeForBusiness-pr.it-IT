---
title: Ottieni elemento
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
ms.assetid: e77bf649-d62a-4d94-80de-066ba47730cd
description: "Riepilogo: informazioni sull'operazione Get Item, che fa parte del servizio Item. Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 295276e6f3b0f577dae9a43c4c0f62e23b8582f4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816795"
---
# <a name="get-item"></a><span data-ttu-id="4d62d-105">Ottieni elemento</span><span class="sxs-lookup"><span data-stu-id="4d62d-105">Get Item</span></span>
 
<span data-ttu-id="4d62d-106">**Riepilogo:** Informazioni sull'operazione Get Item, che fa parte del servizio Item.</span><span class="sxs-lookup"><span data-stu-id="4d62d-106">**Summary:** Learn about the Get Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="4d62d-107">Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="4d62d-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="4d62d-108">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4d62d-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="4d62d-109">L'operazione Get Item fa parte del servizio Item nell'API del repository per Call Quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="4d62d-109">The Get Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item"></a><span data-ttu-id="4d62d-110">Ottieni elemento</span><span class="sxs-lookup"><span data-stu-id="4d62d-110">Get Item</span></span>

<span data-ttu-id="4d62d-111">Get Item restituisce un elemento specifico nel repository.</span><span class="sxs-lookup"><span data-stu-id="4d62d-111">Get Item returns a specific item in the repository.</span></span>
  
|<span data-ttu-id="4d62d-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="4d62d-112">**Method**</span></span>|<span data-ttu-id="4d62d-113">**URI di richiesta**</span><span class="sxs-lookup"><span data-stu-id="4d62d-113">**Request URI**</span></span>|<span data-ttu-id="4d62d-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="4d62d-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4d62d-115">Ottieni</span><span class="sxs-lookup"><span data-stu-id="4d62d-115">GET</span></span>  <br/> |<span data-ttu-id="4d62d-116">/QoERepositoryService/repository/Item/{ItemId}\<portale\>https://</span><span class="sxs-lookup"><span data-stu-id="4d62d-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="4d62d-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="4d62d-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="4d62d-118">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="4d62d-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="4d62d-119">**Richiedi intestazioni** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="4d62d-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4d62d-120">**Richiedi corpo** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="4d62d-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="4d62d-121">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="4d62d-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="4d62d-122">**Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="4d62d-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="4d62d-123">Se non viene trovato un ID elemento specificato, viene restituito il codice di stato 404 (non trovato).</span><span class="sxs-lookup"><span data-stu-id="4d62d-123">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="4d62d-124">**Intestazioni di risposta** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="4d62d-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4d62d-125">**Corpo risposta** : di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="4d62d-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"itemId": 1652,
"userId": 0,
"content": "{\"Title\":\"All Audio Streams\",...}",
"type": "application/json",
"subItemIds": [1653, 1710]
}
```

 <span data-ttu-id="4d62d-126">ID *ItemId* dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="4d62d-126">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="4d62d-127">*userid* -ID dell'utente proprietario di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="4d62d-127">*userId*  - ID of the user who owns this item.</span></span>
  
 <span data-ttu-id="4d62d-128">*contenuto* : contenuto specifico dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="4d62d-128">*content*  - The application-specific content.</span></span>
  
 <span data-ttu-id="4d62d-129">*tipo* : il tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="4d62d-129">*type*  - The type of the content.</span></span> <span data-ttu-id="4d62d-130">Questo campo è impostato dalle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="4d62d-130">This field is set by the applications.</span></span>
  
 <span data-ttu-id="4d62d-131">*Subitemids* -gli ID degli elementi secondari, se presenti.</span><span class="sxs-lookup"><span data-stu-id="4d62d-131">*subItemIds*  - The IDs of sub-Items, if any.</span></span> <span data-ttu-id="4d62d-132">Si tratta di un cortocircuito dell'operazione Get Sub-Items per salvare una chiamata.</span><span class="sxs-lookup"><span data-stu-id="4d62d-132">This is a short-circuit of Get Sub-Items operation to save a call.</span></span> <span data-ttu-id="4d62d-133">Le applicazioni possono ottenere in alternativa le stesse informazioni utilizzando l'operazione Get Sub-Items.</span><span class="sxs-lookup"><span data-stu-id="4d62d-133">Applications can alternatively obtain the same information using Get Sub-Items operation.</span></span>
  

