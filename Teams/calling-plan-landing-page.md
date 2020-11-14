---
title: Piani di chiamata in Microsoft Teams
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
description: Determinare quale piano di chiamate di sistema telefonico Microsoft migliorerà la propria organizzazione con la voce cloud in teams.
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
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="1f76c-103">Qual è il piano di chiamata adatto alle proprie esigenze?</span><span class="sxs-lookup"><span data-stu-id="1f76c-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="1f76c-104">Hai completato l' [Introduzione](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="1f76c-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="1f76c-105">Si è implementato Teams nell'organizzazione, con [chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="1f76c-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="1f76c-106">Forse hai distribuito [riunioni & conferenze](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="1f76c-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="1f76c-107">Ora si è pronti per aggiungere carichi di lavoro cloud Voice e si è deciso di usare il sistema telefonico Microsoft con il piano chiamate per connettersi alla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="1f76c-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="1f76c-108">In questo articolo vengono illustrate le decisioni di distribuzione principali per i piani di chiamata e altre considerazioni che è consigliabile configurare, in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1f76c-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="1f76c-109">Per altre informazioni sulle offerte vocali di Microsoft Cloud, dovresti anche leggere [cloud Voice in Microsoft teams](cloud-voice-landing-page.md) .</span><span class="sxs-lookup"><span data-stu-id="1f76c-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="1f76c-110">Ulteriori informazioni sui piani per le chiamate</span><span class="sxs-lookup"><span data-stu-id="1f76c-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="1f76c-111">Gli articoli seguenti includono ulteriori informazioni sulla distribuzione e l'uso di piani di chiamata Microsoft:</span><span class="sxs-lookup"><span data-stu-id="1f76c-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="1f76c-112">Sistema telefonico in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="1f76c-112">Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="1f76c-113">Piani di chiamata per Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="1f76c-113">Calling Plans for Microsoft 365 or Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="1f76c-114">Configurare i piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="1f76c-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="1f76c-115">Decisioni chiave per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="1f76c-115">Core deployment decisions</span></span>

<span data-ttu-id="1f76c-116">Per usare Microsoft come gestore di telefonia, è necessario ottenere le licenze per il piano di chiamata e assegnarle agli utenti del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="1f76c-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="1f76c-117">Sono disponibili due tipi di piani per le chiamate:</span><span class="sxs-lookup"><span data-stu-id="1f76c-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="1f76c-118">Piani per chiamate nazionali</span><span class="sxs-lookup"><span data-stu-id="1f76c-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="1f76c-119">Piani per chiamate nazionali e internazionali</span><span class="sxs-lookup"><span data-stu-id="1f76c-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="1f76c-120">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="1f76c-120">Ask yourself</span></span>|<span data-ttu-id="1f76c-121">Azione</span><span class="sxs-lookup"><span data-stu-id="1f76c-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="1f76c-122">I piani di chiamata sono disponibili nell'area personale?</span><span class="sxs-lookup"><span data-stu-id="1f76c-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="1f76c-123">Quali posizioni utente avranno il servizio di piano chiamante?</span><span class="sxs-lookup"><span data-stu-id="1f76c-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="1f76c-124">Per altre informazioni, vedere [disponibilità di paesi e aree geografiche per i piani di audioconferenza e chiamate](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="1f76c-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="1f76c-125">I miei utenti hanno bisogno di chiamate internazionali?</span><span class="sxs-lookup"><span data-stu-id="1f76c-125">Do my users need international calling?</span></span> | <span data-ttu-id="1f76c-126">Per altre informazioni, vedere [chiamare piani per Microsoft 365 o Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="1f76c-126">For more information, see [Calling Plans for Microsoft 365 or Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="1f76c-127">Gli utenti hanno licenze per i piani di chiamata?</span><span class="sxs-lookup"><span data-stu-id="1f76c-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="1f76c-128">Per acquistare e assegnare licenze, vedere [passaggio 2: acquistare e assegnare licenze](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="1f76c-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="1f76c-129">I miei utenti hanno ciascuno un numero di telefono diretto verso l'interno?</span><span class="sxs-lookup"><span data-stu-id="1f76c-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="1f76c-130">Per ottenere i numeri di telefono, vedere [passaggio 3: ottenere i numeri di telefono](set-up-calling-plans.md#step-3-get-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="1f76c-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-microsoft-365-or-office-365"></a><span data-ttu-id="1f76c-131">Trasferire i numeri di telefono a Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="1f76c-131">Transfer phone numbers to Microsoft 365 or Office 365</span></span>

<span data-ttu-id="1f76c-132">È facile trasferire i numeri di telefono dal provider di servizi corrente in teams.</span><span class="sxs-lookup"><span data-stu-id="1f76c-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="1f76c-133">Dopo aver convertito i numeri di telefono in teams, Microsoft diventerà il proprio provider di servizi e gli verrà addebitato il numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="1f76c-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="1f76c-134">Per altre informazioni, vedere [trasferire i numeri di telefono in teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="1f76c-134">For more information, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="1f76c-135">Numeri di telefono e posizioni di emergenza</span><span class="sxs-lookup"><span data-stu-id="1f76c-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="1f76c-136">Con i piani per le chiamate in Microsoft 365 o Office 365, ogni utente dell'organizzazione deve avere un numero di telefono univoco diretto (DID) e un indirizzo di emergenza convalidato corrispondente.</span><span class="sxs-lookup"><span data-stu-id="1f76c-136">With Calling Plans in Microsoft 365 or Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="1f76c-137">È anche possibile specificare una posizione di emergenza all'interno dell'indirizzo di emergenza, ad esempio un numero di ufficio o un numero di piano.</span><span class="sxs-lookup"><span data-stu-id="1f76c-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="1f76c-138">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="1f76c-138">Ask yourself</span></span>|<span data-ttu-id="1f76c-139">Azione</span><span class="sxs-lookup"><span data-stu-id="1f76c-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="1f76c-140">Come si vuole che siano dettagliate le informazioni sull'indirizzo di emergenza e sulla posizione?</span><span class="sxs-lookup"><span data-stu-id="1f76c-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="1f76c-141">Per altre informazioni, vedere [quali sono le posizioni di emergenza, gli indirizzi e il routing delle chiamate?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span><span class="sxs-lookup"><span data-stu-id="1f76c-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="1f76c-142">Chiamata dell'identità</span><span class="sxs-lookup"><span data-stu-id="1f76c-142">Calling identity</span></span>

<span data-ttu-id="1f76c-143">Per impostazione predefinita, tutte le chiamate in uscita usano il numero di telefono assegnato come identità di chiamata (ID chiamante).</span><span class="sxs-lookup"><span data-stu-id="1f76c-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="1f76c-144">Il destinatario della chiamata può identificare rapidamente il chiamante e decidere se accettare o rifiutare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="1f76c-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="1f76c-145">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="1f76c-145">Ask yourself</span></span>|<span data-ttu-id="1f76c-146">Azione</span><span class="sxs-lookup"><span data-stu-id="1f76c-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="1f76c-147">Si vuole mascherare o disabilitare l'ID chiamante?</span><span class="sxs-lookup"><span data-stu-id="1f76c-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="1f76c-148">Per modificare o bloccare l'ID chiamante, vedere [impostare l'ID chiamante per un utente](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="1f76c-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||




