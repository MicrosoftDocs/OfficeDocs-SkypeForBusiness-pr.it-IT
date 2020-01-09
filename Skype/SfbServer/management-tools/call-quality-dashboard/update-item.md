---
title: Aggiorna elemento
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b1c15c56-cdae-4f3e-838a-52f0940cf729
description: "Riepilogo: informazioni sull'operazione di aggiornamento degli elementi, che fa parte del servizio elemento. Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 55d21d1e1b8f3814dab7699ff864ba8fea1d23be
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991391"
---
# <a name="update-item"></a><span data-ttu-id="fb82c-105">Aggiorna elemento</span><span class="sxs-lookup"><span data-stu-id="fb82c-105">Update Item</span></span>
 
<span data-ttu-id="fb82c-106">**Riepilogo:** Informazioni sull'operazione degli elementi di aggiornamento, che fa parte del servizio elemento.</span><span class="sxs-lookup"><span data-stu-id="fb82c-106">**Summary:** Learn about the Update Item operation, which is part of the Item Service.</span></span> <span data-ttu-id="fb82c-107">Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="fb82c-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="fb82c-108">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fb82c-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="fb82c-109">L'operazione Update Item fa parte del servizio Item nell'API del repository per Call Quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="fb82c-109">The Update Item operation is part of the Item Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="update-item"></a><span data-ttu-id="fb82c-110">Aggiorna elemento</span><span class="sxs-lookup"><span data-stu-id="fb82c-110">Update Item</span></span>

<span data-ttu-id="fb82c-111">Aggiorna elemento aggiorna un elemento specifico nel repository.</span><span class="sxs-lookup"><span data-stu-id="fb82c-111">Update Item updates a specific item in the repository.</span></span>
  

|<span data-ttu-id="fb82c-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="fb82c-112">**Method**</span></span>|<span data-ttu-id="fb82c-113">**URI di richiesta**</span><span class="sxs-lookup"><span data-stu-id="fb82c-113">**Request URI**</span></span>|<span data-ttu-id="fb82c-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="fb82c-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fb82c-115">INSERIRE</span><span class="sxs-lookup"><span data-stu-id="fb82c-115">PUT</span></span>  <br/> |<span data-ttu-id="fb82c-116">/QoERepositoryService/repository/Item/{ItemId}\<portale\>https://</span><span class="sxs-lookup"><span data-stu-id="fb82c-116">https://\<portal\>/QoERepositoryService/repository/item/{itemId}</span></span>  <br/> |<span data-ttu-id="fb82c-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="fb82c-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="fb82c-118">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="fb82c-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="fb82c-119">**Richiedi intestazioni** -Content-Type: Application/JSON.</span><span class="sxs-lookup"><span data-stu-id="fb82c-119">**Request Headers** -Content-Type: application/json.</span></span>
  
 <span data-ttu-id="fb82c-120">**Richiedi Body** -JSON.</span><span class="sxs-lookup"><span data-stu-id="fb82c-120">**Request Body** - JSON.</span></span>
  
<span data-ttu-id="fb82c-121">Esempio di richiesta payload:</span><span class="sxs-lookup"><span data-stu-id="fb82c-121">Sample request payload:</span></span>
  
```json
{
  content : "{ 'Product' : 'New Product Name'",
  type: "application/json"
}
```

 <span data-ttu-id="fb82c-122">*contenuto*  Dati formattati JSON da archiviare come nuovo contenuto di un elemento secondario esistente.</span><span class="sxs-lookup"><span data-stu-id="fb82c-122">*content*  JSON formatted data to be stored as the new content of an existing sub-Item.</span></span> <span data-ttu-id="fb82c-123">Tecnicamente, un repository può archiviare qualsiasi contenuto di qualsiasi schema, ma se usato per il dashboard della qualità delle chiamate, dovrebbe essere un report o una query.</span><span class="sxs-lookup"><span data-stu-id="fb82c-123">Technically, a repository can store any content of any schema, but when used for Call Quality Dashboard, it should be either a report or a query.</span></span> <span data-ttu-id="fb82c-124">*digitare*  Specifica sempre "application/json" per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="fb82c-124">*type*  Always specify "application/json" for Call Quality Dashboard.</span></span>
  
 <span data-ttu-id="fb82c-125">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="fb82c-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="fb82c-126">**Codice di stato** : un'operazione riuscita restituisce il codice di stato 204 (nessun contenuto).</span><span class="sxs-lookup"><span data-stu-id="fb82c-126">**Status Code** - A successful operation returns status code 204 (No Content).</span></span> <span data-ttu-id="fb82c-127">Se non viene trovato un ID elemento specificato, viene restituito il codice di stato 404 (non trovato).</span><span class="sxs-lookup"><span data-stu-id="fb82c-127">If a specified item ID is not found, it returns status code 404 (Not Found).</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fb82c-128">"Nessun contenuto" non è uno stato di errore.</span><span class="sxs-lookup"><span data-stu-id="fb82c-128">"No Content" is not an error status.</span></span> <span data-ttu-id="fb82c-129">Significa che una risposta non ha restituito nulla nel corpo (al contrario, 200 OK restituisce il contenuto nel corpo).</span><span class="sxs-lookup"><span data-stu-id="fb82c-129">It means that a response did not return anything in the body (in contrast, 200 OK returns content in Body).</span></span> <span data-ttu-id="fb82c-130">Indica che l'elemento è stato aggiornato correttamente.</span><span class="sxs-lookup"><span data-stu-id="fb82c-130">It indicates that the Item was successfully updated.</span></span> 
  
 <span data-ttu-id="fb82c-131">**Intestazioni di risposta** -nessuna.</span><span class="sxs-lookup"><span data-stu-id="fb82c-131">**Response Headers** - None.</span></span>
  
 <span data-ttu-id="fb82c-132">**Corpo della risposta** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="fb82c-132">**Response Body** - None.</span></span>
  

