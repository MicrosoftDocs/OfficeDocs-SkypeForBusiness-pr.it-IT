---
title: Query di database QoE di esempio
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 04e6bdd3-bbd1-47ca-8114-94a3db6beeeb
description: In questa sezione sono incluse query di esempio per il database della qualità percepita dagli utenti (QoE).
ms.openlocfilehash: efc26064e52464ffc2e92e24d5af8dd848368b56
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834366"
---
# <a name="sample-qoe-database-queries"></a><span data-ttu-id="0fbe4-103">Query di database QoE di esempio</span><span class="sxs-lookup"><span data-stu-id="0fbe4-103">Sample QoE database queries</span></span>
 
<span data-ttu-id="0fbe4-104">In questa sezione sono incluse query di esempio per il database della qualità percepita dagli utenti (QoE).</span><span class="sxs-lookup"><span data-stu-id="0fbe4-104">This section contains sample queries for the Quality of Experience (QoE) database.</span></span> 
  
<span data-ttu-id="0fbe4-105">Utilizzare l'esempio seguente per ottenere l'instabilità e la perdita di pacchetti medie per tutti i flussi audio.</span><span class="sxs-lookup"><span data-stu-id="0fbe4-105">Use the following example to get the jitter and packet loss average for all audio streams.</span></span>
  
```SQL
select avg(cast(JitterInterArrival as bigint)) as JitterAvg, avg(PacketLossRate) as PacketLossRateAvg from AudioStream
```

<span data-ttu-id="0fbe4-106">Utilizzare l'esempio seguente per trovare i totali relativi alle conferenze per cui è stata utilizzata la console per riunioni.</span><span class="sxs-lookup"><span data-stu-id="0fbe4-106">Use the following example to find the total numbers of conferences that used Meeting Console.</span></span>
  
```SQL
select avg(ConversationalMOS)
from SessionView s
inner join MediaLineView m
on s.ConferenceDateTime = m.ConferenceDateTime
   and s.SessionSeq = m.SessionSeq
   and m.MediaLineLabel = 0 -- audio media line
   and s.CallerUserAgentType = 4 -- Lync
   and s.CalleeUserAgentType = 4 -- Lync
```

<span data-ttu-id="0fbe4-107">Utilizzare l'esempio seguente per ottenere ConversstionalMOS, SendingMOS e ListendingMOS per dispositivo di acquisizione.</span><span class="sxs-lookup"><span data-stu-id="0fbe4-107">Use the following example to get ConversstionalMOS, SendingMOS and ListendingMOS per capture device.</span></span>
  
```SQL
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
```
