---
title: Configurare le impostazioni globali di bypass multimediale per l'utilizzo delle informazioni sul sito e sulla regione
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure media bypass global settings to use site and region information
ms:assetid: 0a21cdf1-f350-49da-b346-70806f256bea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398150(v=OCS.15)
ms:contentKeyID: 48183360
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c9b875693fb1fb7c9cfca4ae845709c874b0e8c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038318"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-media-bypass-global-settings-in-lync-server-2013-to-use-site-and-region-information"></a><span data-ttu-id="92e6d-102">Configurare le impostazioni globali di bypass multimediale in Lync Server 2013 per l'utilizzo delle informazioni sui siti e sulle aree geografiche</span><span class="sxs-lookup"><span data-stu-id="92e6d-102">Configure media bypass global settings in Lync Server 2013 to use site and region information</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="92e6d-103">_**Ultimo argomento modificato:** 2012-09-21_</span><span class="sxs-lookup"><span data-stu-id="92e6d-103">_**Topic Last Modified:** 2012-09-21_</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="92e6d-104">In questo argomento si presuppone che il bypass multimediale (Media Bypass) sia già stato configurato per qualsiasi connessione trunk dal Mediation Server a un peer (un gateway PSTN (Public Switched Telephone Network), un IP-PBX o un Session Border Controller (SBC) presso un provider di servizi di telefonia Internet o ITSP) per un sito o un servizio specifico per il quale si desidera ignorare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="92e6d-104">This topic assumes that you have already configured media bypass for any trunk connections from the Mediation Server to a peer (a public switched telephone network (PSTN) gateway, an IP-PBX, or a Session Border Controller (SBC) at an Internet Telephony Service Provider (ITSP) for a specific site or service for which you want media to bypass the Mediation Server.</span></span><BR><span data-ttu-id="92e6d-105">In questo argomento si presuppone inoltre che siano stati definiti tutti i siti centrali e i siti di succursale in Generatore di topologie in modo che corrispondano all'area di rete, al sito di rete e alla configurazione della subnet eseguite seguendo i passaggi descritti in <A href="lync-server-2013-create-or-modify-a-network-region.md">creare o modificare un'area di rete in Lync server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">creare o modificare un sito di rete in Lync Server 2013</A>e <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">associare una subnet a un 2013 sito</A></span><span class="sxs-lookup"><span data-stu-id="92e6d-105">This topic also assumes that you have defined all central sites and branch sites in Topology Builder in a way that matches the network region, network site, and subnet configuration that you performed according to the steps in <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A>, <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>, and <A href="lync-server-2013-associate-a-subnet-with-a-network-site.md">Associate a subnet with a network site in Lync Server 2013</A>.</span></span> <span data-ttu-id="92e6d-106">Se non corrispondono, il bypass multimediale avrà esito negativo.</span><span class="sxs-lookup"><span data-stu-id="92e6d-106">If they do not match, then media bypass will not succeed.</span></span>



</div>

<span data-ttu-id="92e6d-p102">Oltre ad abilitare il bypass multimediale per le singole connessioni trunk associate a un peer, è necessario configurare le impostazioni globali. Se si utilizza la procedura illustrata in questo argomento per configurare le impostazioni globali per il bypass multimediale, il presupposto è che una o entrambe le situazioni seguenti incidano sulla configurazione:</span><span class="sxs-lookup"><span data-stu-id="92e6d-p102">In addition to enabling media bypass for individual trunk connections associated with a peer, you must also configure global settings. If you use the steps in this topic to configure global settings for media bypass, the assumption is that one or both of the following situations affects your configuration:</span></span>

  - <span data-ttu-id="92e6d-109">*Non* si dispone di una buona connettività tra gli endpoint di Lync Server e tutti i peer per cui è stato configurato il bypass multimediale sulla connessione trunk.</span><span class="sxs-lookup"><span data-stu-id="92e6d-109">You *do not* have good connectivity between Lync Server endpoints and any peers for which you configured media bypass on the trunk connection.</span></span>

  - <span data-ttu-id="92e6d-110">Il controllo di ammissione di chiamata per la gestione della larghezza di banda è abilitato.</span><span class="sxs-lookup"><span data-stu-id="92e6d-110">Call admission control (CAC) for bandwidth management is enabled.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="92e6d-111">Per informazioni dettagliate sulle considerazioni sia per il controllo di ammissione di chiamata che per il bypass multimediale, vedere la sezione "controllo di ammissione di chiamata per le connessioni PSTN" in <A href="lync-server-2013-media-bypass-and-mediation-server.md">media bypass e Mediation Server in Lync server 2013</A> nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="92e6d-111">For details about the considerations for both call admission control and media bypass, see the "Call Admission Control of PSTN Connections" section in <A href="lync-server-2013-media-bypass-and-mediation-server.md">Media bypass and Mediation Server in Lync Server 2013</A> in the Planning documentation.</span></span>

    
    </div>

