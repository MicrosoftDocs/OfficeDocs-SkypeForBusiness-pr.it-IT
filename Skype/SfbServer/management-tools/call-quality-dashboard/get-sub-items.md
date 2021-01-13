---
title: Get Sub-Items
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: "Riepilogo: informazioni sull'operazione Get Sub-Items, che fa parte del servizio elementi. Il servizio elementi fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: defb0b898c5101513cbb4f6da4382a8bb43bce6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832506"
---
# <a name="get-sub-items"></a><span data-ttu-id="5a9ae-105">Get Sub-Items</span><span class="sxs-lookup"><span data-stu-id="5a9ae-105">Get Sub-Items</span></span>
 
<span data-ttu-id="5a9ae-106">**Riepilogo:** Informazioni sull'operazione Get Sub-Items, che fa parte del servizio elementi.</span><span class="sxs-lookup"><span data-stu-id="5a9ae-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="5a9ae-107">Il servizio elementi fa parte dell'API del repository per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="5a9ae-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="5a9ae-108">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="5a9ae-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="5a9ae-109">L'operazione Get Sub-Items fa parte del servizio elementi nell'API del repository per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="5a9ae-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="5a9ae-110">Get Sub-Items</span><span class="sxs-lookup"><span data-stu-id="5a9ae-110">Get Sub-Items</span></span>

<span data-ttu-id="5a9ae-111">Get Sub-Items restituisce gli elementi secondari di un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="5a9ae-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="5a9ae-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="5a9ae-112">**Method**</span></span>|<span data-ttu-id="5a9ae-113">**URI della richiesta**</span><span class="sxs-lookup"><span data-stu-id="5a9ae-113">**Request URI**</span></span>|<span data-ttu-id="5a9ae-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="5a9ae-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5a9ae-115">GET</span><span class="sxs-lookup"><span data-stu-id="5a9ae-115">GET</span></span>  <br/> |<span data-ttu-id="5a9ae-116">https:// \<portal\> /QoERepositoryService/repository/Item/{ItemId}/SubItem</span><span class="sxs-lookup"><span data-stu-id="5a9ae-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="5a9ae-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="5a9ae-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="5a9ae-118">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="5a9ae-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="5a9ae-119">**Intestazioni richieste** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="5a9ae-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="5a9ae-120">**Corpo richiesta** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="5a9ae-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="5a9ae-121">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="5a9ae-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="5a9ae-122">**Codice di stato** -un'operazione completata restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="5a9ae-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="5a9ae-123">Se un ID utente specificato non viene trovato, restituisce il codice di stato 404 (non trovato).</span><span class="sxs-lookup"><span data-stu-id="5a9ae-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="5a9ae-124">**Intestazioni di risposta** -Nessun intestazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="5a9ae-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="5a9ae-125">**Corpo di risposta** -di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="5a9ae-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5a9ae-126">Viene restituita una matrice di oggetto Item.</span><span class="sxs-lookup"><span data-stu-id="5a9ae-126">An array of Item object is returned.</span></span> 
  
```json
[{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1710,
"userId": 0,
"type": "json"
}]
```

<span data-ttu-id="5a9ae-127">L'oggetto Item restituito dall'operazione Sub-Items contiene solo i tre campi seguenti.</span><span class="sxs-lookup"><span data-stu-id="5a9ae-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="5a9ae-128">*ItemId*  -ID dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="5a9ae-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="5a9ae-129">*userid*  -ID dell'utente a cui appartiene questo elemento.</span><span class="sxs-lookup"><span data-stu-id="5a9ae-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="5a9ae-130">*Type*  : il tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="5a9ae-130">*type*  - The type of the content.</span></span> <span data-ttu-id="5a9ae-131">Questo campo è impostato dalle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="5a9ae-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="5a9ae-132">`Content` e `subItems` i campi non sono inclusi nella risposta per ridurre la quantità di dati trasmessi sulla rete.</span><span class="sxs-lookup"><span data-stu-id="5a9ae-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

