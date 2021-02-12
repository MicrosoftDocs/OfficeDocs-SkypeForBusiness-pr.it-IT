---
title: Routing tra trunk in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: f687a548-1f2e-48ed-9745-a13dc1f3698f
description: Informazioni su come Skype for Business Server VoIP aziendale supporta il routing tra trunk.
ms.openlocfilehash: fc03f0df530be12ad1d08148850c11d8f92a2791
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825597"
---
# <a name="inter-trunk-routing-in-skype-for-business-server"></a><span data-ttu-id="f1258-103">Routing tra trunk in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="f1258-103">Inter-trunk routing in Skype for Business Server</span></span>
 
<span data-ttu-id="f1258-104">Informazioni su come Skype for Business Server VoIP aziendale supporta il routing tra trunk.</span><span class="sxs-lookup"><span data-stu-id="f1258-104">Learn how Skype for Business Server Enterprise Voice supports inter-trunk routing.</span></span>
  
<span data-ttu-id="f1258-105">Skype for Business Server fornisce la gestione delle sessioni di base tramite il supporto del routing tratrunk.</span><span class="sxs-lookup"><span data-stu-id="f1258-105">Skype for Business Server provides basic session management through the support of intertrunk routing.</span></span> <span data-ttu-id="f1258-106">Ciò consente a Skype for Business Server di fornire funzionalità di controllo delle chiamate ai sistemi di telefonia downstream.</span><span class="sxs-lookup"><span data-stu-id="f1258-106">This enables Skype for Business Server to provide call control functionalities to downstream telephony systems.</span></span> <span data-ttu-id="f1258-107">Il routing tra trunk può collegare un IP-PBX a un gateway PSTN (Public Switched Telephone Network) in modo che le chiamate da un telefono PBX (Private Branch Exchange) possano essere instradate verso la rete PSTN e le chiamate in entrata alla rete PSTN possano essere instradate verso un telefono PBX.</span><span class="sxs-lookup"><span data-stu-id="f1258-107">Intertrunk routing can interconnect an IP-PBX to a public switched telephone network (PSTN) gateway so that calls from a private branch exchange (PBX) phone can be routed to the PSTN, and incoming PSTN calls can be routed to a PBX phone.</span></span> <span data-ttu-id="f1258-108">Analogamente, Skype for Business Server può interconnettere due o più sistemi IP-PBX in modo che le chiamate possano essere effettuate e ricevute tra telefoni PBX dai diversi sistemi IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="f1258-108">Similarly, Skype for Business Server can interconnect two or more IP-PBX systems so that calls can be placed and received between PBX phones from the different IP-PBX systems.</span></span> 
  
<span data-ttu-id="f1258-109">Nella figura seguente viene illustrato Skype for Business Server che fornisce l'interconnettività tra un gateway PSTN e un IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="f1258-109">The following figure illustrates Skype for Business Server providing interconnectivity between a PSTN gateway and an IP-PBX.</span></span>
  
![Diagramma del gateway PSTN/IP-PBX connesso a Lync Server](../../media/inter_trunk01.jpg)
  
<span data-ttu-id="f1258-111">Nella figura seguente viene illustrato Skype for Business Server che connette due sistemi IP-PBX.</span><span class="sxs-lookup"><span data-stu-id="f1258-111">The next figure illustrates Skype for Business Server connecting two IP-PBX systems.</span></span>
  
![Diagramma dei sistemi IP-PAX di Lync Server](../../media/inter_trunk02.jpg)
  

