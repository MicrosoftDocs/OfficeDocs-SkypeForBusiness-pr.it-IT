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
description: "Riepilogo: informazioni sull'operazione ottenere membri della dimensione. L'operazione get Members Dimension fa parte dell'API Data per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: ffec3b02a3c876a003adb679a28b0e8f2edb91c2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832636"
---
# <a name="get-dimension-members"></a><span data-ttu-id="71c62-105">Get Dimension Members</span><span class="sxs-lookup"><span data-stu-id="71c62-105">Get Dimension Members</span></span>
 
<span data-ttu-id="71c62-106">**Riepilogo:** Informazioni sull'operazione Get Dimension members.</span><span class="sxs-lookup"><span data-stu-id="71c62-106">**Summary:** Learn about the Get Dimension Members operation.</span></span> <span data-ttu-id="71c62-107">L'operazione get Members Dimension fa parte dell'API Data per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="71c62-107">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span> <span data-ttu-id="71c62-108">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="71c62-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="71c62-109">L'operazione get Members Dimension fa parte dell'API Data per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="71c62-109">The Get Dimension Members operation is part of the Data API for Call Quality Dashboard.</span></span>
  
## <a name="get-dimension-members"></a><span data-ttu-id="71c62-110">Get Dimension Members</span><span class="sxs-lookup"><span data-stu-id="71c62-110">Get Dimension Members</span></span>

<span data-ttu-id="71c62-111">Get Dimension members Operation restituisce l'elenco dei membri di una dimensione specifica.</span><span class="sxs-lookup"><span data-stu-id="71c62-111">Get Dimension Members operation returns the list of members of a specific dimension.</span></span> <span data-ttu-id="71c62-112">È inoltre possibile filtrare l'elenco dei membri e ottenere un sottoinsieme, per ridurre il costo di trasferimento dei cavi.</span><span class="sxs-lookup"><span data-stu-id="71c62-112">It also give the ability to filter the member list and get a subset, to reduce the wire transfer cost.</span></span>
  

|<span data-ttu-id="71c62-113">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="71c62-113">**Method**</span></span>|<span data-ttu-id="71c62-114">**URI della richiesta**</span><span class="sxs-lookup"><span data-stu-id="71c62-114">**Request URI**</span></span>|<span data-ttu-id="71c62-115">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="71c62-115">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="71c62-116">POST</span><span class="sxs-lookup"><span data-stu-id="71c62-116">POST</span></span>  <br/> |<span data-ttu-id="71c62-117">https:// \<portal\> /QoEDataService/DimensionMembers</span><span class="sxs-lookup"><span data-stu-id="71c62-117">https://\<portal\>/QoEDataService/DimensionMembers</span></span>  <br/> |<span data-ttu-id="71c62-118">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="71c62-118">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="71c62-119">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="71c62-119">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="71c62-120">**Intestazioni richieste** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="71c62-120">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="71c62-121">**Corpo richiesta** : contiene il nome della dimensione a cui vogliamo i membri.</span><span class="sxs-lookup"><span data-stu-id="71c62-121">**Request Body** - This contains the name of dimension we want the members for.</span></span> <span data-ttu-id="71c62-122">Anche il numero massimo di membri restituiti, accanto a è possibile specificare un filtro per limitare i membri restituiti.</span><span class="sxs-lookup"><span data-stu-id="71c62-122">Also max number of members returned, beside you can specify some filtering to limit the returned members.</span></span>
  
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

 <span data-ttu-id="71c62-123">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="71c62-123">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="71c62-124">**Codice di stato** -un'operazione completata restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="71c62-124">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="71c62-125">**Intestazioni di risposta** -Nessun intestazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="71c62-125">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="71c62-126">**Corpo di risposta** -di seguito è riportato un payload di risposta di esempio in JSON in risposta a una richiesta per "[StartDate]. [Month] "Dimension.</span><span class="sxs-lookup"><span data-stu-id="71c62-126">**Response Body** - Below is a sample response payload in JSON in response to a request for "[StartDate].[Month]" dimension.</span></span>
  
> [!NOTE]
> <span data-ttu-id="71c62-127">L'elenco Mostra solo una piccola parte dell'elenco.</span><span class="sxs-lookup"><span data-stu-id="71c62-127">The list is only showing a small portion of the list.</span></span> 
  
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
