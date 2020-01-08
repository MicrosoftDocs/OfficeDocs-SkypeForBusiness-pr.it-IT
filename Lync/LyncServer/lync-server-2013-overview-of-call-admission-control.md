---
title: 'Lync Server 2013: Panoramica del controllo di ammissione alle chiamate'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cba1a83ce64fa575cf5de724d5dd215fcb459c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976196"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="3a9c8-102">Panoramica del controllo di ammissione alle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3a9c8-102">Overview of call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3a9c8-103">_**Argomento Ultima modifica:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="3a9c8-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="3a9c8-104">Le comunicazioni in tempo reale sono sensibili alla latenza e alla perdita di pacchetti che possono verificarsi nelle reti congestionate.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-104">Real-time communications are sensitive to the latency and packet loss that can occur on congested networks.</span></span> <span data-ttu-id="3a9c8-105">Il controllo di ammissione di chiamata (CAC) determina, in base alla larghezza di banda della rete disponibile, se consentire la creazione di sessioni di comunicazioni in tempo reale, ad esempio chiamate vocali o videochiamate.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-105">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="3a9c8-106">La progettazione CAC in Lync Server 2013 offre quattro attributi principali:</span><span class="sxs-lookup"><span data-stu-id="3a9c8-106">The CAC design in Lync Server 2013 offers four main attributes:</span></span>

  - <span data-ttu-id="3a9c8-107">È semplice eseguire la distribuzione e la gestione senza richiedere ulteriori dispositivi, ad esempio router appositamente configurati.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-107">It is simple to deploy and manage without requiring additional equipment, such as specially configured routers.</span></span>

  - <span data-ttu-id="3a9c8-108">Risolve i casi di utilizzo delle comunicazioni unificate critiche, ad esempio utenti mobili e più punti di presenza.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-108">It addresses critical unified communications use cases, such as roaming users and multiple points of presence.</span></span> <span data-ttu-id="3a9c8-109">I criteri di CAC vengono applicati in base al punto in cui si trova l'endpoint, non in cui è ospitato l'utente.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-109">CAC policies are enforced according to where the endpoint is located, not where the user is homed.</span></span>

  - <span data-ttu-id="3a9c8-110">Oltre alle chiamate vocali, può essere applicato ad altri traffici, ad esempio videochiamate e sessioni di conferenze audio/video.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-110">In addition to voice calls, it can be applied to other traffic, such as video calls and audio/video conferencing sessions.</span></span>

  - <span data-ttu-id="3a9c8-111">Offre la flessibilità necessaria per consentire la rappresentazione di vari tipi di topologie di rete.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-111">Provides the flexibility to enable representation of various kinds of network topologies.</span></span> <span data-ttu-id="3a9c8-112">Per gli esempi, vedere [componenti e topologie per CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="3a9c8-112">For examples, see [Components and topologies for CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span></span>

<span data-ttu-id="3a9c8-113">Se una nuova sessione vocale o video supera i limiti di larghezza di banda impostati in un collegamento WAN, la sessione viene bloccata oppure (solo per le chiamate telefoniche) viene reinstradata alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-113">If a new voice or video session exceeds the bandwidth limits that you have set on a WAN link, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>

<span data-ttu-id="3a9c8-114">CAC controlla il traffico in tempo reale solo per voce e video.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-114">CAC controls real-time traffic for voice and video only.</span></span> <span data-ttu-id="3a9c8-115">Non controlla il traffico dati.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-115">It does not control data traffic.</span></span>

<span data-ttu-id="3a9c8-116">Gli amministratori definiscono i criteri di CAC, applicati dal servizio dei criteri di larghezza di banda installato con ogni pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-116">Administrators define CAC policies, which are enforced by the Bandwidth Policy Service that is installed with every Front End pool.</span></span> <span data-ttu-id="3a9c8-117">Le impostazioni di CAC vengono propagate automaticamente a tutti i server front-end di Lync in rete.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-117">CAC settings are automatically propagated to all Lync Server Front End Servers in your network.</span></span>

<span data-ttu-id="3a9c8-118">Per le chiamate che non riescono a causa di criteri di CAC, l'ordine di precedenza per il reinstradamento della chiamata è il seguente:</span><span class="sxs-lookup"><span data-stu-id="3a9c8-118">For calls that fail because of CAC policies, the order of precedence for rerouting the call is as follows:</span></span>

1.  <span data-ttu-id="3a9c8-119">Internet</span><span class="sxs-lookup"><span data-stu-id="3a9c8-119">Internet</span></span>

