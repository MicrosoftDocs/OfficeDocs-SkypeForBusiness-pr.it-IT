---
title: Pianificare le opzioni di occupato per Skype for Business Server
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Informazioni sulla caratteristica opzioni occupato in Skype for Business Server.
ms.openlocfilehash: cf9ee9dbb3785804b1bb63f4118a29d29cf7715c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41803246"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="ebea7-103">Pianificare le opzioni di occupato per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ebea7-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="ebea7-104">Informazioni sulla caratteristica opzioni occupato in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ebea7-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="ebea7-105">Opzioni di occupato è un nuovo criterio vocale introdotto nell'aggiornamento cumulativo di 2016 di luglio che consente di configurare il modo in cui vengono gestite le chiamate in arrivo quando un utente è già in una chiamata o una conferenza o se è stata inserita una chiamata in attesa.</span><span class="sxs-lookup"><span data-stu-id="ebea7-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="ebea7-106">Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato o inoltrate alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="ebea7-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="ebea7-107">Il criterio di opzioni occupato è supportato per il failover e il ripristino di emergenza nei pool Front-End associati e nel Survivable Branch Server (SBS).</span><span class="sxs-lookup"><span data-stu-id="ebea7-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="ebea7-108">Questo argomento descrive le caratteristiche delle opzioni di occupato.</span><span class="sxs-lookup"><span data-stu-id="ebea7-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="ebea7-109">Per informazioni su come installare e configurare le opzioni di occupato, vedere [installare e configurare le opzioni di occupato per Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span><span class="sxs-lookup"><span data-stu-id="ebea7-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="ebea7-110">Opzioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="ebea7-110">Configuration options</span></span>

