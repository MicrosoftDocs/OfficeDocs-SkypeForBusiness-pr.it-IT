---
title: Case Study di teams Voice contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Case Study di teams Voice per società multinazionali
appliesto:
- Microsoft Teams
ms.openlocfilehash: 100889bacffdb9de722bd2e1e7295905876dab2e
ms.sourcegitcommit: af15d99837a389b6b26952211e65cd68c4b7f46e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/18/2020
ms.locfileid: "44786017"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="ca942-103">Case Study di Contoso: Panoramica della migrazione di teams Voice</span><span class="sxs-lookup"><span data-stu-id="ca942-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="ca942-104">Questo articolo introduce un caso di studio per il modo in cui una società multinazionale fittizia, contoso, ha implementato una soluzione per la voce teams per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ca942-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="ca942-105">Contoso ha distribuito Microsoft 365 Enterprise e ha affrontato le principali decisioni di progettazione e i dettagli di implementazione per i seguenti servizi: networking, Identity, Windows 10 Enterprise, Office 365 ProPlus, gestione di dispositivi mobili, protezione delle informazioni, sicurezza, aggiornamento da Skype for business a teams, sistema telefonico e servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="ca942-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="ca942-106">Questo articolo illustra in che modo Contoso ha migrato gli utenti locali ai team per la comunicazione, la collaborazione e la voce unificata.</span><span class="sxs-lookup"><span data-stu-id="ca942-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="ca942-107">Per informazioni di base sul modo in cui Contoso ha accelerato la trasformazione digitale usando i servizi cloud di Microsoft, vedere tutti gli articoli principali a partire dalla [Panoramica del case study di Contoso](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="ca942-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="ca942-108">Negli articoli principali sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="ca942-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="ca942-109">Esigenze dell'infrastruttura IT di contoso</span><span class="sxs-lookup"><span data-stu-id="ca942-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="ca942-110">Networking</span><span class="sxs-lookup"><span data-stu-id="ca942-110">Networking</span></span>
- <span data-ttu-id="ca942-111">Identity</span><span class="sxs-lookup"><span data-stu-id="ca942-111">Identity</span></span>
- <span data-ttu-id="ca942-112">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="ca942-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="ca942-113">Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="ca942-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="ca942-114">Gestione di dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="ca942-114">Mobile device management</span></span>
- <span data-ttu-id="ca942-115">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="ca942-115">Information protection</span></span>
- <span data-ttu-id="ca942-116">Riepilogo della sicurezza aziendale di Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ca942-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="ca942-117">Team per un progetto Top-Secret</span><span class="sxs-lookup"><span data-stu-id="ca942-117">Team for a top-secret project</span></span>
- <span data-ttu-id="ca942-118">Sito di SharePoint Online per risorse digitali altamente riservate</span><span class="sxs-lookup"><span data-stu-id="ca942-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="ca942-119">Per informazioni sulla pianificazione di un aggiornamento, è consigliabile iniziare con [l'aggiornamento di Microsoft teams](upgrade-start-here.md).</span><span class="sxs-lookup"><span data-stu-id="ca942-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="ca942-120">Obiettivi aziendali di Contoso per Teams</span><span class="sxs-lookup"><span data-stu-id="ca942-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="ca942-121">Per eseguire la migrazione degli utenti locali ai team per la comunicazione, la collaborazione e la voce unificata, Contoso ha deciso i seguenti obiettivi aziendali:</span><span class="sxs-lookup"><span data-stu-id="ca942-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="ca942-122">Abilitazione Teams</span><span class="sxs-lookup"><span data-stu-id="ca942-122">Teams enablement</span></span> 

  <span data-ttu-id="ca942-123">Il team di comunicazione e collaborazione unificata di Contoso ha abilitato team con i criteri corretti per gestire e abilitare la collaborazione interna ed esterna sicura.</span><span class="sxs-lookup"><span data-stu-id="ca942-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="ca942-124">Aggiornamento da Skype for Business a Teams</span><span class="sxs-lookup"><span data-stu-id="ca942-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="ca942-125">Skype for business è stato ampiamente distribuito in contoso.</span><span class="sxs-lookup"><span data-stu-id="ca942-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="ca942-126">Con la necessità di rimuovere i sistemi legacy, Contoso ha deciso di aggiornare gli utenti di Skype for business ai team.</span><span class="sxs-lookup"><span data-stu-id="ca942-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="ca942-127">Per altre informazioni, vedere [Case Study di Contoso: piano di aggiornamento teams](voice-case-study-migration-plan.md).</span><span class="sxs-lookup"><span data-stu-id="ca942-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="ca942-128">Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="ca942-128">Phone System</span></span>  

  <span data-ttu-id="ca942-129">Skype for business con Enterprise Voice è stato ampiamente distribuito in contoso.</span><span class="sxs-lookup"><span data-stu-id="ca942-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="ca942-130">Con la necessità di spostare i sistemi legacy che sono stati l'hop successivo per i loro server di mediazione, Contoso ha migrato i loro utenti di Skype for Business VoIP per il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="ca942-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="ca942-131">I siti di Contoso hanno usato il piano di chiamata Microsoft, il routing diretto del sistema telefonico o una combinazione di entrambi.</span><span class="sxs-lookup"><span data-stu-id="ca942-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="ca942-132">Per altre informazioni, Vedi [Case Study di Contoso: sistema telefonico](voice-case-study-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="ca942-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="ca942-133">Instradamento basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="ca942-133">Location-Based Routing</span></span> 

  <span data-ttu-id="ca942-134">Con le posizioni di Office nei paesi regolamentati per la telefonia, Contoso ha avuto la necessità di ricreare il routing basato sulla posizione presente in Skype for business nella distribuzione del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="ca942-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="ca942-135">Per altre informazioni, vedere [Case Study di Contoso: routing basato sulla posizione](voice-case-study-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="ca942-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="ca942-136">Chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="ca942-136">Emergency Calling</span></span> 

  <span data-ttu-id="ca942-137">Dove è stato implementato il routing diretto, Contoso ha configurato le chiamate di emergenza con terze parti approvate.</span><span class="sxs-lookup"><span data-stu-id="ca942-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="ca942-138">Per altre informazioni, Vedi [Case Study di Contoso: chiamate di emergenza](voice-case-study-emergency-calling.md).</span><span class="sxs-lookup"><span data-stu-id="ca942-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="ca942-139">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="ca942-139">Audio Conferencing</span></span> 

  <span data-ttu-id="ca942-140">Contoso configura i numeri del servizio di audioconferenza ospitati nel trunk SIP nel proprio provider PSTN.</span><span class="sxs-lookup"><span data-stu-id="ca942-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="ca942-141">Per altre informazioni, vedere [Case Study di Contoso:](voice-case-study-audio-conferencing.md)audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="ca942-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="ca942-142">Ottimizzazione media locale</span><span class="sxs-lookup"><span data-stu-id="ca942-142">Local Media Optimization</span></span> 

  <span data-ttu-id="ca942-143">Contoso ha sfruttato l'ottimizzazione dei contenuti multimediali locali in posizioni in cui è stato eseguito un trunk diretto per il sistema telefonico Microsoft sfruttato da siti remoti.</span><span class="sxs-lookup"><span data-stu-id="ca942-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="ca942-144">Per altre informazioni, vedere [pianificare l'ottimizzazione di elementi multimediali locali](direct-routing-media-optimization.md) e [configurare l'ottimizzazione dei contenuti multimediali locali](direct-routing-media-optimization-configure.md).</span><span class="sxs-lookup"><span data-stu-id="ca942-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="ca942-145">Operatori automatici e code di chiamata</span><span class="sxs-lookup"><span data-stu-id="ca942-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="ca942-146">Come risultato di Covid-19, Contoso ha voluto prestare supporto per il receptionist mentre il personale funzionava in remoto.</span><span class="sxs-lookup"><span data-stu-id="ca942-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="ca942-147">Contoso ha usato gli operatori automatici e le code di chiamata per gestire le chiamate in arrivo al numero di telefono del receptionist.</span><span class="sxs-lookup"><span data-stu-id="ca942-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="ca942-148">Per altre informazioni, vedere [Case Study di Contoso: operatori automatici e code di chiamata](voice-case-study-call-queues.md).</span><span class="sxs-lookup"><span data-stu-id="ca942-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>  


