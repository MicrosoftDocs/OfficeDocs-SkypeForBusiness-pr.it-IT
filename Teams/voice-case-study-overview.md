---
title: Teams caso di studio contoso vocale
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
description: Teams caso di studio vocale per multinazionali
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19200ec5ab1556b0f2b4fda2f389e60bc236015b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097492"
---
# <a name="contoso-case-study-teams-voice-migration-overview"></a><span data-ttu-id="43531-103">Case study contoso: panoramica Teams migrazione vocale</span><span class="sxs-lookup"><span data-stu-id="43531-103">Contoso case study: Teams voice migration overview</span></span>

<span data-ttu-id="43531-104">Questo articolo presenta un case study che illustra come una multinazionale fittizia, Contoso, ha implementato una soluzione vocale Teams per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="43531-104">This article introduces a case study for how a fictional multi-national corporation, Contoso, implemented a Teams voice solution for their organization.</span></span>

<span data-ttu-id="43531-105">Contoso ha distribuito Microsoft 365 Enterprise e ha indirizzato le principali decisioni di progettazione e dettagli di implementazione per i seguenti elementi: rete, identità, Windows 10 Enterprise, Office 365 ProPlus, gestione dei dispositivi mobili, protezione delle informazioni, sicurezza, aggiornamento da Skype for Business a Teams, Sistema telefonico e audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="43531-105">Contoso has deployed Microsoft 365 Enterprise and addressed major design decisions and implementation details for the following: networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, security, upgrade from Skype for Business to Teams, Phone System, and Audio Conferencing.</span></span>  

