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
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Optimization
description: Questo articolo fornisce informazioni sull'uso di un server proxy con Skype for Business.
ms.openlocfilehash: 09ed98c5f69d6e244a5f87125e4ad607e4d16226
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52240415"
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="9b9b8-103">Server proxy per Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="9b9b8-103">Proxy servers for Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

<span data-ttu-id="9b9b8-104">Questo articolo fornisce indicazioni sull'uso di un server proxy con Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9b9b8-104">This article provides guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="9b9b8-105">Consigliamo di non usare un server proxy</span><span class="sxs-lookup"><span data-stu-id="9b9b8-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="9b9b8-106">Per quanto riguarda il traffico di Skype for Business via proxy, Microsoft consiglia di bypassare il proxy.</span><span class="sxs-lookup"><span data-stu-id="9b9b8-106">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="9b9b8-107">I proxy non rendono più sicuro Skype for Business perché il traffico è già crittografato.</span><span class="sxs-lookup"><span data-stu-id="9b9b8-107">Proxies don't make Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="9b9b8-108">Inoltre, avere un proxy può causare problemi.</span><span class="sxs-lookup"><span data-stu-id="9b9b8-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="9b9b8-109">Possono essere introdotti in un ambiente problemi di prestazioni attraverso latenza e perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="9b9b8-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="9b9b8-110">Problemi come questi comportano un'esperienza negativa in scenari Teams o Skype for Business audio e video, in cui i flussi in tempo reale sono essenziali.</span><span class="sxs-lookup"><span data-stu-id="9b9b8-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="9b9b8-111">Se devi usare un server proxy</span><span class="sxs-lookup"><span data-stu-id="9b9b8-111">If you need to use a proxy server</span></span>

<span data-ttu-id="9b9b8-p103">Alcune organizzazioni non hanno la possibilità di bypassare il proxy per il traffico di Skype for Business. Se questo è il tuo caso, dovrai tenere in considerazione i problemi di cui abbiamo parlato.</span><span class="sxs-lookup"><span data-stu-id="9b9b8-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="9b9b8-114">Microsoft inoltre consiglia:</span><span class="sxs-lookup"><span data-stu-id="9b9b8-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="9b9b8-115">Utilizzare la risoluzione DNS esterna</span><span class="sxs-lookup"><span data-stu-id="9b9b8-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="9b9b8-116">Utilizzare l'instradamento diretto basato su UDP</span><span class="sxs-lookup"><span data-stu-id="9b9b8-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="9b9b8-117">Consentire il traffico UDP</span><span class="sxs-lookup"><span data-stu-id="9b9b8-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="9b9b8-118">Seguendo le altre raccomandazioni nelle linee guida di rete:</span><span class="sxs-lookup"><span data-stu-id="9b9b8-118">Following the other recommendations in our networking guidelines:</span></span>
    
  - [<span data-ttu-id="9b9b8-119">Qualità degli elementi multimediali e prestazioni della connessione di rete in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="9b9b8-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](media-quality-and-network-connectivity-performance.md)
    
  - [<span data-ttu-id="9b9b8-120">Ottimizzare la rete per Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="9b9b8-120">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
    
<span data-ttu-id="9b9b8-121">Seguire queste indicazioni dovrebbe ridurre al minimo i potenziali problemi.</span><span class="sxs-lookup"><span data-stu-id="9b9b8-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="9b9b8-122">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="9b9b8-122">Related topics</span></span>

[<span data-ttu-id="9b9b8-123">Ottimizzare la rete per Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="9b9b8-123">Optimizing your network for Skype for Business Online</span></span>](optimizing-your-network.md)
 
