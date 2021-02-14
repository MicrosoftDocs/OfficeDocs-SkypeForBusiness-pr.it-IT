---
title: Tabella UserStatistics
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
ms.assetid: cfaf803b-1679-4169-92d3-533fad3e56ed
description: La tabella UserStatistics è una tabella di supporto. In ogni record della tabella sono archiviate informazioni sull'utilizzo del sistema da parte di un singolo utente. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 65017c9f807b272097b39bac88c80cc81e617ff4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813106"
---
# <a name="userstatistics-table"></a><span data-ttu-id="e339e-105">Tabella UserStatistics</span><span class="sxs-lookup"><span data-stu-id="e339e-105">UserStatistics table</span></span>
 
<span data-ttu-id="e339e-106">La tabella UserStatistics è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="e339e-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="e339e-107">In ogni record della tabella sono archiviate informazioni sull'utilizzo del sistema da parte di un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="e339e-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="e339e-108">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e339e-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="e339e-109">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="e339e-109">**Column**</span></span>|<span data-ttu-id="e339e-110">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="e339e-110">**Data Type**</span></span>|<span data-ttu-id="e339e-111">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="e339e-111">**Key/Index**</span></span>|<span data-ttu-id="e339e-112">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="e339e-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e339e-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="e339e-113">**UserId**</span></span> <br/> |<span data-ttu-id="e339e-114">int</span><span class="sxs-lookup"><span data-stu-id="e339e-114">int</span></span>  <br/> |<span data-ttu-id="e339e-115">Principale</span><span class="sxs-lookup"><span data-stu-id="e339e-115">Primary</span></span>  <br/> |<span data-ttu-id="e339e-116">Numero univoco che identifica l'utente.</span><span class="sxs-lookup"><span data-stu-id="e339e-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="e339e-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="e339e-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="e339e-118">datetime</span><span class="sxs-lookup"><span data-stu-id="e339e-118">datetime</span></span>  <br/> ||<span data-ttu-id="e339e-119">Data/ora dell'ultimo accesso dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e339e-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="e339e-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="e339e-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="e339e-121">datetime</span><span class="sxs-lookup"><span data-stu-id="e339e-121">datetime</span></span>  <br/> ||<span data-ttu-id="e339e-122">Data/ora dell'ultima conferenza organizzata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="e339e-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="e339e-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="e339e-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="e339e-124">datetime</span><span class="sxs-lookup"><span data-stu-id="e339e-124">datetime</span></span>  <br/> ||<span data-ttu-id="e339e-125">Data/ora dell'ultimo errore di chiamata dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e339e-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="e339e-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="e339e-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="e339e-127">datetime</span><span class="sxs-lookup"><span data-stu-id="e339e-127">datetime</span></span>  <br/> ||<span data-ttu-id="e339e-128">Data/ora dell'ultimo errore di chiamata dell'utente in qualità di organizzatore di una conferenza.</span><span class="sxs-lookup"><span data-stu-id="e339e-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

