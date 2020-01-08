---
title: Distribuzione del carico di conferenza di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd78b6dcedc66f5a2235b45066be7faf70d4379b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a><span data-ttu-id="7a06d-102">Distribuzione del carico di conferenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="7a06d-102">Conferencing load distribution in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="7a06d-103">_**Argomento Ultima modifica:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="7a06d-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="7a06d-104">A differenza di altre soluzioni di conferenza dedicate, l'architettura Lync Server è un modello di hardware condiviso.</span><span class="sxs-lookup"><span data-stu-id="7a06d-104">Unlike some other dedicated conferencing solutions, Lync Server architecture is a shared-hardware model.</span></span> <span data-ttu-id="7a06d-105">Questo significa che lo stesso hardware è condiviso da molti componenti software, ognuno dei quali supporta diverse comunicazioni in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="7a06d-105">This means that the same hardware is shared by many software components, each of which supports different real-time communications.</span></span> <span data-ttu-id="7a06d-106">Ogni tipo di comunicazioni in tempo reale colloca carichi specifici nei server.</span><span class="sxs-lookup"><span data-stu-id="7a06d-106">Each type of real-time communications places specific loads on the servers.</span></span> <span data-ttu-id="7a06d-107">Ad esempio, il server front-end può eseguire i componenti di routing SIP (Session Initiation Protocol), le applicazioni Web (ad esempio la ricerca di Rubrica), il servizio Web Conferencing, il servizio di conferenza A/V, le applicazioni VoIP aziendali (ad esempio, l'applicazione per i servizi di conferenza e l'applicazione di Response Group) e Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="7a06d-107">For example, the Front End Server can run the Session Initiation Protocol (SIP) routing components, web applications (such as Address Book search), Web Conferencing service, A/V Conferencing service, Enterprise Voice applications (for example, Conferencing Attendant application and Response Group application), and Mediation Server.</span></span> <span data-ttu-id="7a06d-108">Un set di database nel server front-end offre anche l'archiviazione e l'elaborazione di dati per utenti, contatti, presenza, conferenze e routing vocale.</span><span class="sxs-lookup"><span data-stu-id="7a06d-108">A set of databases on the Front End Server also provide storage and processing for user, contact, presence, conferencing, and voice routing data.</span></span> <span data-ttu-id="7a06d-109">Con questa condivisione hardware, i componenti, i servizi e i processi competono per le risorse della CPU e della memoria, quindi i carichi di lavoro non Conferencing hanno un impatto diretto sulla scalabilità del server.</span><span class="sxs-lookup"><span data-stu-id="7a06d-109">With this hardware sharing, components, services, and processes compete for CPU and memory resources, so non-conferencing workloads have a direct impact on server scaling.</span></span>

<span data-ttu-id="7a06d-110">Rispetto ad altre soluzioni di conferenza basate su porta hardware, Lync Server Conferencing Architecture è un modello senza prenotazione.</span><span class="sxs-lookup"><span data-stu-id="7a06d-110">Compared to other hardware port-based conferencing solutions, Lync Server conferencing architecture is a no-reservation model.</span></span> <span data-ttu-id="7a06d-111">Quando un utente pianifica una riunione, Lync Server crea un record nel database dei servizi di conferenza, che archivia i dati di conferenza, ma non riserva le risorse hardware per la riunione pianificata prima del tempo.</span><span class="sxs-lookup"><span data-stu-id="7a06d-111">When a user schedules a meeting, Lync Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="7a06d-112">Lync Server include invece la logica di bilanciamento del carico incorporata per allocare dinamicamente le risorse di conferenza nei server front-end in modo da distribuire equamente i carichi in tutti i server front-end del pool.</span><span class="sxs-lookup"><span data-stu-id="7a06d-112">Instead, Lync Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="7a06d-113">In questo modo vengono effettivamente riportate e usate risorse hardware, ma è difficile supportare riunioni di grandi dimensioni (soprattutto senza una pianificazione appropriata).</span><span class="sxs-lookup"><span data-stu-id="7a06d-113">This effectively provisions and utilizes hardware resources, but makes it challenging to support very large meetings (especially without appropriate planning).</span></span> <span data-ttu-id="7a06d-114">Ad esempio, quando un pool di Lync Server 2013 è in grado di essere eseguito in prossimità della capacità superiore, ogni server front-end può ospitare circa 125 riunioni di dimensione media.</span><span class="sxs-lookup"><span data-stu-id="7a06d-114">For example, when a Lync Server 2013 pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="7a06d-115">L'aggiunta di un'altra piccola riunione non è un problema, ma l'aggiunta di una riunione per gli utenti di 1000 sarebbe un problema, perché i server front-end probabilmente non sarebbero in grado di supportare una riunione di grandi dimensioni contemporaneamente alle altre riunioni di 125.</span><span class="sxs-lookup"><span data-stu-id="7a06d-115">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

