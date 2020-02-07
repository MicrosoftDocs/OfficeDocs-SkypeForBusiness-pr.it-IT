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
f1.keywords:
- NOCSH
ms.reviewer: crowe
search.appverid: MET150
description: Pagina di destinazione del piano chiamante
appliesto:
- Microsoft Teams
ms.openlocfilehash: c62ce8a891244920257623aea9a62859161a129f
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825194"
---
# <a name="which-calling-plan-is-right-for-you"></a><span data-ttu-id="085e8-103">Qual è il piano di chiamata adatto alle proprie esigenze?</span><span class="sxs-lookup"><span data-stu-id="085e8-103">Which Calling Plan is right for you?</span></span> 

<span data-ttu-id="085e8-104">Hai completato l' [Introduzione](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="085e8-104">You've completed the [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="085e8-105">Si è implementato Teams nell'organizzazione, con [chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="085e8-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="085e8-106">Forse hai distribuito [riunioni & conferenze](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="085e8-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="085e8-107">Ora si è pronti per aggiungere carichi di lavoro cloud Voice e si è deciso di usare il sistema telefonico Microsoft con il piano chiamate per connettersi alla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="085e8-107">Now you're ready to add cloud voice workloads, and you've decided to use Microsoft Phone System with Calling Plan to connect to the Public Switched Telephone Network (PSTN).</span></span> 

<span data-ttu-id="085e8-108">In questo articolo vengono illustrate le decisioni di distribuzione principali per i piani di chiamata e altre considerazioni che è consigliabile configurare, in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="085e8-108">This article describes core deployment decisions for Calling Plans as well as additional considerations you may want to configure, based on your organization's needs.</span></span> <span data-ttu-id="085e8-109">Per altre informazioni sulle offerte vocali di Microsoft Cloud, dovresti anche leggere [cloud Voice in Microsoft teams](cloud-voice-landing-page.md) .</span><span class="sxs-lookup"><span data-stu-id="085e8-109">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>


## <a name="learn-more-about-calling-plans"></a><span data-ttu-id="085e8-110">Ulteriori informazioni sui piani per le chiamate</span><span class="sxs-lookup"><span data-stu-id="085e8-110">Learn more about Calling Plans</span></span>

<span data-ttu-id="085e8-111">Gli articoli seguenti includono ulteriori informazioni sulla distribuzione e l'uso di piani di chiamata Microsoft:</span><span class="sxs-lookup"><span data-stu-id="085e8-111">The following articles provide more information about deploying and using Microsoft Calling Plans:</span></span>

- [<span data-ttu-id="085e8-112">Sistema telefonico di Office 365</span><span class="sxs-lookup"><span data-stu-id="085e8-112">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="085e8-113">Piani di chiamata per Office 365</span><span class="sxs-lookup"><span data-stu-id="085e8-113">Calling Plans for Office 365</span></span>](calling-plans-for-office-365.md)
- [<span data-ttu-id="085e8-114">Configurare i piani per chiamate</span><span class="sxs-lookup"><span data-stu-id="085e8-114">Set up Calling Plans</span></span>](set-up-calling-plans.md)


## <a name="core-deployment-decisions"></a><span data-ttu-id="085e8-115">Decisioni chiave per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="085e8-115">Core deployment decisions</span></span>

<span data-ttu-id="085e8-116">Per usare Microsoft come gestore di telefonia, è necessario ottenere le licenze per il piano di chiamata e assegnarle agli utenti del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="085e8-116">To use Microsoft as your telephony carrier, you need to obtain Calling Plan licenses and assign them to your Phone System users.</span></span> 

<span data-ttu-id="085e8-117">Sono disponibili due tipi di piani per le chiamate:</span><span class="sxs-lookup"><span data-stu-id="085e8-117">There are two types of Calling Plans available:</span></span>

- <span data-ttu-id="085e8-118">Piani per chiamate nazionali</span><span class="sxs-lookup"><span data-stu-id="085e8-118">Domestic Calling Plans</span></span> 
- <span data-ttu-id="085e8-119">Piani per chiamate nazionali e internazionali</span><span class="sxs-lookup"><span data-stu-id="085e8-119">Domestic and International Calling Plans</span></span>

|<span data-ttu-id="085e8-120">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="085e8-120">Ask yourself</span></span>|<span data-ttu-id="085e8-121">Azione</span><span class="sxs-lookup"><span data-stu-id="085e8-121">Action</span></span> |
|------------|-------|
|<span data-ttu-id="085e8-122">I piani di chiamata sono disponibili nell'area personale?</span><span class="sxs-lookup"><span data-stu-id="085e8-122">Are Calling Plans available in my area?</span></span> <span data-ttu-id="085e8-123">Quali posizioni utente avranno il servizio di piano chiamante?</span><span class="sxs-lookup"><span data-stu-id="085e8-123">Which user locations will have Calling Plan service?</span></span> | <span data-ttu-id="085e8-124">Per altre informazioni, vedere [disponibilità di paesi e aree geografiche per i piani di audioconferenza e chiamate](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="085e8-124">For more information, see [Country and region availability for Audio Conferencing and Calling Plans](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md).</span></span> | 
<span data-ttu-id="085e8-125">I miei utenti hanno bisogno di chiamate internazionali?</span><span class="sxs-lookup"><span data-stu-id="085e8-125">Do my users need international calling?</span></span> | <span data-ttu-id="085e8-126">Per altre informazioni, vedere [chiamare piani per Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="085e8-126">For more information, see [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span> |
<span data-ttu-id="085e8-127">Gli utenti hanno licenze per i piani di chiamata?</span><span class="sxs-lookup"><span data-stu-id="085e8-127">Do my users have Calling Plans licenses?</span></span> | <span data-ttu-id="085e8-128">Per acquistare e assegnare licenze, vedere [passaggio 2: acquistare e assegnare licenze](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span><span class="sxs-lookup"><span data-stu-id="085e8-128">To buy and assign licenses, see [Step 2: Buy and assign licenses](set-up-calling-plans.md#step-2-buy-and-assign-licenses).</span></span> |
<span data-ttu-id="085e8-129">I miei utenti hanno ciascuno un numero di telefono diretto verso l'interno?</span><span class="sxs-lookup"><span data-stu-id="085e8-129">Do my users each have a direct inward dial (DID) phone number?</span></span> | <span data-ttu-id="085e8-130">Per ottenere i numeri di telefono, vedere [passaggio 3: ottenere i numeri di telefono](set-up-calling-plans.md#step-3-get-phone-numbers).</span><span class="sxs-lookup"><span data-stu-id="085e8-130">To get phone numbers, see [Step 3: Get phone numbers](set-up-calling-plans.md#step-3-get-phone-numbers).</span></span> |
|||

### <a name="transfer-phone-numbers-to-office-365"></a><span data-ttu-id="085e8-131">Trasferire numeri di telefono in Office 365</span><span class="sxs-lookup"><span data-stu-id="085e8-131">Transfer phone numbers to Office 365</span></span>

<span data-ttu-id="085e8-132">È facile trasferire i numeri di telefono dal provider di servizi corrente in teams.</span><span class="sxs-lookup"><span data-stu-id="085e8-132">It's easy to transfer your phone numbers from your current service provider to Teams.</span></span> <span data-ttu-id="085e8-133">Dopo aver convertito i numeri di telefono in teams, Microsoft diventerà il proprio provider di servizi e gli verrà addebitato il numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="085e8-133">After you port your phone numbers to Teams, Microsoft will become your service provider and will bill you for those phone numbers.</span></span> <span data-ttu-id="085e8-134">Per altre informazioni, vedere [trasferire i numeri di telefono in teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="085e8-134">For more information, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>


### <a name="phone-numbers-and-emergency-locations"></a><span data-ttu-id="085e8-135">Numeri di telefono e posizioni di emergenza</span><span class="sxs-lookup"><span data-stu-id="085e8-135">Phone numbers and emergency locations</span></span>

<span data-ttu-id="085e8-136">Con i piani per le chiamate in Office 365, ogni utente dell'organizzazione deve avere un numero di telefono univoco diretto (DID) e un indirizzo di emergenza convalidato corrispondente.</span><span class="sxs-lookup"><span data-stu-id="085e8-136">With Calling Plans in Office 365, every user in your organization needs to have a unique direct inward dial (DID) phone number and a corresponding validated emergency address.</span></span> <span data-ttu-id="085e8-137">È anche possibile specificare una posizione di emergenza all'interno dell'indirizzo di emergenza, ad esempio un numero di ufficio o un numero di piano.</span><span class="sxs-lookup"><span data-stu-id="085e8-137">You can also specify an emergency location within the emergency address (for example, an office number or floor number).</span></span> 

|<span data-ttu-id="085e8-138">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="085e8-138">Ask yourself</span></span>|<span data-ttu-id="085e8-139">Azione</span><span class="sxs-lookup"><span data-stu-id="085e8-139">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="085e8-140">Come si vuole che siano dettagliate le informazioni sull'indirizzo di emergenza e sulla posizione?</span><span class="sxs-lookup"><span data-stu-id="085e8-140">How detailed do I want the emergency address and location information to be?</span></span> |<span data-ttu-id="085e8-141">Per altre informazioni, vedere [quali sono le posizioni di emergenza, gli indirizzi e il routing delle chiamate?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span><span class="sxs-lookup"><span data-stu-id="085e8-141">For more information, see [What are emergency locations, addresses, and call routing?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-emergency-locations-addresses-and-call-routing).</span></span>


### <a name="calling-identity"></a><span data-ttu-id="085e8-142">Chiamata dell'identità</span><span class="sxs-lookup"><span data-stu-id="085e8-142">Calling identity</span></span>

<span data-ttu-id="085e8-143">Per impostazione predefinita, tutte le chiamate in uscita usano il numero di telefono assegnato come identità di chiamata (ID chiamante).</span><span class="sxs-lookup"><span data-stu-id="085e8-143">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="085e8-144">Il destinatario della chiamata può identificare rapidamente il chiamante e decidere se accettare o rifiutare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="085e8-144">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="085e8-145">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="085e8-145">Ask yourself</span></span>|<span data-ttu-id="085e8-146">Azione</span><span class="sxs-lookup"><span data-stu-id="085e8-146">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="085e8-147">Si vuole mascherare o disabilitare l'ID chiamante?</span><span class="sxs-lookup"><span data-stu-id="085e8-147">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="085e8-148">Per modificare o bloccare l'ID chiamante, vedere [impostare l'ID chiamante per un utente](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="085e8-148">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||




