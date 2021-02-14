---
title: Tabella Media
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
ms.assetid: 1e1b427f-59b5-4564-bde5-1002a80439ee
description: Ogni record rappresenta un tipo di supporto multimediale utilizzato in una sessione peer-to-peer. Una sessione viene rappresentata da più record nella tabella se viene utilizzato più di un tipo di supporto multimediale.
ms.openlocfilehash: ce5b5a2b312307e608367279e4e871ed03063860
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800106"
---
# <a name="media-table"></a><span data-ttu-id="a9792-104">Tabella Media</span><span class="sxs-lookup"><span data-stu-id="a9792-104">Media table</span></span>
 
<span data-ttu-id="a9792-p102">Ogni record rappresenta un tipo di supporto multimediale utilizzato in una sessione peer-to-peer. Una sessione viene rappresentata da più record nella tabella se viene utilizzato più di un tipo di supporto multimediale.</span><span class="sxs-lookup"><span data-stu-id="a9792-p102">Each record represents one media type used in a peer-to-peer session. One session would be represented by multiple records in the table, if more than one media type is used.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a9792-p103">Non utilizzare la tabella Media per calcolare la durata media di una sessione. Questa tabella contiene i dettagli di segnalazione dello scambio multimediale in una sessione. Lo scambio multimediale viene eseguito dalla richiesta INVITE e StartTime indica l'ora di invio di tale richiesta. L'ora di invito non corrisponde necessariamente all'ora di inizio dello scambio multimediale, poiché questo inizia solo dopo che il destinatario ha accettato la sessione. EndTime in genere indica l'ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="a9792-p103">The Media table should not be used to calculate the media duration for a session. This table contains the signaling details of media exchange in a session. Media exchange is done by the INVITE request, and StartTime indicates the time that the INVITE was sent out. The invite time does not necessarily mean the media start time, because media starts only after the sessionee accepts the session. The EndTime usually means the end time of this session.</span></span> 
  
|<span data-ttu-id="a9792-111">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="a9792-111">**Column**</span></span>|<span data-ttu-id="a9792-112">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="a9792-112">**Data Type**</span></span>|<span data-ttu-id="a9792-113">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="a9792-113">**Key/Index**</span></span>|<span data-ttu-id="a9792-114">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="a9792-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a9792-115">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="a9792-115">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="a9792-116">datetime</span><span class="sxs-lookup"><span data-stu-id="a9792-116">datetime</span></span>  <br/> |<span data-ttu-id="a9792-117">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="a9792-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="a9792-118">Data e ora della richiesta di sessione.</span><span class="sxs-lookup"><span data-stu-id="a9792-118">Time of session request.</span></span> <span data-ttu-id="a9792-119">Valore utilizzato insieme a **SessionIdSeq** per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="a9792-119">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="a9792-120">Per ulteriori informazioni, vedere la tabella [Dialogs in Skype for Business Server 2015.](dialogs.md)</span><span class="sxs-lookup"><span data-stu-id="a9792-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a9792-121">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="a9792-121">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="a9792-122">int</span><span class="sxs-lookup"><span data-stu-id="a9792-122">int</span></span>  <br/> |<span data-ttu-id="a9792-123">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="a9792-123">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="a9792-124">Numero ID per identificare la sessione.</span><span class="sxs-lookup"><span data-stu-id="a9792-124">ID number to identify the session.</span></span> <span data-ttu-id="a9792-125">Valore utilizzato insieme a **SessionIdTime** per identificare in modo univoco una sessione.</span><span class="sxs-lookup"><span data-stu-id="a9792-125">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="a9792-126">Per ulteriori informazioni, vedere la tabella [Dialogs in Skype for Business Server 2015.](dialogs.md)</span><span class="sxs-lookup"><span data-stu-id="a9792-126">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a9792-127">**MediaId**</span><span class="sxs-lookup"><span data-stu-id="a9792-127">**MediaId**</span></span> <br/> |<span data-ttu-id="a9792-128">tinyint</span><span class="sxs-lookup"><span data-stu-id="a9792-128">tinyint</span></span>  <br/> |<span data-ttu-id="a9792-129">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="a9792-129">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="a9792-130">Numero univoco che identifica il tipo di elemento multimediale.</span><span class="sxs-lookup"><span data-stu-id="a9792-130">Unique number identifying this media type.</span></span> <span data-ttu-id="a9792-131">Per altre [informazioni, vedi la tabella MediaList.](medialist.md)</span><span class="sxs-lookup"><span data-stu-id="a9792-131">See the [MediaList table](medialist.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a9792-132">**StartTime**</span><span class="sxs-lookup"><span data-stu-id="a9792-132">**StartTime**</span></span> <br/> |<span data-ttu-id="a9792-133">datetime</span><span class="sxs-lookup"><span data-stu-id="a9792-133">datetime</span></span>  <br/> |<span data-ttu-id="a9792-134">Principale</span><span class="sxs-lookup"><span data-stu-id="a9792-134">Primary</span></span>  <br/> |<span data-ttu-id="a9792-p107">Indica l'ora di invio di una richiesta di scambio multimediale e non l'ora di inizio dello scambio multimediale effettivo. **StartTime** include il tempo di configurazione della sessione.</span><span class="sxs-lookup"><span data-stu-id="a9792-p107">This is the time that a media request was sent out, not the real media start time. **StartTime** includes the session setup time. </span></span><br/> |
|<span data-ttu-id="a9792-137">**EndTime**</span><span class="sxs-lookup"><span data-stu-id="a9792-137">**EndTime**</span></span> <br/> |<span data-ttu-id="a9792-138">datetime</span><span class="sxs-lookup"><span data-stu-id="a9792-138">datetime</span></span>  <br/> ||<span data-ttu-id="a9792-139">Ora di fine della sessione.</span><span class="sxs-lookup"><span data-stu-id="a9792-139">This is the end time of the session.</span></span>  <br/> |
   

