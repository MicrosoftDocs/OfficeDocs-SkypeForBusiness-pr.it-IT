---
title: Server proxy per Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: jastark
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 7acaf2c2-35fa-490f-84cd-822e446e0fc7
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: "Questo articolo dà informazioni su come utilizzare un server proxy con Skype for Business."
ms.openlocfilehash: 29438474524c7c1e518fb3130fdaf436e562d76e
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2018
---
# <a name="proxy-servers-for-skype-for-business-online"></a><span data-ttu-id="f0f32-103">Server proxy per Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="f0f32-103">Proxy Servers for Skype for Business Online</span></span>

<span data-ttu-id="f0f32-104">[] Questo articolo dà informazioni su come utilizzare un server proxy con Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f0f32-104">This article will help you with guidance about using a proxy server with Skype for Business.</span></span>
  
## <a name="not-using-a-proxy-server-is-recommended"></a><span data-ttu-id="f0f32-105">Consigliamo di non usare un server proxy</span><span class="sxs-lookup"><span data-stu-id="f0f32-105">Not using a proxy server is recommended</span></span>

<span data-ttu-id="f0f32-p101">Per quanto riguarda il traffico di Skype for Business via proxy, Microsoft consiglia di bypassare il proxy. I proxy non rendono Skype for Business più sicuro perché il suo traffico è già crittografato.</span><span class="sxs-lookup"><span data-stu-id="f0f32-p101">When it comes to Skype for Business traffic over proxies, Microsoft recommends bypassing proxies. Proxies don't make Skype for Business more secure because its traffic is already encrypted.</span></span>
  
<span data-ttu-id="f0f32-p102">Inoltre, avere un proxy può causare problemi. Possono essere introdotti in un ambiente problemi di prestazioni attraverso latenza e perdita di pacchetti. Problemi come questi porteranno a un'esperienza negativa in scenari di Skype for Business come audio e video, in cui i flussi in tempo reale sono essenziali.</span><span class="sxs-lookup"><span data-stu-id="f0f32-p102">And having a proxy can cause issues. Performance-related problems can be introduced to the environment through latency and packet loss. Issues such as these will result in a negative experience in such Skype for Business scenarios as audio and video, where real-time streams are essential.</span></span>
  
## <a name="if-you-need-to-use-a-proxy-server"></a><span data-ttu-id="f0f32-111">Se devi usare un server proxy</span><span class="sxs-lookup"><span data-stu-id="f0f32-111">If you need to use a proxy server</span></span>

<span data-ttu-id="f0f32-p103">Alcune organizzazioni non hanno la possibilità di bypassare il proxy per il traffico di Skype for Business. Se questo è il tuo caso, dovrai tenere in considerazione i problemi di cui abbiamo parlato.</span><span class="sxs-lookup"><span data-stu-id="f0f32-p103">Some organizations have no option to bypass a proxy for Skype for Business traffic. If that's the case for you, the problems mentioned above need to be kept in mind.</span></span>
  
<span data-ttu-id="f0f32-114">Microsoft inoltre consiglia:</span><span class="sxs-lookup"><span data-stu-id="f0f32-114">Microsoft also strongly recommends:</span></span>
  
- <span data-ttu-id="f0f32-115">Utilizzare la risoluzione DNS esterna</span><span class="sxs-lookup"><span data-stu-id="f0f32-115">Using external DNS resolution</span></span>
    
- <span data-ttu-id="f0f32-116">Utilizzare l'instradamento diretto basato su UDP</span><span class="sxs-lookup"><span data-stu-id="f0f32-116">Using direct UDP based routing</span></span>
    
- <span data-ttu-id="f0f32-117">Consentire il traffico UDP</span><span class="sxs-lookup"><span data-stu-id="f0f32-117">Allowing UDP traffic</span></span>
    
