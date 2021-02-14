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
# <a name="phone-system-direct-routing"></a>Instradamento diretto di Sistema telefonico

L'[Introduzione](get-started-with-teams-quick-start.md) è stata completata. Si è implementato Teams nell'organizzazione, con [chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md). Potresti aver distribuito Riunioni [o conferenze &.](deploy-meetings-microsoft-teams-landing-page.md) Ora sei pronto per aggiungere carichi di lavoro vocali sul cloud e hai deciso di usare il tuo gestore di telefonia per la connettività PSTN (Public Switched Telephone Network) tramite l'instradamento diretto del sistema telefonico. Con Instradamento diretto, è possibile usare Sistema telefonico praticamente con qualsiasi gestore telefonico.

Questo articolo descrive le decisioni di base per la distribuzione per il routing diretto, oltre a considerazioni aggiuntive da tenere in considerazione, in base alle esigenze dell'organizzazione. Per altre informazioni sulle offerte vocali cloud di Microsoft, è consigliabile leggere anche [Cloud Voice in Microsoft Teams.](cloud-voice-landing-page.md)

## <a name="learn-more-about-direct-routing"></a>Altre informazioni sull'instradamento diretto

Gli articoli seguenti forniscono altre informazioni sulla configurazione e l'uso dell'instradamento diretto del sistema telefonico. La configurazione del routing diretto richiede una conoscenza della progettazione del routing PSTN. Leggere tutti questi articoli per informazioni su come pianificare e configurare il routing diretto:

- [Pianificare Instradamento diretto](direct-routing-plan.md) 
- [Configurare Instradamento diretto](direct-routing-configure.md)
- [Elenco di Session Border Controller certificati per Instradamento diretto](direct-routing-border-controllers.md)
- [Monitorare e risolvere i problemi di Instradamento diretto](direct-routing-monitor-and-troubleshoot.md)

Inoltre, a seconda dei requisiti, è consigliabile leggere gli articoli seguenti:

-  [Configurare un Session Border Controller per più tenant](direct-routing-sbc-multiple-tenants.md)
-  [Eseguire la migrazione a Instradamento diretto](direct-routing-migrating.md)
-  [Account utente in un ambiente ibrido con connettività PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Guardare la sessione seguente per altre informazioni sul routing diretto: [Routing diretto in Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Decisioni chiave per la distribuzione

Queste sono le decisioni di base da prendere in considerazione per il routing diretto. 

|Chiedersi|Azione |
| :------------|:-------|
|Per quali utenti abiliterò il routing diretto? | Per altre informazioni, vedere [Abilitare gli utenti per il servizio di instradamento diretto.](direct-routing-configure.md) |
Si hanno le licenze necessarie per l'instradamento diretto? | Per altre informazioni, vedere Licenze [e altri requisiti.](direct-routing-plan.md#licensing-and-other-requirements)
|||

### <a name="session-border-controller-sbc-considerations"></a>Considerazioni sul controller dei confini della sessione (SBC)

Con l'instradamento diretto, puoi connettere il tuo controller SBC (Session Border Controller) direttamente al Sistema telefonico.  Per un elenco dei controller dei confini della sessione certificati, consulta [Controllori dei confini della sessione supportati.](direct-routing-border-controllers.md)

|Chiedersi|Azione |
|:------------|:-------|
| Dove e come si distribuiscono gli SBC? | Per altre informazioni, vedere [Configurare l'instradamento diretto](direct-routing-configure.md) | 
Si hanno più tenant? | Per altre informazioni, vedere [Configurare un controller dei confini della sessione per più tenant.](direct-routing-sbc-multiple-tenants.md)|
|||

### <a name="voice-routing-considerations"></a>Considerazioni sul routing vocale

Sarà necessario configurare il Sistema telefonico per instradare le chiamate verso i pc specifici.

|Chiedersi|Azione |
|:------------|:-------|
| Quali criteri di routing vocale, utilizzo PSTN e route vocali è necessario creare? | Per informazioni sul routing vocale, vedere [Configurare il routing vocale.](direct-routing-configure.md)
| Quali utenti saranno assegnati al criterio di routing vocale definito? | Vedere gli esempi in [Configurazione del routing vocale.](direct-routing-configure.md) |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Assicurarsi che le chiamate in arrivo siano sul client teams utilizzando TeamsUpgradePolicy

Il routing diretto è supportato solo con Microsoft Teams. Per ricevere chiamate PSTN tramite routing diretto, è necessario configurare TeamsUpgradePolicy per assicurarsi che le chiamate in arrivo siano ricevute in Teams. Gli utenti devono essere in modalità Solo Teams, che puoi eseguire assegnando loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy. 

|Chiedersi|Azione |
|:------------|:-------|
|Che cosa significa la modalità Solo per Teams? | Per ulteriori informazioni, consulta indicazioni sulla migrazione e [l'interoperabilità](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)per le organizzazioni che usano Teams insieme a Skype for Business.|
|||

## <a name="additional-deployment-considerations"></a>Considerazioni aggiuntive sulla distribuzione

In base alle esigenze e alla configurazione dell'organizzazione, è consigliabile considerare quanto segue:

| Chiedersi| Azione |
| :------------|:-------|
| Hai una distribuzione esistente di Skype for Business Server con connettività ibrida configurata? |  Per informazioni sul provisioning e la gestione degli account utente in un ambiente ibrido, vedere Account utente in un ambiente ibrido con [connettività PSTN.](direct-routing-user-accounts-in-a-hybrid-environment.md)| 
| Stai eseguendo la migrazione all'instradamento diretto da un piano per chiamate o da un ambiente locale Skype for Business? | Per altre informazioni sulla migrazione al routing diretto da un ambiente esistente, vedere [Migrazione al routing diretto.](direct-routing-migrating.md) |
|||
