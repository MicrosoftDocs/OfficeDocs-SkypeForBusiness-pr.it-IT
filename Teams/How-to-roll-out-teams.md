---
title: Come implementare Microsoft Teams
author: lolajacobsen
ms.author: lolaj
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: LolaJ
audience: admin
description: Trovare il percorso giusto per implementare Microsoft Teams nell'organizzazione.
localization_priority: Priority
search.appverid: MET150
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.dashboard.helparticle.rolloutteams
appliesto:
- Microsoft Teams
ms.openlocfilehash: 48756dc6fdcbe2c289abb08b803b169fdb6cee58
ms.sourcegitcommit: 545e466f1fa9163bb00cc96c8db70a70b02af697
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/24/2020
ms.locfileid: "42928429"
---
# <a name="how-to-roll-out-microsoft-teams"></a>Come implementare Microsoft Teams

## <a name="start-here"></a>Iniziare da qui
Sia per le piccole imprese sia per le società multi-nazionali, il primo passo per l'implementazione di Teams è andare alla pagina [Introduzione](get-started-with-teams-quick-start.md). Viene illustrata la procedura per eseguire l'implementazione di Teams su scala ridotta, che per le piccole imprese potrebbe già essere sufficiente, o se si sta implementando rapidamente Teams come primo carico di lavoro di Office 365 per supportare i **lavoratori remoti**. Se l'organizzazione è più grande, usare [Introduzione](get-started-with-teams-quick-start.md) per eseguire un'implementazione pilota di Teams per un gruppo di early adopter, in modo da poter imparare a usare Teams e iniziare a pianificare la distribuzione a livello di organizzazione. 

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
|<IMG src="https://docs.microsoft.com/office/media/icons/migration-teams.svg" alt="Migration arrow symbol" height="50" width="50">|Attualmente uso Skype for Business Online e sono pronto per passare a Teams. |Passare a [Esegui l'aggiornamento a Teams](upgrade-start-here.md).        |
|<IMG SRC="https://docs.microsoft.com/office/media/icons/hybrid-teams.svg" alt="Hybrid symbol" height="50" width="50">|La mia organizzazione usa Skype for Business Server e voglio implementare Teams. |Per un’implementazione completa di Teams è prima necessario configurare la connettività ibrida tra l'ambiente locale e Microsoft 365. Per iniziare, leggere [Pianificare la connettività ibrida tra Skype for Business Server e Office 365](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-hybrid-connectivity). <br><br>È anche consigliabile rivedere [Esegui l'aggiornamento a Teams](upgrade-start-here.md).   |
|<IMG src="https://docs.microsoft.com/office/media/icons/on-premises-teams.svg" alt="On premises symbol" height="50" width="50">|Non ho Skype for Business Server, ma ho una soluzione PSTN locale. Voglio distribuire Teams, mantenendo però la soluzione PSTN locale. |Implementare teams seguendo il [percorso suggerito](#recommended-path-to-teams) indicato sopra.<br><br>Quindi leggere [Pianificare il routing diretto](direct-routing-plan.md) per altre informazioni sull'uso del routing diretto del sistema telefonico per collegare la soluzione PSTN locale a Teams.|
|


