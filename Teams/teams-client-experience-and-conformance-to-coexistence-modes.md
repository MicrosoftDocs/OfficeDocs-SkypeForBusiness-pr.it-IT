---
title: Esperienza del client di Teams e conformità alle modalità di coesistenza
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Informazioni sull'esperienza client di Teams e sulla conformità alle modalità di coesistenza (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
ms.localizationpriority: medium
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91ea07d74bf9b08f627d86191ea08fc0eda1ac4c
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2022
ms.locfileid: "66605835"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Esperienza del client di Teams e conformità alle modalità di coesistenza

<a name="about-upgrade-basic"></a>

Lo scopo delle modalità di coesistenza Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) è fornire agli utenti finali un'esperienza semplice e prevedibile durante la transizione da Skype for Business a Teams.  Per un'organizzazione che passa a Teams, la modalità **Solo team** è la destinazione finale per ogni utente, anche se non tutti gli utenti devono essere assegnati solo a **Teams** (o a qualsiasi altra modalità) contemporaneamente.  Prima che gli utenti raggiungano la modalità TeamsOnly, le organizzazioni possono usare una qualsiasi delle modalità di coesistenza Skype for Business per garantire comunicazioni prevedibili tra gli utenti **solo di Teams** e quelli che non lo sono ancora. 

Quando un utente usa una delle modalità Skype for Business, tutte le chat e le chiamate in arrivo vengono indirizzate al client Skype for Business dell'utente. Per evitare confusione con l'utente finale e garantire la corretta funzionalità di routing, chiamata e chat nel client Teams viene disabilitata quando un utente si trova in una qualsiasi delle modalità Skype for Business. Allo stesso modo, la pianificazione delle riunioni in Teams viene disabilitata in modo esplicito quando gli utenti sono nelle modalità SfBOnly o SfBWithTeamsCollab e vengono abilitati in modo esplicito quando un utente è in modalità SfBWithTeamsCollabAndMeetings.

Poiché la presenza è un'indicazione di raggiungibilità tramite chat e chiamate, quando le chat e le chiamate sono disabilitate, viene nascosta anche la presenza in autonomia in Teams (ovvero la visualizzazione della propria presenza nel client di Teams nell'immagine dell'utente). 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Come cambia la funzionalità disponibile nel client di Teams in base alla modalità

La funzionalità disponibile in Teams dipende dalla modalità di coesistenza dell'utente, impostata da TeamsUpgradePolicy. La tabella seguente riepiloga il comportamento:

|Modalità effettiva dell'utente|Esperienza nel client di Teams|
|---|---|
|Qualsiasi modalità Skype for Business|Le chiamate, le chat e l'auto-presenza sono disabilitate.|
|SfBWithTeamsCollabAndMeetings|Pianificazione delle riunioni è disponibile|
|SfBWithTeamsCollab o SfBOnly<sup>1</sup>|La pianificazione delle riunioni non è disponibile|
|||

Gli screenshot seguenti illustrano la differenza tra la modalità **Solo teams** o **Isole** e tutte le altre modalità. Tieni presente che le icone di chat e chiamate sono disponibili per impostazione predefinita con la modalità **Solo teams** o **Isole** (screenshot sinistro), ma non con le altre modalità (screenshot a destra):

![Confronto affiancato delle modalità di Teams.](media/teams-mode-comparison.png)

Inoltre, la presenza in autonomia non è disponibile nelle altre modalità, come illustrato di seguito.

![Screenshot della presenza personale in Prima riunione.](media/meetings-first-no-self-presence-general.png)
 
**Nota:**
 <sup>1</sup> In questo momento SfBwithTeamsCollab e SfBOnly si comportano allo stesso modo, ma la modalità SfBOnly ha lo scopo di disabilitare anche la funzionalità Canali e file in Teams. Nel frattempo, i canali possono essere nascosti usando i criteri Autorizzazioni app.


## <a name="impact-of-mode-on-other-policy-settings"></a>Impatto della modalità su altre impostazioni dei criteri
Come descritto in precedenza, la modalità coesistenza di un utente influisce sulla funzionalità disponibile nel client Teams dell'utente. Questo significa che il valore di mode può avere la precedenza sul valore di altre impostazioni dei criteri, a seconda della modalità. In particolare, la modalità di coesistenza influisce sulla conformità delle impostazioni dei criteri seguenti:

|**Modalità di accesso (app)**|**Criteri.Impostazione**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Chiamate|TeamsCallingPolicy.AllowPrivateCalling|
|Pianificazione delle riunioni|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Gli amministratori *non* devono impostare in modo esplicito queste impostazioni dei criteri quando usano la modalità di coesistenza, ma è importante tenere presente che queste impostazioni si comportano in modo efficace come indicato di seguito per una determinata modalità. 

|Modalità|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly o Isole|Abilitata|Abilitata|Abilitata|Abilitata|
|SfBWithTeamsCollabAndMeetings|Disattiva|Disattiva|Abilitata|Abilitata|
|SfBWithTeamsCollab o SfBOnly|Disattiva|Disattiva|Disattiva|Disattiva|
||||||

Quando si usa PowerShell, il `Grant-CsTeamsUpgradePolicy` cmdlet controlla la configurazione delle impostazioni corrispondenti in TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy per determinare se tali impostazioni sarebbero sovrapposte da TeamsUpgradePolicy e, in tal caso, viene fornito un messaggio informativo in PowerShell.  Come indicato in precedenza, non è più necessario impostare queste altre impostazioni dei criteri. Di seguito è riportato un esempio dell'avviso di PowerShell:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>Argomenti correlati

[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)