---
title: Tabella IMReportSummary in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: IMReportSummaryTable fornisce un report globale sulle sessioni di messaggistica istantanea svolte in un'organizzazione. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 647b8dc3e48e56d126a65f524de90954b7aeca8f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194790"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="6e8c7-104">Tabella IMReportSummary in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6e8c7-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6e8c7-105">IMReportSummaryTable fornisce un report globale sulle sessioni di messaggistica istantanea svolte in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="6e8c7-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="6e8c7-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6e8c7-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="6e8c7-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="6e8c7-107">**Column**</span></span>|<span data-ttu-id="6e8c7-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="6e8c7-108">**Data Type**</span></span>|<span data-ttu-id="6e8c7-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="6e8c7-109">**Key/Index**</span></span>|<span data-ttu-id="6e8c7-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="6e8c7-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6e8c7-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="6e8c7-111">**StartTime**</span></span> <br/> |<span data-ttu-id="6e8c7-112">DateTime</span><span class="sxs-lookup"><span data-stu-id="6e8c7-112">datetime</span></span>  <br/> |<span data-ttu-id="6e8c7-113">Principale</span><span class="sxs-lookup"><span data-stu-id="6e8c7-113">Primary</span></span>  <br/> |<span data-ttu-id="6e8c7-114">Data e ora di inizio della sessione di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="6e8c7-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="6e8c7-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="6e8c7-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="6e8c7-116">carattere (1)</span><span class="sxs-lookup"><span data-stu-id="6e8c7-116">char(1)</span></span>  <br/> |<span data-ttu-id="6e8c7-117">Principale</span><span class="sxs-lookup"><span data-stu-id="6e8c7-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="6e8c7-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="6e8c7-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="6e8c7-119">nvarchar (257)</span><span class="sxs-lookup"><span data-stu-id="6e8c7-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="6e8c7-120">Principale</span><span class="sxs-lookup"><span data-stu-id="6e8c7-120">Primary</span></span>  <br/> |<span data-ttu-id="6e8c7-121">Nome di dominio completo del pool che ospita la sessione.</span><span class="sxs-lookup"><span data-stu-id="6e8c7-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="6e8c7-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="6e8c7-122">**AuthType**</span></span> <br/> |<span data-ttu-id="6e8c7-123">int</span><span class="sxs-lookup"><span data-stu-id="6e8c7-123">int</span></span>  <br/> |<span data-ttu-id="6e8c7-124">Principale</span><span class="sxs-lookup"><span data-stu-id="6e8c7-124">Primary</span></span>  <br/> |<span data-ttu-id="6e8c7-125">Priorità, ad esempio urgente o non urgente, della chiamata.</span><span class="sxs-lookup"><span data-stu-id="6e8c7-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="6e8c7-126">Le informazioni prioritarie sono archiviate nella [Tabella CallPriorities in Skype for Business Server 2015](callpriorities.md).</span><span class="sxs-lookup"><span data-stu-id="6e8c7-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="6e8c7-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="6e8c7-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="6e8c7-128">bigint</span><span class="sxs-lookup"><span data-stu-id="6e8c7-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="6e8c7-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="6e8c7-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="6e8c7-130">bigint</span><span class="sxs-lookup"><span data-stu-id="6e8c7-130">bigint</span></span>  <br/> ||<span data-ttu-id="6e8c7-131">Numero totale di messaggi istantanei scambiati durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="6e8c7-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

