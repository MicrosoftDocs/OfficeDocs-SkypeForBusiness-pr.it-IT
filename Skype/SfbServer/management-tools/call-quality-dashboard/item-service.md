---
title: Servizio voce per dashboard qualità chiamata (Call Quality Dashboard)
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: b6d7b02a-a34e-4fef-986c-ca442e18fa0c
description: "Riepilogo: informazioni sul servizio elementi, che fa parte dell'API del repository per il dashboard della qualità delle chiamate. Call Quality dashboard è uno strumento per Skype for Business Server."
ms.openlocfilehash: 585ba97d9dedbfcbbd572069a792a121e6156afe
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36186881"
---
# <a name="item-service-for-call-quality-dashboard-cqd"></a><span data-ttu-id="84fcf-104">Servizio voce per dashboard qualità chiamata (Call Quality Dashboard)</span><span class="sxs-lookup"><span data-stu-id="84fcf-104">Item Service for Call Quality Dashboard (CQD)</span></span>
 
<span data-ttu-id="84fcf-105">**Riepilogo:** Informazioni sul servizio elementi, che fa parte dell'API del repository per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="84fcf-105">**Summary:** Learn about the Item Service, which is part of the Repository API for Call Quality Dashboard.</span></span> <span data-ttu-id="84fcf-106">Call Quality dashboard è uno strumento per Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="84fcf-106">Call Quality Dashboard is a tool for Skype for Business Server.</span></span>
  
<span data-ttu-id="84fcf-107">Il servizio elementi fa parte dell'API del repository per il dashboard della qualità delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="84fcf-107">The Item Service is part of the Repository API for Call Quality Dashboard.</span></span>
  
## <a name="item-service"></a><span data-ttu-id="84fcf-108">Servizio elementi</span><span class="sxs-lookup"><span data-stu-id="84fcf-108">Item Service</span></span>

<span data-ttu-id="84fcf-109">API del repository offre un semplice servizio di gestione del contenuto, noto come servizio per gli elementi, che può essere usato per archiviare qualsiasi contenuto definito dall'applicazione per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="84fcf-109">Repository API offers a simple content management service, known as item service, that can be used for storing any application-defined contents for users.</span></span> 
  
<span data-ttu-id="84fcf-110">Il contenuto del sistema è di proprietà dell'utente del sistema e condiviso da tutti gli utenti con accesso di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="84fcf-110">The system contents are owned by the system user and shared by all users with read-only access.</span></span> <span data-ttu-id="84fcf-111">I contenuti utente dedicati sono di proprietà di utenti regolari e solo i proprietari possono modificarli o eliminarli, ma tutti gli utenti hanno comunque accesso di sola lettura.</span><span class="sxs-lookup"><span data-stu-id="84fcf-111">Dedicated user contents are owned by regular users, and only the owners can modify or delete them, but all users still have read-only access to them.</span></span>
  
> [!NOTE]
> <span data-ttu-id="84fcf-112">Questa documentazione API riguarda le operazioni di sola lettura dell'API del repository.</span><span class="sxs-lookup"><span data-stu-id="84fcf-112">This API documentation covers read-only operations of Repository API.</span></span> 
  
<span data-ttu-id="84fcf-113">Il dashboard qualità chiamata salva i report e le query come elementi nel database del repository.</span><span class="sxs-lookup"><span data-stu-id="84fcf-113">Call Quality Dashboard saves Reports and Queries as Items in the repository database.</span></span> <span data-ttu-id="84fcf-114">Un elemento può avere elementi secondari facoltativi e il dashboard qualità chiamata organizza report e query in una struttura gerarchica mediante la caratteristica elementi secondari.</span><span class="sxs-lookup"><span data-stu-id="84fcf-114">An Item can have optional sub-Items, and Call Quality Dashboard organizes Reports and Queries in an hierarchical structure using sub-Items feature.</span></span>
  
<span data-ttu-id="84fcf-115">Il servizio elementi include i concetti seguenti:</span><span class="sxs-lookup"><span data-stu-id="84fcf-115">Item service includes the following concepts:</span></span>
  
