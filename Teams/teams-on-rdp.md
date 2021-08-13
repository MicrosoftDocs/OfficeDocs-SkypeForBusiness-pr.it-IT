---
title: Usare Teams con i servizi desktop remoto
author: cichur
ms.author: v-cichur
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come usare i Microsoft Teams con i servizi desktop remoto.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: d15dabb0b81f86d41540eda7e580c588a0d921bad88eb5fa322fd2103b0cac61
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296463"
---
# <a name="teams-in-remote-desktop-services"></a>Teams in Servizi Desktop remoto

Questo articolo descrive i requisiti e le limitazioni per l'uso di Microsoft Teams in un ambiente di Servizi Desktop remoto.

## <a name="what-is-rds"></a>Che cos'è Servizi Desktop remoto?

Servizi Desktop remoto è la piattaforma ideale per la creazione di soluzioni di virtualizzazione per ogni esigenza del cliente finale. Servizi Desktop remoto consente di distribuire singole applicazioni virtualizzate, fornire un accesso sicuro per dispositivi mobili e desktop remoto e offrire agli utenti finali la possibilità di eseguire le applicazioni e i desktop dal cloud.

Servizi Desktop remoto offre flessibilità di distribuzione, efficienza dei costi ed estendibilità. Servizi Desktop remoto viene fornito tramite un'ampia gamma di opzioni di distribuzione, tra cui Windows Server 2016 per le distribuzioni locali, Microsoft Azure per le distribuzioni cloud e una solida gamma di soluzioni per i partner.
A seconda dell'ambiente e delle preferenze, è possibile configurare la soluzione Servizi Desktop remoto per la virtualizzazione basata su sessione, come infrastruttura desktop virtuale (VDI)

Attualmente, Teams in un ambiente di servizi desktop remoto è disponibile con il supporto per la collaborazione e la funzionalità di chat. Per garantire un'esperienza utente ottimale, seguire le indicazioni di questo articolo.

## <a name="teams-on-rds-with-chat-and-collaboration"></a>Teams in Servizi Desktop remoto con chat e collaborazione

Se l'organizzazione vuole usare solo le funzionalità di chat e collaborazione in Teams, è possibile impostare criteri a livello di utente per disattivare la funzionalità di chiamata e riunione in Teams.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Impostare i criteri per disattivare la funzionalità di chiamata e riunione

È possibile impostare i criteri usando l'interfaccia Microsoft Teams o PowerShell. La propagazione delle modifiche ai criteri potrebbe richiedere del tempo (alcune ore). Se le modifiche per un determinato account non sono immediatamente disponibili, riprovare tra qualche ora.

[**Criteri di chiamata:**](teams-calling-policy.md)Teams include il criterio di chiamata Predefinito DisallowCalling, in cui tutte le funzionalità di chiamata sono disattivate. Assegnare il criterio DisallowCalling a tutti gli utenti dell'organizzazione che usano Teams in un ambiente virtualizzato.

[**Criteri riunione:**](meeting-policies-in-teams.md)Teams include i criteri predefiniti per le riunioni AllOff, in cui tutte le caratteristiche della riunione sono disattivate. Assegnare il criterio AllOff a tutti gli utenti dell'organizzazione che usano Teams in un ambiente virtualizzato.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Assegnare criteri usando l'interfaccia Microsoft Teams di amministrazione

Per assegnare i criteri di chiamata DisallowCalling e i criteri della riunione AllOff a un utente:

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare a **Utenti**.
2. Selezionare l'utente selezionandolo a sinistra del nome utente e quindi **selezionare Modifica impostazioni.**
3. Eseguire la procedura seguente:

    a.  In **Criteri di chiamata** selezionare **DisallowCalling**.

    b.  In **Criteri riunione** selezionare **AllOff**.

4. Selezionare **Applica**.

Per assegnare un criterio a più utenti contemporaneamente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi cercare gli utenti o filtrare la visualizzazione per mostrare gli utenti desiderati.
2. Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti. Per selezionare tutti gli utenti, selezionare il &#x2713; (segno di spunta) nella parte superiore della tabella.
3. Selezionare **Modifica impostazioni,** apportare le modifiche desiderate e quindi scegliere **Applica.**

In caso contrario, è anche possibile eseguire la procedura seguente:

1. Nel riquadro di spostamento sinistro dell'Microsoft Teams di amministrazione passare al criterio da assegnare. Ad esempio:

    - Passare a **Criteri**  >  **chiamate vocali** e quindi selezionare **DisallowCalling**.
    - Passare a **Criteri**  >  **riunione riunioni** e quindi selezionare **AllOff.**

2. Scegliere **Gestisci utenti**.
3. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
4. Dopo aver aggiunto gli utenti, selezionare **Salva.**

#### <a name="assign-policies-using-powershell"></a>Assegnare criteri tramite PowerShell

L'esempio seguente mostra come usare [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) per assegnare il criterio di chiamata DisallowCalling a un utente.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Per altre informazioni sull'uso di PowerShell per gestire i criteri di chiamata, [vedere Set-CsTeamsCallingPolicy.](/powershell/module/skype/set-csteamscallingpolicy)

L'esempio seguente mostra come usare [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) per assegnare i criteri della riunione AllOff a un utente.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Per altre informazioni sull'uso di PowerShell per gestire i criteri delle riunioni, [vedere Set-CsTeamsMeetingPolicy.](/powershell/module/skype/set-csteamsmeetingpolicy)