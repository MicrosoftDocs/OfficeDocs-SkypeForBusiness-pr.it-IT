---
title: Distribuzione del carico per le conferenze di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66cfdab2f59ca29022435a1f7863e8fce79075e6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199129"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a><span data-ttu-id="b2fa0-102">Distribuzione del carico per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2fa0-102">Conferencing load distribution in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2fa0-103">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="b2fa0-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="b2fa0-104">A differenza di altre soluzioni per conferenze dedicate, Lync Server Architecture è un modello di hardware condiviso.</span><span class="sxs-lookup"><span data-stu-id="b2fa0-104">Unlike some other dedicated conferencing solutions, Lync Server architecture is a shared-hardware model.</span></span> <span data-ttu-id="b2fa0-105">Questo significa che lo stesso hardware viene condiviso da molti componenti software, ognuno dei quali supporta tipi diversi di comunicazione in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="b2fa0-105">This means that the same hardware is shared by many software components, each of which supports different real-time communications.</span></span> <span data-ttu-id="b2fa0-106">Ciascun tipo di comunicazione in tempo reale impone un carico specifico ai server.</span><span class="sxs-lookup"><span data-stu-id="b2fa0-106">Each type of real-time communications places specific loads on the servers.</span></span> <span data-ttu-id="b2fa0-107">Ad esempio, il front end server può eseguire i componenti di routing SIP (Session Initiation Protocol), le applicazioni Web (come la ricerca rubrica), il servizio Web Conferencing, il servizio A/V Conferencing, le applicazioni VoIP aziendale, ad esempio l'applicazione Operatore Conferenza e Response Group, e Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="b2fa0-107">For example, the Front End Server can run the Session Initiation Protocol (SIP) routing components, web applications (such as Address Book search), Web Conferencing service, A/V Conferencing service, Enterprise Voice applications (for example, Conferencing Attendant application and Response Group application), and Mediation Server.</span></span> <span data-ttu-id="b2fa0-108">Un set di database sul front end Server fornisce anche l'archiviazione e l'elaborazione per i dati relativi a utenti, contatti, presenza, conferenze e routing vocale.</span><span class="sxs-lookup"><span data-stu-id="b2fa0-108">A set of databases on the Front End Server also provide storage and processing for user, contact, presence, conferencing, and voice routing data.</span></span> <span data-ttu-id="b2fa0-109">Con la condivisione dell'hardware i componenti, i servizi e i processi sono in competizione per le risorse di CPU e memoria, e quindi i carichi di lavoro non correlati alle conferenze influiscono in modo diretto sulla scalabilità dei server.</span><span class="sxs-lookup"><span data-stu-id="b2fa0-109">With this hardware sharing, components, services, and processes compete for CPU and memory resources, so non-conferencing workloads have a direct impact on server scaling.</span></span>

<span data-ttu-id="b2fa0-110">Rispetto ad altre soluzioni per le conferenze basate su porta hardware, Lync Server Conferencing Architecture è un modello senza prenotazione.</span><span class="sxs-lookup"><span data-stu-id="b2fa0-110">Compared to other hardware port-based conferencing solutions, Lync Server conferencing architecture is a no-reservation model.</span></span> <span data-ttu-id="b2fa0-111">Quando un utente pianifica una riunione, Lync Server crea un record nel database delle conferenze, in cui vengono archiviati i dati per le conferenze, ma non riserva le risorse hardware per la riunione pianificata in anticipo.</span><span class="sxs-lookup"><span data-stu-id="b2fa0-111">When a user schedules a meeting, Lync Server creates a record in the conferencing database, which stores conferencing data, but does not reserve any hardware resources for the scheduled meeting ahead of time.</span></span> <span data-ttu-id="b2fa0-112">Al contrario, Lync Server dispone di una logica di bilanciamento del carico incorporata per allocare dinamicamente le risorse di conferenza nei front end server in modo da distribuire i carichi equamente in tutti i Front End Server nel pool.</span><span class="sxs-lookup"><span data-stu-id="b2fa0-112">Instead, Lync Server has built-in load balancing logic to dynamically allocate conferencing resources on Front End Servers in a way that distributes loads equally across all Front End Servers in the pool.</span></span> <span data-ttu-id="b2fa0-113">Questo sistema esegue il provisioning e usa le risorse hardware in modo efficiente, ma rende difficile supportare le riunioni di dimensioni molto grandi (soprattutto se non è stata eseguita una pianificazione accurata).</span><span class="sxs-lookup"><span data-stu-id="b2fa0-113">This effectively provisions and utilizes hardware resources, but makes it challenging to support very large meetings (especially without appropriate planning).</span></span> <span data-ttu-id="b2fa0-114">Ad esempio, quando un pool di Lync Server 2013 è in esecuzione vicino alla capacità massima, ogni Front End Server può ospitare circa 125 riunioni di medie dimensioni.</span><span class="sxs-lookup"><span data-stu-id="b2fa0-114">For example, when a Lync Server 2013 pool is running close to its top capacity, each Front End Server might host approximately 125 average-size meetings.</span></span> <span data-ttu-id="b2fa0-115">L'aggiunta di un'altra riunione di piccole dimensioni non è un problema, ma l'aggiunta di una riunione per gli utenti di 1000 potrebbe essere un problema perché i front end server probabilmente non sarebbero in grado di supportare una riunione di grandi dimensioni contemporaneamente alle altre riunioni di 125.</span><span class="sxs-lookup"><span data-stu-id="b2fa0-115">Adding another small meeting would not be a problem, but adding a meeting for 1000 users would be a problem because the Front End Servers would probably not be able to support such a large meeting at the same time as the other 125 meetings.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

