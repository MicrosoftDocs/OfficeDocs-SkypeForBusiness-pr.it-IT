---
title: Get Items
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
ms.assetid: 9e189a48-4944-4f93-88d7-9d56b56770a6
description: "Riepilogo: informazioni sull'operazione get items, che fa parte del servizio elementi. Il servizio elementi fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 7da3ba77e782abe44896a7c1eb51a458d9a7e0b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832536"
---
# <a name="get-items"></a><span data-ttu-id="1e0a8-105">Get Items</span><span class="sxs-lookup"><span data-stu-id="1e0a8-105">Get Items</span></span>
 
<span data-ttu-id="1e0a8-106">**Riepilogo:** Informazioni sull'operazione get items, che fa parte del servizio elementi.</span><span class="sxs-lookup"><span data-stu-id="1e0a8-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="1e0a8-107">Il servizio elementi fa parte dell'API del repository per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="1e0a8-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="1e0a8-108">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1e0a8-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="1e0a8-109">L'operazione get items è parte del servizio elementi nell'API del repository per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="1e0a8-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="1e0a8-110">Get Items</span><span class="sxs-lookup"><span data-stu-id="1e0a8-110">Get Items</span></span>

<span data-ttu-id="1e0a8-111">Gli elementi Get restituiscono tutti gli elementi nell'archivio.</span><span class="sxs-lookup"><span data-stu-id="1e0a8-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="1e0a8-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="1e0a8-112">**Method**</span></span>|<span data-ttu-id="1e0a8-113">**URI della richiesta**</span><span class="sxs-lookup"><span data-stu-id="1e0a8-113">**Request URI**</span></span>|<span data-ttu-id="1e0a8-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="1e0a8-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1e0a8-115">GET</span><span class="sxs-lookup"><span data-stu-id="1e0a8-115">GET</span></span>  <br/> |<span data-ttu-id="1e0a8-116">https:// \<portal\> /QoERepositoryService/repository/Item</span><span class="sxs-lookup"><span data-stu-id="1e0a8-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="1e0a8-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="1e0a8-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="1e0a8-118">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="1e0a8-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="1e0a8-119">**Intestazioni richieste** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="1e0a8-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1e0a8-120">**Corpo richiesta** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="1e0a8-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="1e0a8-121">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="1e0a8-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="1e0a8-122">**Codice di stato** -un'operazione completata restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="1e0a8-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="1e0a8-123">**Intestazioni di risposta** -Nessun intestazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="1e0a8-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1e0a8-124">**Corpo di risposta** -di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="1e0a8-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e0a8-125">Viene restituita una matrice di oggetti Item.</span><span class="sxs-lookup"><span data-stu-id="1e0a8-125">An array of Item objects is returned.</span></span> <span data-ttu-id="1e0a8-126">Per informazioni dettagliate sull'oggetto Item, vedere Get Item.</span><span class="sxs-lookup"><span data-stu-id="1e0a8-126">For details about Item object, see Get Item.</span></span> 
  
```json
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