2.  <span data-ttu-id="3a9c8-120">PSTN</span><span class="sxs-lookup"><span data-stu-id="3a9c8-120">PSTN</span></span>

3.  <span data-ttu-id="3a9c8-121">Segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="3a9c8-121">Voice mail</span></span>

<span data-ttu-id="3a9c8-122">La registrazione dei dettagli delle chiamate (CDR) acquisisce informazioni sulle chiamate reinstradate alla rete PSTN o alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-122">Call detail recording (CDR) captures information about calls that are rerouted to the PSTN or to voice mail.</span></span> <span data-ttu-id="3a9c8-123">CDR non acquisisce informazioni sulle chiamate reinstradate a Internet, poiché Internet viene considerato come percorso alternativo anziché come opzione secondaria.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-123">CDR does not capture information about calls that are rerouted to the Internet, because the Internet is treated as an alternate path rather than a secondary option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3a9c8-124">I depositi della segreteria telefonica non verranno negati a causa di vincoli di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-124">Voice mail deposits will not be denied because of bandwidth constraints.</span></span>



</div>

<span data-ttu-id="3a9c8-125">Il servizio criteri di larghezza di banda genera due tipi di file di log in formato CSV (comma separated values).</span><span class="sxs-lookup"><span data-stu-id="3a9c8-125">The Bandwidth Policy Service generates two types of log files in comma separated values (CSV) format.</span></span> <span data-ttu-id="3a9c8-126">Il file di log degli **errori di controllo** acquisisce informazioni quando le richieste di larghezza di banda vengono negate.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-126">The **check failures** log file captures information when bandwidth requests are denied.</span></span> <span data-ttu-id="3a9c8-127">Il file di log di **utilizzo del collegamento** acquisisce uno snapshot della topologia di rete e dell'utilizzo della larghezza di banda dei collegamenti WAN.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-127">The **link utilization** log file captures a snapshot of the network topology and the WAN link bandwidth utilization.</span></span> <span data-ttu-id="3a9c8-128">Entrambi i file di log possono aiutarti a ottimizzare i criteri di CAC in base all'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-128">Both of these log files can assist you in fine-tuning your CAC policies based on utilization.</span></span>

<div>

## <a name="call-admission-control-considerations"></a><span data-ttu-id="3a9c8-129">Considerazioni sul controllo dell'ammissione alle chiamate</span><span class="sxs-lookup"><span data-stu-id="3a9c8-129">Call Admission Control Considerations</span></span>

<span data-ttu-id="3a9c8-130">L'amministratore seleziona per installare il servizio criteri di larghezza di banda nel primo pool configurato nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-130">The administrator selects to install the Bandwidth Policy Service on the first pool configured in the central site.</span></span> <span data-ttu-id="3a9c8-131">Poiché esiste un unico sito centrale per ogni area di rete, esiste un solo servizio per i criteri di larghezza di banda per ogni area di rete, che gestisce i criteri di larghezza di banda per l'area geografica, i siti associati e i collegamenti a tali siti.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-131">Since there is a single central site per network region, there is only one Bandwidth Policy Service per network region, which manages bandwidth policy for that region, its associated sites and the links to those sites.</span></span> <span data-ttu-id="3a9c8-132">Il servizio criteri di larghezza di banda viene eseguito come parte dei server front-end e quindi la disponibilità elevata è incorporata all'interno di tale pool.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-132">The Bandwidth Policy Service runs as part of the Front End Servers, and therefore high availability is built-in within that pool.</span></span> <span data-ttu-id="3a9c8-133">Il servizio criteri di larghezza di banda eseguito in ogni server front-end viene sincronizzato ogni 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-133">The Bandwidth Policy Service running on each Front End Server synchronizes every 15 seconds.</span></span> <span data-ttu-id="3a9c8-134">Se il pool Front-end non riesce, i criteri di CAC non vengono più applicati per il sito fino al pool Front-end e di conseguenza il servizio dei criteri di larghezza di banda diventa operativo.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-134">If the Front End pool fails, CAC policies are no longer enforced for that site until the Front End pool and consequently the Bandwidth Policy Service becomes operational again.</span></span> <span data-ttu-id="3a9c8-135">Questo implica che tutte le chiamate verranno effettuate per tutta la durata del servizio per i criteri di larghezza di banda fuori servizio.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-135">This implies that all calls will go through for the duration the Bandwidth Policy Service is out of service.</span></span> <span data-ttu-id="3a9c8-136">È quindi possibile che l'oversubscription della larghezza di banda dei collegamenti durante questo periodo</span><span class="sxs-lookup"><span data-stu-id="3a9c8-136">Therefore there is the possibility of bandwidth oversubscription of your links during this period</span></span>

