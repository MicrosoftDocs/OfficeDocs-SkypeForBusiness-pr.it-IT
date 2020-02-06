---
title: Ottieni impostazione utente
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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: "Riepilogo: informazioni sull'operazione Get User setting, che fa parte del servizio impostazioni utente. Il servizio impostazioni utente fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 4ab9d4d718a2ff411db72f38b59a758523935504
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816755"
---
# <a name="get-user-setting"></a><span data-ttu-id="9428c-105">Ottieni impostazione utente</span><span class="sxs-lookup"><span data-stu-id="9428c-105">Get User Setting</span></span>
 
<span data-ttu-id="9428c-106">**Riepilogo:** Informazioni sull'operazione Get User setting, che fa parte del servizio impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="9428c-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="9428c-107">Il servizio impostazioni utente fa parte dell'API del repository per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="9428c-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="9428c-108">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9428c-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="9428c-109">L'operazione Get User Setting fa parte del servizio impostazioni utente nell'API del repository per Call Quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="9428c-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="9428c-110">Ottieni impostazione utente</span><span class="sxs-lookup"><span data-stu-id="9428c-110">Get User Setting</span></span>

<span data-ttu-id="9428c-111">Per ottenere l'impostazione utente viene restituita una singola impostazione utente.</span><span class="sxs-lookup"><span data-stu-id="9428c-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="9428c-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="9428c-112">**Method**</span></span>|<span data-ttu-id="9428c-113">**URI di richiesta**</span><span class="sxs-lookup"><span data-stu-id="9428c-113">**Request URI**</span></span>|<span data-ttu-id="9428c-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="9428c-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9428c-115">Ottieni</span><span class="sxs-lookup"><span data-stu-id="9428c-115">GET</span></span>  <br/> |<span data-ttu-id="9428c-116">/QoERepositoryService/repository/User/{UserID}/setting/{Key}\<portale\>https://</span><span class="sxs-lookup"><span data-stu-id="9428c-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="9428c-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="9428c-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9428c-118">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="9428c-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="9428c-119">**Richiedi intestazioni** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="9428c-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9428c-120">**Richiedi corpo** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="9428c-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="9428c-121">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="9428c-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="9428c-122">**Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="9428c-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="9428c-123">**Intestazioni di risposta** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="9428c-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9428c-124">**Corpo risposta** : di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="9428c-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="9428c-125">*userid* -ID dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9428c-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="9428c-126">tasto *chiave* dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="9428c-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="9428c-127">*valore-valore* dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="9428c-127">*value*  - Value of the setting.</span></span>
  

