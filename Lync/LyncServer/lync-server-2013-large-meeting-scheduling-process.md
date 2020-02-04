---
title: 'Lync Server 2013: processo di pianificazione per riunioni di grandi dimensioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Large-meeting scheduling process
ms:assetid: de267458-885f-4176-a8d7-1a218e67640e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205334(v=OCS.15)
ms:contentKeyID: 48185639
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b2cfe26b70db612249ca840c86b41fb3d60db663
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738216"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a><span data-ttu-id="fc0fd-102">Processo di pianificazione delle riunioni di grandi dimensioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="fc0fd-102">Large-meeting scheduling process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fc0fd-103">_**Argomento Ultima modifica:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="fc0fd-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="fc0fd-104">Poiché è supportata solo una riunione di grandi dimensioni alla volta nel pool di riunioni di grandi dimensioni dedicato, è consigliabile implementare un processo di pianificazione delle riunioni di grandi dimensioni per evitare conflitti di riunione di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="fc0fd-104">Because only one large meeting at a time is supported on the dedicated large meeting pool, we recommend implementing a large meeting scheduling process to help prevent large meeting conflicts.</span></span> <span data-ttu-id="fc0fd-105">Lo scopo di questo processo di pianificazione è facilitare la configurazione di riunioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="fc0fd-105">The purpose of such the scheduling process is to facilitate setting up large meetings.</span></span> <span data-ttu-id="fc0fd-106">Tale funzionalità non viene fornita direttamente da client Lync Server o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="fc0fd-106">Such capability is not provided directly by Lync Server or Lync Server clients.</span></span> <span data-ttu-id="fc0fd-107">Un modo per implementare un processo di questo tipo consiste nell'usare il sistema di ticketing del team di supporto dell'organizzazione, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="fc0fd-107">One way to implement such a process is to use your organization’s support team’s ticketing system, if available.</span></span>

<span data-ttu-id="fc0fd-108">Per gli organizzatori di riunioni di grandi dimensioni, la pianificazione di una riunione di grandi dimensioni prevede il completamento dei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="fc0fd-108">For organizers of large meetings, scheduling a large meeting involves completing the following steps:</span></span>

1.  <span data-ttu-id="fc0fd-109">L'organizzatore o il delegato della riunione determina l'ora, la durata e le dimensioni di una riunione imminente, oltre all'elenco di relatori.</span><span class="sxs-lookup"><span data-stu-id="fc0fd-109">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters.</span></span> <span data-ttu-id="fc0fd-110">Se la dimensione prevista della riunione supera gli utenti di 250 o per garantire la migliore esperienza utente per una riunione con meno di 250 utenti, l'organizzatore o il delegato invia una richiesta per una riunione di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="fc0fd-110">If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>

2.  <span data-ttu-id="fc0fd-111">Il personale di pianificazione controlla se la data e l'ora richieste sono disponibili.</span><span class="sxs-lookup"><span data-stu-id="fc0fd-111">The scheduling staff checks to see whether the requested date and time is available.</span></span> <span data-ttu-id="fc0fd-112">Poiché supportiamo solo una singola riunione di grandi dimensioni nel pool dedicato alla volta, il personale di pianificazione deve controllare il calendario della riunione di grandi dimensioni per determinare se è prevista un'altra riunione per la data e l'ora richieste.</span><span class="sxs-lookup"><span data-stu-id="fc0fd-112">Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time.</span></span> <span data-ttu-id="fc0fd-113">Se il tempo richiesto è disponibile, il personale approva la convocazione di riunione.</span><span class="sxs-lookup"><span data-stu-id="fc0fd-113">If the requested time is available, the staff approves the meeting request.</span></span>

3.  <span data-ttu-id="fc0fd-114">Se la richiesta è approvata, il personale di pianificazione (usando le credenziali nel pool dedicato) usa il componente aggiuntivo riunione online per Lync 2013 con Outlook per configurare una riunione nel pool di grandi riunioni dedicato.</span><span class="sxs-lookup"><span data-stu-id="fc0fd-114">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Lync 2013 with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="fc0fd-115">L'URL da usare per partecipare alla riunione viene fornito al richiedente come parte della notifica di approvazione.</span><span class="sxs-lookup"><span data-stu-id="fc0fd-115">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>

4.  <span data-ttu-id="fc0fd-116">L'organizzatore o il delegato della riunione usa Outlook per pianificare la riunione imminente, aggiungendo l'URL per partecipare alla riunione all'invito alla riunione.</span><span class="sxs-lookup"><span data-stu-id="fc0fd-116">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="fc0fd-117">L'organizzatore della riunione o il delegato specifica quindi agli utenti di essere invitati e invia l'invito alla riunione.</span><span class="sxs-lookup"><span data-stu-id="fc0fd-117">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
    <span data-ttu-id="fc0fd-118">La figura seguente illustra un flusso di lavoro di richiesta e approvazione tipico per la pianificazione di riunioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="fc0fd-118">The following figure illustrates a typical request and approval workflow for scheduling large meetings.</span></span>
    
    <span data-ttu-id="fc0fd-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span><span class="sxs-lookup"><span data-stu-id="fc0fd-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span></span>  

</div>

<span> </span>

</div>

</div>

</div>

