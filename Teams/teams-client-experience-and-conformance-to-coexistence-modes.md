---
title: Esperienza del client di Teams e conformità alle modalità di coesistenza
author: HowlinWolf-92
ms.author: v-mahoffman
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Informazioni sull'Teams client e sulla conformità alle modalità di coesistenza (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings).
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
ms.openlocfilehash: d346f8f6259eef89b798bec6298f1c1fde0ac0a5
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60865655"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Esperienza del client di Teams e conformità alle modalità di coesistenza

<a name="about-upgrade-basic"></a>

Lo scopo delle modalità di coesistenza di Skype for Business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) è fornire un'esperienza semplice e prevedibile per gli utenti finali quando le organizzazioni passano da Skype for Business a Teams.  Per un'organizzazione che si sposta su Teams, la modalità **solo Teams** è la destinazione finale per ogni utente, anche se non tutti gli utenti devono essere assegnati **contemporaneamente Teams** Only (o qualsiasi altra modalità).  Prima che gli utenti raggiungano la modalità TeamsOnly, le organizzazioni possono usare una delle modalità di coesistenza di Skype for Business per garantire comunicazioni prevedibili tra gli utenti che sono **solo Teams** e quelli che non lo sono ancora. 

Quando un utente è in una delle modalità Skype for Business, tutte le chat e le chiamate in arrivo vengono instradati al client Skype for Business dell'utente. Per evitare confusione con l'utente finale e garantire la corretta funzionalità di routing, chiamate e chat nel client Teams viene disabilitata quando un utente si trova in una delle modalità Skype for Business messaggi. Analogamente, la pianificazione delle riunioni in Teams viene disabilitata in modo esplicito quando gli utenti sono in modalità SfBOnly o SfBWithTeamsCollab e abilitata in modo esplicito quando un utente è in modalità SfBWithTeamsCollabAndMeetings.

Poiché la presenza è un'indicazione della raggiungibilità tramite chat e chiamate, quando la chat e le chiamate sono disabilitate, anche l'auto-presenza in Teams (ovvero la visualizzazione della propria presenza nel client Teams nell'immagine dell'utente) è nascosta. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Modalità di modifica delle funzionalità disponibili Teams client in base alla modalità

La funzionalità disponibile in Teams dipende dalla modalità di coesistenza dell'utente, come impostato da TeamsUpgradePolicy. La tabella seguente riepiloga il comportamento:

|Modalità effettiva dell'utente|Esperienza nel client Teams|
|---|---|
|Qualsiasi Skype for Business automatica|Le chiamate, le chat e l'auto-presenza sono disabilitate.|
|SfBWithTeamsCollabAndMeetings|La pianificazione delle riunioni è disponibile|
|SfBWithTeamsCollab o SfBOnly<sup>1</sup>|La pianificazione delle riunioni non è disponibile|
|||

Gli screenshot seguenti illustrano la differenza tra  **Teams modalità** Solo o Isole e tutte le altre modalità. Si noti che le icone delle chat e delle  chiamate sono disponibili per impostazione predefinita **con la** modalità Solo Teams o Isole (screenshot a sinistra), ma non con le altre modalità (screenshot a destra):

![Confronto affiancato delle modalità di Teams predefinite.](media/teams-mode-comparison.png)

Inoltre, la presenza personale non è disponibile nelle altre modalità, come illustrato di seguito.

![Screenshot della presenza personale in Meetings First.](media/meetings-first-no-self-presence-general.png)
 
**Nota:** 
 <sup>1</sup> Al momento, SfBwithTeamsCollab e SfBOnly si comportano allo stesso modo, ma l'intento è che la modalità SfBOnly disabiliti anche la funzionalità Canali e file in Teams. Nel frattempo, i canali possono essere nascosti usando il criterio Autorizzazioni app.


## <a name="impact-of-mode-on-other-policy-settings"></a>Impatto della modalità su altre impostazioni dei criteri
Come descritto in precedenza, la modalità di coesistenza di un utente influisce sulle funzionalità disponibili nel client di Teams utente. Questo significa che il valore della modalità può avere la precedenza sul valore di altre impostazioni dei criteri, a seconda della modalità. In particolare, la modalità di coesistenza influisce sull'applicazione delle impostazioni dei criteri seguenti:

|**Modalità (app)**|**Policy.Setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Chiamate|TeamsCallingPolicy.AllowPrivateCalling|
|Pianificazione delle riunioni|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Gli amministratori *non devono* impostare in modo esplicito queste impostazioni dei criteri quando usano la modalità di coesistenza, ma è importante comprendere che queste impostazioni si comportano in modo efficace nel modo seguente per una determinata modalità. 

|Modalità|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly o Islands|Abilitata|Abilitata|Abilitata|Abilitata|
|SfBWithTeamsCollabAndMeetings|Disattiva|Disattiva|Abilitata|Abilitata|
|SfBWithTeamsCollab o SfBOnly|Disattiva|Disattiva|Disattiva|Disattiva|
||||||

Quando si usa PowerShell, il cmdlet controlla la configurazione delle impostazioni corrispondenti `Grant-CsTeamsUpgradePolicy` in TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy per determinare se tali impostazioni verrebbero sostituite da TeamsUpgradePolicy e, in tal caso, viene fornito un messaggio informativo in PowerShell.  Come indicato in precedenza, non è più necessario impostare queste altre impostazioni dei criteri. Di seguito è riportato un esempio dell'aspetto dell'avviso di PowerShell:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>Argomenti correlati

[Indicazioni sulla migrazione e l'interoperabilità per le organizzazioni che usano Teams insieme a Skype for Business](./migration-interop-guidance-for-teams-with-skype.md)