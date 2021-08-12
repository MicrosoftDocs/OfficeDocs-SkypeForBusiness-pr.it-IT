---
title: Telefono routing diretto del sistema in Teams
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
description: Informazioni sulla configurazione del routing diretto, sulle decisioni di base necessarie per la distribuzione e sulle considerazioni relative al routing vocale.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 55676d855d3e15c3f767203da981a4fae241f3128a270f5656d770a229f00059
ms.sourcegitcommit: 2a76435beaac1e5daa647e93f693ea8672ec0135
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/11/2021
ms.locfileid: "57848071"
---
# <a name="phone-system-direct-routing"></a>Telefono routing diretto del sistema

L'[Introduzione](get-started-with-teams-quick-start.md) è stata completata. Si è implementato Teams nell'organizzazione, con [chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md). È possibile che sia stata distribuita [la funzionalità Riunioni & conferenza](deploy-meetings-microsoft-teams-landing-page.md). Ora si è pronti per aggiungere carichi di lavoro vocali nel cloud e si è deciso di usare il proprio gestore di telefonia per la connettività PSTN (Public Switched Telephone Network) usando Sistema telefonico Routing diretto. Con Instradamento diretto, è possibile usare Sistema telefonico praticamente con qualsiasi gestore telefonico.

Questo articolo descrive le decisioni di base relative alla distribuzione per il routing diretto e altre considerazioni che è possibile prendere in considerazione, in base alle esigenze dell'organizzazione. È consigliabile leggere [anche Cloud Voice in Microsoft Teams](cloud-voice-landing-page.md) per altre informazioni sulle offerte vocali cloud di Microsoft.

## <a name="learn-more-about-direct-routing"></a>Altre informazioni sul routing diretto

Gli articoli seguenti forniscono altre informazioni sulla configurazione e l'uso Sistema telefonico routing diretto. La configurazione del routing diretto richiede la comprensione della progettazione del routing PSTN. Leggere tutti questi articoli per informazioni su come pianificare e configurare il routing diretto:

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

Con l'instradamento diretto, è possibile connettere il proprio Session Border Controller (SBC) direttamente a Sistema telefonico.  Per un elenco di SBC certificati, vedere [Controller di bordo sessione supportati.](direct-routing-border-controllers.md)

|Chiedersi|Azione |
|:------------|:-------|
| Dove e come si distribuiscono gli SBC? | Per altre informazioni, vedere [Configurare il routing diretto](direct-routing-configure.md) | 
Si hanno più tenant? | Per altre informazioni, vedere [Configurare un session border controller per più tenant.](direct-routing-sbc-multiple-tenants.md)|
|||

### <a name="voice-routing-considerations"></a>Considerazioni sul routing vocale

È necessario configurare le Sistema telefonico per instradare le chiamate agli SBC specifici.

|Chiedersi|Azione |
|:------------|:-------|
| Quali criteri di routing vocale, utilizzo PSTN e route vocali è necessario creare? | Per informazioni sul routing vocale, vedere [Configurare il routing vocale.](direct-routing-configure.md)
| Quali utenti verranno assegnati ai criteri di routing vocale definiti? | Vedere gli esempi in [Configurare il routing vocale.](direct-routing-configure.md) |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Assicurarsi che le chiamate in arrivo atterrano nel client Teams tramite TeamsUpgradePolicy

Il routing diretto è supportato solo con Microsoft Teams. Per ricevere chiamate PSTN tramite Routing diretto, è necessario configurare TeamsUpgradePolicy per assicurarsi che le chiamate in arrivo siano ricevute Teams. Gli utenti devono essere in Teams modalità Solo utenti, che è possibile eseguire assegnando loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy. 

|Chiedersi|Azione |
|:------------|:-------|
|Cosa significa Teams modalità Solo clic? | Per altre informazioni, vedere Indicazioni sulla migrazione e [l'interoperabilità](./migration-interop-guidance-for-teams-with-skype.md)per le organizzazioni che usano Teams insieme a Skype for Business .|
|||

## <a name="additional-deployment-considerations"></a>Considerazioni aggiuntive sulla distribuzione

In base alle esigenze e alla configurazione dell'organizzazione, è consigliabile considerare quanto segue:

| Chiedersi| Azione |
| :------------|:-------|
| Si ha una distribuzione di Skype for Business Server con la connettività ibrida configurata? |  Per informazioni sul provisioning e la gestione degli account utente in un ambiente ibrido, vedere Account utente in un ambiente ibrido [con connettività PSTN.](direct-routing-user-accounts-in-a-hybrid-environment.md)| 
| Si esegue la migrazione a Routing diretto da un piano per chiamate o da un Skype for Business locale? | Per altre informazioni sulla migrazione a Routing diretto da un ambiente esistente, vedere [Migrazione al routing diretto.](direct-routing-migrating.md) |
|||
