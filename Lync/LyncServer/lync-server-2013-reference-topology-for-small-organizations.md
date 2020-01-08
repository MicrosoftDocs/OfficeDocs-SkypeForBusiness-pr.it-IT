---
title: Topologia di riferimento di Lync Server 2013 per le organizzazioni di piccole dimensioni
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c06a3585a342ecc7fa7c41ff2b2b2682d2b8a0c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976594"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a><span data-ttu-id="8b713-102">Topologia di riferimento per Lync Server 2013 in piccole organizzazioni</span><span class="sxs-lookup"><span data-stu-id="8b713-102">Reference topology for Lync Server 2013 in small organizations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8b713-103">_**Argomento Ultima modifica:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="8b713-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="8b713-104">La topologia di riferimento per le piccole organizzazioni Mostra come distribuire una soluzione robusta e altamente disponibile distribuendo solo tre server che esegue Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8b713-104">The reference topology for small organizations shows how you can deploy a robust, highly available solution by deploying only three servers running Lync Server.</span></span>

<span data-ttu-id="8b713-105">**Topologia di riferimento per piccole organizzazioni**</span><span class="sxs-lookup"><span data-stu-id="8b713-105">**Reference topology for small organizations**</span></span>

<span data-ttu-id="8b713-106">![Topologia di riferimento distribuzione di tre server]diagramma(images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "topologia di riferimento per la distribuzione di tre server")</span><span class="sxs-lookup"><span data-stu-id="8b713-106">![Reference topology deploying three servers diagram](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Reference topology deploying three servers diagram")</span></span>

  - <span data-ttu-id="8b713-107">**Coppia di server standard distribuiti**     questa organizzazione ha 4.000 utenti nel loro sito centrale.</span><span class="sxs-lookup"><span data-stu-id="8b713-107">**Pair of Standard Edition Servers Deployed**    This organization has 4,000 users at their central site.</span></span> <span data-ttu-id="8b713-108">L'organizzazione ha distribuito due server standard e li ha abbinati per consentire l'elevata disponibilità e il ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="8b713-108">The organization has deployed two Standard Edition servers and paired them together to enable high availability and disaster recovery.</span></span> <span data-ttu-id="8b713-109">Ogni server abita 2.000 utenti, ma le informazioni su tutti gli utenti vengono sincronizzate tra i due server.</span><span class="sxs-lookup"><span data-stu-id="8b713-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span></span> <span data-ttu-id="8b713-110">Se si abbassa, un amministratore può eseguire il failover di questi utenti per essere serviti dall'altro server, con un minimo di interruzioni per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="8b713-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span></span> <span data-ttu-id="8b713-111">Per altre informazioni sulle caratteristiche di disponibilità elevata e ripristino di emergenza in Lync Server 2013, vedere [pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="8b713-111">For more information about high availability and disaster recovery features in Lync Server 2013, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="8b713-112">**È consigliabile distribuire Edge Server.**    Anche se la distribuzione di un server perimetrale non è necessaria per la messaggistica istantanea, la presenza e le conferenze interne, è consigliabile anche per piccole distribuzioni.</span><span class="sxs-lookup"><span data-stu-id="8b713-112">**Edge Server deployment is recommended.**   Although deploying an Edge Server is not required for internal IM, presence and conferencing, we recommend it even for small deployments.</span></span> <span data-ttu-id="8b713-113">Puoi massimizzare l'investimento di Lync Server distribuendo un server perimetrale per garantire il servizio agli utenti al di fuori dei firewall dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8b713-113">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="8b713-114">I vantaggi includono i seguenti:</span><span class="sxs-lookup"><span data-stu-id="8b713-114">The benefits include the following:</span></span>
    
      - <span data-ttu-id="8b713-115">Gli utenti dell'organizzazione possono usare le funzionalità di Lync Server, se lavorano da casa o sono fuori strada.</span><span class="sxs-lookup"><span data-stu-id="8b713-115">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="8b713-116">Gli utenti possono invitare utenti esterni a partecipare alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="8b713-116">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="8b713-117">Se si ha un partner, un fornitore o un'organizzazione di clienti che usa anche Lync Server, è possibile creare una *relazione federata* con tale organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8b713-117">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="8b713-118">La distribuzione di Lync Server riconoscerebbe quindi gli utenti di tale organizzazione federata, con una migliore collaborazione.</span><span class="sxs-lookup"><span data-stu-id="8b713-118">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="8b713-119">Gli utenti possono scambiare messaggi istantanei con utenti di servizi di messaggistica istantanea pubblici, inclusi uno o più dei seguenti: Windows Live, AOL\!, Yahoo e Google Talk.</span><span class="sxs-lookup"><span data-stu-id="8b713-119">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="8b713-120">Potrebbe essere necessaria una licenza separata per la connettività di messaggistica istantanea pubblica con questi servizi.</span><span class="sxs-lookup"><span data-stu-id="8b713-120">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="8b713-121">A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="8b713-121">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="8b713-122">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="8b713-122">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="8b713-123">Messenger fino alla data di chiusura del servizio.</span><span class="sxs-lookup"><span data-stu-id="8b713-123">Messenger until the service shut down date.</span></span> <span data-ttu-id="8b713-124">Data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="8b713-124">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="8b713-125">è stato annunciato.</span><span class="sxs-lookup"><span data-stu-id="8b713-125">has been announced.</span></span> <span data-ttu-id="8b713-126">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="8b713-126">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="8b713-127">Il PIC USL è una licenza per abbonamento mensile per ogni utente necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="8b713-127">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="8b713-128">Messenger.</span><span class="sxs-lookup"><span data-stu-id="8b713-128">Messenger.</span></span> <span data-ttu-id="8b713-129">La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto di Yahoo!, l'accordo sottostante per il quale sta per finire.</span><span class="sxs-lookup"><span data-stu-id="8b713-129">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="8b713-130">Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="8b713-130">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="8b713-131">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="8b713-131">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="8b713-132">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e voce.</span><span class="sxs-lookup"><span data-stu-id="8b713-132">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="8b713-133">**Sopravvivenza del sito della filiale.**    Questa organizzazione sta usando un programma pilota della funzionalità VoIP aziendale di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8b713-133">**Branch site survivability.**   This organization is running a pilot program of the Enterprise Voice feature of Lync Server.</span></span> <span data-ttu-id="8b713-134">Alcuni utenti usano Lync Server come soluzione vocale unica.</span><span class="sxs-lookup"><span data-stu-id="8b713-134">Some users are using Lync Server as their sole voice solution.</span></span> <span data-ttu-id="8b713-135">Alcuni di questi utenti di Voice Pilot si trovano nel sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="8b713-135">Some of these Voice pilot users are located at the branch site.</span></span> <span data-ttu-id="8b713-136">Il sito di succursale non ha un collegamento WAN (Wide Area Network) affidabile al sito centrale, quindi viene distribuito un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="8b713-136">The branch site does not have a reliable wide area network (WAN) link to the central site, so a Survivable Branch Appliance is deployed there.</span></span> <span data-ttu-id="8b713-137">Con questa distribuzione, se il collegamento WAN si abbassa, gli utenti del sito della filiale possono ancora effettuare e ricevere chiamate (sia le chiamate all'interno dell'organizzazione che le chiamate PSTN), avere la funzionalità della segreteria telefonica e comunicare con messaggistica istantanea a due parti.</span><span class="sxs-lookup"><span data-stu-id="8b713-137">With this deployed, if the WAN link goes down, users at the branch site can still make and receive calls (both calls within the organization and PSTN calls), have voice mail functionality, and communicate with two-party instant messaging (IM).</span></span> <span data-ttu-id="8b713-138">Gli utenti possono essere autenticati anche quando il collegamento WAN non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="8b713-138">Users can also be authenticated when the WAN link is unavailable as well.</span></span>

  - <span data-ttu-id="8b713-139">**Distribuzione della messaggistica unificata di Exchange.**</span><span class="sxs-lookup"><span data-stu-id="8b713-139">**Exchange UM deployment.**</span></span> <span data-ttu-id="8b713-140">Questa topologia di riferimento include un server di messaggistica UNIFICAta di Exchange, che esegue Microsoft Exchange Server e non Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8b713-140">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="8b713-141">Per informazioni dettagliate sulla messaggistica unificata di Exchange, vedere [pianificazione dell'integrazione della messaggistica unificata di Exchange in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) e [integrazione della messaggistica unificata di Exchange ospitata in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="8b713-141">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="8b713-142">**Server di Office Web Apps.**</span><span class="sxs-lookup"><span data-stu-id="8b713-142">**Office Web Apps Server.**</span></span> <span data-ttu-id="8b713-143">È consigliabile distribuire un server di Office Web Apps o una server farm di Office Web Apps in tutte le organizzazioni che usano servizi di conferenza Web.</span><span class="sxs-lookup"><span data-stu-id="8b713-143">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="8b713-144">Office Web Apps Server rende possibile la presentazione di diapositive di PowerPoint in conferenze Web.</span><span class="sxs-lookup"><span data-stu-id="8b713-144">Office Web Apps Server makes it possible for PowerPoint slides to be presented in web conferences.</span></span> <span data-ttu-id="8b713-145">Per altre informazioni, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="8b713-145">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

