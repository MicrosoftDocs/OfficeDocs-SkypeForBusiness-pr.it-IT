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
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: La tabella UserAgent è una tabella di supporto in cui è archiviato un elenco dei vari agenti utente che hanno partecipato alle sessioni registrate nel database. Ogni record nella tabella rappresenta un solo agente utente
ms.openlocfilehash: f0c8a2f182611887db1324d17b6b7c28d6a9393d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194568"
---
# <a name="useragent-table"></a><span data-ttu-id="49974-104">Tabella UserAgent</span><span class="sxs-lookup"><span data-stu-id="49974-104">UserAgent table</span></span>
 
<span data-ttu-id="49974-105">La tabella UserAgent è una tabella di supporto in cui è archiviato un elenco dei vari agenti utente che hanno partecipato alle sessioni registrate nel database.</span><span class="sxs-lookup"><span data-stu-id="49974-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="49974-106">Ogni record nella tabella rappresenta un solo agente utente</span><span class="sxs-lookup"><span data-stu-id="49974-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="49974-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="49974-107">**Column**</span></span>|<span data-ttu-id="49974-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="49974-108">**Data Type**</span></span>|<span data-ttu-id="49974-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="49974-109">**Key/Index**</span></span>|<span data-ttu-id="49974-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="49974-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="49974-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="49974-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="49974-112">int</span><span class="sxs-lookup"><span data-stu-id="49974-112">int</span></span>  <br/> |<span data-ttu-id="49974-113">Principale</span><span class="sxs-lookup"><span data-stu-id="49974-113">Primary</span></span>  <br/> |<span data-ttu-id="49974-114">Numero univoco che identifica questo agente utente.</span><span class="sxs-lookup"><span data-stu-id="49974-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="49974-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="49974-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="49974-116">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="49974-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="49974-117">Univoci</span><span class="sxs-lookup"><span data-stu-id="49974-117">Unique</span></span>  <br/> |<span data-ttu-id="49974-118">Stringa agente utente.</span><span class="sxs-lookup"><span data-stu-id="49974-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="49974-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="49974-119">**UAType**</span></span> <br/> |<span data-ttu-id="49974-120">smallint</span><span class="sxs-lookup"><span data-stu-id="49974-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="49974-121">1 è Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="49974-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="49974-122">2 è un/V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="49974-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="49974-123">4 è Skype for business.</span><span class="sxs-lookup"><span data-stu-id="49974-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="49974-124">8 è il telefono IP.</span><span class="sxs-lookup"><span data-stu-id="49974-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="49974-125">16 è la console Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="49974-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="49974-126">32 è lo strumento di convalida della distribuzione (TVP).</span><span class="sxs-lookup"><span data-stu-id="49974-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="49974-127">64 è Skype for Business Server su computer Macintosh.</span><span class="sxs-lookup"><span data-stu-id="49974-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="49974-128">128 è Skype for Business Server Attendant.</span><span class="sxs-lookup"><span data-stu-id="49974-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="49974-129">256 è un servizio di annunci conferenza.</span><span class="sxs-lookup"><span data-stu-id="49974-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="49974-130">512 è operatore automatico di conferenza.</span><span class="sxs-lookup"><span data-stu-id="49974-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="49974-131">1024 è un'applicazione Response Group.</span><span class="sxs-lookup"><span data-stu-id="49974-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="49974-132">2048 è il controllo vocale esterno.</span><span class="sxs-lookup"><span data-stu-id="49974-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

