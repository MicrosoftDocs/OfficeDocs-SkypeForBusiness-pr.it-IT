---
title: Configurare i server applicazioni attendibili
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
description: In un ambiente misto, se crei un nuovo server applicazioni attendibile, devi impostare il pool hop successivo come un pool di Skype for Business Server 2019. In un ambiente misto viene visualizzato sia il pool legacy che il pool di Skype for Business Server 2019 nell'elenco a discesa. La selezione del pool legacy non è supportata.
ms.openlocfilehash: a853065c8888ce9e160b34d182ec8bde6f4569f3
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813774"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="68156-105">Configurare i server applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="68156-105">Configure trusted application servers</span></span>

<span data-ttu-id="68156-106">In un ambiente misto, se crei un nuovo server applicazioni attendibile, devi impostare il pool hop successivo come un pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="68156-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="68156-107">In un ambiente misto viene visualizzato sia il pool legacy che il pool di Skype for Business Server 2019 nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="68156-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="68156-108">La selezione del pool legacy non è supportata.</span><span class="sxs-lookup"><span data-stu-id="68156-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="68156-109">Se si esegue la migrazione di un server applicazioni attendibile, è anche necessario aggiornare la versione di UCMA in uso.</span><span class="sxs-lookup"><span data-stu-id="68156-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="68156-110">Se crei un nuovo pool di applicazioni attendibili per Skype for Business Server 2019, dovresti aggiornare UCMA alla versione inclusa in Skype for Business Server 2019 o l'ultima versione disponibile.</span><span class="sxs-lookup"><span data-stu-id="68156-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="68156-111">Selezionare Skype for Business Server 2019 come hop successivo quando si crea un server applicazioni attendibile</span><span class="sxs-lookup"><span data-stu-id="68156-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="68156-112">Aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="68156-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="68156-113">Nel riquadro sinistro fare clic con il pulsante destro del mouse su **server applicazioni attendibili** e scegliere **nuovo pool di applicazioni attendibili**.</span><span class="sxs-lookup"><span data-stu-id="68156-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="68156-114">Immettere il **nome di dominio completo del pool** di applicazioni attendibili e selezionare se sarà a server singolo o a più server.</span><span class="sxs-lookup"><span data-stu-id="68156-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="68156-115">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="68156-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="68156-116">Nella pagina **selezionare l'hop successivo** , nell'elenco, selezionare il pool di front end di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="68156-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="68156-117">Fare clic su **fine**.</span><span class="sxs-lookup"><span data-stu-id="68156-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="68156-118">Selezionare il nodo superiore di **Skype for Business Server**e scegliere **pubblica**dal menu **azione** .</span><span class="sxs-lookup"><span data-stu-id="68156-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="68156-119">Verificare che il **pool di applicazioni attendibili** sia stato creato correttamente ed associato al pool Front-end corretto.</span><span class="sxs-lookup"><span data-stu-id="68156-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

