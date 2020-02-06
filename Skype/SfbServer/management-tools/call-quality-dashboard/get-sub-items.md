---
title: Ottieni elementi secondari
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
ms.assetid: 0542eba9-3dda-40de-bba8-095d22825e4e
description: "Riepilogo: informazioni sull'operazione Get Sub-Items, che fa parte del servizio Item. Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 523a6050065680550685337dabfec72c87f30bf7
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816765"
---
# <a name="get-sub-items"></a><span data-ttu-id="d84f8-105">Ottieni elementi secondari</span><span class="sxs-lookup"><span data-stu-id="d84f8-105">Get Sub-Items</span></span>
 
<span data-ttu-id="d84f8-106">**Riepilogo:** Informazioni sull'operazione Get Sub-Items, che fa parte del servizio Item.</span><span class="sxs-lookup"><span data-stu-id="d84f8-106">**Summary:** Learn about the Get Sub-Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="d84f8-107">Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="d84f8-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="d84f8-108">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d84f8-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="d84f8-109">L'operazione Get Sub-Items fa parte del servizio Item nell'API del repository per Call Quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="d84f8-109">The Get Sub-Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-sub-items"></a><span data-ttu-id="d84f8-110">Ottieni elementi secondari</span><span class="sxs-lookup"><span data-stu-id="d84f8-110">Get Sub-Items</span></span>

<span data-ttu-id="d84f8-111">Get Sub-Items restituisce gli elementi secondari di un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="d84f8-111">Get Sub-Items returns a specific Item's sub-items.</span></span>
  

|<span data-ttu-id="d84f8-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="d84f8-112">**Method**</span></span>|<span data-ttu-id="d84f8-113">**URI di richiesta**</span><span class="sxs-lookup"><span data-stu-id="d84f8-113">**Request URI**</span></span>|<span data-ttu-id="d84f8-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="d84f8-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d84f8-115">Ottieni</span><span class="sxs-lookup"><span data-stu-id="d84f8-115">GET</span></span>  <br/> |<span data-ttu-id="d84f8-116">/QoERepositoryService/repository/Item/{ItemId}/SubItem\<portale\>https://</span><span class="sxs-lookup"><span data-stu-id="d84f8-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}/subitem</span></span>  <br/> |<span data-ttu-id="d84f8-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="d84f8-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="d84f8-118">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="d84f8-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="d84f8-119">**Richiedi intestazioni** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="d84f8-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d84f8-120">**Richiedi corpo** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="d84f8-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="d84f8-121">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="d84f8-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="d84f8-122">**Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="d84f8-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="d84f8-123">Se non viene trovato un ID utente specificato, viene restituito il codice di stato 404 (non trovato).</span><span class="sxs-lookup"><span data-stu-id="d84f8-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="d84f8-124">**Intestazioni di risposta** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="d84f8-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="d84f8-125">**Corpo risposta** : di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="d84f8-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d84f8-126">Viene restituita una matrice di oggetto Item.</span><span class="sxs-lookup"><span data-stu-id="d84f8-126">An array of Item object is returned.</span></span> 
  
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

<span data-ttu-id="d84f8-127">L'oggetto Item restituito dall'operazione elementi secondari contiene solo i tre campi seguenti.</span><span class="sxs-lookup"><span data-stu-id="d84f8-127">The Item object returned by Sub-Items operation only contains the following three fields.</span></span> 
  
 <span data-ttu-id="d84f8-128">ID *ItemId* dell'elemento.</span><span class="sxs-lookup"><span data-stu-id="d84f8-128">*itemId*  - ID of the item.</span></span>
  
 <span data-ttu-id="d84f8-129">*userid* -ID dell'utente proprietario di questo elemento.</span><span class="sxs-lookup"><span data-stu-id="d84f8-129">*userId*  - ID of the User who owns this Item.</span></span>
  
 <span data-ttu-id="d84f8-130">*tipo* : il tipo di contenuto.</span><span class="sxs-lookup"><span data-stu-id="d84f8-130">*type*  - The type of the content.</span></span> <span data-ttu-id="d84f8-131">Questo campo è impostato dalle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="d84f8-131">This field is set by the applications.</span></span>
  
> [!NOTE]
>  <span data-ttu-id="d84f8-132">`Content`e `subItems` i campi non sono inclusi nella risposta per ridurre la quantità di dati trasmessi tramite la rete.</span><span class="sxs-lookup"><span data-stu-id="d84f8-132">`Content` and `subItems` fields are not included in the response to reduce the amount of data transmitted over the network.</span></span>
  

