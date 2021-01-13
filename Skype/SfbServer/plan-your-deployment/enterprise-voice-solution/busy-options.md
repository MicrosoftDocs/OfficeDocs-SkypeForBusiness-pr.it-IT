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
description: Per ulteriori informazioni, vedere la funzionalità opzioni occupato in Skype for Business Server.
ms.openlocfilehash: 558d7486ca7aaa794c3114f5c210702a54e02fc4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813696"
---
# <a name="plan-for-busy-options-for-skype-for-business-server"></a><span data-ttu-id="920ae-103">Pianificare le opzioni di disponibilità per Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="920ae-103">Plan for Busy Options for Skype for Business Server</span></span>
 
<span data-ttu-id="920ae-104">Per ulteriori informazioni, vedere la funzionalità opzioni occupato in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="920ae-104">Read about the Busy Options feature in Skype for Business Server.</span></span>
  
<span data-ttu-id="920ae-105">Busy options è un nuovo criterio vocale introdotto nell'aggiornamento cumulativo di luglio 2016 che consente di configurare il modo in cui le chiamate in arrivo vengono gestite quando un utente è già in una chiamata o in una conferenza oppure ha una chiamata in attesa.</span><span class="sxs-lookup"><span data-stu-id="920ae-105">Busy Options is a new voice policy introduced in the July 2016 Cumulative Update that allows you to configure how incoming calls are handled when a user is already in a call or conference, or has a call placed on hold.</span></span> <span data-ttu-id="920ae-106">Le chiamate nuove o in arrivo possono essere rifiutate con un segnale di occupato o inoltrate alla segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="920ae-106">New or incoming calls can be rejected with a busy signal or forwarded to voice mail.</span></span> 
  
<span data-ttu-id="920ae-107">Il criterio delle opzioni di occupato è supportato per il failover e il ripristino di emergenza in pool Front End associati e Survivable Branch Server (SBS).</span><span class="sxs-lookup"><span data-stu-id="920ae-107">The Busy Options policy is supported for failover and disaster recovery on paired Front End Pools and Survivable Branch Servers (SBS).</span></span>
  
