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
ms.openlocfilehash: 6f5a8d63fddf3b8633ebf31651d501458eaf4893
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762174"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a><span data-ttu-id="c6b93-102">Domande frequenti sul supporto per riunioni di grandi dimensioni per Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c6b93-102">Large meeting support FAQ for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c6b93-103">_**Argomento Ultima modifica:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="c6b93-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="c6b93-104">Nelle sezioni seguenti vengono fornite le risposte alle domande comuni per la creazione e l'uso di riunioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="c6b93-104">The following sections provide answers to common questions for creating and running large meetings.</span></span>

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a><span data-ttu-id="c6b93-105">D: quante utenti possono partecipare a una riunione di grandi dimensioni?</span><span class="sxs-lookup"><span data-stu-id="c6b93-105">Q: How many users can participate in a large meeting?</span></span>

<span data-ttu-id="c6b93-106">Il modello utente di Lync Server specifica i limiti degli utenti di 250 in un pool condiviso o 1000 utenti in un pool dedicato alle riunioni di grandi dimensioni, ma questi numeri rappresentano solo il numero di utenti che abbiamo testato e solo per il set specifico di hardware usato nei test.</span><span class="sxs-lookup"><span data-stu-id="c6b93-106">The Lync Server user model specifies limits of 250 users in a shared pool or 1000 users in a pool dedicated to large meetings, but these numbers only represent the number of users we tested and only for the specific set of hardware that we used in our testing.</span></span> <span data-ttu-id="c6b93-107">In base al test, consigliamo i limiti per le dimensioni massime.</span><span class="sxs-lookup"><span data-stu-id="c6b93-107">Based on our testing, we recommend those limits for maximum sizes.</span></span> <span data-ttu-id="c6b93-108">Tuttavia, è possibile controllare il numero effettivo di partecipanti consentiti nelle riunioni dell'organizzazione configurando uno o più criteri di conferenza (che vengono configurati con i cmdlet di Windows PowerShell in Lync Server Management Shell o tramite Lync Server Pannello di controllo).</span><span class="sxs-lookup"><span data-stu-id="c6b93-108">However, you control the actual number of participants allowed in meetings in your organization by configuring one or more conferencing policies (which you configure using Windows PowerShell cmdlets in the Lync Server Management Shell or using the Lync Server Control Panel).</span></span> <span data-ttu-id="c6b93-109">Il numero specificato in un criterio di conferenza può essere qualsiasi numero intero di 32 bit compreso tra 1 e 4.294.967.295, ma le dimensioni consigliate sono comprese tra 2 e 250 partecipanti, inclusi; e il valore predefinito è 250.</span><span class="sxs-lookup"><span data-stu-id="c6b93-109">The number that you specify in a conferencing policy can be any 32-bit whole number between 1 and 4,294,967,295, but the recommended size is between 2 and 250 participants, inclusive; and the default value is 250.</span></span>

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a><span data-ttu-id="c6b93-110">D: quante riunioni o altri carichi di lavoro è possibile avere in un pool dedicato alle riunioni di grandi dimensioni?</span><span class="sxs-lookup"><span data-stu-id="c6b93-110">Q: How many meetings or other workloads can I have in a pool that is dedicated to large meetings?</span></span>

<span data-ttu-id="c6b93-111">Per garantire la migliore esperienza utente in riunioni di grandi dimensioni fino a 1000 partecipanti, è consigliabile ospitare solo una riunione di grandi dimensioni alla volta in un pool dedicato alle riunioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="c6b93-111">To ensure the best user experience in large meetings of up to 1000 participants, we recommend hosting only a single large meeting at a time on a pool that is dedicated to large meetings.</span></span> <span data-ttu-id="c6b93-112">Si consiglia inoltre di non consentire l'esecuzione di altri carichi di lavoro su tale pool quando è in corso una riunione di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="c6b93-112">We also recommend not allowing any other workloads to run on that pool when the large meeting is in progress.</span></span>

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a><span data-ttu-id="c6b93-113">D: gli organizzatori di una riunione di grandi dimensioni devono essere ospitati nel pool dedicato?</span><span class="sxs-lookup"><span data-stu-id="c6b93-113">Q: Should the organizers of large meeting be homed on the dedicated pool?</span></span>

