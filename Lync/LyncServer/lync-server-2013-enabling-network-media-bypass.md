---
title: 'Lync Server 2013: abilitazione del bypass multimediale di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Enabling network media bypass
ms:assetid: 95c4fa06-49d3-41ac-acdc-7dcda66e5508
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182552(v=OCS.15)
ms:contentKeyID: 48184846
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff18c69d6d257a520d2413bff266c97879d4963e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978820"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-network-media-bypass-in-lync-server-2013"></a><span data-ttu-id="9756c-102">Abilitare il bypass multimediale di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9756c-102">Enabling network media bypass in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9756c-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="9756c-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="9756c-104">Le impostazioni di bypass multimediale si applicano globalmente in una distribuzione di Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9756c-104">Media bypass settings apply globally across a Microsoft Lync Server 2013 deployment.</span></span> <span data-ttu-id="9756c-105">Il bypass multimediale consente alle chiamate di aggirare il Mediation Server.</span><span class="sxs-lookup"><span data-stu-id="9756c-105">Media bypass allows calls to bypass the Mediation Server.</span></span> <span data-ttu-id="9756c-106">Per informazioni dettagliate su quando usare il bypass multimediale, vedere [pianificazione di un bypass multimediale in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) nella sezione pianificazione.</span><span class="sxs-lookup"><span data-stu-id="9756c-106">For details about when to use Media bypass, see [Planning for media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md) in the Planning section.</span></span>

<span data-ttu-id="9756c-107">È possibile abilitare e configurare il bypass multimediale dal pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9756c-107">You can enable and configure media bypass from the Lync Server Control Panel.</span></span>

<div>

## <a name="to-enable-and-configure-media-bypass"></a><span data-ttu-id="9756c-108">Per abilitare e configurare il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="9756c-108">To enable and configure media bypass</span></span>

1.  <span data-ttu-id="9756c-109">Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.</span><span class="sxs-lookup"><span data-stu-id="9756c-109">From a user account that is a member of the RTCUniversalServerAdmins group (or has equivalent user rights), or is assigned to the CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="9756c-110">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="9756c-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="9756c-111">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="9756c-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="9756c-112">Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **globale**.</span><span class="sxs-lookup"><span data-stu-id="9756c-112">In the left navigation bar, click **Network Configuration** and then click **Global**.</span></span>

4.  <span data-ttu-id="9756c-113">Nella pagina **globale** fare clic sulla configurazione **globale** .</span><span class="sxs-lookup"><span data-stu-id="9756c-113">On the **Global** page, click the **Global** configuration.</span></span> <span data-ttu-id="9756c-114">Esiste sempre una sola configurazione ed è sempre denominata globale.</span><span class="sxs-lookup"><span data-stu-id="9756c-114">There is always only one configuration, and it is always named Global.</span></span>

5.  <span data-ttu-id="9756c-115">Nel menu **modifica** fare clic su **Visualizza dettagli**.</span><span class="sxs-lookup"><span data-stu-id="9756c-115">On the **Edit** menu, click **View details**.</span></span>

6.  <span data-ttu-id="9756c-116">Nella pagina **Modifica impostazioni globali** fare clic sulla casella di controllo **Abilita esclusione multimediale** .</span><span class="sxs-lookup"><span data-stu-id="9756c-116">On the **Edit Global Setting** page, click the **Enable media bypass** check box.</span></span>

