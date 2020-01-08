---
title: 'Lync Server 2013: opzioni di bypass multimediale globale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Global media bypass options
ms:assetid: 1bd35f90-8587-48a1-b0c2-095a4053fc77
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398255(v=OCS.15)
ms:contentKeyID: 48183551
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4ebe39b6faeffd36f0dfc9e25959fe7a0b356153
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980714"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="global-media-bypass-options-in-lync-server-2013"></a><span data-ttu-id="48b01-102">Opzioni di bypass multimediale globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b01-102">Global media bypass options in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="48b01-103">_**Argomento Ultima modifica:** 2012-10-04_</span><span class="sxs-lookup"><span data-stu-id="48b01-103">_**Topic Last Modified:** 2012-10-04_</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="48b01-104">Questo argomento presuppone che sia già stato configurato il bypass multimediale per i Trunks in un peer (un gateway PSTN (Public Switched Telephone Network), un IP-PBX o un session border controller (SBC) presso un provider di servizi di telefonia Internet) per un sito o un servizio specifico per cui si vuole che l'elemento multimediale ignori il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="48b01-104">This topic assumes that you have already configured media bypass for any trunks to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider) for a specific site or service for which you want media to bypass the Mediation Server.</span></span>



</div>

<span data-ttu-id="48b01-105">Oltre ad abilitare il bypass multimediale per le singole connessioni trunk associate a un peer, devi anche abilitare il bypass multimediale a livello globale.</span><span class="sxs-lookup"><span data-stu-id="48b01-105">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also enable media bypass globally.</span></span> <span data-ttu-id="48b01-106">Le impostazioni di bypass multimediale globale possono specificare che il bypass multimediale viene sempre tentato per le chiamate alla rete PSTN o che il bypass multimediale viene usato usando il mapping delle subnet ai siti di rete e alle aree di rete, in modo simile a quanto avviene tramite il controllo di ammissione delle chiamate, un altro funzionalità vocale avanzata.</span><span class="sxs-lookup"><span data-stu-id="48b01-106">Global media bypass settings can either specify that media bypass is always attempted for calls to the PSTN, or that media bypass is employed by using the mapping of subnets to network sites and network regions—similar to what is done by call admission control, another advanced voice feature.</span></span> <span data-ttu-id="48b01-107">Quando il bypass multimediale e il controllo dell'ammissione alle chiamate sono entrambi abilitati, viene usata automaticamente l'area di rete, il sito di rete e le informazioni di subnet specificate per il controllo di ammissione di chiamata per determinare se usare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="48b01-107">When media bypass and call admission control are both enabled, then the network region, network site, and subnet information that is specified for call admission control is automatically used when determining whether to employ media bypass.</span></span> <span data-ttu-id="48b01-108">Ciò significa che non è possibile specificare che il bypass multimediale venga sempre tentato per le chiamate al PSTN quando il controllo di ammissione delle chiamate è abilitato.</span><span class="sxs-lookup"><span data-stu-id="48b01-108">This means that you cannot specify that media bypass is always attempted for calls to the PSTN when call admission control is enabled.</span></span>

<span data-ttu-id="48b01-109">Questo argomento descrive come usare il pannello di controllo di Lync Server e Lync Server Management Shell insieme per configurare le impostazioni di bypass multimediale globale.</span><span class="sxs-lookup"><span data-stu-id="48b01-109">This topic describes how to use Lync Server Control Panel and Lync Server Management Shell together to configure global media bypass settings.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="48b01-110">Quando si usano questi passaggi per configurare il bypass multimediale, si presume che si disponga di una buona connettività tra i client e il peer Mediation Server, ad esempio un gateway PSTN, un IP-PBX o un SBC presso un provider di trunking SIP.</span><span class="sxs-lookup"><span data-stu-id="48b01-110">When you use these steps to configure media bypass, the assumption is that you have good connectivity between clients and the Mediation Server peer (for example, a PSTN gateway, an IP-PBX, or an SBC at a SIP trunking provider).</span></span> <span data-ttu-id="48b01-111">Se sono presenti limitazioni della larghezza di banda per il collegamento, non è possibile applicare l'esclusione multimediale alla chiamata.</span><span class="sxs-lookup"><span data-stu-id="48b01-111">If there are any bandwidth limitations on the link, media bypass cannot be applied to the call.</span></span> <span data-ttu-id="48b01-112">Il bypass multimediale non si interagisce con ogni gateway PSTN, IP-PBX e SBC.</span><span class="sxs-lookup"><span data-stu-id="48b01-112">Media bypass will not interoperate with every PSTN gateway, IP-PBX, and SBC.</span></span> <span data-ttu-id="48b01-113">Microsoft ha testato un set di gateway PSTN e SBCs con partner certificati e ha eseguito alcuni test con Cisco IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="48b01-113">Microsoft has tested a set of PSTN gateways and SBCs with certified partners and has done some testing with Cisco IP-PBXs.</span></span> <span data-ttu-id="48b01-114">Il bypass multimediale è supportato solo con i prodotti e le versioni elencati in Unified Communications Open Interoperability Program-Lync Server <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>at.</span><span class="sxs-lookup"><span data-stu-id="48b01-114">Media bypass is supported only with products and versions listed on Unified Communications Open Interoperability Program – Lync Server at <A href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</A>.</span></span>



</div>

<div>

## <a name="next-steps-choose-global-media-bypass-settings"></a><span data-ttu-id="48b01-115">Passaggi successivi: scegliere le impostazioni di bypass multimediale globale</span><span class="sxs-lookup"><span data-stu-id="48b01-115">Next Steps: Choose Global Media Bypass Settings</span></span>

<span data-ttu-id="48b01-116">Dopo aver abilitato il bypass multimediale in tutte le connessioni trunk a un peer per siti o servizi specifici, usare il contenuto seguente per eseguire una delle operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="48b01-116">After you have enabled media bypass on any trunk connections to a peer for specific sites or services, use the following content to either:</span></span>

  - <span data-ttu-id="48b01-117">Abilita sempre il bypass multimediale, come descritto in [configurare il bypass multimediale in Lync Server 2013 per aggirare sempre il server Mediation](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="48b01-117">Enable media bypass always, as described in [Configure media bypass in Lync Server 2013 to always bypass the Mediation Server](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md).</span></span>

  - <span data-ttu-id="48b01-118">In alternativa, configurare il bypass multimediale per l'uso delle informazioni sul sito e sulle aree geografiche, come descritto in [configurare le impostazioni globali di bypass multimediale in Lync Server 2013 per l'uso delle informazioni sul sito e sull'area](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)</span><span class="sxs-lookup"><span data-stu-id="48b01-118">Or, configure media bypass to use site and region information, as described in [Configure media bypass global settings in Lync Server 2013 to use site and region information](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="48b01-119">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="48b01-119">See Also</span></span>


[<span data-ttu-id="48b01-120">Configurare un trunk con il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b01-120">Configure a trunk with media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[<span data-ttu-id="48b01-121">Associare una subnet a un sito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b01-121">Associate a subnet with a network site in Lync Server 2013</span></span>](lync-server-2013-associate-a-subnet-with-a-network-site.md)  


[<span data-ttu-id="48b01-122">Configurare il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b01-122">Configure media bypass in Lync Server 2013</span></span>](lync-server-2013-configure-media-bypass.md)  
[<span data-ttu-id="48b01-123">Bypass multimediale e Mediation Server in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="48b01-123">Media bypass and Mediation Server in Lync Server 2013</span></span>](lync-server-2013-media-bypass-and-mediation-server.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