<span data-ttu-id="3a9c8-137">Il servizio criteri di larghezza di banda offre una disponibilità elevata all'interno di un pool Front End; Tuttavia, non offre ridondanza nei pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-137">The Bandwidth Policy Service provides high availability within a Front End pool; however, it does not provide redundancy across Front End pools.</span></span> <span data-ttu-id="3a9c8-138">Il servizio criteri di larghezza di banda non può eseguire il failover da un pool Front-end a un altro.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-138">The Bandwidth Policy Service cannot failover from one Front End pool to another.</span></span> <span data-ttu-id="3a9c8-139">Una volta ripristinato il servizio al pool Front-End, il servizio criteri di larghezza di banda viene ripreso e può applicare di nuovo i controlli dei criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-139">Once service to the Front End pool is restored, the Bandwidth Policy Service is resumed and can enforce bandwidth policy checks again.</span></span>

<div>

## <a name="network-considerations"></a><span data-ttu-id="3a9c8-140">Considerazioni sulla rete</span><span class="sxs-lookup"><span data-stu-id="3a9c8-140">Network Considerations</span></span>

<span data-ttu-id="3a9c8-141">Anche se la restrizione della larghezza di banda per l'audio e il video viene applicata dal servizio criteri di larghezza di banda in Lync Server 2013, questa restrizione non viene applicata al router di rete (Layer 2 e 3).</span><span class="sxs-lookup"><span data-stu-id="3a9c8-141">Although bandwidth restriction for audio and video is enforced by the Bandwidth Policy Service in Lync Server 2013, this restriction is not enforced at the network router (layer 2 and 3).</span></span> <span data-ttu-id="3a9c8-142">Lync Server 2010 CAC non può impedire a un'applicazione dati, ad esempio, di consumare l'intera larghezza di banda della rete su un collegamento WAN, inclusa la larghezza di banda riservata per l'audio e il video in base ai criteri di CAC.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-142">Lync Server 2010 CAC cannot prevent a data application, for example, from consuming the entire network bandwidth on a WAN link, including the bandwidth that is reserved for audio and video by your CAC policy.</span></span> <span data-ttu-id="3a9c8-143">Per proteggere la larghezza di banda necessaria nella rete, è possibile distribuire un protocollo QoS (Quality of Service), ad esempio servizi differenziati (DiffServ).</span><span class="sxs-lookup"><span data-stu-id="3a9c8-143">To protect the necessary bandwidth on your network, you can deploy a Quality of Service (QoS) protocol such as Differentiated Services (DiffServ).</span></span> <span data-ttu-id="3a9c8-144">Una procedura consigliata consiste quindi nel coordinare i criteri di larghezza di banda CAC definiti con le impostazioni QoS eventualmente distribuite.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-144">Therefore, a best practice is to coordinate the CAC bandwidth policies you define with any QoS settings that you might deploy.</span></span>

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a><span data-ttu-id="3a9c8-145">Percorsi multimediali e di segnalazione su VPN</span><span class="sxs-lookup"><span data-stu-id="3a9c8-145">Media and Signaling Paths over VPN</span></span>

<span data-ttu-id="3a9c8-146">Se l'organizzazione supporta i contenuti multimediali tramite VPN, verificare che sia il flusso multimediale che il flusso di segnalazione passano attraverso la rete VPN oppure vengono instradati attraverso Internet.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-146">If your enterprise supports media through VPN, ensure that either both the media stream and the signaling stream go through the VPN or both are routed through the internet.</span></span> <span data-ttu-id="3a9c8-147">Per impostazione predefinita, i flussi di elementi multimediali e di segnalazione passano attraverso il tunnel VPN.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-147">By default, the media and signaling streams go through the VPN tunnel.</span></span>

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a><span data-ttu-id="3a9c8-148">Controllo dell'ammissione delle chiamate degli utenti esterni</span><span class="sxs-lookup"><span data-stu-id="3a9c8-148">Call Admission Control of Outside Users</span></span>

<span data-ttu-id="3a9c8-149">Il controllo di ammissione alle chiamate non viene applicato per gli utenti remoti in cui il traffico di rete scorre su Internet.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-149">Call admission control is not enforced for remote users where the network traffic flows through the Internet.</span></span> <span data-ttu-id="3a9c8-150">Poiché il traffico multimediale sta attraversando Internet, che non è gestito da Lync Server, non è possibile applicare CAC.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-150">Because the media traffic is traversing the Internet, which is not managed by Lync Server, CAC cannot be applied.</span></span> <span data-ttu-id="3a9c8-151">I controlli CAC verranno eseguiti, tuttavia, nella parte della chiamata che scorre attraverso la rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-151">CAC checks will be performed, however, on the portion of the call that flows through the enterprise network.</span></span>

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a><span data-ttu-id="3a9c8-152">Controllo ammissione chiamata delle connessioni PSTN</span><span class="sxs-lookup"><span data-stu-id="3a9c8-152">Call Admission Control of PSTN Connections</span></span>

