---
title: Configurare le impostazioni globali di bypass multimediale per usare le informazioni sul sito e sull'area geografica
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: cd070e6380a896548b851ac7d3472cd86eeba75b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978580"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a><span data-ttu-id="4b30d-102">Configurare le impostazioni globali di bypass multimediale in Lync Server 2013 per l'uso delle informazioni sul sito e sull'area geografica</span><span class="sxs-lookup"><span data-stu-id="4b30d-102">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4b30d-103">_**Argomento Ultima modifica:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="4b30d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="4b30d-104">Questo argomento presuppone che sia già stato configurato il bypass multimediale per eventuali connessioni trunk da Mediation Server a un peer (un gateway PSTN (Public Switched Telephone Network), un IP-PBX o un SBC (Session Border Controller) in un servizio di telefonia Internet Provider (ITSP) per un sito o un servizio specifico per cui si vuole che l'elemento multimediale ignori il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="4b30d-104">This topic assumes that you have already configured media bypass for any trunk connections from the Mediation Server to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="4b30d-105">Questo argomento presuppone inoltre che siano stati definiti tutti i siti centrali e i siti di succursale in Generatore di topologia in modo che corrispondano alla configurazione dell'area di rete, del sito di rete e della subnet eseguita in base alla procedura descritta in <A href="lync-server-2013-create-or-modify-a-network-region.md">creare o modificare un'area di rete in Lync server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">creare o modificare un sito di rete in Lync Server 2013</A>e <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associare una subnet a un sito 2013 di</A></span><span class="sxs-lookup"><span data-stu-id="4b30d-105">This topic also assumes that you have defined all central sites and branch sites in Topology Builder in a way that matches the network region, network site, and subnet configuration that you performed according to the steps in <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>, and <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="4b30d-106">Se non corrispondono, il bypass multimediale non riuscirà.</span><span class="sxs-lookup"><span data-stu-id="4b30d-106">If they do not match, then media bypass will not succeed.</span></span>



</div>

<span data-ttu-id="4b30d-107">Oltre a abilitare il bypass multimediale per le singole connessioni trunk associate a un peer, è anche necessario configurare le impostazioni globali.</span><span class="sxs-lookup"><span data-stu-id="4b30d-107">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also configure global settings.</span></span> <span data-ttu-id="4b30d-108">Se si usano i passaggi descritti in questo argomento per configurare le impostazioni globali per il bypass multimediale, il presupposto è che una o entrambe le situazioni seguenti influiscono sulla configurazione:</span><span class="sxs-lookup"><span data-stu-id="4b30d-108">If you use the steps in this topic to configure global settings for media bypass, the assumption is that one or both of the following situations affects your configuration:</span></span>

  - <span data-ttu-id="4b30d-109">*Non* si dispone di una buona connettività tra endpoint di Lync Server e qualsiasi peer per cui è stato configurato il bypass multimediale nella connessione trunk.</span><span class="sxs-lookup"><span data-stu-id="4b30d-109">You *do not* have good connectivity between Lync Server endpoints and any peers for which you configured media bypass on the trunk connection.</span></span>

  - <span data-ttu-id="4b30d-110">Il controllo di ammissione di chiamata (CAC) per la gestione della larghezza di banda è abilitato.</span><span class="sxs-lookup"><span data-stu-id="4b30d-110">Call admission control (CAC) for bandwidth management is enabled.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="4b30d-111">Per informazioni dettagliate sulle considerazioni sia per il controllo dell'ammissione delle chiamate che per il bypass multimediale, vedere la sezione "controllo ammissione chiamata delle connessioni PSTN" in <A href="lync-server-2013-media-bypass-and-mediation-server.md">media bypass e Mediation Server in Lync server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="4b30d-111">For details about the considerations for both call admission control and media bypass, see the "Call Admission Control of PSTN Connections" section in <A href="lync-server-2013-media-bypass-and-mediation-server.md">Media bypass and Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

<span data-ttu-id="4b30d-112">Le informazioni relative all'area geografica e al sito di rete sono condivise tra il controllo di ammissione delle chiamate e l'esclusione delle funzionalità vocali avanzate dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4b30d-112">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled.</span></span> <span data-ttu-id="4b30d-113">Pertanto, se è già stato configurato il controllo di ammissione delle chiamate, non è necessario usare la procedura seguente per modificare le informazioni relative al sito e alla regione in modo specifico per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="4b30d-113">Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass.</span></span> <span data-ttu-id="4b30d-114">Seguire i passaggi descritti in questa procedura se non sono ancora state configurate le aree geografiche e i siti di rete per il controllo dell'ammissione alle chiamate e si vogliono modificare le impostazioni di bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="4b30d-114">Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span>

