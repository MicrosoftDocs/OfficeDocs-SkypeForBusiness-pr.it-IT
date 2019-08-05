---
title: Connettere il pool pilota agli Edge Server legacy
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Dopo la distribuzione di Skype for Business Server 2019, è necessario configurare una route federativo per il sito. Per usare la route federata usata dall'installazione legacy, Skype for Business Server 2019 deve essere configurato per l'uso della route.
ms.openlocfilehash: 20aacda86c6c49b319859d6f1c175ce6258caddb
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191156"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="9f4b8-104">Connettere il pool pilota agli Edge Server legacy</span><span class="sxs-lookup"><span data-stu-id="9f4b8-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="9f4b8-105">Dopo la distribuzione di Skype for Business Server 2019, è necessario configurare una route federativo per il sito.</span><span class="sxs-lookup"><span data-stu-id="9f4b8-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="9f4b8-106">Per usare la route federata usata dall'installazione legacy, Skype for Business Server 2019 deve essere configurato per l'uso della route.</span><span class="sxs-lookup"><span data-stu-id="9f4b8-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="9f4b8-107">Per consentire al sito di Skype for Business Server 2019 di usare il Director e il server perimetrale della distribuzione legacy, usare generatore di topologie per associare il pool di Edge legacy.</span><span class="sxs-lookup"><span data-stu-id="9f4b8-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="9f4b8-108">Per associare il pool di Edge legacy tramite Generatore di topologia</span><span class="sxs-lookup"><span data-stu-id="9f4b8-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="9f4b8-109">Aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="9f4b8-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="9f4b8-110">Selezionare il sito, che si trova direttamente sotto il nodo **di Skype for Business Server** .</span><span class="sxs-lookup"><span data-stu-id="9f4b8-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="9f4b8-111">Nel menu **azioni** fare clic su **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9f4b8-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="9f4b8-112">Nel riquadro sinistro selezionare **Route federativo**.</span><span class="sxs-lookup"><span data-stu-id="9f4b8-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="9f4b8-113">In **assegnazione della route federativo di sito**selezionare **Abilita federazione SIP**e quindi selezionare il Director legacy o il server perimetrale legacy se non è elencato alcun amministratore.</span><span class="sxs-lookup"><span data-stu-id="9f4b8-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="9f4b8-114">Fare clic su **OK** per chiudere la pagina **modifica proprietà** .</span><span class="sxs-lookup"><span data-stu-id="9f4b8-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="9f4b8-115">In Generatore di topologia, nel nodo di Skype for Business Server 2019, passare al pool **Standard Edition server** o **Enterprise Edition front-end**, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9f4b8-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="9f4b8-116">In **associazioni**selezionare la casella di controllo accanto a **associa Edge pool (per i componenti multimediali)**.</span><span class="sxs-lookup"><span data-stu-id="9f4b8-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="9f4b8-117">Nell'elenco selezionare il server perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="9f4b8-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="9f4b8-118">Fare clic su **OK** per chiudere la pagina **modifica proprietà** .</span><span class="sxs-lookup"><span data-stu-id="9f4b8-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="9f4b8-119">In **Generatore**di topologie selezionare il nodo principale, **Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="9f4b8-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="9f4b8-120">Nel menu **azione** fare clic su **Pubblica topologia**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9f4b8-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="9f4b8-121">Al termine della **pubblicazione guidata** , fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="9f4b8-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

