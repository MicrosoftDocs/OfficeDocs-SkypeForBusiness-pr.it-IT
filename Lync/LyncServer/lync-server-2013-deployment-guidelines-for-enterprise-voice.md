---
title: 'Lync Server 2013: linee guida per la distribuzione di VoIP aziendale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment guidelines for Enterprise Voice
ms:assetid: 8985bd93-7613-4cef-9c89-51df6049ed9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398694(v=OCS.15)
ms:contentKeyID: 48184733
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 770dfe3ce43af7dc2e6984698c095430b5c34f69
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049428"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-guidelines-for-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="2614b-102">Linee guida per la distribuzione di VoIP aziendale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2614b-102">Deployment guidelines for Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2614b-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="2614b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="2614b-104">In questo argomento vengono descritti i prerequisiti e altre linee guida da prendere in considerazione quando si pianifica la distribuzione di Lync Server 2013 e del carico di lavoro VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="2614b-104">This topic describes prerequisites and other guidelines to consider when you are planning to deploy Lync Server 2013 and the Enterprise Voice workload.</span></span>

<div>

## <a name="deployment-prerequisites"></a><span data-ttu-id="2614b-105">Prerequisiti per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="2614b-105">Deployment Prerequisites</span></span>

<span data-ttu-id="2614b-106">Per un'esperienza ottimale quando si distribuisce VoIP aziendale, verificare che l'infrastruttura IT, la rete e i sistemi soddisfino i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="2614b-106">For an optimum experience when deploying Enterprise Voice, make sure that your IT infrastructure, network, and systems meet the following prerequisites:</span></span>

  - <span data-ttu-id="2614b-107">Lync Server 2013 Standard Edition o Enterprise Edition è installato e funzionante nella rete.</span><span class="sxs-lookup"><span data-stu-id="2614b-107">Lync Server 2013 Standard Edition or Enterprise Edition is installed and operational on your network.</span></span>

  - <span data-ttu-id="2614b-108">Tutti i server perimetrali sono distribuiti e operativi nella rete perimetrale, inclusi i server perimetrali con il servizio Access Edge, il servizio A/V Edge, il servizio Web Conferencing Edge e un proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="2614b-108">All Edge Servers are deployed and operational in your perimeter network, including Edge Servers with Access Edge service, A/V Edge service, Web Conferencing Edge service, and a reverse proxy.</span></span>

  - <span data-ttu-id="2614b-109">Uno o più utenti sono stati creati e abilitati per Lync Server.</span><span class="sxs-lookup"><span data-stu-id="2614b-109">One or more users have been created and enabled for Lync Server.</span></span>

  - <span data-ttu-id="2614b-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) o Service Pack più recente o Microsoft Exchange Server 2010 è installato.</span><span class="sxs-lookup"><span data-stu-id="2614b-110">Microsoft Exchange Server 2007 Service Pack 1 (SP1) or latest service pack, or Microsoft Exchange Server 2010 is installed.</span></span> <span data-ttu-id="2614b-111">Uno di questi è necessario per l'integrazione della messaggistica unificata di Exchange con Lync Server e per fornire notifiche ricche e informazioni sui registri di chiamata agli endpoint client.</span><span class="sxs-lookup"><span data-stu-id="2614b-111">One of these is required for integrating Exchange Unified Messaging (UM) with Lync Server and to provide rich notifications and call log information to client endpoints.</span></span>

  - <span data-ttu-id="2614b-112">Un numero di telefono primario univoco è stato designato, normalizzato e copiato nell'attributo **msRTCSIP-line** per ogni utente che deve essere abilitato per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="2614b-112">A unique primary phone number has been designated, normalized, and copied to the **msRTCSIP-line** attribute for each user who is to be enabled for Enterprise Voice.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="2614b-113">Lync Server supporta i numeri e. 164 e i numeri DID (non Direct Inward Dialing).</span><span class="sxs-lookup"><span data-stu-id="2614b-113">Lync Server supports E.164 numbers and non-Direct Inward Dialing (DID) numbers.</span></span> <span data-ttu-id="2614b-114">I numeri non did possono essere rappresentati nel formato <STRONG> &lt;E. 164&gt;; ext =&lt;Extension&gt; </STRONG> o come stringa di cifre, con il requisito che l'interno privato sia univoco all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2614b-114">Non-DID numbers can be represented in the format <STRONG>&lt;E.164&gt;;ext=&lt;extension&gt;</STRONG> or as a string of digits, with the requirement that the private extension is unique across the enterprise.</span></span> <span data-ttu-id="2614b-115">Un numero privato 1001 può ad esempio essere rappresentato come <STRONG>+1425550100;ext=1001</STRONG> o come <STRONG>1001</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="2614b-115">For example, a private number of 1001 can be represented as <STRONG>+1425550100;ext=1001</STRONG>, or as <STRONG>1001</STRONG>.</span></span> <span data-ttu-id="2614b-116">Quando rappresentato come <STRONG>1001</STRONG>, tale numero deve essere univoco nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2614b-116">When represented as <STRONG>1001</STRONG>, the expectation is that this private number is unique across the enterprise.</span></span>

    
    </div>

  - <span data-ttu-id="2614b-117">Gli amministratori che distribuiscono VoIP aziendale devono essere membri del gruppo RTCUniversalServerAdmins.</span><span class="sxs-lookup"><span data-stu-id="2614b-117">Administrators who deploy Enterprise Voice should be members of the RTCUniversalServerAdmins group.</span></span>

  - <span data-ttu-id="2614b-118">Come minimo, Office Communicator 2007 è stato distribuito correttamente.</span><span class="sxs-lookup"><span data-stu-id="2614b-118">At a minimum, Office Communicator 2007 is successfully deployed.</span></span> <span data-ttu-id="2614b-119">Per utilizzare le funzionalità nuove di questa versione, Lync 2013 è distribuito.</span><span class="sxs-lookup"><span data-stu-id="2614b-119">To use features new to this release, Lync 2013 is deployed.</span></span>

  - <span data-ttu-id="2614b-120">L'infrastruttura MKI (Managed Key Infrastructure) è distribuita e configurata mediante un'infrastruttura Microsoft o di un'Autorità di certificazione (CA, Certification Authority) di terze parti.</span><span class="sxs-lookup"><span data-stu-id="2614b-120">Managed key infrastructure (MKI) is deployed and configured, using either a Microsoft or a third-party certification authority (CA) infrastructure.</span></span>

  - <span data-ttu-id="2614b-121">Ogni computer in cui si installa Mediation Server deve avere le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="2614b-121">Each computer on which you install Mediation Server must be:</span></span>
    
      - <span data-ttu-id="2614b-122">Un server membro di un dominio e preparato per i servizi di dominio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2614b-122">A member server of a domain, and prepared for Active Directory Domain Services.</span></span> <span data-ttu-id="2614b-123">Per le procedure di preparazione di servizi di dominio Active Directory, vedere [preparazione di servizi di dominio Active Directory per Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="2614b-123">For Active Directory Domain Services preparation procedures, see [Preparing Active Directory Domain Services for Lync Server 2013](lync-server-2013-preparing-active-directory-domain-services.md) in the Deployment documentation.</span></span>
    
      - <span data-ttu-id="2614b-124">Eseguire uno dei sistemi operativi seguenti:</span><span class="sxs-lookup"><span data-stu-id="2614b-124">Running one of the following operating systems:</span></span>
        
          - <span></span>  
            <span data-ttu-id="2614b-125">Windows Server 2008 Standard a 64 bit</span><span class="sxs-lookup"><span data-stu-id="2614b-125">The 64-bit edition of the Windows Server 2008 Standard operating system</span></span>
        
          - <span></span>  
            <span data-ttu-id="2614b-126">Windows Server 2008 Enterprise a 64 bit</span><span class="sxs-lookup"><span data-stu-id="2614b-126">The 64-bit edition of the Windows Server 2008 Enterprise operating system</span></span>

  - <span data-ttu-id="2614b-p105">Se la connessione alla rete PSTN o al sistema PBX viene eseguita tramite una connessione TDM (Time Division Multiplexing), sono disponibili uno o più gateway PSTN per la distribuzione. Se la connessione avviene tramite un trunk SIP, non è necessario un gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="2614b-p105">If the connection to the public switched telephone network (PSTN) or private branch exchange (PBX) is by means of a Time Division Multiplexing (TDM) connection, one or more PSTN gateways are available for deployment. (If the connection is by means of a SIP trunk, a PSTN gateway is not required.)</span></span>

