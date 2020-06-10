---
title: Server proxy per Teams o Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: reference
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
- seo-marvel-apr2020
description: Questo articolo fornisce informazioni sull'uso di un server proxy con Microsoft teams o Skype for business.
ms.openlocfilehash: 3d8e2e067cce4214f51ee54ec08bafa1f4100770
ms.sourcegitcommit: f586d2765195dbd5b7cf65615a03a1cb098c5466
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/09/2020
ms.locfileid: "44665958"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="192c0-103">Server proxy per Teams o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="192c0-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="192c0-104">Questo articolo fornisce indicazioni sull'uso di un server proxy con team o Skype for business.</span><span class="sxs-lookup"><span data-stu-id="192c0-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="192c0-105">Consigliamo di non usare un server proxy</span><span class="sxs-lookup"><span data-stu-id="192c0-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="192c0-p101">Per quanto riguarda i team o il traffico di Skype for business sui proxy, Microsoft consiglia di ignorare i proxy. I proxy non rendono più sicure le squadre o Skype for business perché il traffico è già crittografato.</span><span class="sxs-lookup"><span data-stu-id="192c0-p101">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="192c0-p102">E avere un proxy può causare problemi. I problemi relativi alle prestazioni possono essere introdotti nell'ambiente attraverso la latenza e la perdita di pacchetti. I problemi come questi generano un'esperienza negativa in tali team o scenari di Skype for business come audio e video, dove i flussi in tempo reale sono essenziali.</span><span class="sxs-lookup"><span data-stu-id="192c0-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="192c0-111">Se devi usare un server proxy</span><span class="sxs-lookup"><span data-stu-id="192c0-111">If you need to use a proxy server</span></span>

<span data-ttu-id="192c0-p103">Alcune organizzazioni non hanno alcuna possibilità di ignorare un proxy per il traffico di teams o Skype for business. In questo caso, i problemi menzionati sopra devono essere tenuti in considerazione.</span><span class="sxs-lookup"><span data-stu-id="192c0-p103">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="192c0-114">Microsoft inoltre consiglia:</span><span class="sxs-lookup"><span data-stu-id="192c0-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="192c0-115">Utilizzare la risoluzione DNS esterna</span><span class="sxs-lookup"><span data-stu-id="192c0-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="192c0-116">Utilizzare l'instradamento diretto basato su UDP</span><span class="sxs-lookup"><span data-stu-id="192c0-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="192c0-117">Consentire il traffico UDP</span><span class="sxs-lookup"><span data-stu-id="192c0-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="192c0-118">Seguire le altre raccomandazioni nelle nostre linee guida per la rete: [preparare la rete dell'organizzazione per i team](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="192c0-118">Following the other recommendations in our networking guidelines: [Prepare your organization's network for Teams](prepare-network.md)</span></span>
  
    
<span data-ttu-id="192c0-119">Seguire queste indicazioni dovrebbe ridurre al minimo i potenziali problemi.</span><span class="sxs-lookup"><span data-stu-id="192c0-119">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="192c0-120">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="192c0-120">Related topics</span></span>

[<span data-ttu-id="192c0-121">Principi di connettività di rete Microsoft 365 e Office 365</span><span class="sxs-lookup"><span data-stu-id="192c0-121">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](https://aka.ms/pnc)

[<span data-ttu-id="192c0-122">Preparare la rete dell'organizzazione per Teams</span><span class="sxs-lookup"><span data-stu-id="192c0-122">Prepare your organization's network for Teams</span></span>](prepare-network.md)
