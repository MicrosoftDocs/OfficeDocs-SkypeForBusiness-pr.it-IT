---
title: Reimpostare il controllo di ammissione di chiamata
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se un pool di front-end legacy ospita il controllo di ammissione delle chiamate (CAC), è necessario trasferire il CAC ospitando un pool di Skype for Business Server 2019 prima di poter rimuovere il pool di front end legacy.
ms.openlocfilehash: 812391eda436906020c41b14a53c8ea18c4b1aee
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36241793"
---
# <a name="reset-call-admission-control"></a><span data-ttu-id="d06c2-103">Reimpostare il controllo di ammissione di chiamata</span><span class="sxs-lookup"><span data-stu-id="d06c2-103">Reset call admission control</span></span>

<span data-ttu-id="d06c2-104">Se un pool di front-end legacy ospita il controllo di ammissione delle chiamate (CAC), è necessario trasferire il CAC ospitando un pool di Skype for Business Server 2019 prima di poter rimuovere il pool di front end legacy.</span><span class="sxs-lookup"><span data-stu-id="d06c2-104">If a legacy Front End pool is hosting call admission control (CAC), you must move CAC hosting to a Skype for Business Server 2019 pool before you can remove the legacy Front End pool.</span></span>
  
### <a name="to-reset-cac"></a><span data-ttu-id="d06c2-105">Per reimpostare CAC</span><span class="sxs-lookup"><span data-stu-id="d06c2-105">To reset CAC</span></span>

1. <span data-ttu-id="d06c2-106">Aprire Generatore di topologie.</span><span class="sxs-lookup"><span data-stu-id="d06c2-106">Open Topology Builder.</span></span>
    
2. <span data-ttu-id="d06c2-107">Fare clic con il pulsante destro del mouse sul nodo del sito e quindi scegliere **modifica proprietà**.</span><span class="sxs-lookup"><span data-stu-id="d06c2-107">Right-click the site node, and then click **Edit Properties**.</span></span>
    
3. <span data-ttu-id="d06c2-108">In **impostazione controllo ammissione chiamata**verificare che sia selezionata l'opzione **Abilita controllo ammissione chiamata** .</span><span class="sxs-lookup"><span data-stu-id="d06c2-108">Under **Call Admission Control setting**, make sure **Enable Call Admission Control** is selected.</span></span> 
    
4. <span data-ttu-id="d06c2-109">In **pool Front-end per eseguire il controllo di ammissione di chiamata (CAC)** selezionare il pool di Skype for Business Server 2019 che ospita CAC e quindi fare clic su **OK**.</span><span class="sxs-lookup"><span data-stu-id="d06c2-109">Under **Front End pool to run call admission control (CAC)**, select the Skype for Business Server 2019 pool that is to host CAC, and then click **OK**.</span></span>
    
5. <span data-ttu-id="d06c2-110">Pubblicare la topologia.</span><span class="sxs-lookup"><span data-stu-id="d06c2-110">Publish the topology.</span></span>
    

