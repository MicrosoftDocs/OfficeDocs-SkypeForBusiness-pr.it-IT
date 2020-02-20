---
title: 'Lync Server 2013: caratteristiche e funzionalità di front end server, messaggistica istantanea e presenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 639df8bdcee7531895eaafe9dd8ca5fac3f6fc3d
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153728"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a><span data-ttu-id="9dac4-102">Caratteristiche e funzionalità di front end server, messaggistica istantanea e presenza in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9dac4-102">Features and functionality of Front End Servers, instant messaging, and presence in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9dac4-103">_**Ultimo argomento modificato:** 2013-03-17_</span><span class="sxs-lookup"><span data-stu-id="9dac4-103">_**Topic Last Modified:** 2013-03-17_</span></span>

<span data-ttu-id="9dac4-104">I Front End Server offrono la maggior parte delle funzionalità di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9dac4-104">Front End Servers provide most Lync Server functionality.</span></span> <span data-ttu-id="9dac4-105">Sono disponibili due edizioni: Lync Server Enterprise Edition, che è stato creato principalmente per organizzazioni di grandi dimensioni e Lync Server Standard Edition, che è stato creato principalmente per organizzazioni di piccole dimensioni che desiderano un Investment hardware più piccolo e non richiedono disponibilità elevata.</span><span class="sxs-lookup"><span data-stu-id="9dac4-105">There are two editions available: Lync Server Enterprise Edition, which is designed primarily for larger organizations, and Lync Server Standard Edition, which is designed primarily for smaller organizations which want a smaller hardware investement and do not require high availability.</span></span> <span data-ttu-id="9dac4-106">Entrambe le edizioni supportano tutti i carichi di lavoro di Lync Server, tra cui messaggistica istantanea, presenza, conferenza e VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="9dac4-106">Both editions support all Lync Server workloads including IM, presence, conferencing, and Enterprise Voice.</span></span>

<span data-ttu-id="9dac4-p102">La messaggistica istantanea consente agli utenti di comunicare tra loro in tempo reale mediante i loro computer con messaggi di testo. Sono supportate le sessioni di messaggistica istantanea sia tra due che tra più parti. Un partecipante a una conversazione di messaggistica istantanea tra due parti può aggiungere un terzo partecipante in qualsiasi momento. In tal caso, la finestra relativa alla conversazione cambia in modo da supportare le funzionalità di conferenza.</span><span class="sxs-lookup"><span data-stu-id="9dac4-p102">Instant messaging (IM) enables your users to communicate with each other in real time on their computers using text-based messages. Both two-party and multiparty IM sessions are supported. A participant in a two-party IM conversation can add a third participant to the conversation at any time. When this happens, the Conversation window changes to support conferencing features.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="9dac4-111">I client Lync e Communicator quando sono coinvolti in una comunicazione One to One, vengono spesso definiti peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="9dac4-111">Lync and Communicator clients when involved in a one to one communication, is often referred to as peer-to-peer.</span></span> <span data-ttu-id="9dac4-112">Tecnicamente, i due client stanno comunicando in una conversazione One to One, con la Central Messaging Multipoint Control Unit (IMMCU) al centro.</span><span class="sxs-lookup"><span data-stu-id="9dac4-112">Technically, the two clients are communicating in a one to one conversation, with the Instant Messaging multipoint control unit (IMMCU) in the middle.</span></span> <span data-ttu-id="9dac4-113">IMMCU è un componente di front end server.</span><span class="sxs-lookup"><span data-stu-id="9dac4-113">The IMMCU is a component of Front End Server.</span></span> <span data-ttu-id="9dac4-114">L'inserimento di IMMCU nel flusso di lavoro di comunicazione necessario consente di abilitare la registrazione dettagli chiamata e altre caratteristiche abilitate dal front end server.</span><span class="sxs-lookup"><span data-stu-id="9dac4-114">Placing the IMMCU in the required communication workflow allows call detail recording and other features that the Front End Server enables.</span></span> <span data-ttu-id="9dac4-115">La comunicazione è da una porta di origine dinamica sul client alla porta del server front-end TLS/TCP/5061 (presupponendo l'utilizzo della sicurezza del layer di trasporto consigliato).</span><span class="sxs-lookup"><span data-stu-id="9dac4-115">Communication is from a dynamic source port on the client to the Front End Server port TLS/TCP/5061 (assuming the use of the recommended transport layer security).</span></span> <span data-ttu-id="9dac4-116">In base alla progettazione, la comunicazione peer-to-peer (così come la messaggistica istantanea a più parti) è possibile solo quando Lync Server e IMMCU sono attivi e disponibili.</span><span class="sxs-lookup"><span data-stu-id="9dac4-116">By design, peer-to-peer communication (as well as multi-party IM) is possible only when Lync Server and the IMMCU is active and available.</span></span>



</div>

<span data-ttu-id="9dac4-117">La *presenza* fornisce informazioni sullo stato di altri utenti presenti sulla rete.</span><span class="sxs-lookup"><span data-stu-id="9dac4-117">*Presence* provides information to users about the status of other on the network.</span></span> <span data-ttu-id="9dac4-118">Lo stato di presenza di un utente fornisce informazioni che aiutano altri utenti a decidere se tentare di contattarlo e se utilizzare la messaggistica istantanea, il telefono o la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="9dac4-118">A user’s presence status provides information to help others decide whether they should try to contact the user and whether to use instant messaging, phone, or email.</span></span> <span data-ttu-id="9dac4-119">La presenza induce a scegliere la comunicazione istantanea ma, segnalando anche se un utente è in riunione o fuori ufficio, consente di capire quando la comunicazione istantanea non può essere utilizzata.</span><span class="sxs-lookup"><span data-stu-id="9dac4-119">Presence encourages instant communication when possible, but it also provides information about whether a user is in a meeting or out of the office, indicating that instant communication is not possible.</span></span> <span data-ttu-id="9dac4-120">Questo stato di presenza viene visualizzato come icona presenza in Lync e in altre applicazioni in grado di riconoscere la presenza, tra cui il client di messaggistica e collaborazione di Microsoft Outlook, Microsoft SharePoint Technologies, Microsoft Word e il foglio di calcolo di Microsoft Excel software.</span><span class="sxs-lookup"><span data-stu-id="9dac4-120">This presence status is displayed as a presence icon in Lync and other presence-aware applications, including the Microsoft Outlook messaging and collaboration client, Microsoft SharePoint technologies, Microsoft Word, and Microsoft Excel spreadsheet software.</span></span> <span data-ttu-id="9dac4-121">L'icona della presenza rappresenta la volontà di comunicare e la disponibilità corrente dell'utente.</span><span class="sxs-lookup"><span data-stu-id="9dac4-121">The presence icon represents the user’s current availability and willingness to communicate.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

