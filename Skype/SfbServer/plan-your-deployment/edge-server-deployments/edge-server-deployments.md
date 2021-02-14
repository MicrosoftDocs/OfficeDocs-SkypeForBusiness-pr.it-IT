---
title: Pianificare le distribuzioni dei server perimetrali in Skype for Business Server
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
description: "Riepilogo: pianificare l'ambiente Skype for Business Server Edge. Questo argomento presenta i concetti di Edge e ti consente di organizzarti con i nostri argomenti più approfonditi."
ms.openlocfilehash: 277e344448f5229d15addf965695f19ec2884649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813806"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="9ab18-104">Pianificare le distribuzioni dei server perimetrali in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9ab18-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="9ab18-105">**Riepilogo:** Pianificare l'ambiente Edge di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9ab18-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="9ab18-106">Questo argomento presenta i concetti di Edge e ti consente di organizzarti con i nostri argomenti più approfonditi.</span><span class="sxs-lookup"><span data-stu-id="9ab18-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="9ab18-107">Quando si dispone di un ambiente Skype for Business Server che funziona correttamente internamente, il passaggio successivo potrebbe consistere nell'introdurre un server perimetrale o un pool di server perimetrali nell'ambiente.</span><span class="sxs-lookup"><span data-stu-id="9ab18-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="9ab18-108">Questo ruolo sarebbe fondamentale se vuoi che i servizi forniti da Skype for Business Server siano usati da persone esterne alla rete interna.</span><span class="sxs-lookup"><span data-stu-id="9ab18-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="9ab18-109">Questi possono potenzialmente includere:</span><span class="sxs-lookup"><span data-stu-id="9ab18-109">These can potentially include:</span></span>
  
- <span data-ttu-id="9ab18-110">Utenti remoti: dipendenti che sono fuori sede, temporaneamente o in modo continuamente.</span><span class="sxs-lookup"><span data-stu-id="9ab18-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="9ab18-111">Utenti federati: dipendenti delle organizzazioni partner.</span><span class="sxs-lookup"><span data-stu-id="9ab18-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="9ab18-112">Utenti mobili.</span><span class="sxs-lookup"><span data-stu-id="9ab18-112">Mobile Users.</span></span>
    
- <span data-ttu-id="9ab18-113">Potenziali clienti, partner e persino utenti anonimi che si desidera invitare a riunioni e presentazioni.</span><span class="sxs-lookup"><span data-stu-id="9ab18-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="9ab18-114">L'accesso degli utenti esterni, che è quello fornito dal server perimetrale, consente tutto questo.</span><span class="sxs-lookup"><span data-stu-id="9ab18-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="9ab18-115">Gli utenti interni potranno usufruire dei servizi seguenti ospitati dalla distribuzione di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="9ab18-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="9ab18-116">Messaggistica istantanea e presenza per le comunicazioni: gli utenti esterni autorizzati possono partecipare a conversazioni e conferenze di messaggistica istantanea.</span><span class="sxs-lookup"><span data-stu-id="9ab18-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="9ab18-117">Possono ottenere informazioni sulla presenza per altri utenti (che ottengono anche le informazioni sulla presenza).</span><span class="sxs-lookup"><span data-stu-id="9ab18-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="9ab18-118">Non sarà possibile effettuare conferenze tra più partecipanti se si utilizza un provider di messaggistica istantanea pubblico, si tratta esclusivamente di comunicazioni peer-to-peer.</span><span class="sxs-lookup"><span data-stu-id="9ab18-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="9ab18-119">Tuttavia, sono supportati entrambi i protocolli SIP e XMPP.</span><span class="sxs-lookup"><span data-stu-id="9ab18-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="9ab18-120">Audio/video (A/V): gli utenti esterni autorizzati possono partecipare alle conferenze audio e video di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="9ab18-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="9ab18-121">Conferenze Web: gli utenti esterni autorizzati possono partecipare alle conferenze di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9ab18-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="9ab18-122">È inoltre possibile abilitare la partecipazione per utenti remoti, federati e anonimi, se lo si desidera.</span><span class="sxs-lookup"><span data-stu-id="9ab18-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="9ab18-123">Gli utenti di messaggistica istantanea pubblica non possono partecipare alle conferenze.</span><span class="sxs-lookup"><span data-stu-id="9ab18-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="9ab18-124">Sono inoltre disponibili opzioni per consentire a questi utenti di partecipare alla condivisione di applicazioni e desktop e di agire anche come organizzatori o relatori della riunione.</span><span class="sxs-lookup"><span data-stu-id="9ab18-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="9ab18-125">L'accesso ai dispositivi mobili è supportato, così come VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="9ab18-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="9ab18-126">È possibile invitare utenti esterni a tali riunioni a cui si desidera che partecipino, anche a utenti anonimi, se si desidera concedere loro le autorizzazioni.</span><span class="sxs-lookup"><span data-stu-id="9ab18-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="9ab18-127">Se si tratta di un'operazione di cui l'organizzazione ha bisogno, la pianificazione di un ambiente perimetrale sarà un grande aiuto per la distribuzione.</span><span class="sxs-lookup"><span data-stu-id="9ab18-127">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it.</span></span> <span data-ttu-id="9ab18-128">Per altre letture, abbiamo gli argomenti elencati di seguito.</span><span class="sxs-lookup"><span data-stu-id="9ab18-128">For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="9ab18-129">I gateway e i proxy XMPP sono disponibili in Skype for Business Server 2015, ma non sono più supportati in Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="9ab18-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="9ab18-130">Per [ulteriori informazioni, vedere Migrating XMPP federation.](../../../SfBServer2019/migration/migrating-xmpp-federation.md)</span><span class="sxs-lookup"><span data-stu-id="9ab18-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="9ab18-131">Argomenti relativi alla pianificazione:</span><span class="sxs-lookup"><span data-stu-id="9ab18-131">Planning topics:</span></span>

<span data-ttu-id="9ab18-132">Gli articoli relativi alla pianificazione sono:</span><span class="sxs-lookup"><span data-stu-id="9ab18-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="9ab18-133">Requisiti di sistema dei server perimetrali in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9ab18-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="9ab18-134">Requisiti ambientali dei server perimetrali in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="9ab18-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="9ab18-135">Scenari di server perimetrali in Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9ab18-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

