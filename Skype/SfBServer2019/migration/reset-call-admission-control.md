---
title: Reimpostare il controllo di ammissione di chiamata
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
description: Se un pool Front end legacy ospita il controllo di ammissione di chiamata (CAC), è necessario spostare il servizio di hosting CAC in un pool di Skype for Business Server 2019 prima di poter rimuovere il pool Front end legacy.
ms.openlocfilehash: 850ab5c13483d024d52c483c63ef09468f8374b3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/16/2020
ms.locfileid: "44753298"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="67f8b-103">Reimpostare il controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="67f8b-103">Reset call admission control</span></span>

<span data-ttu-id="67f8b-104">Se un pool Front end legacy ospita il controllo di ammissione di chiamata (CAC), è necessario spostare il servizio di hosting CAC in un pool di Skype for Business Server 2019 prima di poter rimuovere il pool Front end legacy.</span><span class="sxs-lookup"><span data-stu-id="67f8b-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="67f8b-105">Per reimpostare il servizio Controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="67f8b-105">To reset CAC</span></span>

1. <span data-ttu-id="67f8b-106">Apre lo strumento di generazione topologia</span><span class="sxs-lookup"><span data-stu-id="67f8b-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="67f8b-107">Fare clic con il pulsante destro del mouse sul nodo del sito e quindi scegliere **Modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="67f8b-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="67f8b-108">In **Impostazione controllo di ammissione di chiamata** assicurarsi che l'opzione **Abilita il controllo di ammissione di chiamata** sia selezionata.</span><span class="sxs-lookup"><span data-stu-id="67f8b-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="67f8b-109">In **pool Front end per eseguire il controllo di ammissione di chiamata (CAC)**, selezionare il pool di Skype for Business Server 2019 che ospita il servizio CAC e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="67f8b-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="67f8b-110">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="67f8b-110">Publish the topology.</span></span>
    

