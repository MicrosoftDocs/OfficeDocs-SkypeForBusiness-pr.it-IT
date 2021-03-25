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
description: Altre informazioni sul routing diretto, ad esempio la configurazione, le decisioni di base necessarie per la distribuzione e le considerazioni sul routing vocale.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4298cc34122d6b3bb7d9f9bb1f8698aec864426f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122210"
---
# <a name="phone-system-direct-routing"></a>Instradamento diretto di Sistema telefonico

L'[Introduzione](get-started-with-teams-quick-start.md) è stata completata. Si è implementato Teams nell'organizzazione, con [chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md). È possibile che sia stata distribuita [una conferenza & riunioni.](deploy-meetings-microsoft-teams-landing-page.md) Ora si è pronti per aggiungere carichi di lavoro vocali nel cloud e si è deciso di usare il proprio gestore di telefonia per la connettività PSTN (Public Switched Telephone Network) tramite Il routing diretto del sistema telefonico. Con Instradamento diretto, è possibile usare Sistema telefonico praticamente con qualsiasi gestore telefonico.

Questo articolo descrive le decisioni di base relative alla distribuzione per il routing diretto e altre considerazioni che è possibile prendere in considerazione, in base alle esigenze dell'organizzazione. Per altre informazioni sulle offerte vocali cloud di Microsoft, leggere anche [Cloud Voice in Microsoft Teams.](cloud-voice-landing-page.md)

## <a name="learn-more-about-direct-routing"></a>Altre informazioni sul routing diretto

Gli articoli seguenti forniscono altre informazioni sulla configurazione e l'uso di Phone System Direct Routing. La configurazione del routing diretto richiede la comprensione della progettazione del routing PSTN. Leggere tutti questi articoli per informazioni su come pianificare e configurare il routing diretto:

- [Pianificare Instradamento diretto](direct-routing-plan.md) 
- [Configurare Instradamento diretto](direct-routing-configure.md)
- [Elenco di Session Border Controller certificati per Instradamento diretto](direct-routing-border-controllers.md)
- [Monitorare e risolvere i problemi di Instradamento diretto](direct-routing-monitor-and-troubleshoot.md)

Inoltre, è consigliabile leggere gli articoli seguenti a seconda dei requisiti:

-  [Configurare un Session Border Controller per più tenant](direct-routing-sbc-multiple-tenants.md)
-  [Eseguire la migrazione a Instradamento diretto](direct-routing-migrating.md)
-  [Account utente in un ambiente ibrido con connettività PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Guardare la sessione seguente per altre informazioni sul routing diretto: [Routing diretto in Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Decisioni chiave per la distribuzione

Queste sono le decisioni principali da prendere in considerazione per il routing diretto. 

|Chiedersi|Azione |
| :------------|:-------|
|Per quali utenti abiliterò il routing diretto? | Per altre informazioni, vedere [Abilitare gli utenti per il servizio di routing diretto.](direct-routing-configure.md) |
Si hanno le licenze necessarie per il routing diretto? | Per altre informazioni, vedere [Licenze e altri requisiti.](direct-routing-plan.md#licensing-and-other-requirements)
|||

### <a name="session-border-controller-sbc-considerations"></a>Considerazioni su Session Border Controller (SBC)

Con l'instradamento diretto, è possibile connettere il proprio Session Border Controller (SBC) direttamente al sistema telefonico.  Per un elenco di SBC certificati, vedere [Controller di bordo sessione supportati.](direct-routing-border-controllers.md)

|Chiedersi|Azione |
|:------------|:-------|
| Dove e come si distribuiscono gli SBC? | Per altre informazioni, vedere [Configurare il routing diretto](direct-routing-configure.md) | 
Si hanno più tenant? | Per altre informazioni, vedere [Configurare un session border controller per più tenant.](direct-routing-sbc-multiple-tenants.md)|
|||

### <a name="voice-routing-considerations"></a>Considerazioni sul routing vocale

È necessario configurare Sistema telefonico per instradare le chiamate agli SBC specifici.

|Chiedersi|Azione |
|:------------|:-------|
| Quali criteri di routing vocale, utilizzo PSTN e route vocali è necessario creare? | Per informazioni sul routing vocale, vedere [Configurare il routing vocale.](direct-routing-configure.md)
| Quali utenti verranno assegnati ai criteri di routing vocale definiti? | Vedere gli esempi in [Configurare il routing vocale.](direct-routing-configure.md) |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Assicurarsi che le chiamate in arrivo atterrano nel client Teams usando TeamsUpgradePolicy

Il routing diretto è supportato solo con Microsoft Teams. Per ricevere chiamate PSTN tramite routing diretto, è necessario configurare TeamsUpgradePolicy per assicurarsi che le chiamate in arrivo siano ricevute in Teams. Gli utenti devono essere in modalità Solo Teams, che è possibile eseguire assegnando loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy. 

|Chiedersi|Azione |
|:------------|:-------|
|Che cosa significa la modalità Solo Teams? | Per altre informazioni, vedere Indicazioni sulla migrazione e [l'interoperabilità](./migration-interop-guidance-for-teams-with-skype.md)per le organizzazioni che usano Teams insieme a Skype for Business.|
|||

## <a name="additional-deployment-considerations"></a>Considerazioni aggiuntive sulla distribuzione

In base alle esigenze e alla configurazione dell'organizzazione, è consigliabile considerare quanto segue:

| Chiedersi| Azione |
| :------------|:-------|
| Hai una distribuzione esistente di Skype for Business Server con connettività ibrida configurata? |  Per informazioni sul provisioning e la gestione degli account utente in un ambiente ibrido, vedere Account utente in un ambiente ibrido [con connettività PSTN.](direct-routing-user-accounts-in-a-hybrid-environment.md)| 
| Stai eseguendo la migrazione a Routing diretto dal piano chiamate o da un ambiente locale Skype for Business? | Per altre informazioni sulla migrazione a Routing diretto da un ambiente esistente, vedere [Migrazione al routing diretto](direct-routing-migrating.md). |
|||