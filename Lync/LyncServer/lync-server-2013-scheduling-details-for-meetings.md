---
title: 'Lync Server 2013: pianificare i dettagli per le riunioni'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Scheduling details
ms:assetid: 39ca6fff-2c15-4347-9f1f-6c8687a39a49
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204823(v=OCS.15)
ms:contentKeyID: 48183910
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f027aac5372865bfb2803e19591dadaa1aca4805
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scheduling-details-for-meetings-in-lync-server-2013"></a><span data-ttu-id="ab19d-102">Dettagli della pianificazione per le riunioni in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ab19d-102">Scheduling details for meetings in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab19d-103">_**Argomento Ultima modifica:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="ab19d-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<span data-ttu-id="ab19d-104">Dopo aver verificato che non sia prevista nessun'altra riunione al momento richiesto, il personale di supporto per le riunioni di grandi dimensioni che gestisce la richiesta pianifica la riunione nel pool di grandi riunioni.</span><span class="sxs-lookup"><span data-stu-id="ab19d-104">After checking to ensure that no other meeting is scheduled at the requested time, the large meeting support staff that handles the request schedules the meeting on the large-meeting pool.</span></span> <span data-ttu-id="ab19d-105">Usare il componente aggiuntivo riunione online per Lync installato con il client Lync Server 2013 per eseguire questa attività, usando le credenziali di un utente abilitato per Lync Server nel pool di grandi riunioni dedicato.</span><span class="sxs-lookup"><span data-stu-id="ab19d-105">Use the Online Meeting Add-in for Lync that is installed with the Lync Server 2013 client to perform this task, using the credentials of a user enabled for Lync Server in the dedicated large-meeting pool.</span></span>

