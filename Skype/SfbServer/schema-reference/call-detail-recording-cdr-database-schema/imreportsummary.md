---
title: Tabella IMReportSummary in Skype for Business Server
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
ms.assetid: 27ff9453-53f2-4fae-b637-70a086c9df96
description: La tabella IMReportSummaryTable offre un rapporto complessivo sulle sessioni di messaggistica istantanea eseguite in un'organizzazione. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 6a80918376440c13d60e059744d88c09c2705853
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821526"
---
# <a name="imreportsummary-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c385a-104">Tabella IMReportSummary in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="c385a-104">IMReportSummary table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c385a-105">La tabella IMReportSummaryTable offre un rapporto complessivo sulle sessioni di messaggistica istantanea eseguite in un'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c385a-105">The IMReportSummaryTable provides an overall report on the instant messaging sessions held in an organization.</span></span> <span data-ttu-id="c385a-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="c385a-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="c385a-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="c385a-107">**Column**</span></span>|<span data-ttu-id="c385a-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="c385a-108">**Data Type**</span></span>|<span data-ttu-id="c385a-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="c385a-109">**Key/Index**</span></span>|<span data-ttu-id="c385a-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="c385a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c385a-111">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="c385a-111">**StartTime**</span></span> <br/> |<span data-ttu-id="c385a-112">datetime</span><span class="sxs-lookup"><span data-stu-id="c385a-112">datetime</span></span>  <br/> |<span data-ttu-id="c385a-113">Principale</span><span class="sxs-lookup"><span data-stu-id="c385a-113">Primary</span></span>  <br/> |<span data-ttu-id="c385a-114">Data e ora di inizio della sessione di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="c385a-114">Date and time that the instant messaging session began.</span></span>  <br/> |
|<span data-ttu-id="c385a-115">**TimePeriod**</span><span class="sxs-lookup"><span data-stu-id="c385a-115">**TimePeriod**</span></span> <br/> |<span data-ttu-id="c385a-116">char(1)</span><span class="sxs-lookup"><span data-stu-id="c385a-116">char(1)</span></span>  <br/> |<span data-ttu-id="c385a-117">Principale</span><span class="sxs-lookup"><span data-stu-id="c385a-117">Primary</span></span>  <br/> ||
|<span data-ttu-id="c385a-118">**PoolFQDN**</span><span class="sxs-lookup"><span data-stu-id="c385a-118">**PoolFQDN**</span></span> <br/> |<span data-ttu-id="c385a-119">nvarchar(257)</span><span class="sxs-lookup"><span data-stu-id="c385a-119">nvarchar(257)</span></span>  <br/> |<span data-ttu-id="c385a-120">Principale</span><span class="sxs-lookup"><span data-stu-id="c385a-120">Primary</span></span>  <br/> |<span data-ttu-id="c385a-121">Nome di dominio completo del pool che ospita la sessione.</span><span class="sxs-lookup"><span data-stu-id="c385a-121">Fully qualified domain name of the pool hosting the session.</span></span>  <br/> |
|<span data-ttu-id="c385a-122">**AuthType**</span><span class="sxs-lookup"><span data-stu-id="c385a-122">**AuthType**</span></span> <br/> |<span data-ttu-id="c385a-123">int</span><span class="sxs-lookup"><span data-stu-id="c385a-123">int</span></span>  <br/> |<span data-ttu-id="c385a-124">Principale</span><span class="sxs-lookup"><span data-stu-id="c385a-124">Primary</span></span>  <br/> |<span data-ttu-id="c385a-125">Priorità della chiamata, ad esempio urgente o non urgente.</span><span class="sxs-lookup"><span data-stu-id="c385a-125">Priority (for example, urgent or non-urgent) of the call.</span></span> <span data-ttu-id="c385a-126">Le informazioni sulla priorità vengono archiviate nella [tabella CallPriorities in Skype for Business Server 2015.](callpriorities.md)</span><span class="sxs-lookup"><span data-stu-id="c385a-126">Priority information is stored in the [CallPriorities table in Skype for Business Server 2015](callpriorities.md).</span></span>  <br/> |
|<span data-ttu-id="c385a-127">**SessionCount**</span><span class="sxs-lookup"><span data-stu-id="c385a-127">**SessionCount**</span></span> <br/> |<span data-ttu-id="c385a-128">bigint</span><span class="sxs-lookup"><span data-stu-id="c385a-128">bigint</span></span>  <br/> |||
|<span data-ttu-id="c385a-129">**MsgCount**</span><span class="sxs-lookup"><span data-stu-id="c385a-129">**MsgCount**</span></span> <br/> |<span data-ttu-id="c385a-130">bigint</span><span class="sxs-lookup"><span data-stu-id="c385a-130">bigint</span></span>  <br/> ||<span data-ttu-id="c385a-131">Numero totale di messaggi istantanei scambiati durante la sessione.</span><span class="sxs-lookup"><span data-stu-id="c385a-131">Total number of instant messages exchanged during the session.</span></span>  <br/> |
   

