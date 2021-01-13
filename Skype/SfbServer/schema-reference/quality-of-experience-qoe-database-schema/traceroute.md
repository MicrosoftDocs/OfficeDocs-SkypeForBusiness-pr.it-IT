---
title: Tabella TraceRoute
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
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: Nella tabella TraceRoute sono incluse le informazioni di routing provenienti dalle chiamate. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: 7ecad93cca80a9b7cea73f64158b3c0008a1d6e7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831326"
---
# <a name="traceroute-table"></a><span data-ttu-id="14430-104">Tabella TraceRoute</span><span class="sxs-lookup"><span data-stu-id="14430-104">TraceRoute table</span></span>
 
<span data-ttu-id="14430-105">Nella tabella TraceRoute sono incluse le informazioni di routing provenienti dalle chiamate.</span><span class="sxs-lookup"><span data-stu-id="14430-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="14430-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="14430-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="14430-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="14430-107">**Column**</span></span>|<span data-ttu-id="14430-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="14430-108">**Data Type**</span></span>|<span data-ttu-id="14430-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="14430-109">**Key/Index**</span></span>|<span data-ttu-id="14430-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="14430-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="14430-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="14430-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="14430-112">datetime</span><span class="sxs-lookup"><span data-stu-id="14430-112">datetime</span></span>  <br/> |<span data-ttu-id="14430-113">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="14430-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="14430-114">Data e ora di inizio della chiamata.</span><span class="sxs-lookup"><span data-stu-id="14430-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="14430-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="14430-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="14430-116">int</span><span class="sxs-lookup"><span data-stu-id="14430-116">int</span></span>  <br/> |<span data-ttu-id="14430-117">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="14430-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="14430-118">Identificatore univoco utilizzato per distinguere le diverse chiamate che possono essere iniziate nella stessa data e alla stessa ora.</span><span class="sxs-lookup"><span data-stu-id="14430-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="14430-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="14430-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="14430-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="14430-120">tinyint</span></span>  <br/> |<span data-ttu-id="14430-121">Primaria, esterna</span><span class="sxs-lookup"><span data-stu-id="14430-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="14430-p103">Rappresenta il tipo di linea video utilizzato nella chiamata. I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="14430-p103">Represents the type of video line used in the call. Allowed values are:</span></span>  <br/> <span data-ttu-id="14430-124">0-audio</span><span class="sxs-lookup"><span data-stu-id="14430-124">0 - Audio</span></span>  <br/> <span data-ttu-id="14430-125">1-video</span><span class="sxs-lookup"><span data-stu-id="14430-125">1 - Video</span></span>  <br/> <span data-ttu-id="14430-126">2-Panoramica video</span><span class="sxs-lookup"><span data-stu-id="14430-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="14430-127">3-condivisione di applicazioni/desktop</span><span class="sxs-lookup"><span data-stu-id="14430-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="14430-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="14430-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="14430-129">po'</span><span class="sxs-lookup"><span data-stu-id="14430-129">bit</span></span>  <br/> |<span data-ttu-id="14430-130">Principale</span><span class="sxs-lookup"><span data-stu-id="14430-130">Primary</span></span>  <br/> |<span data-ttu-id="14430-131">Endpoint che ha effettuato la chiamata.</span><span class="sxs-lookup"><span data-stu-id="14430-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="14430-132">**Hop**</span><span class="sxs-lookup"><span data-stu-id="14430-132">**Hop**</span></span> <br/> |<span data-ttu-id="14430-133">int</span><span class="sxs-lookup"><span data-stu-id="14430-133">int</span></span>  <br/> ||<span data-ttu-id="14430-134">Hop di rete.</span><span class="sxs-lookup"><span data-stu-id="14430-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="14430-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="14430-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="14430-136">int</span><span class="sxs-lookup"><span data-stu-id="14430-136">int</span></span>  <br/> |<span data-ttu-id="14430-137">Stranieri</span><span class="sxs-lookup"><span data-stu-id="14430-137">Foreign</span></span>  <br/> |<span data-ttu-id="14430-138">Identificatore univoco dell'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="14430-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="14430-139">Le informazioni sull'indirizzo IP sono archiviate nella [tabella IPAddress](ipaddress.md).</span><span class="sxs-lookup"><span data-stu-id="14430-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="14430-140">**RTT**</span><span class="sxs-lookup"><span data-stu-id="14430-140">**RTT**</span></span> <br/> |<span data-ttu-id="14430-141">int</span><span class="sxs-lookup"><span data-stu-id="14430-141">int</span></span>  <br/> ||<span data-ttu-id="14430-p105">Tempo di roundtrip, ovvero la quantità di tempo necessaria a un pacchetto voce per raggiungere la relativa destinazione e quindi inviare di nuovo la notifica ricevuta.</span><span class="sxs-lookup"><span data-stu-id="14430-p105">Roundtrip time. The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