<span data-ttu-id="43531-106">Questo articolo illustra in che modo Contoso ha eseguito la migrazione degli utenti locali a Teams comunicazioni unificate, collaborazione e voce.</span><span class="sxs-lookup"><span data-stu-id="43531-106">This article focuses on how Contoso migrated their on-premises users to Teams for unified communication, collaboration, and voice.</span></span> <span data-ttu-id="43531-107">Per informazioni di base su come Contoso ha accelerato la trasformazione digitale usando i servizi cloud Di Microsoft, vedere tutti gli articoli di base che iniziano con la panoramica [del case study di Contoso.](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="43531-107">For background information about how Contoso accelerated their digital transformation by using Microsoft's cloud services, see all the core articles starting with the [Contoso case study overview](/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide).</span></span>

https://docs.microsoft.com/microsoft-365/enterprise/contoso-case-study?view=o365-worldwide 

<span data-ttu-id="43531-108">Negli articoli principali sono disponibili informazioni su quanto segue:</span><span class="sxs-lookup"><span data-stu-id="43531-108">In the core articles, you'll find information on the following:</span></span>  

- <span data-ttu-id="43531-109">Esigenze dell'infrastruttura IT di Contoso</span><span class="sxs-lookup"><span data-stu-id="43531-109">Contoso's IT infrastructure needs</span></span>
- <span data-ttu-id="43531-110">Rete</span><span class="sxs-lookup"><span data-stu-id="43531-110">Networking</span></span>
- <span data-ttu-id="43531-111">Identity</span><span class="sxs-lookup"><span data-stu-id="43531-111">Identity</span></span>
- <span data-ttu-id="43531-112">Windows 10 Enterprise</span><span class="sxs-lookup"><span data-stu-id="43531-112">Windows 10 Enterprise</span></span>
- <span data-ttu-id="43531-113">Office 365 Pro Plus</span><span class="sxs-lookup"><span data-stu-id="43531-113">Office 365 Pro Plus</span></span>
- <span data-ttu-id="43531-114">Gestione di dispositivi mobili</span><span class="sxs-lookup"><span data-stu-id="43531-114">Mobile device management</span></span>
- <span data-ttu-id="43531-115">Protezione delle informazioni</span><span class="sxs-lookup"><span data-stu-id="43531-115">Information protection</span></span>
- <span data-ttu-id="43531-116">Riepilogo della Microsoft 365 Enterprise sicurezza</span><span class="sxs-lookup"><span data-stu-id="43531-116">Summary of Microsoft 365 Enterprise security</span></span>
- <span data-ttu-id="43531-117">Team per un progetto top secret</span><span class="sxs-lookup"><span data-stu-id="43531-117">Team for a top-secret project</span></span>
- <span data-ttu-id="43531-118">SharePoint Sito online per risorse digitali altamente riservate</span><span class="sxs-lookup"><span data-stu-id="43531-118">SharePoint Online site for highly confidential digital assets</span></span>

<span data-ttu-id="43531-119">Per informazioni sulla pianificazione di un aggiornamento, è necessario iniziare con Introduzione [all'Microsoft Teams aggiornamento.](upgrade-start-here.md)</span><span class="sxs-lookup"><span data-stu-id="43531-119">For information about planning an upgrade, you'll want to start with [Getting started with your Microsoft Teams upgrade](upgrade-start-here.md).</span></span>

## <a name="contoso-business-goals-for-teams"></a><span data-ttu-id="43531-120">Obiettivi aziendali di Contoso per Teams</span><span class="sxs-lookup"><span data-stu-id="43531-120">Contoso business goals for Teams</span></span>

<span data-ttu-id="43531-121">Per eseguire la migrazione degli utenti locali a Teams comunicazioni unificate, collaborazione e voce, Contoso ha deciso gli obiettivi aziendali seguenti:</span><span class="sxs-lookup"><span data-stu-id="43531-121">To migrate their on-premises users to Teams for unified communication, collaboration, and voice, Contoso decided on the following business goals:</span></span>

- <span data-ttu-id="43531-122">Teams abilitazione</span><span class="sxs-lookup"><span data-stu-id="43531-122">Teams enablement</span></span> 

  <span data-ttu-id="43531-123">Il team di comunicazione e collaborazione unificato di Contoso ha Teams i criteri corretti per governare e abilitare la collaborazione interna ed esterna sicura.</span><span class="sxs-lookup"><span data-stu-id="43531-123">Contoso's unified communication and collaboration team enabled Teams with the correct policies to govern and enable secure internal and external collaboration.</span></span> 

- <span data-ttu-id="43531-124">Aggiornamento da Skype for Business a Teams</span><span class="sxs-lookup"><span data-stu-id="43531-124">Skype for Business to Teams upgrade</span></span> 

  <span data-ttu-id="43531-125">Skype for Business è stato ampiamente distribuito all'interno di Contoso.</span><span class="sxs-lookup"><span data-stu-id="43531-125">Skype for Business was widely deployed within Contoso.</span></span> <span data-ttu-id="43531-126">Con la necessità di allontanare i sistemi legacy, Contoso ha deciso di aggiornare i Skype for Business utenti a Teams.</span><span class="sxs-lookup"><span data-stu-id="43531-126">With the need to move off legacy systems, Contoso decided to upgrade their Skype for Business users to Teams.</span></span> <span data-ttu-id="43531-127">Per altre informazioni, vedere Case [study contoso: Teams di aggiornamento.](voice-case-study-migration-plan.md)</span><span class="sxs-lookup"><span data-stu-id="43531-127">For more information, see [Contoso case study: Teams upgrade plan](voice-case-study-migration-plan.md).</span></span>

- <span data-ttu-id="43531-128">Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="43531-128">Phone System</span></span>  

  <span data-ttu-id="43531-129">Skype for Business con voIP aziendale è stato ampiamente distribuito all'interno di Contoso.</span><span class="sxs-lookup"><span data-stu-id="43531-129">Skype for Business with enterprise voice was widely deployed within Contoso.</span></span> <span data-ttu-id="43531-130">Con la necessità di allontanare i sistemi legacy che rappresentavano l'hop successivo per i server di mediazione, Contoso ha eseguito la migrazione dei Skype for Business voIP aziendali a Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="43531-130">With the need to move off legacy systems that were the next hop for their mediation servers, Contoso migrated their Skype for Business enterprise voice users to Phone System.</span></span> <span data-ttu-id="43531-131">I siti contoso usava il piano per chiamate Microsoft, Sistema telefonico routing diretto o una combinazione di entrambi.</span><span class="sxs-lookup"><span data-stu-id="43531-131">Contoso sites used Microsoft Calling Plan, Phone System Direct Routing, or a combination of both.</span></span> <span data-ttu-id="43531-132">Per altre informazioni, vedere Case [study contoso: Sistema telefonico](voice-case-study-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="43531-132">For more information, see [Contoso case study: Phone System](voice-case-study-phone-system.md).</span></span>

- <span data-ttu-id="43531-133">Instradamento basato sulla posizione</span><span class="sxs-lookup"><span data-stu-id="43531-133">Location-Based Routing</span></span> 

  <span data-ttu-id="43531-134">Con le sedi degli uffici nei paesi regolamentati dalla telefonia, Contoso doveva ricreare il routing Location-Based che era presente in Skype for Business nella distribuzione Sistema telefonico rete.</span><span class="sxs-lookup"><span data-stu-id="43531-134">With office locations in telephony-regulated countries, Contoso needed to recreate the Location-Based Routing that was present in Skype for Business in their Phone System deployment.</span></span> <span data-ttu-id="43531-135">Per altre informazioni, vedere [Case study contoso: Location-Based Routing](voice-case-study-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="43531-135">For more information, see [Contoso case study: Location-Based Routing](voice-case-study-location-based-routing.md).</span></span>

- <span data-ttu-id="43531-136">Chiamate di emergenza</span><span class="sxs-lookup"><span data-stu-id="43531-136">Emergency Calling</span></span> 

  <span data-ttu-id="43531-137">Dove è stato implementato Il routing diretto, Contoso ha configurato le chiamate di emergenza con terze parti approvate.</span><span class="sxs-lookup"><span data-stu-id="43531-137">Where Direct Routing was implemented, Contoso set up emergency calling with approved third parties.</span></span> <span data-ttu-id="43531-138">Per altre informazioni, vedere Caso [di studio Contoso: Chiamate di emergenza.](voice-case-study-emergency-calling.md)</span><span class="sxs-lookup"><span data-stu-id="43531-138">For more information, see [Contoso case study: Emergency Calling](voice-case-study-emergency-calling.md).</span></span>

- <span data-ttu-id="43531-139">Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="43531-139">Audio Conferencing</span></span> 

  <span data-ttu-id="43531-140">Contoso configura i numeri dei servizi di audioconferenza ospitati nel trunk SIP al provider PSTN.</span><span class="sxs-lookup"><span data-stu-id="43531-140">Contoso set up Audio Conferencing service numbers that were hosted on their SIP trunk to their PSTN provider.</span></span> <span data-ttu-id="43531-141">Per altre informazioni, vedere Case [study contoso: Audioconferenza.](voice-case-study-audio-conferencing.md)</span><span class="sxs-lookup"><span data-stu-id="43531-141">For more information, see [Contoso case study: Audio Conferencing](voice-case-study-audio-conferencing.md).</span></span> 

- <span data-ttu-id="43531-142">Ottimizzazione del supporto locale</span><span class="sxs-lookup"><span data-stu-id="43531-142">Local Media Optimization</span></span> 

  <span data-ttu-id="43531-143">Contoso ha sfruttato l'Ottimizzazione multimediale locale in posizioni in cui aveva un unico trunk di percorso diretto Telefono Microsoft sistema che è stato sfruttato da siti remoti.</span><span class="sxs-lookup"><span data-stu-id="43531-143">Contoso took advantage of Local Media Optimization in locations where they had one direct route trunk to Microsoft Phone System that was leveraged by remote sites.</span></span> <span data-ttu-id="43531-144">Per altre informazioni, vedere [Pianificare l'ottimizzazione dei supporti locali](direct-routing-media-optimization.md) [e Configurare l'ottimizzazione dei supporti multimediali locali.](direct-routing-media-optimization-configure.md)</span><span class="sxs-lookup"><span data-stu-id="43531-144">For more information, see [Plan for Local Media Optimization](direct-routing-media-optimization.md) and [Configure Local Media Optimization](direct-routing-media-optimization-configure.md).</span></span>

- <span data-ttu-id="43531-145">Operatori automatici e code di chiamata</span><span class="sxs-lookup"><span data-stu-id="43531-145">Auto Attendants and Call Queues</span></span>

  <span data-ttu-id="43531-146">Come risultato di Covid-19, Contoso voleva fornire supporto per l'addetto alla reception mentre il personale stava lavorando in remoto.</span><span class="sxs-lookup"><span data-stu-id="43531-146">As a result of Covid-19, Contoso wanted to provide receptionist support while their staff was working remotely.</span></span> <span data-ttu-id="43531-147">Contoso ha usato operatori automatici e code di chiamata per gestire le chiamate in arrivo al numero di telefono dell'addetto alla ricezione.</span><span class="sxs-lookup"><span data-stu-id="43531-147">Contoso used auto attendants and call queues to manage incoming calls to their receptionist's phone number.</span></span> <span data-ttu-id="43531-148">Per altre informazioni, vedere [Case study contoso: Operatori automatici e code di chiamata.](voice-case-study-call-queues.md)</span><span class="sxs-lookup"><span data-stu-id="43531-148">For more information, see [Contoso case study: Auto Attendants and Call Queues](voice-case-study-call-queues.md).</span></span>