---
title: Pianificare le opzioni di disponibilità per Skype for Business Server
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
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5f85c6bc-a962-4283-971c-4380d83b3a66
description: Informazioni sulla funzionalità Opzioni occupato in Skype for Business Server.
ms.openlocfilehash: 558d7486ca7aaa794c3114f5c210702a54e02fc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813696"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="fd089-103">Pianificare le opzioni di disponibilità per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="fd089-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="fd089-104">Informazioni sulla funzionalità Opzioni occupato in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fd089-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="fd089-105">Opzioni occupato è un nuovo criterio vocale introdotto nell'aggiornamento cumulativo di luglio 2016 che consente di configurare la modalità di gestione delle chiamate in arrivo quando un utente è già in una chiamata o una conferenza o ha una chiamata messa in attesa.</span><span class="sxs-lookup"><span data-stu-id="fd089-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="fd089-106">Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato o inoltrate alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="fd089-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="fd089-107">Il criterio Opzioni occupato è supportato per il failover e il ripristino di emergenza in pool Front End e Survivable Branch Server (SBS) accoppiati.</span><span class="sxs-lookup"><span data-stu-id="fd089-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="fd089-108">In questo argomento vengono descritte le funzionalità delle opzioni non disponibili.</span><span class="sxs-lookup"><span data-stu-id="fd089-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="fd089-109">Per informazioni su come installare e configurare le opzioni occupato, vedere Installare e configurare le opzioni di occupato [per Skype for Business Server.](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md)</span><span class="sxs-lookup"><span data-stu-id="fd089-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="fd089-110">Opzioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="fd089-110">Configuration options</span></span>

