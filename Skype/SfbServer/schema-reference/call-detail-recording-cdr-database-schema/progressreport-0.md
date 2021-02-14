---
title: Visualizzazione ProgressReport
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
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: Nella visualizzazione ProgressReport vengono archiviate le informazioni relative alle sessioni completate. Tali rapporti sullo stato verranno scritti solo per le chiamate e le sessioni ritenute utili da Lync Server 2013 a fini diagnostici. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 6cc8295e73463fff9d4913efbf9d4844f9316149
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823186"
---
# <a name="progressreport-view"></a><span data-ttu-id="93a28-105">Visualizzazione ProgressReport</span><span class="sxs-lookup"><span data-stu-id="93a28-105">ProgressReport view</span></span>
 
<span data-ttu-id="93a28-106">Nella visualizzazione ProgressReport vengono archiviate le informazioni relative alle sessioni completate.</span><span class="sxs-lookup"><span data-stu-id="93a28-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="93a28-107">Tali rapporti sullo stato verranno scritti solo per le chiamate e le sessioni ritenute utili da Lync Server 2013 a fini diagnostici.</span><span class="sxs-lookup"><span data-stu-id="93a28-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="93a28-108">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="93a28-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="93a28-109">I campi ErrorTime, ErrorReportSeq e ProgressReportSeq non fanno necessariamente riferimento a errori, ma a messaggi che indicano lo stato delle chiamate o dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="93a28-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="93a28-110">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="93a28-110">**Column**</span></span>|<span data-ttu-id="93a28-111">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="93a28-111">**Data Type**</span></span>|<span data-ttu-id="93a28-112">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="93a28-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="93a28-113">**ErrorTime**</span><span class="sxs-lookup"><span data-stu-id="93a28-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="93a28-114">datetime</span><span class="sxs-lookup"><span data-stu-id="93a28-114">datetime</span></span>  <br/> |<span data-ttu-id="93a28-p103">Data/ora in cui si è verificato l'errore. Valore utilizzato con ErrorReportSeq per identificare in modo univoco un errore.</span><span class="sxs-lookup"><span data-stu-id="93a28-p103">Time of error occurred. Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="93a28-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="93a28-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="93a28-118">int</span><span class="sxs-lookup"><span data-stu-id="93a28-118">int</span></span>  <br/> |<span data-ttu-id="93a28-p104">ID che identifica l'errore. Questo valore viene utilizzato insieme a ErrorTime per identificare in modo univoco un errore.</span><span class="sxs-lookup"><span data-stu-id="93a28-p104">ID number to identify the error. Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="93a28-121">**ProgressReportSeq**</span><span class="sxs-lookup"><span data-stu-id="93a28-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="93a28-122">int</span><span class="sxs-lookup"><span data-stu-id="93a28-122">int</span></span>  <br/> |<span data-ttu-id="93a28-123">ID che identifica il rapporto sullo stato.</span><span class="sxs-lookup"><span data-stu-id="93a28-123">ID to identify the progress report.</span></span> <span data-ttu-id="93a28-124">Questo valore viene utilizzato per distinguere i rapporti sullo stato della stessa segnalazione di errore.</span><span class="sxs-lookup"><span data-stu-id="93a28-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="93a28-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="93a28-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="93a28-126">int</span><span class="sxs-lookup"><span data-stu-id="93a28-126">int</span></span>  <br/> |<span data-ttu-id="93a28-127">ID diagnostica della segnalazione di errore.</span><span class="sxs-lookup"><span data-stu-id="93a28-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="93a28-128">**Source**</span><span class="sxs-lookup"><span data-stu-id="93a28-128">**Source**</span></span> <br/> |<span data-ttu-id="93a28-129">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="93a28-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="93a28-130">Nome del server che ha dato origine all'errore (se il rapporto è stato inviato da un componente del server).</span><span class="sxs-lookup"><span data-stu-id="93a28-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="93a28-131">**Applicazione**</span><span class="sxs-lookup"><span data-stu-id="93a28-131">**Application**</span></span> <br/> |<span data-ttu-id="93a28-132">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="93a28-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="93a28-133">Nome dell'applicazione da cui ha avuto origine l'errore (se la segnalazione è stata inviata da un componente server).</span><span class="sxs-lookup"><span data-stu-id="93a28-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="93a28-134">**TelemetryId**</span><span class="sxs-lookup"><span data-stu-id="93a28-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="93a28-135">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="93a28-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="93a28-136">Identificatore univoco di correlazione delle informazioni sul tempo di partecipazione per i diversi componenti coinvolti in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="93a28-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="93a28-137">**SessionSetupTime**</span><span class="sxs-lookup"><span data-stu-id="93a28-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="93a28-138">int</span><span class="sxs-lookup"><span data-stu-id="93a28-138">int</span></span>  <br/> |<span data-ttu-id="93a28-139">Intervallo di tempo, in millisecondi, necessario a un componente specifico per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="93a28-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="93a28-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="93a28-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="93a28-141">varchar(max)</span><span class="sxs-lookup"><span data-stu-id="93a28-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="93a28-142">Ulteriori informazioni sull'errore.</span><span class="sxs-lookup"><span data-stu-id="93a28-142">Additional error information.</span></span>  <br/> |
   

