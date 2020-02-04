---
title: 'Lync Server 2013: progettare il trunk SIP per E9-1-1'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Designing the SIP trunk for E9-1-1
ms:assetid: 4f93b974-b460-45c7-a4a8-6f38e34840f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398323(v=OCS.15)
ms:contentKeyID: 48184096
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b0ca42092b33632dbc7aed84808499b13ab0843c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762514"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="designing-the-sip-trunk-for-e9-1-1-in-lync-server-2013"></a><span data-ttu-id="c989f-102">Progettazione del trunk SIP per E9-1-1 in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c989f-102">Designing the SIP trunk for E9-1-1 in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c989f-103">_**Argomento Ultima modifica:** 2012-10-03_</span><span class="sxs-lookup"><span data-stu-id="c989f-103">_**Topic Last Modified:** 2012-10-03_</span></span>

<span data-ttu-id="c989f-104">Lync Server usa trunk SIP per connettere una chiamata di emergenza al provider di servizi E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="c989f-104">Lync Server uses SIP trunks to connect an emergency call to the E9-1-1 service provider.</span></span> <span data-ttu-id="c989f-105">È possibile configurare trunk SIP per i servizi di emergenza per E9-1-1 in un sito centrale, in più siti centrali o in ogni sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="c989f-105">You can set up emergency service SIP trunks for E9-1-1 at one central site, at multiple central sites, or at each branch site.</span></span> <span data-ttu-id="c989f-106">Tuttavia, se il collegamento WAN tra il sito del chiamante e il sito che ospita il trunk SIP del servizio di emergenza non è disponibile, la chiamata effettuata da un utente nel sito disconnesso avrà bisogno di un record di utilizzo telefonico speciale nel criterio vocale dell'utente che instraderà la chiamata al ECRC tramite il gateway PSTN (Public Switched Telephone Network) locale.</span><span class="sxs-lookup"><span data-stu-id="c989f-106">However, if the WAN link between the caller’s site and the site that hosts the emergency service SIP trunk is unavailable, then a call placed by a user at the disconnected site will need a special phone usage record in the user’s voice policy that will route the call to the ECRC through the local public switched telephone network (PSTN) gateway.</span></span> <span data-ttu-id="c989f-107">Lo stesso vale se i limiti delle chiamate simultanee del controllo di ammissione di chiamata sono in vigore.</span><span class="sxs-lookup"><span data-stu-id="c989f-107">The same is true if call admission control concurrent call limits are in effect.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c989f-108">Esistono due modi per implementare un trunk SIP in un ambiente Lync Server:</span><span class="sxs-lookup"><span data-stu-id="c989f-108">There are two ways to implement a SIP trunk in a Lync Server environment:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="c989f-109">Usare i server di mediazione multihome che usano le interfacce indirizzate verso l'esterno per comunicare con il provider trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="c989f-109">Use multihomed Mediation Servers that use their outward-facing publicly-routed interfaces to communicate with the SIP trunk provider.</span></span></P>
> <LI>
> <P><span data-ttu-id="c989f-110">Usare un SBC (Session Border Controller) locale per garantire un punto di demarcazione sicuro tra i servizi Mediation Server e il provider trunk SIP.</span><span class="sxs-lookup"><span data-stu-id="c989f-110">Use an on-premises Session Border Controller (SBC) to provide a secure demarcation point between the Mediation Servers and the SIP trunk provider’s services.</span></span></P></LI></UL><span data-ttu-id="c989f-111">Se si sceglie quest'ultimo metodo, assicurarsi che la creazione e il modello SBC scelti siano stati certificati e supporti il passaggio dei dati della posizione (PIDF-LO) del formato dei dati della presenza durante il SIP INVITE.</span><span class="sxs-lookup"><span data-stu-id="c989f-111">If you choose the latter method, be sure that the SBC make and model that you choose has been certified and supports passing Presence Information Data Format Location Object (PIDF-LO) location data as part of its SIP INVITE.</span></span> <span data-ttu-id="c989f-112">In caso contrario, le chiamate arriveranno presso il provider di servizi di emergenza privato delle informazioni sulla posizione.</span><span class="sxs-lookup"><span data-stu-id="c989f-112">Otherwise, the calls will arrive at the emergency services service provider stripped of their location information.</span></span> <span data-ttu-id="c989f-113">Per informazioni dettagliate su Certified SBCs, vedere "Infrastructure qualified for Microsoft Lync <A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>" at.</span><span class="sxs-lookup"><span data-stu-id="c989f-113">For details about certified SBCs, see "Infrastructure Qualified for Microsoft Lync" at <A href="http://go.microsoft.com/fwlink/p/?linkid=248425">http://go.microsoft.com/fwlink/p/?LinkId=248425</A>.</span></span><BR><span data-ttu-id="c989f-114">I provider di servizi E9-1-1 forniscono l'accesso a una coppia di SBCs per la ridondanza.</span><span class="sxs-lookup"><span data-stu-id="c989f-114">E9-1-1 service providers supply you with access to a pair of SBCs for redundancy.</span></span> <span data-ttu-id="c989f-115">È necessario prendere diverse decisioni per quanto riguarda la topologia di Mediation Server e la configurazione del routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="c989f-115">You need to make several decisions regarding the Mediation Server topology and call routing configuration.</span></span> <span data-ttu-id="c989f-116">Si tratterà sia di SBCs come peer uguali che di usare il routing round robin per le chiamate tra di essi oppure si designa un SBC come primario e l'altro come secondario?</span><span class="sxs-lookup"><span data-stu-id="c989f-116">Will you treat both SBCs as equal peers and use round-robin routing for calls between them, or will you designate one SBC as primary and the other as secondary?</span></span>



