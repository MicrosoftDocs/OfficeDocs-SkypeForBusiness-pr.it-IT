---
title: Reimpostare il controllo di ammissione di chiamata
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
description: Se un pool di front-end legacy ospita il controllo di ammissione delle chiamate (CAC), è necessario trasferire il CAC ospitando un pool di Skype for Business Server 2019 prima di poter rimuovere il pool di front end legacy.
ms.openlocfilehash: cbc481e55d044ef196bd91dbfa8f7ebc796f28b5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812804"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="1884f-103">Reimpostare il controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="1884f-103">Reset call admission control</span></span>

<span data-ttu-id="1884f-104">Se un pool di front-end legacy ospita il controllo di ammissione delle chiamate (CAC), è necessario trasferire il CAC ospitando un pool di Skype for Business Server 2019 prima di poter rimuovere il pool di front end legacy.</span><span class="sxs-lookup"><span data-stu-id="1884f-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="1884f-105">Per reimpostare CAC</span><span class="sxs-lookup"><span data-stu-id="1884f-105">To reset CAC</span></span>

1. <span data-ttu-id="1884f-106">Aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="1884f-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="1884f-107">Fare clic con il pulsante destro del mouse sul nodo del sito e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="1884f-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="1884f-108">In **impostazione controllo ammissione chiamata**verificare che sia selezionata l'opzione **Abilita controllo ammissione chiamata** .</span><span class="sxs-lookup"><span data-stu-id="1884f-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="1884f-109">In **pool Front-end per eseguire il controllo di ammissione di chiamata (CAC)** selezionare il pool di Skype for Business Server 2019 che ospita CAC e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="1884f-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="1884f-110">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="1884f-110">Publish the topology.</span></span>
    

