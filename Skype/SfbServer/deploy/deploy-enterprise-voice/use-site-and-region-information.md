---
title: Configurare le impostazioni globali di bypass multimediale in Skype for Business Server per l'utilizzo delle informazioni sui siti e sulle aree geografiche
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Configurare il bypass multimediale da utilizzare solo per alcuni siti e aree geografiche in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 58fd4fca90029a8a5f4cd82c6a9616ae66e69cd0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830586"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a><span data-ttu-id="fac2f-103">Configurare le impostazioni globali di bypass multimediale in Skype for Business Server per l'utilizzo delle informazioni sui siti e sulle aree geografiche</span><span class="sxs-lookup"><span data-stu-id="fac2f-103">Configure media bypass global settings in Skype for Business Server to use site and region information</span></span>
 
<span data-ttu-id="fac2f-104">Configurare il bypass multimediale da utilizzare solo per alcuni siti e aree geografiche in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="fac2f-104">Configure media bypass to be used for only certain sites and regions in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="fac2f-105">Se si utilizzano i passaggi descritti in questo argomento per configurare le impostazioni globali per il bypass multimediale, si presuppone che non si disponga di una buona connettività tra tutti gli endpoint di Skype for business e qualsiasi peer per il quale è stato configurato il bypass multimediale sulla connessione trunk.</span><span class="sxs-lookup"><span data-stu-id="fac2f-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you do not have good connectivity between all Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
> [!NOTE]
> <span data-ttu-id="fac2f-p101">Le informazioni relative alle aree di rete e ai siti di rete vengono condivise tra le caratteristiche di VoIP aziendale avanzate del controllo di ammissione di chiamata e del bypass multimediale, quando entrambi sono abilitati. Se il controllo di ammissione di chiamata è già configurato, non sarà pertanto necessario eseguire la procedura seguente per modificare le informazioni sui siti e sulle aree in modo specifico per il bypass multimediale. Eseguire questa procedura se le aree e i siti di rete non sono stati ancora configurati per il controllo di ammissione di chiamata e si desidera modificare le impostazioni per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="fac2f-p101">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled. Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass. Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span> 
  
<span data-ttu-id="fac2f-109">Affinché il bypass multimediale funzioni correttamente, è necessario che esista una coerenza tra un sito come definito in Generatore di topologie e come definito quando si configurano le aree di rete e i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="fac2f-109">For media bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="fac2f-110">Ad esempio, se si dispone di un sito di succursale definito in Generatore di topologie per la distribuzione di un solo gateway PSTN, il sito di succursale deve essere configurato con un criterio VoIP aziendale che consenta agli utenti di siti di succursale di fare in modo che le chiamate PSTN vengano instradate attraverso il gateway PSTN nel sito di succursale.</span><span class="sxs-lookup"><span data-stu-id="fac2f-110">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="fac2f-111">Per configurare le informazioni relative ai siti e alle aree per il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="fac2f-111">To Configure Site and Region Information for Media Bypass</span></span>

1. <span data-ttu-id="fac2f-112">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fac2f-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
2. <span data-ttu-id="fac2f-113">Nella barra di spostamento sinistra fare clic su **Configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="fac2f-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="fac2f-114">Fare doppio clic sulla configurazione **Globale** nella tabella.</span><span class="sxs-lookup"><span data-stu-id="fac2f-114">Double-click the **Global** configuration in the table.</span></span>
    
4. <span data-ttu-id="fac2f-115">Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita bypass multimediale**.</span><span class="sxs-lookup"><span data-stu-id="fac2f-115">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="fac2f-116">Fare clic su **Utilizza configurazione siti e aree**.</span><span class="sxs-lookup"><span data-stu-id="fac2f-116">Click **Use sites and region configuration**.</span></span>
    
6. <span data-ttu-id="fac2f-117">Se necessario, selezionare la casella di controllo **Abilita bypass per siti non mappati**.</span><span class="sxs-lookup"><span data-stu-id="fac2f-117">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="fac2f-p103">Selezionare questa casella di controllo solo se alla stessa area sono associati uno o più siti di grandi dimensioni senza vincoli di larghezza di banda, ad esempio un grande sito centrale, ma anche siti di succursale con vincoli di larghezza di banda. Quando si abilita il bypass per i siti non mappati, la configurazione viene snellita perché è necessario specificare esclusivamente le subnet associate ai siti di succursale anziché tutte le subnet associate a tutti i siti. È consigliabile non selezionare questa casella di controllo se il controllo di ammissione di chiamata è abilitato.</span><span class="sxs-lookup"><span data-stu-id="fac2f-p103">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints. When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites. We recommend that you do not select this check box if call admission control is enabled.</span></span> 
  
7. <span data-ttu-id="fac2f-121">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="fac2f-121">Click **Commit**.</span></span>
    
<span data-ttu-id="fac2f-122">Successivamente, aggiungere le subnet al sito di rete, come descritto in [associare una subnet a un sito di rete](deploy-network.md#BKMK_AssociateSubnets).</span><span class="sxs-lookup"><span data-stu-id="fac2f-122">Next, add subnets to the network site, as described in [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets).</span></span> <span data-ttu-id="fac2f-123">Dopo aver associato tutte le subnet ai siti di rete, la distribuzione del bypass multimediale può considerarsi completata.</span><span class="sxs-lookup"><span data-stu-id="fac2f-123">After you associate all subnets with network sites, media bypass deployment is complete.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="fac2f-124">Se non sono stati ancora creati i siti e le aree di rete, è necessario crearli prima di poter proseguire con la distribuzione del bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="fac2f-124">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="fac2f-125">Per informazioni dettagliate, vedere [deploy Network Regions, sites and Subnets in Skype for business](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="fac2f-125">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="fac2f-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fac2f-126">See also</span></span>

[<span data-ttu-id="fac2f-127">Associare una subnet a un sito di rete</span><span class="sxs-lookup"><span data-stu-id="fac2f-127">Associate a subnet with a network site</span></span>](deploy-network.md#BKMK_AssociateSubnets)

