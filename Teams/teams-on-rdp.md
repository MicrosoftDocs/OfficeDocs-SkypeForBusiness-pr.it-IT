---
title: Usare Teams con i servizi desktop remoto
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: alivano
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come usare Microsoft Teams con i servizi desktop remoto.
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- m365initiative-meetings
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7e18aa0ad95033550d0ef2f7c6049e700d917798
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606095"
---
# <a name="teams-in-remote-desktop-services"></a>Teams in Servizi Desktop remoto

Questo articolo descrive i requisiti e le limitazioni per l'uso di Microsoft Teams in un ambiente servizi Desktop remoto.

## <a name="what-is-rds"></a>Che cos'è Servizi Desktop remoto?

Servizi Desktop remoto è la piattaforma scelta per creare soluzioni di virtualizzazione per ogni esigenza del cliente finale. Servizi Desktop remoto consente di distribuire singole applicazioni virtualizzate, fornire un accesso sicuro a desktop remoto e mobile e offrire agli utenti finali la possibilità di eseguire le applicazioni e i desktop dal cloud.

Servizi Desktop remoto offre flessibilità di distribuzione, efficienza dei costi ed estendibilità. Servizi Desktop remoto viene fornito tramite un'ampia gamma di opzioni di distribuzione, tra cui Windows Server 2016 per le distribuzioni locali, Microsoft Azure per le distribuzioni cloud e una solida gamma di soluzioni partner.
A seconda dell'ambiente e delle preferenze, è possibile configurare la soluzione Servizi Desktop remoto per la virtualizzazione basata su sessione, come infrastruttura VDI (Virtual Desktop Infrastructure)

Attualmente, Teams in un ambiente di servizi desktop remoto è disponibile con il supporto per la collaborazione e le funzionalità di chat. Per garantire un'esperienza utente ottimale, seguire le indicazioni in questo articolo.

## <a name="teams-on-rds-with-chat-and-collaboration"></a>Teams su Servizi Desktop remoto con chat e collaborazione

Se l'organizzazione vuole usare solo le funzionalità di chat e collaborazione in Teams, è possibile impostare criteri a livello utente per disattivare le funzionalità di chiamata e riunione in Teams.

### <a name="set-policies-to-turn-off-calling-and-meeting-functionality"></a>Impostare i criteri per disattivare la funzionalità di chiamata e riunione

È possibile impostare i criteri usando l'interfaccia di amministrazione di Microsoft Teams o PowerShell. La propagazione delle modifiche ai criteri potrebbe richiedere del tempo (alcune ore). Se le modifiche per un determinato account non vengono visualizzate immediatamente, riprova tra poche ore.

[**Criteri per le**](teams-calling-policy.md) chiamate: Teams include il criterio di chiamata DisallowCalling integrato, in cui tutte le funzionalità di chiamata sono disattivate. Assegnare il criterio DisallowCalling a tutti gli utenti dell'organizzazione che usano Teams in un ambiente virtualizzato.

[**Criteri riunione**](meeting-policies-overview.md): Teams include i criteri riunione AllOff predefiniti, in cui tutte le funzionalità per le riunioni sono disattivate. Assegnare il criterio AllOff a tutti gli utenti dell'organizzazione che usano Teams in un ambiente virtualizzato.

#### <a name="assign-policies-using-the-microsoft-teams-admin-center"></a>Assegnare criteri con l'interfaccia di amministrazione di Microsoft Teams

Per assegnare i criteri di chiamata DisallowCalling e AllOff a un utente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti**.
2. Seleziona l'utente selezionando a sinistra del nome utente e quindi seleziona **Modifica impostazioni**.
3. Procedere come segue:

    a.  In **Criteri per le chiamate** seleziona **DisallowCalling**.

    b.  In **Criteri riunione** selezionare **AllOff**.

4. Selezionare **Applica**.

Per assegnare un criterio a più utenti contemporaneamente:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi cercare gli utenti o filtrare la visualizzazione per mostrare gli utenti desiderati.
2. Nella colonna **&#x2713;** (segno di spunta) selezionare gli utenti. Per selezionare tutti gli utenti, selezionare il &#x2713; (segno di spunta) nella parte superiore della tabella.
3. Seleziona **Modifica impostazioni**, apporta le modifiche desiderate e quindi seleziona **Applica**.

In alternativa, è anche possibile eseguire le operazioni seguenti:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare al criterio da assegnare. Ad esempio:

    - Vai a **Criteri per le chiamate** **vocali** >  e quindi seleziona **DisallowCalling**.
    - Passare a **Criteri riunione riunioni** >  e quindi selezionare **AllOff**.

2. Scegliere **Gestisci utenti**.
3. Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi selezionare **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.
4. Dopo aver aggiunto tutti gli utenti, selezionare **Salva**.

#### <a name="assign-policies-using-powershell"></a>Assegnare criteri con PowerShell

Nell'esempio seguente viene illustrato come utilizzare [Grant-CsTeamsCallingPolicy](/powershell/module/skype/grant-csteamscallingpolicy) per assegnare il criterio di chiamata DisallowCalling a un utente.

```PowerShell
Grant-CsTeamsCallingPolicy -PolicyName DisallowCalling -Identity "user email id"
```

Per ulteriori informazioni sull'utilizzo di PowerShell per gestire i criteri di chiamata, vedi [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy).

Nell'esempio seguente viene illustrato come utilizzare [Grant-CsTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) per assegnare il criterio di riunione AllOff a un utente.

```PowerShell
Grant-CsTeamsMeetingPolicy -PolicyName AllOff -Identity "user email id"
```

Per ulteriori informazioni sull'utilizzo di PowerShell per gestire i criteri delle riunioni, vedi [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).