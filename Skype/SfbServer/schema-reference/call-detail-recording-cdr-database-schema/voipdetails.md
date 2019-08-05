---
title: Visualizzazione VoIPDetails
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: La visualizzazione VoIPDetails archivia le informazioni sulle sessioni peer-to-peer, in cui almeno un utente è un utente VoIP. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 7f5f1e3cf1540e1a12a9365753e494ff2d8a371e
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194719"
---
# <a name="voipdetails-view"></a><span data-ttu-id="ef4ae-104">Visualizzazione VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="ef4ae-104">VoIPDetails view</span></span>
 
<span data-ttu-id="ef4ae-105">La visualizzazione VoIPDetails archivia le informazioni sulle sessioni peer-to-peer, in cui almeno un utente è un utente VoIP.</span><span class="sxs-lookup"><span data-stu-id="ef4ae-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="ef4ae-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ef4ae-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ef4ae-107">La visualizzazione VoIPDetails contiene tutte le colonne della [Visualizzazione SessionDetails](sessiondetails-0.md) , oltre alle colonne elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="ef4ae-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="ef4ae-108">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="ef4ae-108">**Column**</span></span>|<span data-ttu-id="ef4ae-109">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="ef4ae-109">**Data Type**</span></span>|<span data-ttu-id="ef4ae-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="ef4ae-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ef4ae-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="ef4ae-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="ef4ae-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ef4ae-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ef4ae-113">URI telefono dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="ef4ae-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="ef4ae-114">**Telefono**</span><span class="sxs-lookup"><span data-stu-id="ef4ae-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="ef4ae-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ef4ae-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ef4ae-116">URI telefono dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="ef4ae-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="ef4ae-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="ef4ae-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="ef4ae-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ef4ae-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ef4ae-119">URI dell'utente che ha scollegato la sessione.</span><span class="sxs-lookup"><span data-stu-id="ef4ae-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="ef4ae-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="ef4ae-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="ef4ae-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ef4ae-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ef4ae-122">Tipo di URI dell'utente che ha scollegato la sessione.</span><span class="sxs-lookup"><span data-stu-id="ef4ae-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="ef4ae-123">Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="ef4ae-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="ef4ae-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="ef4ae-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="ef4ae-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ef4ae-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ef4ae-126">Tenant dell'utente che ha scollegato la sessione.</span><span class="sxs-lookup"><span data-stu-id="ef4ae-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="ef4ae-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="ef4ae-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="ef4ae-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ef4ae-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="ef4ae-129">URI telefono dell'utente che ha scollegato la sessione.</span><span class="sxs-lookup"><span data-stu-id="ef4ae-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="ef4ae-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="ef4ae-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="ef4ae-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ef4ae-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ef4ae-132">Mediation Server usato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="ef4ae-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="ef4ae-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="ef4ae-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="ef4ae-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ef4ae-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ef4ae-135">Mediation Server usato dall'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="ef4ae-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="ef4ae-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="ef4ae-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="ef4ae-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ef4ae-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ef4ae-138">Gateway usato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="ef4ae-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="ef4ae-139">**Togateway**</span><span class="sxs-lookup"><span data-stu-id="ef4ae-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="ef4ae-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="ef4ae-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ef4ae-141">Gateway usato dall'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="ef4ae-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