<span data-ttu-id="fd089-111">Se le opzioni occupato sono abilitate per l'organizzazione, tutti gli utenti dell'organizzazione, sia VoIP aziendale che non VoIP aziendale utenti, possono utilizzare le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="fd089-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="fd089-112">Occupato: in cui le nuove chiamate in arrivo verranno rifiutate con un segnale di occupato se l'utente è occupato.</span><span class="sxs-lookup"><span data-stu-id="fd089-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="fd089-113">Segreteria telefonica su occupato- In cui le nuove chiamate in arrivo verranno inoltrate alla segreteria telefonica se l'utente è occupato.</span><span class="sxs-lookup"><span data-stu-id="fd089-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="fd089-114">La funzionalità Opzioni occupato offre funzionalità di failover.</span><span class="sxs-lookup"><span data-stu-id="fd089-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="fd089-115">Se si verifica un problema e si verifica il failover degli utenti in un altro Front End Server o in un altro pool in Skype for Business Server, le impostazioni delle opzioni di disponibilità verranno mantenute.</span><span class="sxs-lookup"><span data-stu-id="fd089-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="fd089-116">Indipendentemente dalla configurazione delle opzioni di disponibilità, agli utenti di una chiamata o di una conferenza o agli utenti con una chiamata in attesa non viene impedito di avviare nuove chiamate o conferenze.</span><span class="sxs-lookup"><span data-stu-id="fd089-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="fd089-117">Dopo la configurazione, l'impostazione Opzioni occupato è attiva per tutti i dispositivi e i client di chiamata Skype for Business dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fd089-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="fd089-118">In base alle impostazioni relative alle opzioni di occupato dell'utente, la chiamata rifiutata o inviata alla segreteria telefonica non squilla su nessuno dei dispositivi di chiamata dell'utente, inclusi Macintosh, Windows Desktop, client mobili o telefoni IP, a cui l'utente ha effettuato l'accesso.</span><span class="sxs-lookup"><span data-stu-id="fd089-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="fd089-119">Gli utenti potranno visualizzare le notifiche di chiamata senza risposta sui propri client e dispositivi Skype for Business e riceveranno una notifica anche tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="fd089-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="fd089-120">I chiamanti la cui chiamata è stata rifiutata a causa di Occupato riceveranno una notifica nel client Skype for Business che informa che l'utente che ha tentato di raggiungere è occupato in un'altra chiamata.</span><span class="sxs-lookup"><span data-stu-id="fd089-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="fd089-121">È possibile configurare la funzionalità Opzioni occupato utilizzando i cmdlet di PowerShell di Skype for Business per:</span><span class="sxs-lookup"><span data-stu-id="fd089-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="fd089-122">Abilitare o disabilitare i criteri vocali opzioni occupato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fd089-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="fd089-123">Amministrare occupato su Occupato o Segreteria telefonica su Occupato per tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="fd089-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="fd089-124">Amministrare occupato su Occupato o Segreteria telefonica su Occupato per tutti gli utenti ospitati in un particolare pool Front End.</span><span class="sxs-lookup"><span data-stu-id="fd089-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="fd089-125">Amministrare Occupato su Occupato o Segreteria telefonica su Occupato per un elenco di utenti.</span><span class="sxs-lookup"><span data-stu-id="fd089-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="fd089-126">Amministrare occupato su occupato o segreteria telefonica su occupato per un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="fd089-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="fd089-127">Interoperabilità con le applicazioni vocali</span><span class="sxs-lookup"><span data-stu-id="fd089-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="fd089-128">Opzioni occupato garantisce l'interoperabilità con le seguenti applicazioni vocali in Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="fd089-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="fd089-129">Response Group (RGS)</span><span class="sxs-lookup"><span data-stu-id="fd089-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="fd089-130">Le opzioni di occupato impostate sui numeri di Response Group verranno ignorate dal sistema. saranno consentite più chiamate simultanee.</span><span class="sxs-lookup"><span data-stu-id="fd089-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="fd089-131">L'esperienza di routing dell'Operatore corrente in Response Group rimarrà invariata per gli agenti con le impostazioni delle opzioni di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="fd089-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="fd089-132">Le chiamate provenienti da Response Group agli utenti che sono agenti di Response Group non verranno limitate dalle impostazioni delle opzioni occupato e l'esperienza RGS corrente verrà mantenuta.</span><span class="sxs-lookup"><span data-stu-id="fd089-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="fd089-133">Le chiamate non correlate a RGS agli agenti verranno rispettate dalle relative impostazioni relative alle opzioni di disponibilità.</span><span class="sxs-lookup"><span data-stu-id="fd089-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="fd089-134">Intercettazione team</span><span class="sxs-lookup"><span data-stu-id="fd089-134">Team Call</span></span>
    
  - <span data-ttu-id="fd089-135">Le chiamate in arrivo agli utenti impostati per una chiamata al team verranno classificate in ordine di priorità per ignorare le impostazioni Occupato su Occupato e Segreteria telefonica su Occupato.</span><span class="sxs-lookup"><span data-stu-id="fd089-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="fd089-136">L'esperienza corrente della chiamata al team rimarrà invariata con le opzioni occupato impostate per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="fd089-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="fd089-137">Le chiamate non del team correlate a tali utenti verranno rispettate dalle impostazioni delle opzioni occupato.</span><span class="sxs-lookup"><span data-stu-id="fd089-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="fd089-138">Delega capo/amministratore</span><span class="sxs-lookup"><span data-stu-id="fd089-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="fd089-139">Le chiamate in arrivo verso gli utenti che sono impostati per una delega di capo/amministratore come capo o come amministratore avranno la priorità per ignorare le impostazioni Occupato su Occupato e Segreteria telefonica su Occupato.</span><span class="sxs-lookup"><span data-stu-id="fd089-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="fd089-140">L'esperienza corrente di delega del capo/amministratore rimarrà invariata con le opzioni occupato impostate per gli amministratori o il capo.</span><span class="sxs-lookup"><span data-stu-id="fd089-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="fd089-141">Le chiamate agli amministratori correlate alla delega non del capo/amministratore verranno rispettate dalle impostazioni delle opzioni occupato.</span><span class="sxs-lookup"><span data-stu-id="fd089-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="fd089-142">Modalità di linea condivisa</span><span class="sxs-lookup"><span data-stu-id="fd089-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="fd089-143">Le impostazioni relative alle opzioni non disponibili per gli account utente impostati per l'aspetto della linea condivisa verranno ignorate.</span><span class="sxs-lookup"><span data-stu-id="fd089-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="fd089-144">Verranno invece rispettate le opzioni Native Busy on Busy e Voicemail on Busy di Shared Line Appearance.</span><span class="sxs-lookup"><span data-stu-id="fd089-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="fd089-145">Servizio parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="fd089-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="fd089-146">Le chiamate parcheggiate che non sono state recuperate e che squillano a causa del timeout potranno squillare anche se all'utente che ha parcheggiato la chiamata dalle opzioni occupato.</span><span class="sxs-lookup"><span data-stu-id="fd089-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="fd089-147">Conferenza telefonica</span><span class="sxs-lookup"><span data-stu-id="fd089-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="fd089-148">Gli utenti nelle conferenze telefoniche sono considerati non disponibili e le nuove chiamate in arrivo verranno rifiutate con un segnale di occupato o inoltrate alla segreteria telefonica in base alle impostazioni delle opzioni di occupato.</span><span class="sxs-lookup"><span data-stu-id="fd089-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="fd089-149">Agli utenti delle conferenze non viene impedito di avviare nuove chiamate o conferenze tramite Opzioni occupato.</span><span class="sxs-lookup"><span data-stu-id="fd089-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="fd089-150">Gli utenti delle conferenze sono ancora in grado di ricevere nuovi inviti alle conferenze, ma le nuove chiamate peer-to-peer verranno rifiutate in base alle impostazioni delle opzioni di occupato.</span><span class="sxs-lookup"><span data-stu-id="fd089-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="fd089-151">Squillo simultaneo e inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="fd089-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="fd089-152">La funzionalità Occupato non è progettata per funzionare con lo squillo simultaneo e l'inoltro di chiamata.</span><span class="sxs-lookup"><span data-stu-id="fd089-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

