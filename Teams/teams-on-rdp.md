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
description: Informazioni su come usare Microsoft Teams con i servizi Desktop remoto.
localization_priority: Normal
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: dbf8be686029aa995ac0fb8a9977d129746b0c78
ms.sourcegitcommit: e72599d5437773322ae6ef985f804a19101ed84f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2021
ms.locfileid: "50347877"
---
# <a name="teams-in-remote-desktop-services"></a>Teams in Servizi Desktop remoto

Questo articolo descrive i requisiti e le limitazioni per l'uso di Microsoft Teams in un ambiente Servizi Desktop remoto.

## <a name="what-is-rds"></a>Che cos'è Servizi Desktop remoto?

Servizi Desktop remoto è la piattaforma ideale per la creazione di soluzioni di virtualizzazione per ogni esigenza del cliente finale. Servizi Desktop remoto consente di distribuire singole applicazioni virtualizzate, offrire un accesso sicuro a dispositivi mobili e Desktop remoto e offrire agli utenti finali la possibilità di eseguire le applicazioni e i desktop dal cloud.

Servizi Desktop remoto offre flessibilità della distribuzione, efficienza dei costi ed estendibilità. Servizi Desktop remoto offre numerose opzioni di distribuzione, tra cui Windows Server 2016 per le distribuzioni locali, Microsoft Azure per le distribuzioni cloud e una solida gamma di soluzioni partner.
A seconda dell'ambiente e delle preferenze, è possibile configurare la soluzione Servizi Desktop remoto per la virtualizzazione basata su sessione come infrastruttura VDI (Virtual Desktop Infrastructure)

Attualmente Teams in un ambiente di servizi desktop remoto è disponibile con supporto per la collaborazione e la funzionalità di chat. Per assicurare un'esperienza utente ottimale, seguire le indicazioni fornite in questo articolo.

## <a name="teams-on-rds-with-chat-and-collaboration"></a>Teams in Servizi Desktop remoto con chat e collaborazione

Se l'organizzazione vuole usare solo le funzionalità di chat e collaborazione in Teams, è possibile impostare criteri a livello utente per disattivare le funzionalità di chiamata e riunione in Teams.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Impostare i criteri per disattivare la funzionalità di chiamata e riunione

È possibile impostare i criteri usando l'interfaccia di amministrazione di Microsoft Teams o PowerShell. La propagazione delle modifiche ai criteri può richiedere del tempo (alcune ore). Se non si vedono immediatamente le modifiche per un determinato account, riprovare tra qualche ora.

[**Criteri di chiamata:**](teams-calling-policy.md)Teams include il criterio di chiamata DisallowCalling incorporato, in cui tutte le funzionalità di chiamata sono disattivate. Assegnare il criterio DisallowCalling a tutti gli utenti dell'organizzazione che usano Teams in un ambiente virtualizzato.

[**Criteri riunione:**](meeting-policies-in-teams.md)Teams include il criterio predefinito per le riunioni AllOff, in cui tutte le funzionalità per le riunioni sono disattivate. Assegnare il criterio AllOff a tutti gli utenti dell'organizzazione che usano Teams in un ambiente virtualizzato.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Assegnare criteri tramite l'interfaccia di amministrazione di Microsoft Teams

Per assegnare il criterio di chiamata DisallowCalling e il criterio Riunione AllOff a un utente:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, vai a **Utenti.**
2. Selezionare l'utente selezionandolo a sinistra del nome utente e quindi **selezionando Modifica impostazioni.**
3. Eseguire le operazioni seguenti:

    a.  In **Criteri di chiamata** selezionare **DisallowCalling.**

    b.  In **Criteri riunione** selezionare **AllOff.**

4. Selezionare **Applica.**

Per assegnare un criterio a più utenti contemporaneamente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi cercare gli utenti o filtrare la visualizzazione per mostrare gli utenti desiderati.
2. Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti. Per selezionare tutti gli utenti, &#x2713; il segno di spunta nella parte superiore della tabella.
3. Selezionare **Modifica impostazioni,** apportare le modifiche desiderate e quindi scegliere **Applica.**

In caso contrario, è anche possibile eseguire le operazioni seguenti:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams, passare al criterio da assegnare. Ad esempio:

    - Passare ai **criteri per**  >  **le chiamate** vocali, quindi selezionare **DisallowCalling.**
    - Passare a **Criteri**  >  **riunione riunioni,** quindi selezionare **AllOff.**

2. Scegliere **Gestisci utenti**.
3. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
4. Dopo aver aggiunto gli utenti, selezionare **Salva.**

#### <a name="assign-policies-using-powershell"></a>Assegnare criteri con PowerShell

L'esempio seguente mostra come utilizzare [Grant-CsTeamsCallingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamscallingpolicy) per assegnare il criterio di chiamata DisallowCalling a un utente.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Per altre informazioni sull'uso di PowerShell per gestire i criteri di chiamata, vedi [Set-CsTeamsCallingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamscallingpolicy)

L'esempio seguente mostra come utilizzare il cmdlet [Grant-CsTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) per assegnare i criteri di riunione AllOff a un utente.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Per altre informazioni sull'uso di PowerShell per gestire i criteri di riunione, vedi [Set-CsTeamsMeetingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmeetingpolicy)
