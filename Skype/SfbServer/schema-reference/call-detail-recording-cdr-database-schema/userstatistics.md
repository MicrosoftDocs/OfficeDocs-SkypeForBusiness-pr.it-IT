---
title: Tabella UserStatistics
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La tabella UserStatistics è una tabella di supporto. Ogni record nella tabella archivia le informazioni sull'uso di un singolo utente del sistema. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 4801ed2611f3a078811f22f7e5a1cc1a797f6805
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194720"
---
# <a name="userstatistics-table"></a><span data-ttu-id="4f601-105">Tabella UserStatistics</span><span class="sxs-lookup"><span data-stu-id="4f601-105">UserStatistics table</span></span>
 
<span data-ttu-id="4f601-106">La tabella UserStatistics è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="4f601-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="4f601-107">Ogni record nella tabella archivia le informazioni sull'uso di un singolo utente del sistema.</span><span class="sxs-lookup"><span data-stu-id="4f601-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="4f601-108">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4f601-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="4f601-109">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="4f601-109">**Column**</span></span>|<span data-ttu-id="4f601-110">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="4f601-110">**Data Type**</span></span>|<span data-ttu-id="4f601-111">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="4f601-111">**Key/Index**</span></span>|<span data-ttu-id="4f601-112">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="4f601-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4f601-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="4f601-113">**UserId**</span></span> <br/> |<span data-ttu-id="4f601-114">int</span><span class="sxs-lookup"><span data-stu-id="4f601-114">int</span></span>  <br/> |<span data-ttu-id="4f601-115">Principale</span><span class="sxs-lookup"><span data-stu-id="4f601-115">Primary</span></span>  <br/> |<span data-ttu-id="4f601-116">Numero univoco che identifica questo utente.</span><span class="sxs-lookup"><span data-stu-id="4f601-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="4f601-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="4f601-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="4f601-118">DateTime</span><span class="sxs-lookup"><span data-stu-id="4f601-118">datetime</span></span>  <br/> ||<span data-ttu-id="4f601-119">Ultima volta che l'utente ha effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="4f601-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="4f601-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="4f601-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="4f601-121">DateTime</span><span class="sxs-lookup"><span data-stu-id="4f601-121">datetime</span></span>  <br/> ||<span data-ttu-id="4f601-122">L'ultima volta che l'utente ha organizzato una conferenza.</span><span class="sxs-lookup"><span data-stu-id="4f601-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="4f601-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="4f601-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="4f601-124">DateTime</span><span class="sxs-lookup"><span data-stu-id="4f601-124">datetime</span></span>  <br/> ||<span data-ttu-id="4f601-125">L'ultima volta che l'utente ha riscontrato un errore di chiamata.</span><span class="sxs-lookup"><span data-stu-id="4f601-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="4f601-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="4f601-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="4f601-127">DateTime</span><span class="sxs-lookup"><span data-stu-id="4f601-127">datetime</span></span>  <br/> ||<span data-ttu-id="4f601-128">L'ultima volta che l'utente ha sperimentato un errore di chiamata come organizzatore di conferenze.</span><span class="sxs-lookup"><span data-stu-id="4f601-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

