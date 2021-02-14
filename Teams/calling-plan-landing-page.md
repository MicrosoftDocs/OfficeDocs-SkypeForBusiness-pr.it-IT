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
description: Determinare quale piano per le chiamate del sistema telefonico Microsoft sarà più adatto per l'organizzazione su Cloud Voice in Teams.
ms.custom: seo-marvel-mar2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 71fe92646a3a2976e9a4d393e54ea56a7669b400
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031852"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="c35b4-103">Qual è il piano di chiamata adatto alle proprie esigenze?</span><span class="sxs-lookup"><span data-stu-id="c35b4-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="c35b4-104">La guida introduttiva [è stata completata.](get-started-with-teams-quick-start.md)</span><span class="sxs-lookup"><span data-stu-id="c35b4-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="c35b4-105">Si è implementato Teams nell'organizzazione, con [chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="c35b4-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="c35b4-106">Potresti aver distribuito Riunioni [o conferenze &.](deploy-meetings-microsoft-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="c35b4-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="c35b4-107">Ora sei pronto per aggiungere carichi di lavoro vocali nel cloud e hai deciso di usare il Sistema telefonico Microsoft con piano per le chiamate per connetterti alla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="c35b4-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="c35b4-108">Questo articolo descrive le decisioni di distribuzione di base per i piani per chiamate, oltre a considerazioni aggiuntive che è possibile configurare, in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c35b4-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="c35b4-109">Per altre informazioni sulle offerte vocali cloud di Microsoft, è consigliabile leggere anche [Cloud Voice in Microsoft Teams.](cloud-voice-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="c35b4-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="c35b4-110">Ulteriori informazioni sui Piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="c35b4-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="c35b4-111">Gli articoli seguenti forniscono altre informazioni sulla distribuzione e l'utilizzo dei Piani per chiamate Microsoft:</span><span class="sxs-lookup"><span data-stu-id="c35b4-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="c35b4-112">Sistema telefonico in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="c35b4-112">Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="c35b4-113">Piani per chiamate per Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="c35b4-113">Calling Plans for Microsoft 365 or Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="c35b4-114">Configurare i piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="c35b4-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="c35b4-115">Decisioni chiave per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="c35b4-115">Core deployment decisions</span></span>

<span data-ttu-id="c35b4-116">Per utilizzare Microsoft come gestore telefonico, è necessario ottenere le licenze del Piano per chiamate e assegnarle agli utenti del Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="c35b4-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="c35b4-117">Sono disponibili due tipi di Piani per chiamate:</span><span class="sxs-lookup"><span data-stu-id="c35b4-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="c35b4-118">Piani per chiamate nazionali</span><span class="sxs-lookup"><span data-stu-id="c35b4-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="c35b4-119">Piani per chiamate nazionali e internazionali</span><span class="sxs-lookup"><span data-stu-id="c35b4-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="c35b4-120">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="c35b4-120">Ask yourself</span></span>|<span data-ttu-id="c35b4-121">Azione</span><span class="sxs-lookup"><span data-stu-id="c35b4-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="c35b4-122">I Piani per chiamate sono disponibili nella mia area?</span><span class="sxs-lookup"><span data-stu-id="c35b4-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="c35b4-123">Quali località utente hanno il servizio Piano per chiamate?</span><span class="sxs-lookup"><span data-stu-id="c35b4-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="c35b4-124">Per ulteriori informazioni, consulta La [disponibilità del Paese e dell'area geografica per Audioconferenze e Piani per chiamate.](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)</span><span class="sxs-lookup"><span data-stu-id="c35b4-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="c35b4-125">Gli utenti devono effettuare chiamate internazionali?</span><span class="sxs-lookup"><span data-stu-id="c35b4-125">Do my users need international calling?</span></span> | <span data-ttu-id="c35b4-126">Per ulteriori informazioni, consulta [Piani per chiamate per Microsoft 365 o Office 365.](calling-plans-for-office-365.md)</span><span class="sxs-lookup"><span data-stu-id="c35b4-126">For more information, see [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="c35b4-127">Gli utenti hanno licenze di Piani per chiamate?</span><span class="sxs-lookup"><span data-stu-id="c35b4-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="c35b4-128">Per acquistare e assegnare licenze, vedere [il passaggio 2: Acquistare e assegnare licenze.](set-up-calling-plans.md#step-2-buy-and-assign-licenses)</span><span class="sxs-lookup"><span data-stu-id="c35b4-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="c35b4-129">Gli utenti hanno ciascuno un numero di telefono di chiamata diretta verso l'interno (DID)?</span><span class="sxs-lookup"><span data-stu-id="c35b4-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="c35b4-130">Per ottenere i numeri di telefono, [vedi Passaggio 3: Ottenere i numeri di telefono.](set-up-calling-plans.md#step-3-get-phone-numbers)</span><span class="sxs-lookup"><span data-stu-id="c35b4-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a><span data-ttu-id="c35b4-131">Trasferire numeri di telefono a Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="c35b4-131">Transfer phone numbers to Microsoft 365 or Office 365</span></span>

<span data-ttu-id="c35b4-132">È facile trasferire i numeri di telefono dal provider di servizi corrente a Teams.</span><span class="sxs-lookup"><span data-stu-id="c35b4-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="c35b4-133">Dopo il portabilità dei numeri di telefono in Teams, Microsoft diventa il tuo provider di servizi e ti addebita i numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="c35b4-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="c35b4-134">Per altre informazioni, vedere [Trasferire numeri di telefono in Teams.](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)</span><span class="sxs-lookup"><span data-stu-id="c35b4-134">For more information, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="c35b4-135">Numeri di telefono e posizioni di emergenza</span><span class="sxs-lookup"><span data-stu-id="c35b4-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="c35b4-136">Con i Piani per chiamate in Microsoft 365 o Office 365, ogni utente dell'organizzazione deve avere un numero di telefono DID (Direct Inward Dial) univoco e un indirizzo di emergenza convalidato corrispondente.</span><span class="sxs-lookup"><span data-stu-id="c35b4-136">With Calling Plans in Microsoft 365 or Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="c35b4-137">Puoi anche specificare una posizione per gli interventi di emergenza all'interno dell'indirizzo per gli interventi di emergenza (ad esempio, un numero di ufficio o un numero di piano).</span><span class="sxs-lookup"><span data-stu-id="c35b4-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="c35b4-138">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="c35b4-138">Ask yourself</span></span>|<span data-ttu-id="c35b4-139">Azione</span><span class="sxs-lookup"><span data-stu-id="c35b4-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="c35b4-140">Quanto sono dettagliati i dati sull'indirizzo e sulla posizione per gli interventi di emergenza?</span><span class="sxs-lookup"><span data-stu-id="c35b4-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="c35b4-141">Per ulteriori informazioni, consulta Cosa sono il routing delle chiamate, gli indirizzi e le posizioni [per gli interventi di emergenza?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing)</span><span class="sxs-lookup"><span data-stu-id="c35b4-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="c35b4-142">Identità delle chiamate</span><span class="sxs-lookup"><span data-stu-id="c35b4-142">Calling identity</span></span>

<span data-ttu-id="c35b4-143">Per impostazione predefinita, tutte le chiamate in uscita usano il numero di telefono assegnato come identità chiamante (ID chiamante).</span><span class="sxs-lookup"><span data-stu-id="c35b4-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="c35b4-144">Il destinatario della chiamata può velocemente identificare e decidere se accettare o rifiutare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="c35b4-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="c35b4-145">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="c35b4-145">Ask yourself</span></span>|<span data-ttu-id="c35b4-146">Azione</span><span class="sxs-lookup"><span data-stu-id="c35b4-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="c35b4-147">Si vuole mascherare o disabilitare l'ID chiamante?</span><span class="sxs-lookup"><span data-stu-id="c35b4-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="c35b4-148">Per modificare o bloccare l'ID chiamante, vedere [Impostare l'ID chiamante per un utente.](set-the-caller-id-for-a-user.md)</span><span class="sxs-lookup"><span data-stu-id="c35b4-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||




