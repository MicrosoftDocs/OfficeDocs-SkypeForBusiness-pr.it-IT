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
description: "Riepilogo: informazioni sull'operazione Get Items, che fa parte di Item Service. Item Service fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 7da3ba77e782abe44896a7c1eb51a458d9a7e0b8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832536"
---
# <a name="get-items"></a><span data-ttu-id="a4b06-105">Get Items</span><span class="sxs-lookup"><span data-stu-id="a4b06-105">Get Items</span></span>
 
<span data-ttu-id="a4b06-106">**Riepilogo:** Informazioni sull'operazione Get Items, che fa parte di Item Service.</span><span class="sxs-lookup"><span data-stu-id="a4b06-106">**Summary:** Learn about the Get Items operation, which is part of the Item Service.</span></span> <span data-ttu-id="a4b06-107">Item Service fa parte dell'API repository per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="a4b06-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="a4b06-108">Call Quality Dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a4b06-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a4b06-109">L'operazione Get Items fa parte di Item Service nell'API repository per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="a4b06-109">The Get Items operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-items"></a><span data-ttu-id="a4b06-110">Get Items</span><span class="sxs-lookup"><span data-stu-id="a4b06-110">Get Items</span></span>

<span data-ttu-id="a4b06-111">Il metodo Get Items restituisce tutti gli elementi nel repository.</span><span class="sxs-lookup"><span data-stu-id="a4b06-111">Get Items returns all Items in the repository.</span></span>
  
|<span data-ttu-id="a4b06-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="a4b06-112">**Method**</span></span>|<span data-ttu-id="a4b06-113">**URI richiesta**</span><span class="sxs-lookup"><span data-stu-id="a4b06-113">**Request URI**</span></span>|<span data-ttu-id="a4b06-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="a4b06-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a4b06-115">GET</span><span class="sxs-lookup"><span data-stu-id="a4b06-115">GET</span></span>  <br/> |<span data-ttu-id="a4b06-116">https:// \<portal\> /QoERepositoryService/repository/item</span><span class="sxs-lookup"><span data-stu-id="a4b06-116">https://\<portal\>/QoERepositoryService/repository/item</span></span>  <br/> |<span data-ttu-id="a4b06-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="a4b06-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="a4b06-118">**Parametri URI** - Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a4b06-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="a4b06-119">**Intestazioni richiesta** - Nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="a4b06-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a4b06-120">**Corpo della richiesta** - Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a4b06-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="a4b06-121">**Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="a4b06-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="a4b06-122">**Codice di stato:** un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="a4b06-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="a4b06-123">**Intestazioni risposta** - Nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="a4b06-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a4b06-124">**Contenuto della risposta:** di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="a4b06-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a4b06-125">Viene restituita una matrice di oggetti Item.</span><span class="sxs-lookup"><span data-stu-id="a4b06-125">An array of Item objects is returned.</span></span> <span data-ttu-id="a4b06-126">Per informazioni dettagliate sull'oggetto Item, vedere Get Item.</span><span class="sxs-lookup"><span data-stu-id="a4b06-126">For details about Item object, see Get Item.</span></span> 
  
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
