---
title: Modello utente per le conferenze di Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1049ff2d11d76e78661636972c812cc6c9c731f3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42199038"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a><span data-ttu-id="32839-102">Il modello utente per le conferenze in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="32839-102">The conferencing user model in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="32839-103">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="32839-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="32839-104">Una parte critica del modello utente di Lync Server Conferencing è la dimensione della riunione.</span><span class="sxs-lookup"><span data-stu-id="32839-104">A critical part of the Lync Server conferencing user model is meeting size.</span></span> <span data-ttu-id="32839-105">Dopo avere raccolto i dati dai diversi punti dati, come illustrato nella sezione precedente, è stato possibile determinare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="32839-105">After collecting data from the multiple data points (as described in the previous section), we determined the following:</span></span>

  - <span data-ttu-id="32839-106">Nella maggior parte dei casi le riunioni sono riunioni di piccole dimensioni per la collaborazione con una media di 4-6 partecipanti.</span><span class="sxs-lookup"><span data-stu-id="32839-106">Most meetings are actually small collaborative meetings with an average of four to six participants</span></span>

  - <span data-ttu-id="32839-107">All'incirca l'80% delle riunioni ha meno di 20 partecipanti.</span><span class="sxs-lookup"><span data-stu-id="32839-107">Approximately 80 percent of meetings have fewer than 20 participants.</span></span>

  - <span data-ttu-id="32839-108">Il 99,98% delle riunioni ha meno di 100.</span><span class="sxs-lookup"><span data-stu-id="32839-108">99.98 percent of meetings have fewer than 100 participants.</span></span>

<span data-ttu-id="32839-109">Oltre alle dimensioni delle riunioni, nel modello utente per le conferenze vengono inoltre considerati diversi fattori, tra cui i seguenti:</span><span class="sxs-lookup"><span data-stu-id="32839-109">In addition to meeting size, the conferencing user model also takes into account a variety of factors, such as:</span></span>

  - <span data-ttu-id="32839-110">**Riunioni simultanee**   quanti utenti si prevede che siano presenti contemporaneamente nelle riunioni?</span><span class="sxs-lookup"><span data-stu-id="32839-110">**Concurrent meetings**   How many users are expected to be in meetings at the same time?</span></span>

  - <span data-ttu-id="32839-111">**Mix multimediale quali**   tipi di supporti sono disponibili e dovrebbero essere utilizzati dagli utenti nelle riunioni?</span><span class="sxs-lookup"><span data-stu-id="32839-111">**Media mix**   What types of media are available and expected to be used by users in meetings?</span></span>

  - <span data-ttu-id="32839-112">**I tipi**   di utenti sono utenti interni, utenti remoti, utenti federati o utenti anonimi?</span><span class="sxs-lookup"><span data-stu-id="32839-112">**User types**   Are users internal users, remote users, federated users, or anonymous users?</span></span>

  - <span data-ttu-id="32839-113">**Rampa di ritrovo**   per quanto tempo è necessario per tutti gli utenti di una riunione per partecipare a una riunione?</span><span class="sxs-lookup"><span data-stu-id="32839-113">**Meeting ramp up time**   How long does it take for all users of a meeting to join a meeting?</span></span>

<span data-ttu-id="32839-114">Per informazioni dettagliate sul modello utente, vedere [User Models in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="32839-114">For details about the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="32839-115">Per determinare il numero di riunioni e utenti da utilizzare per il testing, sono state eseguite le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="32839-115">To determine the number of meetings and users to use for testing, we did the following:</span></span>

  - <span data-ttu-id="32839-116">Il numero totale degli utenti di un'organizzazione (ad esempio, 80.000 utenti) è stato moltiplicato per la percentuale di riunioni simultanee (ad esempio, il 5% di tutti gli utenti) per determinare il numero totale di utenti che si prevede partecipino a riunioni nello stesso momento (in questo caso, 4.000 utenti).</span><span class="sxs-lookup"><span data-stu-id="32839-116">Took the total number of users in an organization (for example, 80,000 users) and multiplied it by the meeting concurrency rate (for example, 5% of all users) to determine the total number of users expected to be in meetings at the same time (in this example, 4000 users).</span></span>

  - <span data-ttu-id="32839-117">Suddiviso il numero totale di utenti in base al numero di Lync Server 2013, Front End Server nella distribuzione (ad esempio, 8 Server) per determinare il numero stimato di partecipanti alla riunione per Front End Server (in questo esempio, 500 utenti per Front End Server).</span><span class="sxs-lookup"><span data-stu-id="32839-117">Divided the total number of users by the number of Lync Server 2013, Front End Servers in the deployment (for example, 8 servers) to determine the estimated number of meeting participants per Front End Server (in this example, 500 users per Front End Server).</span></span>

  - <span data-ttu-id="32839-118">Il numero di utenti per Front End Server è stato diviso per la dimensione media delle riunioni (ad esempio, 4 utenti) per determinare il numero medio stimato di riunioni per Front End Server (in questo esempio, 125 riunioni per Front End Server).</span><span class="sxs-lookup"><span data-stu-id="32839-118">Divided the number of users per Front End Server by the average meeting size (for example, 4 users) to determine the estimated average number of meetings per Front End Server (in this example, 125 meetings per Front End Server).</span></span>

  - <span data-ttu-id="32839-119">Per ottenere il carico per ogni supporto su ogni Front End Server, è stato valutato il media mix.</span><span class="sxs-lookup"><span data-stu-id="32839-119">To get the per media load on each Front End Server, we estimated the media mix.</span></span> <span data-ttu-id="32839-120">Ad esempio, presupponendo che il 75% delle riunioni richieda più di un semplice supporto audio e che il 50% di tali riunioni richieda la condivisione delle applicazioni, una media di 47 riunioni e 188 utenti si connettono contemporaneamente a ogni Front End Server per la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="32839-120">For example, assuming that 75% of the meetings require more than just audio support and 50% of those meetings require application sharing, an average of 47 meetings and 188 users connect concurrently to each Front End Server for application sharing.</span></span>

  - <span data-ttu-id="32839-121">I test sono stati eseguiti su riunioni di diverse dimensioni (in base al modello utente di un massimo di 250 utenti in un pool condiviso) per assicurare la scalabilità dei server.</span><span class="sxs-lookup"><span data-stu-id="32839-121">Tested a variety of meeting sizes (based our user model of up to 250 users in a shared pool) to ensure server scalability.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

