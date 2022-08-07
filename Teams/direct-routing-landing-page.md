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
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: Informazioni sul sistema telefonico teams con routing diretto.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: dff97fc683acd693f867126661c9bf90550ebbe5
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67269921"
---
# <a name="direct-routing"></a>Routing diretto

L'[Introduzione](get-started-with-teams-quick-start.md) è stata completata. Si è implementato Teams nell'organizzazione, con [chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md). Forse hai distribuito [riunioni & conferenze](deploy-meetings-microsoft-teams-landing-page.md). Ora sei pronto per aggiungere carichi di lavoro vocali e hai deciso di usare il tuo gestore telefonico per la connettività PSTN (Public Switched Telephone Network) usando Sistema telefonico con Routing diretto. Con Instradamento diretto, è possibile usare Sistema telefonico praticamente con qualsiasi gestore telefonico.

Questo articolo descrive le decisioni di distribuzione di base per l'instradamento diretto, oltre a considerazioni aggiuntive che è consigliabile considerare in base alle esigenze dell'organizzazione. Per altre informazioni sulle offerte vocali di Microsoft, leggere anche [Pianificare la soluzione vocale](cloud-voice-landing-page.md) .

## <a name="learn-more-about-direct-routing"></a>Altre informazioni sull'instradamento diretto

Gli articoli seguenti forniscono ulteriori informazioni sulla configurazione e l'utilizzo di Direct Routing. La configurazione del routing diretto richiede la comprensione della progettazione del routing PSTN. Leggere tutti questi articoli per informazioni su come pianificare e configurare l'instradamento diretto:

- [Pianificare Instradamento diretto](direct-routing-plan.md) 
- [Configurare Instradamento diretto](direct-routing-configure.md)
- [Elenco di Session Border Controller certificati per Instradamento diretto](direct-routing-border-controllers.md)
- [Monitorare e risolvere i problemi di Instradamento diretto](direct-routing-monitor-and-troubleshoot.md)

È anche possibile leggere gli articoli seguenti, a seconda dei requisiti:

-  [Configurare un Session Border Controller per più tenant](direct-routing-sbc-multiple-tenants.md)
-  [Eseguire la migrazione a Instradamento diretto](direct-routing-migrating.md)
-  [Account utente in un ambiente ibrido con connettività PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Guarda la sessione seguente per saperne di più sul routing diretto: [Routing diretto in Microsoft Teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Decisioni chiave per la distribuzione

Queste sono le decisioni fondamentali da prendere in considerazione per il routing diretto. 

|Chiedersi|Azione |
| :------------|:-------|
|Per quali utenti abiliterò l'instradamento diretto? | Per altre informazioni, vedere [Abilitare gli utenti per il servizio di routing diretto](direct-routing-configure.md). |
Dispongo delle licenze necessarie per il routing diretto? | Per altre informazioni, vedere [Licenze e altri requisiti](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>Considerazioni su Session Border Controller (SBC)

Con l'instradamento diretto, puoi connettere il controller SBC (Session Border Controller) direttamente al sistema telefonico. Per un elenco degli SBC certificati, vedi [Controller dei confini della sessione supportati](direct-routing-border-controllers.md).

|Chiedersi|Azione |
|:------------|:-------|
| Dove e come si distribuiranno le schede SBC? | Per altre informazioni, vedere [Configurare il routing diretto](direct-routing-configure.md) | 
Si hanno più tenant? | Per altre informazioni, vedere [Configurare un controller dei confini della sessione per più tenant](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>Considerazioni sul routing vocale

Dovrai configurare Sistema telefonico per instradare le chiamate agli SBC specifici.

|Chiedersi|Azione |
|:------------|:-------|
| Quali criteri di routing vocale, utilizzo PSTN e route vocali devo creare? | Per informazioni sul routing vocale, vedere [Configurare il routing vocale](direct-routing-configure.md).
| Quali utenti verranno assegnati al criterio di routing vocale definito? | Vedere gli esempi in [Configurare il routing vocale](direct-routing-configure.md). |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Assicurarsi che le chiamate in arrivo atterrano nel client Teams utilizzando TeamsUpgradePolicy

Il routing diretto è supportato solo con Microsoft Teams. Per ricevere chiamate PSTN tramite routing diretto, è necessario configurare TeamsUpgradePolicy per garantire che le chiamate in arrivo vengano ricevute in Teams. Gli utenti devono essere in modalità TeamsOnly, cosa che è possibile fare assegnando loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy. 

|Chiedersi|Azione |
|:------------|:-------|
|Che cosa significa la modalità TeamsOnly? | Per altre informazioni, vedere [Guida alla migrazione e all'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](./migration-interop-guidance-for-teams-with-skype.md).|
|||


