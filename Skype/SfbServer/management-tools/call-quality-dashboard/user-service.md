---
title: Servizio utente per CQD
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
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: "Riepilogo: informazioni sul servizio utente, che fa parte dell'API del repository per il dashboard qualità chiamata. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: d9f4b771a1bf5efeece4f8fb87195d8567f0426e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803076"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="0a29d-104">Servizio utente per CQD</span><span class="sxs-lookup"><span data-stu-id="0a29d-104">User Service for CQD</span></span>
 
<span data-ttu-id="0a29d-105">**Riepilogo:** Informazioni sul servizio utente, che fa parte dell'API del repository per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="0a29d-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="0a29d-106">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0a29d-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="0a29d-107">Il servizio utente fa parte dell'API del repository per il dashboard qualità chiamata.</span><span class="sxs-lookup"><span data-stu-id="0a29d-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="0a29d-108">Servizio utente</span><span class="sxs-lookup"><span data-stu-id="0a29d-108">User Service</span></span>

<span data-ttu-id="0a29d-109">L'API del repository fornisce un modello semplificato per la gestione degli utenti in cui il provisioning degli utenti (creazione di nuovi account utente) è automatico e implicito.</span><span class="sxs-lookup"><span data-stu-id="0a29d-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="0a29d-110">Quando un utente effettua una richiesta per l'API di repository per la prima volta, viene creato un nuovo record utente.</span><span class="sxs-lookup"><span data-stu-id="0a29d-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="0a29d-111">Call Quality dashboard consente inoltre di creare automaticamente gli elementi dedicati all'utente per il nuovo utente.</span><span class="sxs-lookup"><span data-stu-id="0a29d-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="0a29d-112">I nuovi elementi dedicati all'utente sono cloni completi degli elementi dell'utente del sistema.</span><span class="sxs-lookup"><span data-stu-id="0a29d-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="0a29d-113">In questo modo, gli utenti iniziano con le proprie copie dei report e delle query che possono immediatamente avviare la personalizzazione.</span><span class="sxs-lookup"><span data-stu-id="0a29d-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="0a29d-114">Usando dashboard qualità chiamata, gli utenti possono reimpostare gli elementi dedicati in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="0a29d-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="0a29d-115">**ID utente speciali**</span><span class="sxs-lookup"><span data-stu-id="0a29d-115">**Special User IDs**</span></span>
  
<span data-ttu-id="0a29d-116">L'API del repository include gli URI dell'API REST che prevedono un valore intero per specificare un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="0a29d-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="0a29d-117">Esempio:  `https://<portal>/QoERepositoryService/repository/user/{userId}` .</span><span class="sxs-lookup"><span data-stu-id="0a29d-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="0a29d-118">In questo caso, {userId} deve essere sostituito da un valore intero, ad esempio 0, 1 e così via.</span><span class="sxs-lookup"><span data-stu-id="0a29d-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="0a29d-119">Inoltre, l'API del repository accetterà due ID utente speciali su {userId} in URI.</span><span class="sxs-lookup"><span data-stu-id="0a29d-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="0a29d-120">*default*  : rappresenta l'utente che sta interagendo con l'API.</span><span class="sxs-lookup"><span data-stu-id="0a29d-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="0a29d-121">In questo modo le applicazioni possono accedere al contenuto dell'utente corrente senza tenere conto del valore effettivo dell'ID utente.</span><span class="sxs-lookup"><span data-stu-id="0a29d-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="0a29d-122">Esempio: `https://<portal>/QoERepositoryService/repository/user/default` .</span><span class="sxs-lookup"><span data-stu-id="0a29d-122">Example: `https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="0a29d-123">*System*  : rappresenta l'utente del sistema.</span><span class="sxs-lookup"><span data-stu-id="0a29d-123">*system*  - represents the system user.</span></span> <span data-ttu-id="0a29d-124">In questo modo le applicazioni possono accedere al contenuto dell'utente del sistema senza conoscere il valore effettivo dell'ID utente.</span><span class="sxs-lookup"><span data-stu-id="0a29d-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="0a29d-125">Esempio: `https://<portal>/QoERepositoryService/repository/user/system` .</span><span class="sxs-lookup"><span data-stu-id="0a29d-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="0a29d-126">Se non diversamente specificato, gli ID utente speciali possono essere utilizzati in {userId} in URI.</span><span class="sxs-lookup"><span data-stu-id="0a29d-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="0a29d-127">Le operazioni REST sono incluse nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="0a29d-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="0a29d-128">**Operazione**</span><span class="sxs-lookup"><span data-stu-id="0a29d-128">**Operation**</span></span>|<span data-ttu-id="0a29d-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0a29d-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="0a29d-130">Ottieni utenti</span><span class="sxs-lookup"><span data-stu-id="0a29d-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="0a29d-131">Restituisce un elenco di utenti nel repository.</span><span class="sxs-lookup"><span data-stu-id="0a29d-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="0a29d-132">Ottieni utente</span><span class="sxs-lookup"><span data-stu-id="0a29d-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="0a29d-133">Restituisce un record utente.</span><span class="sxs-lookup"><span data-stu-id="0a29d-133">Returns a user record.</span></span>  <br/> |
   

