---
title: Associare Front End Server al server perimetrale
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/25/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AssociateFrontEndWithEdgePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f09c9b3e-1f5f-4486-8113-e62c10cff138
description: A ogni pool Front End può essere associato un solo server perimetrale o pool di server perimetrali. Quando si abilita l'accesso degli utenti esterni per un sito, è possibile fornire supporto per gli utenti remoti. È inoltre possibile abilitare il supporto per gli utenti federati, che può includere il supporto per gli utenti di specifici provider di connettività di messaggistica istantanea pubblica (ad esempio Windows Live) e il supporto per gli utenti anonimi.
ms.openlocfilehash: dcef84fdf63dc03c35a33650cca7f0f7c5de5900
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103222"
---
# <a name="associate-front-end-with-edge"></a><span data-ttu-id="d6239-105">Associare Front End Server al server perimetrale</span><span class="sxs-lookup"><span data-stu-id="d6239-105">Associate Front End With Edge</span></span>

<span data-ttu-id="d6239-106">A ogni pool Front End può essere associato un solo server perimetrale o pool di server perimetrali.</span><span class="sxs-lookup"><span data-stu-id="d6239-106">Each Front End pool can have only one Edge Server or Edge pool associated with it.</span></span> <span data-ttu-id="d6239-107">Quando si abilita l'accesso degli utenti esterni per un sito, è possibile fornire supporto per gli utenti remoti.</span><span class="sxs-lookup"><span data-stu-id="d6239-107">When you enable external user access for a site, you can provide support for remote users.</span></span> <span data-ttu-id="d6239-108">È inoltre possibile abilitare il supporto per gli utenti federati, che può includere il supporto per gli utenti di specifici provider di connettività di messaggistica istantanea pubblica (ad esempio Windows Live) e il supporto per gli utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="d6239-108">You can also enable support for federated users, which can include support for users of specific public instant messaging (IM) connectivity providers (such as Windows Live), and support for anonymous users.</span></span>

<span data-ttu-id="d6239-109">Tutti i pool in un sito e i pool di più siti centrali possono usare lo stesso server perimetrale, se l'uso non supera la capacità di questo server.</span><span class="sxs-lookup"><span data-stu-id="d6239-109">All pools at a site, and the pools of multiple central sites, can use the same Edge Server, if usage does not exceed the capacity of the Edge Server.</span></span> <span data-ttu-id="d6239-110">Per informazioni dettagliate sul monitoraggio, compresa la scalabilità, vedere [Planning for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="d6239-110">For details about monitoring, including scaling, see [Planning for External User Access](/previous-versions/office/lync-server-2013/lync-server-2013-planning-for-external-user-access) in the Planning documentation.</span></span> <span data-ttu-id="d6239-111">Per informazioni dettagliate sulla progettazione di una topologia per supportare l'accesso degli utenti esterni, vedere [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) nella documentazione relativa alla distribuzione.</span><span class="sxs-lookup"><span data-stu-id="d6239-111">For details about designing a topology to support external user access, see [Define Your Edge Topology](/previous-versions/office/lync-server-2013/lync-server-2013-define-your-edge-topology) in the Deployment documentation.</span></span>