<span data-ttu-id="4b30d-115">In alternativa, seguire questa procedura se si vuole usare le informazioni sul sito e le aree geografiche in esecuzione della decisione di esclusione, ma non si ha intenzione di abilitare il controllo di ammissione alle chiamate.</span><span class="sxs-lookup"><span data-stu-id="4b30d-115">Or, follow these steps if you want to use site and region information in making the bypass decision, but have no intention of enabling call admission control.</span></span> <span data-ttu-id="4b30d-116">In questo caso, i collegamenti con restrizioni di larghezza di banda dovranno essere rappresentati anche tramite criteri intersito di rete, come descritto in [creare criteri intersito di rete in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="4b30d-116">In such a case, bandwidth restricted links will still need to be represented through network intersite policies, as described in [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span></span> <span data-ttu-id="4b30d-117">I vincoli di larghezza di banda effettivi non sono importanti in questo caso, perché il controllo di ammissione delle chiamate non è stato abilitato.</span><span class="sxs-lookup"><span data-stu-id="4b30d-117">The actual bandwidth constraints are not as important in this case, because call admission control has not been enabled.</span></span> <span data-ttu-id="4b30d-118">Questi collegamenti vengono invece usati per partizionare subnet per specificare quelli che non hanno limiti di larghezza di banda e quindi possono usare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="4b30d-118">Instead, these links are used to partition subnets to specify those that have no bandwidth limits and can, therefore, employ media bypass.</span></span> <span data-ttu-id="4b30d-119">Tieni presente che questo è vero anche quando il controllo di ammissione delle chiamate e il bypass multimediale sono entrambi abilitati.</span><span class="sxs-lookup"><span data-stu-id="4b30d-119">Note that this is also true when call admission control and media bypass are both enabled.</span></span>

<span data-ttu-id="4b30d-120">Inoltre, perché il bypass funzioni correttamente, è necessario che la coerenza tra un sito sia definito in Generatore di topologie e che venga definita quando si configurano le aree di rete e i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="4b30d-120">Furthermore, for bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="4b30d-121">Ad esempio, se si ha un sito di succursale definito in Generatore di topologia con un solo gateway PSTN distribuito, il sito di filiale deve essere configurato con un criterio VoIP aziendale che consente agli utenti del sito succursale di avere le chiamate PSTN instradate attraverso la rete PSTN Gateway nel sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="4b30d-121">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="4b30d-122">Per configurare le informazioni sul sito e sulle aree geografiche per il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="4b30d-122">To Configure Site and Region Information for Media Bypass</span></span>

1.  <span data-ttu-id="4b30d-123">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4b30d-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="4b30d-124">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="4b30d-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="4b30d-125">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="4b30d-125">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="4b30d-126">Fare doppio clic sulla configurazione **globale** nella tabella.</span><span class="sxs-lookup"><span data-stu-id="4b30d-126">Double-click the **Global** configuration in the table.</span></span>

4.  <span data-ttu-id="4b30d-127">Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita esclusione multimediale** .</span><span class="sxs-lookup"><span data-stu-id="4b30d-127">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="4b30d-128">Fare clic su **Usa configurazione siti e aree**geografiche.</span><span class="sxs-lookup"><span data-stu-id="4b30d-128">Click **Use sites and region configuration**.</span></span>

6.  <span data-ttu-id="4b30d-129">Se necessario, selezionare la casella **di controllo Abilita bypass per i siti non mappati** .</span><span class="sxs-lookup"><span data-stu-id="4b30d-129">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="4b30d-130">Selezionare questa casella di controllo solo se si hanno uno o più siti di grandi dimensioni associati alla stessa area geografica che non hanno vincoli di larghezza di banda, ad esempio un sito centrale di grandi dimensioni, ma si hanno anche alcuni siti di succursale associati alla stessa area geografica con larghezza di banda vincoli.</span><span class="sxs-lookup"><span data-stu-id="4b30d-130">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="4b30d-131">Quando si Abilita l'esclusione per i siti non mappati, la configurazione viene semplificata in quanto si specificano solo le subnet associate ai siti di succursale, invece di specificare tutte le subnet associate a tutti i siti.</span><span class="sxs-lookup"><span data-stu-id="4b30d-131">When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="4b30d-132">È consigliabile non selezionare questa casella di controllo se il controllo di ammissione di chiamata è abilitato.</span><span class="sxs-lookup"><span data-stu-id="4b30d-132">We recommend that you do not select this check box if call admission control is enabled.</span></span>

    
    </div>

7.  <span data-ttu-id="4b30d-133">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="4b30d-133">Click **Commit**.</span></span>

<span data-ttu-id="4b30d-134">Aggiungere quindi le subnet al sito di rete, come descritto in [associare subnet ai siti di rete per il bypass multimediale in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="4b30d-134">Next, add subnets to the network site, as described in [Associate subnets with network sites for media bypass in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span></span> <span data-ttu-id="4b30d-135">Le procedure effettive per l'associazione di subnet con i siti di rete sono descritte in [associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md). Dopo aver associato tutte le subnet con i siti di rete, la distribuzione di bypass multimediale è completa.</span><span class="sxs-lookup"><span data-stu-id="4b30d-135">(The actual procedures for associating subnets with network sites are described in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) After you associate all subnets with network sites, media bypass deployment is complete.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="4b30d-136">Se non sono già state create aree di rete e siti di rete, è necessario prima di tutto crearle prima di procedere con la distribuzione di bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="4b30d-136">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="4b30d-137">Per informazioni dettagliate, vedere <A href="lync-server-2013-create-or-modify-a-network-region.md">creare o modificare un'area di rete in Lync server 2013</A> e <A href="lync-server-2013-create-or-modify-a-network-site.md">creare o modificare un sito di rete in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="4b30d-137">For details, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A> and <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4b30d-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b30d-138">See Also</span></span>


[<span data-ttu-id="4b30d-139">Associare subnet a siti di rete per il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4b30d-139">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

