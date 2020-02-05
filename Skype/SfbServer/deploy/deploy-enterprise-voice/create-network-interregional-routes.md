---
title: Creare route interregionali di rete in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Creare o modificare le route interregionali di rete, usate dal controllo di ammissione delle chiamate vocali aziendali in Skype for Business Server.
ms.openlocfilehash: 2a55e3e2028494a8bc9dc25164eaa67b08d35f83
ms.sourcegitcommit: dd3a3ab4ddbdcfe772f30fb01ba3b97c45c43dd4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41767929"
---
# <a name="create-network-interregional-routes-in-skype-for-business-server"></a><span data-ttu-id="1abdb-103">Creare route interregionali di rete in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1abdb-103">Create network interregional routes in Skype for Business Server</span></span>
 
<span data-ttu-id="1abdb-104">Creare o modificare le route interregionali di rete, usate dal controllo di ammissione delle chiamate vocali aziendali in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1abdb-104">Create or modify network interregional routes, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="1abdb-105">Una route interregionale di rete definisce la route tra una coppia di aree della rete.</span><span class="sxs-lookup"><span data-stu-id="1abdb-105">A network interregional route defines the route between a pair of network regions.</span></span> <span data-ttu-id="1abdb-106">Ogni coppia di aree di rete nella distribuzione del controllo di ammissione alle chiamate richiede una route interregionale di rete.</span><span class="sxs-lookup"><span data-stu-id="1abdb-106">Each pair of network regions in your call admission control deployment requires a network interregional route.</span></span> <span data-ttu-id="1abdb-107">In questo modo ogni area di rete della distribuzione consente di accedere a tutte le altre aree geografiche.</span><span class="sxs-lookup"><span data-stu-id="1abdb-107">This enables every network region within the deployment to access every other region.</span></span>
  
<span data-ttu-id="1abdb-108">Mentre i collegamenti per le aree geografiche impostano limitazioni della larghezza di banda sulle connessioni tra regioni, una route interregionale determina il percorso collegato che la connessione attraverserà da un'area a un'altra.</span><span class="sxs-lookup"><span data-stu-id="1abdb-108">While region links set bandwidth limitations on the connections between regions, an interregional route determines which linked path the connection will traverse from one region to another.</span></span>
  
<span data-ttu-id="1abdb-109">Nella topologia di esempio è necessario definire le route interregionali di rete per ognuna delle tre coppie di aree geografiche: Nord America/EMEA, EMEA/APAC e Nord America/APAC.</span><span class="sxs-lookup"><span data-stu-id="1abdb-109">In the example topology, network interregional routes must be defined for each of the three region pairs: North America/EMEA, EMEA/APAC, and North America/APAC.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="1abdb-110">Per creare route interregionali di rete tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="1abdb-110">To create network interregional routes by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="1abdb-111">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="1abdb-111">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="1abdb-112">Eseguire il cmdlet **New-CsNetworkInterRegionRoute** per definire le route necessarie.</span><span class="sxs-lookup"><span data-stu-id="1abdb-112">Run the **New-CsNetworkInterRegionRoute** cmdlet to define the required routes.</span></span> <span data-ttu-id="1abdb-113">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="1abdb-113">For example, run:</span></span>
    
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
    > <span data-ttu-id="1abdb-114">La route Interregional Network Nord America/APAC richiede due collegamenti all'area geografica di rete perché non è presente un collegamento all'area di rete diretta.</span><span class="sxs-lookup"><span data-stu-id="1abdb-114">The North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
### <a name="to-create-network-interregional-routes-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="1abdb-115">Per creare route interregionali di rete tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="1abdb-115">To create network interregional routes by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="1abdb-116">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="1abdb-116">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="1abdb-117">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="1abdb-117">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="1abdb-118">Fare clic sul pulsante di spostamento della **Route geografica** .</span><span class="sxs-lookup"><span data-stu-id="1abdb-118">Click the **Region Route** navigation button.</span></span>
    
4. <span data-ttu-id="1abdb-119">Fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="1abdb-119">Click **New**.</span></span>
    
5. <span data-ttu-id="1abdb-120">Nella pagina **nuova route dell'area geografica** fare clic su **nome** e quindi digitare un nome per la route interregionale di rete.</span><span class="sxs-lookup"><span data-stu-id="1abdb-120">On the **New Region Route** page, click **Name** and then type a name for the network interregional route.</span></span>
    
6. <span data-ttu-id="1abdb-121">Fare clic su **area geografica #1**e quindi fare clic su un'area di rete nell'elenco che si vuole instradare all'area geografica di rete #2.</span><span class="sxs-lookup"><span data-stu-id="1abdb-121">Click **Network Region #1**, and then click a network region in the list that you want to route to Network Region #2.</span></span>
    
7. <span data-ttu-id="1abdb-122">Fare clic su **area geografica #2**e quindi fare clic su un'area di rete nell'elenco che si vuole instradare all'area geografica di rete #1.</span><span class="sxs-lookup"><span data-stu-id="1abdb-122">Click **Network Region #2**, and then click a network region in the list that you want to route to Network Region #1.</span></span>
    
8. <span data-ttu-id="1abdb-123">Fare clic su **Aggiungi** accanto al campo **collegamenti area di rete** e quindi aggiungere un collegamento all'area di rete che verrà usato nella route interregionale di rete.</span><span class="sxs-lookup"><span data-stu-id="1abdb-123">Click **Add** beside the **Network Region Links** field, and then add a network region link that will be used in the network interregional route.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1abdb-124">Se si sta creando una route per due aree di rete che non dispongono di un collegamento all'area di rete diretta, è necessario aggiungere tutti i collegamenti necessari per completare la route.</span><span class="sxs-lookup"><span data-stu-id="1abdb-124">If you are creating a route for two network regions that do not have a direct network region link between them, you must add all the necessary links to complete the route.</span></span> <span data-ttu-id="1abdb-125">Ad esempio, la route Interregional Network Nord America/APAC richiede due collegamenti all'area geografica di rete perché non è presente un collegamento all'area di rete diretta.</span><span class="sxs-lookup"><span data-stu-id="1abdb-125">For example, the North America/APAC network interregional route requires two network region links because there is no direct network region link between them.</span></span> 
  
9. <span data-ttu-id="1abdb-126">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="1abdb-126">Click **Commit**.</span></span>
    
10. <span data-ttu-id="1abdb-127">Per completare la creazione di route interregionali di rete per la topologia, ripetere i passaggi da 4 a 9 con le impostazioni per altre route interregionali di rete.</span><span class="sxs-lookup"><span data-stu-id="1abdb-127">To finish creating network interregional routes for your topology, repeat steps 4 through 9 with settings for other network interregional routes.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="1abdb-128">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1abdb-128">See also</span></span>

[<span data-ttu-id="1abdb-129">New-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="1abdb-129">New-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="1abdb-130">Get-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="1abdb-130">Get-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="1abdb-131">Set-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="1abdb-131">Set-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkinterregionroute?view=skype-ps)
  
[<span data-ttu-id="1abdb-132">Remove-CsNetworkInterRegionRoute</span><span class="sxs-lookup"><span data-stu-id="1abdb-132">Remove-CsNetworkInterRegionRoute</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkinterregionroute?view=skype-ps)
