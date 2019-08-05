---
title: Ottenere gli utenti
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 87d34baf-4c31-468d-b8f7-4faca0bc7a54
description: "Riepilogo: informazioni sull'operazione Get Users, che fa parte del servizio utente. Il servizio utente fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 22223c37dad39f171afc27eb9e0520b8b32335c5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186887"
---
# <a name="get-users"></a><span data-ttu-id="a6657-105">Ottenere gli utenti</span><span class="sxs-lookup"><span data-stu-id="a6657-105">Get Users</span></span>
 
<span data-ttu-id="a6657-106">**Riepilogo:** Informazioni sull'operazione Get Users, che fa parte del servizio utente.</span><span class="sxs-lookup"><span data-stu-id="a6657-106">**Summary:** Learn about the Get Users operation, which is part of the User Service.</span></span> <span data-ttu-id="a6657-107">Il servizio utente fa parte dell'API del repository per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="a6657-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="a6657-108">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a6657-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a6657-109">L'operazione Get Users fa parte del servizio utente nell'API del repository per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="a6657-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-users"></a><span data-ttu-id="a6657-110">Ottenere gli utenti</span><span class="sxs-lookup"><span data-stu-id="a6657-110">Get Users</span></span>

<span data-ttu-id="a6657-111">Ottenere gli utenti restituisce un elenco di utenti nel repository.</span><span class="sxs-lookup"><span data-stu-id="a6657-111">Get Users returns a list of users in the repository.</span></span>
  
|<span data-ttu-id="a6657-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="a6657-112">**Method**</span></span>|<span data-ttu-id="a6657-113">**URI di richiesta**</span><span class="sxs-lookup"><span data-stu-id="a6657-113">**Request URI**</span></span>|<span data-ttu-id="a6657-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="a6657-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a6657-115">Ottieni</span><span class="sxs-lookup"><span data-stu-id="a6657-115">GET</span></span>  <br/> |<span data-ttu-id="a6657-116">/QoERepositoryService/repository/user\<portale\>https://</span><span class="sxs-lookup"><span data-stu-id="a6657-116">https://\<portal\>/QoERepositoryService/repository/user</span></span>  <br/> |<span data-ttu-id="a6657-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="a6657-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="a6657-118">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="a6657-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="a6657-119">**Richiedi intestazioni** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="a6657-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a6657-120">**Richiedi corpo** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="a6657-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="a6657-121">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="a6657-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="a6657-122">**Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="a6657-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span>
  
 <span data-ttu-id="a6657-123">**Intestazioni di risposta** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="a6657-123">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a6657-124">**Corpo risposta** : di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="a6657-124">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a6657-125">Viene restituita una matrice di oggetti User.</span><span class="sxs-lookup"><span data-stu-id="a6657-125">An array of User objects is returned.</span></span> <span data-ttu-id="a6657-126">Per informazioni dettagliate sull'oggetto utente, vedere ottenere l'utente.</span><span class="sxs-lookup"><span data-stu-id="a6657-126">For details about the User object, see Get User.</span></span> 
  
```
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


