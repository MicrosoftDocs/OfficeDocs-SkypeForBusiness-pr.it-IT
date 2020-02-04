---
title: 'Lync Server 2013: pianificazione per il controllo delle chiamate remote'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for remote call control
ms:assetid: 688a0328-1aa7-449f-b5f7-98c876112ed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558658(v=OCS.15)
ms:contentKeyID: 48184371
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4c07674be037c7d2fe06d6e2811dcd3264cc6db
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725226"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-remote-call-control-in-lync-server-2013"></a><span data-ttu-id="40421-102">Pianificazione del controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40421-102">Planning for remote call control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="40421-103">_**Argomento Ultima modifica:** 2012-09-05_</span><span class="sxs-lookup"><span data-stu-id="40421-103">_**Topic Last Modified:** 2012-09-05_</span></span>

<span data-ttu-id="40421-104">In Lync Server 2013 il supporto per scenari di controllo delle chiamate remote consente agli utenti di controllare i telefoni PBX (Private Branch Exchange) usando Lync 2013 nei propri computer desktop.</span><span class="sxs-lookup"><span data-stu-id="40421-104">In Lync Server 2013, support for remote call control scenarios enables users to control their private branch exchange (PBX) phones by using Lync 2013 on their desktop computers.</span></span> <span data-ttu-id="40421-105">Questa sezione descrive le caratteristiche del controllo delle chiamate remote e i requisiti per la distribuzione del controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="40421-105">This section describes remote call control features and requirements for deploying remote call control.</span></span>

<span data-ttu-id="40421-106">L'integrazione tra un PBX e Lync Server 2013 consente agli utenti abilitati per il controllo delle chiamate remote di usare l'interfaccia utente di Lync 2013 per controllare le chiamate sui telefoni PBX nei modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="40421-106">Integration between a PBX and Lync Server 2013 makes it possible for users enabled for remote call control to use the Lync 2013 user interface (UI) to control calls on their PBX phones in the following ways:</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="40421-107">In definitiva, le funzionalità del PBX che ospita un telefono PBX dell'utente determinano le funzionalità di controllo delle chiamate remote che saranno disponibili per l'utente.</span><span class="sxs-lookup"><span data-stu-id="40421-107">Ultimately, the capabilities of the PBX that hosts a user’s PBX phone determine the remote call control features that will be available to that user.</span></span>



</div>

  - <span data-ttu-id="40421-108">Effettuare una chiamata in uscita</span><span class="sxs-lookup"><span data-stu-id="40421-108">Make an outgoing call</span></span>

  - <span data-ttu-id="40421-109">Rispondere a una chiamata in arrivo</span><span class="sxs-lookup"><span data-stu-id="40421-109">Answer an incoming call</span></span>

  - <span data-ttu-id="40421-110">Rispondere a una chiamata in arrivo con un messaggio istantaneo</span><span class="sxs-lookup"><span data-stu-id="40421-110">Answer an incoming call with an instant message</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="40421-111">Quando il numero di telefono del chiamante può essere associato a un indirizzo di messaggio istantaneo nell'elenco indirizzi globale (GAL) dell'organizzazione, nell'elenco contatti di Lync del destinatario o nell'organizzazione di un partner federato.</span><span class="sxs-lookup"><span data-stu-id="40421-111">That is, when the caller’s phone number can be associated with an instant message address in your organization’s global address list (GAL), in the callee’s Lync Contacts list, or in a federated partner’s organization.</span></span>

    
    </div>

  - <span data-ttu-id="40421-112">Trasferire una chiamata</span><span class="sxs-lookup"><span data-stu-id="40421-112">Transfer a call</span></span>

  - <span data-ttu-id="40421-113">Inoltrare una chiamata in arrivo</span><span class="sxs-lookup"><span data-stu-id="40421-113">Forward an incoming call</span></span>

  - <span data-ttu-id="40421-114">Posizionare le chiamate in attesa</span><span class="sxs-lookup"><span data-stu-id="40421-114">Place calls on hold</span></span>

  - <span data-ttu-id="40421-115">Alternare più chiamate simultanee</span><span class="sxs-lookup"><span data-stu-id="40421-115">Alternate between multiple concurrent calls</span></span>

  - <span data-ttu-id="40421-116">Rispondere a una seconda chiamata mentre si è già in una chiamata (ovvero chiamata in attesa)</span><span class="sxs-lookup"><span data-stu-id="40421-116">Answer a second call while already in a call (that is, call waiting)</span></span>

  - <span data-ttu-id="40421-117">Digitare le cifre DTMF (Dual-Tone Multifrequency)</span><span class="sxs-lookup"><span data-stu-id="40421-117">Dial dual-tone multifrequency (DTMF) digits</span></span>

  - <span data-ttu-id="40421-118">Nella finestra di conversazione digitare note in Microsoft Office OneNote programma di acquisizione appunti</span><span class="sxs-lookup"><span data-stu-id="40421-118">In the Conversation window, type notes in Microsoft Office OneNote note-taking program</span></span>

