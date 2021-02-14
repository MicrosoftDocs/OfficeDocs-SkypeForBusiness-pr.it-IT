---
title: Update Item
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
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: "Riepilogo: informazioni sull'operazione Update Item, che fa parte di Item Service. Item Service fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 78da2fa414b4ba266f9e6aba4feac5ff73150062
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803086"
---
# <a name="update-item"></a><span data-ttu-id="a6ae7-105">Update Item</span><span class="sxs-lookup"><span data-stu-id="a6ae7-105">Update Item</span></span>
 
<span data-ttu-id="a6ae7-106">**Riepilogo:** Informazioni sull'operazione Update Item, che fa parte di Item Service.</span><span class="sxs-lookup"><span data-stu-id="a6ae7-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="a6ae7-107">Item Service fa parte dell'API repository per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="a6ae7-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="a6ae7-108">Call Quality Dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a6ae7-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a6ae7-109">L'operazione Update Item fa parte di Item Service nell'API repository per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="a6ae7-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="a6ae7-110">Update Item</span><span class="sxs-lookup"><span data-stu-id="a6ae7-110">Update Item</span></span>

<span data-ttu-id="a6ae7-111">Update Item aggiorna un elemento specifico nel repository.</span><span class="sxs-lookup"><span data-stu-id="a6ae7-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="a6ae7-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="a6ae7-112">**Method**</span></span>|<span data-ttu-id="a6ae7-113">**URI richiesta**</span><span class="sxs-lookup"><span data-stu-id="a6ae7-113">**Request URI**</span></span>|<span data-ttu-id="a6ae7-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="a6ae7-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a6ae7-115">PUT</span><span class="sxs-lookup"><span data-stu-id="a6ae7-115">PUT</span></span>  <br/> |<span data-ttu-id="a6ae7-116">https:// \<portal\> /QoERepositoryService/repository/item/{itemId}</span><span class="sxs-lookup"><span data-stu-id="a6ae7-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="a6ae7-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="a6ae7-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="a6ae7-118">**Parametri URI** - Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a6ae7-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="a6ae7-119">**Request Headers** -Content-Type: application/json.</span><span class="sxs-lookup"><span data-stu-id="a6ae7-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="a6ae7-120">**Corpo della richiesta** - JSON.</span><span class="sxs-lookup"><span data-stu-id="a6ae7-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="a6ae7-121">Payload della richiesta di esempio:</span><span class="sxs-lookup"><span data-stu-id="a6ae7-121">Sample request payload:</span></span>
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="a6ae7-122">*content*  Dati in formato JSON da archiviare come nuovo contenuto di un elemento secondario esistente.</span><span class="sxs-lookup"><span data-stu-id="a6ae7-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="a6ae7-123">Tecnicamente, un repository può archiviare qualsiasi contenuto di qualsiasi schema, ma se usato per Call Quality Dashboard, deve essere un report o una query.</span><span class="sxs-lookup"><span data-stu-id="a6ae7-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="a6ae7-124">*type*  Specificare sempre "application/json" per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="a6ae7-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="a6ae7-125">**Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="a6ae7-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="a6ae7-126">**Codice di stato:** un'operazione riuscita restituisce il codice di stato 204 (Nessun contenuto).</span><span class="sxs-lookup"><span data-stu-id="a6ae7-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="a6ae7-127">Se non viene trovato un ID elemento specificato, viene restituito il codice di stato 404 (Non trovato).</span><span class="sxs-lookup"><span data-stu-id="a6ae7-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="a6ae7-128">Lo stato "Nessun contenuto" non è uno stato di errore.</span><span class="sxs-lookup"><span data-stu-id="a6ae7-128">"No Content" is not an error status.</span></span> <span data-ttu-id="a6ae7-129">Significa che una risposta non ha restituito nulla nel corpo (al contrario, 200 OK restituisce il contenuto nel corpo).</span><span class="sxs-lookup"><span data-stu-id="a6ae7-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="a6ae7-130">Indica che l'elemento è stato aggiornato correttamente.</span><span class="sxs-lookup"><span data-stu-id="a6ae7-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="a6ae7-131">**Intestazioni risposta** - Nessuna.</span><span class="sxs-lookup"><span data-stu-id="a6ae7-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="a6ae7-132">**Corpo della risposta** - Nessuno.</span><span class="sxs-lookup"><span data-stu-id="a6ae7-132">**Response Body** - None.</span></span>
  

