---
title: 'Lync Server 2013: Tempo di ripristino per il failover e il failback dei pool'
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
ms.openlocfilehash: 3fff6f74b5d486c05d01bcd3a911ae674b4f0708
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724452"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="recovery-time-for-pool-failover-and-pool-failback-in-lync-server-2013"></a><span data-ttu-id="6b71c-102">Tempo di ripristino per il failover e il failback dei pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="6b71c-102">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6b71c-103">_**Argomento Ultima modifica:** 2012-09-10_</span><span class="sxs-lookup"><span data-stu-id="6b71c-103">_**Topic Last Modified:** 2012-09-10_</span></span>

<span data-ttu-id="6b71c-104">Per il failover del pool e il failback del pool, la destinazione ingegneristica per l'obiettivo del tempo di recupero (RTO) è di 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="6b71c-104">For pool failover and pool failback, the engineering target for recovery time objective (RTO) is 30 minutes.</span></span> <span data-ttu-id="6b71c-105">Questo è il tempo necessario per il failover, dopo che gli amministratori hanno determinato che si è verificato un disastro e avviato le procedure di failover.</span><span class="sxs-lookup"><span data-stu-id="6b71c-105">This is the time required for the failover to happen, after administrators have determined there was a disaster and initiated the failover procedures.</span></span> <span data-ttu-id="6b71c-106">Non include il tempo per gli amministratori di valutare la situazione e prendere una decisione, né include il tempo per cui gli utenti possono accedere di nuovo dopo il completamento del failover.</span><span class="sxs-lookup"><span data-stu-id="6b71c-106">It does not include the time for administrators to assess the situation and make a decision, nor does it include the time for users to sign in again after failover is complete.</span></span>

<span data-ttu-id="6b71c-107">Per il failover del pool e il failback del pool, la destinazione ingegneristica per l'obiettivo del punto di ripristino (RPO) è di 30 minuti.</span><span class="sxs-lookup"><span data-stu-id="6b71c-107">For pool failover and pool failback, the engineering target for recovery point objective (RPO) is 30 minutes.</span></span> <span data-ttu-id="6b71c-108">Rappresenta la misura temporale dei dati che potrebbero essere persi a causa del disastro causato dalla latenza della replica del servizio di backup.</span><span class="sxs-lookup"><span data-stu-id="6b71c-108">This represents the time measure of data that could be lost due to the disaster, due to replication latency of the Backup Service.</span></span> <span data-ttu-id="6b71c-109">Ad esempio, se un pool scende alle 10:00 A.M. e RPO è di 30 minuti, i dati vengono scritti nel pool tra 9:30 A.M.</span><span class="sxs-lookup"><span data-stu-id="6b71c-109">For example, if a pool goes down at 10:00 A.M., and the RPO is 30 minutes, data written to the pool between 9:30 A.M.</span></span> <span data-ttu-id="6b71c-110">e 10:00. M. potrebbe non essere stato replicato nel pool di backup e andrebbe perduto.</span><span class="sxs-lookup"><span data-stu-id="6b71c-110">and 10:00 A.M.might not have replicated to the backup pool, and would be lost.</span></span>

<span data-ttu-id="6b71c-111">Tutti i numeri di RTO e RPO in questo documento presuppongono che i due centri dati si trovino all'interno della stessa area geografica con il trasporto ad alta velocità e a bassa latenza tra i due siti.</span><span class="sxs-lookup"><span data-stu-id="6b71c-111">All RTO and RPO numbers in this document assume that the two data centers are located within the same world region with high-speed, low-latency transport between the two sites.</span></span> <span data-ttu-id="6b71c-112">Questi numeri vengono misurati per un pool con 40.000 utenti attivi simultaneamente e 200.000 gli utenti abilitati per Lync rispetto a un modello di utente predefinito in cui non è presente alcun backlog nella replica dei dati.</span><span class="sxs-lookup"><span data-stu-id="6b71c-112">These numbers are measured for a pool with 40,000 concurrently active users and 200,000 users enabled for Lync with respect to a pre-defined user model where there is no backlog in data replication.</span></span> <span data-ttu-id="6b71c-113">Sono soggetti a modifiche in base al test delle prestazioni e alla convalida.</span><span class="sxs-lookup"><span data-stu-id="6b71c-113">They are subject to change based on performance testing and validation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

