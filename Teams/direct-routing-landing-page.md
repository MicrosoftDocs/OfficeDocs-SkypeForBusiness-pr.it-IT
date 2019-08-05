---
title: Routing diretto del sistema telefonico
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
F1keywords: ms.teamsadmincenter.directrouting.overview
description: Pagina di destinazione per il routing diretto
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59f7cf4f1249956f3c763d12fcd96bf5c10a9fac
ms.sourcegitcommit: 79ec789a22acf1686c33a5cc8ba3bd50049f94b8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "36181969"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="3ec8d-103">Routing diretto del sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="3ec8d-103">Phone System Direct Routing</span></span>

<span data-ttu-id="3ec8d-104">È stato completato per [iniziare](get-started-with-teams-quick-start.md).</span><span class="sxs-lookup"><span data-stu-id="3ec8d-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="3ec8d-105">Sono stati distribuiti team con [chat, team, canali, & app](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in tutta l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3ec8d-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="3ec8d-106">Forse hai distribuito [riunioni & conferenze](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="3ec8d-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="3ec8d-107">Ora si è pronti per aggiungere carichi di lavoro cloud Voice e si è deciso di usare il proprio gestore di telefonia per la connettività PSTN (Public Switched Telephone Network) usando il routing diretto del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="3ec8d-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="3ec8d-108">Con il routing diretto, puoi usare il sistema telefonico con virtualmente qualsiasi gestore di telefonia.</span><span class="sxs-lookup"><span data-stu-id="3ec8d-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="3ec8d-109">Questo articolo descrive le decisioni di distribuzione di base per il routing diretto, oltre a considerazioni aggiuntive che potrebbero essere utili, in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="3ec8d-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="3ec8d-110">Per altre informazioni sulle offerte vocali di Microsoft Cloud, dovresti anche leggere [cloud Voice in Microsoft teams](cloud-voice-landing-page.md) .</span><span class="sxs-lookup"><span data-stu-id="3ec8d-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="3ec8d-111">Leggi altre informazioni sul routing diretto</span><span class="sxs-lookup"><span data-stu-id="3ec8d-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="3ec8d-112">Gli articoli seguenti includono altre informazioni su come configurare e usare il routing diretto del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="3ec8d-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="3ec8d-113">La configurazione del routing diretto richiede la comprensione della progettazione di routing PSTN.</span><span class="sxs-lookup"><span data-stu-id="3ec8d-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="3ec8d-114">Per informazioni su come pianificare e configurare il routing diretto, leggere tutti questi articoli:</span><span class="sxs-lookup"><span data-stu-id="3ec8d-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="3ec8d-115">Pianificare il routing diretto</span><span class="sxs-lookup"><span data-stu-id="3ec8d-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="3ec8d-116">Configurare il routing diretto</span><span class="sxs-lookup"><span data-stu-id="3ec8d-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="3ec8d-117">Elenco dei controller di bordo della sessione certificati per il routing diretto</span><span class="sxs-lookup"><span data-stu-id="3ec8d-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="3ec8d-118">Monitorare e risolvere i problemi di routing diretto</span><span class="sxs-lookup"><span data-stu-id="3ec8d-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="3ec8d-119">È inoltre possibile leggere gli articoli seguenti a seconda dei requisiti desiderati:</span><span class="sxs-lookup"><span data-stu-id="3ec8d-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="3ec8d-120">Configurare un controller di bordo della sessione per più tenant</span><span class="sxs-lookup"><span data-stu-id="3ec8d-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="3ec8d-121">Eseguire la migrazione a routing diretto</span><span class="sxs-lookup"><span data-stu-id="3ec8d-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="3ec8d-122">Account utente in un ambiente ibrido con connettività PSTN</span><span class="sxs-lookup"><span data-stu-id="3ec8d-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="3ec8d-123">Vedere la sessione seguente per altre informazioni sul routing diretto: [routing diretto in Microsoft teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="3ec8d-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="3ec8d-124">Decisioni di distribuzione principali</span><span class="sxs-lookup"><span data-stu-id="3ec8d-124">Core deployment decisions</span></span>

<span data-ttu-id="3ec8d-125">Queste sono le decisioni principali da prendere in considerazione per il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="3ec8d-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="3ec8d-126">Chiedi a te stesso</span><span class="sxs-lookup"><span data-stu-id="3ec8d-126">Ask yourself</span></span>|<span data-ttu-id="3ec8d-127">Azione</span><span class="sxs-lookup"><span data-stu-id="3ec8d-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="3ec8d-128">Per quali utenti si Abilita il routing diretto?</span><span class="sxs-lookup"><span data-stu-id="3ec8d-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="3ec8d-129">Per altre informazioni, vedere [abilitare gli utenti per il servizio di routing diretto](direct-routing-configure.md#enable-users-for-direct-routing-service).</span><span class="sxs-lookup"><span data-stu-id="3ec8d-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md#enable-users-for-direct-routing-service).</span></span> |
<span data-ttu-id="3ec8d-130">Sono disponibili le licenze necessarie per il routing diretto?</span><span class="sxs-lookup"><span data-stu-id="3ec8d-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="3ec8d-131">Per altre informazioni, Vedi [licenze e altri requisiti](direct-routing-plan.md#licensing-and-other-requirements).</span><span class="sxs-lookup"><span data-stu-id="3ec8d-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="3ec8d-132">Considerazioni su Session Border Controller (SBC)</span><span class="sxs-lookup"><span data-stu-id="3ec8d-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="3ec8d-133">Con il routing diretto, devi connettere il tuo session border controller (SBC) direttamente al sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="3ec8d-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="3ec8d-134">Per un elenco di SBCs certificati, vedere [controller di bordo della sessione supportati](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="3ec8d-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="3ec8d-135">Chiedi a te stesso</span><span class="sxs-lookup"><span data-stu-id="3ec8d-135">Ask yourself</span></span>|<span data-ttu-id="3ec8d-136">Azione</span><span class="sxs-lookup"><span data-stu-id="3ec8d-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="3ec8d-137">Dove e come si distribuisce SBCs?</span><span class="sxs-lookup"><span data-stu-id="3ec8d-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="3ec8d-138">Per altre informazioni, vedere [configurare il routing diretto](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="3ec8d-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="3ec8d-139">Si hanno più tenant?</span><span class="sxs-lookup"><span data-stu-id="3ec8d-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="3ec8d-140">Per altre informazioni, vedere [configurare un controller di bordo della sessione per più tenant](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="3ec8d-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="3ec8d-141">Considerazioni sul routing vocale</span><span class="sxs-lookup"><span data-stu-id="3ec8d-141">Voice routing considerations</span></span>

<span data-ttu-id="3ec8d-142">È necessario configurare il sistema telefonico per instradare le chiamate allo specifico SBCs.</span><span class="sxs-lookup"><span data-stu-id="3ec8d-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="3ec8d-143">Chiedi a te stesso</span><span class="sxs-lookup"><span data-stu-id="3ec8d-143">Ask yourself</span></span>|<span data-ttu-id="3ec8d-144">Azione</span><span class="sxs-lookup"><span data-stu-id="3ec8d-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="3ec8d-145">Quali criteri di routing vocale, utilizzo PSTN e route vocali è necessario creare?</span><span class="sxs-lookup"><span data-stu-id="3ec8d-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="3ec8d-146">Per informazioni sul routing vocale, vedere [configurare il routing vocale](direct-routing-configure.md#configure-voice-routing).</span><span class="sxs-lookup"><span data-stu-id="3ec8d-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span>
| <span data-ttu-id="3ec8d-147">Quali utenti verranno assegnati ai criteri di routing vocale definiti?</span><span class="sxs-lookup"><span data-stu-id="3ec8d-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="3ec8d-148">Vedere gli esempi in [configurare il routing vocale](direct-routing-configure.md#configure-voice-routing).</span><span class="sxs-lookup"><span data-stu-id="3ec8d-148">See the examples in [Configure Voice Routing](direct-routing-configure.md#configure-voice-routing).</span></span> |
|||

### <a name="calling-and-interop-policies"></a><span data-ttu-id="3ec8d-149">Criteri di chiamata e di interoperabilità</span><span class="sxs-lookup"><span data-stu-id="3ec8d-149">Calling and interop policies</span></span>

<span data-ttu-id="3ec8d-150">Il routing diretto è supportato solo con Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="3ec8d-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="3ec8d-151">Per effettuare o ricevere chiamate PSTN tramite routing diretto, è necessario configurare i criteri necessari per garantire che le chiamate in arrivo vengano ricevute in teams.</span><span class="sxs-lookup"><span data-stu-id="3ec8d-151">To place or receive PSTN calls through Direct Routing, you need to configure the necessary policies to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="3ec8d-152">Puoi configurare gli utenti per impostare Team come client preferito per le chiamate configurando l'utente per la modalità solo teams o configurando teams come client chiamante preferito assegnando TeamsCallingPolicy e TeamsInteropPolicy.</span><span class="sxs-lookup"><span data-stu-id="3ec8d-152">You can configure users to set Teams as their preferred client for calls by either configuring the user for Teams Only mode or configuring Teams as the preferred calling client by assigning the TeamsCallingPolicy and the TeamsInteropPolicy.</span></span>

|<span data-ttu-id="3ec8d-153">Chiedi a te stesso</span><span class="sxs-lookup"><span data-stu-id="3ec8d-153">Ask yourself</span></span>|<span data-ttu-id="3ec8d-154">Azione</span><span class="sxs-lookup"><span data-stu-id="3ec8d-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="3ec8d-155">Come si imposta teams come client preferito per le chiamate?</span><span class="sxs-lookup"><span data-stu-id="3ec8d-155">How will I set Teams as the preferred client for calls?</span></span> | <span data-ttu-id="3ec8d-156">Per altre informazioni, vedere [impostare Microsoft teams come client chiamante preferito per gli utenti](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span><span class="sxs-lookup"><span data-stu-id="3ec8d-156">For more information, see [Set Microsoft Teams as the preferred calling client for users](direct-routing-configure.md#set-microsoft-teams-as-the-preferred-calling-client-for-users).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="3ec8d-157">Considerazioni aggiuntive sulla distribuzione</span><span class="sxs-lookup"><span data-stu-id="3ec8d-157">Additional deployment considerations</span></span>

<span data-ttu-id="3ec8d-158">Si può prendere in considerazione quanto segue, in base alle esigenze e alla configurazione dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="3ec8d-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="3ec8d-159">Chiedi a te stesso</span><span class="sxs-lookup"><span data-stu-id="3ec8d-159">Ask yourself</span></span>| <span data-ttu-id="3ec8d-160">Azione</span><span class="sxs-lookup"><span data-stu-id="3ec8d-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="3ec8d-161">Si dispone di una distribuzione di Skype for Business Server esistente con connettività ibrida configurata?</span><span class="sxs-lookup"><span data-stu-id="3ec8d-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="3ec8d-162">Per informazioni su come eseguire il provisioning e la gestione degli account utente in un ambiente ibrido, vedere [account utente in un ambiente ibrido con connettività PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md).</span><span class="sxs-lookup"><span data-stu-id="3ec8d-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="3ec8d-163">Si esegue la migrazione a routing diretto dal piano chiamante o da un ambiente locale di Skype for business?</span><span class="sxs-lookup"><span data-stu-id="3ec8d-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="3ec8d-164">Per altre informazioni sulla migrazione a routing diretto da un ambiente esistente, vedere [migrazione al routing diretto](direct-routing-migrating.md).</span><span class="sxs-lookup"><span data-stu-id="3ec8d-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
