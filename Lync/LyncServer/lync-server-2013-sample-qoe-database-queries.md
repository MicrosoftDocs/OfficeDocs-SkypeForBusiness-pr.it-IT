---
title: 'Lync Server 2013: query del database QoE di esempio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Sample QoE database queries
ms:assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398100(v=OCS.15)
ms:contentKeyID: 48183280
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 441384c2ed8dae6f03aa6034ceba2248710e9d3c
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511023"
---
# <a name="sample-qoe-database-queries-in-lync-server-2013"></a><span data-ttu-id="1316f-102">Query del database QoE di esempio in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1316f-102">Sample QoE database queries in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1316f-103">_**Ultimo argomento modificato:** 2012-10-17_</span><span class="sxs-lookup"><span data-stu-id="1316f-103">_**Topic Last Modified:** 2012-10-17_</span></span>

<span data-ttu-id="1316f-104">In questa sezione sono incluse query di esempio per il database della qualità percepita dagli utenti (QoE).</span><span class="sxs-lookup"><span data-stu-id="1316f-104">This section contains sample queries for the Quality of Experience (QoE) database.</span></span>

<span data-ttu-id="1316f-105">Utilizzare l'esempio seguente per ottenere l'instabilità e la perdita di pacchetti medie per tutti i flussi audio.</span><span class="sxs-lookup"><span data-stu-id="1316f-105">Use the following example to get the jitter and packet loss average for all audio streams.</span></span>

    select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream

<span data-ttu-id="1316f-106">Utilizzare l'esempio seguente per trovare i totali relativi alle conferenze per cui è stata utilizzata la console per riunioni.</span><span class="sxs-lookup"><span data-stu-id="1316f-106">Use the following example to find the total numbers of conferences that used Meeting Console.</span></span>

    select avg(ConversationalMOS)
    from SessionView s
    inner join MediaLineView m
    on s.ConferenceDateTime = m.ConferenceDateTime
       and s.SessionSeq = m.SessionSeq
       and m.MediaLineLabel = 0 -- audio media line
       and s.CallerUserAgentType = 4 -- Lync
       and s.CalleeUserAgentType = 4 -- Lync

<span data-ttu-id="1316f-107">Utilizzare l'esempio seguente per ottenere ConversstionalMOS, SendingMOS e ListendingMOS per dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="1316f-107">Use the following example to get ConversstionalMOS, SendingMOS and ListendingMOS per capture device.</span></span>

    select t.DeviceName as Device, count(*) as SampleNum, avg(ConversationalMOS) as ConversationalMOS, avg(SendListenMOS) SendingMOS, avg(RecvListenMOS) as ListendingMOS
    from
    (
       select m.CallerCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
       from MediaLineView m
       inner join AudioStream a
       on m.ConferenceDateTime = a.ConferenceDateTime
          and m.SessionSeq = a.SessionSeq
          and m.MediaLineLabel = 0
    
       union
    
       select m.CalleeCaptureDev as DeviceName, m.ConferenceDateTime, m.SessionSeq, a.StreamID, m.ConversationalMOS,a.SendListenMOS, a.RecvListenMOS
       from MediaLineView m
       inner join AudioStream a
       on m.ConferenceDateTime = a.ConferenceDateTime
          and m.SessionSeq = a.SessionSeq
          and m.MediaLineLabel = 0
    
    )as t
    group by t.DeviceName
    order by SampleNum desc

</div>

<span> </span>

</div>

</div>

</div>