</div>

<div>

## <a name="power-network-or-telephone-service-outages"></a><span data-ttu-id="2614b-129">Interruzioni dell'alimentazione, della rete o del servizio telefonico</span><span class="sxs-lookup"><span data-stu-id="2614b-129">Power, Network, or Telephone Service Outages</span></span>

<span data-ttu-id="2614b-130">Se si verifica un'interruzione, un disturbo o un degrado di altro tipo dei servizi di alimentazione, rete o telefono in una posizione, la voce, la messaggistica istantanea, la presenza e altre caratteristiche di Lync Server e qualsiasi dispositivo connesso a Lync Server potrebbero non funzionare correttamente.</span><span class="sxs-lookup"><span data-stu-id="2614b-130">If there is an outage, disruption, or other degradation of the power, network, or telephone services at your location, the voice, instant messaging, presence, and other features of Lync Server and any device connected to Lync Server may not work properly.</span></span>

</div>

<div>

## <a name="enterprise-voice-depends-on-server-availability-and-voice-client-and-hardware-operability"></a><span data-ttu-id="2614b-131">VoIP aziendale dipende dalla disponibilità del server e dall'operatività hardware e dei client vocali</span><span class="sxs-lookup"><span data-stu-id="2614b-131">Enterprise Voice Depends on Server Availability and Voice Client and Hardware Operability</span></span>

