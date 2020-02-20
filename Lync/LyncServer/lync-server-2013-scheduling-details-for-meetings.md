---
title: 'Lync Server 2013: pianificazione dei dettagli per le riunioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scheduling details
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48183910
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2fa7186ed00ea2c42db392af72555bdbbbeeaaab
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144164"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a><span data-ttu-id="2e001-102">Dettagli sulla pianificazione delle riunioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2e001-102">Scheduling details for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2e001-103">_**Ultimo argomento modificato:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="2e001-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="2e001-104">Dopo avere verificato che nel periodo di tempo richiesto non sono pianificate altre riunioni, il personale di supporto delle riunioni di grandi dimensioni che gestisce le richieste pianifica la riunione nel pool di riunioni di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="2e001-104">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> <span data-ttu-id="2e001-105">Utilizzare il componente aggiuntivo per riunioni online per Lync installato con il client Lync Server 2013 per eseguire questa attività, utilizzando le credenziali di un utente abilitato per Lync Server nel pool di riunioni di grandi dimensioni dedicato.</span><span class="sxs-lookup"><span data-stu-id="2e001-105">Use the Online Meeting Add-in for Lync that is installed with the Lync Server 2013 client to perform this task, using the credentials of a user enabled for Lync Server in the dedicated large-meeting pool.</span></span>

<span data-ttu-id="2e001-106">Per assicurare la migliore esperienza utente, è importante pianificare la riunione di grandi dimensioni con i livelli di diritto di accesso appropriati e impostazioni delle riunioni specifiche per le esigenze dell'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="2e001-106">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer’s needs.</span></span> <span data-ttu-id="2e001-107">È consigliabile configurare le seguenti impostazioni di pianificazione nelle opzioni di riunione di Lync:</span><span class="sxs-lookup"><span data-stu-id="2e001-107">We recommend the following scheduling settings configured in Lync Meeting options:</span></span>

  - <span data-ttu-id="2e001-108">Usare una nuova area riunioni per ciascuna riunione di grandi dimensioni anziché riutilizzare l'area riunione dedicata.</span><span class="sxs-lookup"><span data-stu-id="2e001-108">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span>

  - <span data-ttu-id="2e001-109">Specificare il livello di accesso alla riunione come segue:</span><span class="sxs-lookup"><span data-stu-id="2e001-109">Specify the meeting access level as follows:</span></span>
    
      - <span data-ttu-id="2e001-p103">Se almeno un invitato è esterno all'organizzazione, impostare il tipo di accesso alla riunione su **Tutti gli utenti (senza restrizioni)**. Ciò consente di evitare di dover gestire una sala d'attesa di dimensioni potenzialmente grandi quando la riunione è in corso.</span><span class="sxs-lookup"><span data-stu-id="2e001-p103">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions**. This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
      - <span data-ttu-id="2e001-112">Se la riunione prevede solo partecipanti interni, impostare il tipo di accesso su **Tutti gli utenti dell'organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="2e001-112">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="2e001-113">Evitare di impostare il tipo di accesso alla riunione su <STRONG>Persone invitate appartenenti alla società</STRONG> perché questa impostazione costringe gli organizzatori ad aggiungere all'elenco degli invitati tutti gli indirizzi di posta elettronica degli utenti e non è possibile invitare un gruppo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2e001-113">Avoid setting the meeting access type to <STRONG>People I invite from my company</STRONG> because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span><BR><span data-ttu-id="2e001-p104">Evitare di impostare il tipo di accesso alla riunione su <STRONG>Solo io, l'organizzatore della riunione</STRONG> perché questa impostazione richiede che ciascun partecipante, inclusi i relatori, stiano in sala d'attesa durante l'esecuzione della riunione. La persona responsabile della riunione di grandi dimensioni deve quindi costantemente monitorare l'elenco della sala d'attesa e ammettere i nuovi utenti che si trovano in sala d'attesa.</span><span class="sxs-lookup"><span data-stu-id="2e001-p104">Avoid setting the meeting access type to <STRONG>Only me, the meeting organizer</STRONG> because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time. The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>

        
        </div>

  - <span data-ttu-id="2e001-116">Selezionare l'opzione **Consenti ai chiamanti di entrare direttamente** per consentire agli utenti che accedono dall'esterno mediante chiamata telefonica di accedere alla riunione automaticamente.</span><span class="sxs-lookup"><span data-stu-id="2e001-116">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>

  - <span data-ttu-id="2e001-117">Invitare esplicitamente gli utenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2e001-117">Explicitly invite the following users:</span></span>
    
      - <span data-ttu-id="2e001-118">Organizzatore della riunione e delegato (richiedente)</span><span class="sxs-lookup"><span data-stu-id="2e001-118">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="2e001-119">L'elenco dei relatori fornito da un richiedente della riunione</span><span class="sxs-lookup"><span data-stu-id="2e001-119">The list of presenters provided by a meeting requester</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2e001-120">Se il tipo di accesso alla riunione è impostato su <STRONG>Persone scelte dall'utente</STRONG>, è necessario aggiungere esplicitamente come invitato ciascun partecipante di una riunione di grandi dimensioni.</span><span class="sxs-lookup"><span data-stu-id="2e001-120">If the meeting access type is set to <STRONG>People I choose</STRONG>, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="2e001-p105">Gestire esplicitamente i relatori anziché impostare l'opzione su uno dei valori di promozione automatica. Assicurarsi di aggiungere gli utenti seguenti come relatori:</span><span class="sxs-lookup"><span data-stu-id="2e001-p105">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values. Be sure to add the following users as presenters:</span></span>
    
      - <span data-ttu-id="2e001-123">Organizzatore della riunione e delegato (richiedente)</span><span class="sxs-lookup"><span data-stu-id="2e001-123">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="2e001-124">L'elenco dei relatori fornito dai richiedenti di riunioni di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="2e001-124">The list of presenters provided by large meeting requesters</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2e001-p106">Grazie alla gestione esplicita dei relatori, è possibile controllare il numero di relatori limitandolo alla quantità necessaria per rendere possibile la realizzazione di una riunione di grandi dimensioni efficace. Se la maggioranza dei partecipanti alla riunione dispone del ruolo di partecipante, si riducono le probabilità che i partecipanti assumano per errore il controllo della presentazione, eliminino una presentazione di PowerPoint, disattivino/attivino l'audio dei relatori o siano causa di altre interruzioni della riunione.</span><span class="sxs-lookup"><span data-stu-id="2e001-p106">By explicitly managing presenters, you can control the number of presenters, so that you can limit presenters to a small enough number to make it possible to have an effective large meeting. If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="2e001-127">Selezionare l'impostazione **Disattiva l'audio di tutti i partecipanti** per fare in modo che durante la riunione venga trasmesso solo l'audio dei relatori.</span><span class="sxs-lookup"><span data-stu-id="2e001-127">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>

  - <span data-ttu-id="2e001-128">Selezionare l'impostazione **Blocca video partecipanti** per fare in modo che durante la riunione venga trasmesso solo il video dei relatori.</span><span class="sxs-lookup"><span data-stu-id="2e001-128">Check the **Block attendees’ video** setting to make sure only presenters can broadcast video into the meeting.</span></span>

<span data-ttu-id="2e001-129">Nella figura seguente vengono illustrate le impostazioni consigliate per il componente aggiuntivo per riunioni online per Lync.</span><span class="sxs-lookup"><span data-stu-id="2e001-129">The following figure shows the recommended settings for the Online Meeting Add-in for Lync.</span></span>

<span data-ttu-id="2e001-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span><span class="sxs-lookup"><span data-stu-id="2e001-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

