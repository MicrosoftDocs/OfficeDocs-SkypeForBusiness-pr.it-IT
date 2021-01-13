---
title: Pianificare le distribuzioni di server perimetrali in Skype for Business Server
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
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: "Riepilogo: pianificare l'ambiente Edge di Skype for Business Server. In questo argomento vengono illustrati i concetti di Edge e vengono organizzati gli argomenti più approfonditi."
ms.openlocfilehash: 277e344448f5229d15addf965695f19ec2884649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813806"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="0065d-104">Pianificare le distribuzioni di server perimetrali in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="0065d-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="0065d-105">**Riepilogo:** Pianificare l'ambiente Edge di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0065d-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="0065d-106">In questo argomento vengono illustrati i concetti di Edge e vengono organizzati gli argomenti più approfonditi.</span><span class="sxs-lookup"><span data-stu-id="0065d-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="0065d-107">Quando si dispone di un ambiente Skype for Business Server che funziona bene internamente, il passaggio successivo potrebbe essere quello di introdurre un server perimetrale o un pool perimetrale nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="0065d-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="0065d-108">Questo ruolo sarebbe essenziale se si desidera che i servizi forniti da Skype for Business Server siano utilizzati da utenti esterni alla rete interna.</span><span class="sxs-lookup"><span data-stu-id="0065d-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="0065d-109">Questi possono potenzialmente includere:</span><span class="sxs-lookup"><span data-stu-id="0065d-109">These can potentially include:</span></span>
  
- <span data-ttu-id="0065d-110">Utenti remoti: dipendenti che sono fuori sede, temporaneamente o in modalità continua.</span><span class="sxs-lookup"><span data-stu-id="0065d-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="0065d-111">Utenti federati: dipendenti delle organizzazioni partner.</span><span class="sxs-lookup"><span data-stu-id="0065d-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="0065d-112">Utenti mobili.</span><span class="sxs-lookup"><span data-stu-id="0065d-112">Mobile Users.</span></span>
    
- <span data-ttu-id="0065d-113">Potenziali clienti, partner e persino utenti anonimi che si desidera invitare a riunioni e presentazioni.</span><span class="sxs-lookup"><span data-stu-id="0065d-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="0065d-114">L'accesso degli utenti esterni, ovvero la fornitura dei server perimetrali, consente di eseguire tutte le operazioni.</span><span class="sxs-lookup"><span data-stu-id="0065d-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="0065d-115">Gli utenti interni saranno in grado di usufruire dei seguenti servizi ospitati dalla distribuzione di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="0065d-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="0065d-116">Messaggistica istantanea e presenza per la comunicazione: gli utenti esterni autorizzati possono partecipare a conversazioni e conferenze di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="0065d-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="0065d-117">Sono in grado di ottenere informazioni sulla presenza per gli altri utenti (che ricevono anche informazioni sulla presenza).</span><span class="sxs-lookup"><span data-stu-id="0065d-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="0065d-118">Se si utilizza un provider di messaggistica istantanea pubblico, la comunicazione peer-to-peer non sarà in grado di eseguire conferenze con più partecipanti.</span><span class="sxs-lookup"><span data-stu-id="0065d-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="0065d-119">Tuttavia, entrambi i protocolli SIP e XMPP sono supportati.</span><span class="sxs-lookup"><span data-stu-id="0065d-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="0065d-120">Servizi di conferenza audio/video (A/V): gli utenti esterni autorizzati possono partecipare alle conferenze audio e video di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0065d-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="0065d-121">Web Conferencing: gli utenti esterni autorizzati possono partecipare alle conferenze di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="0065d-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="0065d-122">Se lo si desidera, è anche possibile abilitare la partecipazione per gli utenti remoti, gli utenti federati e gli utenti anonimi.</span><span class="sxs-lookup"><span data-stu-id="0065d-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="0065d-123">Gli utenti di messaggistica istantanea pubblica non possono partecipare alle conferenze.</span><span class="sxs-lookup"><span data-stu-id="0065d-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="0065d-124">Sono inoltre disponibili opzioni che consentono agli utenti di partecipare alla condivisione di applicazioni e desktop e di agire anche come organizzatori di riunioni o relatori.</span><span class="sxs-lookup"><span data-stu-id="0065d-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="0065d-125">L'accesso ai dispositivi mobili è supportato, come VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="0065d-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="0065d-126">È possibile invitare gli utenti esterni a quelle riunioni a cui si desidera partecipare, anche gli utenti anonimi, se si desidera concedere loro autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="0065d-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="0065d-127">Se si tratta di una cosa che l'organizzazione ha bisogno, la pianificazione di un ambiente Edge sarà di grande aiuto per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="0065d-127">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it.</span></span> <span data-ttu-id="0065d-128">Per ulteriori informazioni, sono disponibili gli argomenti elencati di seguito.</span><span class="sxs-lookup"><span data-stu-id="0065d-128">For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="0065d-129">I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015 ma non sono più supportati in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0065d-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="0065d-130">Per ulteriori informazioni, vedere [migrazione della Federazione XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) .</span><span class="sxs-lookup"><span data-stu-id="0065d-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="0065d-131">Argomenti relativi alla pianificazione:</span><span class="sxs-lookup"><span data-stu-id="0065d-131">Planning topics:</span></span>

<span data-ttu-id="0065d-132">Gli articoli di pianificazione sono:</span><span class="sxs-lookup"><span data-stu-id="0065d-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="0065d-133">Requisiti di sistema per i server perimetrali in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0065d-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="0065d-134">Requisiti ambientali dei server perimetrali in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0065d-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="0065d-135">Scenari del server perimetrale in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0065d-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

