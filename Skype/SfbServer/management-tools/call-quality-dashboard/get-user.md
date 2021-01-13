---
title: Get User
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
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: "Riepilogo: informazioni su come ottenere l'operazione utente, che fa parte del servizio utente. Il servizio utente fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: dd2bb5e46ddbe3e65faf441a11e39cbc5429e473
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49832416"
---
# <a name="get-user"></a><span data-ttu-id="1e06f-105">Get User</span><span class="sxs-lookup"><span data-stu-id="1e06f-105">Get User</span></span>
 
<span data-ttu-id="1e06f-106">**Riepilogo:** Informazioni sull'operazione Get utente, che fa parte del servizio utente.</span><span class="sxs-lookup"><span data-stu-id="1e06f-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="1e06f-107">Il servizio utente fa parte dell'API del repository per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="1e06f-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="1e06f-108">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1e06f-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="1e06f-109">L'operazione Get Users fa parte del servizio utente nell'API del repository per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="1e06f-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="1e06f-110">Get User</span><span class="sxs-lookup"><span data-stu-id="1e06f-110">Get User</span></span>

<span data-ttu-id="1e06f-111">Get utente restituisce un record utente dall'archivio.</span><span class="sxs-lookup"><span data-stu-id="1e06f-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="1e06f-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="1e06f-112">**Method**</span></span>|<span data-ttu-id="1e06f-113">**URI della richiesta**</span><span class="sxs-lookup"><span data-stu-id="1e06f-113">**Request URI**</span></span>|<span data-ttu-id="1e06f-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="1e06f-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1e06f-115">GET</span><span class="sxs-lookup"><span data-stu-id="1e06f-115">GET</span></span>  <br/> |<span data-ttu-id="1e06f-116">https:// \<portal\> /QoERepositoryService/repository/User/{UserID}</span><span class="sxs-lookup"><span data-stu-id="1e06f-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="1e06f-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="1e06f-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="1e06f-118">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="1e06f-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="1e06f-119">**Intestazioni richieste** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="1e06f-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1e06f-120">**Corpo richiesta** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="1e06f-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="1e06f-121">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="1e06f-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="1e06f-122">**Codice di stato** -un'operazione completata restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="1e06f-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="1e06f-123">Se un ID utente specificato non viene trovato, restituisce il codice di stato 404 (non trovato).</span><span class="sxs-lookup"><span data-stu-id="1e06f-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="1e06f-124">**Intestazioni di risposta** -Nessun intestazioni aggiuntive.</span><span class="sxs-lookup"><span data-stu-id="1e06f-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="1e06f-125">**Corpo di risposta** -di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="1e06f-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="1e06f-126">*userid*  -ID dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1e06f-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="1e06f-127">*LoginName*  -identificazione utente esterno per utenti normali.</span><span class="sxs-lookup"><span data-stu-id="1e06f-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="1e06f-128">Se viene utilizzata l'autenticazione di Windows per l'autenticazione degli utenti, può trattarsi di un nome di dominio completo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="1e06f-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="1e06f-129">*defaultItemId*  -ID dell'elemento predefinito per questo utente.</span><span class="sxs-lookup"><span data-stu-id="1e06f-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="1e06f-130">L'elemento predefinito è l'elemento più in alto associato all'utente.</span><span class="sxs-lookup"><span data-stu-id="1e06f-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="1e06f-131">Tutti gli altri elementi posseduti dall'utente possono essere spostati dall'elemento predefinito.</span><span class="sxs-lookup"><span data-stu-id="1e06f-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1e06f-132">Specificare il  `defaultItemId` valore per ottenere l'operazione sugli elementi per recuperare i dettagli dell'elemento predefinito.</span><span class="sxs-lookup"><span data-stu-id="1e06f-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

