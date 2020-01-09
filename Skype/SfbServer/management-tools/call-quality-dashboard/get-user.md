---
title: Ottieni utente
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 52b89a4b-a0bd-493d-bb5e-e21904eb8e48
description: "Riepilogo: informazioni sull'operazione Get User, che fa parte del servizio utente. Il servizio utente fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 09dcbbaeaae98ed7b01f3d710cfda23aa5fa986f
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992623"
---
# <a name="get-user"></a><span data-ttu-id="a96d9-105">Ottieni utente</span><span class="sxs-lookup"><span data-stu-id="a96d9-105">Get User</span></span>
 
<span data-ttu-id="a96d9-106">**Riepilogo:** Informazioni sull'operazione Get User, che fa parte del servizio utente.</span><span class="sxs-lookup"><span data-stu-id="a96d9-106">**Summary:** Learn about the Get User operation, which is part of the User Service.</span></span> <span data-ttu-id="a96d9-107">Il servizio utente fa parte dell'API del repository per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="a96d9-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="a96d9-108">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a96d9-108">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a96d9-109">L'operazione Get Users fa parte del servizio utente nell'API del repository per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="a96d9-109">The Get Users operation is part of the User Service in the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="get-user"></a><span data-ttu-id="a96d9-110">Ottieni utente</span><span class="sxs-lookup"><span data-stu-id="a96d9-110">Get User</span></span>

<span data-ttu-id="a96d9-111">Get User restituisce un record utente dal repository.</span><span class="sxs-lookup"><span data-stu-id="a96d9-111">Get User returns a user record from the repository.</span></span>
  
|<span data-ttu-id="a96d9-112">**Metodo**</span><span class="sxs-lookup"><span data-stu-id="a96d9-112">**Method**</span></span>|<span data-ttu-id="a96d9-113">**URI di richiesta**</span><span class="sxs-lookup"><span data-stu-id="a96d9-113">**Request URI**</span></span>|<span data-ttu-id="a96d9-114">**Versione HTTP**</span><span class="sxs-lookup"><span data-stu-id="a96d9-114">**HTTP Version**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a96d9-115">Ottieni</span><span class="sxs-lookup"><span data-stu-id="a96d9-115">GET</span></span>  <br/> |<span data-ttu-id="a96d9-116">/QoERepositoryService/repository/User/{UserID}\<portale\>https://</span><span class="sxs-lookup"><span data-stu-id="a96d9-116">https://\<portal\>/QoERepositoryService/repository/user/{userId}</span></span>  <br/> |<span data-ttu-id="a96d9-117">HTTP/1.1</span><span class="sxs-lookup"><span data-stu-id="a96d9-117">HTTP/1.1</span></span>  <br/> |
   
 <span data-ttu-id="a96d9-118">**Parametri URI** -None.</span><span class="sxs-lookup"><span data-stu-id="a96d9-118">**URI Parameters** - None.</span></span>
  
 <span data-ttu-id="a96d9-119">**Richiedi intestazioni** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="a96d9-119">**Request Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a96d9-120">**Richiedi corpo** -nessuno.</span><span class="sxs-lookup"><span data-stu-id="a96d9-120">**Request Body** - None.</span></span>
  
 <span data-ttu-id="a96d9-121">**Risposta** : la risposta include un codice di stato HTTP e un set di intestazioni di risposta.</span><span class="sxs-lookup"><span data-stu-id="a96d9-121">**Response** - The response includes an HTTP status code and a set of response headers.</span></span>
  
 <span data-ttu-id="a96d9-122">**Codice di stato** : un'operazione riuscita restituisce il codice di stato 200 (OK).</span><span class="sxs-lookup"><span data-stu-id="a96d9-122">**Status Code** - A successful operation returns status code 200 (OK).</span></span> <span data-ttu-id="a96d9-123">Se non viene trovato un ID utente specificato, viene restituito il codice di stato 404 (non trovato).</span><span class="sxs-lookup"><span data-stu-id="a96d9-123">If a specified user ID is not found, it returns status code 404 (Not Found).</span></span>
  
 <span data-ttu-id="a96d9-124">**Intestazioni di risposta** -nessuna intestazione aggiuntiva.</span><span class="sxs-lookup"><span data-stu-id="a96d9-124">**Response Headers** - No additional headers.</span></span>
  
 <span data-ttu-id="a96d9-125">**Corpo risposta** : di seguito è riportato un payload di risposta di esempio in JSON.</span><span class="sxs-lookup"><span data-stu-id="a96d9-125">**Response Body** - Below is a sample response payload in JSON.</span></span>
  
```json
{
"userId": 0,
"loginName": "system",
"defaultItemId": 1655
}
```

 <span data-ttu-id="a96d9-126">*userid* -ID dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a96d9-126">*userId*  - ID of the user.</span></span>
  
 <span data-ttu-id="a96d9-127">*LoginName* -Identificativo utente esterno per utenti regolari.</span><span class="sxs-lookup"><span data-stu-id="a96d9-127">*loginName*  - External user identification for regular users.</span></span> <span data-ttu-id="a96d9-128">Se l'autenticazione di Windows viene usata per l'autenticazione degli utenti, può trattarsi di un nome di dominio completo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="a96d9-128">If Windows Authentication is used for authenticating users, then this may be a FQDN of the user.</span></span>
  
 <span data-ttu-id="a96d9-129">*defaultItemId* -ID dell'elemento predefinito per l'utente.</span><span class="sxs-lookup"><span data-stu-id="a96d9-129">*defaultItemId*  - ID of the default Item for this user.</span></span> <span data-ttu-id="a96d9-130">L'elemento predefinito è l'elemento in primo piano associato all'utente.</span><span class="sxs-lookup"><span data-stu-id="a96d9-130">The default Item is the top-most Item that is associated to the user.</span></span> <span data-ttu-id="a96d9-131">Tutti gli altri elementi posseduti dall'utente possono essere spostati dall'elemento predefinito.</span><span class="sxs-lookup"><span data-stu-id="a96d9-131">All other Items this user owns can be navigated from the default Item.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a96d9-132">Fornisci il `defaultItemId` valore per ottenere l'operazione Item per recuperare i dettagli dell'elemento predefinito.</span><span class="sxs-lookup"><span data-stu-id="a96d9-132">Supply the  `defaultItemId` value to Get Item operation to retrieve the details of the default Item.</span></span>
  

