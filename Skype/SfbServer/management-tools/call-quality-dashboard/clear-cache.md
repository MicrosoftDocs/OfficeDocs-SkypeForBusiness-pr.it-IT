---
title: Cancellare la cache
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 08648b16-7a64-41d8-9577-5000a20fce46
description: "Riepilogo: informazioni sull'operazione Clear cache, che fa parte dell'API dati per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 38648e1a910f93a30bd6da8807321acad0330e62
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186983"
---
# <a name="clear-cache"></a><span data-ttu-id="b61b9-104">Cancellare la cache</span><span class="sxs-lookup"><span data-stu-id="b61b9-104">Clear Cache</span></span>
 
<span data-ttu-id="b61b9-105">**Riepilogo:** Informazioni sull'operazione Clear cache, che fa parte dell'API dati per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="b61b9-105">**Summary:** Learn about the Clear Cache operation, which is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="b61b9-106">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b61b9-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="b61b9-107">L'operazione Cancella cache fa parte dell'API dati per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="b61b9-107">The Clear Cache operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="clear-cache"></a><span data-ttu-id="b61b9-108">Cancellare la cache</span><span class="sxs-lookup"><span data-stu-id="b61b9-108">Clear Cache</span></span>

<span data-ttu-id="b61b9-109">Cancella operazione cache Elimina la cache sul server per query e dati.</span><span class="sxs-lookup"><span data-stu-id="b61b9-109">Clear Cache operation deletes the cache on server for queries and data.</span></span> <span data-ttu-id="b61b9-110">In questo modo verrà reimpostata la cache e in seguito verranno riprodotti nuovi dati dal cubo QoE per le nuove richieste.</span><span class="sxs-lookup"><span data-stu-id="b61b9-110">This will reset the cache and we will get fresh data from QoE Cube afterward for new requests.</span></span>
  

|<span data-ttu-id="b61b9-111">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="b61b9-111">**Method**</span></span>|<span data-ttu-id="b61b9-112">**URI di richiesta**</span><span class="sxs-lookup"><span data-stu-id="b61b9-112">**Request URI**</span></span>|<span data-ttu-id="b61b9-113">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="b61b9-113">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b61b9-114">Inserisci</span><span class="sxs-lookup"><span data-stu-id="b61b9-114">POST</span></span>  <br/> |<span data-ttu-id="b61b9-115">/QoEDataService/ClearCache\<portale\>https://</span><span class="sxs-lookup"><span data-stu-id="b61b9-115">https://\<portal\>/QoEDataService/ClearCache</span></span>  <br/> |<span data-ttu-id="b61b9-116">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="b61b9-116">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="b61b9-117">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="b61b9-117">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="b61b9-118">**Richiedi intestazioni** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="b61b9-118">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b61b9-119">**Richiedi corpo** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="b61b9-119">**Request Body** - None.</span></span>
  
 <span data-ttu-id="b61b9-120">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="b61b9-120">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="b61b9-121">**Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="b61b9-121">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="b61b9-122">**Intestazioni di risposta** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="b61b9-122">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="b61b9-123">**Corpo della risposta** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="b61b9-123">**Response Body** - None.</span></span>
  

