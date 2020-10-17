---
title: 'Lync Server 2013: attivazione del bypass multimediale di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4caab36c57c3c8901bd0691e5623f232879bd03
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528523"
---
# <a name="enabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="1d8ba-102">Abilitazione del bypass multimediale di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d8ba-102">Enabling network media bypass in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d8ba-103">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="1d8ba-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="1d8ba-104">Le impostazioni di bypass multimediale vengono applicate a livello globale in una distribuzione di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="1d8ba-105">Il bypass multimediale consente alle chiamate di bypassare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="1d8ba-106">Per informazioni dettagliate sull'utilizzo di bypass multimediale, vedere [Planning for Media Bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) nella sezione Planning.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.</span></span>

<span data-ttu-id="1d8ba-107">È possibile abilitare e configurare il bypass multimediale dal pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-107">You can enable and configure media bypass from the Lync Server Control Panel.</span></span>

<div>

## <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="1d8ba-108">Per abilitare e configurare il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="1d8ba-108">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="1d8ba-109">Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="1d8ba-110">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="1d8ba-111">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="1d8ba-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="1d8ba-112">Sulla barra di spostamento sinistra fare clic su  \*\*Configurazione di rete \*\* e quindi su  \*\*Globale \*\*.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="1d8ba-p103">Nella pagina  \*\*Globale \*\* fare clic sulla scheda della configurazione  \*\*Globale \*\*. Esiste sempre una sola configurazione ed è sempre denominata Globale.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-p103">On the **Global** page, click the **Global** configuration. There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="1d8ba-115">Scegliere  \*\*Mostra dettagli \*\* dal menu  \*\*Modifica \*\*.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="1d8ba-116">Nella pagina **Modifica impostazioni globali** fare clic sulla casella di controllo **Abilita bypass multimediale** .</span><span class="sxs-lookup"><span data-stu-id="1d8ba-116">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="1d8ba-117">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d8ba-117">Select one of the following options:</span></span>
    
      - <span data-ttu-id="1d8ba-118">**Ignora sempre**     Selezionare questa opzione per tentare il bypass multimediale su tutte le chiamate.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-118">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="1d8ba-119">Questa opzione non sarà disponibile se il controllo di ammissione di chiamata (CAC) è abilitato.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-119">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="1d8ba-120">Se il servizio di controllo di ammissione non è abilitato, selezionare questa opzione nei casi seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d8ba-120">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="1d8ba-121">Non è necessario il controllo della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-121">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="1d8ba-122">Non è necessario disporre di una configurazione fine per determinare quando dovrebbe verificarsi un bypass.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-122">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="1d8ba-123">La connettività tra gateway e client è completa.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-123">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="1d8ba-124">**Utilizzare la configurazione**     dei siti e delle aree geografiche Se il servizio di controllo di ammissione è abilitato, questa opzione è selezionata per impostazione predefinita e non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-124">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="1d8ba-125">Quando questa opzione è selezionata, i siti e le aree di configurazione di rete verranno utilizzati per determinare quando è possibile il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-125">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="1d8ba-126">Se si seleziona questa opzione, è possibile scegliere di abilitare il bypass per i siti non mappati.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-126">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="1d8ba-127">Fare clic sulla casella di controllo **Abilita bypass per i siti non mappati** solo se si dispone di uno o più siti di grandi dimensioni associati alla stessa area che non dispongono di vincoli di larghezza di banda (ad esempio, un sito centrale di grandi dimensioni) e si dispone anche di alcuni siti di succursale associati alla stessa area in cui sono presenti vincoli di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-127">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="1d8ba-128">Quando si Abilita il bypass per i siti non mappati, la configurazione viene semplificata perché sono state specificate solo le subnet associate ai siti di succursale anziché la necessità di specificare tutte le subnet associate a tutti i siti.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-128">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="1d8ba-129">Si consiglia di non selezionare la casella **di controllo Abilita bypass per i siti non mappati** se è abilitato CAC.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-129">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="1d8ba-130">Fare clic su  \*\*Commit \*\* per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="1d8ba-130">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="1d8ba-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d8ba-131">See Also</span></span>


[<span data-ttu-id="1d8ba-132">Disabilitazione del bypass multimediale di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d8ba-132">Disabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-disabling-network-media-bypass.md)  


[<span data-ttu-id="1d8ba-133">Opzioni di bypass multimediale globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d8ba-133">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="1d8ba-134">Pianificazione del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1d8ba-134">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

