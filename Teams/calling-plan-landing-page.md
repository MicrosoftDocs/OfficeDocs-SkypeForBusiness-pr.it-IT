---
title: Piani per chiamate in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: Determinare quale piano per le chiamate al sistema telefonico Microsoft sarà più adatto all'organizzazione su Cloud Voice in Teams.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: b88af706f79dd195e2f9363ff45e586a1123686f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102732"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="8f2bd-103">Qual è il piano di chiamata adatto alle proprie esigenze?</span><span class="sxs-lookup"><span data-stu-id="8f2bd-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="8f2bd-104">È stata completata la [guida introduttiva.](get-started-with-teams-quick-start.md)</span><span class="sxs-lookup"><span data-stu-id="8f2bd-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="8f2bd-105">Si è implementato Teams nell'organizzazione, con [chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="8f2bd-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="8f2bd-106">È possibile che sia stata distribuita [una conferenza & riunioni.](deploy-meetings-microsoft-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="8f2bd-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="8f2bd-107">Ora si è pronti per aggiungere carichi di lavoro vocali nel cloud e si è deciso di usare Microsoft Phone System con piano per chiamate per connettersi alla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="8f2bd-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="8f2bd-108">Questo articolo descrive le decisioni di base relative alla distribuzione per i piani per chiamate e altre considerazioni da configurare, in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8f2bd-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="8f2bd-109">Per altre informazioni sulle offerte vocali cloud di Microsoft, leggere anche [Cloud Voice in Microsoft Teams.](cloud-voice-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="8f2bd-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="8f2bd-110">Altre informazioni sui Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="8f2bd-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="8f2bd-111">Gli articoli seguenti forniscono altre informazioni sulla distribuzione e l'uso di Piani per chiamate Microsoft:</span><span class="sxs-lookup"><span data-stu-id="8f2bd-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="8f2bd-112">Sistema telefonico in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="8f2bd-112">Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="8f2bd-113">Piani per chiamate per Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="8f2bd-113">Calling Plans for Microsoft 365 or Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="8f2bd-114">Configurare i piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="8f2bd-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="8f2bd-115">Decisioni chiave per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="8f2bd-115">Core deployment decisions</span></span>

<span data-ttu-id="8f2bd-116">Per usare Microsoft come gestore di telefonia, è necessario ottenere le licenze del Piano per chiamate e assegnarle agli utenti del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="8f2bd-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="8f2bd-117">Sono disponibili due tipi di Piani per chiamate:</span><span class="sxs-lookup"><span data-stu-id="8f2bd-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="8f2bd-118">Piani per chiamate nazionali</span><span class="sxs-lookup"><span data-stu-id="8f2bd-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="8f2bd-119">Piani per chiamate nazionali e internazionali</span><span class="sxs-lookup"><span data-stu-id="8f2bd-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="8f2bd-120">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="8f2bd-120">Ask yourself</span></span>|<span data-ttu-id="8f2bd-121">Azione</span><span class="sxs-lookup"><span data-stu-id="8f2bd-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="8f2bd-122">I Piani per chiamate sono disponibili nella mia area?</span><span class="sxs-lookup"><span data-stu-id="8f2bd-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="8f2bd-123">Quali località utente avranno il servizio Piano per le chiamate?</span><span class="sxs-lookup"><span data-stu-id="8f2bd-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="8f2bd-124">Per altre informazioni, vedere [Disponibilità di paesi e aree geografica per audioconferenze e piani per chiamate.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="8f2bd-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="8f2bd-125">Gli utenti hanno bisogno di chiamate internazionali?</span><span class="sxs-lookup"><span data-stu-id="8f2bd-125">Do my users need international calling?</span></span> | <span data-ttu-id="8f2bd-126">Per altre informazioni, vedere [Piani per chiamate per Microsoft 365 o Office 365.](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="8f2bd-126">For more information, see [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="8f2bd-127">Gli utenti hanno licenze per i Piani per chiamate?</span><span class="sxs-lookup"><span data-stu-id="8f2bd-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="8f2bd-128">Per acquistare e assegnare licenze, vedere [Passaggio 2: Acquistare e assegnare licenze.](set-up-calling-plans.md#step-2-buy-and-assign-licenses)</span><span class="sxs-lookup"><span data-stu-id="8f2bd-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="8f2bd-129">Tutti gli utenti hanno un numero di telefono DID (Direct Inward Dial) ?</span><span class="sxs-lookup"><span data-stu-id="8f2bd-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="8f2bd-130">Per ottenere i numeri di telefono, vedere [Passaggio 3: Ottenere numeri di telefono](set-up-calling-plans.md#step-3-get-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="8f2bd-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a><span data-ttu-id="8f2bd-131">Trasferire numeri di telefono in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="8f2bd-131">Transfer phone numbers to Microsoft 365 or Office 365</span></span>

<span data-ttu-id="8f2bd-132">È facile trasferire i numeri di telefono dal provider di servizi corrente a Teams.</span><span class="sxs-lookup"><span data-stu-id="8f2bd-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="8f2bd-133">Dopo aver portato i numeri di telefono in Teams, Microsoft diventerà il provider di servizi e ti addebiterà tali numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="8f2bd-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="8f2bd-134">Per altre informazioni, vedere [Trasferire numeri di telefono in Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="8f2bd-134">For more information, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="8f2bd-135">Numeri di telefono e posizioni di emergenza</span><span class="sxs-lookup"><span data-stu-id="8f2bd-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="8f2bd-136">Con Piani per chiamate in Microsoft 365 o Office 365, ogni utente dell'organizzazione deve avere un numero di telefono DID (Direct InWard Dial) univoco e un indirizzo di emergenza convalidato corrispondente.</span><span class="sxs-lookup"><span data-stu-id="8f2bd-136">With Calling Plans in Microsoft 365 or Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="8f2bd-137">È anche possibile specificare una posizione per gli interventi di emergenza all'interno dell'indirizzo di emergenza, ad esempio un numero di ufficio o un numero di piano.</span><span class="sxs-lookup"><span data-stu-id="8f2bd-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="8f2bd-138">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="8f2bd-138">Ask yourself</span></span>|<span data-ttu-id="8f2bd-139">Azione</span><span class="sxs-lookup"><span data-stu-id="8f2bd-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="8f2bd-140">Quanto è dettagliato l'indirizzo di emergenza e le informazioni sulla posizione?</span><span class="sxs-lookup"><span data-stu-id="8f2bd-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="8f2bd-141">Per altre informazioni, vedere [Che cosa sono le località di emergenza, gli indirizzi e il routing delle chiamate?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span><span class="sxs-lookup"><span data-stu-id="8f2bd-141">For more information, see [What are emergency locations, addresses, and call routing?](/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="8f2bd-142">Identità chiamante</span><span class="sxs-lookup"><span data-stu-id="8f2bd-142">Calling identity</span></span>

<span data-ttu-id="8f2bd-143">Per impostazione predefinita, tutte le chiamate in uscita usano il numero di telefono assegnato come identità chiamante (ID chiamante).</span><span class="sxs-lookup"><span data-stu-id="8f2bd-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="8f2bd-144">Il destinatario della chiamata può velocemente identificare e decidere se accettare o rifiutare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="8f2bd-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="8f2bd-145">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="8f2bd-145">Ask yourself</span></span>|<span data-ttu-id="8f2bd-146">Azione</span><span class="sxs-lookup"><span data-stu-id="8f2bd-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="8f2bd-147">Si vuole mascherare o disabilitare l'ID chiamante?</span><span class="sxs-lookup"><span data-stu-id="8f2bd-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="8f2bd-148">Per modificare o bloccare l'ID chiamante, vedere [Impostare l'ID chiamante per un utente.](set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="8f2bd-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||