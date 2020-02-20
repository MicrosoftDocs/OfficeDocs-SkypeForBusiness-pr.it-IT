---
title: 'Lync Server 2013: configurare il bypass multimediale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413028(v=OCS.15)
ms:contentKeyID: 48185836
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6f1bf38bc20878de55b51ef6a59640e64ada8f02
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153758"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-in-lync-server-2013"></a><span data-ttu-id="e47ed-102">Configurare il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e47ed-102">Configure media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e47ed-103">_**Ultimo argomento modificato:** 2013-02-24_</span><span class="sxs-lookup"><span data-stu-id="e47ed-103">_**Topic Last Modified:** 2013-02-24_</span></span>

<span data-ttu-id="e47ed-104">In questa sezione si presuppone che sia stato già pubblicato e configurato almeno uno o più Mediation Server, come descritto in [define a Mediation Server in Generatore di topologie in Lync server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) e [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md)oppure in [define and Configure a front end pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) e [pubblicare la topologia in Lync Server 2013](lync-server-2013-publish-the-topology.md), rispettivamente, tutti nella documentazione relativa alla</span><span class="sxs-lookup"><span data-stu-id="e47ed-104">This section assumes that you have already published and configured either at least one or more Mediation Servers (as described in [Define a Mediation Server in Topology Builder in Lync Server 2013](lync-server-2013-define-a-mediation-server-in-topology-builder.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), or in [Define and configure a Front End pool or Standard Edition server in Lync Server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md) and [Publish the topology in Lync Server 2013](lync-server-2013-publish-the-topology.md), respectively, all in the Deployment documentation).</span></span>

<span data-ttu-id="e47ed-105">In questa sezione si presuppone inoltre che sia stato definito almeno un peer gateway per fornire la connettività PSTN, come descritto in [define a gateway in Generatore di topologie in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="e47ed-105">This section also assumes that you have defined at least one gateway peer to provide PSTN connectivity, as described in [Define a gateway in Topology Builder in Lync Server 2013](lync-server-2013-define-a-gateway-in-topology-builder.md).</span></span> <span data-ttu-id="e47ed-106">Se il peer a cui ci si connette è l'SBC di un provider di trunking SIP, assicurarsi che il provider sia un provider qualificato e che il provider supporti il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="e47ed-106">If the peer you connect to is the SBC of a SIP trunking provider, make sure that the provider is a qualified provider and that the provider supports media bypass.</span></span> <span data-ttu-id="e47ed-107">Ad esempio, molti provider di trunking SIP consentiranno solo a SBC di ricevere traffico dal Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="e47ed-107">For example, many SIP trunking providers will only allow their SBC to receive traffic from the Mediation Server.</span></span> <span data-ttu-id="e47ed-108">In caso affermativo, non è necessario abilitare il bypass per il trunk in questione.</span><span class="sxs-lookup"><span data-stu-id="e47ed-108">If so, then bypass must not be enabled for the trunk in question.</span></span> <span data-ttu-id="e47ed-109">Inoltre, non è possibile abilitare il bypass multimediale, a meno che l'organizzazione non riveli gli indirizzi IP della rete interna al provider di trunking SIP.</span><span class="sxs-lookup"><span data-stu-id="e47ed-109">Also, you cannot enable media bypass unless your organization reveals its internal network IP addresses to the SIP trunking provider.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="e47ed-110">Il bypass multimediale non interagisce con ogni gateway PSTN, ogni IP-PBX e ogni SBC.</span><span class="sxs-lookup"><span data-stu-id="e47ed-110">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="e47ed-111">Microsoft ha testato una serie di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con i sistemi IP-PBX Cisco.</span><span class="sxs-lookup"><span data-stu-id="e47ed-111">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="e47ed-112">Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program – Lync Server <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>at.</span><span class="sxs-lookup"><span data-stu-id="e47ed-112">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="https://go.microsoft.com/fwlink/p/?linkid=214406">https://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<span data-ttu-id="e47ed-113">In questa sezione viene descritto come abilitare il bypass multimediale per ridurre l'elaborazione necessaria del Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="e47ed-113">This section describes how to enable media bypass to reduce the processing required of the Mediation Server.</span></span> <span data-ttu-id="e47ed-114">Prima di abilitare il bypass multimediale, verificare che l'ambiente soddisfi le condizioni necessarie per il supporto del bypass multimediale, come descritto in [Planning for Media Bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="e47ed-114">Before you enable media bypass, make sure that your environment meets the conditions required to support media bypass, as described in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning documentation.</span></span> <span data-ttu-id="e47ed-115">Assicurarsi inoltre di utilizzare le informazioni in [Planning for Media Bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) per decidere se abilitare le impostazioni globali di bypass multimediale per ignorare sempre il Mediation Server o per utilizzare le informazioni sul sito e le aree geografiche quando si determina se ignorare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="e47ed-115">Also make sure that you used the information in [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) to decide whether to enable media bypass global settings to always bypass the Mediation Server or to use site and region information when determining whether to bypass the Mediation Server.</span></span>

<span data-ttu-id="e47ed-116">Se è già stato configurato facoltativamente il controllo di ammissione di chiamata (CAC), un'altra funzionalità di VoIP aziendale avanzata, si noti che la prenotazione di larghezza di banda eseguita dal controllo di ammissione di chiamata non è applicabile alle chiamate per le quali viene utilizzato il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="e47ed-116">If you have already optionally configured call admission control (CAC), another advanced Enterprise Voice feature, note that the bandwidth reservation performed by call admission control does not apply to any calls for which media bypass is employed.</span></span> <span data-ttu-id="e47ed-117">La verifica dell'utilizzo del bypass multimediale viene eseguita per prima e, se il bypass multimediale è occupato, il controllo di ammissione di chiamata non viene utilizzato per la chiamata. solo se il controllo bypass multimediale ha esito negativo è la verifica eseguita per il controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="e47ed-117">The verification of whether to employ media bypass is performed first, and if media bypass is employed, call admission control is not used for the call; only if the media bypass check fails is the check performed for call admission control.</span></span> <span data-ttu-id="e47ed-118">Le due caratteristiche sono quindi esclusive per una chiamata specifica instradata alla rete PSTN.</span><span class="sxs-lookup"><span data-stu-id="e47ed-118">The two features are thus mutually exclusive for any particular call that is routed to the PSTN.</span></span> <span data-ttu-id="e47ed-119">Questa è la logica perché il bypass multimediale presuppone che non esistano vincoli di larghezza di banda tra gli endpoint multimediali di una chiamata. il bypass multimediale non può essere eseguito sui collegamenti con larghezza di banda limitata.</span><span class="sxs-lookup"><span data-stu-id="e47ed-119">This is the logic because media bypass assumes that bandwidth constraints do not exist between the media endpoints on a call; media bypass cannot be performed on links with restricted bandwidth.</span></span> <span data-ttu-id="e47ed-120">Di conseguenza, una delle seguenti operazioni si applicherà a una chiamata PSTN: a) il contenuto multimediale ignora il Mediation Server e il controllo di ammissione di chiamata non riserva la larghezza di banda per la chiamata. o b) il controllo di ammissione di chiamata applica la prenotazione della larghezza di banda alla chiamata e il supporto viene elaborato dal Mediation Server coinvolto nella chiamata.</span><span class="sxs-lookup"><span data-stu-id="e47ed-120">As a result, one of the following will apply to a PSTN call: a) media bypasses the Mediation Server, and call admission control does not reserve bandwidth for the call; or b) call admission control applies bandwidth reservation to the call, and media is processed by the Mediation Server involved in the call.</span></span>