<span data-ttu-id="2614b-132">Le comunicazioni vocali con Lync Server dipendono dalla disponibilità del software del server e dal corretto funzionamento dei client vocali o dei dispositivi telefonici hardware che si connettono al software del server.</span><span class="sxs-lookup"><span data-stu-id="2614b-132">Voice communications with Lync Server depend upon the availability of the server software and the proper functioning of the voice clients or the hardware phone devices connecting to the server software.</span></span>

</div>

<div>

## <a name="alternative-means-of-accessing-emergency-services"></a><span data-ttu-id="2614b-133">Metodi alternativi di accesso ai servizi di emergenza</span><span class="sxs-lookup"><span data-stu-id="2614b-133">Alternative Means of Accessing Emergency Services</span></span>

<span data-ttu-id="2614b-134">Per le posizioni in cui si installa un client vocale, ad esempio un PC che esegue Lync client o un dispositivo Lync Phone Edition, si consiglia di mantenere un'opzione di backup per consentire agli utenti di chiamare i servizi di emergenza (ad esempio, 911 o 999) in caso di errore di alimentazione , riduzione della connettività di rete, interruzione del servizio telefonico o altro problema che può inibire il funzionamento dei dispositivi Lync Server, Lync o Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="2614b-134">For those locations where you install a voice client (for example, a PC running Lync client or an Lync Phone Edition device), we recommend that you maintain a backup option for users to call emergency services (for example, 911 or 999) in case of a power failure, network connectivity degradation, telephone service outage, or other issue that may inhibit operation of Lync Server, Lync, or Lync Phone Edition devices.</span></span> <span data-ttu-id="2614b-135">Tali opzioni alternative possono includere un telefono connesso a una linea PSTN (Public Switched Telephone Network) standard o un telefono cellulare.</span><span class="sxs-lookup"><span data-stu-id="2614b-135">Such alternative options could include a telephone connected to a standard public switched telephone network line or a cell phone.</span></span>

</div>

<div>

## <a name="emergency-calls-and-multi-line-telephone-systems"></a><span data-ttu-id="2614b-136">Chiamate di emergenza e sistemi telefonici multilinea</span><span class="sxs-lookup"><span data-stu-id="2614b-136">Emergency Calls and Multi-Line Telephone Systems</span></span>

<span data-ttu-id="2614b-137">L'utilizzo di un sistema telefonico multilinea (MTLS, Multiline Telephone System) può essere soggetto alle leggi statali e/o federali degli Stati Uniti e di altri paesi che obbligano a mostrare in chiaro ai servizi di emergenza il numero di telefono, l'interno e/o la località del chiamante quando quest'ultimo effettua una chiamata di emergenza (ad esempio, il 113).</span><span class="sxs-lookup"><span data-stu-id="2614b-137">The use of a multiline telephone system (MLTS) may be subject to U.S state or federal laws or the laws of other countries/regions that require the MLTS to provide a caller’s telephone number, extension, and/or physical location to applicable emergency services when a caller is placed to emergency services (for example, when dialing an emergency access number such as 911 or 999).</span></span> <span data-ttu-id="2614b-138">In questa versione, Lync Server può essere configurato in modo da fornire la posizione fisica del chiamante a un provider di servizi di emergenza, come descritto in [Planning for Emergency Services (E9-1-1) in Lync server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span><span class="sxs-lookup"><span data-stu-id="2614b-138">In this release, Lync Server can be configured to provide a caller’s physical location to an emergency services provider, as described in [Planning for emergency services (E9-1-1) in Lync Server 2013](lync-server-2013-planning-for-emergency-services-e9-1-1.md).</span></span> <span data-ttu-id="2614b-139">La conformità con le leggi di MLTS è l'unica responsabilità dell'acquirente dei dispositivi Lync Server, Lync client e Lync Phone Edition.</span><span class="sxs-lookup"><span data-stu-id="2614b-139">Compliance with MLTS laws is the sole responsibility of the purchaser of Lync Server, Lync client, and Lync Phone Edition devices.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

