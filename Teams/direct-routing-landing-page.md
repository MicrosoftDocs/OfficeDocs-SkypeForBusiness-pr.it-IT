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
description: Leggi altre informazioni sul routing diretto e leggi le decisioni di distribuzione necessarie che dovrai affrontare.
ms.custom: seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba1732864a765af5bb5a0dfc5504f1d37b5460b5
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904581"
---
# <a name="phone-system-direct-routing"></a>Instradamento diretto di Sistema telefonico

L'[Introduzione](get-started-with-teams-quick-start.md) è stata completata. Si è implementato Teams nell'organizzazione, con [chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md). Forse hai distribuito [riunioni & conferenze](deploy-meetings-microsoft-teams-landing-page.md). Ora si è pronti per aggiungere carichi di lavoro cloud Voice e si è deciso di usare il proprio gestore di telefonia per la connettività PSTN (Public Switched Telephone Network) usando il routing diretto del sistema telefonico. Con Instradamento diretto, è possibile usare Sistema telefonico praticamente con qualsiasi gestore telefonico.

Questo articolo descrive le decisioni di distribuzione di base per il routing diretto, oltre a considerazioni aggiuntive che potrebbero essere utili, in base alle esigenze dell'organizzazione. Per altre informazioni sulle offerte vocali di Microsoft Cloud, dovresti anche leggere [cloud Voice in Microsoft teams](cloud-voice-landing-page.md) .

## <a name="learn-more-about-direct-routing"></a>Leggi altre informazioni sul routing diretto

Gli articoli seguenti includono altre informazioni su come configurare e usare il routing diretto del sistema telefonico. La configurazione del routing diretto richiede la comprensione della progettazione di routing PSTN. Per informazioni su come pianificare e configurare il routing diretto, leggere tutti questi articoli:

- [Pianificare Instradamento diretto](direct-routing-plan.md) 
- [Configurare Instradamento diretto](direct-routing-configure.md)
- [Elenco di Session Border Controller certificati per Instradamento diretto](direct-routing-border-controllers.md)
- [Monitorare e risolvere i problemi di Instradamento diretto](direct-routing-monitor-and-troubleshoot.md)

È inoltre possibile leggere gli articoli seguenti a seconda dei requisiti desiderati:

-  [Configurare un Session Border Controller per più tenant](direct-routing-sbc-multiple-tenants.md)
-  [Eseguire la migrazione a Instradamento diretto](direct-routing-migrating.md)
-  [Account utente in un ambiente ibrido con connettività PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Vedere la sessione seguente per altre informazioni sul routing diretto: [routing diretto in Microsoft teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Decisioni chiave per la distribuzione

Queste sono le decisioni principali da prendere in considerazione per il routing diretto. 

|Chiedersi|Azione |
| :------------|:-------|
|Per quali utenti si Abilita il routing diretto? | Per altre informazioni, vedere [abilitare gli utenti per il servizio di routing diretto](direct-routing-configure.md). |
Sono disponibili le licenze necessarie per il routing diretto? | Per altre informazioni, Vedi [licenze e altri requisiti](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>Considerazioni su Session Border Controller (SBC)

Con il routing diretto, devi connettere il tuo session border controller (SBC) direttamente al sistema telefonico.  Per un elenco di SBCs certificati, vedere [controller di bordo della sessione supportati](direct-routing-border-controllers.md).

|Chiedersi|Azione |
|:------------|:-------|
| Dove e come si distribuisce SBCs? | Per altre informazioni, vedere [configurare il routing diretto](direct-routing-configure.md) | 
Si hanno più tenant? | Per altre informazioni, vedere [configurare un controller di bordo della sessione per più tenant](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>Considerazioni sul routing vocale

È necessario configurare il sistema telefonico per instradare le chiamate allo specifico SBCs.

|Chiedersi|Azione |
|:------------|:-------|
| Quali criteri di routing vocale, utilizzo PSTN e route vocali è necessario creare? | Per informazioni sul routing vocale, vedere [configurare il routing vocale](direct-routing-configure.md).
| Quali utenti verranno assegnati ai criteri di routing vocale definiti? | Vedere gli esempi in [configurare il routing vocale](direct-routing-configure.md). |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Assicurarsi che le chiamate in arrivo atterrino nel client teams usando TeamsUpgradePolicy

Il routing diretto è supportato solo con Microsoft teams. Per ricevere chiamate PSTN tramite routing diretto, è necessario configurare TeamsUpgradePolicy per garantire che le chiamate in arrivo vengano ricevute in teams. Gli utenti devono essere in modalità solo teams, che è possibile eseguire assegnando loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy. 

|Chiedersi|Azione |
|:------------|:-------|
|Cosa significa la modalità solo Teams? | Per altre informazioni, Vedi [linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).|
|||

## <a name="additional-deployment-considerations"></a>Considerazioni aggiuntive sulla distribuzione

Si può prendere in considerazione quanto segue, in base alle esigenze e alla configurazione dell'organizzazione:

| Chiedersi| Azione |
| :------------|:-------|
| Si dispone di una distribuzione di Skype for Business Server esistente con connettività ibrida configurata? |  Per informazioni su come eseguire il provisioning e la gestione degli account utente in un ambiente ibrido, vedere [account utente in un ambiente ibrido con connettività PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md).| 
| Si esegue la migrazione a routing diretto dal piano chiamante o da un ambiente locale di Skype for business? | Per altre informazioni sulla migrazione a routing diretto da un ambiente esistente, vedere [migrazione al routing diretto](direct-routing-migrating.md). |
|||
