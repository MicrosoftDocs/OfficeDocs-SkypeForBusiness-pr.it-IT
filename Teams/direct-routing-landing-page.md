---
title: Instradamento diretto di Sistema telefonico
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Leggi altre informazioni sul routing diretto e leggi le decisioni di distribuzione necessarie che dovrai affrontare.
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c988670a17a9ba2f803c11740d97404de52d4d5
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48497303"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="0b547-103">Instradamento diretto di Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="0b547-103">Phone System Direct Routing</span></span>

<span data-ttu-id="0b547-104">L'[Introduzione](get-started-with-teams-quick-start.md) è stata completata.</span><span class="sxs-lookup"><span data-stu-id="0b547-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="0b547-105">Si è implementato Teams nell'organizzazione, con [chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="0b547-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="0b547-106">Forse hai distribuito [riunioni & conferenze](deploy-meetings-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="0b547-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="0b547-107">Ora si è pronti per aggiungere carichi di lavoro cloud Voice e si è deciso di usare il proprio gestore di telefonia per la connettività PSTN (Public Switched Telephone Network) usando il routing diretto del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="0b547-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="0b547-108">Con Instradamento diretto, è possibile usare Sistema telefonico praticamente con qualsiasi gestore telefonico.</span><span class="sxs-lookup"><span data-stu-id="0b547-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="0b547-109">Questo articolo descrive le decisioni di distribuzione di base per il routing diretto, oltre a considerazioni aggiuntive che potrebbero essere utili, in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="0b547-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="0b547-110">Per altre informazioni sulle offerte vocali di Microsoft Cloud, dovresti anche leggere [cloud Voice in Microsoft teams](cloud-voice-landing-page.md) .</span><span class="sxs-lookup"><span data-stu-id="0b547-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="0b547-111">Leggi altre informazioni sul routing diretto</span><span class="sxs-lookup"><span data-stu-id="0b547-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="0b547-112">Gli articoli seguenti includono altre informazioni su come configurare e usare il routing diretto del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="0b547-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="0b547-113">La configurazione del routing diretto richiede la comprensione della progettazione di routing PSTN.</span><span class="sxs-lookup"><span data-stu-id="0b547-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="0b547-114">Per informazioni su come pianificare e configurare il routing diretto, leggere tutti questi articoli:</span><span class="sxs-lookup"><span data-stu-id="0b547-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="0b547-115">Pianificare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="0b547-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="0b547-116">Configurare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="0b547-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="0b547-117">Elenco di Session Border Controller certificati per Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="0b547-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="0b547-118">Monitorare e risolvere i problemi di Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="0b547-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="0b547-119">È inoltre possibile leggere gli articoli seguenti a seconda dei requisiti desiderati:</span><span class="sxs-lookup"><span data-stu-id="0b547-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="0b547-120">Configurare un Session Border Controller per più tenant</span><span class="sxs-lookup"><span data-stu-id="0b547-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="0b547-121">Eseguire la migrazione a Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="0b547-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="0b547-122">Account utente in un ambiente ibrido con connettività PSTN</span><span class="sxs-lookup"><span data-stu-id="0b547-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="0b547-123">Vedere la sessione seguente per altre informazioni sul routing diretto: [routing diretto in Microsoft teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="0b547-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="0b547-124">Decisioni chiave per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="0b547-124">Core deployment decisions</span></span>

<span data-ttu-id="0b547-125">Queste sono le decisioni principali da prendere in considerazione per il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="0b547-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="0b547-126">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="0b547-126">Ask yourself</span></span>|<span data-ttu-id="0b547-127">Azione</span><span class="sxs-lookup"><span data-stu-id="0b547-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="0b547-128">Per quali utenti si Abilita il routing diretto?</span><span class="sxs-lookup"><span data-stu-id="0b547-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="0b547-129">Per altre informazioni, vedere [abilitare gli utenti per il servizio di routing diretto](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="0b547-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md).</span></span> |
<span data-ttu-id="0b547-130">Sono disponibili le licenze necessarie per il routing diretto?</span><span class="sxs-lookup"><span data-stu-id="0b547-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="0b547-131">Per altre informazioni, Vedi [licenze e altri requisiti](direct-routing-plan.md#licensing-and-other-requirements).</span><span class="sxs-lookup"><span data-stu-id="0b547-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="0b547-132">Considerazioni su Session Border Controller (SBC)</span><span class="sxs-lookup"><span data-stu-id="0b547-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="0b547-133">Con il routing diretto, devi connettere il tuo session border controller (SBC) direttamente al sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="0b547-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="0b547-134">Per un elenco di SBCs certificati, vedere [controller di bordo della sessione supportati](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="0b547-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="0b547-135">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="0b547-135">Ask yourself</span></span>|<span data-ttu-id="0b547-136">Azione</span><span class="sxs-lookup"><span data-stu-id="0b547-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="0b547-137">Dove e come si distribuisce SBCs?</span><span class="sxs-lookup"><span data-stu-id="0b547-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="0b547-138">Per altre informazioni, vedere [configurare il routing diretto](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="0b547-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="0b547-139">Si hanno più tenant?</span><span class="sxs-lookup"><span data-stu-id="0b547-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="0b547-140">Per altre informazioni, vedere [configurare un controller di bordo della sessione per più tenant](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="0b547-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="0b547-141">Considerazioni sul routing vocale</span><span class="sxs-lookup"><span data-stu-id="0b547-141">Voice routing considerations</span></span>

<span data-ttu-id="0b547-142">È necessario configurare il sistema telefonico per instradare le chiamate allo specifico SBCs.</span><span class="sxs-lookup"><span data-stu-id="0b547-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="0b547-143">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="0b547-143">Ask yourself</span></span>|<span data-ttu-id="0b547-144">Azione</span><span class="sxs-lookup"><span data-stu-id="0b547-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="0b547-145">Quali criteri di routing vocale, utilizzo PSTN e route vocali è necessario creare?</span><span class="sxs-lookup"><span data-stu-id="0b547-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="0b547-146">Per informazioni sul routing vocale, vedere [configurare il routing vocale](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="0b547-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md).</span></span>
| <span data-ttu-id="0b547-147">Quali utenti verranno assegnati ai criteri di routing vocale definiti?</span><span class="sxs-lookup"><span data-stu-id="0b547-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="0b547-148">Vedere gli esempi in [configurare il routing vocale](direct-routing-configure.md).</span><span class="sxs-lookup"><span data-stu-id="0b547-148">See the examples in [Configure Voice Routing](direct-routing-configure.md).</span></span> |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a><span data-ttu-id="0b547-149">Assicurarsi che le chiamate in arrivo atterrino nel client teams usando TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="0b547-149">Ensure incoming calls land in the Teams client using TeamsUpgradePolicy</span></span>

<span data-ttu-id="0b547-150">Il routing diretto è supportato solo con Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="0b547-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="0b547-151">Per ricevere chiamate PSTN tramite routing diretto, è necessario configurare TeamsUpgradePolicy per garantire che le chiamate in arrivo vengano ricevute in teams.</span><span class="sxs-lookup"><span data-stu-id="0b547-151">To receive PSTN calls through Direct Routing, you need to configure TeamsUpgradePolicy to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="0b547-152">Gli utenti devono essere in modalità solo teams, che è possibile eseguire assegnando loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="0b547-152">Users must be in Teams Only mode, which you can do by assigning them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> 

|<span data-ttu-id="0b547-153">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="0b547-153">Ask yourself</span></span>|<span data-ttu-id="0b547-154">Azione</span><span class="sxs-lookup"><span data-stu-id="0b547-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="0b547-155">Cosa significa la modalità solo Teams?</span><span class="sxs-lookup"><span data-stu-id="0b547-155">What does Teams Only mode mean?</span></span> | <span data-ttu-id="0b547-156">Per altre informazioni, Vedi [linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span><span class="sxs-lookup"><span data-stu-id="0b547-156">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="0b547-157">Considerazioni aggiuntive sulla distribuzione</span><span class="sxs-lookup"><span data-stu-id="0b547-157">Additional deployment considerations</span></span>

<span data-ttu-id="0b547-158">Si può prendere in considerazione quanto segue, in base alle esigenze e alla configurazione dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="0b547-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="0b547-159">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="0b547-159">Ask yourself</span></span>| <span data-ttu-id="0b547-160">Azione</span><span class="sxs-lookup"><span data-stu-id="0b547-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="0b547-161">Si dispone di una distribuzione di Skype for Business Server esistente con connettività ibrida configurata?</span><span class="sxs-lookup"><span data-stu-id="0b547-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="0b547-162">Per informazioni su come eseguire il provisioning e la gestione degli account utente in un ambiente ibrido, vedere [account utente in un ambiente ibrido con connettività PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md).</span><span class="sxs-lookup"><span data-stu-id="0b547-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="0b547-163">Si esegue la migrazione a routing diretto dal piano chiamante o da un ambiente locale di Skype for business?</span><span class="sxs-lookup"><span data-stu-id="0b547-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="0b547-164">Per altre informazioni sulla migrazione a routing diretto da un ambiente esistente, vedere [migrazione al routing diretto](direct-routing-migrating.md).</span><span class="sxs-lookup"><span data-stu-id="0b547-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
