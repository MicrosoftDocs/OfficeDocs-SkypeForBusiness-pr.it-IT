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
ms.openlocfilehash: 952eb7064844cf0e77e829cd2506c4303504074c
ms.sourcegitcommit: 3ed779277540589eabef745685ab6c67d8a8ff90
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/19/2020
ms.locfileid: "44281671"
---
# <a name="cloud-voice-in-microsoft-teams"></a><span data-ttu-id="22803-103">Cloud Voice in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="22803-103">Cloud voice in Microsoft Teams</span></span>

<span data-ttu-id="22803-104">L'[Introduzione](get-started-with-teams-quick-start.md) è stata completata.</span><span class="sxs-lookup"><span data-stu-id="22803-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="22803-105">Si è implementato Teams nell'organizzazione, con [chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="22803-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="22803-106">Forse hai distribuito [riunioni & conferenze](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="22803-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="22803-107">Ora si è pronti ad aggiungere funzionalità di cloud Voice per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="22803-107">Now you're ready to add cloud voice capabilities for your users.</span></span> 

<span data-ttu-id="22803-108">Cloud Voice offre funzionalità PBX (Private Branch Exchange) e opzioni per la connessione alla rete PSTN (Public Switched Telephone Network).</span><span class="sxs-lookup"><span data-stu-id="22803-108">Cloud voice provides Private Branch Exchange (PBX) capabilities, and options for connecting to the Public Switched Telephone Network (PSTN).</span></span>

<span data-ttu-id="22803-109">Questo articolo consente di decidere se è necessario modificare le impostazioni vocali predefinite del cloud, in base al profilo dell'organizzazione e ai requisiti aziendali, quindi illustra ogni modifica.</span><span class="sxs-lookup"><span data-stu-id="22803-109">This article helps you decide whether you need to change any of the default cloud voice settings, based on your organization's profile and business requirements, then it walks you through each change.</span></span> <span data-ttu-id="22803-110">Le impostazioni sono suddivise in due gruppi, a partire dal set di [modifiche che è più probabile apportare](#core-deployment-decisions).</span><span class="sxs-lookup"><span data-stu-id="22803-110">We've split the settings into two groups, starting with the core set of [changes you are more likely to make](#core-deployment-decisions).</span></span> <span data-ttu-id="22803-111">Il secondo gruppo include le [impostazioni aggiuntive](#additional-deployment-decisions) che può essere utile configurare in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="22803-111">The second group includes the [additional settings](#additional-deployment-decisions) you may want to configure, based on your organization's needs.</span></span>

<span data-ttu-id="22803-112">È consigliabile che tutte le organizzazioni funzionino tramite le decisioni principali e quindi, se l'organizzazione ha requisiti aggiuntivi, esaminare il materiale seguente.</span><span class="sxs-lookup"><span data-stu-id="22803-112">We recommend that all organizations work through the core decisions and then, if your organization has additional requirements, review the following material.</span></span>



## <a name="learn-more-about-cloud-voice"></a><span data-ttu-id="22803-113">Leggi altre informazioni su cloud Voice</span><span class="sxs-lookup"><span data-stu-id="22803-113">Learn more about cloud voice</span></span>

<span data-ttu-id="22803-114">Gli articoli seguenti includono ulteriori informazioni sulla distribuzione e l'uso delle funzionalità vocali cloud in teams:</span><span class="sxs-lookup"><span data-stu-id="22803-114">The following articles provide more information about deploying and using cloud voice features in Teams:</span></span>

- [<span data-ttu-id="22803-115">Sistema telefonico di Office 365</span><span class="sxs-lookup"><span data-stu-id="22803-115">Phone System in Office 365</span></span>](what-is-phone-system-in-office-365.md)
- [<span data-ttu-id="22803-116">Sistema telefonico con piani di chiamata</span><span class="sxs-lookup"><span data-stu-id="22803-116">Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)
- [<span data-ttu-id="22803-117">Instradamento diretto di Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="22803-117">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)
- [<span data-ttu-id="22803-118">Distribuzione di cloud Voice</span><span class="sxs-lookup"><span data-stu-id="22803-118">Cloud voice deployment</span></span>](cloud-voice-deployment.md)
- [<span data-ttu-id="22803-119">Soluzioni di telefonia Microsoft</span><span class="sxs-lookup"><span data-stu-id="22803-119">Microsoft telephony solutions</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/msft-telephony-solutions)
- <span data-ttu-id="22803-120">Per altre informazioni sul sistema telefonico, vedere la sessione seguente: [Introduzione al sistema telefonico in Microsoft teams](https://aka.ms/teams-phone-system)</span><span class="sxs-lookup"><span data-stu-id="22803-120">Watch the following session to learn more about Phone System: [Introduction to Phone System in Microsoft Teams](https://aka.ms/teams-phone-system)</span></span>


## <a name="core-deployment-decisions"></a><span data-ttu-id="22803-121">Decisioni chiave per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="22803-121">Core deployment decisions</span></span>

<span data-ttu-id="22803-122">Di seguito sono illustrate le impostazioni che la maggior parte delle organizzazioni vorrà modificare se le impostazioni predefinite di Teams non sono adeguate.</span><span class="sxs-lookup"><span data-stu-id="22803-122">These are the settings that most organizations want to change (if the Teams default settings don't work for the organization).</span></span>

## <a name="phone-system-office-365"></a><span data-ttu-id="22803-123">Sistema telefonico (Office 365)</span><span class="sxs-lookup"><span data-stu-id="22803-123">Phone System (Office 365)</span></span>

<span data-ttu-id="22803-124">Sistema telefonico è la tecnologia Microsoft per abilitare il controllo delle chiamate e le funzionalità del PBX (Private Branch Exchange) nel cloud di Office 365.</span><span class="sxs-lookup"><span data-stu-id="22803-124">Phone System is Microsoft's technology for enabling call control and Private Branch Exchange (PBX) capabilities in the Office 365 cloud.</span></span> <span data-ttu-id="22803-125">Sistema telefonico consente di sostituire il sistema PBX (Private Branch Exchange) esistente con un set di caratteristiche direttamente recapitate da Office 365 e strettamente integrate nell'esperienza di produttività del cloud aziendale.</span><span class="sxs-lookup"><span data-stu-id="22803-125">Phone System allows you to replace your existing Private Branch Exchange (PBX) system with a set of features directly delivered from Office 365 and tightly integrated into the company's cloud productivity experience.</span></span>


|<span data-ttu-id="22803-126">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="22803-126">Ask yourself</span></span>|<span data-ttu-id="22803-127">Azione</span><span class="sxs-lookup"><span data-stu-id="22803-127">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="22803-128">In quali sedi utente o uffici verrà implementato il sistema telefonico?</span><span class="sxs-lookup"><span data-stu-id="22803-128">In which user locations or offices will I implement Phone System?</span></span> |<span data-ttu-id="22803-129">Per altre informazioni sul sistema telefonico, vedere [cos'è il sistema telefonico in Office 365](what-is-phone-system-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="22803-129">For more information about Phone System, see [What is Phone System in Office 365](what-is-phone-system-in-office-365.md).</span></span></li></ul>|
|||

## <a name="connection-to-the-public-switched-telephone-network-pstn"></a><span data-ttu-id="22803-130">Connessione alla rete PSTN (Public Switched Telephone Network)</span><span class="sxs-lookup"><span data-stu-id="22803-130">Connection to the Public Switched Telephone Network (PSTN)</span></span>

<span data-ttu-id="22803-131">Per connettere il sistema telefonico alla rete PSTN (Public Switched Telephone Network) in modo che gli utenti possano effettuare telefonate in tutto il mondo, sono disponibili opzioni in base alle esigenze aziendali.</span><span class="sxs-lookup"><span data-stu-id="22803-131">To connect Phone System to the Public Switched Telephone Network (PSTN) so that users can make phone calls around the world, you have options based on your business need.</span></span>  <span data-ttu-id="22803-132">Porsi le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="22803-132">Ask yourself the following:</span></span>


|<span data-ttu-id="22803-133">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="22803-133">Ask yourself</span></span>|<span data-ttu-id="22803-134">Azione</span><span class="sxs-lookup"><span data-stu-id="22803-134">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="22803-135">Si vuole usare Microsoft Calling Plan come gestore di telefonia?</span><span class="sxs-lookup"><span data-stu-id="22803-135">Do I want to use Microsoft Calling Plan as my telephony carrier?</span></span> | <span data-ttu-id="22803-136">Per altre informazioni, Vedi [sistema telefonico con piani di chiamata](calling-plan-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="22803-136">For more information, see [Phone System with Calling Plans](calling-plan-landing-page.md).</span></span>|
| <span data-ttu-id="22803-137">È necessario usare il proprio gestore di telefonia?</span><span class="sxs-lookup"><span data-stu-id="22803-137">Do I need to use my own telephony carrier?</span></span> | <span data-ttu-id="22803-138">Per altre informazioni, Vedi [sistema telefonico con routing diretto](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="22803-138">For more information, see [Phone System with Direct Routing](direct-routing-landing-page.md).</span></span>
|||


## <a name="additional-deployment-decisions"></a><span data-ttu-id="22803-139">Ulteriori decisioni per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="22803-139">Additional deployment decisions</span></span>

<span data-ttu-id="22803-140">Potrebbe essere necessario modificare le impostazioni per le seguenti, in base alle esigenze e alla configurazione dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="22803-140">You may want to change settings for the following, based on your organization's needs and configuration:</span></span>

- <span data-ttu-id="22803-141">Segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="22803-141">Voicemail</span></span>
- <span data-ttu-id="22803-142">Chiamata dell'identità</span><span class="sxs-lookup"><span data-stu-id="22803-142">Calling identity</span></span>
- <span data-ttu-id="22803-143">Numeri di telefono da Microsoft</span><span class="sxs-lookup"><span data-stu-id="22803-143">Phone numbers from Microsoft</span></span>
- <span data-ttu-id="22803-144">Dial plan</span><span class="sxs-lookup"><span data-stu-id="22803-144">Dial plans</span></span>
- <span data-ttu-id="22803-145">Code di chiamata</span><span class="sxs-lookup"><span data-stu-id="22803-145">Call queues</span></span>
- <span data-ttu-id="22803-146">Operatori automatici</span><span class="sxs-lookup"><span data-stu-id="22803-146">Auto attendants</span></span>

### <a name="voicemail"></a><span data-ttu-id="22803-147">Segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="22803-147">Voicemail</span></span>

<span data-ttu-id="22803-148">Cloud voicemail, alimentato da servizi di Azure voicemail, supporta i depositi della segreteria telefonica solo alle cassette postali di Exchange e non supporta sistemi di posta elettronica di terze parti.</span><span class="sxs-lookup"><span data-stu-id="22803-148">Cloud Voicemail, powered by Azure Voicemail services, supports voicemail deposits to Exchange mailboxes only and doesn't support third-party email systems.</span></span> <span data-ttu-id="22803-149">Cloud Voicemail include la trascrizione della segreteria telefonica, che è abilitata per tutti gli utenti dell'organizzazione per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="22803-149">Cloud Voicemail includes voicemail transcription, which is enabled for all users in your organization by default.</span></span> <span data-ttu-id="22803-150">Le esigenze aziendali potrebbero richiedere la disattivazione della trascrizione della segreteria telefonica per utenti specifici o tutti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="22803-150">Your business needs might require that you disable voicemail transcription for specific users or everyone throughout the organization.</span></span>

|<span data-ttu-id="22803-151">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="22803-151">Ask yourself</span></span>|<span data-ttu-id="22803-152">Azione</span><span class="sxs-lookup"><span data-stu-id="22803-152">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="22803-153">Si vuole abilitare la segreteria telefonica cloud?</span><span class="sxs-lookup"><span data-stu-id="22803-153">Do I want to enable Cloud Voicemail?</span></span> | <span data-ttu-id="22803-154">Per le procedure di configurazione della segreteria telefonica, vedere [configurare la segreteria telefonica cloud](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="22803-154">For voicemail setup procedures, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>
| <span data-ttu-id="22803-155">Si vuole abilitare la trascrizione della segreteria telefonica per alcuni o tutti gli utenti?</span><span class="sxs-lookup"><span data-stu-id="22803-155">Do I want to enable voicemail transcription for some or all of my users?</span></span> | <span data-ttu-id="22803-156">Per disattivare la trascrizione della segreteria telefonica, vedere [impostazione di criteri per la segreteria telefonica nell'organizzazione](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="22803-156">To turn off voicemail transcription, see [Setting voicemail policies in your organization](set-up-phone-system-voicemail.md#setting-voicemail-policies-in-your-organization).</span></span></li></ul>|
|||

### <a name="calling-identity"></a><span data-ttu-id="22803-157">Chiamata dell'identità</span><span class="sxs-lookup"><span data-stu-id="22803-157">Calling identity</span></span>

<span data-ttu-id="22803-158">Per impostazione predefinita, tutte le chiamate in uscita usano il numero di telefono assegnato come identità di chiamata (ID chiamante).</span><span class="sxs-lookup"><span data-stu-id="22803-158">By default, all outbound calls use the assigned phone number as calling identity (caller ID).</span></span> <span data-ttu-id="22803-159">Il destinatario della chiamata può identificare rapidamente il chiamante e decidere se accettare o rifiutare la chiamata.</span><span class="sxs-lookup"><span data-stu-id="22803-159">The recipient of the call can quickly identify the caller and decide whether to accept or reject the call.</span></span>

|<span data-ttu-id="22803-160">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="22803-160">Ask yourself</span></span>|<span data-ttu-id="22803-161">Azione</span><span class="sxs-lookup"><span data-stu-id="22803-161">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="22803-162">Si vuole mascherare o disabilitare l'ID chiamante?</span><span class="sxs-lookup"><span data-stu-id="22803-162">Do I want to mask or disable caller ID?</span></span> | <span data-ttu-id="22803-163">Per modificare o bloccare l'ID chiamante, vedere [impostare l'ID chiamante per un utente](set-the-caller-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="22803-163">To change or block the caller ID, see [Set the caller ID for a user](set-the-caller-id-for-a-user.md).</span></span> |
|||

### <a name="phone-numbers-from-microsoft"></a><span data-ttu-id="22803-164">Numeri di telefono da Microsoft</span><span class="sxs-lookup"><span data-stu-id="22803-164">Phone numbers from Microsoft</span></span>

<span data-ttu-id="22803-165">Microsoft ha due tipi di numeri di telefono disponibili: i numeri di *abbonato* (utente), che possono essere assegnati agli utenti dell'organizzazione e i numeri di *servizio* , disponibili come numeri di servizio a pedaggio e a numero verde, che hanno una maggiore capacità di chiamata simultanea rispetto ai numeri di abbonati e che possono essere assegnati a servizi come audioconferenza, operatori automatici o code di chiamata.</span><span class="sxs-lookup"><span data-stu-id="22803-165">Microsoft has two types of telephone numbers available: *subscriber* (user) numbers, which can be assigned to users in your organization, and *service* numbers, available as toll and toll-free service numbers, which have higher concurrent call capacity than subscriber numbers and can be assigned to services such as Audio Conferencing, Auto Attendants, or Call Queues.</span></span>

|<span data-ttu-id="22803-166">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="22803-166">Ask yourself</span></span>|<span data-ttu-id="22803-167">Azione</span><span class="sxs-lookup"><span data-stu-id="22803-167">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="22803-168">Quali posizioni utente richiedono nuovi numeri di telefono da Microsoft?</span><span class="sxs-lookup"><span data-stu-id="22803-168">Which user locations need new phone numbers from Microsoft?</span></span> | <span data-ttu-id="22803-169">Per informazioni su come ottenere i numeri di telefono, vedere [gestire i numeri di telefono per l'organizzazione](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) e [ottenere i numeri di telefono per gli utenti](getting-phone-numbers-for-your-users.md).</span><span class="sxs-lookup"><span data-stu-id="22803-169">For information about getting phone numbers, see [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) and [Getting phone numbers for your users](getting-phone-numbers-for-your-users.md).</span></span> 
| <span data-ttu-id="22803-170">Quale tipo di numero di telefono (abbonato o servizio) è necessario?</span><span class="sxs-lookup"><span data-stu-id="22803-170">Which type of telephone number (subscriber or service) do I need?</span></span> | <span data-ttu-id="22803-171">Per selezionare il tipo di numero di telefono necessario, vedere i [diversi tipi di numeri di telefono usati per chiamare i piani](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span><span class="sxs-lookup"><span data-stu-id="22803-171">To help you pick the type of phone number you need, see [Different kinds of phone numbers used for Calling Plans](different-kinds-of-phone-numbers-used-for-calling-plans.md).</span></span>
<span data-ttu-id="22803-172">Come si trasferiscono I numeri di telefono esistenti in teams?</span><span class="sxs-lookup"><span data-stu-id="22803-172">How do I port existing phone numbers to Teams?</span></span>|<span data-ttu-id="22803-173">Per altre informazioni, vedere [trasferire i numeri di telefono in Microsoft teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="22803-173">For more information, see [Transfer phone numbers to Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>
|||

### <a name="dial-plans"></a><span data-ttu-id="22803-174">Dial plan</span><span class="sxs-lookup"><span data-stu-id="22803-174">Dial plans</span></span>

<span data-ttu-id="22803-175">Un dial plan nella caratteristica sistema telefonico di Office 365 è un set di regole di normalizzazione che traducono i numeri di telefono composti in un formato alternativo (in genere E. 164) per l'autorizzazione alle chiamate e il routing delle chiamate.</span><span class="sxs-lookup"><span data-stu-id="22803-175">A dial plan in the Phone System feature of Office 365 is a set of normalization rules that translate dialed phone numbers into an alternate format (typically E.164 format) for call authorization and call routing.</span></span>

<span data-ttu-id="22803-176">Per altre informazioni sui dial plan, vedere [Che cosa sono i dial plan?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="22803-176">For more information about dial plans, see [What are dial plans?](https://docs.microsoft.com/SkypeForBusiness/what-are-calling-plans-in-office-365/what-are-dial-plans)</span></span>

|<span data-ttu-id="22803-177">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="22803-177">Ask yourself</span></span>|<span data-ttu-id="22803-178">Azione</span><span class="sxs-lookup"><span data-stu-id="22803-178">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="22803-179">L'organizzazione ha bisogno di un dial plan personalizzato?</span><span class="sxs-lookup"><span data-stu-id="22803-179">Does my organization need a customized dial plan?</span></span> | <span data-ttu-id="22803-180">Per determinare se è necessario un piano di chiamata personalizzato, vedere [pianificazione per i piani di chiamata del tenant](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span><span class="sxs-lookup"><span data-stu-id="22803-180">To help determine if you need a custom dial plan, see [Planning for tenant dial plans](what-are-dial-plans.md#planning-for-tenant-dial-plans)</span></span>|
<span data-ttu-id="22803-181">Quali utenti devono avere un dial plan personalizzato e quale dial plan del tenant occorre assegnare a ogni utente?</span><span class="sxs-lookup"><span data-stu-id="22803-181">Which users require a customized dial plan, and which tenant dial plan should be assigned to each user?</span></span> | <span data-ttu-id="22803-182">Per aggiungere utenti a un dial plan personalizzato in PowerShell, vedere [creare e gestire piani di chiamata](create-and-manage-dial-plans.md).</span><span class="sxs-lookup"><span data-stu-id="22803-182">To add users to a customized dial plan in PowerShell, see [Create and manage dial plans](create-and-manage-dial-plans.md).</span></span> |
|||

### <a name="call-queues"></a><span data-ttu-id="22803-183">Code di chiamata</span><span class="sxs-lookup"><span data-stu-id="22803-183">Call queues</span></span>

<span data-ttu-id="22803-184">Le code delle chiamate Cloud includono i messaggi di saluto usati quando qualcuno chiama un numero di telefono per l'organizzazione, la possibilità di inserire automaticamente le chiamate in attesa e la possibilità di cercare l'agente di chiamata disponibile per gestire la chiamata mentre le persone che chiamano ascoltano musica in attesa.</span><span class="sxs-lookup"><span data-stu-id="22803-184">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="22803-185">È possibile creare code di chiamata singole o multiple per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="22803-185">You can create single or multiple call queues for your organization.</span></span> 


|<span data-ttu-id="22803-186">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="22803-186">Ask yourself</span></span>|<span data-ttu-id="22803-187">Azione</span><span class="sxs-lookup"><span data-stu-id="22803-187">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="22803-188">L'organizzazione ha bisogno delle code di chiamata?</span><span class="sxs-lookup"><span data-stu-id="22803-188">Does my organization need call queues?</span></span> | <span data-ttu-id="22803-189">Per altre informazioni, vedere [creare una coda di chiamata cloud](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) e [configurare il sistema telefonico](setting-up-your-phone-system.md).</span><span class="sxs-lookup"><span data-stu-id="22803-189">For more information, see [Create a Cloud call queue](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) and [Setting up your Phone System](setting-up-your-phone-system.md).</span></span> |

### <a name="auto-attendants"></a><span data-ttu-id="22803-190">Operatori automatici</span><span class="sxs-lookup"><span data-stu-id="22803-190">Auto attendants</span></span>

<span data-ttu-id="22803-191">Gli operatori automatici cloud possono essere usati per creare un sistema di menu per l'organizzazione che consente ai chiamanti esterni e interni di spostarsi in un sistema di menu per individuare e trasferire le chiamate agli utenti o ai reparti aziendali dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="22803-191">Cloud auto attendants can be used to create a menu system for your organization that lets external and internal callers move through a menu system to locate and place or transfer calls to company users or departments in your organization.</span></span>

|<span data-ttu-id="22803-192">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="22803-192">Ask yourself</span></span>|<span data-ttu-id="22803-193">Azione</span><span class="sxs-lookup"><span data-stu-id="22803-193">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="22803-194">L'organizzazione ha bisogno di operatori automatici?</span><span class="sxs-lookup"><span data-stu-id="22803-194">Does my organization need auto attendants?</span></span> | <span data-ttu-id="22803-195">Per altre informazioni, vedere [cosa sono gli operatori automatici di cloud](what-are-phone-system-auto-attendants.md) e [configurare un operatore automatico cloud](create-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="22803-195">For more information, see [What are Cloud auto attendants](what-are-phone-system-auto-attendants.md) and [Set up a Cloud auto attendant](create-a-phone-system-auto-attendant.md).</span></span> |

### <a name="devices"></a><span data-ttu-id="22803-196">Dispositivi</span><span class="sxs-lookup"><span data-stu-id="22803-196">Devices</span></span>

<span data-ttu-id="22803-197">Per altre informazioni sui dispositivi supportati, vedere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="22803-197">For more information about supported devices, see the following:</span></span>

- [<span data-ttu-id="22803-198">Gestire i dispositivi in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="22803-198">Manage your devices in Microsoft Teams</span></span>](devices/device-management.md)
- [<span data-ttu-id="22803-199">Telefoni IP</span><span class="sxs-lookup"><span data-stu-id="22803-199">IP Phones</span></span>](https://docs.microsoft.com/skypeforbusiness/certification/devices-ip-phones?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="22803-200">Dispositivi video e audio USB</span><span class="sxs-lookup"><span data-stu-id="22803-200">USB audio and video devices</span></span>](https://docs.microsoft.com/skypeforbusiness/certification/devices-usb-devices?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)
- [<span data-ttu-id="22803-201">Comunicazioni intelligenti per i dispositivi</span><span class="sxs-lookup"><span data-stu-id="22803-201">Intelligent communications for devices</span></span>](https://products.office.com/microsoft-teams/across-devices?ms.url=officecomteamsdevices&rtc=1)