<span data-ttu-id="40421-119">Inoltre, quando un utente è abilitato per il controllo delle chiamate remote, Lync 2013 fornisce all'utente le informazioni sulle chiamate seguenti:</span><span class="sxs-lookup"><span data-stu-id="40421-119">Additionally, when a user is enabled for remote call control, Lync 2013 provides the user with the following call information:</span></span>

  - <span data-ttu-id="40421-120">Identificazione di un chiamante per nome quando il numero di telefono del chiamante è presente nell'elenco dei contatti di un client di messaggistica e collaborazione di Microsoft Office Outlook e Collaboration di un utente abilitato al controllo remoto, un elenco di contatti di Lync o un GAL dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="40421-120">Identification of a caller by name when the caller’s phone number exists in the Contacts list of a remote call control-enabled user’s Microsoft Office Outlook messaging and collaboration client, Lync Contacts list, or your organization’s GAL.</span></span>

  - <span data-ttu-id="40421-121">Passate le chiamate in entrata e in uscita, salvate nella cartella Cronologia conversazioni di Outlook.</span><span class="sxs-lookup"><span data-stu-id="40421-121">Past incoming and outgoing calls, which are saved in the Conversation History folder in Outlook.</span></span>

  - <span data-ttu-id="40421-122">Notifiche di chiamata perse, che vengono inviate alla cartella posta in arrivo di Outlook dell'utente, ma vengono generate solo se Lync è in funzione quando viene ricevuta la chiamata in arrivo.</span><span class="sxs-lookup"><span data-stu-id="40421-122">Missed call notifications, which are sent to the user’s Outlook Inbox folder, but are generated only if Lync is running when the incoming call is received.</span></span>

<div>

## <a name="remote-call-control-and-enterprise-voice"></a><span data-ttu-id="40421-123">Controllo delle chiamate remote e VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="40421-123">Remote Call Control and Enterprise Voice</span></span>

<span data-ttu-id="40421-124">Anche se le funzionalità di controllo delle chiamate remote sono separate dalle caratteristiche di VoIP aziendale e gli utenti non possono essere abilitati per entrambi, Enterprise Voice offre un sottoinsieme di funzionalità disponibili anche per gli utenti abilitati per il controllo delle chiamate remote.</span><span class="sxs-lookup"><span data-stu-id="40421-124">Although remote call control features are separate from Enterprise Voice features and users cannot be enabled for both, Enterprise Voice provides a subset of features that are also available to users who are enabled for remote call control.</span></span> <span data-ttu-id="40421-125">Se Enterprise Voice viene distribuita, gli utenti abilitati per il controllo delle chiamate remote possono usare Lync per accedere alle caratteristiche di VoIP aziendale seguenti:</span><span class="sxs-lookup"><span data-stu-id="40421-125">If Enterprise Voice is deployed, users who are enabled for remote call control can use Lync to access the following Enterprise Voice features:</span></span>

  - <span data-ttu-id="40421-126">Effettuare e ricevere chiamate audio in un altro client Lync</span><span class="sxs-lookup"><span data-stu-id="40421-126">Make and receive audio calls to another Lync client</span></span>

  - <span data-ttu-id="40421-127">Partecipare alla parte audio di una conferenza creata da un utente abilitato per VoIP aziendale</span><span class="sxs-lookup"><span data-stu-id="40421-127">Join the audio portion of a conference created by a user who is enabled for Enterprise Voice</span></span>

</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="40421-128">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="40421-128">In This Section</span></span>

  - [<span data-ttu-id="40421-129">Attività di distribuzione per il controllo delle chiamate remote in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="40421-129">Deployment tasks for remote call control in Lync Server 2013</span></span>](lync-server-2013-deployment-tasks-for-remote-call-control.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

