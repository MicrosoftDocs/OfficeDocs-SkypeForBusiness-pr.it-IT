---
title: Lync Server 2013 tempo di ripristino per il failover del pool e il failback del pool
description: Lync Server 2013 tempo di ripristino per il failover del pool e il failback del pool.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Recovery time for pool failover and pool failback
ms:assetid: 902c658f-8442-4d0d-b3ad-bf795ecd550d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205079(v=OCS.15)
ms:contentKeyID: 48184786
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bb09c32ac4d062358a511464dc21aa7346ee034
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559172"
---
# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a><span data-ttu-id="7f123-103">Tempo di ripristino per il failover del pool e il failback del pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7f123-103">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7f123-104">_**Ultimo argomento modificato:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="7f123-104">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="7f123-p101">Per il failover e il failback dei pool, l'obiettivo tecnico relativo al tempo di ripristino è di 30 minuti. Si tratta del tempo necessario per l'esecuzione del failover dopo che gli amministratori hanno determinano l'esistenza di un'emergenza e hanno avviato le procedure di failover. Non include il tempo necessario agli amministratori per valutare la situazione e prendere decisioni né quello impiegato dagli utenti per ripetere l'accesso dopo il completamento del failover.</span><span class="sxs-lookup"><span data-stu-id="7f123-p101">For pool failover and pool failback, the engineering target for recovery time objective (RTO) is 30 minutes. This is the time required for the failover to happen, after administrators have determined there was a disaster and initiated the failover procedures. It does not include the time for administrators to assess the situation and make a decision, nor does it include the time for users to sign in again after failover is complete.</span></span>

<span data-ttu-id="7f123-108">Per il failover e il failback del pool, l'obiettivo tecnico relativo al punto di ripristino è pari a 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="7f123-108">For pool failover and pool failback, the engineering target for recovery point objective (RPO) is 30 minutes.</span></span> <span data-ttu-id="7f123-109">Questo valore rappresenta la misura temporale dei dati che potrebbero essere persi a causa dell'emergenza, in virtù della latenza della replica del servizio di backup.</span><span class="sxs-lookup"><span data-stu-id="7f123-109">This represents the time measure of data that could be lost due to the disaster, due to replication latency of the Backup Service.</span></span> <span data-ttu-id="7f123-110">Ad esempio, se un pool scende alle 10:00 A.M. e il RPO è di 30 minuti, i dati vengono scritti nel pool tra 9:30 A.M.</span><span class="sxs-lookup"><span data-stu-id="7f123-110">For example, if a pool goes down at 10:00 A.M., and the RPO is 30 minutes, data written to the pool between 9:30 A.M.</span></span> <span data-ttu-id="7f123-111">e 10:00 potrebbe non essere stato replicato nel pool di backup e verrebbe perso.</span><span class="sxs-lookup"><span data-stu-id="7f123-111">and 10:00 A.M.might not have replicated to the backup pool, and would be lost.</span></span>

<span data-ttu-id="7f123-112">Tutti i numeri degli obiettivi relativi al tempo e al punto di ripristino riportati in questo documento presuppongono che i due data center si trovino nella medesima area geografica con trasporto ad alta velocità e bassa latenza tra i siti.</span><span class="sxs-lookup"><span data-stu-id="7f123-112">All RTO and RPO numbers in this document assume that the two data centers are located within the same world region with high-speed, low-latency transport between the two sites.</span></span> <span data-ttu-id="7f123-113">Questi numeri sono misurati per un pool con 40.000 utenti attivi contemporaneamente e 200.000 utenti abilitati per Lync rispetto a un modello utente predefinito in cui non è presente alcun backlog nella replica dei dati.</span><span class="sxs-lookup"><span data-stu-id="7f123-113">These numbers are measured for a pool with 40,000 concurrently active users and 200,000 users enabled for Lync with respect to a pre-defined user model where there is no backlog in data replication.</span></span> <span data-ttu-id="7f123-114">Le cifre sono soggette a modifiche a seconda dei test e della convalida delle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="7f123-114">They are subject to change based on performance testing and validation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

