---
title: Routing tra trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype for Business Server fornisce la gestione delle sessioni di base tramite il supporto del routing tra trunk. '
ms.openlocfilehash: d509b4f9de489e65ed8443fd1aad92e24363fb55
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814126"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="e843a-103">Routing tra trunk in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e843a-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="e843a-104">Skype for Business Server fornisce la gestione delle sessioni di base tramite il supporto del routing tra trunk.</span><span class="sxs-lookup"><span data-stu-id="e843a-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="e843a-105">Questa funzionalità consente a Skype for Business Server di fornire funzionalità di controllo delle chiamate ai sistemi di telefonia downstream.</span><span class="sxs-lookup"><span data-stu-id="e843a-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="e843a-106">Il routing tra trunk può collegare un IP-PBX a un gateway PSTN (Public Switched Telephone Network) in modo che le chiamate da un telefono PBX (Private Branch Exchange) possano essere instradate verso la rete PSTN e le chiamate in entrata alla rete PSTN possano essere instradate verso un telefono PBX.</span><span class="sxs-lookup"><span data-stu-id="e843a-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="e843a-107">Analogamente, Skype for Business Server può interconnettere due o più sistemi IP-PBX in modo che le chiamate possano essere inserite e ricevute tra i telefoni PBX dei diversi sistemi IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="e843a-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="e843a-108">Nella figura seguente viene illustrato Skype for Business Server che fornisce l'interconnettività tra un gateway PSTN e un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="e843a-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![Interconnettività tra un gateway PSTN e un IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="e843a-110">Nella figura seguente viene illustrato Skype for Business Server che collega due sistemi IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="e843a-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![Skype for Business Server che collega due sistemi IP-PGX](../../media/two-ip-pbx-systems.jpg)