<span data-ttu-id="920ae-108">In questo argomento vengono descritte le caratteristiche delle opzioni di occupato.</span><span class="sxs-lookup"><span data-stu-id="920ae-108">This topic describes the features of Busy Options.</span></span> <span data-ttu-id="920ae-109">Per informazioni su come installare e configurare le opzioni di occupato, vedere [Install and Configure busy options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span><span class="sxs-lookup"><span data-stu-id="920ae-109">For information about how to install and configure Busy Options, see [Install and configure Busy Options for Skype for Business Server](../../deploy/deploy-enterprise-voice/install-and-configure-busy-options.md).</span></span>
  
## <a name="configuration-options"></a><span data-ttu-id="920ae-110">Opzioni di configurazione</span><span class="sxs-lookup"><span data-stu-id="920ae-110">Configuration options</span></span>

<span data-ttu-id="920ae-111">Se per l'organizzazione sono abilitate le opzioni di disponibilità, tutti gli utenti dell'organizzazione, sia VoIP aziendale che utenti non di VoIP aziendale, possono utilizzare le seguenti funzionalità:</span><span class="sxs-lookup"><span data-stu-id="920ae-111">If Busy Options is enabled for the organization, all users in your organization, both Enterprise Voice and non-Enterprise Voice users, can use the following features:</span></span>
  
- <span data-ttu-id="920ae-112">Occupato su occupato-in cui le nuove chiamate in arrivo verranno rifiutate con un segnale di occupato se l'utente è occupato.</span><span class="sxs-lookup"><span data-stu-id="920ae-112">Busy on Busy - In which new incoming calls will be rejected with a busy signal if the user is busy.</span></span>
    
- <span data-ttu-id="920ae-113">Segreteria telefonica su occupato-in cui le nuove chiamate in entrata verranno inoltrate alla segreteria telefonica se l'utente è occupato.</span><span class="sxs-lookup"><span data-stu-id="920ae-113">Voicemail on Busy - In which new incoming calls will be forwarded to voice mail if the user is busy.</span></span>
    
<span data-ttu-id="920ae-114">La funzionalità opzioni occupate offre funzionalità di failover.</span><span class="sxs-lookup"><span data-stu-id="920ae-114">The Busy Options feature provides failover capability.</span></span> <span data-ttu-id="920ae-115">Se si verifica un problema e gli utenti eseguono il failover su un altro front end server o su un altro pool in Skype for Business Server, verranno mantenute le impostazioni delle opzioni occupate.</span><span class="sxs-lookup"><span data-stu-id="920ae-115">If a problem occurs and users fail over to another Front End Server or to another pool in Skype for Business Server, their Busy Options settings will be preserved.</span></span>
  
<span data-ttu-id="920ae-116">Indipendentemente dal modo in cui sono configurate le opzioni di disponibilità, gli utenti di una chiamata o di una conferenza o di quelli con una chiamata in attesa non sono stati impediti dall'avvio di nuove chiamate o conferenze.</span><span class="sxs-lookup"><span data-stu-id="920ae-116">Regardless of how their busy options are configured, users in a call or conference, or those with a call on hold, are not prevented from initiating new calls or conferences.</span></span> 
  
<span data-ttu-id="920ae-117">Dopo la configurazione, l'impostazione delle opzioni di occupato è attiva per tutti i client e i dispositivi di chiamata Skype for business dell'utente.</span><span class="sxs-lookup"><span data-stu-id="920ae-117">After configuration, the Busy Options setting is in effect for all the user's Skype for Business call devices and clients.</span></span> <span data-ttu-id="920ae-118">In base alle impostazioni delle opzioni di occupato dell'utente, la chiamata rifiutata o inviata alla segreteria telefonica non suonerebbe nei dispositivi di chiamata dell'utente, inclusi Macintosh, desktop di Windows, client mobili o telefoni IP, in cui l'utente ha eseguito l'accesso.</span><span class="sxs-lookup"><span data-stu-id="920ae-118">Based on the user's Busy Options settings, the call that is rejected or sent to voice mail would not ring on any of the user's call devices--including Macintosh, Windows Desktop, mobile clients, or IP phones--on which the user is signed in.</span></span> 
  
<span data-ttu-id="920ae-119">Gli utenti visualizzeranno le notifiche di chiamata senza risposta nei client e dispositivi Skype for business e verranno informati anche tramite posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="920ae-119">Users will see missed-call notifications on their Skype for Business clients and devices, and they will be notified by email as well.</span></span> <span data-ttu-id="920ae-120">I chiamanti la cui chiamata è stata rifiutata a causa di occupato su occupato vedrà una notifica nel loro client Skype for business che indica che l'utente che ha tentato di raggiungere è occupato su un'altra chiamata.</span><span class="sxs-lookup"><span data-stu-id="920ae-120">Callers whose call was rejected due to Busy on Busy will see a notification in their Skype for Business client stating that the user they attempted to reach is busy on another call.</span></span>
  
<span data-ttu-id="920ae-121">È possibile configurare la funzionalità di opzioni di occupato tramite i cmdlet di PowerShell per Skype for business per:</span><span class="sxs-lookup"><span data-stu-id="920ae-121">You can configure the Busy Options feature by using Skype for Business PowerShell cmdlets to:</span></span>
  
- <span data-ttu-id="920ae-122">Abilitare o disabilitare i criteri vocali per le opzioni di disponibilità per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="920ae-122">Enable or disable Busy Options Voice policy for the Enterprise.</span></span>
    
- <span data-ttu-id="920ae-123">Amministrare occupato su occupato o segreteria telefonica su occupato per tutti gli utenti dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="920ae-123">Administer Busy on Busy or Voicemail on Busy for all the users in the Enterprise.</span></span>
    
- <span data-ttu-id="920ae-124">Amministrare occupato su occupato o segreteria telefonica su occupato per tutti gli utenti ospitati in un pool Front end specifico.</span><span class="sxs-lookup"><span data-stu-id="920ae-124">Administer Busy on Busy or Voicemail on Busy for all the users homed in a particular Front End pool.</span></span>
    
- <span data-ttu-id="920ae-125">Amministrare occupato su occupato o segreteria telefonica su occupato per un elenco di utenti.</span><span class="sxs-lookup"><span data-stu-id="920ae-125">Administer Busy on Busy or Voicemail on Busy for a list of users.</span></span>
    
- <span data-ttu-id="920ae-126">Amministrare occupato su occupato o segreteria telefonica su occupato per un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="920ae-126">Administer Busy on Busy or Voicemail on Busy for a single user.</span></span>
    
## <a name="interoperability-with-voice-applications"></a><span data-ttu-id="920ae-127">Interoperabilità con le applicazioni vocali</span><span class="sxs-lookup"><span data-stu-id="920ae-127">Interoperability with Voice applications</span></span>

<span data-ttu-id="920ae-128">Le opzioni di occupato offrono interoperabilità con le applicazioni vocali seguenti in Skype for business:</span><span class="sxs-lookup"><span data-stu-id="920ae-128">Busy Options provides interoperability with the following Voice applications in Skype for Business:</span></span>
  
- <span data-ttu-id="920ae-129">Gruppi di risposta (RGS)</span><span class="sxs-lookup"><span data-stu-id="920ae-129">Response Groups (RGS)</span></span>
    
  - <span data-ttu-id="920ae-130">Le opzioni di occupato impostate sui numeri dei Response Group verranno ignorate dal sistema. sono consentite più chiamate simultanee.</span><span class="sxs-lookup"><span data-stu-id="920ae-130">Busy Options set on Response Group numbers will be ignored by the system; multiple concurrent calls will be allowed.</span></span> 
    
  - <span data-ttu-id="920ae-131">L'esperienza di routing degli addetti corrente nei Response Group rimarrà invariata per gli agenti con impostazioni delle opzioni occupate.</span><span class="sxs-lookup"><span data-stu-id="920ae-131">The current Attendant routing experience in Response Groups will remain unchanged for the Agents with Busy Options settings.</span></span>
    
  - <span data-ttu-id="920ae-132">Le chiamate provenienti da Response Group per gli utenti che sono agenti Response Group non verranno limitate dalle impostazioni delle opzioni occupate e l'esperienza di RGS corrente verrà mantenuta.</span><span class="sxs-lookup"><span data-stu-id="920ae-132">The calls coming from Response Groups to the users who are Response Groups Agents will not be throttled by Busy Options settings and the current RGS experience will be maintained.</span></span>
    
  - <span data-ttu-id="920ae-133">Le chiamate correlate non RGS agli agenti saranno onorate dalle impostazioni relative alle opzioni occupate.</span><span class="sxs-lookup"><span data-stu-id="920ae-133">The non-RGS related calls to the Agents will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="920ae-134">Intercettazione team</span><span class="sxs-lookup"><span data-stu-id="920ae-134">Team Call</span></span>
    
  - <span data-ttu-id="920ae-135">Le chiamate in arrivo per gli utenti che sono configurati per una chiamata del team avranno la priorità per ignorare occupato su occupato e segreteria telefonica su impostazioni occupato.</span><span class="sxs-lookup"><span data-stu-id="920ae-135">Incoming calls to users who are set up for a Team Call will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="920ae-136">L'esperienza di chiamata del team corrente rimarrà invariata con le opzioni di occupato impostate per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="920ae-136">The current Team Call experience will remain unchanged with Busy Options set for the users.</span></span>
    
  - <span data-ttu-id="920ae-137">Le chiamate non correlate alla chiamata del team a tali utenti verranno onorate dalle impostazioni relative alle opzioni occupate.</span><span class="sxs-lookup"><span data-stu-id="920ae-137">The non-Team Call related calls to such users will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="920ae-138">Delega di boss/admin</span><span class="sxs-lookup"><span data-stu-id="920ae-138">Boss/Admin Delegation</span></span> 
    
  - <span data-ttu-id="920ae-139">Le chiamate in arrivo per gli utenti che sono configurati per una delega di boss/amministratore o come capo o amministratore avranno la priorità di ignorare occupato su occupato e segreteria telefonica su impostazioni occupato.</span><span class="sxs-lookup"><span data-stu-id="920ae-139">Incoming calls to users who are set up for a Boss/Admin Delegation either as Boss or an Admin will be prioritized to ignore Busy on Busy and Voicemail on Busy settings.</span></span>
    
  - <span data-ttu-id="920ae-140">L'esperienza di delega corrente del boss/amministratore rimarrà invariata con le opzioni di occupato impostate per gli amministratori o il boss.</span><span class="sxs-lookup"><span data-stu-id="920ae-140">The current Boss/Admin Delegation experience will remain unchanged with Busy Options set for the Admins or Boss.</span></span>
    
  - <span data-ttu-id="920ae-141">Le chiamate di deleghe non boss/admin correlate agli amministratori saranno onorate dalle impostazioni relative alle opzioni occupate.</span><span class="sxs-lookup"><span data-stu-id="920ae-141">The non-Boss/Admin Delegation related calls to Admins will be honored by their Busy Options settings.</span></span>
    
- <span data-ttu-id="920ae-142">Modalità di linea condivisa</span><span class="sxs-lookup"><span data-stu-id="920ae-142">Shared Line Appearance</span></span> 
    
  - <span data-ttu-id="920ae-143">Le impostazioni delle opzioni di occupato sugli account utente configurati per l'aspetto della linea condivisa verranno ignorate.</span><span class="sxs-lookup"><span data-stu-id="920ae-143">Busy Options settings on user accounts set up for Shared Line Appearance will be ignored.</span></span> 
    
  - <span data-ttu-id="920ae-144">L'aspetto nativo della linea condivisa è occupato da occupato e la segreteria telefonica su Opzioni occupate verrà invece rispettata.</span><span class="sxs-lookup"><span data-stu-id="920ae-144">Shared Line Appearance's native Busy on Busy and Voicemail on Busy options will be honored instead.</span></span>
    
- <span data-ttu-id="920ae-145">Servizio parcheggio di chiamata</span><span class="sxs-lookup"><span data-stu-id="920ae-145">Call Parking Service</span></span> 
    
  - <span data-ttu-id="920ae-146">Le chiamate parcheggiate che non sono state recuperate e squillano di nuovo a causa dei tempi di inattività potranno squillare anche se all'utente che ha parcheggiato la chiamata dalle opzioni di occupato.</span><span class="sxs-lookup"><span data-stu-id="920ae-146">Parked calls that were not retrieved and are ringing back due to timing out will be allowed to ring though to the user who parked the call by the Busy Options.</span></span> 
    
- <span data-ttu-id="920ae-147">Conferenze telefoniche</span><span class="sxs-lookup"><span data-stu-id="920ae-147">Call Conferencing</span></span>
    
  - <span data-ttu-id="920ae-148">Gli utenti nelle chiamate in conferenza sono considerati occupati e le nuove chiamate in arrivo verranno rifiutate con un segnale di occupato o inoltrate alla segreteria telefonica in base alle impostazioni delle opzioni di occupato.</span><span class="sxs-lookup"><span data-stu-id="920ae-148">Users in conference calls are considered Busy and new incoming calls will be rejected with a busy signal or forwarded to voice mail according to their Busy Options settings.</span></span>
    
  - <span data-ttu-id="920ae-149">Agli utenti nelle conferenze non è impedito di avviare nuove chiamate o conferenze in base alle opzioni di occupato.</span><span class="sxs-lookup"><span data-stu-id="920ae-149">Users in conferences are not prevented from initiating new calls or conferences by Busy Options.</span></span>
    
  - <span data-ttu-id="920ae-150">Gli utenti nelle conferenze sono ancora in grado di ricevere nuovi inviti alla conferenza, ma le nuove chiamate peer-to-peer verranno rifiutate in base alle impostazioni delle opzioni occupate.</span><span class="sxs-lookup"><span data-stu-id="920ae-150">Users in conferences are still able to receive new conference invitations, but new peer-to-peer calls will be rejected according to their Busy Options settings.</span></span>
    
- <span data-ttu-id="920ae-151">Squillo simultaneo e inoltro di chiamata</span><span class="sxs-lookup"><span data-stu-id="920ae-151">Simultaneous Ring and Call Forwarding</span></span>
    
    <span data-ttu-id="920ae-152">La funzionalità occupato su occupato non è progettata per l'utilizzo con squillo simultaneo e inoltro di chiamata.</span><span class="sxs-lookup"><span data-stu-id="920ae-152">The Busy on Busy feature is not designed to work with Simultaneous Ring and Call Forwarding.</span></span>
    