</div>

<span data-ttu-id="c989f-117">Per informazioni dettagliate sulla distribuzione di un trunk SIP in Lync Server, vedere [come implementare il trunking SIP in Lync server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="c989f-117">For details about deploying a SIP trunk in Lync Server, see [How do I implement SIP trunking in Lync Server 2013?](lync-server-2013-how-do-i-implement-sip-trunking.md).</span></span> <span data-ttu-id="c989f-118">Le domande seguenti consentiranno di decidere come distribuire i trunk SIP per E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="c989f-118">The following questions will help you decide how to deploy the SIP trunks for E9-1-1.</span></span>

  - <span data-ttu-id="c989f-119">**È consigliabile distribuire il trunk SIP in una connessione Internet dedicata o affittata?**</span><span class="sxs-lookup"><span data-stu-id="c989f-119">**Should you deploy the SIP trunk over a dedicated leased or a shared internet connection?**</span></span>  
    <span data-ttu-id="c989f-120">È importante che le chiamate di emergenza si connettano sempre.</span><span class="sxs-lookup"><span data-stu-id="c989f-120">It is important that emergency calls always connect.</span></span> <span data-ttu-id="c989f-121">Una linea dedicata offre una connessione che non verrà superata da altri traffici sulla rete e offre la possibilità di implementare la qualità del servizio (QoS).</span><span class="sxs-lookup"><span data-stu-id="c989f-121">A dedicated line provides a connection that will not be preempted by other traffic on the network, and gives you the ability to implement Quality of Service (QoS).</span></span> <span data-ttu-id="c989f-122">Tenere presente che, se ci si connette a provider di servizi di emergenza tramite Internet pubblico ed è necessario garantire la riservatezza delle chiamate di emergenza, è necessaria la crittografia IPSec.</span><span class="sxs-lookup"><span data-stu-id="c989f-122">Remember that if you are connecting to emergency services service providers over the public Internet and you need to guarantee the confidentiality of emergency calls, IPSec encryption is required.</span></span>

<!-- end list -->

  - <span data-ttu-id="c989f-123">**La distribuzione E9-1-1 è progettata per la tolleranza ai disastri?**</span><span class="sxs-lookup"><span data-stu-id="c989f-123">**Is your E9-1-1 deployment designed for disaster tolerance?**</span></span>  
    <span data-ttu-id="c989f-124">Poiché si tratta di una soluzione di emergenza, la resilienza è importante.</span><span class="sxs-lookup"><span data-stu-id="c989f-124">Because this is an emergency solution, resiliency is important.</span></span> <span data-ttu-id="c989f-125">Distribuire i server di mediazione primari e secondari e i trunk SIP in posizioni tolleranti al disastro.</span><span class="sxs-lookup"><span data-stu-id="c989f-125">Deploy your primary and secondary Mediation Servers and SIP trunks in disaster tolerant locations.</span></span> <span data-ttu-id="c989f-126">È consigliabile distribuire il server di mediazione principale più vicino agli utenti supportati e instradare le chiamate di failover tramite il Mediation Server secondario (che si trova in una posizione geografica diversa).</span><span class="sxs-lookup"><span data-stu-id="c989f-126">It is a good idea to deploy your primary Mediation Server closest to the users that it is supporting, and route failover calls through the secondary Mediation Server (located in a different geographic location).</span></span>

<!-- end list -->

  - <span data-ttu-id="c989f-127">**È necessario distribuire un trunk SIP separato per ogni filiale?**</span><span class="sxs-lookup"><span data-stu-id="c989f-127">**Should you deploy a separate SIP trunk for each branch office?**</span></span>  
    <span data-ttu-id="c989f-128">Lync Server offre diverse strategie per la gestione della resilienza vocale nelle filiali, tra cui: avere reti di dati resilienti, distribuire un trunk SIP in ogni ramo o spingere le chiamate verso il gateway locale durante le interruzioni.</span><span class="sxs-lookup"><span data-stu-id="c989f-128">Lync Server provides several strategies for handling voice resiliency in branch offices, including: having resilient data networks, deploying a SIP trunk at each branch, or pushing calls out to the local gateway during outages.</span></span> <span data-ttu-id="c989f-129">Per informazioni dettagliate, vedere [trunking SIP del sito di succursale in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span><span class="sxs-lookup"><span data-stu-id="c989f-129">For details, see [Branch site SIP trunking in Lync Server 2013](lync-server-2013-branch-site-sip-trunking.md).</span></span>

<!-- end list -->

  - <span data-ttu-id="c989f-130">**Il controllo di ammissione delle chiamate (CAC) è abilitato?**</span><span class="sxs-lookup"><span data-stu-id="c989f-130">**Is call admission control (CAC) enabled?**</span></span>  
    <span data-ttu-id="c989f-131">Lync Server non gestisce le chiamate di emergenza in modo diverso rispetto a una normale chiamata.</span><span class="sxs-lookup"><span data-stu-id="c989f-131">Lync Server does not handle emergency calls any differently than an ordinary call.</span></span> <span data-ttu-id="c989f-132">Per questo motivo, la gestione della larghezza di banda o il controllo di ammissione delle chiamate (CAC) possono avere un impatto negativo su una configurazione E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="c989f-132">For this reason, bandwidth management, or call admission control (CAC), can have a negative impact on an E9-1-1 configuration.</span></span> <span data-ttu-id="c989f-133">Le chiamate di emergenza verranno bloccate o indirizzate al gateway PSTN locale se è abilitato un CAC e il limite configurato viene superato in un collegamento in cui vengono instradate le chiamate di emergenza.</span><span class="sxs-lookup"><span data-stu-id="c989f-133">Emergency calls will be blocked or routed to the local PSTN gateway if a CAC is enabled and the configured limit is exceeded on a link where emergency calls are being routed.</span></span> <span data-ttu-id="c989f-134">Come indicato in precedenza in questo argomento, tali chiamate non avranno dati sulla posizione e dovranno essere indirizzate manualmente al ECRC.</span><span class="sxs-lookup"><span data-stu-id="c989f-134">As indicated earlier in this topic, such calls will not have location data and must be manually routed to the ECRC.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

