---
title: 'Lync Server 2013: domande frequenti sul supporto per riunioni di grandi dimensioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bcb5e8ecf3843a8997daa818ed75b33162cfb70
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42186699"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a><span data-ttu-id="e8884-102">Domande frequenti sul supporto per le riunioni di grandi dimensioni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e8884-102">Large meeting support FAQ for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e8884-103">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="e8884-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="e8884-104">Le sezioni seguenti forniscono risposte alle domande comuni sulla creazione e sull'esecuzione di riunioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="e8884-104">The following sections provide answers to common questions for creating and running large meetings.</span></span>

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a><span data-ttu-id="e8884-105">D: quanti utenti possono partecipare a una riunione di grandi dimensioni?</span><span class="sxs-lookup"><span data-stu-id="e8884-105">Q: How many users can participate in a large meeting?</span></span>

<span data-ttu-id="e8884-106">Il modello utente di Lync Server consente di specificare i limiti di 250 utenti in un pool condiviso o 1000 utenti in un pool dedicato a riunioni di grandi dimensioni, ma questi numeri rappresentano solo il numero di utenti che sono stati testati e solo per l'insieme specifico di hardware utilizzato per il testing.</span><span class="sxs-lookup"><span data-stu-id="e8884-106">The Lync Server user model specifies limits of 250 users in a shared pool or 1000 users in a pool dedicated to large meetings, but these numbers only represent the number of users we tested and only for the specific set of hardware that we used in our testing.</span></span> <span data-ttu-id="e8884-107">In base ai test, si consiglia di utilizzare i limiti per le dimensioni massime.</span><span class="sxs-lookup"><span data-stu-id="e8884-107">Based on our testing, we recommend those limits for maximum sizes.</span></span> <span data-ttu-id="e8884-108">Tuttavia, è possibile controllare il numero effettivo di partecipanti consentiti nelle riunioni dell'organizzazione configurando uno o più criteri di conferenza (che vengono configurati utilizzando i cmdlet di Windows PowerShell in Lync Server Management Shell o utilizzando Lync Server Pannello di controllo).</span><span class="sxs-lookup"><span data-stu-id="e8884-108">However, you control the actual number of participants allowed in meetings in your organization by configuring one or more conferencing policies (which you configure using Windows PowerShell cmdlets in the Lync Server Management Shell or using the Lync Server Control Panel).</span></span> <span data-ttu-id="e8884-109">Il numero specificato in un criterio di conferenza può essere un numero intero di 32 bit compreso tra 1 e 4.294.967.295, ma le dimensioni consigliate sono comprese tra 2 e 250 partecipanti, inclusi. e il valore predefinito è 250.</span><span class="sxs-lookup"><span data-stu-id="e8884-109">The number that you specify in a conferencing policy can be any 32-bit whole number between 1 and 4,294,967,295, but the recommended size is between 2 and 250 participants, inclusive; and the default value is 250.</span></span>

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a><span data-ttu-id="e8884-110">D: quante riunioni o altri carichi di lavoro si posso avere in un pool dedicato alle riunioni di grandi dimensioni?</span><span class="sxs-lookup"><span data-stu-id="e8884-110">Q: How many meetings or other workloads can I have in a pool that is dedicated to large meetings?</span></span>

<span data-ttu-id="e8884-p102">Per offrire la migliore esperienza utente nelle riunioni di grandi dimensioni che includono fino a 1000 partecipanti, è consigliabile ospitare una sola grande riunione per volta in un pool dedicato alle riunioni di grandi dimensioni. È inoltre preferibile non consentire l'esecuzione di altri carichi di lavoro sullo stesso pool durante una riunione di questo tipo.</span><span class="sxs-lookup"><span data-stu-id="e8884-p102">To ensure the best user experience in large meetings of up to 1000 participants, we recommend hosting only a single large meeting at a time on a pool that is dedicated to large meetings. We also recommend not allowing any other workloads to run on that pool when the large meeting is in progress.</span></span>

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a><span data-ttu-id="e8884-113">D: gli organizzatori di riunioni di grandi dimensioni devono essere ospitati nel pool dedicato?</span><span class="sxs-lookup"><span data-stu-id="e8884-113">Q: Should the organizers of large meeting be homed on the dedicated pool?</span></span>