- <span data-ttu-id="84fcf-116">**Elemento** -l'elemento di base del repository.</span><span class="sxs-lookup"><span data-stu-id="84fcf-116">**Item** - the basic element of repository.</span></span> <span data-ttu-id="84fcf-117">Ogni elemento è di proprietà di un solo utente.</span><span class="sxs-lookup"><span data-stu-id="84fcf-117">Each Item is owned by exactly one User.</span></span>
    
- <span data-ttu-id="84fcf-118">**Elemento secondario** : la meccanica organizzativa di base del repository.</span><span class="sxs-lookup"><span data-stu-id="84fcf-118">**Sub-Item** - the basic organizational mechanics of repository.</span></span> <span data-ttu-id="84fcf-119">L'elemento può avere zero, uno o più elementi subordinati.</span><span class="sxs-lookup"><span data-stu-id="84fcf-119">Item can have zero, one, or more subordinate Items.</span></span>
    
- <span data-ttu-id="84fcf-120">**Antenati elemento** -l'elenco di elementi, a partire dall'elemento in primo piano, che è l'elemento predefinito dell'utente, che porta a un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="84fcf-120">**Item Ancestors** - the list of Items, beginning from the top-most Item, which is the default Item of the User, leading to a given Item.</span></span>
    
- <span data-ttu-id="84fcf-121">**Contenuto dell'elemento** -contenuto specifico dell'applicazione archiviato in elementi.</span><span class="sxs-lookup"><span data-stu-id="84fcf-121">**Item Content** - the application-specific content stored in Items.</span></span> <span data-ttu-id="84fcf-122">Il dashboard qualità chiamata consente di salvare le rappresentazioni JSON di report e query in contenuto.</span><span class="sxs-lookup"><span data-stu-id="84fcf-122">Call Quality Dashboard saves JSON representations of Reports and Queries in Contents.</span></span>
    
<span data-ttu-id="84fcf-123">Le operazioni REST sono incluse nella tabella seguente.</span><span class="sxs-lookup"><span data-stu-id="84fcf-123">The REST operations are included in the following table.</span></span>
  

|<span data-ttu-id="84fcf-124">**Operazione**</span><span class="sxs-lookup"><span data-stu-id="84fcf-124">**Operation**</span></span>|<span data-ttu-id="84fcf-125">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="84fcf-125">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="84fcf-126">Ottenere gli elementi</span><span class="sxs-lookup"><span data-stu-id="84fcf-126">Get Items</span></span>](get-items.md) <br/> |<span data-ttu-id="84fcf-127">Get Items restituisce tutti gli elementi del repository.</span><span class="sxs-lookup"><span data-stu-id="84fcf-127">Get Items returns all Items in the repository.</span></span>  <br/> |
|[<span data-ttu-id="84fcf-128">Ottieni elemento</span><span class="sxs-lookup"><span data-stu-id="84fcf-128">Get Item</span></span>](get-item.md) <br/> |<span data-ttu-id="84fcf-129">Ottieni elemento restituisce un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="84fcf-129">Get Item returns a specific Item.</span></span>  <br/> |
|[<span data-ttu-id="84fcf-130">Ottenere voci secondarie</span><span class="sxs-lookup"><span data-stu-id="84fcf-130">Get Sub-Items</span></span>](get-sub-items.md) <br/> |<span data-ttu-id="84fcf-131">Get Sub-Items restituisce gli elementi secondari di un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="84fcf-131">Get Sub-Items returns a specific Item's sub-Items.</span></span>  <br/> |
|[<span data-ttu-id="84fcf-132">Ottenere gli antenati degli elementi</span><span class="sxs-lookup"><span data-stu-id="84fcf-132">Get Item Ancestors</span></span>](get-item-ancestors.md) <br/> |<span data-ttu-id="84fcf-133">Ottenere gli antenati degli elementi restituisce gli antenati di un elemento specifico.</span><span class="sxs-lookup"><span data-stu-id="84fcf-133">Get Item Ancestors returns a specific Item's ancestors.</span></span>  <br/> |
|[<span data-ttu-id="84fcf-134">Aggiorna elemento</span><span class="sxs-lookup"><span data-stu-id="84fcf-134">Update Item</span></span>](update-item.md) <br/> |<span data-ttu-id="84fcf-135">Aggiornare un elemento specifico nel repository.</span><span class="sxs-lookup"><span data-stu-id="84fcf-135">Update a specific item in the repository.</span></span>  <br/> |
   

