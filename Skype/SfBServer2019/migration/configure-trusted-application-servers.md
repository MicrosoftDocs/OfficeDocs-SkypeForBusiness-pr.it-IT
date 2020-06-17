---
title: Configurare i server applicazioni attendibili
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
description: In un ambiente misto, se si crea un nuovo server applicazioni attendibili, è necessario impostare il pool dell'hop successivo come pool di Skype for Business Server 2019. In un ambiente misto, sia il pool legacy che il pool di Skype for Business Server 2019 vengono visualizzati nell'elenco a discesa. La selezione del pool legacy non è supportata.
ms.openlocfilehash: 1c0aac1efa4f83a81ccf2f3bb5ecbc925ee58839
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753946"
---
# <a name="configure-trusted-application-servers"></a><span data-ttu-id="fa408-105">Configurare i server applicazioni attendibili</span><span class="sxs-lookup"><span data-stu-id="fa408-105">Configure trusted application servers</span></span>

<span data-ttu-id="fa408-106">In un ambiente misto, se si crea un nuovo server applicazioni attendibili, è necessario impostare il pool dell'hop successivo come pool di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fa408-106">In a mixed environment, if you create a new trusted application server, you must set the next hop pool to be a Skype for Business Server 2019 pool.</span></span> <span data-ttu-id="fa408-107">In un ambiente misto, sia il pool legacy che il pool di Skype for Business Server 2019 vengono visualizzati nell'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="fa408-107">In a mixed environment, both the legacy pool and the Skype for Business Server 2019 pool appear in the drop-down list.</span></span> <span data-ttu-id="fa408-108">La selezione del pool legacy non è supportata.</span><span class="sxs-lookup"><span data-stu-id="fa408-108">Selecting the legacy pool is not supported.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fa408-109">Se si esegue la migrazione di un server applicazioni attendibile, è necessario aggiornare anche la versione di UCMA in uso.</span><span class="sxs-lookup"><span data-stu-id="fa408-109">If you are migrating a trusted application server, you should also update the version of UCMA you are using.</span></span> <span data-ttu-id="fa408-110">Se si crea un nuovo pool di applicazioni attendibili per Skype for Business Server 2019, è necessario aggiornare UCMA alla versione inclusa con Skype for Business Server 2019 o la versione più recente disponibile.</span><span class="sxs-lookup"><span data-stu-id="fa408-110">If you create a new Trusted Application Pool for Skype for Business Server 2019, you should update UCMA to the version that is included with Skype for Business Server 2019 or the latest version available.</span></span> 
  
### <a name="select-skype-for-business-server-2019-as-next-hop-when-creating-a-trusted-application-server"></a><span data-ttu-id="fa408-111">Selezionare Skype for Business Server 2019 come hop successivo durante la creazione di un server applicazioni attendibile</span><span class="sxs-lookup"><span data-stu-id="fa408-111">Select Skype for Business Server 2019 as next hop when creating a Trusted application server</span></span>

1. <span data-ttu-id="fa408-112">Apre lo strumento di generazione topologia</span><span class="sxs-lookup"><span data-stu-id="fa408-112">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="fa408-113">Nel riquadro sinistro fare clic con il pulsante destro del mouse su **server applicazioni attendibili** e scegliere **nuovo pool di applicazioni attendibili**.</span><span class="sxs-lookup"><span data-stu-id="fa408-113">In the left pane, right-click **Trusted application servers** and click **New Trusted Application Pool**.</span></span>
    
3. <span data-ttu-id="fa408-114">Immettere il **nome di dominio completo del pool** di applicazioni attendibili e specificare se sarà a server singolo o a più server.</span><span class="sxs-lookup"><span data-stu-id="fa408-114">Enter the **Pool FQDN** of the trusted application pool and select whether it will be single-server or multiple-server.</span></span> 
    
4. <span data-ttu-id="fa408-115">Fare clic su **Avanti**.</span><span class="sxs-lookup"><span data-stu-id="fa408-115">Click **Next**.</span></span>
    
5. <span data-ttu-id="fa408-116">Nella pagina **selezionare l'hop successivo** , nell'elenco, selezionare il pool Front End di Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="fa408-116">On the **Select the next hop** page, from the list, select the Skype for Business Server 2019 Front End pool.</span></span> 
    
6. <span data-ttu-id="fa408-117">Fare clic su **Fine**.</span><span class="sxs-lookup"><span data-stu-id="fa408-117">Click **Finish**.</span></span>
    
7. <span data-ttu-id="fa408-118">Selezionare il nodo principale **Skype for Business Server**e scegliere **pubblica**dal menu **azione** .</span><span class="sxs-lookup"><span data-stu-id="fa408-118">Select the top node **Skype for Business Server**, and from the **Action** menu select **Publish**.</span></span>
    
    <span data-ttu-id="fa408-119">Verificare che il **pool di applicazioni attendibili** sia stato creato correttamente e sia associato al pool Front end corretto.</span><span class="sxs-lookup"><span data-stu-id="fa408-119">Verify that the **Trusted Application Pool** has been created successfully and is associated with the correct Front End pool.</span></span> 
    

