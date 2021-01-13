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
description: La tabella UserStatistics è una tabella di supporto. Ogni record nella tabella archivia le informazioni sull'utilizzo del sistema da parte di un singolo utente. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 65017c9f807b272097b39bac88c80cc81e617ff4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813106"
---
# <a name="userstatistics-table"></a><span data-ttu-id="7aea8-105">Tabella UserStatistics</span><span class="sxs-lookup"><span data-stu-id="7aea8-105">UserStatistics table</span></span>
 
<span data-ttu-id="7aea8-106">La tabella UserStatistics è una tabella di supporto.</span><span class="sxs-lookup"><span data-stu-id="7aea8-106">The UserStatistics table is a supporting table.</span></span> <span data-ttu-id="7aea8-107">Ogni record nella tabella archivia le informazioni sull'utilizzo del sistema da parte di un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="7aea8-107">Each record in the table stores information about an individual user's usage of the system.</span></span> <span data-ttu-id="7aea8-108">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7aea8-108">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="7aea8-109">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="7aea8-109">**Column**</span></span>|<span data-ttu-id="7aea8-110">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="7aea8-110">**Data Type**</span></span>|<span data-ttu-id="7aea8-111">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="7aea8-111">**Key/Index**</span></span>|<span data-ttu-id="7aea8-112">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="7aea8-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7aea8-113">**UserId**</span><span class="sxs-lookup"><span data-stu-id="7aea8-113">**UserId**</span></span> <br/> |<span data-ttu-id="7aea8-114">int</span><span class="sxs-lookup"><span data-stu-id="7aea8-114">int</span></span>  <br/> |<span data-ttu-id="7aea8-115">Principale</span><span class="sxs-lookup"><span data-stu-id="7aea8-115">Primary</span></span>  <br/> |<span data-ttu-id="7aea8-116">Numero univoco che identifica l'utente.</span><span class="sxs-lookup"><span data-stu-id="7aea8-116">Unique number identifying this user.</span></span>  <br/> |
|<span data-ttu-id="7aea8-117">**LastLogInTime**</span><span class="sxs-lookup"><span data-stu-id="7aea8-117">**LastLogInTime**</span></span> <br/> |<span data-ttu-id="7aea8-118">datetime</span><span class="sxs-lookup"><span data-stu-id="7aea8-118">datetime</span></span>  <br/> ||<span data-ttu-id="7aea8-119">Data/ora dell'ultimo accesso dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7aea8-119">Last time the user logged in.</span></span>  <br/> |
|<span data-ttu-id="7aea8-120">**LastConfOrganizedTime**</span><span class="sxs-lookup"><span data-stu-id="7aea8-120">**LastConfOrganizedTime**</span></span> <br/> |<span data-ttu-id="7aea8-121">datetime</span><span class="sxs-lookup"><span data-stu-id="7aea8-121">datetime</span></span>  <br/> ||<span data-ttu-id="7aea8-122">Data/ora dell'ultima conferenza organizzata dall'utente.</span><span class="sxs-lookup"><span data-stu-id="7aea8-122">Last time the user organized a conference.</span></span>  <br/> |
|<span data-ttu-id="7aea8-123">**LastCallOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="7aea8-123">**LastCallOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="7aea8-124">datetime</span><span class="sxs-lookup"><span data-stu-id="7aea8-124">datetime</span></span>  <br/> ||<span data-ttu-id="7aea8-125">Data/ora dell'ultimo errore di chiamata dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7aea8-125">Last time the user experienced a call failure.</span></span>  <br/> |
|<span data-ttu-id="7aea8-126">**LastConfOrganizerCallFailureTime**</span><span class="sxs-lookup"><span data-stu-id="7aea8-126">**LastConfOrganizerCallFailureTime**</span></span> <br/> |<span data-ttu-id="7aea8-127">datetime</span><span class="sxs-lookup"><span data-stu-id="7aea8-127">datetime</span></span>  <br/> ||<span data-ttu-id="7aea8-128">Data/ora dell'ultimo errore di chiamata dell'utente in qualità di organizzatore di una conferenza.</span><span class="sxs-lookup"><span data-stu-id="7aea8-128">Last time the user experienced a call failure as a conference organizer.</span></span>  <br/> |
   