<span data-ttu-id="e8884-p103">No. È consigliabile non ospitare nel pool dedicato utenti al di fuori del personale dedicato che gestisce la pianificazione di riunioni di grandi dimensioni. In questo modo si evita che ulteriore traffico di comunicazioni in tempo reale determini problemi con le riunioni di grandi dimensioni ospitate nel pool. È necessario pianificare le riunioni di grandi dimensioni nel pool dedicato utilizzando un account utente del personale preposto alla pianificazione delle riunioni di questo tipo. L'account utente dell'organizzatore della riunione (l'utente che richiede una riunione di grandi dimensioni) deve essere aggiunto come relatore della riunione.</span><span class="sxs-lookup"><span data-stu-id="e8884-p103">No. We recommend not homing any users other than the dedicated staff that manages scheduling of large meetings on the dedicated pool. This prevents other real-time communications traffic from causing problems with large meetings that are hosted in the pool. You should schedule large meetings on the dedicated pool using a user account of the large meeting scheduling staff. You should add the user account of the meeting organizer (the user who requests a large meeting) as a presenter for the large meeting.</span></span>

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a><span data-ttu-id="e8884-119">D: quali supporti multimediali posso usare in una riunione di grandi dimensioni?</span><span class="sxs-lookup"><span data-stu-id="e8884-119">Q: What media modalities can I use in a large meeting?</span></span>

<span data-ttu-id="e8884-120">Le riunioni di grandi dimensioni con un massimo di 1000 utenti possono includere audio, video, condivisione PowerPoint, lavagne e sondaggio delle presenze.</span><span class="sxs-lookup"><span data-stu-id="e8884-120">Large meetings with up to 1000 users can include audio, video, PowerPoint sharing, whiteboards, and presence polling.</span></span>

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a><span data-ttu-id="e8884-121">D: posso usare la messaggistica istantanea di gruppo nelle riunioni di grandi dimensioni?</span><span class="sxs-lookup"><span data-stu-id="e8884-121">Q: Can I use group instant messaging (IM) in large meetings?</span></span>

<span data-ttu-id="e8884-122">Sì.</span><span class="sxs-lookup"><span data-stu-id="e8884-122">Yes.</span></span> <span data-ttu-id="e8884-123">Tuttavia, un numero elevato di messaggi istantanei, specialmente se inviati da numerosi partecipanti alla riunione, può influire sull'esperienza dell'utente a causa di problemi di scorrimento rapido del testo nella finestra di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="e8884-123">However, large numbers of instant messages, especially when sent by a large number of meeting participants, can affect the user experience due to problems with fast text scrolling in the IM window.</span></span> <span data-ttu-id="e8884-124">La distribuzione di una grande quantità di messaggi istantanei fino a 1000 utenti può anche introdurre carichi significativi del server, che possono influire sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="e8884-124">Delivering a large amount of instant messages to up to 1000 users can also introduce significant server loads, which can affect performance.</span></span> <span data-ttu-id="e8884-125">In generale, la messaggistica istantanea è necessaria solo per domande e\&risposte (Q As).</span><span class="sxs-lookup"><span data-stu-id="e8884-125">Generally, IM is only required for questions and answers (Q\&As).</span></span>

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a><span data-ttu-id="e8884-126">Gli utenti possono partecipare alle riunioni di grandi dimensioni componendo un numero da un telefono?</span><span class="sxs-lookup"><span data-stu-id="e8884-126">Can users join large meetings by dialing in from a phone?</span></span>

<span data-ttu-id="e8884-127">Sì.</span><span class="sxs-lookup"><span data-stu-id="e8884-127">Yes.</span></span> <span data-ttu-id="e8884-128">Se il pool di Lync Server 2013 è stato distribuito correttamente e abilitato per le conferenze telefoniche con accesso esterno, gli utenti saranno in grado di partecipare alle riunioni di grandi dimensioni componendo l'accesso.</span><span class="sxs-lookup"><span data-stu-id="e8884-128">If the Lync Server 2013 pool is properly deployed and enabled for dial-in conferencing, users will be able to join the large meetings by dialing in.</span></span> <span data-ttu-id="e8884-129">Il test ha rilevato che fino al 15% dei 1000 utenti può partecipare alla riunione per un periodo superiore ai 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="e8884-129">Our testing has shown that up to 15% of the 1000 users can join the large meeting over a 10 minute period.</span></span>

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a><span data-ttu-id="e8884-130">D: posso ospitare riunioni di grandi dimensioni in una topologia virtuale?</span><span class="sxs-lookup"><span data-stu-id="e8884-130">Q: Can I host large meetings in a virtual topology?</span></span>

<span data-ttu-id="e8884-131">Non sono stati eseguiti test sulle riunioni di grandi dimensioni in una topologia virtuale, pertanto non l'uso delle macchine virtuali per ospitare un pool dedicato per le riunioni di grandi dimensioni non è supportato.</span><span class="sxs-lookup"><span data-stu-id="e8884-131">We have not tested large meetings in a virtual topology, so we do not support the use of virtual machines to host a dedicated pool for large meetings.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

