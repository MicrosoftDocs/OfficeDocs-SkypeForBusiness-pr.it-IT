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
description: "Riepilogo: informazioni sull'operazione Get Sub-Items, che fa parte di Item Service. Item Service fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: defb0b898c5101513cbb4f6da4382a8bb43bce6e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832506"
---
# <a name="get-sub-items"></a><span data-ttu-id="dc8d2-105">Get Sub-Items</span><span class="sxs-lookup"><span data-stu-id="dc8d2-105">Get Sub-Items</span></span>
 
<span data-ttu-id="dc8d2-106">**Riepilogo:** Informazioni sull'operazione Get Sub-Items, che fa parte di Item Service.</span><span class="sxs-lookup"><span data-stu-id="dc8d2-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="dc8d2-107">Item Service fa parte dell'API repository per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="dc8d2-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="dc8d2-108">Call Quality Dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dc8d2-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="dc8d2-109">L'operazione Get Sub-Items fa parte di Item Service nell'API repository per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="dc8d2-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="dc8d2-110">Get Sub-Items</span><span class="sxs-lookup"><span data-stu-id="dc8d2-110">Get Sub-Items</span></span>

<span data-ttu-id="dc8d2-111">Ottiene Sub-Items gli elementi secondari di un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="dc8d2-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="dc8d2-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="dc8d2-112">**Method**</span></span>|<span data-ttu-id="dc8d2-113">**URI richiesta**</span><span class="sxs-lookup"><span data-stu-id="dc8d2-113">**Request URI**</span></span>|<span data-ttu-id="dc8d2-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="dc8d2-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dc8d2-115">GET</span><span class="sxs-lookup"><span data-stu-id="dc8d2-115">GET</span></span>  <br/> |<span data-ttu-id="dc8d2-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}/subitem</span><span class="sxs-lookup"><span data-stu-id="dc8d2-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="dc8d2-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="dc8d2-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="dc8d2-118">**Parametri URI** - Nessuno.</span><span class="sxs-lookup"><span data-stu-id="dc8d2-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="dc8d2-119">**Intestazioni richiesta** - Nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="dc8d2-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="dc8d2-120">**Corpo della richiesta** - Nessuno.</span><span class="sxs-lookup"><span data-stu-id="dc8d2-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="dc8d2-121">**Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="dc8d2-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="dc8d2-122">**Codice di stato:** un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="dc8d2-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="dc8d2-123">Se non viene trovato un ID utente specificato, viene restituito il codice di stato 404 (Non trovato).</span><span class="sxs-lookup"><span data-stu-id="dc8d2-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="dc8d2-124">**Intestazioni risposta** - Nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="dc8d2-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="dc8d2-125">**Contenuto della risposta:** di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="dc8d2-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="dc8d2-126">Viene restituita una matrice di oggetti Item.</span><span class="sxs-lookup"><span data-stu-id="dc8d2-126">An array of Item object is returned.</span></span> 
  
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

<span data-ttu-id="dc8d2-127">L'oggetto Item restituito Sub-Items'operazione contiene solo i tre campi seguenti.</span><span class="sxs-lookup"><span data-stu-id="dc8d2-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="dc8d2-128">*itemId*  - ID dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="dc8d2-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="dc8d2-129">*userId*  - ID dell'utente proprietario dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="dc8d2-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="dc8d2-130">*type*  - Tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="dc8d2-130">*type*  - The type of the content.</span></span> <span data-ttu-id="dc8d2-131">Questo campo viene impostato dalle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="dc8d2-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="dc8d2-132">`Content` e i campi non sono inclusi nella risposta per ridurre la quantità di dati `subItems` trasmessi in rete.</span><span class="sxs-lookup"><span data-stu-id="dc8d2-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

