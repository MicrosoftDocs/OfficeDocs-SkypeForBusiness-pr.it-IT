---
title: Modello di conferenza utente di Lync Server 2013
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
ms.openlocfilehash: 4f517e6d3ea3a832c4331377fa49ef7e474377de
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756380"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="the-conferencing-user-model-in-lync-server-2013"></a><span data-ttu-id="1ff51-102">Modello di conferenza utente in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1ff51-102">The conferencing user model in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1ff51-103">_**Argomento Ultima modifica:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="1ff51-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="1ff51-104">Una parte fondamentale del modello di conferenza utente di Lync Server è la dimensione della riunione.</span><span class="sxs-lookup"><span data-stu-id="1ff51-104">A critical part of the Lync Server conferencing user model is meeting size.</span></span> <span data-ttu-id="1ff51-105">Dopo aver raccolto i dati dai più punti dati, come descritto nella sezione precedente, sono stati determinati i seguenti elementi:</span><span class="sxs-lookup"><span data-stu-id="1ff51-105">After collecting data from the multiple data points (as described in the previous section), we determined the following:</span></span>

  - <span data-ttu-id="1ff51-106">La maggior parte delle riunioni è in realtà una piccola riunione di collaborazione con una media di quattro o sei partecipanti</span><span class="sxs-lookup"><span data-stu-id="1ff51-106">Most meetings are actually small collaborative meetings with an average of four to six participants</span></span>

  - <span data-ttu-id="1ff51-107">Circa il 80% delle riunioni ha meno di 20 partecipanti.</span><span class="sxs-lookup"><span data-stu-id="1ff51-107">Approximately 80 percent of meetings have fewer than 20 participants.</span></span>

  - <span data-ttu-id="1ff51-108">99,98% delle riunioni hanno meno di 100 partecipanti.</span><span class="sxs-lookup"><span data-stu-id="1ff51-108">99.98 percent of meetings have fewer than 100 participants.</span></span>

<span data-ttu-id="1ff51-109">Oltre alle dimensioni della riunione, il modello per gli utenti dei servizi di conferenza tiene conto anche di diversi fattori, ad esempio:</span><span class="sxs-lookup"><span data-stu-id="1ff51-109">In addition to meeting size, the conferencing user model also takes into account a variety of factors, such as:</span></span>

  - <span data-ttu-id="1ff51-110">**Riunioni simultanee**   quante volte si prevede che gli utenti si trovino in riunioni contemporaneamente?</span><span class="sxs-lookup"><span data-stu-id="1ff51-110">**Concurrent meetings**   How many users are expected to be in meetings at the same time?</span></span>

  - <span data-ttu-id="1ff51-111">**Media mix**   quali tipi di elementi multimediali sono disponibili e che dovrebbero essere usati dagli utenti nelle riunioni?</span><span class="sxs-lookup"><span data-stu-id="1ff51-111">**Media mix**   What types of media are available and expected to be used by users in meetings?</span></span>

  - <span data-ttu-id="1ff51-112">**I tipi**   utente sono utenti interni, utenti remoti, utenti federati o utenti anonimi?</span><span class="sxs-lookup"><span data-stu-id="1ff51-112">**User types**   Are users internal users, remote users, federated users, or anonymous users?</span></span>

  - <span data-ttu-id="1ff51-113">**Rampa di riunione**   per quanto tempo è necessario per tutti gli utenti di una riunione partecipare a una riunione?</span><span class="sxs-lookup"><span data-stu-id="1ff51-113">**Meeting ramp up time**   How long does it take for all users of a meeting to join a meeting?</span></span>

<span data-ttu-id="1ff51-114">Per informazioni dettagliate sul modello utente, vedere [modelli utente in Lync Server 2013](lync-server-2013-user-models.md).</span><span class="sxs-lookup"><span data-stu-id="1ff51-114">For details about the user model, see [User models in Lync Server 2013](lync-server-2013-user-models.md).</span></span>

<span data-ttu-id="1ff51-115">Per determinare il numero di riunioni e utenti da usare per il test, abbiamo eseguito le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1ff51-115">To determine the number of meetings and users to use for testing, we did the following:</span></span>

  - <span data-ttu-id="1ff51-116">Il numero totale di utenti di un'organizzazione, ad esempio gli utenti di 80.000, lo ha moltiplicato per la percentuale di concorrenza della riunione (ad esempio, 5% di tutti gli utenti) per determinare il numero totale di utenti che dovrebbero essere presenti in riunioni contemporaneamente (in questo esempio , 4000 utenti).</span><span class="sxs-lookup"><span data-stu-id="1ff51-116">Took the total number of users in an organization (for example, 80,000 users) and multiplied it by the meeting concurrency rate (for example, 5% of all users) to determine the total number of users expected to be in meetings at the same time (in this example, 4000 users).</span></span>

  - <span data-ttu-id="1ff51-117">Diviso il numero totale di utenti in base al numero di Lync Server 2013, server front-end nella distribuzione (ad esempio, 8 Server) per determinare il numero stimato di partecipanti alla riunione per server front-end (in questo esempio, 500 utenti per server front-end).</span><span class="sxs-lookup"><span data-stu-id="1ff51-117">Divided the total number of users by the number of Lync Server 2013, Front End Servers in the deployment (for example, 8 servers) to determine the estimated number of meeting participants per Front End Server (in this example, 500 users per Front End Server).</span></span>

  - <span data-ttu-id="1ff51-118">Diviso il numero di utenti per server front-end per la dimensione media della riunione (ad esempio 4 utenti) per determinare il numero medio stimato di riunioni per server front-end (in questo esempio, le riunioni di 125 per server front-end).</span><span class="sxs-lookup"><span data-stu-id="1ff51-118">Divided the number of users per Front End Server by the average meeting size (for example, 4 users) to determine the estimated average number of meetings per Front End Server (in this example, 125 meetings per Front End Server).</span></span>

  - <span data-ttu-id="1ff51-119">Per ottenere il caricamento per mezzo di ogni server front-end, abbiamo valutato la combinazione di elementi multimediali.</span><span class="sxs-lookup"><span data-stu-id="1ff51-119">To get the per media load on each Front End Server, we estimated the media mix.</span></span> <span data-ttu-id="1ff51-120">Ad esempio, supponendo che il 75% delle riunioni richieda più di un semplice supporto audio e che il 50% di queste riunioni richieda la condivisione delle applicazioni, una media di 47 riunioni e 188 utenti si connettono simultaneamente a ogni server front-end per la condivisione delle applicazioni.</span><span class="sxs-lookup"><span data-stu-id="1ff51-120">For example, assuming that 75% of the meetings require more than just audio support and 50% of those meetings require application sharing, an average of 47 meetings and 188 users connect concurrently to each Front End Server for application sharing.</span></span>

  - <span data-ttu-id="1ff51-121">È stata testata una varietà di dimensioni delle riunioni (in base al modello utente di un massimo di 250 utenti in un pool condiviso) per garantire la scalabilità del server.</span><span class="sxs-lookup"><span data-stu-id="1ff51-121">Tested a variety of meeting sizes (based our user model of up to 250 users in a shared pool) to ensure server scalability.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

