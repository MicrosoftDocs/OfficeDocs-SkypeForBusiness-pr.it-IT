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
description: "Riepilogo: informazioni sul servizio utente, che fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: d9f4b771a1bf5efeece4f8fb87195d8567f0426e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49803076"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="ee303-104">Servizio utente per CQD</span><span class="sxs-lookup"><span data-stu-id="ee303-104">User Service for CQD</span></span>
 
<span data-ttu-id="ee303-105">**Riepilogo:** Informazioni sul servizio utente, che fa parte dell'API repository per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="ee303-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="ee303-106">Call Quality Dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ee303-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="ee303-107">Il servizio utente fa parte dell'API repository per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="ee303-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="ee303-108">Servizio utente</span><span class="sxs-lookup"><span data-stu-id="ee303-108">User Service</span></span>

<span data-ttu-id="ee303-109">L'API repository offre un modello di gestione degli utenti semplificato in cui il provisioning degli utenti (creazione di nuovi account utente) è automatico e implicito.</span><span class="sxs-lookup"><span data-stu-id="ee303-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="ee303-110">Quando un utente effettua una richiesta sull'API repository per la prima volta, il repository crea un nuovo record Utente.</span><span class="sxs-lookup"><span data-stu-id="ee303-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="ee303-111">Call Quality Dashboard crea inoltre automaticamente elementi dedicati all'utente per il nuovo utente.</span><span class="sxs-lookup"><span data-stu-id="ee303-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="ee303-112">I nuovi elementi dedicati all'utente sono cloni completi degli elementi dell'utente di sistema.</span><span class="sxs-lookup"><span data-stu-id="ee303-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="ee303-113">In questo modo, gli utenti iniziano con le proprie copie di report e query che possono iniziare immediatamente a personalizzare.</span><span class="sxs-lookup"><span data-stu-id="ee303-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ee303-114">Utilizzando call quality dashboard, gli utenti possono reimpostare gli elementi dedicati in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="ee303-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="ee303-115">**ID utente speciali**</span><span class="sxs-lookup"><span data-stu-id="ee303-115">**Special User IDs**</span></span>
  
<span data-ttu-id="ee303-116">L'API di repository include URI DELL'API REST che prevedono un valore intero per specificare un utente specifico.</span><span class="sxs-lookup"><span data-stu-id="ee303-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="ee303-117">Esempio:  `https://<portal>/QoERepositoryService/repository/user/{userId}` .</span><span class="sxs-lookup"><span data-stu-id="ee303-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="ee303-118">In questo caso, {userId} deve essere sostituito da un valore intero, ad esempio 0, 1 e così via.</span><span class="sxs-lookup"><span data-stu-id="ee303-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="ee303-119">Inoltre, l'API repository accetterà due ID utente speciali in {userId} negli URI.</span><span class="sxs-lookup"><span data-stu-id="ee303-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="ee303-120">*default-*  rappresenta l'utente che sta attualmente interagendo con l'API.</span><span class="sxs-lookup"><span data-stu-id="ee303-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="ee303-121">In questo modo le applicazioni possono accedere al contenuto dell'utente corrente senza tenere traccia del valore effettivo dell'ID utente.</span><span class="sxs-lookup"><span data-stu-id="ee303-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="ee303-122">Esempio: `https://<portal>/QoERepositoryService/repository/user/default` .</span><span class="sxs-lookup"><span data-stu-id="ee303-122">Example: `https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="ee303-123">*system*  - rappresenta l'utente del sistema.</span><span class="sxs-lookup"><span data-stu-id="ee303-123">*system*  - represents the system user.</span></span> <span data-ttu-id="ee303-124">In questo modo le applicazioni possono accedere al contenuto dell'utente di sistema senza conoscere il valore effettivo dell'ID utente.</span><span class="sxs-lookup"><span data-stu-id="ee303-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="ee303-125">Esempio: `https://<portal>/QoERepositoryService/repository/user/system` .</span><span class="sxs-lookup"><span data-stu-id="ee303-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="ee303-126">Se non specificato diversamente, gli ID utente speciali possono essere utilizzati in {userId} negli URI.</span><span class="sxs-lookup"><span data-stu-id="ee303-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="ee303-127">Le operazioni REST sono incluse nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="ee303-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="ee303-128">**Operazione**</span><span class="sxs-lookup"><span data-stu-id="ee303-128">**Operation**</span></span>|<span data-ttu-id="ee303-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="ee303-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="ee303-130">Ottieni utenti</span><span class="sxs-lookup"><span data-stu-id="ee303-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="ee303-131">Restituisce un elenco di utenti nel repository.</span><span class="sxs-lookup"><span data-stu-id="ee303-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="ee303-132">Ottieni utente</span><span class="sxs-lookup"><span data-stu-id="ee303-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="ee303-133">Restituisce un record utente.</span><span class="sxs-lookup"><span data-stu-id="ee303-133">Returns a user record.</span></span>  <br/> |
   

