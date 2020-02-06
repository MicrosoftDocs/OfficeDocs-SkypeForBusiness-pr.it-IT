---
title: Componenti necessari per VoIP aziendale in Skype for Business Server
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
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Riepilogo dei componenti di VoIP aziendale in Skype for Business Server.
ms.openlocfilehash: a2e32e2301a404afd06038d438fbb62a13235d65
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803106"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="fa2d8-103">Componenti necessari per VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fa2d8-103">Components required for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="fa2d8-104">Riepilogo dei componenti di VoIP aziendale in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="fa2d8-105">Per distribuire VoIP aziendale, nella topologia sono necessari i componenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="fa2d8-106">Uno o più server di mediazione, che traducono la segnalazione e, in alcune configurazioni, elementi multimediali tra il server Skype for business, l'infrastruttura VoIP aziendale e un gateway PSTN (Public Switched Telephone Network) o un protocollo di avvio della sessione (SIP) trunk.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="fa2d8-107">I Mediation Server sono il componente più importante della distribuzione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="fa2d8-108">Per altre informazioni, Vedi [Componente Mediation Server in Skype for Business Server](mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="fa2d8-108">For more information, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>
    
    <span data-ttu-id="fa2d8-109">I server di mediazione possono essere collocati con Front End Server o installati come server autonomi.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="fa2d8-110">Componenti di connettività PSTN, che possono includere trunk SIP o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="fa2d8-111">Per altre informazioni, Vedi [componenti di connettività PSTN in Skype for Business Server](pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="fa2d8-111">For more information, see [PSTN connectivity components in Skype for Business Server](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="fa2d8-112">Edge Server, che consente di usare le funzionalità vocali aziendali dagli utenti quando si trovano al di fuori del firewall dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="fa2d8-113">Il servizio Access Edge offre una segnalazione SIP per le chiamate degli utenti di Skype for business che si trovano al di fuori del firewall dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="fa2d8-114">L'A/V Edge Services consente l'attraversamento multimediale di NAT e firewall.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="fa2d8-115">Un chiamante che usa un client Unified Communications (UC) all'esterno del firewall aziendale si basa sul servizio A/V Edge sia per le singole che per le conferenze telefoniche.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="fa2d8-116">Il servizio di autenticazione A/V è collocato e fornisce servizi di autenticazione per il servizio A/V Edge.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-116">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service.</span></span> <span data-ttu-id="fa2d8-117">Gli utenti esterni che tentano di connettersi al servizio a/V Edge richiedono un token di autenticazione fornito dal servizio di autenticazione A/V prima che le chiamate possano passare.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-117">Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="fa2d8-118">Inoltre, alcuni componenti Enterprise Voice vengono eseguiti nei server front-end.</span><span class="sxs-lookup"><span data-stu-id="fa2d8-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="fa2d8-119">Per informazioni dettagliate su questi componenti, vedere [componenti VoIP di front end server per Skype for Business Server](front-end-server-voip.md)</span><span class="sxs-lookup"><span data-stu-id="fa2d8-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)</span></span>
    