<div>

## <a name="next-steps-enable-media-bypass-on-the-trunk-connection"></a><span data-ttu-id="e47ed-121">Passaggi successivi: abilitare il bypass multimediale sulla connessione trunk</span><span class="sxs-lookup"><span data-stu-id="e47ed-121">Next Steps: Enable Media Bypass on the Trunk Connection</span></span>

<span data-ttu-id="e47ed-122">Dopo aver configurato le impostazioni iniziali per la connettività PSTN (dial plan, criteri vocali, record di utilizzo PSTN, route di chiamata in uscita e regole di conversione), iniziare il processo di abilitazione del bypass multimediale tramite la procedura descritta in [Configure a Trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="e47ed-122">After configuring initial settings for PSTN connectivity (dial plans, voice policies, PSTN usage records, outbound call routes, and translation rules), begin the process of enabling media bypass by using the steps in [Configure a trunk with media bypass in Lync Server 2013](lync-server-2013-configure-a-trunk-with-media-bypass.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e47ed-123">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e47ed-123">See Also</span></span>


[<span data-ttu-id="e47ed-124">Configurare un trunk con bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e47ed-124">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="e47ed-125">Configurare il bypass multimediale in Lync Server 2013 per ignorare sempre il Mediation Server</span><span class="sxs-lookup"><span data-stu-id="e47ed-125">Configure media bypass in Lync Server 2013 to always bypass the Mediation Server</span></span>](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[<span data-ttu-id="e47ed-126">Configurare le impostazioni globali di bypass multimediale in Lync Server 2013 per l'utilizzo delle informazioni sui siti e sulle aree geografiche</span><span class="sxs-lookup"><span data-stu-id="e47ed-126">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  


[<span data-ttu-id="e47ed-127">Opzioni di bypass multimediale globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e47ed-127">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="e47ed-128">Pianificazione del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e47ed-128">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

