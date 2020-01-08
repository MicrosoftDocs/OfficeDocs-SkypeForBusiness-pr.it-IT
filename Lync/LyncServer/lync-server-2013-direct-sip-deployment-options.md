---
title: 'Lync Server 2013: Opzioni di distribuzione SIP diretta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Direct SIP deployment options
ms:assetid: 84691944-03f2-4a89-9f2b-1ab3d7f388cc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398672(v=OCS.15)
ms:contentKeyID: 48184692
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 277b64346dc17815438f2ac34da58f36d2b150f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="direct-sip-deployment-options-in-lync-server-2013"></a><span data-ttu-id="ec14b-102">Opzioni di distribuzione SIP diretta in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ec14b-102">Direct SIP deployment options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ec14b-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="ec14b-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<span data-ttu-id="ec14b-104">In questo argomento vengono fornite topologie ad esempio per la distribuzione di connessioni SIP dirette.</span><span class="sxs-lookup"><span data-stu-id="ec14b-104">This topic provides example topologies for deploying direct SIP connections.</span></span>

<div id="sectionSection0" class="section">

<span id="BKMK_CommunicationsServerStand_Alone"></span>

<div>

## <a name="lync-server-stand-alone"></a><span data-ttu-id="ec14b-105">Lync Server autonomo</span><span class="sxs-lookup"><span data-stu-id="ec14b-105">Lync Server Stand-Alone</span></span>

<span data-ttu-id="ec14b-106">Se l'organizzazione usa una delle distribuzioni descritte in questa sezione, è possibile usare Lync Server 2013 come unica soluzione per la telefonia per parte o tutta l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ec14b-106">If your organization uses one of the deployments described in this section, you can use Lync Server 2013 as the sole telephony solution for part or all of an organization.</span></span> <span data-ttu-id="ec14b-107">Questa sezione descrive in dettaglio le distribuzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ec14b-107">This section describes the following deployments in detail:</span></span>

  - <span data-ttu-id="ec14b-108">**Distribuzione incrementale:** Questa opzione presuppone che si disponga di un'infrastruttura PBX (Private Branch Exchange) esistente e che si voglia inserire in modo incrementale la voce aziendale in gruppi o team più piccoli all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ec14b-108">**Incremental deployment:** This option assumes that you have an existing private branch exchange (PBX) infrastructure and you intend to introduce Enterprise Voice incrementally to smaller groups or teams within your organization.</span></span>

  - <span data-ttu-id="ec14b-109">**Distribuzione solo VoIP di Lync Server:** questa opzione presuppone che si stia pensando di distribuire Enterprise Voice in un sito che non ha un'infrastruttura di telefonia tradizionale.</span><span class="sxs-lookup"><span data-stu-id="ec14b-109">**Lync Server VoIP-only deployment:** this option assumes that you are considering deploying Enterprise Voice at a site that does not have a traditional telephony infrastructure.</span></span>

<div>

## <a name="incremental-deployment"></a><span data-ttu-id="ec14b-110">Distribuzione incrementale</span><span class="sxs-lookup"><span data-stu-id="ec14b-110">Incremental Deployment</span></span>

<span data-ttu-id="ec14b-111">Nella distribuzione incrementale Lync Server 2013 è l'unica soluzione di telefonia per singoli team o reparti, mentre gli altri utenti di un'organizzazione continuano a usare un PBX.</span><span class="sxs-lookup"><span data-stu-id="ec14b-111">In incremental deployment, Lync Server 2013 is the sole telephony solution for individual teams or departments, while the rest of the users in an organization continue to use a PBX.</span></span> <span data-ttu-id="ec14b-112">Questa strategia di distribuzione incrementale offre un modo per introdurre la telefonia IP nella tua azienda attraverso programmi pilota controllati.</span><span class="sxs-lookup"><span data-stu-id="ec14b-112">This incremental deployment strategy provides one way to introduce IP telephony into your enterprise through controlled pilot programs.</span></span> <span data-ttu-id="ec14b-113">I gruppi di lavoro le cui esigenze di comunicazione sono meglio serviti da Microsoft Unified Communications vengono spostati in Enterprise Voice, mentre altri utenti restano nel PBX esistente.</span><span class="sxs-lookup"><span data-stu-id="ec14b-113">Workgroups whose communication needs are best served by Microsoft Unified Communications are moved to Enterprise Voice, while other users remain on the existing PBX.</span></span> <span data-ttu-id="ec14b-114">È possibile eseguire la migrazione di altri gruppi di lavoro a VoIP aziendale, se necessario.</span><span class="sxs-lookup"><span data-stu-id="ec14b-114">Additional workgroups can be migrated to Enterprise Voice, as needed.</span></span>