7.  <span data-ttu-id="9756c-117">Selezionare una delle opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9756c-117">Select one of the following options:</span></span>
    
      - <span data-ttu-id="9756c-118">**Ignora sempre seleziona**   questa opzione per provare il bypass multimediale in tutte le chiamate.</span><span class="sxs-lookup"><span data-stu-id="9756c-118">**Always bypass**   Select this option to attempt media bypass on all calls.</span></span> <span data-ttu-id="9756c-119">Questa opzione non sarà disponibile se il controllo di ammissione di chiamata (CAC) è abilitato.</span><span class="sxs-lookup"><span data-stu-id="9756c-119">This option will be unavailable if call admission control (CAC) is enabled.</span></span> <span data-ttu-id="9756c-120">Se CAC non è abilitato, selezionare questa opzione nelle situazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9756c-120">If CAC is not enabled, select this option in the following situations:</span></span>
        
          - <span data-ttu-id="9756c-121">Non è necessario il controllo della larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="9756c-121">There is no need for bandwidth control.</span></span>
        
          - <span data-ttu-id="9756c-122">Non c'è bisogno di una configurazione a grana fine per determinare quando deve avvenire il bypass.</span><span class="sxs-lookup"><span data-stu-id="9756c-122">There is no need for fine-grained configuration to determine when bypass should happen.</span></span>
        
          - <span data-ttu-id="9756c-123">Esiste una connettività completa tra gateway e client.</span><span class="sxs-lookup"><span data-stu-id="9756c-123">There is full connectivity between gateways and clients.</span></span>
    
      - <span data-ttu-id="9756c-124">**Usare i siti e la configurazione**   dell'area se è abilitato CAC, questa opzione è selezionata per impostazione predefinita e non può essere modificata.</span><span class="sxs-lookup"><span data-stu-id="9756c-124">**Use sites and region configuration**   If CAC is enabled, this option is selected by default and cannot be changed.</span></span> <span data-ttu-id="9756c-125">Quando questa opzione è selezionata, i siti e le aree di configurazione della rete verranno usati per determinare quando il bypass multimediale è possibile.</span><span class="sxs-lookup"><span data-stu-id="9756c-125">When this option is selected, network configuration sites and regions will be used to determine when media bypass is possible.</span></span> <span data-ttu-id="9756c-126">Se si seleziona questa opzione, è possibile scegliere di abilitare il bypass per i siti non mappati.</span><span class="sxs-lookup"><span data-stu-id="9756c-126">If you select this option, you can choose to enable bypass for sites that are not mapped.</span></span> <span data-ttu-id="9756c-127">Fare clic sulla casella **di controllo Abilita esclusione per i siti non mappati** solo se si hanno uno o più siti di grandi dimensioni associati alla stessa area geografica che non hanno vincoli di larghezza di banda, ad esempio un sito centrale di grandi dimensioni, e si hanno anche alcuni siti di succursale associati alla stessa area geografica con vincoli di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="9756c-127">Click the **Enable bypass for non-mapped sites** check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site) and you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="9756c-128">Quando si Abilita l'esclusione per i siti non mappati, la configurazione viene semplificata perché si specificano solo le subnet associate ai siti di succursale e non è necessario specificare tutte le subnet associate a tutti i siti.</span><span class="sxs-lookup"><span data-stu-id="9756c-128">When you enable bypass for non-mapped sites, configuration is streamlined because you specify only the subnets associated with the branch sites rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="9756c-129">È consigliabile non selezionare la casella di controllo **Abilita esclusione per i siti non mappati** se è abilitato CAC.</span><span class="sxs-lookup"><span data-stu-id="9756c-129">We recommend that you do not select the **Enable bypass for non-mapped sites** check box if CAC is enabled.</span></span>

8.  <span data-ttu-id="9756c-130">Fare clic su **conferma** per salvare le modifiche.</span><span class="sxs-lookup"><span data-stu-id="9756c-130">Click **Commit** to save your changes.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="9756c-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="9756c-131">See Also</span></span>


[<span data-ttu-id="9756c-132">Disabilitare il bypass multimediale di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9756c-132">Disabling network media bypass in Lync Server 2013</span></span>](lync-server-2013-disabling-network-media-bypass.md)  


[<span data-ttu-id="9756c-133">Opzioni di bypass multimediale globale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9756c-133">Global media bypass options in Lync Server 2013</span></span>](lync-server-2013-global-media-bypass-options.md)  


[<span data-ttu-id="9756c-134">Pianificazione del bypass multimediale in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9756c-134">Planning for media bypass in Lync Server 2013</span></span>](lync-server-2013-planning-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