<span data-ttu-id="c6b93-114">Non.</span><span class="sxs-lookup"><span data-stu-id="c6b93-114">No.</span></span> <span data-ttu-id="c6b93-115">Ti consigliamo di non dirigere gli utenti a parte il personale dedicato che gestisce la pianificazione di riunioni di grandi dimensioni nel pool dedicato.</span><span class="sxs-lookup"><span data-stu-id="c6b93-115">We recommend not homing any users other than the dedicated staff that manages scheduling of large meetings on the dedicated pool.</span></span> <span data-ttu-id="c6b93-116">In questo modo, il traffico di comunicazioni in tempo reale viene impedito causando problemi con riunioni di grandi dimensioni ospitate nel pool.</span><span class="sxs-lookup"><span data-stu-id="c6b93-116">This prevents other real-time communications traffic from causing problems with large meetings that are hosted in the pool.</span></span> <span data-ttu-id="c6b93-117">È consigliabile pianificare riunioni di grandi dimensioni nel pool dedicato usando un account utente del personale di pianificazione della riunione di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="c6b93-117">You should schedule large meetings on the dedicated pool using a user account of the large meeting scheduling staff.</span></span> <span data-ttu-id="c6b93-118">È necessario aggiungere l'account utente dell'organizzatore della riunione (l'utente che richiede una riunione di grandi dimensioni) come relatore per la riunione di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="c6b93-118">You should add the user account of the meeting organizer (the user who requests a large meeting) as a presenter for the large meeting.</span></span>

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a><span data-ttu-id="c6b93-119">D: quali modalità multimediali è possibile usare in una riunione di grandi dimensioni?</span><span class="sxs-lookup"><span data-stu-id="c6b93-119">Q: What media modalities can I use in a large meeting?</span></span>

<span data-ttu-id="c6b93-120">Le riunioni di grandi dimensioni con gli utenti fino a 1000 possono includere audio, video, condivisione di PowerPoint, lavagne e polling della presenza.</span><span class="sxs-lookup"><span data-stu-id="c6b93-120">Large meetings with up to 1000 users can include audio, video, PowerPoint sharing, whiteboards, and presence polling.</span></span>

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a><span data-ttu-id="c6b93-121">D: è possibile usare la messaggistica istantanea di gruppo in riunioni di grandi dimensioni?</span><span class="sxs-lookup"><span data-stu-id="c6b93-121">Q: Can I use group instant messaging (IM) in large meetings?</span></span>

<span data-ttu-id="c6b93-122">Sì.</span><span class="sxs-lookup"><span data-stu-id="c6b93-122">Yes.</span></span> <span data-ttu-id="c6b93-123">Tuttavia, un numero elevato di messaggi istantanei, soprattutto se inviati da numerosi partecipanti alla riunione, può influire sull'esperienza utente a causa di problemi di scorrimento rapido del testo nella finestra di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="c6b93-123">However, large numbers of instant messages, especially when sent by a large number of meeting participants, can affect the user experience due to problems with fast text scrolling in the IM window.</span></span> <span data-ttu-id="c6b93-124">La distribuzione di un numero elevato di messaggi istantanei a un massimo di 1000 utenti può anche introdurre carichi significativi del server, che possono influire sulle prestazioni.</span><span class="sxs-lookup"><span data-stu-id="c6b93-124">Delivering a large amount of instant messages to up to 1000 users can also introduce significant server loads, which can affect performance.</span></span> <span data-ttu-id="c6b93-125">In genere, la messaggistica istantanea è necessaria solo per domande e\&risposte (Q As).</span><span class="sxs-lookup"><span data-stu-id="c6b93-125">Generally, IM is only required for questions and answers (Q\&As).</span></span>

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a><span data-ttu-id="c6b93-126">Gli utenti possono partecipare a riunioni di grandi dimensioni componendo da un telefono?</span><span class="sxs-lookup"><span data-stu-id="c6b93-126">Can users join large meetings by dialing in from a phone?</span></span>

<span data-ttu-id="c6b93-127">Sì.</span><span class="sxs-lookup"><span data-stu-id="c6b93-127">Yes.</span></span> <span data-ttu-id="c6b93-128">Se il pool di Lync Server 2013 è stato distribuito correttamente e abilitato per i servizi di conferenza telefonica con accesso esterno, gli utenti potranno partecipare alle riunioni di grandi dimensioni effettuando la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c6b93-128">If the Lync Server 2013 pool is properly deployed and enabled for dial-in conferencing, users will be able to join the large meetings by dialing in.</span></span> <span data-ttu-id="c6b93-129">I nostri test hanno dimostrato che fino al 15% degli utenti di 1000 possono partecipare alla riunione di grandi dimensioni per un periodo di 10 minuti.</span><span class="sxs-lookup"><span data-stu-id="c6b93-129">Our testing has shown that up to 15% of the 1000 users can join the large meeting over a 10 minute period.</span></span>

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a><span data-ttu-id="c6b93-130">D: è possibile ospitare riunioni di grandi dimensioni in una topologia virtuale?</span><span class="sxs-lookup"><span data-stu-id="c6b93-130">Q: Can I host large meetings in a virtual topology?</span></span>

<span data-ttu-id="c6b93-131">Non sono state testate riunioni di grandi dimensioni in una topologia virtuale, quindi non è supportato l'uso di macchine virtuali per ospitare un pool dedicato per riunioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="c6b93-131">We have not tested large meetings in a virtual topology, so we do not support the use of virtual machines to host a dedicated pool for large meetings.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

