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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La tabella UserStatistics è una tabella di supporto. Ogni record nella tabella archivia le informazioni sull'uso di un singolo utente del sistema. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 048c26279deb6f89e69784d754567dfde84d9983
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814794"
---
# <a name="userstatistics-table"></a><span data-ttu-id="69477-105">Tabella UserStatistics</span><span class="sxs-lookup"><span data-stu-id="69477-105">UserStatistics table</span></span>
 
<span data-ttu-id="69477-106">La tabella UserStatistics è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="69477-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="69477-107">Ogni record nella tabella archivia le informazioni sull'uso di un singolo utente del sistema.</span><span class="sxs-lookup"><span data-stu-id="69477-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="69477-108">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="69477-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="69477-109">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="69477-109">**Column**</span></span>|<span data-ttu-id="69477-110">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="69477-110">**Data Type**</span></span>|<span data-ttu-id="69477-111">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="69477-111">**Key/Index**</span></span>|<span data-ttu-id="69477-112">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="69477-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="69477-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="69477-113">**UserId**</span></span> <br/> |<span data-ttu-id="69477-114">int</span><span class="sxs-lookup"><span data-stu-id="69477-114">int</span></span>  <br/> |<span data-ttu-id="69477-115">Principale</span><span class="sxs-lookup"><span data-stu-id="69477-115">Primary</span></span>  <br/> |<span data-ttu-id="69477-116">Numero univoco che identifica questo utente.</span><span class="sxs-lookup"><span data-stu-id="69477-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="69477-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="69477-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="69477-118">DateTime</span><span class="sxs-lookup"><span data-stu-id="69477-118">datetime</span></span>  <br/> ||<span data-ttu-id="69477-119">Ultima volta che l'utente ha effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="69477-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="69477-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="69477-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="69477-121">DateTime</span><span class="sxs-lookup"><span data-stu-id="69477-121">datetime</span></span>  <br/> ||<span data-ttu-id="69477-122">L'ultima volta che l'utente ha organizzato una conferenza.</span><span class="sxs-lookup"><span data-stu-id="69477-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="69477-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="69477-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="69477-124">DateTime</span><span class="sxs-lookup"><span data-stu-id="69477-124">datetime</span></span>  <br/> ||<span data-ttu-id="69477-125">L'ultima volta che l'utente ha riscontrato un errore di chiamata.</span><span class="sxs-lookup"><span data-stu-id="69477-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="69477-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="69477-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="69477-127">DateTime</span><span class="sxs-lookup"><span data-stu-id="69477-127">datetime</span></span>  <br/> ||<span data-ttu-id="69477-128">L'ultima volta che l'utente ha sperimentato un errore di chiamata come organizzatore di conferenze.</span><span class="sxs-lookup"><span data-stu-id="69477-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

