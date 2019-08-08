---
title: Configurare le impostazioni globali di bypass multimediale in Skype for Business Server per l'uso delle informazioni sul sito e sulle aree geografiche
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 0a21cdf1-f350-49da-b346-70806f256bea
description: Configurare il bypass multimediale da usare solo per determinati siti e aree geografiche in Skype for Business Server VoIP aziendale.
ms.openlocfilehash: 3bfb3dca6e53316d5c1de71abad976ae9223c787
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36240285"
---
# <a name="configure-media-bypass-global-settings-in-skype-for-business-server-to-use-site-and-region-information"></a><span data-ttu-id="ff2ea-103">Configurare le impostazioni globali di bypass multimediale in Skype for Business Server per l'uso delle informazioni sul sito e sulle aree geografiche</span><span class="sxs-lookup"><span data-stu-id="ff2ea-103">Configure media bypass global settings in Skype for Business Server to use site and region information</span></span>
 
<span data-ttu-id="ff2ea-104">Configurare il bypass multimediale da usare solo per determinati siti e aree geografiche in Skype for Business Server VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-104">Configure media bypass to be used for only certain sites and regions in Skype for Business Server Enterprise Voice.</span></span> 
  
 <span data-ttu-id="ff2ea-105">Se si usano i passaggi descritti in questo argomento per configurare le impostazioni globali per il bypass multimediale, si presume che non si disponga di una buona connettività tra tutti gli endpoint di Skype for business e qualsiasi peer per cui è stato configurato il bypass multimediale nella connessione trunk.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-105">If you use the steps in this topic to configure global settings for media bypass, the assumption is that you do not have good connectivity between all Skype for Business endpoints and any peer for which you configured media bypass on the trunk connection.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ff2ea-106">Le informazioni relative all'area geografica e al sito di rete sono condivise tra il controllo di ammissione delle chiamate e l'esclusione delle funzionalità vocali avanzate dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-106">Network region and network site information is shared between call admission control and media bypass advanced Enterprise Voice features when both are enabled.</span></span> <span data-ttu-id="ff2ea-107">Pertanto, se è già stato configurato il controllo di ammissione delle chiamate, non è necessario usare la procedura seguente per modificare le informazioni relative al sito e alla regione in modo specifico per il bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-107">Therefore, if you have already configured call admission control, you are not required to use the following procedure to edit the site and region information specifically for media bypass.</span></span> <span data-ttu-id="ff2ea-108">Seguire i passaggi descritti in questa procedura se non sono ancora state configurate le aree geografiche e i siti di rete per il controllo dell'ammissione alle chiamate e si vogliono modificare le impostazioni di bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-108">Follow the steps in this procedure if you have not yet configured network regions and sites for call admission control, and you want to change media bypass settings.</span></span> 
  
<span data-ttu-id="ff2ea-109">Per consentire il corretto funzionamento del bypass multimediale, è necessario che la coerenza tra un sito sia definito in Generatore di topologie e che venga definita quando si configurano le aree di rete e i siti di rete.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-109">For media bypass to work properly there must be consistency between a site as defined in Topology Builder and as it is defined when you configure network regions and network sites.</span></span> <span data-ttu-id="ff2ea-110">Ad esempio, se si ha un sito di succursale definito in Generatore di topologia con un solo gateway PSTN distribuito, il sito di filiale deve essere configurato con un criterio VoIP aziendale che consente agli utenti del sito succursale di avere le chiamate PSTN instradate attraverso la rete PSTN Gateway nel sito della filiale.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-110">For example, if you have a branch site that you defined in Topology Builder as having only a PSTN gateway deployed, then that branch site must be configured with an Enterprise Voice policy that enables branch site users to have their PSTN calls routed through the PSTN gateway at the branch site.</span></span>
  
### <a name="to-configure-site-and-region-information-for-media-bypass"></a><span data-ttu-id="ff2ea-111">Per configurare le informazioni sul sito e sulle aree geografiche per il bypass multimediale</span><span class="sxs-lookup"><span data-stu-id="ff2ea-111">To Configure Site and Region Information for Media Bypass</span></span>

