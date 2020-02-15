---
title: Come implementare Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.date: 1/28/2019
ms.reviewer: LolaJ
audience: admin
description: Trovare il percorso giusto per implementare Microsoft Teams nell'organizzazione.
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.rolloutteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 32c1ea2ceb816d54c08cbe22e8dabf1b8eb24f6d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045438"
---
# <a name="how-to-roll-out-microsoft-teams"></a>Come implementare Microsoft Teams

## <a name="start-here"></a>Iniziare da qui
Sia per le piccole imprese sia per le aziende multinazionali, il primo passo per l’implementazione di Teams è [Introduzione](get-started-with-teams-quick-start.md). Viene descritta l’implementazione di Teams su scala ridotta, che per le piccole imprese potrebbe già essere sufficiente. Se l'organizzazione è più grande, usare [Introduzione](get-started-with-teams-quick-start.md) per eseguire un'implementazione pilota di Teams per un gruppo di early adopter, in modo da poter imparare a usare Teams e iniziare a pianificare la distribuzione a livello di organizzazione. 

## <a name="recommended-path-to-teams"></a>Percorso suggerito per Teams


È consigliabile implementare Teams in fasi, un carico di lavoro dopo l’altro, quando l'organizzazione è pronta. **Non è necessario attendere il completamento di un passaggio prima di passare al successivo.** Alcune organizzazioni potrebbero voler distribuire tutte le funzionalità di Teams contemporaneamente, mentre altre potrebbero preferire un procedimento a fasi. Ecco i carichi di lavoro di Teams, nell'ordine in cui è consigliabile implementarli:

- [Introduzione](get-started-with-teams-quick-start.md)
- [Chat, team, canali e app](deploy-chat-teams-channels-microsoft-teams-landing-page.md)
- [Riunioni e conferenze](deploy-meetings-microsoft-teams-landing-page.md)
- [Cloud Voice](cloud-voice-landing-page.md)

[Hub di adozione](adopt-microsoft-teams-landing-page.md): durante l'implementazione di Teams è possibile usare queste risorse per agevolare l'adozione di Teams.

![Diagramma che illustra i percorsi di distribuzione di Teams](media/how-to-roll-out-teams-image1.png)


## <a name="if-youre-starting-from-skype-for-business-on-premises-or-hybrid-deployments"></a>Se si inizia da Skype for Business, dalle distribuzioni locali o ibride

Se si arriva a Teams da Skype for Business (online o locale) oppure se è necessaria una configurazione ibrida, è comunque necessario seguire il [percorso suggerito](#recommended-path-to-teams) sopra per distribuire Teams, ma prima di tutto vanno eseguite alcune operazioni di pianificazione aggiuntive. Innanzitutto esaminare le linee guida corrispondenti al profilo dell'organizzazione riportate nella tabella seguente.



|  |Profilo dell’organizzazione|Linee guida  |
|---------|---------|---------|
|<IMG src="https://docs.microsoft.com/office/media/icons/migration-blue.svg" alt="An icon representing migration" height="50" width="50">|Attualmente uso Skype for Business Online e sono pronto per passare a Teams. |Passare a [Esegui l'aggiornamento a Teams](upgrade-start-here.md).        |
|<IMG SRC="https://docs.microsoft.com/office/media/icons/hybrid-blue.svg" alt="An icon representing hybrid connectivity" height="50" width="50">|La mia organizzazione usa Skype for Business Server e voglio implementare Teams. |Per un’implementazione completa di Teams è prima necessario configurare la connettività ibrida tra l'ambiente locale e Microsoft 365. Per iniziare, leggere [Pianificare la connettività ibrida tra Skype for Business Server e Office 365](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-hybrid-connectivity). <br><br>È anche consigliabile rivedere [Esegui l'aggiornamento a Teams](upgrade-start-here.md).    |
|<IMG src="https://docs.microsoft.com/office/media/icons/on-premises.svg" alt="An icon representing an on-premises solution" height="50" width="50">|Non ho Skype for Business Server, ma ho una soluzione PSTN locale. Voglio distribuire Teams, mantenendo però la soluzione PSTN locale. |Implementare teams seguendo il [percorso suggerito](#recommended-path-to-teams) indicato sopra.<br><br>Quindi leggere [Pianificare il routing diretto](direct-routing-plan.md) per altre informazioni sull'uso del routing diretto del sistema telefonico per collegare la soluzione PSTN locale a Teams.|
|


