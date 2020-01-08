---
title: 'Lync Server 2013: Funzionalità della messaggistica unificata integrata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Features of integrated Unified Messaging and Lync Server
ms:assetid: 094f549d-fccc-43ab-9f39-6ddd18130915
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398144(v=OCS.15)
ms:contentKeyID: 48183353
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b5dc6396bd78977d099e650f14ae1a0b4b46c54e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985491"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-of-integrated-unified-messaging-and-lync-server-2013"></a><span data-ttu-id="e3afc-102">Funzionalità della messaggistica unificata integrata e Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e3afc-102">Features of integrated Unified Messaging and Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e3afc-103">_**Argomento Ultima modifica:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e3afc-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e3afc-104">Lync Server 2013, Enterprise Voice usa l'infrastruttura di messaggistica UNIFICAta di Exchange per fornire le risposte alle chiamate, le notifiche delle chiamate, l'accesso vocale (inclusi i messaggi vocali) e i servizi di operatore automatico.</span><span class="sxs-lookup"><span data-stu-id="e3afc-104">Lync Server 2013, Enterprise Voice uses the Exchange Unified Messaging (UM) infrastructure to provide call answering, call notification, voice access (including voice mail), and auto-attendant services.</span></span>

<div>

## <a name="call-answering"></a><span data-ttu-id="e3afc-105">Segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="e3afc-105">Call Answering</span></span>

<span data-ttu-id="e3afc-106">La segreteria telefonica è la ricezione di messaggi vocali per conto degli utenti le cui chiamate non rispondono o sono occupate.</span><span class="sxs-lookup"><span data-stu-id="e3afc-106">Call answering is the receiving of voice messages on behalf of users whose calls are not answered or are busy.</span></span> <span data-ttu-id="e3afc-107">Include la riproduzione di un saluto personale, la registrazione di un messaggio e l'invio del messaggio in coda per il recapito alla cassetta postale dell'utente, archiviato nel server cassette postali di Exchange.</span><span class="sxs-lookup"><span data-stu-id="e3afc-107">It includes playing a personal greeting, recording a message, and submitting the message to be queued for delivery to the user's mailbox, which is stored on the Exchange mailbox server.</span></span>

<span data-ttu-id="e3afc-108">Se un chiamante lascia un messaggio, il messaggio viene instradato alla posta in arrivo dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e3afc-108">If a caller leaves a message, the message is routed to the user's Inbox.</span></span> <span data-ttu-id="e3afc-109">Se un chiamante sceglie di non uscire da un messaggio, nella cassetta postale dell'utente viene archiviata una notifica di chiamata senza risposta.</span><span class="sxs-lookup"><span data-stu-id="e3afc-109">If a caller chooses not to leave a message, a missed call notification is stored in the user's mailbox.</span></span> <span data-ttu-id="e3afc-110">Gli utenti possono quindi accedere alla posta in arrivo usando il client di messaggistica e collaborazione di Microsoft Outlook, Outlook Web Access, la tecnologia Exchange ActiveSync o Outlook Voice Access.</span><span class="sxs-lookup"><span data-stu-id="e3afc-110">Users can then access their Inbox by using the Microsoft Outlook messaging and collaboration client, Outlook Web Access, the Exchange ActiveSync technology, or Outlook Voice Access.</span></span> <span data-ttu-id="e3afc-111">L'oggetto e la priorità delle chiamate possono essere visualizzati in modo simile a quello del messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="e3afc-111">The subject and priority of calls can be displayed in a way similar to that of email.</span></span>

</div>

<div>

## <a name="outlook-voice-access"></a><span data-ttu-id="e3afc-112">Outlook Voice Access</span><span class="sxs-lookup"><span data-stu-id="e3afc-112">Outlook Voice Access</span></span>

<span data-ttu-id="e3afc-113">Outlook Voice Access consente a un utente di VoIP aziendale di accedere non solo alla segreteria telefonica, ma anche alla posta in arrivo di Exchange, inclusi posta elettronica, calendario e contatti da un'interfaccia di telefonia.</span><span class="sxs-lookup"><span data-stu-id="e3afc-113">Outlook Voice Access enables an Enterprise Voice user to access not just voice mail, but also the Exchange inbox, including email, calendar, and contacts from a telephony interface.</span></span> <span data-ttu-id="e3afc-114">Il numero di accesso del Sottoscrittore viene assegnato dall'amministratore della messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="e3afc-114">The subscriber access number is assigned by an Exchange UM administrator.</span></span>

</div>

<div>

## <a name="auto-attendant"></a><span data-ttu-id="e3afc-115">Operatore automatico</span><span class="sxs-lookup"><span data-stu-id="e3afc-115">Auto Attendant</span></span>

<span data-ttu-id="e3afc-116">Operatore automatico è una funzionalità di messaggistica unificata di Exchange che può essere usata per configurare un numero di telefono che gli utenti esterni possono chiamare per raggiungere i rappresentanti della società.</span><span class="sxs-lookup"><span data-stu-id="e3afc-116">Auto attendant is an Exchange UM feature that can be used to configure a phone number that outside users can dial to reach company representatives.</span></span> <span data-ttu-id="e3afc-117">In particolare, fornisce una serie di richieste vocali che assistono un chiamante esterno nell'esplorazione di un sistema di menu.</span><span class="sxs-lookup"><span data-stu-id="e3afc-117">In particular, it provides a series of voice prompts that assist an external caller in navigating a menu system.</span></span> <span data-ttu-id="e3afc-118">L'elenco delle opzioni disponibili è configurato nel server Messaggistica unificata di Exchange dall'amministratore di messaggistica unificata</span><span class="sxs-lookup"><span data-stu-id="e3afc-118">The list of available options is configured on the Exchange UM server by the Exchange UM administrator.</span></span>

</div>

<div>

## <a name="fax-services"></a><span data-ttu-id="e3afc-119">Servizi fax</span><span class="sxs-lookup"><span data-stu-id="e3afc-119">Fax Services</span></span>

<span data-ttu-id="e3afc-120">La messaggistica unificata di Exchange include le caratteristiche fax, che consentono agli utenti di ricevere i fax in arrivo nelle cassette postali di Exchange.</span><span class="sxs-lookup"><span data-stu-id="e3afc-120">Exchange UM includes fax features, which enable users to receive incoming faxes in their Exchange mailboxes.</span></span> <span data-ttu-id="e3afc-121">Per informazioni dettagliate, vedere la pagina relativa alla messaggistica unificata nella documentazione su [http://go.microsoft.com/fwlink/p/?linkId=135652](http://go.microsoft.com/fwlink/p/?linkid=135652)Microsoft Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="e3afc-121">For details, see "Unified Messaging" in the Microsoft Exchange Server documentation at [http://go.microsoft.com/fwlink/p/?linkId=135652](http://go.microsoft.com/fwlink/p/?linkid=135652).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e3afc-122">I servizi fax forniti dal server Messaggistica unificata di Exchange non sono disponibili nelle distribuzioni di Lync Server integrate con Microsoft Exchange Server 2010, Exchange 2010 con il Service Pack più recente o Exchange 2013.</span><span class="sxs-lookup"><span data-stu-id="e3afc-122">Fax services provided by the Exchange UM server are not available in Lync Server deployments that are integrated with Microsoft Exchange Server 2010, Exchange 2010 with the latest service pack, or Exchange 2013.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

