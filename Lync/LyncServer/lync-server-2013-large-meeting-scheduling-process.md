---
title: 'Lync Server 2013: processo di pianificazione delle riunioni di grandi dimensioni'
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
ms.openlocfilehash: b83d5225982817342e6d2361099efb1ce1dcc80a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="large-meeting-scheduling-process-in-lync-server-2013"></a><span data-ttu-id="44db6-102">Processo di pianificazione delle riunioni di grandi dimensioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="44db6-102">Large-meeting scheduling process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="44db6-103">_**Ultimo argomento modificato:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="44db6-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="44db6-104">Dato che nel pool dedicato per le riunioni di grandi dimensioni è supportata una sola riunione di grandi dimensioni alla volta, è consigliabile implementare un processo per la pianificazione di questo tipo di riunioni in modo da evitare conflitti.</span><span class="sxs-lookup"><span data-stu-id="44db6-104">Because only one large meeting at a time is supported on the dedicated large meeting pool, we recommend implementing a large meeting scheduling process to help prevent large meeting conflicts.</span></span> <span data-ttu-id="44db6-105">Lo scopo di tale processo di pianificazione è agevolare la configurazione delle riunioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="44db6-105">The purpose of such the scheduling process is to facilitate setting up large meetings.</span></span> <span data-ttu-id="44db6-106">Tale funzionalità non viene fornita direttamente dai client Lync Server o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="44db6-106">Such capability is not provided directly by Lync Server or Lync Server clients.</span></span> <span data-ttu-id="44db6-107">Un metodo per implementare un processo di questo tipo consiste nell'utilizzare il sistema di gestione dei ticket del team di supporto tecnico dell'organizzazione, se disponibile.</span><span class="sxs-lookup"><span data-stu-id="44db6-107">One way to implement such a process is to use your organization’s support team’s ticketing system, if available.</span></span>

<span data-ttu-id="44db6-108">Per gli organizzatori di riunioni di grandi dimensioni, la pianificazione include l'esecuzione dei passaggi seguenti:</span><span class="sxs-lookup"><span data-stu-id="44db6-108">For organizers of large meetings, scheduling a large meeting involves completing the following steps:</span></span>

1.  <span data-ttu-id="44db6-p102">L'organizzatore della riunione o il delegato stabilisce data e ora, durata e dimensioni di una riunione prossima, oltre all'elenco dei relatori. Se le dimensioni previste per la riunione superano i 250 utenti oppure per assicurare un'esperienza utente ottimale per una riunione con meno di 250 utenti, l'organizzatore o il delegato invia una richiesta per una riunione di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="44db6-p102">The meeting organizer or delegate determines the time, duration, and size of an upcoming meeting, in addition to the list of presenters. If the anticipated meeting size exceeds 250 users or to ensure the best user experience for a meeting of fewer than 250 users, the organizer or the delegate submits a request for a large meeting.</span></span>

2.  <span data-ttu-id="44db6-p103">Il personale addetto della pianificazione verifica se la data e l'ora richieste sono disponibili. Dato che nel pool dedicato è supportata una sola riunione di grandi dimensioni alla volta, il personale addetto alla pianificazione deve controllare il calendario di questo tipo di riunioni per stabilire se ne è già presente un'altra pianificata per la data e l'ora richieste. Se l'intervallo di tempo richiesto risulta disponibile, la richiesta di riunione viene approvata.</span><span class="sxs-lookup"><span data-stu-id="44db6-p103">The scheduling staff checks to see whether the requested date and time is available. Since we support only a single large meeting on the dedicated pool at a time, the scheduling staff needs to check the large-meeting calendar to determine whether there is another meeting scheduled for the requested date and time. If the requested time is available, the staff approves the meeting request.</span></span>

3.  <span data-ttu-id="44db6-114">Se la richiesta viene approvata, il personale di pianificazione (utilizzando le credenziali nel pool dedicato) utilizza il componente aggiuntivo per riunioni online per Lync 2013 con Outlook per impostare una riunione nel pool di riunioni di grandi dimensioni dedicato.</span><span class="sxs-lookup"><span data-stu-id="44db6-114">If the request is approved, the scheduling staff (using credentials on the dedicated pool) uses Online Meeting Add-in for Lync 2013 with Outlook to set up a meeting on the dedicated large-meeting pool.</span></span> <span data-ttu-id="44db6-115">L'URL da utilizzare per partecipare alla riunione viene fornito al richiedente nell'ambito della notifica dell'approvazione.</span><span class="sxs-lookup"><span data-stu-id="44db6-115">The URL to be used to join the meeting is provided to the requester as part of the approval notice.</span></span>

4.  <span data-ttu-id="44db6-116">L'organizzatore della riunione o il delegato utilizza Outlook per pianificare la riunione imminente, aggiungendo l'URL per la partecipazione alla riunione all'invito alla riunione.</span><span class="sxs-lookup"><span data-stu-id="44db6-116">The meeting organizer or delegate uses Outlook to schedule the upcoming meeting, adding the URL for joining the meeting to the meeting invitation.</span></span> <span data-ttu-id="44db6-117">L'organizzatore della riunione o il delegato specifica quindi gli utenti da invitare e invia l'invito alla riunione.</span><span class="sxs-lookup"><span data-stu-id="44db6-117">The meeting organizer or delegate then specifies the users to be invited and sends out the meeting invitation.</span></span>
    
    <span data-ttu-id="44db6-118">Nella figura seguente sono illustrati una richiesta e un flusso di lavoro di approvazione tipici per la pianificazione di riunioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="44db6-118">The following figure illustrates a typical request and approval workflow for scheduling large meetings.</span></span>
    
    <span data-ttu-id="44db6-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span><span class="sxs-lookup"><span data-stu-id="44db6-119">![5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d](images/JJ205334.5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d(OCS.15).jpg "5d8b1f62-1dc3-47bf-bf8f-be2d8899ab9d")</span></span>  

</div>

<span> </span>

</div>

</div>

</div>