<span data-ttu-id="ec14b-115">L'opzione incrementale è consigliata se sono presenti gruppi di utenti chiaramente definiti con requisiti di comunicazione comuni e che si prestano alla gestione centralizzata.</span><span class="sxs-lookup"><span data-stu-id="ec14b-115">The incremental option is recommended if you have clearly defined user groups that have communication requirements in common and that lend themselves to centralized management.</span></span> <span data-ttu-id="ec14b-116">Questa opzione è efficace anche se sono presenti team o reparti distribuiti su aree geografiche estese, in cui i risparmi in spese interurbane possono essere significativi.</span><span class="sxs-lookup"><span data-stu-id="ec14b-116">This option is also effective if you have teams or departments that are spread over wide geographic areas, where the savings in long-distance charges can be significant.</span></span> <span data-ttu-id="ec14b-117">In realtà, questa opzione è utile per creare team virtuali i cui membri potrebbero essere sparsi in tutto il mondo.</span><span class="sxs-lookup"><span data-stu-id="ec14b-117">In fact, this option is useful for creating virtual teams whose members may be scattered across the globe.</span></span> <span data-ttu-id="ec14b-118">È possibile creare, modificare o sciogliere tali team in risposta rapida a requisiti aziendali mutevoli.</span><span class="sxs-lookup"><span data-stu-id="ec14b-118">You can create, modify, or disband such teams in rapid response to shifting business requirements.</span></span>

<span data-ttu-id="ec14b-119">La figura seguente mostra la topologia generica per la distribuzione di VoIP aziendale dietro un PBX.</span><span class="sxs-lookup"><span data-stu-id="ec14b-119">The following figure shows the generic topology for deployment of Enterprise Voice behind a PBX.</span></span> <span data-ttu-id="ec14b-120">Questa è la topologia consigliata per la distribuzione incrementale.</span><span class="sxs-lookup"><span data-stu-id="ec14b-120">This is the recommended topology for incremental deployment.</span></span>

<span data-ttu-id="ec14b-121">**Opzione di distribuzione incrementale**</span><span class="sxs-lookup"><span data-stu-id="ec14b-121">**Incremental deployment option**</span></span>

<span data-ttu-id="ec14b-122">![Opzione di migrazione dipartimentale]diagramma(images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "opzione di migrazione dipartimentale")</span><span class="sxs-lookup"><span data-stu-id="ec14b-122">![Departmental Migration Option diagram](images/Gg398672.e951ecf4-7cd2-425a-9106-76977492d682(OCS.15).jpg "Departmental Migration Option diagram")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ec14b-123">Se si connette la distribuzione di Lync Server a un partner SIP diretto certificato, non è necessario un gateway PSTN (Public Switched Telephone Network) tra il Mediation Server e il PBX.</span><span class="sxs-lookup"><span data-stu-id="ec14b-123">If you are connecting your Lync Server deployment to a certified Direct SIP partner, a public switched telephone network (PSTN) gateway between the Mediation Server and the PBX is not required.</span></span> <span data-ttu-id="ec14b-124">Per un elenco dei partner SIP diretti certificati, vedere il sito Web Microsoft Unified Communications Open Interoperability Program <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span><span class="sxs-lookup"><span data-stu-id="ec14b-124">For a list of certified Direct SIP partners, see the Microsoft Unified Communications Open Interoperability Program website at <A href="http://go.microsoft.com/fwlink/p/?linkid=203309">http://go.microsoft.com/fwlink/p/?linkId=203309</A>.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="ec14b-125">Il percorso multimediale mostrato in questa figura è abilitato per il bypass multimediale (la configurazione consigliata).</span><span class="sxs-lookup"><span data-stu-id="ec14b-125">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="ec14b-126">Se si sceglie di disabilitare il bypass multimediale, il percorso multimediale viene instradato attraverso il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="ec14b-126">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

