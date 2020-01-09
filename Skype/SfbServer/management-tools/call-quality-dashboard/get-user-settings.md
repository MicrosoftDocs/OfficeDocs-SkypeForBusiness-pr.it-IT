---
title: Ottieni impostazioni utente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: "Riepilogo: informazioni sull'operazione Ottieni impostazioni utente, che fa parte del servizio impostazioni utente. Il servizio impostazioni utente fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 42934496b8b65132a67d4012d81d7b8997859726
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992633"
---
# <a name="get-user-settings"></a><span data-ttu-id="b75e2-105">Ottieni impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="b75e2-105">Get User Settings</span></span>
 
<span data-ttu-id="b75e2-106">**Riepilogo:** Informazioni sull'operazione Ottieni impostazioni utente, che fa parte del servizio impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="b75e2-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="b75e2-107">Il servizio impostazioni utente fa parte dell'API del repository per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="b75e2-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="b75e2-108">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="b75e2-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="b75e2-109">L'operazione Ottieni impostazioni utente fa parte del servizio impostazioni utente nell'API del repository per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="b75e2-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="b75e2-110">Ottieni impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="b75e2-110">Get User Settings</span></span>

<span data-ttu-id="b75e2-111">Ottieni impostazioni utente restituisce un elenco di impostazioni per un utente specificato.</span><span class="sxs-lookup"><span data-stu-id="b75e2-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="b75e2-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="b75e2-112">**Method**</span></span>|<span data-ttu-id="b75e2-113">**URI di richiesta**</span><span class="sxs-lookup"><span data-stu-id="b75e2-113">**Request URI**</span></span>|<span data-ttu-id="b75e2-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="b75e2-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b75e2-115">Ottieni</span><span class="sxs-lookup"><span data-stu-id="b75e2-115">GET</span></span>  <br/> |<span data-ttu-id="b75e2-116">/QoERepositoryService/repository/User/{UserID}/setting\<portale\>https://</span><span class="sxs-lookup"><span data-stu-id="b75e2-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="b75e2-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="b75e2-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="b75e2-118">**Parametri URI**</span><span class="sxs-lookup"><span data-stu-id="b75e2-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="b75e2-119">*effettivi* -facoltativo.</span><span class="sxs-lookup"><span data-stu-id="b75e2-119">*effective*  - Optional.</span></span> <span data-ttu-id="b75e2-120">Questo parametro si applica solo quando viene usato l'ID utente speciale default.</span><span class="sxs-lookup"><span data-stu-id="b75e2-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="b75e2-121">In altri casi verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="b75e2-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="b75e2-122">`True`Restituisce le impostazioni utente effettive e `false` restituisce solo le impostazioni utente (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="b75e2-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="b75e2-123">**Richiedi intestazioni** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="b75e2-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="b75e2-124">**Richiedi corpo** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="b75e2-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="b75e2-125">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="b75e2-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="b75e2-126">**Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="b75e2-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="b75e2-127">**Intestazioni di risposta** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="b75e2-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="b75e2-128">**Corpo risposta** : di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="b75e2-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
[{
"userId": 6,
"key": "ShowDescriptions",
"value": "true"
},
{
"userId": 6,
"key": "ShowTimeStamps",
"value": "true"
}]
```
