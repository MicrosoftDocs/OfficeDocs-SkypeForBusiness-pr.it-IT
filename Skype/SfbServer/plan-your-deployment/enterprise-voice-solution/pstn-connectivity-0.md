---
title: Pianificare la connettività PSTN in Skype for Business Server
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
ms.assetid: 280f684a-740a-443d-8ecf-574241382a42
description: Pianificare la connettività PSTN in VoIP aziendale in Skype for Business Server.
ms.openlocfilehash: 492f4e2cc71644cb1e9957f407a549cce5dbc31d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813566"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="9e3b2-103">Pianificare la connettività PSTN in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9e3b2-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="9e3b2-104">Pianificare la connettività PSTN in VoIP aziendale in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9e3b2-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="9e3b2-105">Una soluzione VoIP di livello aziendale deve essere in grado di garantire le chiamate da e verso la rete PSTN (Public Switched Telephone Network) senza alcun decadimento della qualità del servizio (QoS).</span><span class="sxs-lookup"><span data-stu-id="9e3b2-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="9e3b2-106">Gli utenti che e ricevono chiamate non devono essere a conoscenza della tecnologia sottostante: dal punto di vista dell'utente, una chiamata tra l'infrastruttura VoIP aziendale e la rete PSTN dovrebbe sembrare un'altra chiamata telefonica.</span><span class="sxs-lookup"><span data-stu-id="9e3b2-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="9e3b2-107">Skype for Business Server offre connettività PSTN affidabile e scalabile utilizzando le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9e3b2-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="9e3b2-108">**Trunk SIP** con un provider di servizi di telefonia Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="9e3b2-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="9e3b2-109">**Connessioni SIP dirette** con un gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="9e3b2-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="9e3b2-110">**Connessioni SIP dirette** con un PBX</span><span class="sxs-lookup"><span data-stu-id="9e3b2-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="9e3b2-111">A seconda delle dimensioni, della copertura geografica e dell'infrastruttura vocale esistente, un'azienda può usare una, due o addirittura tutte e tre le opzioni in ubicazioni diverse.</span><span class="sxs-lookup"><span data-stu-id="9e3b2-111">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span> <span data-ttu-id="9e3b2-112">Per informazioni dettagliate su queste opzioni, vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="9e3b2-112">For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="9e3b2-113">Contenuto della sezione</span><span class="sxs-lookup"><span data-stu-id="9e3b2-113">In this section</span></span>

- [<span data-ttu-id="9e3b2-114">SIP trunking in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9e3b2-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="9e3b2-115">Connessioni SIP dirette in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9e3b2-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="9e3b2-116">M:N trunk in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9e3b2-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="9e3b2-117">Regole di conversione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9e3b2-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="9e3b2-118">Pianificare il routing vocale in uscita in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9e3b2-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