<span data-ttu-id="ec14b-127">In questa topologia sono abilitati i reparti o i gruppi di lavoro selezionati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="ec14b-127">In this topology, selected departments or workgroups are enabled for Enterprise Voice.</span></span> <span data-ttu-id="ec14b-128">Un gateway PSTN collega il gruppo di lavoro abilitato VoIP (Voice over Internet Protocol) al PBX.</span><span class="sxs-lookup"><span data-stu-id="ec14b-128">A PSTN gateway links the Voice over Internet Protocol (VoIP)-enabled workgroup to the PBX.</span></span> <span data-ttu-id="ec14b-129">Gli utenti abilitati per VoIP aziendale, inclusi i dipendenti remoti, comunicano tramite la rete IP.</span><span class="sxs-lookup"><span data-stu-id="ec14b-129">Users who are enabled for Enterprise Voice, including remote workers, communicate across the IP network.</span></span> <span data-ttu-id="ec14b-130">Le chiamate effettuate dagli utenti di VoIP aziendale alla rete PSTN e ai colleghi che non sono abilitate per VoIP aziendale vengono instradate al gateway PSTN appropriato.</span><span class="sxs-lookup"><span data-stu-id="ec14b-130">Calls by Enterprise Voice users to the PSTN and to coworkers who are not enabled for Enterprise Voice are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="ec14b-131">Le chiamate di colleghi che si trovano ancora nel sistema PBX o dai chiamanti della rete PSTN vengono instradate al gateway PSTN, che inoltra le chiamate a Lync Server per il routing.</span><span class="sxs-lookup"><span data-stu-id="ec14b-131">Calls from colleagues who are still on the PBX system, or from callers on the PSTN, are routed to the PSTN gateway, which forwards the calls to Lync Server for routing.</span></span>

<span data-ttu-id="ec14b-132">Esistono due configurazioni consigliate per connettere Enterprise Voice a un'infrastruttura PBX esistente per l'interoperabilità: VoIP aziendale dietro il PBX e VoIP aziendale davanti al PBX.</span><span class="sxs-lookup"><span data-stu-id="ec14b-132">There are two recommended configurations for connecting Enterprise Voice to an existing PBX infrastructure for interoperability: Enterprise Voice behind the PBX and Enterprise Voice in front of the PBX.</span></span>

<div>

## <a name="enterprise-voice-behind-the-pbx"></a><span data-ttu-id="ec14b-133">VoIP aziendale dietro il PBX</span><span class="sxs-lookup"><span data-stu-id="ec14b-133">Enterprise Voice Behind the PBX</span></span>

<span data-ttu-id="ec14b-134">Quando Enterprise Voice viene distribuita dietro il PBX, tutte le chiamate dalla rete PSTN arrivano al PBX, che instrada le chiamate agli utenti di VoIP aziendale a un gateway PSTN e chiama gli utenti PBX al PBX.</span><span class="sxs-lookup"><span data-stu-id="ec14b-134">When Enterprise Voice is deployed behind the PBX, all calls from the PSTN arrive at the PBX, which routes calls to Enterprise Voice users to a PSTN gateway, and calls to PBX users to the PBX.</span></span>

</div>

<div>

## <a name="enterprise-voice-in-front-of-the-pbx"></a><span data-ttu-id="ec14b-135">VoIP aziendale davanti al PBX</span><span class="sxs-lookup"><span data-stu-id="ec14b-135">Enterprise Voice in Front of the PBX</span></span>

