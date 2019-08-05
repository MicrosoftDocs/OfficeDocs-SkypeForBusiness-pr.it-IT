---
title: Routing inter-trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Informazioni su come Skype for Business Server VoIP aziendale supporta il routing tra trunk.
ms.openlocfilehash: f590463eced61cf2e8b19a27f7cfc2dd648c63c1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187682"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="49963-103">Routing inter-trunk in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="49963-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="49963-104">Informazioni su come Skype for Business Server VoIP aziendale supporta il routing tra trunk.</span><span class="sxs-lookup"><span data-stu-id="49963-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="49963-105">Skype for Business Server offre una gestione delle sessioni di base tramite il supporto del routing intertrunk.</span><span class="sxs-lookup"><span data-stu-id="49963-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="49963-106">In questo modo Skype for Business Server offre funzionalità per il controllo delle chiamate ai sistemi di telefonia downstream.</span><span class="sxs-lookup"><span data-stu-id="49963-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="49963-107">Il routing intertrunk può interconnettere un IP-PBX a un gateway PSTN (Public Switched Telephone Network) in modo che le chiamate da un telefono PBX (Private Branch Exchange) possano essere indirizzate alla rete PSTN e le chiamate PSTN in arrivo possano essere indirizzate a un telefono PBX.</span><span class="sxs-lookup"><span data-stu-id="49963-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="49963-108">Analogamente, Skype for Business Server può interconnettere due o più sistemi IP-PBX in modo che le chiamate possano essere inserite e ricevute tra i telefoni PBX dei diversi sistemi IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="49963-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="49963-109">La figura seguente illustra Skype for Business Server che fornisce l'interconnettività tra un gateway PSTN e un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="49963-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Diagramma delle connessioni tra Lync Server e gateway PSTN/IP-PBX](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="49963-111">Nella figura seguente viene illustrato Skype for Business Server che connette due sistemi IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="49963-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Diagramma delle interconnessioni tra Lync Server e sistemi IP-PAX](../../media/inter_trunk02.jpg)
  

