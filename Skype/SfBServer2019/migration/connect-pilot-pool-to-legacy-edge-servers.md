---
title: Connettere il pool pilota ai server legacy di Edge Server
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Dopo aver distribuito Skype for Business Server 2019, è necessario configurare una route di federazione per il sito. Per utilizzare la route federata utilizzata dall'installazione legacy, è necessario configurare Skype for Business Server 2019 per l'utilizzo di questa route.
ms.openlocfilehash: 8243ebbf9540587dedd8e4ae3a51e22f9a315728
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753926"
---
# <a name="connect-pilot-pool-to-legacy-edge-servers"></a><span data-ttu-id="1c410-104">Connettere il pool pilota ai server legacy di Edge Server</span><span class="sxs-lookup"><span data-stu-id="1c410-104">Connect pilot pool to legacy Edge Servers</span></span>

<span data-ttu-id="1c410-105">Dopo aver distribuito Skype for Business Server 2019, è necessario configurare una route di federazione per il sito.</span><span class="sxs-lookup"><span data-stu-id="1c410-105">After deploying Skype for Business Server 2019, you need to configure a federation route for your site.</span></span> <span data-ttu-id="1c410-106">Per utilizzare la route federata utilizzata dall'installazione legacy, è necessario configurare Skype for Business Server 2019 per l'utilizzo di questa route.</span><span class="sxs-lookup"><span data-stu-id="1c410-106">In order to use the federated route that is being used by the legacy installation, Skype for Business Server 2019 must be configured to use this route.</span></span> 
  
<span data-ttu-id="1c410-107">Per abilitare il sito di Skype for Business Server 2019 per l'utilizzo del server Director e Edge della distribuzione legacy, utilizzare Generatore di topologie per associare il pool perimetrale legacy.</span><span class="sxs-lookup"><span data-stu-id="1c410-107">To enable the Skype for Business Server 2019 site to use the Director and Edge Server of the legacy deployment, use Topology Builder to associate the legacy Edge pool.</span></span>
  
### <a name="to-associate-the-legacy-edge-pool-by-using-topology-builder"></a><span data-ttu-id="1c410-108">Per associare il pool di server perimetrali legacy tramite Generatore di topologie</span><span class="sxs-lookup"><span data-stu-id="1c410-108">To associate the legacy Edge pool by using Topology Builder</span></span>

1. <span data-ttu-id="1c410-109">Apre lo strumento di generazione topologia</span><span class="sxs-lookup"><span data-stu-id="1c410-109">Open Topology Builder.</span></span> 
    
2. <span data-ttu-id="1c410-110">Seleziona il tuo sito, che è direttamente sotto il nodo **di Skype for Business Server** .</span><span class="sxs-lookup"><span data-stu-id="1c410-110">Select your site, which is directly below the **Skype for Business Server** node.</span></span> 
    
3. <span data-ttu-id="1c410-111">Scegliere **Modifica proprietà** dal menu **Azioni**.</span><span class="sxs-lookup"><span data-stu-id="1c410-111">On the **Actions** menu, click **Edit Properties**.</span></span>
    
4. <span data-ttu-id="1c410-112">Nel riquadro sinistro selezionare **Route di federazione**.</span><span class="sxs-lookup"><span data-stu-id="1c410-112">In the left pane, select **Federation route**.</span></span>
    
5. <span data-ttu-id="1c410-113">In **Assegnazione route federazione sito**selezionare **Abilita federazione SIP**e quindi selezionare il server Director legacy o legacy Edge se non è elencato alcun Director.</span><span class="sxs-lookup"><span data-stu-id="1c410-113">Under **Site federation route assignment**, select **Enable SIP federation**, and then select the legacy Director, or the legacy Edge Server if no Director is listed.</span></span>
  
6. <span data-ttu-id="1c410-114">Fare clic su  \*\*OK \*\* per chiudere la pagina  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="1c410-114">Click **OK** to close the **Edit Properties** page.</span></span> 
    
7. <span data-ttu-id="1c410-115">In Generatore di topologie, nel nodo Skype for Business Server 2019, passare a **Server Standard Edition** o **pool Enterprise Edition front end**, fare clic con il pulsante destro del mouse sul pool e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1c410-115">In Topology Builder, under the Skype for Business Server 2019 node, navigate to the **Standard Edition server** or **Enterprise Edition Front End pools**, right-click the pool, and then click **Edit Properties**.</span></span>
    
8. <span data-ttu-id="1c410-116">In **Associazioni** selezionare la casella di controllo accanto ad **Associa pool di server perimetrali (per componenti multimediali)**.</span><span class="sxs-lookup"><span data-stu-id="1c410-116">Under **Associations**, select the check box next to **Associate Edge pool (for media components)**.</span></span> 
    
9. <span data-ttu-id="1c410-117">Selezionare il server perimetrale legacy nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="1c410-117">From the list, select the legacy Edge Server.</span></span> 
  
10. <span data-ttu-id="1c410-118">Fare clic su  \*\*OK \*\* per chiudere la pagina  \*\*Modifica proprietà \*\*.</span><span class="sxs-lookup"><span data-stu-id="1c410-118">Click **OK** to close the **Edit Properties** page.</span></span> 
    
11. <span data-ttu-id="1c410-119">In **Generatore di topologie**selezionare il nodo di primo livello, **Skype for Business Server**.</span><span class="sxs-lookup"><span data-stu-id="1c410-119">In **Topology Builder**, select the top-most node, **Skype for Business Server**.</span></span>
    
12. <span data-ttu-id="1c410-120">Scegliere **Pubblica topologia** dal menu **Azione** e quindi scegliere **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="1c410-120">From the **Action** menu, click **Publish Topology**, and then click **Next**.</span></span>
    
13. <span data-ttu-id="1c410-121">Al termine della Pubblicazione guidata \*\*\*\* fare clic su  \*\*Fine \*\*.</span><span class="sxs-lookup"><span data-stu-id="1c410-121">When the **Publishing wizard** completes, click **Finish**.</span></span>
    

