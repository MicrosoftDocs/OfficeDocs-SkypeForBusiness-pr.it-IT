---
title: Visualizzazione UserAgent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: La visualizzazione UserAgent archivia le informazioni sugli agenti utente coinvolti nelle sessioni che hanno record nel database. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 874a9c986ec77c3e19b557cd65dcf6dbeb045752
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194569"
---
# <a name="useragent-view"></a><span data-ttu-id="89b43-104">Visualizzazione UserAgent</span><span class="sxs-lookup"><span data-stu-id="89b43-104">UserAgent view</span></span>
 
<span data-ttu-id="89b43-105">La visualizzazione UserAgent archivia le informazioni sugli agenti utente coinvolti nelle sessioni che hanno record nel database.</span><span class="sxs-lookup"><span data-stu-id="89b43-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="89b43-106">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="89b43-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="89b43-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="89b43-107">**Column**</span></span>|<span data-ttu-id="89b43-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="89b43-108">**Data Type**</span></span>|<span data-ttu-id="89b43-109">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="89b43-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="89b43-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="89b43-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="89b43-111">int</span><span class="sxs-lookup"><span data-stu-id="89b43-111">int</span></span>  <br/> |<span data-ttu-id="89b43-112">Numero univoco che identifica questo agente utente.</span><span class="sxs-lookup"><span data-stu-id="89b43-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="89b43-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="89b43-113">UserAgent</span></span>  <br/> |<span data-ttu-id="89b43-114">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="89b43-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="89b43-115">Stringa agente utente.</span><span class="sxs-lookup"><span data-stu-id="89b43-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="89b43-116">UAType</span><span class="sxs-lookup"><span data-stu-id="89b43-116">UAType</span></span>  <br/> |<span data-ttu-id="89b43-117">smallint</span><span class="sxs-lookup"><span data-stu-id="89b43-117">smallint</span></span>  <br/> |<span data-ttu-id="89b43-118">Tipo di agente utente.</span><span class="sxs-lookup"><span data-stu-id="89b43-118">Type of user agent.</span></span> <span data-ttu-id="89b43-119">Per altri dettagli, vedere la [tabella UserAgent](useragent.md) .</span><span class="sxs-lookup"><span data-stu-id="89b43-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="89b43-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="89b43-120">UACategory</span></span>  <br/> |<span data-ttu-id="89b43-121">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="89b43-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="89b43-122">Categoria a cui appartiene l'agente utente.</span><span class="sxs-lookup"><span data-stu-id="89b43-122">Category that the user agent belongs to.</span></span> <span data-ttu-id="89b43-123">Ad esempio, l'agente utente Conferencing_Attendant_ 1.0 appartiene alla UACategory CAA.</span><span class="sxs-lookup"><span data-stu-id="89b43-123">For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

