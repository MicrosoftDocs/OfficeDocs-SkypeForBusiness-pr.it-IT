---
title: Cloud Voice in Microsoft Teams
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
- M365-voice
ms.reviewer: crowe
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.cloudvoice
- seo-marvel-apr2020
search.appverid: MET150
description: Leggi altre informazioni sulla funzionalità cloud Voice e leggi le decisioni di distribuzione necessarie che dovrai affrontare.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 8106e5ef30b71ec82e9b1ae42f785b7a73b170a5
ms.sourcegitcommit: f7f86744c6dbf0db87e1408fd1f4b770fda07ff9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/17/2020
ms.locfileid: "45158644"
---
# <a name="voice---phone-system-and-pstn-connectivity-options"></a><span data-ttu-id="9d742-103">Opzioni di connettività PSTN e di sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="9d742-103">Voice - Phone System and PSTN connectivity options</span></span>

<span data-ttu-id="9d742-104">L'[Introduzione](get-started-with-teams-quick-start.md) è stata completata.</span><span class="sxs-lookup"><span data-stu-id="9d742-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="9d742-105">Si è implementato Teams nell'organizzazione, con [chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="9d742-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="9d742-106">Forse hai distribuito [riunioni & conferenze](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="9d742-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="9d742-107">Ora si è pronti per aggiungere funzionalità vocali per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="9d742-107">Now you're ready to add voice capabilities for your users.</span></span> 

<span data-ttu-id="9d742-108">Voice offre funzionalità PBX (Private Branch Exchange) e opzioni per la connessione alla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="9d742-108">Voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="9d742-109">Questo articolo consente di decidere se è necessario modificare le impostazioni vocali predefinite, in base al profilo dell'organizzazione e ai requisiti aziendali, quindi illustra ogni modifica.</span><span class="sxs-lookup"><span data-stu-id="9d742-109">This article helps you decide whether you need to change any of the default voice settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="9d742-110">Le impostazioni sono suddivise in due gruppi, a partire dal set di [modifiche che è più probabile apportare](#core-deployment-decisions).</span><span class="sxs-lookup"><span data-stu-id="9d742-110">We've split the settings into two groups, starting with the core set of [changes you are more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="9d742-111">Il secondo gruppo include le [impostazioni aggiuntive](#additional-deployment-decisions) che può essere utile configurare in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9d742-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="9d742-112">È consigliabile che tutte le organizzazioni funzionino tramite le decisioni principali e quindi, se l'organizzazione ha requisiti aggiuntivi, esaminare il materiale seguente.</span><span class="sxs-lookup"><span data-stu-id="9d742-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>



## <a name="learn-more-about-voice"></a><span data-ttu-id="9d742-113">Leggi altre informazioni su Voice</span><span class="sxs-lookup"><span data-stu-id="9d742-113">Learn more about voice</span></span>

<span data-ttu-id="9d742-114">Gli articoli seguenti includono ulteriori informazioni sulla distribuzione e l'uso delle funzionalità vocali in teams:</span><span class="sxs-lookup"><span data-stu-id="9d742-114">The following articles provide more information about deploying and using voice features in Teams:</span></span>

- [<span data-ttu-id="9d742-115">Sistema telefonico in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="9d742-115">Phone System in Microsoft 365 or Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="9d742-116">Sistema telefonico con piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="9d742-116">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="9d742-117">Instradamento diretto di Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="9d742-117">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="9d742-118">Soluzioni di telefonia Microsoft</span><span class="sxs-lookup"><span data-stu-id="9d742-118">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="9d742-119">Per altre informazioni sul sistema telefonico, vedere la sessione seguente: [Introduzione al sistema telefonico in Microsoft teams](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="9d742-119">Watch the following session to learn more about Phone System: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="9d742-120">Decisioni chiave per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="9d742-120">Core deployment decisions</span></span>

<span data-ttu-id="9d742-121">Di seguito sono illustrate le impostazioni che la maggior parte delle organizzazioni vorrà modificare se le impostazioni predefinite di Teams non sono adeguate.</span><span class="sxs-lookup"><span data-stu-id="9d742-121">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="9d742-122">Sistema telefonico (Office 365)</span><span class="sxs-lookup"><span data-stu-id="9d742-122">Phone System (Office 365)</span></span>

<span data-ttu-id="9d742-123">Sistema telefonico è la tecnologia Microsoft per l'abilitazione del controllo delle chiamate e delle funzionalità Private Branch Exchange (PBX) in Microsoft 365 o Office 365 cloud.</span><span class="sxs-lookup"><span data-stu-id="9d742-123">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Microsoft 365 or Office 365 cloud.</span></span> <span data-ttu-id="9d742-124">Il sistema telefonico consente di sostituire il sistema PBX (Private Branch Exchange) esistente con un set di funzionalità fornite direttamente da Microsoft 365 o Office 365 e strettamente integrate nell'esperienza di produttività del cloud aziendale.</span><span class="sxs-lookup"><span data-stu-id="9d742-124">Phone System allows you to replace your existing Private Branch Exchange (PBX) system with a set of features directly delivered from Microsoft 365 or Office 365 and tightly integrated into the company's cloud productivity experience.</span></span>


|<span data-ttu-id="9d742-125">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="9d742-125">Ask yourself</span></span>|<span data-ttu-id="9d742-126">Azione</span><span class="sxs-lookup"><span data-stu-id="9d742-126">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="9d742-127">In quali sedi utente o uffici verrà implementato il sistema telefonico?</span><span class="sxs-lookup"><span data-stu-id="9d742-127">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="9d742-128">Per altre informazioni sul sistema telefonico, vedere [cos'è il sistema telefonico in Microsoft 365 o Office 365](what-is-phone-system-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="9d742-128">For more information about Phone System, see [What is Phone System in Microsoft 365 or Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="9d742-129">Connessione alla rete PSTN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="9d742-129">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="9d742-130">Per connettere il sistema telefonico alla rete PSTN (Public Switched Telephone Network) in modo che gli utenti possano effettuare telefonate in tutto il mondo, sono disponibili opzioni in base alle esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="9d742-130">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="9d742-131">Porsi le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="9d742-131">Ask yourself the following:</span></span>


|<span data-ttu-id="9d742-132">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="9d742-132">Ask yourself</span></span>|<span data-ttu-id="9d742-133">Azione</span><span class="sxs-lookup"><span data-stu-id="9d742-133">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="9d742-134">Si vuole usare Microsoft Calling Plan come gestore di telefonia?</span><span class="sxs-lookup"><span data-stu-id="9d742-134">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="9d742-135">Per altre informazioni, Vedi [sistema telefonico con piani di chiamata](calling-plan-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="9d742-135">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="9d742-136">È necessario usare il proprio gestore di telefonia?</span><span class="sxs-lookup"><span data-stu-id="9d742-136">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="9d742-137">Per altre informazioni, Vedi [sistema telefonico con routing diretto](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="9d742-137">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="9d742-138">Ulteriori decisioni per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="9d742-138">Additional deployment decisions</span></span>

<span data-ttu-id="9d742-139">Potrebbe essere necessario modificare le impostazioni per le seguenti, in base alle esigenze e alla configurazione dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="9d742-139">You may want to change settings for the following, based on your organization's needs and configuration:</span></span>

- <span data-ttu-id="9d742-140">Segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="9d742-140">Voicemail</span></span>
- <span data-ttu-id="9d742-141">Chiamata dell'identità</span><span class="sxs-lookup"><span data-stu-id="9d742-141">Calling identity</span></span>
- <span data-ttu-id="9d742-142">Numeri di telefono da Microsoft</span><span class="sxs-lookup"><span data-stu-id="9d742-142">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="9d742-143">Dial plan</span><span class="sxs-lookup"><span data-stu-id="9d742-143">Dial plans</span></span>
- <span data-ttu-id="9d742-144">Code di chiamata</span><span class="sxs-lookup"><span data-stu-id="9d742-144">Call queues</span></span>
- <span data-ttu-id="9d742-145">Operatori automatici</span><span class="sxs-lookup"><span data-stu-id="9d742-145">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="9d742-146">Segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="9d742-146">Voicemail</span></span>

<span data-ttu-id="9d742-147">Cloud voicemail, alimentato da servizi di Azure voicemail, supporta i depositi della segreteria telefonica solo alle cassette postali di Exchange e non supporta sistemi di posta elettronica di terze parti.</span><span class="sxs-lookup"><span data-stu-id="9d742-147">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn't support third-party email systems.</span></span> <span data-ttu-id="9d742-148">Cloud Voicemail include la trascrizione della segreteria telefonica, che è abilitata per tutti gli utenti dell'organizzazione per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="9d742-148">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="9d742-149">Le esigenze aziendali potrebbero richiedere la disattivazione della trascrizione della segreteria telefonica per utenti specifici o tutti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9d742-149">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="9d742-150">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="9d742-150">Ask yourself</span></span>|<span data-ttu-id="9d742-151">Azione</span><span class="sxs-lookup"><span data-stu-id="9d742-151">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="9d742-152">Si vuole abilitare la segreteria telefonica cloud?</span><span class="sxs-lookup"><span data-stu-id="9d742-152">Do I want to enable Cloud Voicemail?</span></span> | <span data-ttu-id="9d742-153">Per le procedure di configurazione della segreteria telefonica, vedere [configurare la segreteria telefonica cloud](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="9d742-153">For voicemail setup procedures, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="9d742-154">Si vuole abilitare la trascrizione della segreteria telefonica per alcuni o tutti gli utenti?</span><span class="sxs-lookup"><span data-stu-id="9d742-154">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="9d742-155">Per disattivare la trascrizione della segreteria telefonica, vedere [impostazione di criteri per la segreteria telefonica nell'organizzazione](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="9d742-155">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="9d742-156">Chiamata dell'identità</span><span class="sxs-lookup"><span data-stu-id="9d742-156">Calling identity</span></span>

<span data-ttu-id="9d742-157">Per impostazione predefinita, tutte le chiamate in uscita usano il numero di telefono assegnato come identità di chiamata (ID chiamante).</span><span class="sxs-lookup"><span data-stu-id="9d742-157">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="9d742-158">Il destinatario della chiamata può identificare rapidamente il chiamante e decidere se accettare o rifiutare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="9d742-158">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="9d742-159">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="9d742-159">Ask yourself</span></span>|<span data-ttu-id="9d742-160">Azione</span><span class="sxs-lookup"><span data-stu-id="9d742-160">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="9d742-161">Si vuole mascherare o disabilitare l'ID chiamante?</span><span class="sxs-lookup"><span data-stu-id="9d742-161">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="9d742-162">Per modificare o bloccare l'ID chiamante, vedere [impostare l'ID chiamante per un utente](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="9d742-162">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="9d742-163">Numeri di telefono da Microsoft</span><span class="sxs-lookup"><span data-stu-id="9d742-163">Phone numbers from Microsoft</span></span>

<span data-ttu-id="9d742-164">Microsoft ha due tipi di numeri di telefono disponibili: i numeri di *abbonato* (utente), che possono essere assegnati agli utenti dell'organizzazione e i numeri di *servizio* , disponibili come numeri di servizio a pedaggio e a numero verde, che hanno una maggiore capacità di chiamata simultanea rispetto ai numeri di abbonati e che possono essere assegnati a servizi come audioconferenza, operatori automatici o code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="9d742-164">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="9d742-165">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="9d742-165">Ask yourself</span></span>|<span data-ttu-id="9d742-166">Azione</span><span class="sxs-lookup"><span data-stu-id="9d742-166">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="9d742-167">Quali posizioni utente richiedono nuovi numeri di telefono da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="9d742-167">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="9d742-168">Per informazioni su come ottenere i numeri di telefono, vedere [gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) e [ottenere i numeri di telefono per gli utenti](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="9d742-168">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span> 
| <span data-ttu-id="9d742-169">Quale tipo di numero di telefono (abbonato o servizio) è necessario?</span><span class="sxs-lookup"><span data-stu-id="9d742-169">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="9d742-170">Per selezionare il tipo di numero di telefono necessario, vedere i [diversi tipi di numeri di telefono usati per chiamare i piani](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="9d742-170">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="9d742-171">Come si trasferiscono I numeri di telefono esistenti in teams?</span><span class="sxs-lookup"><span data-stu-id="9d742-171">How do I port existing phone numbers to Teams?</span></span>|<span data-ttu-id="9d742-172">Per altre informazioni, vedere [trasferire i numeri di telefono in Microsoft teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="9d742-172">For more information, see [Transfer phone numbers to Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="9d742-173">Dial plan</span><span class="sxs-lookup"><span data-stu-id="9d742-173">Dial plans</span></span>

<span data-ttu-id="9d742-174">Un dial plan nella caratteristica sistema telefonico di Microsoft 365 o Office 365 è un set di regole di normalizzazione che traducono i numeri di telefono composti in un formato alternativo (in genere E. 164) per l'autorizzazione alle chiamate e il routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="9d742-174">A dial plan in the Phone System feature of Microsoft 365 or Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="9d742-175">Per altre informazioni sui dial plan, vedere [Che cosa sono i dial plan?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="9d742-175">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="9d742-176">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="9d742-176">Ask yourself</span></span>|<span data-ttu-id="9d742-177">Azione</span><span class="sxs-lookup"><span data-stu-id="9d742-177">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="9d742-178">L'organizzazione ha bisogno di un dial plan personalizzato?</span><span class="sxs-lookup"><span data-stu-id="9d742-178">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="9d742-179">Per determinare se è necessario un piano di chiamata personalizzato, vedere [pianificazione per i piani di chiamata del tenant](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="9d742-179">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span></span>|
<span data-ttu-id="9d742-180">Quali utenti devono avere un dial plan personalizzato e quale dial plan del tenant occorre assegnare a ogni utente?</span><span class="sxs-lookup"><span data-stu-id="9d742-180">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="9d742-181">Per aggiungere utenti a un dial plan personalizzato in PowerShell, vedere [creare e gestire piani di chiamata](create-and-manage-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="9d742-181">To add users to a customized dial plan in PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="9d742-182">Code di chiamata</span><span class="sxs-lookup"><span data-stu-id="9d742-182">Call queues</span></span>

<span data-ttu-id="9d742-183">Le code delle chiamate Cloud includono i messaggi di saluto usati quando qualcuno chiama un numero di telefono per l'organizzazione, la possibilità di inserire automaticamente le chiamate in attesa e la possibilità di cercare l'agente di chiamata disponibile per gestire la chiamata mentre le persone che chiamano ascoltano musica in attesa.</span><span class="sxs-lookup"><span data-stu-id="9d742-183">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="9d742-184">È possibile creare code di chiamata singole o multiple per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9d742-184">You can create single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="9d742-185">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="9d742-185">Ask yourself</span></span>|<span data-ttu-id="9d742-186">Azione</span><span class="sxs-lookup"><span data-stu-id="9d742-186">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="9d742-187">L'organizzazione ha bisogno delle code di chiamata?</span><span class="sxs-lookup"><span data-stu-id="9d742-187">Does my organization need call queues?</span></span> | <span data-ttu-id="9d742-188">Per altre informazioni, vedere [creare una coda di chiamata cloud](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) e [configurare il sistema telefonico](setting-up-your-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="9d742-188">For more information, see [Create a Cloud call queue](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="9d742-189">Operatori automatici</span><span class="sxs-lookup"><span data-stu-id="9d742-189">Auto attendants</span></span>

<span data-ttu-id="9d742-190">Gli operatori automatici cloud possono essere usati per creare un sistema di menu per l'organizzazione che consente ai chiamanti esterni e interni di spostarsi in un sistema di menu per individuare e trasferire le chiamate agli utenti o ai reparti aziendali dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="9d742-190">Cloud auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="9d742-191">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="9d742-191">Ask yourself</span></span>|<span data-ttu-id="9d742-192">Azione</span><span class="sxs-lookup"><span data-stu-id="9d742-192">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="9d742-193">L'organizzazione ha bisogno di operatori automatici?</span><span class="sxs-lookup"><span data-stu-id="9d742-193">Does my organization need auto attendants?</span></span> | <span data-ttu-id="9d742-194">Per altre informazioni, vedere [cosa sono gli operatori automatici di cloud](what-are-phone-system-auto-attendants.md) e [configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="9d742-194">For more information, see [What are Cloud auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> |

### <a name="devices"></a><span data-ttu-id="9d742-195">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="9d742-195">Devices</span></span>

<span data-ttu-id="9d742-196">Per altre informazioni sui dispositivi supportati, vedere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="9d742-196">For more information about supported devices, see the following:</span></span>

- [<span data-ttu-id="9d742-197">Gestire i dispositivi in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9d742-197">Manage your devices in Microsoft Teams</span></span>](devices/device-management.md)
- [<span data-ttu-id="9d742-198">Telefoni IP</span><span class="sxs-lookup"><span data-stu-id="9d742-198">IP Phones</span></span>](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="9d742-199">Dispositivi video e audio USB</span><span class="sxs-lookup"><span data-stu-id="9d742-199">USB audio and video devices</span></span>](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="9d742-200">Comunicazioni intelligenti per i dispositivi</span><span class="sxs-lookup"><span data-stu-id="9d742-200">Intelligent communications for devices</span></span>](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


