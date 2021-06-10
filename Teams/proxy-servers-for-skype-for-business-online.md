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
description: Questo articolo fornisce informazioni sull'uso di un server proxy con Microsoft Teams o Skype for Business.
ms.openlocfilehash: 0e2089cfa327a610c3ee98f1f20862a28939fd0c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51117724"
---
# <a name="proxy-servers-for-teams-or-skype-for-business-online"></a><span data-ttu-id="73af0-103">Server proxy per Teams o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="73af0-103">Proxy servers for Teams or Skype for Business Online</span></span>

<span data-ttu-id="73af0-104">Questo articolo fornisce indicazioni sull'uso di un server proxy con Teams o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="73af0-104">This article provides guidance about using a proxy server with Teams or Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="73af0-105">Consigliamo di non usare un server proxy</span><span class="sxs-lookup"><span data-stu-id="73af0-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="73af0-106">Per quanto riguarda il traffico Teams o Skype for Business proxy, Microsoft consiglia di ignorare i proxy.</span><span class="sxs-lookup"><span data-stu-id="73af0-106">When it comes to Teams or Skype for Business traffic over proxies, Microsoft recommends bypassing proxies.</span></span> <span data-ttu-id="73af0-107">I proxy non rendono più Teams o Skype for Business perché il traffico è già crittografato.</span><span class="sxs-lookup"><span data-stu-id="73af0-107">Proxies don't make Teams or Skype for Business more secure because the traffic is already encrypted.</span></span>
  
<span data-ttu-id="73af0-108">Inoltre, avere un proxy può causare problemi.</span><span class="sxs-lookup"><span data-stu-id="73af0-108">And having a proxy can cause issues.</span></span> <span data-ttu-id="73af0-109">Possono essere introdotti in un ambiente problemi di prestazioni attraverso latenza e perdita di pacchetti.</span><span class="sxs-lookup"><span data-stu-id="73af0-109">Performance-related problems can be introduced to the environment through latency and packet loss.</span></span> <span data-ttu-id="73af0-110">Problemi come questi comportano un'esperienza negativa in scenari Teams o Skype for Business audio e video, in cui i flussi in tempo reale sono essenziali.</span><span class="sxs-lookup"><span data-stu-id="73af0-110">Issues such as these will result in a negative experience in such Teams or Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="73af0-111">Se devi usare un server proxy</span><span class="sxs-lookup"><span data-stu-id="73af0-111">If you need to use a proxy server</span></span>

<span data-ttu-id="73af0-112">Alcune organizzazioni non hanno alcuna opzione per ignorare un proxy per Teams o Skype for Business traffico.</span><span class="sxs-lookup"><span data-stu-id="73af0-112">Some organizations have no option to bypass a proxy for Teams or Skype for Business traffic.</span></span> <span data-ttu-id="73af0-113">Se questo è il tuo caso, dovrai tenere in considerazione i problemi di cui abbiamo parlato.</span><span class="sxs-lookup"><span data-stu-id="73af0-113">If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="73af0-114">Microsoft inoltre consiglia:</span><span class="sxs-lookup"><span data-stu-id="73af0-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="73af0-115">Utilizzare la risoluzione DNS esterna</span><span class="sxs-lookup"><span data-stu-id="73af0-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="73af0-116">Utilizzare l'instradamento diretto basato su UDP</span><span class="sxs-lookup"><span data-stu-id="73af0-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="73af0-117">Consentire il traffico UDP</span><span class="sxs-lookup"><span data-stu-id="73af0-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="73af0-118">Seguire gli altri suggerimenti nelle linee guida di rete: Preparare la rete [dell'organizzazione per Teams](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="73af0-118">Following the other recommendations in our networking guidelines: [Prepare your organization's network for Teams](prepare-network.md)</span></span>
  
    
<span data-ttu-id="73af0-119">Seguire queste indicazioni dovrebbe ridurre al minimo i potenziali problemi.</span><span class="sxs-lookup"><span data-stu-id="73af0-119">Following this guidance should minimize potential problems.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="73af0-120">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="73af0-120">Related topics</span></span>

[<span data-ttu-id="73af0-121">Principi di connettività di rete di Microsoft 365 e Office 365</span><span class="sxs-lookup"><span data-stu-id="73af0-121">Microsoft 365 and Office 365 Network Connectivity Principles</span></span>](/microsoft-365/enterprise/microsoft-365-network-connectivity-principles)

[<span data-ttu-id="73af0-122">Preparare la rete dell'organizzazione per Teams</span><span class="sxs-lookup"><span data-stu-id="73af0-122">Prepare your organization's network for Teams</span></span>](prepare-network.md)