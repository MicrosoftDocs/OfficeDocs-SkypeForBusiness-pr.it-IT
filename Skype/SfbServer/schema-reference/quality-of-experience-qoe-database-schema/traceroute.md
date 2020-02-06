---
title: Tabella TraceRoute
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
ms.assetid: b9493cef-6ece-4f13-bf68-dbf132aab4f4
description: La tabella TraceRoute contiene le informazioni di routing dalle chiamate. Questa tabella è stata introdotta in Microsoft Lync Server 2013.
ms.openlocfilehash: e257bf6d89d04cd0f4784e62e7ac2876b6ede7e5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805114"
---
# <a name="traceroute-table"></a><span data-ttu-id="da1f9-104">Tabella TraceRoute</span><span class="sxs-lookup"><span data-stu-id="da1f9-104">TraceRoute table</span></span>
 
<span data-ttu-id="da1f9-105">La tabella TraceRoute contiene le informazioni di routing dalle chiamate.</span><span class="sxs-lookup"><span data-stu-id="da1f9-105">The TraceRoute table contains routing information from calls.</span></span> <span data-ttu-id="da1f9-106">Questa tabella è stata introdotta in Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="da1f9-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="da1f9-107">**Colonna**</span><span class="sxs-lookup"><span data-stu-id="da1f9-107">**Column**</span></span>|<span data-ttu-id="da1f9-108">**Tipo di dati**</span><span class="sxs-lookup"><span data-stu-id="da1f9-108">**Data Type**</span></span>|<span data-ttu-id="da1f9-109">**Chiave/indice**</span><span class="sxs-lookup"><span data-stu-id="da1f9-109">**Key/Index**</span></span>|<span data-ttu-id="da1f9-110">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="da1f9-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="da1f9-111">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="da1f9-111">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="da1f9-112">DateTime</span><span class="sxs-lookup"><span data-stu-id="da1f9-112">datetime</span></span>  <br/> |<span data-ttu-id="da1f9-113">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="da1f9-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="da1f9-114">Data e ora di inizio della chiamata.</span><span class="sxs-lookup"><span data-stu-id="da1f9-114">Date and time that the call began.</span></span>  <br/> |
|<span data-ttu-id="da1f9-115">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="da1f9-115">**SessionSeq**</span></span> <br/> |<span data-ttu-id="da1f9-116">int</span><span class="sxs-lookup"><span data-stu-id="da1f9-116">int</span></span>  <br/> |<span data-ttu-id="da1f9-117">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="da1f9-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="da1f9-118">Identificatore univoco usato per distinguere tra più chiamate che potrebbero essere iniziate nella stessa data e contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="da1f9-118">Unique identifier used to distinguish between multiple calls that might have begun on the same date and at the same time.</span></span>  <br/> |
|<span data-ttu-id="da1f9-119">**MediaLineLabel**</span><span class="sxs-lookup"><span data-stu-id="da1f9-119">**MediaLineLabel**</span></span> <br/> |<span data-ttu-id="da1f9-120">tinyint</span><span class="sxs-lookup"><span data-stu-id="da1f9-120">tinyint</span></span>  <br/> |<span data-ttu-id="da1f9-121">Primaria, straniera</span><span class="sxs-lookup"><span data-stu-id="da1f9-121">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="da1f9-122">Rappresenta il tipo di linea video usato nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="da1f9-122">Represents the type of video line used in the call.</span></span> <span data-ttu-id="da1f9-123">I valori consentiti sono:</span><span class="sxs-lookup"><span data-stu-id="da1f9-123">Allowed values are:</span></span>  <br/> <span data-ttu-id="da1f9-124">0-audio</span><span class="sxs-lookup"><span data-stu-id="da1f9-124">0 - Audio</span></span>  <br/> <span data-ttu-id="da1f9-125">1-video</span><span class="sxs-lookup"><span data-stu-id="da1f9-125">1 - Video</span></span>  <br/> <span data-ttu-id="da1f9-126">2-video panoramico</span><span class="sxs-lookup"><span data-stu-id="da1f9-126">2 - Panoramic video</span></span>  <br/> <span data-ttu-id="da1f9-127">3-condivisione di applicazioni/desktop</span><span class="sxs-lookup"><span data-stu-id="da1f9-127">3 - Application/Desktop sharing</span></span>  <br/> |
|<span data-ttu-id="da1f9-128">**FromCaller**</span><span class="sxs-lookup"><span data-stu-id="da1f9-128">**FromCaller**</span></span> <br/> |<span data-ttu-id="da1f9-129">po'</span><span class="sxs-lookup"><span data-stu-id="da1f9-129">bit</span></span>  <br/> |<span data-ttu-id="da1f9-130">Principale</span><span class="sxs-lookup"><span data-stu-id="da1f9-130">Primary</span></span>  <br/> |<span data-ttu-id="da1f9-131">Endpoint che ha posto la chiamata.</span><span class="sxs-lookup"><span data-stu-id="da1f9-131">Endpoint that placed the call.</span></span>  <br/> |
|<span data-ttu-id="da1f9-132">**Hop**</span><span class="sxs-lookup"><span data-stu-id="da1f9-132">**Hop**</span></span> <br/> |<span data-ttu-id="da1f9-133">int</span><span class="sxs-lookup"><span data-stu-id="da1f9-133">int</span></span>  <br/> ||<span data-ttu-id="da1f9-134">Hop di rete/</span><span class="sxs-lookup"><span data-stu-id="da1f9-134">Network hop/</span></span>  <br/> |
|<span data-ttu-id="da1f9-135">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="da1f9-135">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="da1f9-136">int</span><span class="sxs-lookup"><span data-stu-id="da1f9-136">int</span></span>  <br/> |<span data-ttu-id="da1f9-137">Esterna</span><span class="sxs-lookup"><span data-stu-id="da1f9-137">Foreign</span></span>  <br/> |<span data-ttu-id="da1f9-138">Identificatore univoco per l'indirizzo IP.</span><span class="sxs-lookup"><span data-stu-id="da1f9-138">Unique identifier for the IP address.</span></span> <span data-ttu-id="da1f9-139">Le informazioni sull'indirizzo IP sono archiviate nella [tabella IPAddress](ipaddress.md).</span><span class="sxs-lookup"><span data-stu-id="da1f9-139">IP address information is stored in the [IPAddress table](ipaddress.md).</span></span>  <br/> |
|<span data-ttu-id="da1f9-140">**RTT**</span><span class="sxs-lookup"><span data-stu-id="da1f9-140">**RTT**</span></span> <br/> |<span data-ttu-id="da1f9-141">int</span><span class="sxs-lookup"><span data-stu-id="da1f9-141">int</span></span>  <br/> ||<span data-ttu-id="da1f9-142">Ora di andata e ritorno.</span><span class="sxs-lookup"><span data-stu-id="da1f9-142">Roundtrip time.</span></span> <span data-ttu-id="da1f9-143">Il tempo di andata e ritorno misura la quantità di tempo necessaria per il pacchetto vocale per raggiungere la destinazione e quindi inviare di nuovo la notifica che è stata ricevuta.</span><span class="sxs-lookup"><span data-stu-id="da1f9-143">The roundtrip time measures the amount of time it takes for a voice packet to reach its destination and then send back notification that it was received.</span></span>  <br/> |
   

