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
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Altre informazioni sul routing diretto, ad esempio la configurazione, le decisioni di distribuzione di base necessarie e considerazioni sul routing vocale.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1c5120f60778879be0978cb80c56daf99e5b5a38
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031822"
---
# <a name="phone-system-direct-routing"></a><span data-ttu-id="bb35f-103">Instradamento diretto di Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="bb35f-103">Phone System Direct Routing</span></span>

<span data-ttu-id="bb35f-104">L'[Introduzione](get-started-with-teams-quick-start.md) è stata completata.</span><span class="sxs-lookup"><span data-stu-id="bb35f-104">You've completed [Get started](get-started-with-teams-quick-start.md).</span></span> <span data-ttu-id="bb35f-105">Si è implementato Teams nell'organizzazione, con [chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="bb35f-105">You've rolled out Teams with [chat, teams, channels, & apps](deploy-chat-teams-channels-microsoft-teams-landing-page.md) across your organization.</span></span> <span data-ttu-id="bb35f-106">Potresti aver distribuito Riunioni [o conferenze &.](deploy-meetings-microsoft-teams-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="bb35f-106">Maybe you've deployed [Meetings & conferencing](deploy-meetings-microsoft-teams-landing-page.md).</span></span> <span data-ttu-id="bb35f-107">Ora sei pronto per aggiungere carichi di lavoro vocali sul cloud e hai deciso di usare il tuo gestore di telefonia per la connettività PSTN (Public Switched Telephone Network) tramite l'instradamento diretto del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="bb35f-107">Now you're ready to add cloud voice workloads, and you've decided to use your own telephony carrier for Public Switched Telephone Network (PSTN) connectivity by using Phone System Direct Routing.</span></span> <span data-ttu-id="bb35f-108">Con Instradamento diretto, è possibile usare Sistema telefonico praticamente con qualsiasi gestore telefonico.</span><span class="sxs-lookup"><span data-stu-id="bb35f-108">With Direct Routing, you can use Phone System with virtually any telephony carrier.</span></span>

<span data-ttu-id="bb35f-109">Questo articolo descrive le decisioni di base per la distribuzione per il routing diretto, oltre a considerazioni aggiuntive da tenere in considerazione, in base alle esigenze dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="bb35f-109">This article describes core deployment decisions for Direct Routing as well as additional considerations you may want to think about, based on your organization's needs.</span></span> <span data-ttu-id="bb35f-110">Per altre informazioni sulle offerte vocali cloud di Microsoft, è consigliabile leggere anche [Cloud Voice in Microsoft Teams.](cloud-voice-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="bb35f-110">You should also read [Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) for more information about Microsoft's cloud voice offerings.</span></span>

## <a name="learn-more-about-direct-routing"></a><span data-ttu-id="bb35f-111">Altre informazioni sull'instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="bb35f-111">Learn more about Direct Routing</span></span>

<span data-ttu-id="bb35f-112">Gli articoli seguenti forniscono altre informazioni sulla configurazione e l'uso dell'instradamento diretto del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="bb35f-112">The following articles provide more information about configuring and using Phone System Direct Routing.</span></span> <span data-ttu-id="bb35f-113">La configurazione del routing diretto richiede una conoscenza della progettazione del routing PSTN.</span><span class="sxs-lookup"><span data-stu-id="bb35f-113">Configuring Direct Routing requires understanding of PSTN routing design.</span></span> <span data-ttu-id="bb35f-114">Leggere tutti questi articoli per informazioni su come pianificare e configurare il routing diretto:</span><span class="sxs-lookup"><span data-stu-id="bb35f-114">You should read all of these articles to understand how to plan and configure Direct Routing:</span></span>

- [<span data-ttu-id="bb35f-115">Pianificare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="bb35f-115">Plan Direct Routing</span></span>](direct-routing-plan.md) 
- [<span data-ttu-id="bb35f-116">Configurare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="bb35f-116">Configure Direct Routing</span></span>](direct-routing-configure.md)
- [<span data-ttu-id="bb35f-117">Elenco di Session Border Controller certificati per Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="bb35f-117">List of Session Border Controllers certified for Direct Routing</span></span>](direct-routing-border-controllers.md)
- [<span data-ttu-id="bb35f-118">Monitorare e risolvere i problemi di Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="bb35f-118">Monitor and troubleshoot Direct Routing</span></span>](direct-routing-monitor-and-troubleshoot.md)

<span data-ttu-id="bb35f-119">Inoltre, a seconda dei requisiti, è consigliabile leggere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="bb35f-119">In addition, you might want to read the following articles depending on your requirements:</span></span>

-  [<span data-ttu-id="bb35f-120">Configurare un Session Border Controller per più tenant</span><span class="sxs-lookup"><span data-stu-id="bb35f-120">Configure a Session Border Controller for multiple tenants</span></span>](direct-routing-sbc-multiple-tenants.md)
-  [<span data-ttu-id="bb35f-121">Eseguire la migrazione a Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="bb35f-121">Migrate to Direct Routing</span></span>](direct-routing-migrating.md)
-  [<span data-ttu-id="bb35f-122">Account utente in un ambiente ibrido con connettività PSTN</span><span class="sxs-lookup"><span data-stu-id="bb35f-122">User accounts in a hybrid environment with PSTN connectivity</span></span>](direct-routing-user-accounts-in-a-hybrid-environment.md)
- <span data-ttu-id="bb35f-123">Guardare la sessione seguente per altre informazioni sul routing diretto: [Routing diretto in Microsoft Teams](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="bb35f-123">Watch the following session to learn more about Direct Routing: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing)</span></span>

## <a name="core-deployment-decisions"></a><span data-ttu-id="bb35f-124">Decisioni chiave per la distribuzione</span><span class="sxs-lookup"><span data-stu-id="bb35f-124">Core deployment decisions</span></span>

<span data-ttu-id="bb35f-125">Queste sono le decisioni di base da prendere in considerazione per il routing diretto.</span><span class="sxs-lookup"><span data-stu-id="bb35f-125">These are the core decisions to consider for Direct Routing.</span></span> 

|<span data-ttu-id="bb35f-126">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="bb35f-126">Ask yourself</span></span>|<span data-ttu-id="bb35f-127">Azione</span><span class="sxs-lookup"><span data-stu-id="bb35f-127">Action</span></span> |
| :------------|:-------|
|<span data-ttu-id="bb35f-128">Per quali utenti abiliterò il routing diretto?</span><span class="sxs-lookup"><span data-stu-id="bb35f-128">For which users will I enable Direct Routing?</span></span> | <span data-ttu-id="bb35f-129">Per altre informazioni, vedere [Abilitare gli utenti per il servizio di instradamento diretto.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="bb35f-129">For more information, see [Enable users for Direct Routing Service](direct-routing-configure.md).</span></span> |
<span data-ttu-id="bb35f-130">Si hanno le licenze necessarie per l'instradamento diretto?</span><span class="sxs-lookup"><span data-stu-id="bb35f-130">Do I have the required licenses for Direct Routing?</span></span> | <span data-ttu-id="bb35f-131">Per altre informazioni, vedere Licenze [e altri requisiti.](direct-routing-plan.md#licensing-and-other-requirements)</span><span class="sxs-lookup"><span data-stu-id="bb35f-131">For more information, see [Licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements).</span></span>
|||

### <a name="session-border-controller-sbc-considerations"></a><span data-ttu-id="bb35f-132">Considerazioni sul controller dei confini della sessione (SBC)</span><span class="sxs-lookup"><span data-stu-id="bb35f-132">Session Border Controller (SBC) considerations</span></span>

<span data-ttu-id="bb35f-133">Con l'instradamento diretto, puoi connettere il tuo controller SBC (Session Border Controller) direttamente al Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="bb35f-133">With Direct Routing, you connect your own Session Border Controller (SBC) directly to Phone System.</span></span>  <span data-ttu-id="bb35f-134">Per un elenco dei controller dei confini della sessione certificati, consulta [Controllori dei confini della sessione supportati.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="bb35f-134">For a list of certified SBCs, see [Supported Session Border Controllers](direct-routing-border-controllers.md).</span></span>

|<span data-ttu-id="bb35f-135">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="bb35f-135">Ask yourself</span></span>|<span data-ttu-id="bb35f-136">Azione</span><span class="sxs-lookup"><span data-stu-id="bb35f-136">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="bb35f-137">Dove e come si distribuiscono gli SBC?</span><span class="sxs-lookup"><span data-stu-id="bb35f-137">Where and how will I deploy SBCs?</span></span> | <span data-ttu-id="bb35f-138">Per altre informazioni, vedere [Configurare l'instradamento diretto](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="bb35f-138">For more information, see [Configure Direct Routing](direct-routing-configure.md)</span></span> | 
<span data-ttu-id="bb35f-139">Si hanno più tenant?</span><span class="sxs-lookup"><span data-stu-id="bb35f-139">Do I have multiple tenants?</span></span> | <span data-ttu-id="bb35f-140">Per altre informazioni, vedere [Configurare un controller dei confini della sessione per più tenant.](direct-routing-sbc-multiple-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="bb35f-140">For more information, see [Configure a Session Border Controller for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>|
|||

### <a name="voice-routing-considerations"></a><span data-ttu-id="bb35f-141">Considerazioni sul routing vocale</span><span class="sxs-lookup"><span data-stu-id="bb35f-141">Voice routing considerations</span></span>

<span data-ttu-id="bb35f-142">Sarà necessario configurare il Sistema telefonico per instradare le chiamate verso i pc specifici.</span><span class="sxs-lookup"><span data-stu-id="bb35f-142">You'll need to configure Phone System to route the calls to the specific SBCs.</span></span>

|<span data-ttu-id="bb35f-143">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="bb35f-143">Ask yourself</span></span>|<span data-ttu-id="bb35f-144">Azione</span><span class="sxs-lookup"><span data-stu-id="bb35f-144">Action</span></span> |
|:------------|:-------|
| <span data-ttu-id="bb35f-145">Quali criteri di routing vocale, utilizzo PSTN e route vocali è necessario creare?</span><span class="sxs-lookup"><span data-stu-id="bb35f-145">What voice routing policies, PSTN usage, and voice routes do I need to create?</span></span> | <span data-ttu-id="bb35f-146">Per informazioni sul routing vocale, vedere [Configurare il routing vocale.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="bb35f-146">For voice routing  information, see [Configure Voice Routing](direct-routing-configure.md).</span></span>
| <span data-ttu-id="bb35f-147">Quali utenti saranno assegnati al criterio di routing vocale definito?</span><span class="sxs-lookup"><span data-stu-id="bb35f-147">Which users will be assigned to the voice routing policy that I define?</span></span> | <span data-ttu-id="bb35f-148">Vedere gli esempi in [Configurazione del routing vocale.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="bb35f-148">See the examples in [Configure Voice Routing](direct-routing-configure.md).</span></span> |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a><span data-ttu-id="bb35f-149">Assicurarsi che le chiamate in arrivo siano sul client teams utilizzando TeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="bb35f-149">Ensure incoming calls land in the Teams client using TeamsUpgradePolicy</span></span>

<span data-ttu-id="bb35f-150">Il routing diretto è supportato solo con Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bb35f-150">Direct Routing is only supported with Microsoft Teams.</span></span> <span data-ttu-id="bb35f-151">Per ricevere chiamate PSTN tramite routing diretto, è necessario configurare TeamsUpgradePolicy per assicurarsi che le chiamate in arrivo siano ricevute in Teams.</span><span class="sxs-lookup"><span data-stu-id="bb35f-151">To receive PSTN calls through Direct Routing, you need to configure TeamsUpgradePolicy to ensure incoming calls are received in Teams.</span></span> <span data-ttu-id="bb35f-152">Gli utenti devono essere in modalità Solo Teams, che puoi eseguire assegnando loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="bb35f-152">Users must be in Teams Only mode, which you can do by assigning them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> 

|<span data-ttu-id="bb35f-153">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="bb35f-153">Ask yourself</span></span>|<span data-ttu-id="bb35f-154">Azione</span><span class="sxs-lookup"><span data-stu-id="bb35f-154">Action</span></span> |
|:------------|:-------|
|<span data-ttu-id="bb35f-155">Che cosa significa la modalità Solo per Teams?</span><span class="sxs-lookup"><span data-stu-id="bb35f-155">What does Teams Only mode mean?</span></span> | <span data-ttu-id="bb35f-156">Per ulteriori informazioni, consulta indicazioni sulla migrazione e [l'interoperabilità](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)per le organizzazioni che usano Teams insieme a Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="bb35f-156">For more information, see [Migration and interoperability guidance for organizations using Teams together with Skype for Business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).</span></span>|
|||

## <a name="additional-deployment-considerations"></a><span data-ttu-id="bb35f-157">Considerazioni aggiuntive sulla distribuzione</span><span class="sxs-lookup"><span data-stu-id="bb35f-157">Additional deployment considerations</span></span>

<span data-ttu-id="bb35f-158">In base alle esigenze e alla configurazione dell'organizzazione, è consigliabile considerare quanto segue:</span><span class="sxs-lookup"><span data-stu-id="bb35f-158">You may want to consider the following, based on your organization's needs and configuration:</span></span>

| <span data-ttu-id="bb35f-159">Chiedersi</span><span class="sxs-lookup"><span data-stu-id="bb35f-159">Ask yourself</span></span>| <span data-ttu-id="bb35f-160">Azione</span><span class="sxs-lookup"><span data-stu-id="bb35f-160">Action</span></span> |
| :------------|:-------|
| <span data-ttu-id="bb35f-161">Hai una distribuzione esistente di Skype for Business Server con connettività ibrida configurata?</span><span class="sxs-lookup"><span data-stu-id="bb35f-161">Do you have an existing Skype for Business Server deployment with hybrid connectivity configured?</span></span> |  <span data-ttu-id="bb35f-162">Per informazioni sul provisioning e la gestione degli account utente in un ambiente ibrido, vedere Account utente in un ambiente ibrido con [connettività PSTN.](direct-routing-user-accounts-in-a-hybrid-environment.md)</span><span class="sxs-lookup"><span data-stu-id="bb35f-162">To understand how user accounts in a hybrid environment are provisioned and managed, see [User accounts in a hybrid environment with PSTN connectivity](direct-routing-user-accounts-in-a-hybrid-environment.md).</span></span>| 
| <span data-ttu-id="bb35f-163">Stai eseguendo la migrazione all'instradamento diretto da un piano per chiamate o da un ambiente locale Skype for Business?</span><span class="sxs-lookup"><span data-stu-id="bb35f-163">Are you migrating to Direct Routing from Calling Plan or from a Skype for Business on-premises environment?</span></span> | <span data-ttu-id="bb35f-164">Per altre informazioni sulla migrazione al routing diretto da un ambiente esistente, vedere [Migrazione al routing diretto.](direct-routing-migrating.md)</span><span class="sxs-lookup"><span data-stu-id="bb35f-164">To understand more about migrating to Direct Routing from an existing environment, see [Migrating to Direct Routing](direct-routing-migrating.md).</span></span> |
|||
