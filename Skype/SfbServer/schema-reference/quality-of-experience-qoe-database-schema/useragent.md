---
title: Tabella UserAgent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La tabella UserAgent è una tabella di supporto in cui è archiviato un elenco dei vari agenti utente che hanno partecipato alle sessioni registrate nel database. Ogni record nella tabella rappresenta un solo agente utente
ms.openlocfilehash: d0a287881a352801d237894c5b150b5a08d91fc8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805054"
---
# <a name="useragent-table"></a><span data-ttu-id="1ad54-104">Tabella UserAgent</span><span class="sxs-lookup"><span data-stu-id="1ad54-104">UserAgent table</span></span>
 
<span data-ttu-id="1ad54-105">La tabella UserAgent è una tabella di supporto in cui è archiviato un elenco dei vari agenti utente che hanno partecipato alle sessioni registrate nel database.</span><span class="sxs-lookup"><span data-stu-id="1ad54-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="1ad54-106">Ogni record nella tabella rappresenta un solo agente utente</span><span class="sxs-lookup"><span data-stu-id="1ad54-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="1ad54-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="1ad54-107">**Column**</span></span>|<span data-ttu-id="1ad54-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="1ad54-108">**Data Type**</span></span>|<span data-ttu-id="1ad54-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="1ad54-109">**Key/Index**</span></span>|<span data-ttu-id="1ad54-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="1ad54-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1ad54-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="1ad54-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="1ad54-112">int</span><span class="sxs-lookup"><span data-stu-id="1ad54-112">int</span></span>  <br/> |<span data-ttu-id="1ad54-113">Principale</span><span class="sxs-lookup"><span data-stu-id="1ad54-113">Primary</span></span>  <br/> |<span data-ttu-id="1ad54-114">Numero univoco che identifica questo agente utente.</span><span class="sxs-lookup"><span data-stu-id="1ad54-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="1ad54-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="1ad54-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="1ad54-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="1ad54-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="1ad54-117">Univoci</span><span class="sxs-lookup"><span data-stu-id="1ad54-117">Unique</span></span>  <br/> |<span data-ttu-id="1ad54-118">Stringa agente utente.</span><span class="sxs-lookup"><span data-stu-id="1ad54-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="1ad54-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="1ad54-119">**UAType**</span></span> <br/> |<span data-ttu-id="1ad54-120">smallint</span><span class="sxs-lookup"><span data-stu-id="1ad54-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="1ad54-121">1 è Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="1ad54-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="1ad54-122">2 è un/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="1ad54-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="1ad54-123">4 è Skype for business.</span><span class="sxs-lookup"><span data-stu-id="1ad54-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="1ad54-124">8 è il telefono IP.</span><span class="sxs-lookup"><span data-stu-id="1ad54-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="1ad54-125">16 è la console Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="1ad54-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="1ad54-126">32 è lo strumento di convalida della distribuzione (TVP).</span><span class="sxs-lookup"><span data-stu-id="1ad54-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="1ad54-127">64 è Skype for Business Server su computer Macintosh.</span><span class="sxs-lookup"><span data-stu-id="1ad54-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="1ad54-128">128 è Skype for Business Server Attendant.</span><span class="sxs-lookup"><span data-stu-id="1ad54-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="1ad54-129">256 è un servizio di annunci conferenza.</span><span class="sxs-lookup"><span data-stu-id="1ad54-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="1ad54-130">512 è operatore automatico di conferenza.</span><span class="sxs-lookup"><span data-stu-id="1ad54-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="1ad54-131">1024 è un'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="1ad54-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="1ad54-132">2048 è il controllo vocale esterno.</span><span class="sxs-lookup"><span data-stu-id="1ad54-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