<span data-ttu-id="92e6d-p103">Le informazioni relative alle aree di rete e ai siti di rete vengono condivise tra le caratteristiche di VoIP aziendale avanzate del controllo di ammissione di chiamata e del bypass multimediale, quando entrambi sono abilitati. Se il controllo di ammissione di chiamata è già configurato, non sarà pertanto necessario eseguire la procedura seguente per modificare le informazioni sui siti e sulle aree in modo specifico per il bypass multimediale. Eseguire questa procedura se le aree e i siti di rete non sono stati ancora configurati per il controllo di ammissione di chiamata e si desidera modificare le impostazioni per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="92e6d-p103">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span>

<span data-ttu-id="92e6d-115">In alternativa, eseguire questa procedura se si desidera utilizzare le informazioni sui siti e sulle aree per prendere una decisione relativa al bypass, ma non si ha alcuna intenzione di abilitare il controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="92e6d-115">Or, follow these steps if you want to use site and region information in making the bypass decision, but have no intention of enabling call admission control.</span></span> <span data-ttu-id="92e6d-116">In tal caso, i collegamenti con restrizioni di larghezza di banda dovranno comunque essere rappresentati tramite criteri intersito di rete, come descritto in [creare criteri intersito di rete in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span><span class="sxs-lookup"><span data-stu-id="92e6d-116">In such a case, bandwidth restricted links will still need to be represented through network intersite policies, as described in [Create network intersite policies in Lync Server 2013](lync-server-2013-create-network-intersite-policies.md).</span></span> <span data-ttu-id="92e6d-117">Gli effettivi vincoli di larghezza di banda in questa circostanza sono meno importanti perché il controllo di ammissione di chiamata non è stato abilitato.</span><span class="sxs-lookup"><span data-stu-id="92e6d-117">The actual bandwidth constraints are not as important in this case, because call admission control has not been enabled.</span></span> <span data-ttu-id="92e6d-118">Questi collegamenti vengono invece utilizzati per suddividere le subnet in modo da specificare quelle senza limiti di larghezza di banda e che possono quindi utilizzare il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="92e6d-118">Instead, these links are used to partition subnets to specify those that have no bandwidth limits and can, therefore, employ media bypass.</span></span> <span data-ttu-id="92e6d-119">Ciò si verifica anche quando il controllo di ammissione di chiamata e il bypass multimediale sono entrambi abilitati.</span><span class="sxs-lookup"><span data-stu-id="92e6d-119">Note that this is also true when call admission control and media bypass are both enabled.</span></span>

<span data-ttu-id="92e6d-120">Inoltre, affinché il bypass funzioni correttamente, è necessario che esista una coerenza tra un sito come definito in Generatore di topologie e come viene definito quando si configurano le aree di rete e i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="92e6d-120">Furthermore, for bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="92e6d-121">Ad esempio, se si dispone di un sito di succursale definito in Generatore di topologie per la distribuzione di un solo gateway PSTN, il sito di succursale deve essere configurato con un criterio VoIP aziendale che consenta agli utenti di un sito di succursale di fare in modo che le chiamate PSTN vengano instradate attraverso la rete PSTN Gateway nel sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="92e6d-121">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>

<div>

## <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="92e6d-122">Per configurare le informazioni relative ai siti e alle aree per il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="92e6d-122">To Configure Site and Region Information for Media Bypass</span></span>

1.  <span data-ttu-id="92e6d-123">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="92e6d-123">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="92e6d-124">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="92e6d-124">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="92e6d-125">Nella barra di spostamento sinistra fare clic su **Configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="92e6d-125">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="92e6d-126">Fare doppio clic sulla configurazione **Globale** nella tabella.</span><span class="sxs-lookup"><span data-stu-id="92e6d-126">Double-click the **Global** configuration in the table.</span></span>

4.  <span data-ttu-id="92e6d-127">Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita bypass multimediale**.</span><span class="sxs-lookup"><span data-stu-id="92e6d-127">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>

5.  <span data-ttu-id="92e6d-128">Fare clic su **Utilizza configurazione siti e aree**.</span><span class="sxs-lookup"><span data-stu-id="92e6d-128">Click **Use sites and region configuration**.</span></span>

6.  <span data-ttu-id="92e6d-129">Se necessario, selezionare la casella di controllo **Abilita bypass per siti non mappati**.</span><span class="sxs-lookup"><span data-stu-id="92e6d-129">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    <div>
    

    > [!NOTE]
    > <span data-ttu-id="92e6d-p107">Selezionare questa casella di controllo solo se alla stessa area sono associati uno o più siti di grandi dimensioni senza vincoli di larghezza di banda, ad esempio un grande sito centrale, ma anche siti di succursale con vincoli di larghezza di banda. Quando si abilita il bypass per i siti non mappati, la configurazione viene snellita perché è necessario specificare esclusivamente le subnet associate ai siti di succursale anziché tutte le subnet associate a tutti i siti. È consigliabile non selezionare questa casella di controllo se il controllo di ammissione di chiamata è abilitato.</span><span class="sxs-lookup"><span data-stu-id="92e6d-p107">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span>

    
    </div>

7.  <span data-ttu-id="92e6d-133">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="92e6d-133">Click **Commit**.</span></span>

<span data-ttu-id="92e6d-134">Successivamente, aggiungere le subnet al sito di rete, come descritto in [associare subnet a siti di rete per il bypass multimediale in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span><span class="sxs-lookup"><span data-stu-id="92e6d-134">Next, add subnets to the network site, as described in [Associate subnets with network sites for media bypass in Lync Server 2013](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md).</span></span> <span data-ttu-id="92e6d-135">Le procedure effettive per l'associazione di subnet a siti di rete sono descritte in [associare una subnet a un sito di rete in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md). Dopo aver associato tutte le subnet a siti di rete, la distribuzione di bypass multimediale è stata completata.</span><span class="sxs-lookup"><span data-stu-id="92e6d-135">(The actual procedures for associating subnets with network sites are described in [Associate a subnet with a network site in Lync Server 2013](lync-server-2013-associate-a-subnet-with-a-network-site.md).) After you associate all subnets with network sites, media bypass deployment is complete.</span></span>

<div>


> [!IMPORTANT]
> <span data-ttu-id="92e6d-136">Se non sono stati ancora creati i siti e le aree di rete, è necessario crearli prima di poter proseguire con la distribuzione del bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="92e6d-136">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="92e6d-137">Per informazioni dettagliate, vedere <A href="lync-server-2013-create-or-modify-a-network-region.md">creare o modificare un'area di rete in Lync server 2013</A> e <A href="lync-server-2013-create-or-modify-a-network-site.md">creare o modificare un sito di rete in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="92e6d-137">For details, see <A href="lync-server-2013-create-or-modify-a-network-region.md">Create or modify a network region in Lync Server 2013</A> and <A href="lync-server-2013-create-or-modify-a-network-site.md">Create or modify a network site in Lync Server 2013</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="92e6d-138">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92e6d-138">See Also</span></span>


[<span data-ttu-id="92e6d-139">Associare subnet a siti di rete per il bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="92e6d-139">Associate subnets with network sites for media bypass in Lync Server 2013</span></span>](lync-server-2013-associate-subnets-with-network-sites-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

