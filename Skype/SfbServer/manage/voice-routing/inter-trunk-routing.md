---
title: Routing inter-trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 'Skype for Business Server offre una gestione delle sessioni di base tramite il supporto del routing intertrunk. '
ms.openlocfilehash: c3381c6ae6bd86c416e6bd3349cf54d6fb530a08
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41816966"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="18a94-103">Routing inter-trunk in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="18a94-103">Inter-trunk routing in Skype for Business Server</span></span>

<span data-ttu-id="18a94-104">Skype for Business Server offre una gestione delle sessioni di base tramite il supporto del routing intertrunk.</span><span class="sxs-lookup"><span data-stu-id="18a94-104">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="18a94-105">Questa funzionalità consente a Skype for Business Server di specificare le funzionalità di controllo delle chiamate per i sistemi di telefonia downstream.</span><span class="sxs-lookup"><span data-stu-id="18a94-105">This capability enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="18a94-106">Il routing intertrunk può interconnettere un IP-PBX a un gateway PSTN (Public Switched Telephone Network) in modo che le chiamate da un telefono PBX (Private Branch Exchange) possano essere indirizzate alla rete PSTN e le chiamate PSTN in arrivo possano essere indirizzate a un telefono PBX.</span><span class="sxs-lookup"><span data-stu-id="18a94-106">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="18a94-107">Analogamente, Skype for Business Server può interconnettere due o più sistemi IP-PBX in modo che le chiamate possano essere inserite e ricevute tra i telefoni PBX dei diversi sistemi IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="18a94-107">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 


<span data-ttu-id="18a94-108">La figura seguente illustra Skype for Business Server che fornisce l'interconnettività tra un gateway PSTN e un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="18a94-108">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>

![Interconnettività tra un gateway PSTN e un IP-PBX](../../media/pstn-gateway-ip-pbx.jpg)

<span data-ttu-id="18a94-110">Nella figura seguente viene illustrato Skype for Business Server che connette due sistemi IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="18a94-110">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>

![Skype for Business Server che connette due sistemi IP-PGX](../../media/two-ip-pbx-systems.jpg)

