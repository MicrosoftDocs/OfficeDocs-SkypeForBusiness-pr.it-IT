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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 14c44736-71ba-4fc5-82c7-1df65bf6261c
description: La visualizzazione VoIPDetails archivia le informazioni sulle sessioni peer-to-peer, in cui almeno un utente è un utente VoIP. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 4d3aec4c58c2cb11f21ec6403f7532bcde46b05e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814774"
---
# <a name="voipdetails-view"></a><span data-ttu-id="0f131-104">Visualizzazione VoIPDetails</span><span class="sxs-lookup"><span data-stu-id="0f131-104">VoIPDetails view</span></span>
 
<span data-ttu-id="0f131-105">La visualizzazione VoIPDetails archivia le informazioni sulle sessioni peer-to-peer, in cui almeno un utente è un utente VoIP.</span><span class="sxs-lookup"><span data-stu-id="0f131-105">The VoIPDetails view stores information about peer-to-peer sessions, where at least one user is a VoIP user.</span></span> <span data-ttu-id="0f131-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="0f131-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="0f131-107">La visualizzazione VoIPDetails contiene tutte le colonne della [Visualizzazione SessionDetails](sessiondetails-0.md) , oltre alle colonne elencate di seguito.</span><span class="sxs-lookup"><span data-stu-id="0f131-107">The VoIPDetails view contains all of the columns in the [SessionDetails view](sessiondetails-0.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="0f131-108">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="0f131-108">**Column**</span></span>|<span data-ttu-id="0f131-109">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="0f131-109">**Data Type**</span></span>|<span data-ttu-id="0f131-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="0f131-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0f131-111">**FromPhone**</span><span class="sxs-lookup"><span data-stu-id="0f131-111">**FromPhone**</span></span> <br/> |<span data-ttu-id="0f131-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0f131-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="0f131-113">URI telefono dell'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="0f131-113">Phone URI of the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="0f131-114">**Telefono**</span><span class="sxs-lookup"><span data-stu-id="0f131-114">**ToPhone**</span></span> <br/> |<span data-ttu-id="0f131-115">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0f131-115">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="0f131-116">URI telefono dell'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="0f131-116">Phone URI of the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="0f131-117">**DisconnectedByUri**</span><span class="sxs-lookup"><span data-stu-id="0f131-117">**DisconnectedByUri**</span></span> <br/> |<span data-ttu-id="0f131-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0f131-118">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="0f131-119">URI dell'utente che ha scollegato la sessione.</span><span class="sxs-lookup"><span data-stu-id="0f131-119">URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="0f131-120">**DisconnectedByUriType**</span><span class="sxs-lookup"><span data-stu-id="0f131-120">**DisconnectedByUriType**</span></span> <br/> |<span data-ttu-id="0f131-121">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0f131-121">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0f131-122">Tipo di URI dell'utente che ha scollegato la sessione.</span><span class="sxs-lookup"><span data-stu-id="0f131-122">Type of URI of the user who disconnected the session.</span></span> <span data-ttu-id="0f131-123">Per altre informazioni, vedere la [tabella UriTypes](uritypes.md) .</span><span class="sxs-lookup"><span data-stu-id="0f131-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="0f131-124">**DisconnectedByTenant**</span><span class="sxs-lookup"><span data-stu-id="0f131-124">**DisconnectedByTenant**</span></span> <br/> |<span data-ttu-id="0f131-125">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0f131-125">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0f131-126">Tenant dell'utente che ha scollegato la sessione.</span><span class="sxs-lookup"><span data-stu-id="0f131-126">Tenant of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="0f131-127">**DisconnectedByPhone**</span><span class="sxs-lookup"><span data-stu-id="0f131-127">**DisconnectedByPhone**</span></span> <br/> |<span data-ttu-id="0f131-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="0f131-128">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="0f131-129">URI telefono dell'utente che ha scollegato la sessione.</span><span class="sxs-lookup"><span data-stu-id="0f131-129">Phone URI of the user who disconnected the session.</span></span>  <br/> |
|<span data-ttu-id="0f131-130">**FromMediationServer**</span><span class="sxs-lookup"><span data-stu-id="0f131-130">**FromMediationServer**</span></span> <br/> |<span data-ttu-id="0f131-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0f131-131">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0f131-132">Mediation Server usato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="0f131-132">Mediation Server used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="0f131-133">**ToMediationServer**</span><span class="sxs-lookup"><span data-stu-id="0f131-133">**ToMediationServer**</span></span> <br/> |<span data-ttu-id="0f131-134">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0f131-134">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0f131-135">Mediation Server usato dall'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="0f131-135">Mediation Server used by the user who joined the session.</span></span>  <br/> |
|<span data-ttu-id="0f131-136">**FromGateway**</span><span class="sxs-lookup"><span data-stu-id="0f131-136">**FromGateway**</span></span> <br/> |<span data-ttu-id="0f131-137">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0f131-137">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0f131-138">Gateway usato dall'utente che ha avviato la sessione.</span><span class="sxs-lookup"><span data-stu-id="0f131-138">Gateway used by the user who started the session.</span></span>  <br/> |
|<span data-ttu-id="0f131-139">**Togateway**</span><span class="sxs-lookup"><span data-stu-id="0f131-139">**ToGateway**</span></span> <br/> |<span data-ttu-id="0f131-140">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="0f131-140">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="0f131-141">Gateway usato dall'utente che ha partecipato alla sessione.</span><span class="sxs-lookup"><span data-stu-id="0f131-141">Gateway used by the user who joined the session.</span></span>  <br/> |
   

