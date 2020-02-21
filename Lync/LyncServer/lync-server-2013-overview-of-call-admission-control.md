---
title: 'Lync Server 2013: Panoramica del controllo di ammissione di chiamata'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df9d65a56a8e2ed398dc5277045efeaaf68b8f58
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216422"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="17cb5-102">Panoramica del controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="17cb5-102">Overview of call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="17cb5-103">_**Ultimo argomento modificato:** 2012-09-22_</span><span class="sxs-lookup"><span data-stu-id="17cb5-103">_**Topic Last Modified:** 2012-09-22_</span></span>

<span data-ttu-id="17cb5-104">Le comunicazioni in tempo reale sono sensibili alla latenza e alla perdita di pacchetti che possono verificarsi in reti congestionate.</span><span class="sxs-lookup"><span data-stu-id="17cb5-104">Real-time communications are sensitive to the latency and packet loss that can occur on congested networks.</span></span> <span data-ttu-id="17cb5-105">Il controllo di ammissione di chiamata determina, in base alla larghezza di banda disponibile, se consentire di stabilire sessioni di comunicazione in tempo reale, ad esempio chiamate vocali o videochiamate.</span><span class="sxs-lookup"><span data-stu-id="17cb5-105">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="17cb5-106">La progettazione del servizio di controllo di ammissione in Lync Server 2013 offre quattro attributi principali:</span><span class="sxs-lookup"><span data-stu-id="17cb5-106">The CAC design in Lync Server 2013 offers four main attributes:</span></span>

  - <span data-ttu-id="17cb5-107">È semplice da distribuire e gestire senza richiedere apparecchiature aggiuntive, ad esempio router configurati in modo speciale.</span><span class="sxs-lookup"><span data-stu-id="17cb5-107">It is simple to deploy and manage without requiring additional equipment, such as specially configured routers.</span></span>

  - <span data-ttu-id="17cb5-p102">Consente di risolvere casi critici di utilizzo delle comunicazioni unificate, ad esempio relativi a utenti mobili e a più punti di presenza. I criteri di controllo di ammissione di chiamata vengono applicati in base alla posizione dell'endpoint e non a quella in cui risiede l'utente.</span><span class="sxs-lookup"><span data-stu-id="17cb5-p102">It addresses critical unified communications use cases, such as roaming users and multiple points of presence. CAC policies are enforced according to where the endpoint is located, not where the user is homed.</span></span>

  - <span data-ttu-id="17cb5-110">Oltre alle chiamate vocali, può essere applicato ad altro traffico, ad esempio alle videochiamate e alle sessioni di conferenza audio/video.</span><span class="sxs-lookup"><span data-stu-id="17cb5-110">In addition to voice calls, it can be applied to other traffic, such as video calls and audio/video conferencing sessions.</span></span>

  - <span data-ttu-id="17cb5-111">Offre la flessibilità necessaria per consentire la rappresentazione di diversi tipi di topologie di rete.</span><span class="sxs-lookup"><span data-stu-id="17cb5-111">Provides the flexibility to enable representation of various kinds of network topologies.</span></span> <span data-ttu-id="17cb5-112">Per alcuni esempi, vedere [componenti e topologie per il servizio di controllo di ammissione in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span><span class="sxs-lookup"><span data-stu-id="17cb5-112">For examples, see [Components and topologies for CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).</span></span>

<span data-ttu-id="17cb5-113">Se una nuova sessione vocale o video supera i limiti di larghezza di banda impostati in un collegamento WAN, la sessione viene bloccata (solo per le chiamate telefoniche) o reinstradata alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="17cb5-113">If a new voice or video session exceeds the bandwidth limits that you have set on a WAN link, the session is either blocked or (for phone calls only) rerouted to the PSTN.</span></span>

<span data-ttu-id="17cb5-p104">Il controllo di ammissione di chiamata controlla solo il traffico audio e video in tempo reale, ma non il traffico di dati.</span><span class="sxs-lookup"><span data-stu-id="17cb5-p104">CAC controls real-time traffic for voice and video only. It does not control data traffic.</span></span>

<span data-ttu-id="17cb5-116">Gli amministratori definiscono i criteri di CAC, applicati dal servizio criteri di larghezza di banda installato con tutti i pool Front end.</span><span class="sxs-lookup"><span data-stu-id="17cb5-116">Administrators define CAC policies, which are enforced by the Bandwidth Policy Service that is installed with every Front End pool.</span></span> <span data-ttu-id="17cb5-117">Le impostazioni del servizio di controllo di ammissione vengono propagate automaticamente a tutti i server front end di Lync Server della rete.</span><span class="sxs-lookup"><span data-stu-id="17cb5-117">CAC settings are automatically propagated to all Lync Server Front End Servers in your network.</span></span>

<span data-ttu-id="17cb5-118">Per le chiamate non riuscite a causa di criteri di controllo di ammissione di chiamata, l'ordine di precedenza per il rerouting della chiamata è il seguente:</span><span class="sxs-lookup"><span data-stu-id="17cb5-118">For calls that fail because of CAC policies, the order of precedence for rerouting the call is as follows:</span></span>

1.  <span data-ttu-id="17cb5-119">Internet</span><span class="sxs-lookup"><span data-stu-id="17cb5-119">Internet</span></span>

2.  <span data-ttu-id="17cb5-120">PSTN</span><span class="sxs-lookup"><span data-stu-id="17cb5-120">PSTN</span></span>

3.  <span data-ttu-id="17cb5-121">Segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="17cb5-121">Voice mail</span></span>

<span data-ttu-id="17cb5-p106">Tramite la registrazione dettagli chiamata (CDR) vengono acquisite informazioni sulle chiamate reinstradate alla rete PSTN o alla segreteria telefonica. CDR non consente l'acquisizione di informazioni sulle chiamate reinstradate a Internet, perché Internet viene considerato un percorso alternativo anziché un'opzione secondaria.</span><span class="sxs-lookup"><span data-stu-id="17cb5-p106">Call detail recording (CDR) captures information about calls that are rerouted to the PSTN or to voice mail. CDR does not capture information about calls that are rerouted to the Internet, because the Internet is treated as an alternate path rather than a secondary option.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="17cb5-124">L'archiviazione nella segreteria telefonica non viene negata a causa di vincoli di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="17cb5-124">Voice mail deposits will not be denied because of bandwidth constraints.</span></span>



</div>

<span data-ttu-id="17cb5-p107">Il servizio criteri di larghezza di banda genera due tipi di file di registro in formato con valori separati da virgole (CSV). Nel file di registro degli **errori di verifica** vengono acquisite informazioni quando vengono negate richieste di larghezza di banda. Nel file di registro dell'**utilizzo dei collegamenti** viene acquisita un'istantanea dell'utilizzo della larghezza di banda della topologia di rete e del collegamento WAN. Entrambi questi file di registro possono semplificare l'ottimizzazione dei criteri di controllo di ammissione di chiamata in base all'utilizzo.</span><span class="sxs-lookup"><span data-stu-id="17cb5-p107">The Bandwidth Policy Service generates two types of log files in comma separated values (CSV) format. The **check failures** log file captures information when bandwidth requests are denied. The **link utilization** log file captures a snapshot of the network topology and the WAN link bandwidth utilization. Both of these log files can assist you in fine-tuning your CAC policies based on utilization.</span></span>

<div>

## <a name="call-admission-control-considerations"></a><span data-ttu-id="17cb5-129">Considerazioni relative al controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="17cb5-129">Call Admission Control Considerations</span></span>

<span data-ttu-id="17cb5-130">L'amministratore seleziona per installare il servizio criteri di larghezza di banda sul primo pool configurato nel sito centrale.</span><span class="sxs-lookup"><span data-stu-id="17cb5-130">The administrator selects to install the Bandwidth Policy Service on the first pool configured in the central site.</span></span> <span data-ttu-id="17cb5-131">Poiché è presente un unico sito centrale per ogni area di rete, è presente un solo servizio criteri di larghezza di banda per ogni area di rete, che consente di gestire i criteri di larghezza di banda per tale area, i siti associati e i collegamenti a tali siti.</span><span class="sxs-lookup"><span data-stu-id="17cb5-131">Since there is a single central site per network region, there is only one Bandwidth Policy Service per network region, which manages bandwidth policy for that region, its associated sites and the links to those sites.</span></span> <span data-ttu-id="17cb5-132">Il servizio criteri di larghezza di banda viene eseguito come parte dei front end server e quindi la disponibilità elevata è incorporata all'interno di tale pool.</span><span class="sxs-lookup"><span data-stu-id="17cb5-132">The Bandwidth Policy Service runs as part of the Front End Servers, and therefore high availability is built-in within that pool.</span></span> <span data-ttu-id="17cb5-133">Il servizio dei criteri di larghezza di banda in esecuzione su ogni Front End Server Sincronizza ogni 15 secondi.</span><span class="sxs-lookup"><span data-stu-id="17cb5-133">The Bandwidth Policy Service running on each Front End Server synchronizes every 15 seconds.</span></span> <span data-ttu-id="17cb5-134">Se il pool Front End ha esito negativo, i criteri di CAC non vengono più applicati per il sito fino a quando il pool Front end e di conseguenza il servizio criteri di larghezza di banda diventeranno di nuovo operativi.</span><span class="sxs-lookup"><span data-stu-id="17cb5-134">If the Front End pool fails, CAC policies are no longer enforced for that site until the Front End pool and consequently the Bandwidth Policy Service becomes operational again.</span></span> <span data-ttu-id="17cb5-135">Questo implica che tutte le chiamate passeranno per la durata del servizio dei criteri di larghezza di banda non è in servizio.</span><span class="sxs-lookup"><span data-stu-id="17cb5-135">This implies that all calls will go through for the duration the Bandwidth Policy Service is out of service.</span></span> <span data-ttu-id="17cb5-136">Vi è pertanto la possibilità di oversubscription della larghezza di banda dei collegamenti durante questo periodo</span><span class="sxs-lookup"><span data-stu-id="17cb5-136">Therefore there is the possibility of bandwidth oversubscription of your links during this period</span></span>

<span data-ttu-id="17cb5-137">Il servizio criteri di larghezza di banda garantisce una disponibilità elevata all'interno di un pool Front end. Tuttavia, non fornisce la ridondanza nei pool Front end.</span><span class="sxs-lookup"><span data-stu-id="17cb5-137">The Bandwidth Policy Service provides high availability within a Front End pool; however, it does not provide redundancy across Front End pools.</span></span> <span data-ttu-id="17cb5-138">Il servizio criteri di larghezza di banda non può eseguire il failover da un pool Front end a un altro.</span><span class="sxs-lookup"><span data-stu-id="17cb5-138">The Bandwidth Policy Service cannot failover from one Front End pool to another.</span></span> <span data-ttu-id="17cb5-139">Dopo il ripristino del servizio per il pool Front End, il servizio criteri di larghezza di banda viene ripristinato e può applicare di nuovo i controlli dei criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="17cb5-139">Once service to the Front End pool is restored, the Bandwidth Policy Service is resumed and can enforce bandwidth policy checks again.</span></span>

<div>

## <a name="network-considerations"></a><span data-ttu-id="17cb5-140">Considerazioni sulla rete</span><span class="sxs-lookup"><span data-stu-id="17cb5-140">Network Considerations</span></span>

<span data-ttu-id="17cb5-141">Anche se la limitazione della larghezza di banda per l'audio e il video viene applicata dal servizio criteri di larghezza di banda in Lync Server 2013, questa restrizione non viene applicata al router di rete (Layer 2 e 3).</span><span class="sxs-lookup"><span data-stu-id="17cb5-141">Although bandwidth restriction for audio and video is enforced by the Bandwidth Policy Service in Lync Server 2013, this restriction is not enforced at the network router (layer 2 and 3).</span></span> <span data-ttu-id="17cb5-142">Lync Server 2010 CAC non è in grado di impedire l'utilizzo dell'intera larghezza di banda della rete su un collegamento WAN, inclusa la larghezza di banda riservata per audio e video da parte del criterio di controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="17cb5-142">Lync Server 2010 CAC cannot prevent a data application, for example, from consuming the entire network bandwidth on a WAN link, including the bandwidth that is reserved for audio and video by your CAC policy.</span></span> <span data-ttu-id="17cb5-143">Per proteggere la larghezza di banda necessaria per la rete, è possibile distribuire un protocollo QoS (Quality of Service), ad esempio servizi differenziati (DiffServ).</span><span class="sxs-lookup"><span data-stu-id="17cb5-143">To protect the necessary bandwidth on your network, you can deploy a Quality of Service (QoS) protocol such as Differentiated Services (DiffServ).</span></span> <span data-ttu-id="17cb5-144">Pertanto, una procedura consigliata consiste nel coordinare i criteri di larghezza di banda di CAC definiti con eventuali impostazioni QoS che è possibile distribuire.</span><span class="sxs-lookup"><span data-stu-id="17cb5-144">Therefore, a best practice is to coordinate the CAC bandwidth policies you define with any QoS settings that you might deploy.</span></span>

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a><span data-ttu-id="17cb5-145">Percorsi di contenuti multimediali e segnali su VPN</span><span class="sxs-lookup"><span data-stu-id="17cb5-145">Media and Signaling Paths over VPN</span></span>

<span data-ttu-id="17cb5-p111">Se l'organizzazione supporta contenuto multimediale tramite VPN, verificare che il flusso multimediale e il flusso dei segnali attraversino la rete VPN o che venga eseguito il routing di entrambi tramite internet. Per impostazione predefinita, i flussi multimediali e dei segnali passano attraverso il tunnel VPN.</span><span class="sxs-lookup"><span data-stu-id="17cb5-p111">If your enterprise supports media through VPN, ensure that either both the media stream and the signaling stream go through the VPN or both are routed through the internet. By default, the media and signaling streams go through the VPN tunnel.</span></span>

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a><span data-ttu-id="17cb5-148">Controllo di ammissione di chiamata di utenti esterni</span><span class="sxs-lookup"><span data-stu-id="17cb5-148">Call Admission Control of Outside Users</span></span>

<span data-ttu-id="17cb5-149">Il controllo di ammissione di chiamata non viene applicato per utenti remoti nei casi in cui il flusso del traffico di rete viene eseguito tramite Internet.</span><span class="sxs-lookup"><span data-stu-id="17cb5-149">Call admission control is not enforced for remote users where the network traffic flows through the Internet.</span></span> <span data-ttu-id="17cb5-150">Poiché il traffico multimediale attraversa Internet, che non è gestito da Lync Server, non è possibile applicare il servizio di controllo di accesso.</span><span class="sxs-lookup"><span data-stu-id="17cb5-150">Because the media traffic is traversing the Internet, which is not managed by Lync Server, CAC cannot be applied.</span></span> <span data-ttu-id="17cb5-151">Tali controlli verranno tuttavia eseguiti sulla parte della chiamata il cui flusso attraversa la rete aziendale.</span><span class="sxs-lookup"><span data-stu-id="17cb5-151">CAC checks will be performed, however, on the portion of the call that flows through the enterprise network.</span></span>

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a><span data-ttu-id="17cb5-152">Controllo di ammissione di chiamata di connessioni PSTN</span><span class="sxs-lookup"><span data-stu-id="17cb5-152">Call Admission Control of PSTN Connections</span></span>

<span data-ttu-id="17cb5-153">Il controllo di ammissione di chiamata è applicabile sul Mediation Server, indipendentemente dal fatto che sia connesso a un IP/PBX, a un gateway PSTN o a un trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="17cb5-153">Call admission control is enforceable on the Mediation Server regardless of whether it is connected to an IP/PBX, a PSTN gateway, or a SIP trunk.</span></span> <span data-ttu-id="17cb5-154">Poiché il Mediation Server è un agente utente back-to-back (B2BUA), termina il supporto.</span><span class="sxs-lookup"><span data-stu-id="17cb5-154">Because the Mediation Server is a back-to-back user agent (B2BUA), it terminates media.</span></span> <span data-ttu-id="17cb5-155">Ha due lati di connessione: un lato connesso a Lync Server e un lato del gateway, connesso a gateway PSTN, IP/PBX o trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="17cb5-155">It has two connection sides: a side that is connected to Lync Server and a gateway side, which is connected to PSTN gateways, IP/PBXs, or SIP trunks.</span></span> <span data-ttu-id="17cb5-156">Per informazioni dettagliate sulle connessioni PSTN, vedere [Planning for PSTN Connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="17cb5-156">For details about PSTN connections, see [Planning for PSTN connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).</span></span>

<span data-ttu-id="17cb5-157">Il servizio di controllo di ammissione può essere applicato su entrambi i lati del Mediation Server, a meno che non sia abilitato il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="17cb5-157">CAC can be enforced on both sides of the Mediation Server unless media bypass is enabled.</span></span> <span data-ttu-id="17cb5-158">Se il bypass multimediale è abilitato, il traffico multimediale non attraversa il Mediation Server, ma invece scorre direttamente tra il client Lync e il gateway.</span><span class="sxs-lookup"><span data-stu-id="17cb5-158">If media bypass is enabled, the media traffic doesn’t traverse the Mediation Server but instead flows directly between the Lync client and the gateway.</span></span> <span data-ttu-id="17cb5-159">In questo caso, il controllo di ammissione di chiamata non è necessario.</span><span class="sxs-lookup"><span data-stu-id="17cb5-159">In this case, CAC is not needed.</span></span> <span data-ttu-id="17cb5-160">Per informazioni dettagliate, vedere [Planning for Media Bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="17cb5-160">For details, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).</span></span>

<span data-ttu-id="17cb5-161">Nella figura seguente viene illustrata l'applicazione di controllo di ammissione di chiamata in connessioni PSTN con o senza il bypass multimediale abilitato.</span><span class="sxs-lookup"><span data-stu-id="17cb5-161">The following figure illustrates how CAC is enforced on PSTN connections with and without media bypass enabled.</span></span>

<span data-ttu-id="17cb5-162">**Applicazione del controllo di ammissione di chiamata in connessioni alla rete PSTN**</span><span class="sxs-lookup"><span data-stu-id="17cb5-162">**Call admission control enforcement on connections to the PSTN**</span></span>

<span data-ttu-id="17cb5-163">![Controllo dell'applicazione della connessione al bypass multimediale di Voice CAC](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Controllo dell'applicazione della connessione al bypass multimediale di Voice CAC")</span><span class="sxs-lookup"><span data-stu-id="17cb5-163">![Voice CAC Media Bypass Connection Enforcement](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Voice CAC Media Bypass Connection Enforcement")</span></span>

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a><span data-ttu-id="17cb5-164">Compatibilità del controllo di ammissione di chiamata con le versioni precedenti di Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="17cb5-164">Compatibility of Call Admission Control with Earlier Versions of Office Communications Server</span></span>

<span data-ttu-id="17cb5-165">Il controllo di ammissione di chiamata può essere abilitato solo sugli endpoint abilitati per Lync Server 2010 e versioni successive.</span><span class="sxs-lookup"><span data-stu-id="17cb5-165">Call admission control can be enabled only on endpoints that are enabled for Lync Server 2010 and later.</span></span>

<span data-ttu-id="17cb5-166">Non è possibile abilitare il controllo di ammissione di chiamata sugli endpoint che eseguono Office Communicator 2007 R2 o versioni precedenti.</span><span class="sxs-lookup"><span data-stu-id="17cb5-166">Call admission control cannot be enabled on endpoints running Office Communicator 2007 R2 or earlier.</span></span>

<span data-ttu-id="17cb5-167">**Applicazione del controllo di ammissione di chiamata in versioni di Lync Server diverse**</span><span class="sxs-lookup"><span data-stu-id="17cb5-167">**Application of CAC on different Lync Server versions**</span></span>

<span data-ttu-id="17cb5-168">![Diagramma di confronto delle versioni di Voice CAC](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Diagramma di confronto delle versioni di Voice CAC")</span><span class="sxs-lookup"><span data-stu-id="17cb5-168">![Voice CAC Version Comparison diagram](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Voice CAC Version Comparison diagram")</span></span>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

