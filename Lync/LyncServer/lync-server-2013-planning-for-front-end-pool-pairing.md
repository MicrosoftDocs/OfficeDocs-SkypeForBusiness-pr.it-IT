---
title: "Lync Server 2013: pianificazione dell'abbinamento dei pool Front End"
description: "Lync Server 2013: pianificazione dell'abbinamento dei pool Front end."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Front End pool pairing
ms:assetid: cca5773d-57ff-45ce-a7b4-f82ae697c477
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205293(v=OCS.15)
ms:contentKeyID: 48185508
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac235cf682e286132836e13b34b457adf2bfc233
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562792"
---
# <a name="planning-for-front-end-pool-pairing-in-lync-server-2013"></a><span data-ttu-id="ae013-103">Pianificazione dell'abbinamento dei pool Front end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae013-103">Planning for Front End pool pairing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ae013-104">_**Ultimo argomento modificato:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="ae013-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="ae013-105">Per le migliori funzionalità di ripristino di emergenza in Lync Server 2013, distribuire coppie di pool Front end tra due siti dislocati in aree geografiche diverse.</span><span class="sxs-lookup"><span data-stu-id="ae013-105">For the best disaster recovery abilities in Lync Server 2013, deploy pairs of Front End pools across two geographically dispersed sites.</span></span> <span data-ttu-id="ae013-106">Ogni sito contiene un pool Front end che è associato a un pool Front End corrispondente nell'altro sito.</span><span class="sxs-lookup"><span data-stu-id="ae013-106">Each site contains a Front End pool which is paired with a corresponding Front End pool in the other site.</span></span> <span data-ttu-id="ae013-107">Entrambi i siti sono attivi e il servizio di backup di Lync Server fornisce la replica dei dati in tempo reale per mantenere sincronizzati i pool.</span><span class="sxs-lookup"><span data-stu-id="ae013-107">Both sites are active, and the Lync Server Backup Service provides real-time data replication to keep the pools synchronized.</span></span> <span data-ttu-id="ae013-108">Il servizio di backup è una nuova funzionalità di Lync Server 2013, progettata per supportare la soluzione di ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="ae013-108">The Backup Service is a new feature in Lync Server 2013, designed to support the disaster recovery solution.</span></span> <span data-ttu-id="ae013-109">L'installazione viene eseguita in un pool Front end quando si associa il pool a un altro pool Front end.</span><span class="sxs-lookup"><span data-stu-id="ae013-109">It is installed on a Front End pool when you pair the pool with another Front End pool.</span></span>

<span data-ttu-id="ae013-110">Se il pool in un sito ha esito negativo, è possibile eseguire il failover degli utenti da tale pool al pool nell'altro sito, che fornisce quindi Servizi a tutti gli utenti in entrambi i pool.</span><span class="sxs-lookup"><span data-stu-id="ae013-110">If the pool in one site fails, you can fail over the users from that pool to the pool in the other site, which then provides services to all the users in both pools.</span></span> <span data-ttu-id="ae013-111">A scopo di pianificazione della capacità, ogni pool deve essere progettato per gestire i carichi di lavoro di tutti gli utenti in entrambi i pool in caso di emergenza.</span><span class="sxs-lookup"><span data-stu-id="ae013-111">For capacity planning purposes, each pool should be designed to handle the workloads of all users in both pools in the event of a disaster.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ae013-112">Argomenti della sezione</span><span class="sxs-lookup"><span data-stu-id="ae013-112">In This Section</span></span>

  - [<span data-ttu-id="ae013-113">Opzioni di abbinamento del pool supportate e procedure consigliate per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae013-113">Supported pool pairing options and best practices for Lync Server 2013</span></span>](lync-server-2013-supported-pool-pairing-options-and-best-practices.md)

  - [<span data-ttu-id="ae013-114">Relazioni di registrazione di backup in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae013-114">Backup Registrar relationships in Lync Server 2013</span></span>](lync-server-2013-backup-registrar-relationships.md)

  - [<span data-ttu-id="ae013-115">Tempo di ripristino per il failover del pool e il failback del pool in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae013-115">Recovery time for pool failover and pool failback in Lync Server 2013</span></span>](lync-server-2013-recovery-time-for-pool-failover-and-pool-failback.md)

  - [<span data-ttu-id="ae013-116">Failover dell'archivio di gestione centrale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae013-116">Central Management store failover in Lync Server 2013</span></span>](lync-server-2013-central-management-store-failover.md)

  - [<span data-ttu-id="ae013-117">Sicurezza dei dati per l'abbinamento del pool Front end in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ae013-117">Front End pool pairing data security in Lync Server 2013</span></span>](lync-server-2013-front-end-pool-pairing-data-security.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

