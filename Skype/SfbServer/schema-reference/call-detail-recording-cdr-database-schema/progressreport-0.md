---
title: Visualizzazione ProgressReport
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
ms.assetid: b49f3fc7-0e2f-498f-8505-aaaf54e435f9
description: La Visualizzazione ProgressReport archivia le informazioni sulle sessioni completate. I report sullo stato di avanzamento verranno scritti solo per le chiamate e le sessioni che Lync Server 2013 determina può essere utile per scopi diagnostici. Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: c07b9db8ebd9f898ab9d8feb5b07c4723209522c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814984"
---
# <a name="progressreport-view"></a><span data-ttu-id="9c047-105">Visualizzazione ProgressReport</span><span class="sxs-lookup"><span data-stu-id="9c047-105">ProgressReport view</span></span>
 
<span data-ttu-id="9c047-106">La Visualizzazione ProgressReport archivia le informazioni sulle sessioni completate.</span><span class="sxs-lookup"><span data-stu-id="9c047-106">The ProgressReport view stores information about completed sessions.</span></span> <span data-ttu-id="9c047-107">I report sullo stato di avanzamento verranno scritti solo per le chiamate e le sessioni che Lync Server 2013 determina può essere utile per scopi diagnostici.</span><span class="sxs-lookup"><span data-stu-id="9c047-107">Progress reports will be written only for calls and sessions that Lync Server 2013 determines might be useful for diagnostic purposes.</span></span> <span data-ttu-id="9c047-108">Questa visualizzazione è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9c047-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="9c047-109">I campi ErrorTime, ErrorReportSeq e ProgressReportSeq non si riferiscono necessariamente agli errori, ma ai messaggi che indicano lo stato delle chiamate o dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="9c047-109">The ErrorTime, ErrorReportSeq and ProgressReportSeq fields don't necessarily refer to errors but to messages that indicate the status of calls or messages.</span></span> 
  
|<span data-ttu-id="9c047-110">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="9c047-110">**Column**</span></span>|<span data-ttu-id="9c047-111">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="9c047-111">**Data Type**</span></span>|<span data-ttu-id="9c047-112">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="9c047-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9c047-113">**ErrorTime**</span><span class="sxs-lookup"><span data-stu-id="9c047-113">**ErrorTime**</span></span> <br/> |<span data-ttu-id="9c047-114">DateTime</span><span class="sxs-lookup"><span data-stu-id="9c047-114">datetime</span></span>  <br/> |<span data-ttu-id="9c047-115">Periodo di errore.</span><span class="sxs-lookup"><span data-stu-id="9c047-115">Time of error occurred.</span></span> <span data-ttu-id="9c047-116">Usato in combinazione con ErrorReportSeq per identificare in modo univoco un errore.</span><span class="sxs-lookup"><span data-stu-id="9c047-116">Used in conjunction with ErrorReportSeq to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="9c047-117">**ErrorReportSeq**</span><span class="sxs-lookup"><span data-stu-id="9c047-117">**ErrorReportSeq**</span></span> <br/> |<span data-ttu-id="9c047-118">int</span><span class="sxs-lookup"><span data-stu-id="9c047-118">int</span></span>  <br/> |<span data-ttu-id="9c047-119">Numero ID per identificare l'errore.</span><span class="sxs-lookup"><span data-stu-id="9c047-119">ID number to identify the error.</span></span> <span data-ttu-id="9c047-120">Usato in combinazione con ErrorTime per identificare in modo univoco un errore.</span><span class="sxs-lookup"><span data-stu-id="9c047-120">Used in conjunction with ErrorTime to uniquely identify an error.</span></span>  <br/> |
|<span data-ttu-id="9c047-121">**ProgressReportSeq**</span><span class="sxs-lookup"><span data-stu-id="9c047-121">**ProgressReportSeq**</span></span> <br/> |<span data-ttu-id="9c047-122">int</span><span class="sxs-lookup"><span data-stu-id="9c047-122">int</span></span>  <br/> |<span data-ttu-id="9c047-123">ID per identificare il report di stato.</span><span class="sxs-lookup"><span data-stu-id="9c047-123">ID to identify the progress report.</span></span> <span data-ttu-id="9c047-124">Usato per distinguere i report sullo stato dello stesso rapporto di errore.</span><span class="sxs-lookup"><span data-stu-id="9c047-124">Used to distinguish progress reports of the same error report.</span></span>  <br/> |
|<span data-ttu-id="9c047-125">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="9c047-125">**MsDiagId**</span></span> <br/> |<span data-ttu-id="9c047-126">int</span><span class="sxs-lookup"><span data-stu-id="9c047-126">int</span></span>  <br/> |<span data-ttu-id="9c047-127">ID di diagnostica per il report degli errori.</span><span class="sxs-lookup"><span data-stu-id="9c047-127">Diagnostic ID for the error report.</span></span>  <br/> |
|<span data-ttu-id="9c047-128">**Fonte**</span><span class="sxs-lookup"><span data-stu-id="9c047-128">**Source**</span></span> <br/> |<span data-ttu-id="9c047-129">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9c047-129">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9c047-130">Nome del server che ha originato l'errore (se il report è stato inviato da un componente server).</span><span class="sxs-lookup"><span data-stu-id="9c047-130">Name of server that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="9c047-131">**Applicazione**</span><span class="sxs-lookup"><span data-stu-id="9c047-131">**Application**</span></span> <br/> |<span data-ttu-id="9c047-132">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9c047-132">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9c047-133">Nome dell'applicazione che ha originato l'errore (se il report è stato inviato da un componente server).</span><span class="sxs-lookup"><span data-stu-id="9c047-133">Name of application that originated the error (if report was sent from a server component).</span></span>  <br/> |
|<span data-ttu-id="9c047-134">**TelemetryId**</span><span class="sxs-lookup"><span data-stu-id="9c047-134">**TelemetryId**</span></span> <br/> |<span data-ttu-id="9c047-135">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="9c047-135">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="9c047-136">Identificatore univoco che correla le informazioni sul tempo di join per i diversi componenti coinvolti in una conferenza.</span><span class="sxs-lookup"><span data-stu-id="9c047-136">Unique identifier correlating join time information for the different components involved in a conference.</span></span>  <br/> |
|<span data-ttu-id="9c047-137">**SessionSetupTime**</span><span class="sxs-lookup"><span data-stu-id="9c047-137">**SessionSetupTime**</span></span> <br/> |<span data-ttu-id="9c047-138">int</span><span class="sxs-lookup"><span data-stu-id="9c047-138">int</span></span>  <br/> |<span data-ttu-id="9c047-139">Ora (in millisecondi) necessaria per un componente specifico per partecipare a una conferenza.</span><span class="sxs-lookup"><span data-stu-id="9c047-139">Time (in milliseconds) required for a specific component to join a conference.</span></span>  <br/> |
|<span data-ttu-id="9c047-140">**MsDiagHeader**</span><span class="sxs-lookup"><span data-stu-id="9c047-140">**MsDiagHeader**</span></span> <br/> |<span data-ttu-id="9c047-141">varchar (max)</span><span class="sxs-lookup"><span data-stu-id="9c047-141">varchar(max)</span></span>  <br/> |<span data-ttu-id="9c047-142">Altre informazioni sugli errori.</span><span class="sxs-lookup"><span data-stu-id="9c047-142">Additional error information.</span></span>  <br/> |
   

