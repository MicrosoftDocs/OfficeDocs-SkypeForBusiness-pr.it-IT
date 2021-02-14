---
title: Tabella UserAgent
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La tabella UserAgent è una tabella di supporto in cui è archiviato un elenco dei vari agenti utente che hanno partecipato alle sessioni registrate nel database. Ogni record nella tabella rappresenta un agente utente
ms.openlocfilehash: a1d0e647ff78d409555988a27592228fac2643be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799936"
---
# <a name="useragent-table"></a><span data-ttu-id="bf3e5-104">Tabella UserAgent</span><span class="sxs-lookup"><span data-stu-id="bf3e5-104">UserAgent table</span></span>
 
<span data-ttu-id="bf3e5-105">La tabella UserAgent è una tabella di supporto in cui è archiviato un elenco dei vari agenti utente che hanno partecipato alle sessioni registrate nel database.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="bf3e5-106">Ogni record nella tabella rappresenta un agente utente</span><span class="sxs-lookup"><span data-stu-id="bf3e5-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="bf3e5-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="bf3e5-107">**Column**</span></span>|<span data-ttu-id="bf3e5-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="bf3e5-108">**Data Type**</span></span>|<span data-ttu-id="bf3e5-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="bf3e5-109">**Key/Index**</span></span>|<span data-ttu-id="bf3e5-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="bf3e5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bf3e5-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="bf3e5-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="bf3e5-112">int</span><span class="sxs-lookup"><span data-stu-id="bf3e5-112">int</span></span>  <br/> |<span data-ttu-id="bf3e5-113">Principale</span><span class="sxs-lookup"><span data-stu-id="bf3e5-113">Primary</span></span>  <br/> |<span data-ttu-id="bf3e5-114">Numero univoco che identifica l'agente utente.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="bf3e5-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="bf3e5-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="bf3e5-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="bf3e5-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="bf3e5-117">Univoco</span><span class="sxs-lookup"><span data-stu-id="bf3e5-117">Unique</span></span>  <br/> |<span data-ttu-id="bf3e5-118">Stringa agente utente.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="bf3e5-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="bf3e5-119">**UAType**</span></span> <br/> |<span data-ttu-id="bf3e5-120">smallint</span><span class="sxs-lookup"><span data-stu-id="bf3e5-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="bf3e5-121">1 è Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="bf3e5-122">2 è A/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="bf3e5-123">4 è Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="bf3e5-124">8 è telefono IP.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="bf3e5-125">16 è live meeting console.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="bf3e5-126">32 è lo strumento di convalida della distribuzione (DVT).</span><span class="sxs-lookup"><span data-stu-id="bf3e5-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="bf3e5-127">64 è Skype for Business Server su computer Macintosh.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="bf3e5-128">128 è Skype for Business Server Attendant.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="bf3e5-129">256 è il servizio Annuncio conferenza.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="bf3e5-130">512 è il numero di Operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="bf3e5-131">1024 è l'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="bf3e5-132">Il 2048 è esterno al controllo vocale.</span><span class="sxs-lookup"><span data-stu-id="bf3e5-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

