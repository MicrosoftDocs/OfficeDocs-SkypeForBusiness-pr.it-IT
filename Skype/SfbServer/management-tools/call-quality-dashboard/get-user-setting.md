---
title: Ottenere impostazione utente
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
ms.assetid: 16611a55-79fb-487a-a936-20caca829f87
description: "Riepilogo: informazioni sull'operazione Get User Setting, che fa parte del servizio impostazioni utente. Il servizio impostazioni utente fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 82632f5de7ae215d6f34d9f0b39e500fb713a1be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832486"
---
# <a name="get-user-setting"></a><span data-ttu-id="63aa2-105">Ottenere impostazione utente</span><span class="sxs-lookup"><span data-stu-id="63aa2-105">Get User Setting</span></span>
 
<span data-ttu-id="63aa2-106">**Riepilogo:** Informazioni sull'operazione Ottieni impostazione utente, che fa parte del servizio impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="63aa2-106">**Summary:** Learn about the Get User Setting operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="63aa2-107">Il servizio impostazioni utente fa parte dell'API repository per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="63aa2-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="63aa2-108">Call Quality Dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="63aa2-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="63aa2-109">L'operazione Get User Setting fa parte del servizio impostazioni utente nell'API repository per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="63aa2-109">The Get User Setting operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-setting"></a><span data-ttu-id="63aa2-110">Ottenere impostazione utente</span><span class="sxs-lookup"><span data-stu-id="63aa2-110">Get User Setting</span></span>

<span data-ttu-id="63aa2-111">Get User Setting restituisce un'impostazione utente singola.</span><span class="sxs-lookup"><span data-stu-id="63aa2-111">Get User Setting returns a single user setting.</span></span>
  

|<span data-ttu-id="63aa2-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="63aa2-112">**Method**</span></span>|<span data-ttu-id="63aa2-113">**URI richiesta**</span><span class="sxs-lookup"><span data-stu-id="63aa2-113">**Request URI**</span></span>|<span data-ttu-id="63aa2-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="63aa2-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="63aa2-115">GET</span><span class="sxs-lookup"><span data-stu-id="63aa2-115">GET</span></span>  <br/> |<span data-ttu-id="63aa2-116">https:// \<portal\> /QoERepositoryService/repository/user/{userId}/setting/{key}</span><span class="sxs-lookup"><span data-stu-id="63aa2-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting/{key}</span></span>  <br/> |<span data-ttu-id="63aa2-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="63aa2-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="63aa2-118">**Parametri URI** - Nessuno.</span><span class="sxs-lookup"><span data-stu-id="63aa2-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="63aa2-119">**Intestazioni richiesta** - Nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="63aa2-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="63aa2-120">**Corpo della richiesta** - Nessuno.</span><span class="sxs-lookup"><span data-stu-id="63aa2-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="63aa2-121">**Risposta:** la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="63aa2-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="63aa2-122">**Codice di stato:** un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="63aa2-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="63aa2-123">**Intestazioni risposta** - Nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="63aa2-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="63aa2-124">**Contenuto della risposta:** di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="63aa2-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
}
```

 <span data-ttu-id="63aa2-125">*userId*  - ID dell'utente.</span><span class="sxs-lookup"><span data-stu-id="63aa2-125">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="63aa2-126">*key*  - Chiave dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="63aa2-126">*key*  - Key of the setting.</span></span>
  
 <span data-ttu-id="63aa2-127">*value*  - Valore dell'impostazione.</span><span class="sxs-lookup"><span data-stu-id="63aa2-127">*value*  - Value of the setting.</span></span>
  

