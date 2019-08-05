---
title: Pianificare le distribuzioni di Edge Server in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: "Riepilogo: pianificare l'ambiente di Skype for Business Server Edge. Questo argomento illustra i concetti di Edge e ti consente di organizzarti con i nostri argomenti più approfonditi."
ms.openlocfilehash: 536ab82ec6845c55a0ee067ad8c1a4f5d9b9e153
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187814"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="e45de-104">Pianificare le distribuzioni di Edge Server in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="e45de-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="e45de-105">**Riepilogo:** Pianificare l'ambiente di Skype for Business Server Edge.</span><span class="sxs-lookup"><span data-stu-id="e45de-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="e45de-106">Questo argomento illustra i concetti di Edge e ti consente di organizzarti con i nostri argomenti più approfonditi.</span><span class="sxs-lookup"><span data-stu-id="e45de-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="e45de-107">Quando si ha un ambiente di Skype for Business Server che funziona bene internamente, il passaggio successivo potrebbe essere l'introduzione di un Edge Server o di un pool di Edge nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="e45de-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="e45de-108">Questo ruolo sarebbe essenziale se si vuole che i servizi forniti da Skype for Business Server vengano usati dagli utenti esterni alla rete interna.</span><span class="sxs-lookup"><span data-stu-id="e45de-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="e45de-109">Questi possono includere potenzialmente:</span><span class="sxs-lookup"><span data-stu-id="e45de-109">These can potentially include:</span></span>
  
- <span data-ttu-id="e45de-110">Utenti remoti: i dipendenti che sono fuori sede, temporaneamente o in modo continuo.</span><span class="sxs-lookup"><span data-stu-id="e45de-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="e45de-111">Utenti federati: dipendenti delle organizzazioni partner.</span><span class="sxs-lookup"><span data-stu-id="e45de-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="e45de-112">Utenti mobili.</span><span class="sxs-lookup"><span data-stu-id="e45de-112">Mobile Users.</span></span>
    
- <span data-ttu-id="e45de-113">Potenziali clienti, partner e persino utenti anonimi che si vogliono invitare a riunioni e presentazioni.</span><span class="sxs-lookup"><span data-stu-id="e45de-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="e45de-114">L'accesso degli utenti esterni, che è quello che offre Edge Server, consente di ottenere tutto questo.</span><span class="sxs-lookup"><span data-stu-id="e45de-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="e45de-115">Gli utenti interni potranno usufruire dei servizi seguenti ospitati dalla distribuzione di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="e45de-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="e45de-116">Messaggistica istantanea e presenza per la comunicazione: gli utenti esterni autorizzati possono partecipare a conversazioni e conferenze di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="e45de-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="e45de-117">Possono ottenere informazioni sulla presenza per altri utenti (che ricevono anche le informazioni sulla presenza).</span><span class="sxs-lookup"><span data-stu-id="e45de-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="e45de-118">Non sarà possibile eseguire conferenze multiparte se si usa un provider di messaggistica istantanea pubblica, che è strettamente correlato alla comunicazione peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="e45de-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="e45de-119">Ma sono supportati sia i protocolli SIP che XMPP.</span><span class="sxs-lookup"><span data-stu-id="e45de-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="e45de-120">Servizi di conferenza audio/video (A/V): gli utenti esterni autorizzati possono partecipare alle conferenze audio e video di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="e45de-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="e45de-121">Web Conferencing: gli utenti esterni autorizzati possono partecipare alle conferenze di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="e45de-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="e45de-122">È anche possibile abilitare la partecipazione per utenti remoti, utenti federati e utenti anonimi, se si preferisce.</span><span class="sxs-lookup"><span data-stu-id="e45de-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="e45de-123">Gli utenti di messaggistica istantanea pubblica non possono partecipare alle conferenze.</span><span class="sxs-lookup"><span data-stu-id="e45de-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="e45de-124">Sono disponibili anche opzioni per consentire a questi utenti di partecipare a una condivisione di applicazioni e desktop e anche di fungere da organizzatori o relatori della riunione.</span><span class="sxs-lookup"><span data-stu-id="e45de-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="e45de-125">L'accesso al dispositivo mobile è supportato, così come VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="e45de-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="e45de-126">È possibile invitare utenti esterni alle riunioni a cui si vuole partecipare, anche agli utenti anonimi, se si desidera concedere loro le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="e45de-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="e45de-127">Se si tratta di un aspetto che l'organizzazione ha bisogno, la pianificazione di un ambiente Edge sarà di grande aiuto per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e45de-127">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it.</span></span> <span data-ttu-id="e45de-128">Per ulteriori informazioni, abbiamo gli argomenti elencati di seguito.</span><span class="sxs-lookup"><span data-stu-id="e45de-128">For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="e45de-129">I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="e45de-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="e45de-130">Per altre informazioni, Vedi [migrazione della Federazione XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="e45de-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="e45de-131">Argomenti di pianificazione:</span><span class="sxs-lookup"><span data-stu-id="e45de-131">Planning topics:</span></span>

<span data-ttu-id="e45de-132">Gli articoli per la pianificazione sono:</span><span class="sxs-lookup"><span data-stu-id="e45de-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="e45de-133">Requisiti di sistema di Edge Server in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e45de-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="e45de-134">Requisiti ambientali di Edge Server in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e45de-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="e45de-135">Scenari di Edge Server in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e45de-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

