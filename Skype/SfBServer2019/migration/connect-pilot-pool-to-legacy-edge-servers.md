---
title: Connettere il pool pilota ai server legacy di Edge Server
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Dopo la distribuzione di Skype for Business Server 2019, è necessario configurare una route federativo per il sito. Per usare la route federata usata dall'installazione legacy, Skype for Business Server 2019 deve essere configurato per l'uso della route.
ms.openlocfilehash: 6cc49da3cb27679ef295c7bbeca122aea5a89d10
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813704"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="9984e-104">Connettere il pool pilota ai server legacy di Edge Server</span><span class="sxs-lookup"><span data-stu-id="9984e-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="9984e-105">Dopo la distribuzione di Skype for Business Server 2019, è necessario configurare una route federativo per il sito.</span><span class="sxs-lookup"><span data-stu-id="9984e-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="9984e-106">Per usare la route federata usata dall'installazione legacy, Skype for Business Server 2019 deve essere configurato per l'uso della route.</span><span class="sxs-lookup"><span data-stu-id="9984e-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="9984e-107">Per consentire al sito di Skype for Business Server 2019 di usare il Director e il server perimetrale della distribuzione legacy, usare generatore di topologie per associare il pool di Edge legacy.</span><span class="sxs-lookup"><span data-stu-id="9984e-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="9984e-108">Per associare il pool di Edge legacy tramite Generatore di topologia</span><span class="sxs-lookup"><span data-stu-id="9984e-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="9984e-109">Aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="9984e-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="9984e-110">Selezionare il sito, che si trova direttamente sotto il nodo **di Skype for Business Server** .</span><span class="sxs-lookup"><span data-stu-id="9984e-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="9984e-111">Nel menu **azioni** fare clic su **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9984e-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="9984e-112">Nel riquadro sinistro selezionare **Route federativo**.</span><span class="sxs-lookup"><span data-stu-id="9984e-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="9984e-113">In **assegnazione della route federativo di sito**selezionare **Abilita federazione SIP**e quindi selezionare il Director legacy o il server perimetrale legacy se non è elencato alcun amministratore.</span><span class="sxs-lookup"><span data-stu-id="9984e-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="9984e-114">Fare clic su **OK** per chiudere la pagina **modifica proprietà** .</span><span class="sxs-lookup"><span data-stu-id="9984e-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="9984e-115">In Generatore di topologia, nel nodo di Skype for Business Server 2019, passare al pool **Standard Edition server** o **Enterprise Edition front-end**, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9984e-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="9984e-116">In **associazioni**selezionare la casella di controllo accanto a **associa Edge pool (per i componenti multimediali)**.</span><span class="sxs-lookup"><span data-stu-id="9984e-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="9984e-117">Nell'elenco selezionare il server perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="9984e-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="9984e-118">Fare clic su **OK** per chiudere la pagina **modifica proprietà** .</span><span class="sxs-lookup"><span data-stu-id="9984e-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="9984e-119">In **Generatore di topologie**selezionare il nodo principale, **Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="9984e-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="9984e-120">Nel menu **azione** fare clic su **Pubblica topologia**e quindi su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="9984e-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="9984e-121">Al termine della **pubblicazione guidata** , fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="9984e-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