- <span data-ttu-id="f0f32-118">Seguire le altre raccomandazioni nelle nostre linee guida di rete:</span><span class="sxs-lookup"><span data-stu-id="f0f32-118">Following the other recommendations in our Networking guidelines:</span></span>
    
  - [<span data-ttu-id="f0f32-119">Qualità degli elementi multimediali e prestazioni della connessione di rete in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="f0f32-119">Media Quality and Network Connectivity Performance in Skype for Business Online</span></span>](https://support.office.com/en-us/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
    
  - [<span data-ttu-id="f0f32-120">Ottimizzare la rete per Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="f0f32-120">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)
    
<span data-ttu-id="f0f32-121">Seguire queste indicazioni dovrebbe ridurre al minimo i potenziali problemi.</span><span class="sxs-lookup"><span data-stu-id="f0f32-121">Following this guidance should minimize potential problems.</span></span>
  
## <a name="proxy-vendors-with-built-in-skype-for-business-support-or-configuration-options"></a><span data-ttu-id="f0f32-122">Fornitori di proxy con supporto Skype for Business integrato o opzioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="f0f32-122">Proxy vendors with built-in Skype for Business support or configuration options</span></span>

<span data-ttu-id="f0f32-123">Questa sezione contiene informazioni sui fornitori di proxy che forniscono prodotti o servizi che si sono dimostrati compatibili con il traffico di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="f0f32-123">This section will contain information about proxy vendors who provide products or services that are proven to work successfully with Skype for Business traffic.</span></span>
  
<span data-ttu-id="f0f32-124">Per le organizzazioni che utilizzano **le soluzioni Bluecoat Proxy**, è stato pubblicato un nuovo firmware che risolve diversi problemi con:</span><span class="sxs-lookup"><span data-stu-id="f0f32-124">For organizations using **Bluecoat Proxy solutions**, a new firmware has been released which addresses several issues with:</span></span>
    
  - <span data-ttu-id="f0f32-125">intercettazione SSL</span><span class="sxs-lookup"><span data-stu-id="f0f32-125">SSL interception</span></span>
    
  - <span data-ttu-id="f0f32-126">controlli OCSP/SRL</span><span class="sxs-lookup"><span data-stu-id="f0f32-126">OCSP/SRL checks</span></span>
    
  - <span data-ttu-id="f0f32-127">SIP via TLS</span><span class="sxs-lookup"><span data-stu-id="f0f32-127">SIP over TLS</span></span>
    
  - <span data-ttu-id="f0f32-128">supporto per TURN</span><span class="sxs-lookup"><span data-stu-id="f0f32-128">support for TURN</span></span>
    
<span data-ttu-id="f0f32-p104">Il supporto nativo di Bluecoat per Skype for Business può essere attivato con facilità, e permette l'identificazione del traffico interessato e la sua corretta gestione. Questo garantisce autenticazione, segnalazione e flusso di traffico multimediale ottimali per offrire un'ottima esperienza utente senza problemi di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f0f32-p104">Bluecoat's native support for Skype for Business can easily be enabled, allowing for the identification of relevant traffic, and managing it appropriately. This ensures optimal authentication, signaling, and media traffic flow, to provide a great user experience without security concerns.</span></span>
    
<span data-ttu-id="f0f32-131">Consultare il collegamento seguente se Proxy Bluecoat è una parte della topologia di rete: https://support.symantec.com/en_US/article.DOC9757.html</span><span class="sxs-lookup"><span data-stu-id="f0f32-131">Please refer to the following link if Bluecoat Proxy is a part of your network topology: https://support.symantec.com/en_US/article.DOC9757.html</span></span>

## <a name="related-topics"></a><span data-ttu-id="f0f32-132">See also</span><span class="sxs-lookup"><span data-stu-id="f0f32-132">Related topics</span></span>

[<span data-ttu-id="f0f32-133">Ottimizzare la rete per Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="f0f32-133">Optimizing your network for Skype for Business Online</span></span>](https://support.office.com/en-us/article/Optimizing-your-network-for-Skype-for-Business-Online-b363bdca-b00d-4150-96c3-ec7eab5a8a43)

## <a name="feedback"></a><span data-ttu-id="f0f32-134">Commenti e suggerimenti?</span><span class="sxs-lookup"><span data-stu-id="f0f32-134">Feedback?</span></span>
<span data-ttu-id="f0f32-135">Per inviare commenti e suggerimenti prodotto o per consentire us sapere come ci si limita, vedere [Skype per commenti e suggerimenti Business](https://www.skypefeedback.com).</span><span class="sxs-lookup"><span data-stu-id="f0f32-135">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>