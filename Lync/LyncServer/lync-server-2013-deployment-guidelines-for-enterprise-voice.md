---
title: 'Lync Server 2013: Linee guida per la distribuzione di VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0f4f6198f8fb82720834d112bcf363554aaf84d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985508"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="38b9a-102">Linee guida per la distribuzione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="38b9a-102">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="38b9a-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="38b9a-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="38b9a-104">Questo argomento descrive i prerequisiti e altre linee guida da tenere in considerazione quando si prevede di distribuire Lync Server 2013 e il carico di lavoro VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="38b9a-104">This topic describes prerequisites and other guidelines to consider when you are planning to deploy Lync Server 2013 and the Enterprise Voice workload.</span></span>

<div>

## <a name="deployment-prerequisites"></a><span data-ttu-id="38b9a-105">Prerequisiti per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="38b9a-105">Deployment Prerequisites</span></span>

<span data-ttu-id="38b9a-106">Per un'esperienza ottimale durante la distribuzione di VoIP aziendale, verificare che l'infrastruttura IT, la rete e i sistemi soddisfino i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="38b9a-106">For an optimum experience when deploying Enterprise Voice, make sure that your IT infrastructure, network, and systems meet the following prerequisites:</span></span>

  - <span data-ttu-id="38b9a-107">Lync Server 2013 Standard Edition o Enterprise Edition è installato e funzionante in rete.</span><span class="sxs-lookup"><span data-stu-id="38b9a-107">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="38b9a-108">Tutti i server perimetrali sono distribuiti e operativi nella rete perimetrale, inclusi i server perimetrali con Access Edge Services, A/V Edge service, Web Conferencing Edge service e un proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="38b9a-108">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers with Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="38b9a-109">Uno o più utenti sono stati creati e abilitati per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="38b9a-109">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="38b9a-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) o ultimo Service Pack o Microsoft Exchange Server 2010 è installato.</span><span class="sxs-lookup"><span data-stu-id="38b9a-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack, or Microsoft Exchange Server 2010 is installed.</span></span> <span data-ttu-id="38b9a-111">Uno di questi è necessario per l'integrazione della messaggistica UNIFICAta di Exchange con Lync Server e per la fornitura di notifiche ricche e informazioni sul log delle chiamate agli endpoint client.</span><span class="sxs-lookup"><span data-stu-id="38b9a-111">One of these is required for integrating Exchange Unified Messaging (UM) with Lync Server and to provide rich notifications and call log information to client endpoints.</span></span>

  - <span data-ttu-id="38b9a-112">Un numero di telefono primario univoco è stato designato, normalizzato e copiato nell'attributo **msRTCSIP-line** per ogni utente che deve essere abilitato per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="38b9a-112">A unique primary phone number has been designated, normalized, and copied to the **msRTCSIP-line** attribute for each user who is to be enabled for Enterprise Voice.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="38b9a-113">Lync Server supporta i numeri e. 164 e i numeri DID (non Direct Inward Dialing).</span><span class="sxs-lookup"><span data-stu-id="38b9a-113">Lync Server supports E.164 numbers and non-Direct Inward Dialing (DID) numbers.</span></span> <span data-ttu-id="38b9a-114">I numeri non did possono essere rappresentati nel formato <STRONG> &lt;E. 164&gt;; ext =&lt;Extension&gt; </STRONG> o come stringa di cifre, con il requisito che l'estensione privata sia univoca in tutta l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="38b9a-114">Non-DID numbers can be represented in the format <STRONG>&lt;E.164&gt;;ext=&lt;extension&gt;</STRONG> or as a string of digits, with the requirement that the private extension is unique across the enterprise.</span></span> <span data-ttu-id="38b9a-115">Ad esempio, un numero privato di 1001 può essere rappresentato come <STRONG>+ 1425550100; EXT = 1001</STRONG>o come <STRONG>1001</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="38b9a-115">For example, a private number of 1001 can be represented as <STRONG>+1425550100;ext=1001</STRONG>, or as <STRONG>1001</STRONG>.</span></span> <span data-ttu-id="38b9a-116">Una volta rappresentato come <STRONG>1001</STRONG>, l'aspettativa è che questo numero privato sia univoco in tutta l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="38b9a-116">When represented as <STRONG>1001</STRONG>, the expectation is that this private number is unique across the enterprise.</span></span>

    
    </div>

  - <span data-ttu-id="38b9a-117">Gli amministratori che distribuiscono VoIP aziendale devono essere membri del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="38b9a-117">Administrators who deploy Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="38b9a-118">Office Communicator 2007 viene distribuito con successo.</span><span class="sxs-lookup"><span data-stu-id="38b9a-118">At a minimum, Office Communicator 2007 is successfully deployed.</span></span> <span data-ttu-id="38b9a-119">Per usare le nuove caratteristiche di questa versione, viene distribuito Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="38b9a-119">To use features new to this release, Lync 2013 is deployed.</span></span>

  - <span data-ttu-id="38b9a-120">L'infrastruttura MKI (Managed Key Infrastructure) viene distribuita e configurata usando un'infrastruttura di autorità di certificazione (CA) Microsoft o di terze parti.</span><span class="sxs-lookup"><span data-stu-id="38b9a-120">Managed key infrastructure (MKI) is deployed and configured, using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>

  - <span data-ttu-id="38b9a-121">Ogni computer in cui è installato Mediation Server deve essere:</span><span class="sxs-lookup"><span data-stu-id="38b9a-121">Each computer on which you install Mediation Server must be:</span></span>
    
      - <span data-ttu-id="38b9a-122">Un server membro di un dominio e preparato per servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="38b9a-122">A member server of a domain, and prepared for Active Directory Domain Services.</span></span> <span data-ttu-id="38b9a-123">Per le procedure di preparazione dei servizi di dominio Active Directory, vedere [preparazione di servizi di dominio Active Directory per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="38b9a-123">For Active Directory Domain Services preparation procedures, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="38b9a-124">Eseguire uno dei sistemi operativi seguenti:</span><span class="sxs-lookup"><span data-stu-id="38b9a-124">Running one of the following operating systems:</span></span>
        
          - <span></span>  
            <span data-ttu-id="38b9a-125">Versione 64-bit del sistema operativo standard di Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="38b9a-125">The 64-bit edition of the Windows Server 2008 Standard operating system</span></span>
        
          - <span></span>  
            <span data-ttu-id="38b9a-126">Versione 64-bit del sistema operativo Windows Server 2008 Enterprise</span><span class="sxs-lookup"><span data-stu-id="38b9a-126">The 64-bit edition of the Windows Server 2008 Enterprise operating system</span></span>

  - <span data-ttu-id="38b9a-127">Se la connessione alla rete PSTN (Public Switched Telephone Network) o PBX (Private Branch Exchange) è mediante una connessione TDM (Time Division Multiplexing), è disponibile uno o più gateway PSTN per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="38b9a-127">If the connection to the public switched telephone network (PSTN) or private branch exchange (PBX) is by means of a Time Division Multiplexing (TDM) connection, one or more PSTN gateways are available for deployment.</span></span> <span data-ttu-id="38b9a-128">Se la connessione è per mezzo di un trunk SIP, non è necessario un gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="38b9a-128">(If the connection is by means of a SIP trunk, a PSTN gateway is not required.)</span></span>

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a><span data-ttu-id="38b9a-129">Interruzioni del servizio di alimentazione, di rete o telefoniche</span><span class="sxs-lookup"><span data-stu-id="38b9a-129">Power, Network, or Telephone Service Outages</span></span>

<span data-ttu-id="38b9a-130">In caso di interruzioni, interruzioni o altre degradazioni dei servizi di Power, Network o telefono nella propria posizione, la voce, la messaggistica istantanea, la presenza e altre funzionalità di Lync Server e qualsiasi dispositivo connesso a Lync Server potrebbero non funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="38b9a-130">If there is an outage, disruption, or other degradation of the power, network, or telephone services at your location, the voice, instant messaging, presence, and other features of Lync Server and any device connected to Lync Server may not work properly.</span></span>

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a><span data-ttu-id="38b9a-131">Enterprise Voice dipende dalla disponibilità del server e dalla funzionalità del client vocale e dell'hardware</span><span class="sxs-lookup"><span data-stu-id="38b9a-131">Enterprise Voice Depends on Server Availability and Voice Client and Hardware Operability</span></span>

<span data-ttu-id="38b9a-132">Le comunicazioni vocali con Lync Server dipendono dalla disponibilità del software server e dal corretto funzionamento dei client vocali o dei dispositivi telefonici hardware che si connettono al software server.</span><span class="sxs-lookup"><span data-stu-id="38b9a-132">Voice communications with Lync Server depend upon the availability of the server software and the proper functioning of the voice clients or the hardware phone devices connecting to the server software.</span></span>

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a><span data-ttu-id="38b9a-133">Mezzi alternativi per accedere ai servizi di emergenza</span><span class="sxs-lookup"><span data-stu-id="38b9a-133">Alternative Means of Accessing Emergency Services</span></span>

<span data-ttu-id="38b9a-134">Per i percorsi in cui si installa un client vocale, ad esempio un PC con un client Lync o un dispositivo Lync Phone Edition, è consigliabile mantenere un'opzione di backup per consentire agli utenti di chiamare i servizi di emergenza (ad esempio, 911 o 999) in caso di interruzione di corrente , degradazione della connettività di rete, interruzione del servizio telefonico o altro problema che potrebbe inibire il funzionamento dei dispositivi Lync Server, Lync o Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="38b9a-134">For those locations where you install a voice client (for example, a PC running Lync client or an Lync Phone Edition device), we recommend that you maintain a backup option for users to call emergency services (for example, 911 or 999) in case of a power failure, network connectivity degradation, telephone service outage, or other issue that may inhibit operation of Lync Server, Lync, or Lync Phone Edition devices.</span></span> <span data-ttu-id="38b9a-135">Queste opzioni alternative potrebbero includere un telefono connesso a una linea di rete telefonica pubblica commutata standard o a un telefono cellulare.</span><span class="sxs-lookup"><span data-stu-id="38b9a-135">Such alternative options could include a telephone connected to a standard public switched telephone network line or a cell phone.</span></span>

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a><span data-ttu-id="38b9a-136">Chiamate di emergenza e sistemi telefonici multilinea</span><span class="sxs-lookup"><span data-stu-id="38b9a-136">Emergency Calls and Multi-Line Telephone Systems</span></span>

<span data-ttu-id="38b9a-137">L'uso di un sistema telefonico multilinea (MLTS) può essere soggetto alle leggi statali o federali degli Stati Uniti o alle leggi di altri paesi/aree geografiche che richiedono alla MLTS di specificare il numero di telefono, l'estensione e/o la posizione fisica del chiamante per i servizi di emergenza applicabili quando un chiamante viene inserito in servizi di emergenza, ad esempio quando si digita un 999 911 numero di accesso di</span><span class="sxs-lookup"><span data-stu-id="38b9a-137">The use of a multiline telephone system (MLTS) may be subject to U.S state or federal laws or the laws of other countries/regions that require the MLTS to provide a caller’s telephone number, extension, and/or physical location to applicable emergency services when a caller is placed to emergency services (for example, when dialing an emergency access number such as 911 or 999).</span></span> <span data-ttu-id="38b9a-138">In questa versione Lync Server può essere configurato in modo da consentire la posizione fisica del chiamante a un provider di servizi di emergenza, come descritto in [pianificazione per i servizi di emergenza (E9-1-1) in Lync server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span><span class="sxs-lookup"><span data-stu-id="38b9a-138">In this release, Lync Server can be configured to provide a caller’s physical location to an emergency services provider, as described in [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span> <span data-ttu-id="38b9a-139">La conformità alle leggi di MLTS è la sola responsabilità dell'acquirente dei dispositivi Lync Server, Lync client e Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="38b9a-139">Compliance with MLTS laws is the sole responsibility of the purchaser of Lync Server, Lync client, and Lync Phone Edition devices.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