<span data-ttu-id="ebea7-111">Se le opzioni di occupato sono abilitate per l'organizzazione, tutti gli utenti dell'organizzazione, sia VoIP aziendale che utenti non aziendali, possono usare le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="ebea7-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="ebea7-112">Occupato in busy-in cui le nuove chiamate in arrivo verranno rifiutate con un segnale di occupato se l'utente è occupato.</span><span class="sxs-lookup"><span data-stu-id="ebea7-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="ebea7-113">Segreteria telefonica in occupato, in cui le nuove chiamate in arrivo verranno inoltrate alla segreteria telefonica se l'utente è occupato.</span><span class="sxs-lookup"><span data-stu-id="ebea7-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="ebea7-114">La caratteristica opzioni occupato offre funzionalità di failover.</span><span class="sxs-lookup"><span data-stu-id="ebea7-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="ebea7-115">Se si verifica un problema e gli utenti non riescono a eseguire il failover in un altro server front-end o in un altro pool in Skype for Business Server, le impostazioni delle opzioni occupate verranno mantenute.</span><span class="sxs-lookup"><span data-stu-id="ebea7-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="ebea7-116">Indipendentemente dal modo in cui sono configurate le opzioni di occupato, gli utenti di una chiamata o di una conferenza o quelli con una chiamata in attesa non vengono impediti di avviare nuove chiamate o conferenze.</span><span class="sxs-lookup"><span data-stu-id="ebea7-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="ebea7-117">Dopo la configurazione, l'impostazione opzioni occupato è attiva per tutti i client e i dispositivi di chiamata Skype for business dell'utente.</span><span class="sxs-lookup"><span data-stu-id="ebea7-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="ebea7-118">In base alle impostazioni delle opzioni di occupato dell'utente, la chiamata rifiutata o inviata alla segreteria telefonica non suonerebbe su uno dei dispositivi di chiamata dell'utente, tra cui Macintosh, desktop di Windows, client mobili o telefoni IP, in cui l'utente ha eseguito l'accesso.</span><span class="sxs-lookup"><span data-stu-id="ebea7-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="ebea7-119">Gli utenti vedranno le notifiche per le chiamate perse nei loro client e dispositivi Skype for business e verranno avvisati anche tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="ebea7-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="ebea7-120">I chiamanti la cui chiamata è stata rifiutata a causa di impegni occupati vedranno una notifica nel client Skype for business che informa che l'utente che ha tentato di raggiungere è impegnato in un'altra chiamata.</span><span class="sxs-lookup"><span data-stu-id="ebea7-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="ebea7-121">È possibile configurare la caratteristica opzioni occupato usando i cmdlet di PowerShell per Skype for business per:</span><span class="sxs-lookup"><span data-stu-id="ebea7-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="ebea7-122">Abilitare o disabilitare i criteri vocali delle opzioni di occupato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ebea7-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="ebea7-123">Gestire occupato o Voicemail occupato per tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ebea7-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="ebea7-124">Amministrare occupato o Voicemail occupato per tutti gli utenti ospitati in un determinato pool Front-end.</span><span class="sxs-lookup"><span data-stu-id="ebea7-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="ebea7-125">Amministrare occupato o Voicemail occupato per un elenco di utenti.</span><span class="sxs-lookup"><span data-stu-id="ebea7-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="ebea7-126">Amministrare occupato o Voicemail occupato per un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="ebea7-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="ebea7-127">Interoperabilità con le applicazioni vocali</span><span class="sxs-lookup"><span data-stu-id="ebea7-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="ebea7-128">Le opzioni di occupato offrono l'interoperabilità con le applicazioni vocali seguenti in Skype for business:</span><span class="sxs-lookup"><span data-stu-id="ebea7-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="ebea7-129">Gruppi di risposte (RGS)</span><span class="sxs-lookup"><span data-stu-id="ebea7-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="ebea7-130">Le opzioni di occupato impostate sui numeri di Response Group verranno ignorate dal sistema. saranno consentite più chiamate simultanee.</span><span class="sxs-lookup"><span data-stu-id="ebea7-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="ebea7-131">L'esperienza di routing degli assistenti correnti nei gruppi di risposte rimarrà invariata per gli agenti con le impostazioni delle opzioni occupate.</span><span class="sxs-lookup"><span data-stu-id="ebea7-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="ebea7-132">Le chiamate provenienti da Response Groups agli utenti che sono agenti Response Groups non verranno limitate dalle impostazioni delle opzioni occupate e l'esperienza corrente di RGS verrà mantenuta.</span><span class="sxs-lookup"><span data-stu-id="ebea7-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="ebea7-133">Le chiamate correlate non-RGS agli agenti saranno onorate dalle impostazioni delle opzioni occupate.</span><span class="sxs-lookup"><span data-stu-id="ebea7-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="ebea7-134">Chiamata in team</span><span class="sxs-lookup"><span data-stu-id="ebea7-134">Team Call</span></span>
    
  - <span data-ttu-id="ebea7-135">Le chiamate in arrivo per gli utenti configurati per una chiamata al team verranno impostate come priorità per ignorare le attività occupato e la segreteria telefonica nelle impostazioni di occupato.</span><span class="sxs-lookup"><span data-stu-id="ebea7-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="ebea7-136">L'esperienza di chiamata del team corrente rimarrà invariata con le opzioni di occupato impostate per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="ebea7-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="ebea7-137">Le chiamate non correlate alla chiamata in team a tali utenti saranno onorate dalle impostazioni delle opzioni occupate.</span><span class="sxs-lookup"><span data-stu-id="ebea7-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="ebea7-138">Delega di boss/admin</span><span class="sxs-lookup"><span data-stu-id="ebea7-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="ebea7-139">Le chiamate in arrivo agli utenti configurati per una delega di capo/amministratore, come capo o amministratore, saranno in ordine di priorità per ignorare la disponibilità e la segreteria telefonica nelle impostazioni di occupato.</span><span class="sxs-lookup"><span data-stu-id="ebea7-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="ebea7-140">L'esperienza di delega corrente per il boss o l'amministratore rimarrà invariata con le opzioni di occupato impostate per gli amministratori o il boss.</span><span class="sxs-lookup"><span data-stu-id="ebea7-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="ebea7-141">Le chiamate correlate alla delega di non-boss/admin per gli amministratori saranno onorate dalle impostazioni delle opzioni occupate.</span><span class="sxs-lookup"><span data-stu-id="ebea7-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="ebea7-142">Aspetto della linea condivisa</span><span class="sxs-lookup"><span data-stu-id="ebea7-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="ebea7-143">Le impostazioni delle opzioni di occupato sugli account utente impostati per l'aspetto della linea condivisa verranno ignorate.</span><span class="sxs-lookup"><span data-stu-id="ebea7-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="ebea7-144">L'aspetto della linea condivisa nativa occupato e la segreteria telefonica sulle opzioni di occupato saranno onorati.</span><span class="sxs-lookup"><span data-stu-id="ebea7-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="ebea7-145">Servizio di parcheggio delle chiamate</span><span class="sxs-lookup"><span data-stu-id="ebea7-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="ebea7-146">Le chiamate parcheggiate che non sono state recuperate e squillano di nuovo a causa di un timeout sarà consentito squillare anche se l'utente ha parcheggiato la chiamata tramite le opzioni di occupato.</span><span class="sxs-lookup"><span data-stu-id="ebea7-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="ebea7-147">Conferenza telefonica</span><span class="sxs-lookup"><span data-stu-id="ebea7-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="ebea7-148">Gli utenti delle chiamate in conferenza vengono considerati occupati e le nuove chiamate in arrivo verranno rifiutate con un segnale di occupato o inoltrate alla segreteria telefonica in base alle impostazioni delle opzioni occupate.</span><span class="sxs-lookup"><span data-stu-id="ebea7-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="ebea7-149">Agli utenti delle conferenze non viene impedito di avviare nuove chiamate o conferenze per le opzioni di occupato.</span><span class="sxs-lookup"><span data-stu-id="ebea7-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="ebea7-150">Gli utenti delle conferenze possono comunque ricevere nuovi inviti alle conferenze, ma le nuove chiamate peer-to-peer verranno rifiutate in base alle impostazioni delle opzioni occupate.</span><span class="sxs-lookup"><span data-stu-id="ebea7-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="ebea7-151">Squillo simultaneo e inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="ebea7-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="ebea7-152">La funzionalità occupato su occupato non è progettata per l'utilizzo con squillo simultaneo e inoltro di chiamata.</span><span class="sxs-lookup"><span data-stu-id="ebea7-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

