---
title: Esperienza del client di Teams e conformità alle modalità di coesistenza
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
ms.reviewer: bjwhalen
audience: admin
description: Esperienza del client di Teams e conformità alle modalità di coesistenza
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e2687f00a2d0ccb02e742d5077e472aa1dc37ed
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706616"
---
# <a name="teams-client-experience-and-conformance-to-coexistence-modes"></a>Esperienza del client di Teams e conformità alle modalità di coesistenza

<a name="about-upgrade-basic"></a>

Lo scopo delle modalità di coesistenza di Skype for business (SfBOnly, SfBWithTeamsCollab, SfBWithTeamsCollabAndMeetings) è quello di creare un'esperienza semplice e prevedibile per gli utenti finali come organizzazioni di transizione da Skype for business a teams.  Per un'organizzazione che si sposta in teams, la modalità **solo teams** è la destinazione finale per ogni utente, anche se non tutti gli utenti devono essere assegnati **solo a teams** (o qualsiasi altra modalità) allo stesso tempo.  Prima che gli utenti raggiungano la modalità TeamsOnly, le organizzazioni possono usare una qualsiasi delle modalità di coesistenza di Skype for business per garantire una comunicazione prevedibile tra gli utenti **solo team** e quelli che non sono ancora stati. 

Quando un utente si trova in una delle modalità Skype for business, tutte le chat in arrivo e le chiamate vengono instradate al client Skype for business dell'utente. Per evitare la confusione degli utenti finali e garantire un corretto routing, le funzionalità di chiamata e chat nel client teams vengono disabilitate quando un utente si trova in una delle modalità Skype for business. Analogamente, la pianificazione delle riunioni in teams viene disabilitata esplicitamente quando gli utenti si trovano nelle modalità SfBOnly o SfBWithTeamsCollab e abilitata esplicitamente quando un utente si trova in modalità SfBWithTeamsCollabAndMeetings.

Poiché la presenza è un'indicazione della raggiungibilità tramite chat e chiamate, quando la chat e le chiamate sono disabilitate, l'autonomia in teams (ovvero la visualizzazione della propria presenza nel client teams nell'immagine dell'utente) è nascosta. 

## <a name="how-the-available-functionality-in-teams-client-changes-based-on-mode"></a>Come vengono modificate le funzionalità disponibili in teams client in base alla modalità

La funzionalità disponibile in teams dipende dalla modalità di coesistenza dell'utente, come impostato da TeamsUpgradePolicy. La tabella seguente riepiloga il comportamento:

|Modalità effettiva dell'utente|Esperienza nel client Teams|
|---|---|
|Qualsiasi modalità Skype for business|La chiamata, la chat e la presenza personale sono disabilitate.|
|SfBWithTeamsCollabAndMeetings|La pianificazione delle riunioni è disponibile|
|SfBWithTeamsCollab o SfBOnly<sup>1</sup>|La pianificazione delle riunioni non è disponibile|
|||

Gli screenshot seguenti illustrano la differenza tra **solo team** o modalità **isole** e tutte le altre modalità. Tieni presente che le icone della chat e delle chiamate sono disponibili per impostazione predefinita con **solo team** o modalità **isole** (schermata a sinistra), ma non con le altre modalità (schermata destra):

![Confronto affiancato delle modalità Teams](media/teams-mode-comparison.png)

Inoltre, la presenza automatica non è disponibile nelle altre modalità, come illustrato di seguito.

![Screenshot della presenza automatica nelle riunioni prima](media/meetings-first-no-self-presence-general.png)
 
**Nota:**
<sup>1</sup> in questo momento, SfBwithTeamsCollab e SfBOnly si comportano allo stesso modo, ma lo scopo è la modalità SfBOnly per disabilitare anche la funzionalità canali e file in teams. Nel frattempo i canali possono essere nascosti usando i criteri delle autorizzazioni dell'app.


## <a name="impact-of-mode-on-other-policy-settings"></a>Impatto della modalità in altre impostazioni dei criteri
Come descritto in precedenza, l'impatto della modalità di coesistenza di un utente è la funzionalità disponibile nel client Teams dell'utente. Questo significa che il valore della modalità può avere la precedenza sul valore di altre impostazioni dei criteri, a seconda della modalità. In particolare, la modalità di coesistenza ha un impatto sull'onorabilità delle seguenti impostazioni dei criteri:

|**Modalità (app)**|**Policy. setting**|
|---|---|
|Chat|TeamsMessagingPolicy.AllowUserChat|
|Chiamate|TeamsCallingPolicy.AllowPrivateCalling|
|Pianificazione delle riunioni|TeamsMeetingPolicy.AllowPrivateMeetingScheduling</br>TeamsMeetingPolicy.AllowChannelMeetingScheduling|
|||

Gli amministratori *non* devono impostare in modo esplicito queste impostazioni dei criteri quando si usa la modalità di coesistenza, ma è importante capire che queste impostazioni si comportano in modo efficace come segue per una modalità specificata. 

|Modalità|AllowUserChat|AllowPrivateCalling|AllowPrivateMeetingScheduling|AllowChannelMeetingScheduling|
|---|---|---|---|---|
|TeamsOnly o isole|Abilitata|Abilitata|Abilitata|Abilitata|
|SfBWithTeamsCollabAndMeetings|Disabilitata|Disabilitata|Abilitata|Abilitata|
|SfBWithTeamsCollab o SfBOnly|Disabilitata|Disabilitata|Disabilitata|Disabilitata|
||||||

Quando si usa PowerShell, `Grant-CsTeamsUpgradePolicy` il cmdlet controlla la configurazione delle impostazioni corrispondenti in TeamsMessagingPolicy, TeamsCallingPolicy e TeamsMeetingPolicy per determinare se tali impostazioni verrebbero sostituite da TeamsUpgradePolicy e, in caso affermativo, viene fornito un messaggio informativo in PowerShell.  Come indicato sopra, non è più necessario impostare queste altre impostazioni dei criteri. Di seguito è riportato un esempio di come appare l'avviso di PowerShell:

`Grant-CsTeamsUpgradePolicy -Identity user1@contoso.com -PolicyName SfBWithTeamsCollab`

`WARNING: The user 'user1@contoso.com' currently has enabled values for: AllowUserChat, AllowPrivateCalling, AllowPrivateMeetingScheduling, AllowChannelMeetingScheduling, however these values will be ignored. This is because you are granting this user TeamsUpgradePolicy with mode=SfBWithTeamsCollab, which causes the Teams client to behave as if they are disabled.`



## <a name="related-topics"></a>Argomenti correlati

[Linee guida per la migrazione e l'interoperabilità per le organizzazioni che usano team insieme a Skype for business](https://docs.microsoft.com/microsoftteams/migration-interop-guidance-for-teams-with-skype)




