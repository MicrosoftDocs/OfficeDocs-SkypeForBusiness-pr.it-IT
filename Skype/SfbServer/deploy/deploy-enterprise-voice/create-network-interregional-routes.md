---
title: Creare route interregionali di rete in Skype for Business Server
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
ms.assetid: 5555262a-a502-4b01-9593-836dd30064f5
description: Creare o modificare le route interregionali di rete, utilizzate VoIP aziendale controllo di ammissione di chiamata in Skype for Business Server.
ms.openlocfilehash: d9ea8def930a075c93effede73ddb3f12d999334
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093124"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a><span data-ttu-id="79e72-103">Creare route interregionali di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="79e72-103">Create network interregional routes in Skype for Business Server</span></span>
 
<span data-ttu-id="79e72-104">Creare o modificare le route interregionali di rete, utilizzate VoIP aziendale controllo di ammissione di chiamata in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="79e72-104">Create or modify network interregional routes, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="79e72-105">Una route interregionale di rete definisce la route tra una coppia di aree di rete.</span><span class="sxs-lookup"><span data-stu-id="79e72-105">A network interregional route defines the route between a pair of network regions.</span></span> <span data-ttu-id="79e72-106">Ogni coppia di aree di rete nella distribuzione del controllo di ammissione di chiamata richiede una route interregionale di rete.</span><span class="sxs-lookup"><span data-stu-id="79e72-106">Each pair of network regions in your call admission control deployment requires a network interregional route.</span></span> <span data-ttu-id="79e72-107">In tal modo ogni area di rete della distribuzione può accedere a tutte le altre aree.</span><span class="sxs-lookup"><span data-stu-id="79e72-107">This enables every network region within the deployment to access every other region.</span></span>
  
<span data-ttu-id="79e72-108">Mentre i collegamenti area impostano limitazioni di larghezza di banda per le connessioni tra aree geografiche, una route interregionale determina il percorso collegato che la connessione attraverserà da un'area all'altra.</span><span class="sxs-lookup"><span data-stu-id="79e72-108">While region links set bandwidth limitations on the connections between regions, an interregional route determines which linked path the connection will traverse from one region to another.</span></span>
  
<span data-ttu-id="79e72-109">Nella topologia di esempio è necessario definire route interregionali di rete per ognuna delle tre coppie di aree: Nord America/EMEA, EMEA/APAC e Nord America/APAC.</span><span class="sxs-lookup"><span data-stu-id="79e72-109">In the example topology, network interregional routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="79e72-110">Per creare route interregionali di rete tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="79e72-110">To create network interregional routes by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="79e72-111">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="79e72-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="79e72-112">Eseguire il cmdlet **New-CsNetworkInterRegionRoute** per definire le route richieste.</span><span class="sxs-lookup"><span data-stu-id="79e72-112">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="79e72-113">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="79e72-113">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
   ```

   ```powershell
   New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
   ```

    > [!NOTE]
    > <span data-ttu-id="79e72-114">La route interregionale di rete Nord America/APAC richiede due collegamenti di area di rete perché non esiste un collegamento diretto tra le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="79e72-114">The North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="79e72-115">Per creare route interregionali di rete tramite il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="79e72-115">To create network interregional routes by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="79e72-116">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="79e72-116">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="79e72-117">Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="79e72-117">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="79e72-118">Fare clic sul pulsante di spostamento **Route area**.</span><span class="sxs-lookup"><span data-stu-id="79e72-118">Click the **Region Route** navigation button.</span></span>
    
4. <span data-ttu-id="79e72-119">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="79e72-119">Click **New**.</span></span>
    
5. <span data-ttu-id="79e72-120">Nella pagina **Nuova route area** fare clic su **Nome** e quindi digitare un nome per la route interregionale di rete.</span><span class="sxs-lookup"><span data-stu-id="79e72-120">On the **New Region Route** page, click **Name** and then type a name for the network interregional route.</span></span>
    
6. <span data-ttu-id="79e72-121">Fare clic su **Area di rete 1** e quindi fare clic su un'area di rete nell'elenco per il routing all'area di rete 2.</span><span class="sxs-lookup"><span data-stu-id="79e72-121">Click **Network Region #1**, and then click a network region in the list that you want to route to Network Region #2.</span></span>
    
7. <span data-ttu-id="79e72-122">Fare clic su **Area di rete 2** e quindi fare clic su un'area di rete nell'elenco per il routing all'area di rete 1.</span><span class="sxs-lookup"><span data-stu-id="79e72-122">Click **Network Region #2**, and then click a network region in the list that you want to route to Network Region #1.</span></span>
    
8. <span data-ttu-id="79e72-123">Fare **clic su** Aggiungi accanto al **campo** Collegamenti area di rete e quindi aggiungere un collegamento di area di rete che verrà utilizzato nella route interregionale di rete.</span><span class="sxs-lookup"><span data-stu-id="79e72-123">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregional route.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="79e72-124">Se si crea una route per due aree di rete tra le quali non esiste un collegamento diretto, è necessario aggiungere tutti i collegamenti necessari per completare la route.</span><span class="sxs-lookup"><span data-stu-id="79e72-124">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span></span> <span data-ttu-id="79e72-125">Ad esempio, la route interregionale di rete Nord America/APAC richiede due collegamenti di area di rete perché non esiste un collegamento diretto tra le aree di rete.</span><span class="sxs-lookup"><span data-stu-id="79e72-125">For example, the North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
9. <span data-ttu-id="79e72-126">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="79e72-126">Click **Commit**.</span></span>
    
10. <span data-ttu-id="79e72-127">Per completare la creazione di route interregionali di rete per la topologia, ripetere i passaggi da 4 a 9 con le impostazioni per altre route interregionali di rete.</span><span class="sxs-lookup"><span data-stu-id="79e72-127">To finish creating network interregional routes for your topology, repeat steps 4 through 9 with settings for other network interregional routes.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="79e72-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="79e72-128">See also</span></span>

[<span data-ttu-id="79e72-129">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="79e72-129">New-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="79e72-130">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="79e72-130">Get-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="79e72-131">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="79e72-131">Set-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="79e72-132">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="79e72-132">Remove-CsNetworkInterRegionRoute</span></span>](/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)