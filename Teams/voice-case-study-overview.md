---
title: Case study di Teams voice Contoso
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
description: Case study vocale di Teams per multinazionali
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19200ec5ab1556b0f2b4fda2f389e60bc236015b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097492"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="bcc2e-103">Case study contoso: Panoramica della migrazione vocale di Teams</span><span class="sxs-lookup"><span data-stu-id="bcc2e-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="bcc2e-104">Questo articolo presenta un case study che illustra come una multinazionale fittizia, Contoso, ha implementato una soluzione vocale di Teams per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="bcc2e-105">Contoso ha distribuito Microsoft 365 Enterprise e ha indirizzato le principali decisioni di progettazione e i dettagli di implementazione per i seguenti elementi: rete, identità, Windows 10 Enterprise, Office 365 ProPlus, gestione dei dispositivi mobili, protezione delle informazioni, sicurezza, aggiornamento da Skype for Business a Teams, Sistema telefonico e Audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="bcc2e-106">Questo articolo illustra in che modo Contoso ha eseguito la migrazione degli utenti locali a Teams per comunicazioni unificate, collaborazione e voce.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="bcc2e-107">Per informazioni di base su come Contoso ha accelerato la trasformazione digitale usando i servizi cloud Di Microsoft, vedere tutti gli articoli di base che iniziano con la panoramica [del case study di Contoso.](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="bcc2e-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="bcc2e-108">Negli articoli principali sono disponibili informazioni su quanto segue:</span><span class="sxs-lookup"><span data-stu-id="bcc2e-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="bcc2e-109">Esigenze dell'infrastruttura IT di Contoso</span><span class="sxs-lookup"><span data-stu-id="bcc2e-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="bcc2e-110">Rete</span><span class="sxs-lookup"><span data-stu-id="bcc2e-110">Networking</span></span>
- <span data-ttu-id="bcc2e-111">Identity</span><span class="sxs-lookup"><span data-stu-id="bcc2e-111">Identity</span></span>
- <span data-ttu-id="bcc2e-112">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bcc2e-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="bcc2e-113">Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="bcc2e-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="bcc2e-114">Gestione di dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="bcc2e-114">Mobile device management</span></span>
- <span data-ttu-id="bcc2e-115">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="bcc2e-115">Information protection</span></span>
- <span data-ttu-id="bcc2e-116">Riepilogo della sicurezza di Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="bcc2e-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="bcc2e-117">Team per un progetto top secret</span><span class="sxs-lookup"><span data-stu-id="bcc2e-117">Team for a top-secret project</span></span>
- <span data-ttu-id="bcc2e-118">Sito di SharePoint Online per risorse digitali altamente riservate</span><span class="sxs-lookup"><span data-stu-id="bcc2e-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="bcc2e-119">Per informazioni sulla pianificazione di un aggiornamento, è necessario iniziare con Introduzione [all'aggiornamento di Microsoft Teams.](upgrade-start-here.md)</span><span class="sxs-lookup"><span data-stu-id="bcc2e-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="bcc2e-120">Obiettivi aziendali contoso per Teams</span><span class="sxs-lookup"><span data-stu-id="bcc2e-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="bcc2e-121">Per eseguire la migrazione degli utenti locali a Teams per comunicazioni unificate, collaborazione e voce, Contoso ha deciso gli obiettivi aziendali seguenti:</span><span class="sxs-lookup"><span data-stu-id="bcc2e-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="bcc2e-122">Abilitazione di Teams</span><span class="sxs-lookup"><span data-stu-id="bcc2e-122">Teams enablement</span></span> 

  <span data-ttu-id="bcc2e-123">Il team di comunicazione e collaborazione unificato di Contoso ha abilitato Teams con i criteri corretti per governare e abilitare la collaborazione interna ed esterna sicura.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="bcc2e-124">Aggiornamento da Skype for Business a Teams</span><span class="sxs-lookup"><span data-stu-id="bcc2e-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="bcc2e-125">Skype for Business è stato ampiamente distribuito all'interno di Contoso.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="bcc2e-126">Con la necessità di allontanare i sistemi legacy, Contoso ha deciso di aggiornare gli utenti skype for business a Teams.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="bcc2e-127">Per altre informazioni, vedere Case [study contoso: Piano di aggiornamento di Teams.](voice-case-study-migration-plan.md)</span><span class="sxs-lookup"><span data-stu-id="bcc2e-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="bcc2e-128">Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="bcc2e-128">Phone System</span></span>  

  <span data-ttu-id="bcc2e-129">Skype for Business con voIP aziendale è stato ampiamente distribuito all'interno di Contoso.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="bcc2e-130">Con la necessità di allontanare i sistemi legacy che rappresentavano l'hop successivo per i server di mediazione, Contoso ha eseguito la migrazione degli utenti voIP aziendali Skype for Business a Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="bcc2e-131">I siti contoso hanno usato Microsoft Calling Plan, Phone System Direct Routing o una combinazione di entrambi.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="bcc2e-132">Per altre informazioni, vedere Caso [di studio contoso: Sistema telefonico](voice-case-study-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="bcc2e-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="bcc2e-133">Instradamento basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="bcc2e-133">Location-Based Routing</span></span> 

  <span data-ttu-id="bcc2e-134">Con le sedi degli uffici nei paesi regolamentati dalla telefonia, Contoso doveva ricreare il routing Location-Based che era presente in Skype for Business nella distribuzione del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="bcc2e-135">Per altre informazioni, vedere [Case study contoso: Location-Based Routing](voice-case-study-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="bcc2e-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="bcc2e-136">Chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="bcc2e-136">Emergency Calling</span></span> 

  <span data-ttu-id="bcc2e-137">Dove è stato implementato Il routing diretto, Contoso ha configurato le chiamate di emergenza con terze parti approvate.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="bcc2e-138">Per altre informazioni, vedere Caso [di studio Contoso: Chiamate di emergenza.](voice-case-study-emergency-calling.md)</span><span class="sxs-lookup"><span data-stu-id="bcc2e-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="bcc2e-139">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="bcc2e-139">Audio Conferencing</span></span> 

  <span data-ttu-id="bcc2e-140">Contoso configura i numeri dei servizi di audioconferenza ospitati nel trunk SIP al provider PSTN.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="bcc2e-141">Per altre informazioni, vedere Case [study contoso: Audioconferenza.](voice-case-study-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="bcc2e-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="bcc2e-142">Ottimizzazione del supporto locale</span><span class="sxs-lookup"><span data-stu-id="bcc2e-142">Local Media Optimization</span></span> 

  <span data-ttu-id="bcc2e-143">Contoso ha sfruttato l'Ottimizzazione multimediale locale nelle posizioni in cui aveva un unico trunk di percorso diretto a Microsoft Phone System che è stato sfruttato da siti remoti.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="bcc2e-144">Per altre informazioni, vedere [Pianificare l'ottimizzazione dei supporti locali](direct-routing-media-optimization.md) [e Configurare l'ottimizzazione dei supporti multimediali locali.](direct-routing-media-optimization-configure.md)</span><span class="sxs-lookup"><span data-stu-id="bcc2e-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="bcc2e-145">Operatori automatici e code di chiamata</span><span class="sxs-lookup"><span data-stu-id="bcc2e-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="bcc2e-146">Come risultato di Covid-19, Contoso voleva fornire supporto per l'addetto alla reception mentre il personale stava lavorando in remoto.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="bcc2e-147">Contoso ha usato operatori automatici e code di chiamata per gestire le chiamate in arrivo al numero di telefono dell'addetto alla ricezione.</span><span class="sxs-lookup"><span data-stu-id="bcc2e-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="bcc2e-148">Per altre informazioni, vedere [Case study contoso: Operatori automatici e code di chiamata.](voice-case-study-call-queues.md)</span><span class="sxs-lookup"><span data-stu-id="bcc2e-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>