<span data-ttu-id="ec14b-136">Quando Enterprise Voice viene distribuita davanti al PBX, tutte le chiamate arrivano al gateway PSTN, che instrada le chiamate per gli utenti di VoIP aziendale a Lync Server e chiama gli utenti PBX al PBX.</span><span class="sxs-lookup"><span data-stu-id="ec14b-136">When Enterprise Voice is deployed in front of the PBX, all calls arrive at the PSTN gateway, which routes calls for Enterprise Voice users to Lync Server and calls for PBX users to the PBX.</span></span> <span data-ttu-id="ec14b-137">Le chiamate alla rete PSTN sia dagli utenti VoIP aziendali che da quelli PBX vengono instradate tramite il network IP al gateway PSTN più efficiente rispetto ai costi.</span><span class="sxs-lookup"><span data-stu-id="ec14b-137">Calls to the PSTN from both Enterprise Voice and PBX users are routed over the IP network to the most cost-efficient PSTN gateway.</span></span> <span data-ttu-id="ec14b-138">La tabella seguente mostra i vantaggi e gli svantaggi di questa configurazione.</span><span class="sxs-lookup"><span data-stu-id="ec14b-138">The following table shows the advantages and disadvantages of this configuration.</span></span>

### <a name="advantages-and-disadvantages-of-deploying-enterprise-voice-in-front-of-pbx"></a><span data-ttu-id="ec14b-139">Vantaggi e svantaggi della distribuzione di VoIP aziendale davanti al PBX</span><span class="sxs-lookup"><span data-stu-id="ec14b-139">Advantages and Disadvantages of Deploying Enterprise Voice in Front of PBX</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ec14b-140">Vantaggi</span><span class="sxs-lookup"><span data-stu-id="ec14b-140">Advantages</span></span></th>
<th><span data-ttu-id="ec14b-141">Svantaggi</span><span class="sxs-lookup"><span data-stu-id="ec14b-141">Disadvantages</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ec14b-142">Il PBX serve ancora agli utenti non abilitati per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="ec14b-142">PBX still serves users not enabled for Enterprise Voice.</span></span></p></td>
<td><p><span data-ttu-id="ec14b-143">I gateway esistenti potrebbero non supportare le caratteristiche o le capacità desiderate.</span><span class="sxs-lookup"><span data-stu-id="ec14b-143">Existing gateways may not support the features or capacity that you want.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ec14b-144">PBX gestisce tutti i dispositivi precedenti.</span><span class="sxs-lookup"><span data-stu-id="ec14b-144">PBX handles all earlier devices.</span></span></p></td>
<td><p><span data-ttu-id="ec14b-145">Richiede un trunk dal gateway al PBX e dal gateway al server Mediation.</span><span class="sxs-lookup"><span data-stu-id="ec14b-145">Requires a trunk from gateway to the PBX and from the gateway to the Mediation Server.</span></span> <span data-ttu-id="ec14b-146">Potrebbe essere necessario un numero maggiore di Trunks dal provider di servizi.</span><span class="sxs-lookup"><span data-stu-id="ec14b-146">You may need more trunks from the service provider.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ec14b-147">Gli utenti di VoIP aziendale mantengono gli stessi numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="ec14b-147">Enterprise Voice users keep the same phone numbers.</span></span></p></td>
<td><p> </p></td>
</tr>
</tbody>
</table>


</div>

</div>

<div>

## <a name="lync-server-voip-only-deployment"></a><span data-ttu-id="ec14b-148">Distribuzione solo VoIP di Lync Server</span><span class="sxs-lookup"><span data-stu-id="ec14b-148">Lync Server VoIP-Only Deployment</span></span>

