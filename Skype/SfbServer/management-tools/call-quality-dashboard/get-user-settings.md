---
title: Ottenere impostazioni utente
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
ms.assetid: bdfe063b-e808-4f3c-884a-acbbabb9be0a
description: "Riepilogo: informazioni sull'operazione Get User Settings, che fa parte del servizio impostazioni utente. Il servizio impostazioni utente fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: e2ebf39ba5a7de5d36a8b1ea0441808b6e71f97b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832476"
---
# <a name="get-user-settings"></a><span data-ttu-id="26d27-105">Ottenere impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="26d27-105">Get User Settings</span></span>
 
<span data-ttu-id="26d27-106">**Riepilogo:** Informazioni sull'operazione Get User Settings, che fa parte del servizio impostazioni utente.</span><span class="sxs-lookup"><span data-stu-id="26d27-106">**Summary:** Learn about the Get User Settings operation, which is part of the User Settings Service.</span></span> <span data-ttu-id="26d27-107">Il servizio impostazioni utente fa parte dell'API del repository per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="26d27-107">The User Settings Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="26d27-108">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="26d27-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="26d27-109">L'operazione Ottieni impostazioni utente fa parte del servizio impostazioni utente nell'API del repository per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="26d27-109">The Get User Settings operation is part of the User Settings Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user-settings"></a><span data-ttu-id="26d27-110">Ottenere impostazioni utente</span><span class="sxs-lookup"><span data-stu-id="26d27-110">Get User Settings</span></span>

<span data-ttu-id="26d27-111">Ottenere le impostazioni utente restituisce un elenco di impostazioni per un utente specificato.</span><span class="sxs-lookup"><span data-stu-id="26d27-111">Get User Settings returns a list of settings for a specified user.</span></span>
  

|<span data-ttu-id="26d27-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="26d27-112">**Method**</span></span>|<span data-ttu-id="26d27-113">**URI della richiesta**</span><span class="sxs-lookup"><span data-stu-id="26d27-113">**Request URI**</span></span>|<span data-ttu-id="26d27-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="26d27-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="26d27-115">GET</span><span class="sxs-lookup"><span data-stu-id="26d27-115">GET</span></span>  <br/> |<span data-ttu-id="26d27-116">https:// \<portal\> /QoERepositoryService/repository/User/{UserID}/setting</span><span class="sxs-lookup"><span data-stu-id="26d27-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}/setting</span></span>  <br/> |<span data-ttu-id="26d27-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="26d27-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="26d27-118">**Parametri URI**</span><span class="sxs-lookup"><span data-stu-id="26d27-118">**URI Parameters**</span></span>
  
- <span data-ttu-id="26d27-119">*efficace*  -facoltativo.</span><span class="sxs-lookup"><span data-stu-id="26d27-119">*effective*  - Optional.</span></span> <span data-ttu-id="26d27-120">Questo parametro si applica solo quando viene utilizzato il valore predefinito dell'ID utente speciale.</span><span class="sxs-lookup"><span data-stu-id="26d27-120">This parameter applies only when the special user ID default is used.</span></span> <span data-ttu-id="26d27-121">In altri casi, verrà ignorato.</span><span class="sxs-lookup"><span data-stu-id="26d27-121">In other cases, it will be ignored.</span></span> <span data-ttu-id="26d27-122">`True` restituisce impostazioni utente effettive e `false` restituisce solo le impostazioni utente (impostazione predefinita).</span><span class="sxs-lookup"><span data-stu-id="26d27-122">`True` returns effective user settings and `false` returns just user settings (default).</span></span>
    
  <span data-ttu-id="26d27-123">**Intestazioni richieste** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="26d27-123">**Request Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="26d27-124">**Corpo richiesta** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="26d27-124">**Request Body** - None.</span></span>
  
  <span data-ttu-id="26d27-125">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="26d27-125">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
  <span data-ttu-id="26d27-126">**Codice di stato** -un'operazione completata restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="26d27-126">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
  <span data-ttu-id="26d27-127">**Intestazioni di risposta** -Nessun intestazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="26d27-127">**Response Headers** - No additional headers.</span></span>
  
  <span data-ttu-id="26d27-128">**Corpo di risposta** -di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="26d27-128">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
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
