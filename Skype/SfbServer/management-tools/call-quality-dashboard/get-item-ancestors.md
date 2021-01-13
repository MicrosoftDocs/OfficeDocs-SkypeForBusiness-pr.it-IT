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
description: "Riepilogo: informazioni sull'operazione ottenere gli antenati degli elementi, che fa parte del servizio elementi. Il servizio elementi fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 59fcd10f620b32151346e8732e67ae6151a258ff
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832576"
---
# <a name="get-item-ancestors"></a><span data-ttu-id="09493-105">Get Item Ancestors</span><span class="sxs-lookup"><span data-stu-id="09493-105">Get Item Ancestors</span></span>
 
<span data-ttu-id="09493-106">**Riepilogo:** Informazioni sull'operazione ottenere gli antenati degli elementi, che fa parte del servizio elementi.</span><span class="sxs-lookup"><span data-stu-id="09493-106">**Summary:** Learn about the Get Item Ancestors operation, which is part of the Item Service.</span></span> <span data-ttu-id="09493-107">Il servizio elementi fa parte dell'API del repository per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="09493-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="09493-108">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="09493-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="09493-109">L'operazione ottenere gli antenati dell'elemento fa parte del servizio elementi nell'API del repository per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="09493-109">The Get Item Ancestors operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-item-ancestors"></a><span data-ttu-id="09493-110">Get Item Ancestors</span><span class="sxs-lookup"><span data-stu-id="09493-110">Get Item Ancestors</span></span>

<span data-ttu-id="09493-111">Ottenere gli antenati degli elementi restituisce una specifica voce antenati dall'archivio.</span><span class="sxs-lookup"><span data-stu-id="09493-111">Get Item Ancestors returns a specific items ancestors from the repository.</span></span>
  

|<span data-ttu-id="09493-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="09493-112">**Method**</span></span>|<span data-ttu-id="09493-113">**URI della richiesta**</span><span class="sxs-lookup"><span data-stu-id="09493-113">**Request URI**</span></span>|<span data-ttu-id="09493-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="09493-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="09493-115">GET</span><span class="sxs-lookup"><span data-stu-id="09493-115">GET</span></span>  <br/> |<span data-ttu-id="09493-116">https:// \<portal\> /QoERepositoryService/repository/itemAncestors/{ItemId}</span><span class="sxs-lookup"><span data-stu-id="09493-116">https://\<portal\>/QoERepositoryService/repository/itemAncestors/{itemId}</span></span>  <br/> |<span data-ttu-id="09493-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="09493-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="09493-118">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="09493-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="09493-119">**Intestazioni richieste** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="09493-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="09493-120">**Corpo richiesta** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="09493-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="09493-121">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="09493-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="09493-122">**Codice di stato** -un'operazione completata restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="09493-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="09493-123">Se un ID utente specificato non viene trovato, restituisce il codice di stato 404 (non trovato).</span><span class="sxs-lookup"><span data-stu-id="09493-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="09493-124">**Intestazioni di risposta** -Nessun intestazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="09493-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="09493-125">**Corpo di risposta** -di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="09493-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
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

 <span data-ttu-id="09493-126">*Item1*  -ID dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="09493-126">*Item1*  - ID of the item.</span></span>
  
 <span data-ttu-id="09493-127">*Item2*  -Depth è la distanza dall'elemento.</span><span class="sxs-lookup"><span data-stu-id="09493-127">*Item2*  - Depth is the distance from the Item.</span></span> <span data-ttu-id="09493-128">0 è l'elemento padre immediato.</span><span class="sxs-lookup"><span data-stu-id="09493-128">0 is the immediate parent.</span></span>
  
 <span data-ttu-id="09493-129">*Item3*  -title dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="09493-129">*Item3*  - Title of the item.</span></span>
  

