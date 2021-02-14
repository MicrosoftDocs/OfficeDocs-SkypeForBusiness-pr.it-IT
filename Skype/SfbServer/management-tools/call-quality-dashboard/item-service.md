---
title: Item Service for Call Quality Dashboard (CQD)
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
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: "Riepilogo: informazioni su Item Service, che fa parte dell'API repository per call quality dashboard. Call Quality Dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: b904f814a837af13e4015af5fbaca924739b8997
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827706"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="a8c75-104">Item Service for Call Quality Dashboard (CQD)</span><span class="sxs-lookup"><span data-stu-id="a8c75-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="a8c75-105">**Riepilogo:** Informazioni su Item Service, che fa parte dell'API repository per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="a8c75-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="a8c75-106">Call Quality Dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="a8c75-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="a8c75-107">Item Service fa parte dell'API repository per call quality dashboard.</span><span class="sxs-lookup"><span data-stu-id="a8c75-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="a8c75-108">Servizio elementi</span><span class="sxs-lookup"><span data-stu-id="a8c75-108">Item Service</span></span>

<span data-ttu-id="a8c75-109">L'API repository offre un semplice servizio di gestione del contenuto, noto come servizio elementi, che può essere usato per archiviare qualsiasi contenuto definito dall'applicazione per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="a8c75-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="a8c75-110">Il contenuto del sistema è di proprietà dell'utente di sistema e condiviso da tutti gli utenti con accesso in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="a8c75-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="a8c75-111">I contenuti degli utenti dedicati sono di proprietà di utenti normali e solo i proprietari possono modificarli o eliminarli, ma tutti gli utenti hanno ancora accesso in sola lettura.</span><span class="sxs-lookup"><span data-stu-id="a8c75-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a8c75-112">Questa documentazione dell'API illustra le operazioni di sola lettura dell'API repository.</span><span class="sxs-lookup"><span data-stu-id="a8c75-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="a8c75-113">Il dashboard qualità delle chiamate salva i rapporti e le query come elementi nel database repository.</span><span class="sxs-lookup"><span data-stu-id="a8c75-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="a8c75-114">Un elemento può avere elementi secondari facoltativi e call quality dashboard organizza report e query in una struttura gerarchica utilizzando la funzionalità elementi secondari.</span><span class="sxs-lookup"><span data-stu-id="a8c75-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="a8c75-115">Il servizio elementi include i concetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="a8c75-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="a8c75-116">**Elemento** : l'elemento di base del repository.</span><span class="sxs-lookup"><span data-stu-id="a8c75-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="a8c75-117">Ogni elemento è di proprietà esattamente di un utente.</span><span class="sxs-lookup"><span data-stu-id="a8c75-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="a8c75-118">**Sotto-elemento:** le meccaniche organizzative di base dell'archivio.</span><span class="sxs-lookup"><span data-stu-id="a8c75-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="a8c75-119">L'elemento può avere zero, uno o più elementi subordinati.</span><span class="sxs-lookup"><span data-stu-id="a8c75-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="a8c75-120">**Predecessori elemento** - Elenco di elementi, a partire dall'elemento più in alto, che è l'elemento predefinito dell'utente, che conduce a un determinato elemento.</span><span class="sxs-lookup"><span data-stu-id="a8c75-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="a8c75-121">**Contenuto elemento:** il contenuto specifico dell'applicazione archiviato in Elementi.</span><span class="sxs-lookup"><span data-stu-id="a8c75-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="a8c75-122">Call Quality Dashboard salva le rappresentazioni JSON di report e query nel contenuto.</span><span class="sxs-lookup"><span data-stu-id="a8c75-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="a8c75-123">Le operazioni REST sono incluse nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="a8c75-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="a8c75-124">**Operazione**</span><span class="sxs-lookup"><span data-stu-id="a8c75-124">**Operation**</span></span>|<span data-ttu-id="a8c75-125">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="a8c75-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="a8c75-126">Ottenere elementi</span><span class="sxs-lookup"><span data-stu-id="a8c75-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="a8c75-127">Il metodo Get Items restituisce tutti gli elementi nel repository.</span><span class="sxs-lookup"><span data-stu-id="a8c75-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="a8c75-128">Ottieni elemento</span><span class="sxs-lookup"><span data-stu-id="a8c75-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="a8c75-129">Get Item restituisce un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="a8c75-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="a8c75-130">Ottieni elementi secondari</span><span class="sxs-lookup"><span data-stu-id="a8c75-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="a8c75-131">Ottiene Sub-Items restituisce gli elementi secondari di un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="a8c75-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="a8c75-132">Ottieni predecessori elemento</span><span class="sxs-lookup"><span data-stu-id="a8c75-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="a8c75-133">Get Item Predecessors restituisce i predecessori di un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="a8c75-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="a8c75-134">Aggiorna elemento</span><span class="sxs-lookup"><span data-stu-id="a8c75-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="a8c75-135">Aggiornare un elemento specifico nel repository.</span><span class="sxs-lookup"><span data-stu-id="a8c75-135">Update a specific item in the repository.</span></span>  <br/> |
   

