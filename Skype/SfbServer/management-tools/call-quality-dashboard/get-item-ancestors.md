---
title: Ottieni predecessori elemento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d39b1dbc-1514-43ec-8593-9f23b3fcae62
description: "Riepilogo: informazioni sull'operazione Ottieni antenati elemento, che fa parte del servizio elemento. Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: c82ae699cab0bf812f281fc2f2ad54323bcf8f7f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992683"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="2e874-105">Ottieni predecessori elemento</span><span class="sxs-lookup"><span data-stu-id="2e874-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="2e874-106">**Riepilogo:** Informazioni sull'operazione Ottieni antenati elemento, che fa parte del servizio elemento.</span><span class="sxs-lookup"><span data-stu-id="2e874-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="2e874-107">Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="2e874-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="2e874-108">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2e874-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="2e874-109">L'operazione Ottieni antenati elemento fa parte del servizio elemento nell'API del repository per Call Quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="2e874-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="2e874-110">Ottieni predecessori elemento</span><span class="sxs-lookup"><span data-stu-id="2e874-110">Get Item Ancestors</span></span>

<span data-ttu-id="2e874-111">Ottenere gli antenati degli elementi restituisce un elemento specifico antenati dal repository.</span><span class="sxs-lookup"><span data-stu-id="2e874-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="2e874-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="2e874-112">**Method**</span></span>|<span data-ttu-id="2e874-113">**URI di richiesta**</span><span class="sxs-lookup"><span data-stu-id="2e874-113">**Request URI**</span></span>|<span data-ttu-id="2e874-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="2e874-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2e874-115">Ottieni</span><span class="sxs-lookup"><span data-stu-id="2e874-115">GET</span></span>  <br/> |<span data-ttu-id="2e874-116">/QoERepositoryService/repository/itemAncestors/{ItemId}\<portale\>https://</span><span class="sxs-lookup"><span data-stu-id="2e874-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="2e874-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="2e874-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="2e874-118">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="2e874-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="2e874-119">**Richiedi intestazioni** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="2e874-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="2e874-120">**Richiedi corpo** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="2e874-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="2e874-121">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="2e874-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="2e874-122">**Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="2e874-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="2e874-123">Se non viene trovato un ID utente specificato, viene restituito il codice di stato 404 (non trovato).</span><span class="sxs-lookup"><span data-stu-id="2e874-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="2e874-124">**Intestazioni di risposta** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="2e874-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="2e874-125">**Corpo risposta** : di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="2e874-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
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

 <span data-ttu-id="2e874-126">*Item1* -ID dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="2e874-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="2e874-127">*Item2* -Depth è la distanza dall'elemento.</span><span class="sxs-lookup"><span data-stu-id="2e874-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="2e874-128">0 è l'elemento padre immediato.</span><span class="sxs-lookup"><span data-stu-id="2e874-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="2e874-129">*Item3* -titolo dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="2e874-129">*Item3*  - Title of the item.</span></span>
  