<span data-ttu-id="ab19d-106">Per garantire la migliore esperienza utente, è importante pianificare la riunione di grandi dimensioni con i livelli di accesso corretti e le impostazioni delle riunioni appropriate per le esigenze dell'organizzatore della riunione.</span><span class="sxs-lookup"><span data-stu-id="ab19d-106">To ensure the best user experience, it is important to schedule the large meeting with the right access levels and meeting settings that are appropriate to the meeting organizer’s needs.</span></span> <span data-ttu-id="ab19d-107">È consigliabile configurare le impostazioni di pianificazione seguenti nelle opzioni di riunione di Lync:</span><span class="sxs-lookup"><span data-stu-id="ab19d-107">We recommend the following scheduling settings configured in Lync Meeting options:</span></span>

  - <span data-ttu-id="ab19d-108">Usare un nuovo spazio per riunioni per ogni riunione di grandi dimensioni invece di riutilizzare lo spazio dedicato per le riunioni.</span><span class="sxs-lookup"><span data-stu-id="ab19d-108">Use a new meeting space for each large meeting instead of reusing the dedicated meeting space.</span></span>

  - <span data-ttu-id="ab19d-109">Specificare il livello di accesso alla riunione come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="ab19d-109">Specify the meeting access level as follows:</span></span>
    
      - <span data-ttu-id="ab19d-110">Se almeno un invitato è esterno all'organizzazione, imposta il tipo di accesso alla riunione a **chiunque (nessuna restrizione**.</span><span class="sxs-lookup"><span data-stu-id="ab19d-110">If at least one invitee is external to the organization, set the meeting access type to **Anyone (no restrictions**.</span></span> <span data-ttu-id="ab19d-111">In questo modo è possibile evitare di dover gestire una sala di attesa potenzialmente grande quando la riunione è in corso.</span><span class="sxs-lookup"><span data-stu-id="ab19d-111">This enables you to avoid having to manage a potentially large lobby when the meeting is in progress.</span></span>
    
      - <span data-ttu-id="ab19d-112">Se la riunione è una riunione interna, impostare il tipo di accesso alla riunione per **tutti gli utenti dell'organizzazione**.</span><span class="sxs-lookup"><span data-stu-id="ab19d-112">If the meeting is an internal-only meeting, set the meeting access type to **Anyone from my organization**.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="ab19d-113">Evitare di impostare il tipo di accesso alla riunione per le <STRONG>persone che invito dalla mia società</STRONG> perché quando si usa questa impostazione, gli organizzatori devono aggiungere tutti gli indirizzi di posta elettronica dell'utente all'elenco di invitati e non è possibile invitare un gruppo di distribuzione.</span><span class="sxs-lookup"><span data-stu-id="ab19d-113">Avoid setting the meeting access type to <STRONG>People I invite from my company</STRONG> because when you use this setting, organizers must add all user email addresses to the invitee list and you cannot invite a distribution group.</span></span><BR><span data-ttu-id="ab19d-114">Evitare di impostare il tipo di accesso alla riunione <STRONG>solo a me, l'organizzatore della riunione</STRONG> perché questa impostazione richiede che ogni partecipante alla riunione, inclusi i relatori, debba essere inserito nella sala di attesa in fase di esecuzione della riunione.</span><span class="sxs-lookup"><span data-stu-id="ab19d-114">Avoid setting the meeting access type to <STRONG>Only me, the meeting organizer</STRONG> because this setting requires that every meeting participant, including presenters, must be put in the lobby at meeting run time.</span></span> <span data-ttu-id="ab19d-115">La persona responsabile dell'uso della riunione di grandi dimensioni deve quindi monitorare costantemente il roster della sala di attesa e ammettere nuovi utenti che si trovano nell'atrio.</span><span class="sxs-lookup"><span data-stu-id="ab19d-115">The person responsible for running the large meeting must then constantly monitor the lobby roster and admit new users who are in the lobby.</span></span>

        
        </div>

  - <span data-ttu-id="ab19d-116">Consentire agli utenti che accedono tramite telefono di accedere automaticamente alla riunione controllando che i **chiamanti entrino direttamente nell'** impostazione.</span><span class="sxs-lookup"><span data-stu-id="ab19d-116">Allow users who dial-in from phones to enter the meeting automatically by checking the **Callers get in directly** setting.</span></span>

  - <span data-ttu-id="ab19d-117">Invitare esplicitamente gli utenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ab19d-117">Explicitly invite the following users:</span></span>
    
      - <span data-ttu-id="ab19d-118">Organizzatore della riunione e delegato (richiedente)</span><span class="sxs-lookup"><span data-stu-id="ab19d-118">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="ab19d-119">Elenco di relatori forniti da un richiedente di una riunione</span><span class="sxs-lookup"><span data-stu-id="ab19d-119">The list of presenters provided by a meeting requester</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ab19d-120">Se il tipo di accesso alla riunione è impostato per gli <STRONG>utenti scelti</STRONG>, è necessario aggiungere esplicitamente ogni partecipante di una riunione di grandi dimensioni come invito della riunione.</span><span class="sxs-lookup"><span data-stu-id="ab19d-120">If the meeting access type is set to <STRONG>People I choose</STRONG>, you need to explicitly add each participant of a large meeting as an invitee of the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="ab19d-121">Gestisci esplicitamente i relatori, invece di impostare l'opzione Presenter su uno dei valori di promozione automatica.</span><span class="sxs-lookup"><span data-stu-id="ab19d-121">Explicitly manage presenters, instead of setting the presenter option to one of the auto-promote values.</span></span> <span data-ttu-id="ab19d-122">Assicurarsi di aggiungere gli utenti seguenti come relatori:</span><span class="sxs-lookup"><span data-stu-id="ab19d-122">Be sure to add the following users as presenters:</span></span>
    
      - <span data-ttu-id="ab19d-123">Organizzatore della riunione e delegato (richiedente)</span><span class="sxs-lookup"><span data-stu-id="ab19d-123">Meeting organizer and delegate (requester)</span></span>
    
      - <span data-ttu-id="ab19d-124">Elenco di relatori forniti da convocazione di riunione di grandi dimensioni</span><span class="sxs-lookup"><span data-stu-id="ab19d-124">The list of presenters provided by large meeting requesters</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="ab19d-125">Con la gestione esplicita dei relatori, puoi controllare il numero di relatori, in modo da poter limitare i relatori a un numero abbastanza piccolo per consentire una riunione di grandi dimensioni efficace.</span><span class="sxs-lookup"><span data-stu-id="ab19d-125">By explicitly managing presenters, you can control the number of presenters, so that you can limit presenters to a small enough number to make it possible to have an effective large meeting.</span></span> <span data-ttu-id="ab19d-126">Se la maggior parte dei partecipanti alla riunione ha il ruolo di partecipante, consente di ridurre la probabilità che le persone prendano accidentalmente il controllo della presentazione, eliminando una presentazione di PowerPoint, riattivando o disattivando i relatori e altre interruzioni alla riunione.</span><span class="sxs-lookup"><span data-stu-id="ab19d-126">If the majority of meeting participants have the attendee role, it helps reduce the chance of people accidentally taking control of the presentation, deleting a PowerPoint presentation, muting/unmuting presenters, and other disruptions to the meeting.</span></span>

    
    </div>

  - <span data-ttu-id="ab19d-127">Selezionare l'impostazione **Disattiva tutti i partecipanti** per verificare che solo i relatori possano trasmettere l'audio alla riunione.</span><span class="sxs-lookup"><span data-stu-id="ab19d-127">Check the **Mute all attendees** setting to make sure that only presenters can broadcast audio into the meeting.</span></span>

  - <span data-ttu-id="ab19d-128">Controlla l'impostazione del **video dei partecipanti al blocco** per verificare che solo i relatori possano trasmettere video alla riunione.</span><span class="sxs-lookup"><span data-stu-id="ab19d-128">Check the **Block attendees’ video** setting to make sure only presenters can broadcast video into the meeting.</span></span>

<span data-ttu-id="ab19d-129">La figura seguente mostra le impostazioni consigliate per il componente aggiuntivo riunione online per Lync.</span><span class="sxs-lookup"><span data-stu-id="ab19d-129">The following figure shows the recommended settings for the Online Meeting Add-in for Lync.</span></span>

<span data-ttu-id="ab19d-130">![54e4e70d-06B0-45CD-8D94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06B0-45CD-8D94-bab649cd5dc0")</span><span class="sxs-lookup"><span data-stu-id="ab19d-130">![54e4e70d-06b0-45cd-8d94-bab649cd5dc0](images/JJ204823.54e4e70d-06b0-45cd-8d94-bab649cd5dc0(OCS.15).jpg "54e4e70d-06b0-45cd-8d94-bab649cd5dc0")</span></span>

</div>

<span> </span>

</div>

</div>

</div>

