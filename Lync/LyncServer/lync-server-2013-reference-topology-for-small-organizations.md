---
title: Topologia di riferimento per Lync Server 2013 per organizzazioni di piccole dimensioni
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Reference topology for small organizations
ms:assetid: 0453aeee-c41f-44e6-a6e0-aaace526ca08
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398095(v=OCS.15)
ms:contentKeyID: 48183272
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1f4c9d99e95dea0edd0b5990b0bb198dfe59dc61
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="reference-topology-for-lync-server-2013-in-small-organizations"></a><span data-ttu-id="80d10-102">Topologia di riferimento per Lync Server 2013 in organizzazioni di piccole dimensioni</span><span class="sxs-lookup"><span data-stu-id="80d10-102">Reference topology for Lync Server 2013 in small organizations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="80d10-103">_**Ultimo argomento modificato:** 2013-10-07_</span><span class="sxs-lookup"><span data-stu-id="80d10-103">_**Topic Last Modified:** 2013-10-07_</span></span>

<span data-ttu-id="80d10-104">La topologia di riferimento per le organizzazioni di piccole dimensioni dimostra come è possibile distribuire una soluzione robusta e a disponibilità elevata distribuendo solo tre server che eseguono Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80d10-104">The reference topology for small organizations shows how you can deploy a robust, highly available solution by deploying only three servers running Lync Server.</span></span>

<span data-ttu-id="80d10-105">**Topologia di riferimento per le organizzazioni di piccole dimensioni**</span><span class="sxs-lookup"><span data-stu-id="80d10-105">**Reference topology for small organizations**</span></span>

