---
title: Get Dimension Members
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
ms.assetid: bd89bbf7-cb98-4cd8-bbfa-0484663d14db
description: "Riepilogo: informazioni sull'operazione Get Dimension Members. L'operazione Get Dimension Members fa parte dell'API dei dati per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: ffec3b02a3c876a003adb679a28b0e8f2edb91c2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832636"
---
# <a name="get-dimension-members"></a><span data-ttu-id="4a62c-105">Get Dimension Members</span><span class="sxs-lookup"><span data-stu-id="4a62c-105">Get Dimension Members</span></span>
 
<span data-ttu-id="4a62c-106">**Riepilogo:** Informazioni sull'operazione Get Dimension Members.</span><span class="sxs-lookup"><span data-stu-id="4a62c-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="4a62c-107">L'operazione Get Dimension Members fa parte dell'API dei dati per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="4a62c-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="4a62c-108">Call Quality Dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4a62c-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="4a62c-109">L'operazione Get Dimension Members fa parte dell'API dei dati per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="4a62c-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="4a62c-110">Get Dimension Members</span><span class="sxs-lookup"><span data-stu-id="4a62c-110">Get Dimension Members</span></span>

<span data-ttu-id="4a62c-111">L'operazione Get Dimension Members restituisce l'elenco dei membri di una dimensione specifica.</span><span class="sxs-lookup"><span data-stu-id="4a62c-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="4a62c-112">Consente inoltre di filtrare l'elenco dei membri e ottenere un sottoinsieme, per ridurre il costo del trasferimento bancario.</span><span class="sxs-lookup"><span data-stu-id="4a62c-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="4a62c-113">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="4a62c-113">**Method**</span></span>|<span data-ttu-id="4a62c-114">**URI richiesta**</span><span class="sxs-lookup"><span data-stu-id="4a62c-114">**Request URI**</span></span>|<span data-ttu-id="4a62c-115">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="4a62c-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="4a62c-116">POST</span><span class="sxs-lookup"><span data-stu-id="4a62c-116">POST</span></span>  <br/> |<span data-ttu-id="4a62c-117">https:// \<portal\> /QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="4a62c-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="4a62c-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="4a62c-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="4a62c-119">**Parametri URI** - Nessuno.</span><span class="sxs-lookup"><span data-stu-id="4a62c-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="4a62c-120">**Intestazioni richiesta** - Nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="4a62c-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4a62c-121">**Corpo della** richiesta: contiene il nome della dimensione per cui si desiderano i membri.</span><span class="sxs-lookup"><span data-stu-id="4a62c-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="4a62c-122">Oltre al numero massimo di membri restituiti, è possibile specificare un filtro per limitare i membri restituiti.</span><span class="sxs-lookup"><span data-stu-id="4a62c-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
```json
{
"ByPassCache": false,
"DataModelName": "[StartDate].[Month]",
"SearchCaption": "",
"SearchValue": "",
"PageNumber": 0,
"PageSize": 8000
}
```

 <span data-ttu-id="4a62c-123">**Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="4a62c-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="4a62c-124">**Codice di stato:** un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="4a62c-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="4a62c-125">**Intestazioni risposta** - Nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="4a62c-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="4a62c-126">**Corpo della risposta:** di seguito è riportato un payload di risposta di esempio in JSON in risposta a una richiesta di "[StartDate]. Dimensione [Month]".</span><span class="sxs-lookup"><span data-stu-id="4a62c-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="4a62c-127">L'elenco mostra solo una piccola parte dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="4a62c-127">The list is only showing a small portion of the list.</span></span> 
  
```json
{
"MembersCount": 493,
"Members": [["[1990-01-01T00:00:00]",
"January 1990"],
["[1990-02-01T00:00:00]",
"February 1990"],
["[1990-03-01T00:00:00]",
"March 1990"],
 
    ...
    
["[2030-10-01T00:00:00]",
"October 2030"],
["[2030-11-01T00:00:00]",
"November 2030"],
["[2030-12-01T00:00:00]",
"December 2030"],
["[2031-01-01T00:00:00]",
"January 2031"]]
}
```
