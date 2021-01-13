---
title: Get Users
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
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: "Riepilogo: informazioni sull'operazione Get Users, che fa parte del servizio utente. Il servizio utente fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: a830663fc97d8fda727d1ebb008d97407796cc7c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832426"
---
# <a name="get-users"></a><span data-ttu-id="9dfa5-105">Get Users</span><span class="sxs-lookup"><span data-stu-id="9dfa5-105">Get Users</span></span>
 
<span data-ttu-id="9dfa5-106">**Riepilogo:** Informazioni sull'operazione Get Users, che fa parte del servizio utente.</span><span class="sxs-lookup"><span data-stu-id="9dfa5-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="9dfa5-107">Il servizio utente fa parte dell'API del repository per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dfa5-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="9dfa5-108">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9dfa5-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="9dfa5-109">L'operazione Get Users fa parte del servizio utente nell'API del repository per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="9dfa5-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="9dfa5-110">Get Users</span><span class="sxs-lookup"><span data-stu-id="9dfa5-110">Get Users</span></span>

<span data-ttu-id="9dfa5-111">Ottenere gli utenti restituisce un elenco di utenti nel repository.</span><span class="sxs-lookup"><span data-stu-id="9dfa5-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="9dfa5-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="9dfa5-112">**Method**</span></span>|<span data-ttu-id="9dfa5-113">**URI della richiesta**</span><span class="sxs-lookup"><span data-stu-id="9dfa5-113">**Request URI**</span></span>|<span data-ttu-id="9dfa5-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="9dfa5-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9dfa5-115">GET</span><span class="sxs-lookup"><span data-stu-id="9dfa5-115">GET</span></span>  <br/> |<span data-ttu-id="9dfa5-116">https:// \<portal\> /QoERepositoryService/repository/User</span><span class="sxs-lookup"><span data-stu-id="9dfa5-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="9dfa5-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="9dfa5-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="9dfa5-118">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="9dfa5-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="9dfa5-119">**Intestazioni richieste** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="9dfa5-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9dfa5-120">**Corpo richiesta** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="9dfa5-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="9dfa5-121">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="9dfa5-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="9dfa5-122">**Codice di stato** -un'operazione completata restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="9dfa5-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="9dfa5-123">**Intestazioni di risposta** -Nessun intestazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="9dfa5-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="9dfa5-124">**Corpo di risposta** -di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="9dfa5-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9dfa5-125">Viene restituita una matrice di oggetti User.</span><span class="sxs-lookup"><span data-stu-id="9dfa5-125">An array of User objects is returned.</span></span> <span data-ttu-id="9dfa5-126">Per informazioni dettagliate sull'oggetto utente, vedere Get User.</span><span class="sxs-lookup"><span data-stu-id="9dfa5-126">For details about the User object, see Get User.</span></span> 
  
```json
[{
"userId": 0,
"loginName": "system",
"defaultItemId": 1652
},
{
"userId": 1,
"loginName": "SAMPLEDOMAIN\\testuser1",
"defaultItemId": 1652
},
{
"userId": 2,
"loginName": "SAMPLEDOMAIN\\testuser2",
"defaultItemId": 1774
}]
```