<span data-ttu-id="3a9c8-153">Il controllo di ammissione delle chiamate è impostabile sul server Mediation indipendentemente dal fatto che sia connesso a un IP/PBX, a un gateway PSTN o a un trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-153">Call admission control is enforceable on the Mediation Server regardless of whether it is connected to an IP/PBX, a PSTN gateway, or a SIP trunk.</span></span> <span data-ttu-id="3a9c8-154">Poiché il Mediation Server è un agente utente back-to-back (B2BUA), termina media.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-154">Because the Mediation Server is a back-to-back user agent (B2BUA), it terminates media.</span></span> <span data-ttu-id="3a9c8-155">Ha due lati di connessione: un lato connesso a Lync Server e un lato del gateway, che è connesso a gateway PSTN, IP/PBX o trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-155">It has two connection sides: a side that is connected to Lync Server and a gateway side, which is connected to PSTN gateways, IP/PBXs, or SIP trunks.</span></span> <span data-ttu-id="3a9c8-156">Per informazioni dettagliate sulle connessioni PSTN, vedere [pianificazione della connettività PSTN in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="3a9c8-156">For details about PSTN connections, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span></span>

<span data-ttu-id="3a9c8-157">CAC può essere applicato su entrambi i lati del Mediation Server, a meno che non sia abilitato il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-157">CAC can be enforced on both sides of the Mediation Server unless media bypass is enabled.</span></span> <span data-ttu-id="3a9c8-158">Se il bypass multimediale è abilitato, il traffico multimediale non attraversa il Mediation Server, bensì fluisce direttamente tra il client Lync e il gateway.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-158">If media bypass is enabled, the media traffic doesn’t traverse the Mediation Server but instead flows directly between the Lync client and the gateway.</span></span> <span data-ttu-id="3a9c8-159">In questo caso, CAC non è necessario.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-159">In this case, CAC is not needed.</span></span> <span data-ttu-id="3a9c8-160">Per informazioni dettagliate, vedere [pianificazione di un bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="3a9c8-160">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span></span>

<span data-ttu-id="3a9c8-161">Nella figura seguente viene illustrato il modo in cui CAC viene applicato alle connessioni PSTN con e senza bypass multimediale abilitato.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-161">The following figure illustrates how CAC is enforced on PSTN connections with and without media bypass enabled.</span></span>

<span data-ttu-id="3a9c8-162">**Applicazione controllo ammissione chiamata sulle connessioni alla rete PSTN**</span><span class="sxs-lookup"><span data-stu-id="3a9c8-162">**Call admission control enforcement on connections to the PSTN**</span></span>

<span data-ttu-id="3a9c8-163">![Voice CAC media bypass connessione](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "voce CAC media bypass") per l'applicazione della connessione</span><span class="sxs-lookup"><span data-stu-id="3a9c8-163">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a><span data-ttu-id="3a9c8-164">Compatibilità del controllo di ammissione alle chiamate con versioni precedenti di Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="3a9c8-164">Compatibility of Call Admission Control with Earlier Versions of Office Communications Server</span></span>

<span data-ttu-id="3a9c8-165">Il controllo di ammissione delle chiamate può essere abilitato solo sugli endpoint abilitati per Lync Server 2010 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-165">Call admission control can be enabled only on endpoints that are enabled for Lync Server 2010 and later.</span></span>

<span data-ttu-id="3a9c8-166">Non è possibile abilitare il controllo ammissione chiamata in endpoint con Office Communicator 2007 R2 o versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="3a9c8-166">Call admission control cannot be enabled on endpoints running Office Communicator 2007 R2 or earlier.</span></span>

<span data-ttu-id="3a9c8-167">**Applicazione di CAC in diverse versioni di Lync Server**</span><span class="sxs-lookup"><span data-stu-id="3a9c8-167">**Application of CAC on different Lync Server versions**</span></span>

<span data-ttu-id="3a9c8-168">Diagramma di(images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Confronto versioni Voice") ![CAC]</span><span class="sxs-lookup"><span data-stu-id="3a9c8-168">![Voice CAC Version Comparison diagram](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Voice CAC Version Comparison diagram")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

