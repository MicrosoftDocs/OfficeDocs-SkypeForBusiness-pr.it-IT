---
title: Visualizzazione VoIPDetails
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: Nella visualizzazione VoIPDetails vengono archiviate le informazioni sulle sessioni peer-to-peer, che contengono almeno un utente VoIP. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: b42fecc7a0f43f86dba2439a373c7013c605a5e0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813076"
---
# <a name="voipdetails-view"></a><span data-ttu-id="546b2-104">Visualizzazione VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="546b2-104">VoIPDetails view</span></span>
 
<span data-ttu-id="546b2-105">Nella visualizzazione VoIPDetails vengono archiviate le informazioni sulle sessioni peer-to-peer, che contengono almeno un utente VoIP.</span><span class="sxs-lookup"><span data-stu-id="546b2-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="546b2-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="546b2-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="546b2-107">La visualizzazione VoIPDetails contiene tutte le colonne nella visualizzazione [SessionDetails,](sessiondetails-0.md) oltre alle colonne elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="546b2-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="546b2-108">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="546b2-108">**Column**</span></span>|<span data-ttu-id="546b2-109">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="546b2-109">**Data Type**</span></span>|<span data-ttu-id="546b2-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="546b2-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="546b2-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="546b2-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="546b2-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="546b2-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="546b2-113">URI telefono dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="546b2-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="546b2-114">**ToPhone**</span><span class="sxs-lookup"><span data-stu-id="546b2-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="546b2-115">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="546b2-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="546b2-116">URI telefono dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="546b2-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="546b2-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="546b2-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="546b2-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="546b2-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="546b2-119">URI dell'utente che ha interrotto la sessione.</span><span class="sxs-lookup"><span data-stu-id="546b2-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="546b2-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="546b2-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="546b2-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="546b2-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="546b2-122">Tipo di URI dell'utente che ha interrotto la sessione.</span><span class="sxs-lookup"><span data-stu-id="546b2-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="546b2-123">Per altre [informazioni, vedi la tabella UriTypes.](uritypes.md)</span><span class="sxs-lookup"><span data-stu-id="546b2-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="546b2-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="546b2-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="546b2-125">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="546b2-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="546b2-126">Tenant dell'utente che ha interrotto la sessione.</span><span class="sxs-lookup"><span data-stu-id="546b2-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="546b2-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="546b2-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="546b2-128">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="546b2-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="546b2-129">URI telefono dell'utente che ha interrotto la sessione.</span><span class="sxs-lookup"><span data-stu-id="546b2-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="546b2-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="546b2-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="546b2-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="546b2-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="546b2-132">Mediation Server utilizzato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="546b2-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="546b2-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="546b2-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="546b2-134">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="546b2-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="546b2-135">Mediation Server utilizzato dall'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="546b2-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="546b2-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="546b2-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="546b2-137">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="546b2-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="546b2-138">Gateway utilizzato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="546b2-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="546b2-139">**ToGateway**</span><span class="sxs-lookup"><span data-stu-id="546b2-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="546b2-140">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="546b2-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="546b2-141">Gateway utilizzato dall'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="546b2-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

