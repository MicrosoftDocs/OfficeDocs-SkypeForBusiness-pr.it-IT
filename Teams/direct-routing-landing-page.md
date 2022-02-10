---
title: Routing diretto
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: filippse
ms.date: 01/28/2019
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Informazioni sulle Teams Sistema telefonico con Il routing diretto.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3fe723ee8347ea96c87cb0a9e85f7794c5e50e01
ms.sourcegitcommit: 5e9b50cd1b513f06734be6c024ac06d293b27089
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/10/2022
ms.locfileid: "62518708"
---
# <a name="direct-routing"></a>Routing diretto

L'[Introduzione](get-started-with-teams-quick-start.md) è stata completata. Si è implementato Teams nell'organizzazione, con [chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md). È possibile che sia stata distribuita [una conferenza & riunioni](deploy-meetings-microsoft-teams-landing-page.md). Ora si è pronti per aggiungere carichi di lavoro vocali e si è deciso di usare il proprio gestore di telefonia per la connettività PSTN (Public Switched Telephone Network) usando Sistema telefonico con routing diretto. Con Instradamento diretto, è possibile usare Sistema telefonico praticamente con qualsiasi gestore telefonico.

Questo articolo descrive le decisioni di base relative alla distribuzione per il routing diretto e altre considerazioni che è possibile prendere in considerazione, in base alle esigenze dell'organizzazione. Per altre [informazioni sulle offerte](cloud-voice-landing-page.md) vocali di Microsoft, vedere Pianificare la soluzione vocale.

## <a name="learn-more-about-direct-routing"></a>Altre informazioni sul routing diretto

Gli articoli seguenti forniscono altre informazioni sulla configurazione e l'uso del routing diretto. La configurazione del routing diretto richiede la comprensione della progettazione del routing PSTN. Leggere tutti questi articoli per informazioni su come pianificare e configurare il routing diretto:

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
|Per quali utenti abiliterò il routing diretto? | Per altre informazioni, vedere [Abilitare gli utenti per il servizio di routing diretto](direct-routing-configure.md). |
Si hanno le licenze necessarie per il routing diretto? | Per altre informazioni, vedere [Licenze e altri requisiti](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>Considerazioni su Session Border Controller (SBC)

Con l'instradamento diretto, è possibile connettere il proprio Session Border Controller (SBC) direttamente a Sistema telefonico. Per un elenco di SBC certificati, vedere [Controller di bordo sessione supportati](direct-routing-border-controllers.md).

|Chiedersi|Azione |
|:------------|:-------|
| Dove e come si distribuiscono gli SBC? | Per altre informazioni, vedere [Configurare il routing diretto](direct-routing-configure.md) | 
Si hanno più tenant? | Per altre informazioni, vedere [Configurare un session border controller per più tenant](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>Considerazioni sul routing vocale

È necessario configurare le Sistema telefonico per instradare le chiamate agli SBC specifici.

|Chiedersi|Azione |
|:------------|:-------|
| Quali criteri di routing vocale, utilizzo PSTN e route vocali è necessario creare? | Per informazioni sul routing vocale, vedere [Configurare il routing vocale](direct-routing-configure.md).
| Quali utenti verranno assegnati ai criteri di routing vocale definiti? | Vedere gli esempi in [Configurare il routing vocale](direct-routing-configure.md). |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Assicurarsi che le chiamate in arrivo atterrano nel client Teams tramite TeamsUpgradePolicy

Il routing diretto è supportato solo con Microsoft Teams. Per ricevere chiamate PSTN tramite routing diretto, è necessario configurare TeamsUpgradePolicy per assicurarsi che le chiamate in arrivo siano ricevute Teams. Gli utenti devono essere in modalità TeamsOnly, che è possibile eseguire assegnando loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy. 

|Chiedersi|Azione |
|:------------|:-------|
|Cosa significa la modalità TeamsOnly? | Per altre informazioni, vedere [Indicazioni sulla migrazione e l'interoperabilità](./migration-interop-guidance-for-teams-with-skype.md) per le organizzazioni che usano Teams insieme a Skype for Business.|
|||


