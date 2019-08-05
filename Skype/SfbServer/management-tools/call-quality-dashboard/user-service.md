---
title: Servizio utente per Call Quality dashboard
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: abd5c828-42dd-4f48-bf87-29993193cb3a
description: "Riepilogo: informazioni sul servizio utente, che fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 6e0a6a58be98469458a8c8e7063402ff6477c35f
ms.sourcegitcommit: 208321bb45f7fb228757b9958a13f7e0bca91687
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/25/2019
ms.locfileid: "36195888"
---
# <a name="user-service-for-cqd"></a><span data-ttu-id="4d6a7-104">Servizio utente per Call Quality dashboard</span><span class="sxs-lookup"><span data-stu-id="4d6a7-104">User Service for CQD</span></span>
 
<span data-ttu-id="4d6a7-105">**Riepilogo:** Informazioni sul servizio utente, che fa parte dell'API del repository per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-105">**Summary:** Learn about the User Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="4d6a7-106">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="4d6a7-107">Il servizio utente fa parte dell'API del repository per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-107">The User Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="user-service"></a><span data-ttu-id="4d6a7-108">Servizio utente</span><span class="sxs-lookup"><span data-stu-id="4d6a7-108">User Service</span></span>

<span data-ttu-id="4d6a7-109">L'API del repository offre un modello di gestione semplificato degli utenti in cui il provisioning degli utenti (creazione di nuovi account utente) è automatico e implicito.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-109">Repository API provides a simplified user management model where user provisioning (creating new user accounts) is automatic and implicit.</span></span> <span data-ttu-id="4d6a7-110">Quando un utente effettua una richiesta contro l'API del repository per la prima volta, il repository crea un nuovo record utente.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-110">When a user make a request against Repository API for the first time, the repository creates a new User record.</span></span> 
  
<span data-ttu-id="4d6a7-111">Il dashboard qualità chiamata crea inoltre automaticamente un elemento dedicato agli utenti per il nuovo utente.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-111">Call Quality Dashboard also automatically creates a user dedicated items for the new user.</span></span> <span data-ttu-id="4d6a7-112">I nuovi elementi dedicati agli utenti sono cloni completi degli elementi dell'utente del sistema.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-112">The new user dedicated items are complete clones of system user's items.</span></span> <span data-ttu-id="4d6a7-113">In questo modo, gli utenti iniziano con le proprie copie di report e query che possono immediatamente iniziare a personalizzare.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-113">This way, users start with their own copies of Reports and Queries that they can immediately start customizing.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4d6a7-114">Usando dashboard qualità chiamata, gli utenti possono reimpostare gli elementi dedicati in qualsiasi momento.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-114">Using Call Quality Dashboard, users can reset their dedicated items anytime.</span></span> 
  
 <span data-ttu-id="4d6a7-115">**ID utente speciali**</span><span class="sxs-lookup"><span data-stu-id="4d6a7-115">**Special User IDs**</span></span>
  
<span data-ttu-id="4d6a7-116">L'API del repository include gli URI delle API REST che prevedono un valore intero per specificare un determinato utente.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-116">Repository API includes REST API URIs that expects an integer value to specify a particular user.</span></span> <span data-ttu-id="4d6a7-117">Esempio: `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-117">Example:  `https://<portal>/QoERepositoryService/repository/user/{userId}`.</span></span> <span data-ttu-id="4d6a7-118">In questo caso, {userId} deve essere sostituito da un valore intero come 0, 1 e così via.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-118">Here, {userId} should be replaced by an integer value such as 0, 1, etc.</span></span>
  
<span data-ttu-id="4d6a7-119">Inoltre, l'API del repository accetterà due ID utente speciali in {userId} in URI.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-119">Moreover, Repository API will accept two special user IDs at {userId} in URIs.</span></span>
  
-  <span data-ttu-id="4d6a7-120">*default* : rappresenta l'utente che sta interagendo con l'API.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-120">*default*  - represents the user who is currently interacting with the API.</span></span> <span data-ttu-id="4d6a7-121">Questo consente alle applicazioni di accedere al contenuto dell'utente corrente senza tenere traccia del valore effettivo dell'ID utente.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-121">This allows applications to access current user's contents without keeping track of the actual user ID value.</span></span> <span data-ttu-id="4d6a7-122">Esempio: `https://<portal>/QoERepositoryService/repository/user/default`.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-122">Example: `https://<portal>/QoERepositoryService/repository/user/default`.</span></span>
    
-  <span data-ttu-id="4d6a7-123">*System* : rappresenta l'utente del sistema.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-123">*system*  - represents the system user.</span></span> <span data-ttu-id="4d6a7-124">Questo consente alle applicazioni di accedere al contenuto dell'utente del sistema senza conoscere il valore effettivo dell'ID utente.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-124">This allows applications to access the system user's contents without knowing the actual user ID value.</span></span> <span data-ttu-id="4d6a7-125">Esempio: `https://<portal>/QoERepositoryService/repository/user/system`.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-125">Example: `https://<portal>/QoERepositoryService/repository/user/system`.</span></span>
    
<span data-ttu-id="4d6a7-126">Se non diversamente specificato, gli ID utente speciali possono essere usati presso {userId} in URI.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-126">Unless otherwise noted, the special user IDs can be used at {userId} in URIs.</span></span> 
  
<span data-ttu-id="4d6a7-127">Le operazioni REST sono incluse nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-127">The REST operations are included in the following table.</span></span>
  
|<span data-ttu-id="4d6a7-128">**Operazione**</span><span class="sxs-lookup"><span data-stu-id="4d6a7-128">**Operation**</span></span>|<span data-ttu-id="4d6a7-129">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="4d6a7-129">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="4d6a7-130">Ottenere gli utenti</span><span class="sxs-lookup"><span data-stu-id="4d6a7-130">Get Users</span></span>](get-users.md) <br/> |<span data-ttu-id="4d6a7-131">Restituisce un elenco di utenti nel repository.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-131">Returns a list of users in the repository.</span></span>  <br/> |
|[<span data-ttu-id="4d6a7-132">Ottenere l'utente</span><span class="sxs-lookup"><span data-stu-id="4d6a7-132">Get User</span></span>](get-user.md) <br/> |<span data-ttu-id="4d6a7-133">Restituisce un record utente.</span><span class="sxs-lookup"><span data-stu-id="4d6a7-133">Returns a user record.</span></span>  <br/> |
   