<span data-ttu-id="ec14b-149">Enterprise Voice offre nuove aziende e nuovi siti di Office per le aziende esistenti, con l'opportunità di implementare una soluzione VoIP completa senza doversi preoccupare dell'integrazione PBX o di incorrere in una sostanziale distribuzione e manutenzione costi di un'infrastruttura IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="ec14b-149">Enterprise Voice provides new businesses, and also new office sites for existing businesses, with the opportunity to implement a full-featured VoIP solution without having to worry about PBX integration or incurring the substantial deployment and maintenance costs of an IP-PBX infrastructure.</span></span> <span data-ttu-id="ec14b-150">Questa soluzione supporta sia i lavoratori in loco che i dipendenti remoti.</span><span class="sxs-lookup"><span data-stu-id="ec14b-150">This solution supports both on-site and remote workers.</span></span>

<span data-ttu-id="ec14b-151">In questa distribuzione tutte le chiamate vengono instradate tramite la rete IP.</span><span class="sxs-lookup"><span data-stu-id="ec14b-151">In this deployment, all calls are routed over the IP network.</span></span> <span data-ttu-id="ec14b-152">Le chiamate alla rete PSTN vengono instradate al gateway PSTN appropriato.</span><span class="sxs-lookup"><span data-stu-id="ec14b-152">Calls to the PSTN are routed to the appropriate PSTN gateway.</span></span> <span data-ttu-id="ec14b-153">Lync 2013 o Lync Phone Edition funge da softphone.</span><span class="sxs-lookup"><span data-stu-id="ec14b-153">Lync 2013 or Lync Phone Edition serves as a softphone.</span></span> <span data-ttu-id="ec14b-154">Il controllo delle chiamate remote non è disponibile e non è necessario perché non ci sono telefoni PBX da controllare dagli utenti.</span><span class="sxs-lookup"><span data-stu-id="ec14b-154">Remote call control is unavailable and unnecessary because there are no PBX phones for users to control.</span></span> <span data-ttu-id="ec14b-155">I servizi di segreteria telefonica e di operatore automatico sono disponibili tramite la distribuzione facoltativa della messaggistica unificata di Exchange.</span><span class="sxs-lookup"><span data-stu-id="ec14b-155">Voice mail and auto-attendant services are available through the optional deployment of Exchange Unified Messaging (UM).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ec14b-156">Oltre all'infrastruttura di rete necessaria per supportare Lync Server 2013, una distribuzione solo VoIP può usare un piccolo gateway qualificato per il supporto di fax e dispositivi analogici.</span><span class="sxs-lookup"><span data-stu-id="ec14b-156">In addition to the network infrastructure that is required to support Lync Server 2013, a VoIP-only deployment can use a small, qualified gateway to support fax machines and analog devices.</span></span>



</div>

<span data-ttu-id="ec14b-157">La figura seguente mostra una topologia tipica per una distribuzione solo VoIP.</span><span class="sxs-lookup"><span data-stu-id="ec14b-157">The following figure shows a typical topology for a VoIP-only deployment.</span></span>

<span data-ttu-id="ec14b-158">**Opzione di distribuzione solo VoIP**</span><span class="sxs-lookup"><span data-stu-id="ec14b-158">**VoIP-only deployment option**</span></span>

<span data-ttu-id="ec14b-159">Opzione di distribuzione di ![Greenfidle](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle")</span><span class="sxs-lookup"><span data-stu-id="ec14b-159">![Greenfidle deployment option](images/Gg398672.820dc5fe-0e20-431b-ae4e-fefdf2221d3b(OCS.15).jpg "Greenfidle deployment option")</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ec14b-160">Il percorso multimediale mostrato in questa figura è abilitato per il bypass multimediale (la configurazione consigliata).</span><span class="sxs-lookup"><span data-stu-id="ec14b-160">The media path shown in this figure has media bypass enabled (the recommended configuration).</span></span> <span data-ttu-id="ec14b-161">Se si sceglie di disabilitare il bypass multimediale, il percorso multimediale viene instradato attraverso il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="ec14b-161">If you opt to disable media bypass, the media path is routed through the Mediation Server.</span></span>



</div>

</div>

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

