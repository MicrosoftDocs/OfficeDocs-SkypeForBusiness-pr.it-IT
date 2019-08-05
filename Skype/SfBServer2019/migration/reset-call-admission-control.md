---
title: Reimpostare il controllo di ammissione di chiamata
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se un pool di front-end legacy ospita il controllo di ammissione delle chiamate (CAC), è necessario trasferire il CAC ospitando un pool di Skype for Business Server 2019 prima di poter rimuovere il pool di front end legacy.
ms.openlocfilehash: 7b4aa42b20bfad5506d47c16038d1765f3ac8571
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36195854"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="9c626-103">Reimpostare il controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="9c626-103">Reset call admission control</span></span>

<span data-ttu-id="9c626-104">Se un pool di front-end legacy ospita il controllo di ammissione delle chiamate (CAC), è necessario trasferire il CAC ospitando un pool di Skype for Business Server 2019 prima di poter rimuovere il pool di front end legacy.</span><span class="sxs-lookup"><span data-stu-id="9c626-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="9c626-105">Per reimpostare CAC</span><span class="sxs-lookup"><span data-stu-id="9c626-105">To reset CAC</span></span>

1. <span data-ttu-id="9c626-106">Aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="9c626-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="9c626-107">Fare clic con il pulsante destro del mouse sul nodo del sito e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="9c626-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="9c626-108">In **impostazione controllo ammissione chiamata**verificare che sia selezionata l'opzione **Abilita controllo ammissione chiamata** .</span><span class="sxs-lookup"><span data-stu-id="9c626-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="9c626-109">In **pool Front-end per eseguire il controllo di ammissione di chiamata (CAC)** selezionare il pool di Skype for Business Server 2019 che ospita CAC e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="9c626-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="9c626-110">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="9c626-110">Publish the topology.</span></span>
    