<span data-ttu-id="80d10-106">![Topologia di riferimento per la distribuzione di tre server diagramma](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Topologia di riferimento per la distribuzione di tre server diagramma")</span><span class="sxs-lookup"><span data-stu-id="80d10-106">![Reference topology deploying three servers diagram](images/Gg398095.25196d0d-dd07-451b-83ba-94c0ddf59030(OCS.15).jpg "Reference topology deploying three servers diagram")</span></span>

  - <span data-ttu-id="80d10-107">**Coppia di server Standard Edition distribuiti**     in questa organizzazione sono disponibili 4.000 utenti nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="80d10-107">**Pair of Standard Edition Servers Deployed**    This organization has 4,000 users at their central site.</span></span> <span data-ttu-id="80d10-108">L'organizzazione ha distribuito due server Standard Edition e li ha accoppiati insieme per abilitare la disponibilità elevata e il ripristino di emergenza.</span><span class="sxs-lookup"><span data-stu-id="80d10-108">The organization has deployed two Standard Edition servers and paired them together to enable high availability and disaster recovery.</span></span> <span data-ttu-id="80d10-109">Ogni server Homes 2.000 utenti, ma le informazioni su tutti gli utenti vengono sincronizzate tra i due server.</span><span class="sxs-lookup"><span data-stu-id="80d10-109">Each server homes 2,000 users, but information about all users is synchronized between the two servers.</span></span> <span data-ttu-id="80d10-110">Se si abbassa, un amministratore può avere esito negativo su quegli utenti che devono essere serviti dall'altro server, con un minimo di interruzioni per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="80d10-110">If one goes down, an administrator can fail over those users to be served by the other server, with a minimum of disruption to users.</span></span> <span data-ttu-id="80d10-111">Per ulteriori informazioni sulle funzionalità di disponibilità elevata e ripristino di emergenza in Lync Server 2013, vedere [pianificazione per la disponibilità elevata e il ripristino di emergenza in Lync server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="80d10-111">For more information about high availability and disaster recovery features in Lync Server 2013, see [Planning for high availability and disaster recovery in Lync Server 2013](lync-server-2013-planning-for-high-availability-and-disaster-recovery.md).</span></span>

  - <span data-ttu-id="80d10-112">**La distribuzione del server perimetrale è consigliata.**    Anche se la distribuzione di un server perimetrale non è necessaria per la messaggistica istantanea, la presenza e le conferenze interne, è consigliabile anche per le distribuzioni di piccole dimensioni.</span><span class="sxs-lookup"><span data-stu-id="80d10-112">**Edge Server deployment is recommended.**   Although deploying an Edge Server is not required for internal IM, presence and conferencing, we recommend it even for small deployments.</span></span> <span data-ttu-id="80d10-113">È possibile massimizzare l'investimento di Lync Server distribuendo un server perimetrale per fornire il servizio agli utenti attualmente esterni ai firewall dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="80d10-113">You can maximize your Lync Server investment by deploying an Edge Server to provide service to users currently outside your organization’s firewalls.</span></span> <span data-ttu-id="80d10-114">Tra i vantaggi derivanti dall'utilizzo di server perimetrali sono inclusi i seguenti:</span><span class="sxs-lookup"><span data-stu-id="80d10-114">The benefits include the following:</span></span>
    
      - <span data-ttu-id="80d10-115">Gli utenti dell'organizzazione possono utilizzare le funzionalità di Lync Server, se lavorano da casa o sono in viaggio.</span><span class="sxs-lookup"><span data-stu-id="80d10-115">Your organization’s own users can use Lync Server functionality, if they are working from home or are out on the road.</span></span>
    
      - <span data-ttu-id="80d10-116">Gli utenti possono invitare utenti esterni a partecipare alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="80d10-116">Your users can invite outside users to participate in meetings.</span></span>
    
      - <span data-ttu-id="80d10-117">Se si dispone di un partner, un fornitore o un'organizzazione del cliente che utilizza anche Lync Server, è possibile creare una *relazione federata* con tale organizzazione.</span><span class="sxs-lookup"><span data-stu-id="80d10-117">If you have a partner, vendor or customer organization that also uses Lync Server, you can form a *federated relationship* with that organization.</span></span> <span data-ttu-id="80d10-118">La distribuzione di Lync Server dovrebbe quindi riconoscere gli utenti provenienti da tale organizzazione federata, determinando una maggiore collaborazione.</span><span class="sxs-lookup"><span data-stu-id="80d10-118">Your Lync Server deployment would then recognize users from that federated organization, leading to better collaboration.</span></span>
    
      - <span data-ttu-id="80d10-119">Gli utenti possono scambiare messaggi istantanei con gli utenti di servizi di messaggistica istantanea pubblici, inclusi uno o più dei seguenti: Windows Live,\!AOL, Yahoo e Google Talk.</span><span class="sxs-lookup"><span data-stu-id="80d10-119">Your users can exchange instant messages with users of public IM services, including any or all of the following: Windows Live, AOL, Yahoo\!, and Google Talk.</span></span> <span data-ttu-id="80d10-120">Potrebbe essere necessaria una licenza separata per la connettività di messaggistica istantanea pubblica con questi servizi.</span><span class="sxs-lookup"><span data-stu-id="80d10-120">A separate license might be required for public IM connectivity with these services.</span></span>
        
        <div>
        

        > [!IMPORTANT]  
        > <UL>
        > <LI>
        > <P><span data-ttu-id="80d10-121">Al 1 ° settembre 2012, la licenza di sottoscrizione di Microsoft Lync Public IM Connectivity ("PIC USL") non è più disponibile per l'acquisto dei contratti nuovi o rinnovati.</span><span class="sxs-lookup"><span data-stu-id="80d10-121">As of September 1st, 2012, the Microsoft Lync Public IM Connectivity User Subscription License (“PIC USL”) is no longer available for purchase for new or renewing agreements.</span></span> <span data-ttu-id="80d10-122">I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="80d10-122">Customers with active licenses will be able to continue to federate with Yahoo!</span></span> <span data-ttu-id="80d10-123">Messenger fino alla data di arresto del servizio.</span><span class="sxs-lookup"><span data-stu-id="80d10-123">Messenger until the service shut down date.</span></span> <span data-ttu-id="80d10-124">Una data di fine vita del 2014 giugno per AOL e Yahoo!</span><span class="sxs-lookup"><span data-stu-id="80d10-124">An end of life date of June 2014 for AOL and Yahoo!</span></span> <span data-ttu-id="80d10-125">sono stati annunciati.</span><span class="sxs-lookup"><span data-stu-id="80d10-125">has been announced.</span></span> <span data-ttu-id="80d10-126">Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="80d10-126">For details, see <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">Support for public instant messenger connectivity in Lync Server 2013</A>.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="80d10-127">Il PIC USL è una licenza per ogni utente per ogni mese che è necessaria per Lync Server o Office Communications Server per la Federazione con Yahoo!</span><span class="sxs-lookup"><span data-stu-id="80d10-127">The PIC USL is a per-user per-month subscription license that is required for Lync Server or Office Communications Server to federate with Yahoo!</span></span> <span data-ttu-id="80d10-128">Messaggero.</span><span class="sxs-lookup"><span data-stu-id="80d10-128">Messenger.</span></span> <span data-ttu-id="80d10-129">La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale si sta liquidando.</span><span class="sxs-lookup"><span data-stu-id="80d10-129">Microsoft’s ability to provide this service has been contingent upon support from Yahoo!, the underlying agreement for which is winding down.</span></span></P>
        > <LI>
        > <P><span data-ttu-id="80d10-130">Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="80d10-130">More than ever, Lync is a powerful tool for connecting across organizations and with individuals around the world.</span></span> <span data-ttu-id="80d10-131">La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync.</span><span class="sxs-lookup"><span data-stu-id="80d10-131">Federation with Windows Live Messenger requires no additional user/device licenses beyond the Lync Standard CAL.</span></span> <span data-ttu-id="80d10-132">La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</span><span class="sxs-lookup"><span data-stu-id="80d10-132">Skype federation will be added to this list, enabling Lync users to reach hundreds of millions of people with IM and voice.</span></span></P></LI></UL>

        
        </div>

  - <span data-ttu-id="80d10-133">**Survivable site di succursale.**    Questa organizzazione esegue un programma pilota della caratteristica VoIP aziendale di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80d10-133">**Branch site survivability.**   This organization is running a pilot program of the Enterprise Voice feature of Lync Server.</span></span> <span data-ttu-id="80d10-134">Alcuni utenti utilizzano Lync Server come soluzione vocale unica.</span><span class="sxs-lookup"><span data-stu-id="80d10-134">Some users are using Lync Server as their sole voice solution.</span></span> <span data-ttu-id="80d10-135">Alcuni di questi utenti sono ubicati nel sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="80d10-135">Some of these Voice pilot users are located at the branch site.</span></span> <span data-ttu-id="80d10-136">Il sito di succursale non dispone di un collegamento WAN (Wide Area Network) affidabile al sito centrale, quindi viene distribuito un Survivable Branch Appliance.</span><span class="sxs-lookup"><span data-stu-id="80d10-136">The branch site does not have a reliable wide area network (WAN) link to the central site, so a Survivable Branch Appliance is deployed there.</span></span> <span data-ttu-id="80d10-137">Con questa distribuzione, se il collegamento WAN si abbassa, gli utenti del sito di succursale possono ancora effettuare e ricevere chiamate (sia le chiamate all'interno dell'organizzazione che le chiamate PSTN), hanno la funzionalità della segreteria telefonica e comunicano con la messaggistica istantanea con due parti.</span><span class="sxs-lookup"><span data-stu-id="80d10-137">With this deployed, if the WAN link goes down, users at the branch site can still make and receive calls (both calls within the organization and PSTN calls), have voice mail functionality, and communicate with two-party instant messaging (IM).</span></span> <span data-ttu-id="80d10-138">Gli utenti possono inoltre essere autenticati anche quando il collegamento WAN non è disponibile.</span><span class="sxs-lookup"><span data-stu-id="80d10-138">Users can also be authenticated when the WAN link is unavailable as well.</span></span>

  - <span data-ttu-id="80d10-139">**Distribuzione di Messaggistica unificata di Exchange.**</span><span class="sxs-lookup"><span data-stu-id="80d10-139">**Exchange UM deployment.**</span></span> <span data-ttu-id="80d10-140">Questa topologia di riferimento include un server di messaggistica unificata di Exchange, che esegue Microsoft Exchange Server, non Lync Server.</span><span class="sxs-lookup"><span data-stu-id="80d10-140">This reference topology includes an Exchange Unified Messaging (UM) Server, which runs Microsoft Exchange Server, not Lync Server.</span></span>
    
    <span data-ttu-id="80d10-141">Per informazioni dettagliate sulla messaggistica UNIFICAta di Exchange, vedere [pianificazione dell'integrazione della messaggistica unificata di Exchange in Lync server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) e [integrazione della messaggistica unificata di Exchange ospitata in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="80d10-141">For details about Exchange UM, see [Planning for Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-planning-for-exchange-unified-messaging-integration.md) and [Hosted Exchange Unified Messaging integration in Lync Server 2013](lync-server-2013-hosted-exchange-unified-messaging-integration.md) in the Planning documentation.</span></span>

  - <span data-ttu-id="80d10-142">**Server Office Web Apps.**</span><span class="sxs-lookup"><span data-stu-id="80d10-142">**Office Web Apps Server.**</span></span> <span data-ttu-id="80d10-143">È consigliabile distribuire un server Office Web Apps o una farm di server Office Web Apps in ogni organizzazione che utilizza le conferenze Web.</span><span class="sxs-lookup"><span data-stu-id="80d10-143">We recommend deploying an Office Web Apps Server or Office Web Apps Server farm in every organization that uses web conferencing.</span></span> <span data-ttu-id="80d10-144">Il server Office Web Apps rende possibile la presentazione di diapositive di PowerPoint nelle conferenze Web.</span><span class="sxs-lookup"><span data-stu-id="80d10-144">Office Web Apps Server makes it possible for PowerPoint slides to be presented in web conferences.</span></span> <span data-ttu-id="80d10-145">Per ulteriori informazioni, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span><span class="sxs-lookup"><span data-stu-id="80d10-145">For more information, see [Configuring integration with Office Web Apps Server and Lync Server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

