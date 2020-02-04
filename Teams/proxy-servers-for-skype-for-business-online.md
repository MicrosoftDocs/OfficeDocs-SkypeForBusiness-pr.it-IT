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
- NOCSH
ms.custom:
- Optimization
description: Questo articolo fornisce informazioni sull'uso di un server proxy con team o Skype for business.
ms.openlocfilehash: e71dd21d8d359093b5dada84a8d0788e8dff6af3
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/03/2020
ms.locfileid: "41708832"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="c0955-103">Server proxy per Teams o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c0955-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="c0955-104">Questo articolo fornisce indicazioni sull'uso di un server proxy con team o Skype for business.</span><span class="sxs-lookup"><span data-stu-id="c0955-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="c0955-105">Consigliamo di non usare un server proxy</span><span class="sxs-lookup"><span data-stu-id="c0955-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="c0955-p101">Per quanto riguarda i team o il traffico di Skype for business sui proxy, Microsoft consiglia di ignorare i proxy. I proxy non rendono più sicure le squadre o Skype for business perché il traffico è già crittografato.</span><span class="sxs-lookup"><span data-stu-id="c0955-p101">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="c0955-p102">E avere un proxy può causare problemi. I problemi relativi alle prestazioni possono essere introdotti nell'ambiente attraverso la latenza e la perdita di pacchetti. I problemi come questi generano un'esperienza negativa in tali team o scenari di Skype for business come audio e video, dove i flussi in tempo reale sono essenziali.</span><span class="sxs-lookup"><span data-stu-id="c0955-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="c0955-111">Se devi usare un server proxy</span><span class="sxs-lookup"><span data-stu-id="c0955-111">If you need to use a proxy server</span></span>

<span data-ttu-id="c0955-p103">Alcune organizzazioni non hanno alcuna possibilità di ignorare un proxy per il traffico di teams o Skype for business. In questo caso, i problemi menzionati sopra devono essere tenuti in considerazione.</span><span class="sxs-lookup"><span data-stu-id="c0955-p103">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="c0955-114">Microsoft inoltre consiglia:</span><span class="sxs-lookup"><span data-stu-id="c0955-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="c0955-115">Utilizzare la risoluzione DNS esterna</span><span class="sxs-lookup"><span data-stu-id="c0955-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="c0955-116">Utilizzare l'instradamento diretto basato su UDP</span><span class="sxs-lookup"><span data-stu-id="c0955-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="c0955-117">Consentire il traffico UDP</span><span class="sxs-lookup"><span data-stu-id="c0955-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="c0955-118">Seguire le altre raccomandazioni nelle nostre linee guida per la rete:</span><span class="sxs-lookup"><span data-stu-id="c0955-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="c0955-119">Qualità degli elementi multimediali e prestazioni della connessione di rete in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="c0955-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="c0955-120">Ottimizzare la rete per Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="c0955-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="c0955-121">Seguire queste indicazioni dovrebbe ridurre al minimo i potenziali problemi.</span><span class="sxs-lookup"><span data-stu-id="c0955-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c0955-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c0955-122">Related topics</span></span>

[<span data-ttu-id="c0955-123">Ottimizzare la rete per Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="c0955-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 