---
title: Pianificare la connettività PSTN in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
ms.openlocfilehash: 12c18ba0be3f01651fb72ff325d7e51566da86ae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802546"
---
# <a name="plan-for-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="8c8e0-103">Pianificare la connettività PSTN in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8c8e0-103">Plan for PSTN connectivity in Skype for Business Server</span></span>
 
<span data-ttu-id="8c8e0-104">Pianificare la connettività PSTN in VoIP aziendale in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8c8e0-104">Plan for PSTN connectivity in Enterprise Voice in Skype for Business Server.</span></span>
  
<span data-ttu-id="8c8e0-105">Una soluzione VoIP di livello aziendale deve prevedere le chiamate da e verso la rete PSTN (Public Switched Telephone Network) senza alcun calo di qualità del servizio (QoS).</span><span class="sxs-lookup"><span data-stu-id="8c8e0-105">An enterprise-grade VoIP solution must provide for calls to and from the public switched telephone network (PSTN) without any decline in Quality of Service (QoS).</span></span> <span data-ttu-id="8c8e0-106">Gli utenti che dispongono e ricevono chiamate non devono essere a conoscenza della tecnologia sottostante: dal punto di vista dell'utente, una chiamata tra l'infrastruttura VoIP aziendale e la rete PSTN dovrebbe sembrare solo un'altra telefonata.</span><span class="sxs-lookup"><span data-stu-id="8c8e0-106">Users who place and receive calls should not be aware of the underlying technology: from the user's perspective, a call between the Enterprise Voice infrastructure and the PSTN should seem like just another phone call.</span></span>
  
<span data-ttu-id="8c8e0-107">Skype for Business Server offre connettività PSTN affidabile e scalabile usando le opzioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="8c8e0-107">Skype for Business Server provides reliable, scalable PSTN connectivity by using the following options:</span></span>
  
- <span data-ttu-id="8c8e0-108">**Trunk SIP** in un provider di servizi di telefonia Internet (ITSP)</span><span class="sxs-lookup"><span data-stu-id="8c8e0-108">**SIP trunks** to an Internet telephony service provider (ITSP)</span></span>
    
- <span data-ttu-id="8c8e0-109">**Connessioni SIP dirette** a un gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="8c8e0-109">**Direct SIP connections** to a PSTN gateway</span></span>
    
- <span data-ttu-id="8c8e0-110">**Connessioni SIP dirette** a un PBX</span><span class="sxs-lookup"><span data-stu-id="8c8e0-110">**Direct SIP connections** to a PBX</span></span>
    
<span data-ttu-id="8c8e0-111">A seconda delle dimensioni, della copertura geografica e dell'infrastruttura vocale esistente, un'organizzazione può usare una, due o anche tutte e tre le opzioni in varie posizioni.</span><span class="sxs-lookup"><span data-stu-id="8c8e0-111">Depending on its size, geographic coverage, and existing voice infrastructure, an enterprise may use one, two, or even all three of these options at various locations.</span></span> <span data-ttu-id="8c8e0-112">Per informazioni dettagliate su queste opzioni, vedere le sezioni seguenti.</span><span class="sxs-lookup"><span data-stu-id="8c8e0-112">For details about these options, see the following sections.</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="8c8e0-113">In questa sezione</span><span class="sxs-lookup"><span data-stu-id="8c8e0-113">In this section</span></span>

- [<span data-ttu-id="8c8e0-114">Trunking SIP in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8c8e0-114">SIP trunking in Skype for Business Server</span></span>](sip-trunking.md)
    
- [<span data-ttu-id="8c8e0-115">Connessioni SIP dirette in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8c8e0-115">Direct SIP connections in Skype for Business Server</span></span>](direct-sip.md)
    
- [<span data-ttu-id="8c8e0-116">Trunk M:N in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8c8e0-116">M:N trunk in Skype for Business Server</span></span>](m-n-trunk.md)
    
- [<span data-ttu-id="8c8e0-117">Regole di traduzione in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8c8e0-117">Translation rules in Skype for Business Server</span></span>](translation-rules.md)
    
- [<span data-ttu-id="8c8e0-118">Pianificare il routing vocale in uscita in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="8c8e0-118">Plan for outbound voice routing in Skype for Business Server</span></span>](outbound-voice-routing.md)
    

