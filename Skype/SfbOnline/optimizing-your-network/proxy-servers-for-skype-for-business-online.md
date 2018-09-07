---
title: Server proxy per Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Questo articolo dà informazioni su come utilizzare un server proxy con Skype for Business.
ms.openlocfilehash: 3d83e2f6d4eb2b88a52eb949217ac2f00c72acff
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23850014"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="636bb-103">Server proxy per Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="636bb-103">Proxy Servers for Skype for Business Online</span></span>

<span data-ttu-id="636bb-104">[] Questo articolo dà informazioni su come utilizzare un server proxy con Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="636bb-104">This article will help you with guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="636bb-105">Consigliamo di non usare un server proxy</span><span class="sxs-lookup"><span data-stu-id="636bb-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="636bb-p101">Per quanto riguarda il traffico di Skype for Business via proxy, Microsoft consiglia di bypassare il proxy. I proxy non rendono Skype for Business più sicuro perché il suo traffico è già crittografato.</span><span class="sxs-lookup"><span data-stu-id="636bb-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because its traffic is already encrypted.</span></span>
  
<span data-ttu-id="636bb-p102">Inoltre, avere un proxy può causare problemi. Possono essere introdotti in un ambiente problemi di prestazioni attraverso latenza e perdita di pacchetti. Problemi come questi porteranno a un'esperienza negativa in scenari di Skype for Business come audio e video, in cui i flussi in tempo reale sono essenziali.</span><span class="sxs-lookup"><span data-stu-id="636bb-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="636bb-111">Se devi usare un server proxy</span><span class="sxs-lookup"><span data-stu-id="636bb-111">If you need to use a proxy server</span></span>

<span data-ttu-id="636bb-p103">Alcune organizzazioni non hanno la possibilità di bypassare il proxy per il traffico di Skype for Business. Se questo è il tuo caso, dovrai tenere in considerazione i problemi di cui abbiamo parlato.</span><span class="sxs-lookup"><span data-stu-id="636bb-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="636bb-114">Microsoft inoltre consiglia:</span><span class="sxs-lookup"><span data-stu-id="636bb-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="636bb-115">Utilizzare la risoluzione DNS esterna</span><span class="sxs-lookup"><span data-stu-id="636bb-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="636bb-116">Utilizzare l'instradamento diretto basato su UDP</span><span class="sxs-lookup"><span data-stu-id="636bb-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="636bb-117">Consentire il traffico UDP</span><span class="sxs-lookup"><span data-stu-id="636bb-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="636bb-118">Seguire le altre raccomandazioni nelle nostre linee guida di rete:</span><span class="sxs-lookup"><span data-stu-id="636bb-118">Following the other recommendations in our Networking guidelines:</span></span>
    
  - [<span data-ttu-id="636bb-119">Qualità degli elementi multimediali e prestazioni della connessione di rete in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="636bb-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="636bb-120">Ottimizzare la rete per Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="636bb-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="636bb-121">Seguire queste indicazioni dovrebbe ridurre al minimo i potenziali problemi.</span><span class="sxs-lookup"><span data-stu-id="636bb-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="636bb-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="636bb-122">Related topics</span></span>

[<span data-ttu-id="636bb-123">Ottimizzare la rete per Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="636bb-123">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

  
 