1. <span data-ttu-id="ff2ea-112">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-112">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
2. <span data-ttu-id="ff2ea-113">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-113">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="ff2ea-114">Fare doppio clic sulla configurazione **globale** nella tabella.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-114">Double-click the **Global** configuration in the table.</span></span>
    
4. <span data-ttu-id="ff2ea-115">Nella pagina **Modifica impostazioni globali** selezionare la casella di controllo **Abilita esclusione multimediale** .</span><span class="sxs-lookup"><span data-stu-id="ff2ea-115">On the **Edit Global Setting** page, select the **Enable media bypass** check box.</span></span>
    
5. <span data-ttu-id="ff2ea-116">Fare clic su **Usa configurazione siti e aree**geografiche.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-116">Click **Use sites and region configuration**.</span></span>
    
6. <span data-ttu-id="ff2ea-117">Se necessario, selezionare la casella **di controllo Abilita bypass per i siti non mappati** .</span><span class="sxs-lookup"><span data-stu-id="ff2ea-117">If necessary, select the **Enable bypass for non-mapped sites** check box.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="ff2ea-118">Selezionare questa casella di controllo solo se si hanno uno o più siti di grandi dimensioni associati alla stessa area geografica che non hanno vincoli di larghezza di banda, ad esempio un sito centrale di grandi dimensioni, ma si hanno anche alcuni siti di succursale associati alla stessa area geografica con larghezza di banda vincoli.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-118">Select this check box only if you have one or more large sites associated with the same region that do not have bandwidth constraints (for example, a large central site), but you also have some branch sites associated with the same region that do have bandwidth constraints.</span></span> <span data-ttu-id="ff2ea-119">Quando si Abilita l'esclusione per i siti non mappati, la configurazione viene semplificata in quanto si specificano solo le subnet associate ai siti di succursale, invece di specificare tutte le subnet associate a tutti i siti.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-119">When you enable bypass for non-mapped sites, configuration is streamlined in that you specify only the subnets associated with the branch sites, rather than needing to specify all subnets associated with all sites.</span></span> <span data-ttu-id="ff2ea-120">È consigliabile non selezionare questa casella di controllo se il controllo di ammissione di chiamata è abilitato.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-120">We recommend that you do not select this check box if call admission control is enabled.</span></span> 
  
7. <span data-ttu-id="ff2ea-121">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-121">Click **Commit**.</span></span>
    
<span data-ttu-id="ff2ea-122">Aggiungere quindi le subnet al sito di rete, come descritto in [associare una subnet a un sito di rete](deploy-network.md#BKMK_AssociateSubnets).</span><span class="sxs-lookup"><span data-stu-id="ff2ea-122">Next, add subnets to the network site, as described in [Associate a subnet with a network site](deploy-network.md#BKMK_AssociateSubnets).</span></span> <span data-ttu-id="ff2ea-123">Dopo aver associato tutte le subnet con i siti di rete, la distribuzione di bypass multimediale è completa.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-123">After you associate all subnets with network sites, media bypass deployment is complete.</span></span>
> [!IMPORTANT]
> <span data-ttu-id="ff2ea-124">Se non sono già state create aree di rete e siti di rete, è necessario prima di tutto crearle prima di procedere con la distribuzione di bypass multimediale.</span><span class="sxs-lookup"><span data-stu-id="ff2ea-124">If you have not already created network regions and network sites, you must first create those before you can proceed with media bypass deployment.</span></span> <span data-ttu-id="ff2ea-125">Per informazioni dettagliate, vedere [distribuire aree di rete, siti e subnet in Skype for business](deploy-network.md).</span><span class="sxs-lookup"><span data-stu-id="ff2ea-125">For details, see [Deploy network regions, sites and subnets in Skype for Business](deploy-network.md).</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="ff2ea-126">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ff2ea-126">See also</span></span>

[<span data-ttu-id="ff2ea-127">Associare una subnet a un sito di rete</span><span class="sxs-lookup"><span data-stu-id="ff2ea-127">Associate a subnet with a network site</span></span>](deploy-network.md#BKMK_AssociateSubnets)

