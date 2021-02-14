---
title: Case study su Teams per Contoso
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 06/17/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365solution-voice
ms.reviewer: jowrig
search.appverid: MET150
f1.keywords:
- NOCSH
description: Case study vocale di Teams per multi-national corporation
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3a964075dfae514759309a81a7d7140cddd10220
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701224"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="74b88-103">Case study contoso: Panoramica della migrazione vocale di Teams</span><span class="sxs-lookup"><span data-stu-id="74b88-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="74b88-104">Questo articolo presenta un case study sul modo in cui una multinazionale fittizia, Contoso, ha implementato una soluzione vocale di Teams per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="74b88-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="74b88-105">Contoso ha distribuito Microsoft 365 Enterprise e ha definito le principali decisioni di progettazione e dettagli di implementazione per: rete, identità, Windows 10 Enterprise, Office 365 ProPlus, gestione di dispositivi mobili, protezione delle informazioni, sicurezza, aggiornamento da Skype for Business a Teams, Sistema telefonico e Audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="74b88-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="74b88-106">Questo articolo illustra in che modo Contoso ha eseguito la migrazione degli utenti locali a Teams per comunicazioni unificate, collaborazione e voce.</span><span class="sxs-lookup"><span data-stu-id="74b88-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="74b88-107">Per informazioni generali su come Contoso ha accelerato la trasformazione digitale usando i servizi cloud Microsoft, vedere tutti gli articoli di base a partire dalla panoramica [del case study di Contoso.](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="74b88-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="74b88-108">Negli articoli principali sono disponibili le informazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="74b88-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="74b88-109">Necessità dell'infrastruttura IT di Contoso</span><span class="sxs-lookup"><span data-stu-id="74b88-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="74b88-110">Rete</span><span class="sxs-lookup"><span data-stu-id="74b88-110">Networking</span></span>
- <span data-ttu-id="74b88-111">Identity</span><span class="sxs-lookup"><span data-stu-id="74b88-111">Identity</span></span>
- <span data-ttu-id="74b88-112">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="74b88-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="74b88-113">Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="74b88-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="74b88-114">Gestione di dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="74b88-114">Mobile device management</span></span>
- <span data-ttu-id="74b88-115">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="74b88-115">Information protection</span></span>
- <span data-ttu-id="74b88-116">Riepilogo della sicurezza di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="74b88-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="74b88-117">Team per un progetto top-secret</span><span class="sxs-lookup"><span data-stu-id="74b88-117">Team for a top-secret project</span></span>
- <span data-ttu-id="74b88-118">Sito di SharePoint Online per risorse digitali altamente riservate</span><span class="sxs-lookup"><span data-stu-id="74b88-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="74b88-119">Per informazioni sulla pianificazione di un aggiornamento, è possibile iniziare con l'aggiornamento [a Microsoft Teams.](upgrade-start-here.md)</span><span class="sxs-lookup"><span data-stu-id="74b88-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="74b88-120">Obiettivi aziendali di Contoso per Teams</span><span class="sxs-lookup"><span data-stu-id="74b88-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="74b88-121">Per eseguire la migrazione degli utenti locali a Teams per comunicazioni unificate, collaborazione e voce, Contoso ha deciso i seguenti obiettivi aziendali:</span><span class="sxs-lookup"><span data-stu-id="74b88-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="74b88-122">Abilitazione di Teams</span><span class="sxs-lookup"><span data-stu-id="74b88-122">Teams enablement</span></span> 

  <span data-ttu-id="74b88-123">Il team di comunicazione e collaborazione unificato di Contoso ha abilitato Teams con i criteri corretti per governare e consentire la collaborazione interna ed esterna sicura.</span><span class="sxs-lookup"><span data-stu-id="74b88-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="74b88-124">Aggiornamento da Skype for Business a Teams</span><span class="sxs-lookup"><span data-stu-id="74b88-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="74b88-125">Skype for Business è stato ampiamente distribuito all'interno di Contoso.</span><span class="sxs-lookup"><span data-stu-id="74b88-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="74b88-126">Con l'esigenza di spostare i sistemi legacy, Contoso ha deciso di aggiornare gli utenti di Skype for Business a Teams.</span><span class="sxs-lookup"><span data-stu-id="74b88-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="74b88-127">Per altre informazioni, vedere il case [study contoso: piano di aggiornamento di Teams.](voice-case-study-migration-plan.md)</span><span class="sxs-lookup"><span data-stu-id="74b88-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="74b88-128">Phone System</span><span class="sxs-lookup"><span data-stu-id="74b88-128">Phone System</span></span>  

  <span data-ttu-id="74b88-129">Skype for Business con voce aziendale è stato ampiamente distribuito all'interno di Contoso.</span><span class="sxs-lookup"><span data-stu-id="74b88-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="74b88-130">Con la necessità di spostare i sistemi legacy che rappresentavano l'hop successivo per i loro mediation server, Contoso ha eseguito la migrazione dei loro utenti VoIP aziendale di Skype for Business al Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="74b88-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="74b88-131">I siti Contoso usava il Piano per chiamate Microsoft, l'instradamento diretto del sistema telefonico o una combinazione di entrambi.</span><span class="sxs-lookup"><span data-stu-id="74b88-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="74b88-132">Per altre informazioni, vedere il [case study di Contoso: Sistema telefonico.](voice-case-study-phone-system.md)</span><span class="sxs-lookup"><span data-stu-id="74b88-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="74b88-133">Instradamento basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="74b88-133">Location-Based Routing</span></span> 

  <span data-ttu-id="74b88-134">Con le sedi di uffici in paesi regolamentati dalla telefonia, Contoso ha bisogno di ricreare il routing Location-Based presente in Skype for Business nella distribuzione del Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="74b88-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="74b88-135">Per altre informazioni, vedere il [case study contoso: Location-Based routing.](voice-case-study-location-based-routing.md)</span><span class="sxs-lookup"><span data-stu-id="74b88-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="74b88-136">Chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="74b88-136">Emergency Calling</span></span> 

  <span data-ttu-id="74b88-137">Dove è stato implementato il routing diretto, Contoso ha configurato le chiamate di emergenza con terze parti approvate.</span><span class="sxs-lookup"><span data-stu-id="74b88-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="74b88-138">Per ulteriori informazioni, consulta il [case study di Contoso: Chiamate di emergenza.](voice-case-study-emergency-calling.md)</span><span class="sxs-lookup"><span data-stu-id="74b88-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="74b88-139">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="74b88-139">Audio Conferencing</span></span> 

  <span data-ttu-id="74b88-140">Contoso ha configurato i numeri dei servizi di audioconferenza ospitati nel trunk SIP al proprio provider PSTN.</span><span class="sxs-lookup"><span data-stu-id="74b88-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="74b88-141">Per altre informazioni, vedere il [case study di Contoso: Audioconferenza.](voice-case-study-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="74b88-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="74b88-142">Ottimizzazione degli elementi multimediali locali</span><span class="sxs-lookup"><span data-stu-id="74b88-142">Local Media Optimization</span></span> 

  <span data-ttu-id="74b88-143">Contoso ha sfruttato l'Ottimizzazione supporto locale in posizioni in cui aveva un trunk di percorso diretto al Sistema telefonico Microsoft, sfruttato dai siti remoti.</span><span class="sxs-lookup"><span data-stu-id="74b88-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="74b88-144">Per altre informazioni, vedere [Pianificare l'ottimizzazione degli elementi](direct-routing-media-optimization.md) multimediali locali e Configurare [l'ottimizzazione degli elementi multimediali locali.](direct-routing-media-optimization-configure.md)</span><span class="sxs-lookup"><span data-stu-id="74b88-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="74b88-145">Operatori automatici e code di chiamata</span><span class="sxs-lookup"><span data-stu-id="74b88-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="74b88-146">In seguito al lavoro di Covid-19, Contoso ha voluto fornire assistenza all'addetto della reception mentre il personale lavora da remoto.</span><span class="sxs-lookup"><span data-stu-id="74b88-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="74b88-147">Contoso ha utilizzato operatori automatici e code di chiamata per gestire le chiamate in arrivo al numero di telefono dell'addetto alla reception.</span><span class="sxs-lookup"><span data-stu-id="74b88-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="74b88-148">Per ulteriori informazioni, consulta il [case study di Contoso: Operatori automatici e Code di chiamata.](voice-case-study-call-queues.md)</span><span class="sxs-lookup"><span data-stu-id="74b88-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>  


