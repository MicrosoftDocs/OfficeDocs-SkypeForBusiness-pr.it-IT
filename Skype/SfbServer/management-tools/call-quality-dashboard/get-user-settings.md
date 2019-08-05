---
title: Ottenere le impostazioni utente
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
ms.openlocfilehash: 8d1bb1da9e9a186cbc10f0c8ba36275348bb7267
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186893"
---
# <a name="get-user-settings"></a><span data-ttu-id="57e11-105">Ottenere le impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="57e11-105">Get User Settings</span></span>
 
<span data-ttu-id="57e11-106">**Riepilogo:** Informazioni sull'operazione Ottieni impostazioni utente, che fa parte del servizio impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="57e11-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="57e11-107">Il servizio impostazioni utente fa parte dell'API del repository per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="57e11-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="57e11-108">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="57e11-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="57e11-109">L'operazione Ottieni impostazioni utente fa parte del servizio impostazioni utente nell'API del repository per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="57e11-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="57e11-110">Ottenere le impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="57e11-110">Get User Settings</span></span>

<span data-ttu-id="57e11-111">Ottieni impostazioni utente restituisce un elenco di impostazioni per un utente specificato.</span><span class="sxs-lookup"><span data-stu-id="57e11-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="57e11-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="57e11-112">**Method**</span></span>|<span data-ttu-id="57e11-113">**URI di richiesta**</span><span class="sxs-lookup"><span data-stu-id="57e11-113">**Request URI**</span></span>|<span data-ttu-id="57e11-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="57e11-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="57e11-115">Ottieni</span><span class="sxs-lookup"><span data-stu-id="57e11-115">GET</span></span>  <br/> |<span data-ttu-id="57e11-116">/QoERepositoryService/repository/User/{UserID}/setting\<portale\>https://</span><span class="sxs-lookup"><span data-stu-id="57e11-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="57e11-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="57e11-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="57e11-118">**Parametri URI**</span><span class="sxs-lookup"><span data-stu-id="57e11-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="57e11-119">*effettivi* -facoltativo.</span><span class="sxs-lookup"><span data-stu-id="57e11-119">*effective*  - Optional.</span></span> <span data-ttu-id="57e11-120">Questo parametro si applica solo quando viene usato l'ID utente speciale default.</span><span class="sxs-lookup"><span data-stu-id="57e11-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="57e11-121">In altri casi verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="57e11-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="57e11-122">`True`Restituisce le impostazioni utente effettive e `false` restituisce solo le impostazioni utente (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="57e11-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="57e11-123">**Richiedi intestazioni** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="57e11-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="57e11-124">**Richiedi corpo** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="57e11-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="57e11-125">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="57e11-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="57e11-126">**Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="57e11-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="57e11-127">**Intestazioni di risposta** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="57e11-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="57e11-128">**Corpo risposta** : di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="57e11-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```
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
