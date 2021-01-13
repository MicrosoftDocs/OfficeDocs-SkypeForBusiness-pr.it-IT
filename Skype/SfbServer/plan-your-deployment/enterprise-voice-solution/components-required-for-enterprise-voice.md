---
title: Componenti necessari per VoIP aziendale in Skype for Business Server
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
ms.assetid: ee219976-c39a-4b2f-988d-886c339700f7
description: Un riepilogo dei componenti di VoIP aziendale in Skype for Business Server.
ms.openlocfilehash: 1a7f13cc171af44ecbd0f48706ec12d882e50b33
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49825826"
---
# <a name="components-required-for-enterprise-voice-in-skype-for-business-server"></a><span data-ttu-id="777d4-103">Componenti necessari per VoIP aziendale in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="777d4-103">Components required for Enterprise Voice in Skype for Business Server</span></span>
 
<span data-ttu-id="777d4-104">Un riepilogo dei componenti di VoIP aziendale in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="777d4-104">A summary of the Enterprise Voice components in Skype for Business Server.</span></span>
  
<span data-ttu-id="777d4-105">Per distribuire VoIP aziendale, nella topologia sono necessari i componenti seguenti.</span><span class="sxs-lookup"><span data-stu-id="777d4-105">To deploy Enterprise Voice, the following components are required in your topology.</span></span> 
  
- <span data-ttu-id="777d4-106">Uno o più Mediation Server, che traducono la segnalazione e, in alcune configurazioni, i contenuti multimediali tra il server Skype for business, l'infrastruttura VoIP aziendale e un gateway PSTN (Public Switched Telephone Network) o un trunk SIP (Session Initiation Protocol).</span><span class="sxs-lookup"><span data-stu-id="777d4-106">One or more Mediation Servers, which translate signaling and, in some configurations, media between your internal Skype for Business Server, Enterprise Voice infrastructure and a public switched telephone network (PSTN) gateway or a Session Initiation Protocol (SIP) trunk.</span></span> <span data-ttu-id="777d4-107">I Mediation Server sono il componente più cruciale della distribuzione di VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="777d4-107">The Mediation Servers are the most crucial component in your Enterprise Voice deployment.</span></span> <span data-ttu-id="777d4-108">Per ulteriori informazioni, vedere [Componente Mediation Server in Skype for Business Server](mediation-server.md).</span><span class="sxs-lookup"><span data-stu-id="777d4-108">For more information, see [Mediation Server component in Skype for Business Server](mediation-server.md).</span></span>
    
    <span data-ttu-id="777d4-109">I Mediation Server possono essere collocati con Front End Server o essere installati come server autonomi.</span><span class="sxs-lookup"><span data-stu-id="777d4-109">Mediation Servers can be collocated with Front End Servers or installed as standalone servers.</span></span>
    
- <span data-ttu-id="777d4-110">Componenti di connettività PSTN, che possono includere trunk SIP o gateway PSTN.</span><span class="sxs-lookup"><span data-stu-id="777d4-110">PSTN connectivity components, which can include SIP trunks or PSTN gateways.</span></span> <span data-ttu-id="777d4-111">Per ulteriori informazioni, vedere [componenti di connettività PSTN in Skype for Business Server](pstn-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="777d4-111">For more information, see [PSTN connectivity components in Skype for Business Server](pstn-connectivity.md).</span></span>
    
- <span data-ttu-id="777d4-112">Server perimetrali, che consente l'utilizzo di funzionalità VoIP aziendale da parte degli utenti quando si trovano all'esterno del firewall dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="777d4-112">Edge Servers, which enables the use of Enterprise Voice features by your users when they are outside your organization's firewall.</span></span> 
    
    <span data-ttu-id="777d4-113">Il servizio Access Edge fornisce la segnalazione SIP per le chiamate provenienti da utenti Skype for business che si trovano all'esterno del firewall dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="777d4-113">The Access Edge service provides SIP signaling for calls from Skype for Business users who are outside your organization's firewall.</span></span> <span data-ttu-id="777d4-114">Il servizio A/V Edge consente l'attraversamento del contenuto multimediale in NAT e nei firewall.</span><span class="sxs-lookup"><span data-stu-id="777d4-114">The A/V Edge service enables media traversal of NAT and firewalls.</span></span> <span data-ttu-id="777d4-115">Un chiamante che utilizza un client per le comunicazioni unificate dall'esterno del firewall aziendale utilizza il servizio A/V Edge per singole chiamate e conferenze telefoniche.</span><span class="sxs-lookup"><span data-stu-id="777d4-115">A caller who uses a unified communications (UC) client from outside the corporate firewall relies on the A/V Edge service for both individual and conference calls.</span></span>
    
    <span data-ttu-id="777d4-p104">Il servizio di autenticazione A/V si trova nella stessa posizione del servizio A/V Edge e offre servizi di autenticazione per questo servizio. Gli utenti esterni che tentano di connettersi al servizio A/V Edge devono disporre di un token di autenticazione fornito dal servizio di autenticazione A/V prima di poter effettuare le proprie chiamate.</span><span class="sxs-lookup"><span data-stu-id="777d4-p104">The A/V Authentication service is collocated with, and provides authentication services for, the A/V Edge service. Outside users who attempt to connect to the A/V Edge service require an authentication token that is provided by the A/V Authentication Service before their calls can go through.</span></span>
    
- <span data-ttu-id="777d4-118">Inoltre, alcuni componenti di VoIP aziendale vengono eseguiti nei Front End Server.</span><span class="sxs-lookup"><span data-stu-id="777d4-118">Additionally, some Enterprise Voice components run on Front End Servers.</span></span> <span data-ttu-id="777d4-119">Per informazioni dettagliate su questi componenti, vedere [front end server VoIP Components for Skype for Business Server](front-end-server-voip.md)</span><span class="sxs-lookup"><span data-stu-id="777d4-119">For details about these components, see [Front End Server VoIP components for Skype for Business Server](front-end-server-voip.md)</span></span>
    

