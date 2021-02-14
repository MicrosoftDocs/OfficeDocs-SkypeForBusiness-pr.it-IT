---
title: Clear Cache
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
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: "Riepilogo: informazioni sull'operazione Cancella cache, che fa parte dell'API dati per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: c9b966bb1e35a5a6255cd75ea6c685daaf220a09
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806416"
---
# <a name="clear-cache"></a><span data-ttu-id="20032-104">Clear Cache</span><span class="sxs-lookup"><span data-stu-id="20032-104">Clear Cache</span></span>
 
<span data-ttu-id="20032-105">**Riepilogo:** Informazioni sull'operazione Cancella cache, che fa parte dell'API dati per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="20032-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="20032-106">Call Quality Dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="20032-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="20032-107">L'operazione Cancella cache fa parte dell'API dati per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="20032-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="20032-108">Clear Cache</span><span class="sxs-lookup"><span data-stu-id="20032-108">Clear Cache</span></span>

<span data-ttu-id="20032-109">L'operazione Cancella cache elimina la cache sul server per query e dati.</span><span class="sxs-lookup"><span data-stu-id="20032-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="20032-110">In questo modo verrà reimpostata la cache e in seguito si otterrà nuovi dati dal cubo QoE per le nuove richieste.</span><span class="sxs-lookup"><span data-stu-id="20032-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="20032-111">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="20032-111">**Method**</span></span>|<span data-ttu-id="20032-112">**URI richiesta**</span><span class="sxs-lookup"><span data-stu-id="20032-112">**Request URI**</span></span>|<span data-ttu-id="20032-113">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="20032-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="20032-114">POST</span><span class="sxs-lookup"><span data-stu-id="20032-114">POST</span></span>  <br/> |<span data-ttu-id="20032-115">https:// \<portal\> /QoEDataService/ClearCache</span><span class="sxs-lookup"><span data-stu-id="20032-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="20032-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="20032-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="20032-117">**Parametri URI** - Nessuno.</span><span class="sxs-lookup"><span data-stu-id="20032-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="20032-118">**Intestazioni richiesta** - Nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="20032-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="20032-119">**Corpo della richiesta** - Nessuno.</span><span class="sxs-lookup"><span data-stu-id="20032-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="20032-120">**Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="20032-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="20032-121">**Codice di stato:** un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="20032-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="20032-122">**Intestazioni risposta** - Nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="20032-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="20032-123">**Corpo della risposta** - Nessuno.</span><span class="sxs-lookup"><span data-stu-id="20032-123">**Response Body** - None.</span></span>
  

