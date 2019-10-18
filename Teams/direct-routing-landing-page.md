---
title: Routing diretto del sistema telefonico
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
f1keywords: ms.teamsadmincenter.directrouting.overview
description: Pagina di destinazione per il routing diretto
appliesto:
- Microsoft Teams
ms.openlocfilehash: decbe74eaece7508c2118175bd25f8acab200cc2
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37572191"
---
# <a name="phone-system-direct-routing"></a>Routing diretto del sistema telefonico

È stato completato per [iniziare](get-started-with-teams-quick-start.md). Sono stati distribuiti team con [chat, team, canali, & app](deploy-chat-teams-channels-microsoft-teams-landing-page.md) in tutta l'organizzazione. Forse hai distribuito [riunioni & conferenze](deploy-meetings-microsoft-teams-landing-page.md). Ora si è pronti per aggiungere carichi di lavoro cloud Voice e si è deciso di usare il proprio gestore di telefonia per la connettività PSTN (Public Switched Telephone Network) usando il routing diretto del sistema telefonico. Con il routing diretto, puoi usare il sistema telefonico con virtualmente qualsiasi gestore di telefonia.

Questo articolo descrive le decisioni di distribuzione di base per il routing diretto, oltre a considerazioni aggiuntive che potrebbero essere utili, in base alle esigenze dell'organizzazione. Per altre informazioni sulle offerte vocali di Microsoft Cloud, dovresti anche leggere [cloud Voice in Microsoft teams](cloud-voice-landing-page.md) .

## <a name="learn-more-about-direct-routing"></a>Leggi altre informazioni sul routing diretto

Gli articoli seguenti includono altre informazioni su come configurare e usare il routing diretto del sistema telefonico. La configurazione del routing diretto richiede la comprensione della progettazione di routing PSTN. Per informazioni su come pianificare e configurare il routing diretto, leggere tutti questi articoli:

- [Pianificare il routing diretto](direct-routing-plan.md) 
- [Configurare il routing diretto](direct-routing-configure.md)
- [Elenco dei controller di bordo della sessione certificati per il routing diretto](direct-routing-border-controllers.md)
- [Monitorare e risolvere i problemi di routing diretto](direct-routing-monitor-and-troubleshoot.md)

È inoltre possibile leggere gli articoli seguenti a seconda dei requisiti desiderati:

-  [Configurare un controller di bordo della sessione per più tenant](direct-routing-sbc-multiple-tenants.md)
-  [Eseguire la migrazione a routing diretto](direct-routing-migrating.md)
-  [Account utente in un ambiente ibrido con connettività PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md)
- Vedere la sessione seguente per altre informazioni sul routing diretto: [routing diretto in Microsoft teams](https://aka.ms/teams-direct-routing)

## <a name="core-deployment-decisions"></a>Decisioni di distribuzione principali

Queste sono le decisioni principali da prendere in considerazione per il routing diretto. 

|Chiedi a te stesso|Azione |
| :------------|:-------|
|Per quali utenti si Abilita il routing diretto? | Per altre informazioni, vedere [abilitare gli utenti per il servizio di routing diretto](direct-routing-configure.md#enable-users-for-direct-routing-service). |
Sono disponibili le licenze necessarie per il routing diretto? | Per altre informazioni, Vedi [licenze e altri requisiti](direct-routing-plan.md#licensing-and-other-requirements).
|||

### <a name="session-border-controller-sbc-considerations"></a>Considerazioni su Session Border Controller (SBC)

Con il routing diretto, devi connettere il tuo session border controller (SBC) direttamente al sistema telefonico.  Per un elenco di SBCs certificati, vedere [controller di bordo della sessione supportati](direct-routing-border-controllers.md).

|Chiedi a te stesso|Azione |
|:------------|:-------|
| Dove e come si distribuisce SBCs? | Per altre informazioni, vedere [configurare il routing diretto](direct-routing-configure.md) | 
Si hanno più tenant? | Per altre informazioni, vedere [configurare un controller di bordo della sessione per più tenant](direct-routing-sbc-multiple-tenants.md).|
|||

### <a name="voice-routing-considerations"></a>Considerazioni sul routing vocale

È necessario configurare il sistema telefonico per instradare le chiamate allo specifico SBCs.

|Chiedi a te stesso|Azione |
|:------------|:-------|
| Quali criteri di routing vocale, utilizzo PSTN e route vocali è necessario creare? | Per informazioni sul routing vocale, vedere [configurare il routing vocale](direct-routing-configure.md#configure-voice-routing).
| Quali utenti verranno assegnati ai criteri di routing vocale definiti? | Vedere gli esempi in [configurare il routing vocale](direct-routing-configure.md#configure-voice-routing). |
|||

### <a name="ensure-incoming-calls-land-in-the-teams-client-using-teamsupgradepolicy"></a>Assicurarsi che le chiamate in arrivo atterrino nel client teams usando TeamsUpgradePolicy

Il routing diretto è supportato solo con Microsoft teams. Per ricevere chiamate PSTN tramite routing diretto, è necessario configurare TeamsUpgradePolicy per garantire che le chiamate in arrivo vengano ricevute in teams. Gli utenti devono essere in modalità solo teams, che è possibile eseguire assegnando loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy. 

|Chiedi a te stesso|Azione |
|:------------|:-------|
|Cosa significa la modalità solo Teams? | Per altre informazioni, Vedi [linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype).|
|||

## <a name="additional-deployment-considerations"></a>Considerazioni aggiuntive sulla distribuzione

Si può prendere in considerazione quanto segue, in base alle esigenze e alla configurazione dell'organizzazione:

| Chiedi a te stesso| Azione |
| :------------|:-------|
| Si dispone di una distribuzione di Skype for Business Server esistente con connettività ibrida configurata? |  Per informazioni su come eseguire il provisioning e la gestione degli account utente in un ambiente ibrido, vedere [account utente in un ambiente ibrido con connettività PSTN](direct-routing-user-accounts-in-a-hybrid-environment.md).| 
| Si esegue la migrazione a routing diretto dal piano chiamante o da un ambiente locale di Skype for business? | Per altre informazioni sulla migrazione a routing diretto da un ambiente esistente, vedere [migrazione al routing diretto](direct-routing-migrating.md). |
|||
