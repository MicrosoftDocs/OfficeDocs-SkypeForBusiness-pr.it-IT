---
title: Ottenere gli elementi
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: "Riepilogo: informazioni sull'operazione get items, che fa parte del servizio Item. Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: a1e7e8525df77cd5aacafb6d41316a985fbe9694
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186929"
---
# <a name="get-items"></a><span data-ttu-id="b742f-105">Ottenere gli elementi</span><span class="sxs-lookup"><span data-stu-id="b742f-105">Get Items</span></span>
 
<span data-ttu-id="b742f-106">**Riepilogo:** Informazioni sull'operazione get items, che fa parte del servizio Item.</span><span class="sxs-lookup"><span data-stu-id="b742f-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="b742f-107">Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="b742f-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="b742f-108">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b742f-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="b742f-109">L'operazione get items fa parte del servizio Item nell'API del repository per Call Quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="b742f-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="b742f-110">Ottenere gli elementi</span><span class="sxs-lookup"><span data-stu-id="b742f-110">Get Items</span></span>

<span data-ttu-id="b742f-111">Get Items restituisce tutti gli elementi del repository.</span><span class="sxs-lookup"><span data-stu-id="b742f-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="b742f-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="b742f-112">**Method**</span></span>|<span data-ttu-id="b742f-113">**URI di richiesta**</span><span class="sxs-lookup"><span data-stu-id="b742f-113">**Request URI**</span></span>|<span data-ttu-id="b742f-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="b742f-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b742f-115">Ottieni</span><span class="sxs-lookup"><span data-stu-id="b742f-115">GET</span></span>  <br/> |<span data-ttu-id="b742f-116">/QoERepositoryService/repository/Item\<portale\>https://</span><span class="sxs-lookup"><span data-stu-id="b742f-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="b742f-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="b742f-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="b742f-118">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="b742f-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="b742f-119">**Richiedi intestazioni** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="b742f-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b742f-120">**Richiedi corpo** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="b742f-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="b742f-121">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="b742f-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="b742f-122">**Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="b742f-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="b742f-123">**Intestazioni di risposta** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="b742f-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b742f-124">**Corpo risposta** : di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="b742f-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="b742f-125">Viene restituita una matrice di oggetti Item.</span><span class="sxs-lookup"><span data-stu-id="b742f-125">An array of Item objects is returned.</span></span> <span data-ttu-id="b742f-126">Per informazioni dettagliate sull'oggetto elemento, vedere ottenere un elemento.</span><span class="sxs-lookup"><span data-stu-id="b742f-126">For details about Item object, see Get Item.</span></span> 
  
```
[{
"itemId": 1652,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1653,
"userId": 0,
"type": "application/json"
},
{
"itemId": 1654,
"userId": 0,
"type": "application/json"
}]
```
