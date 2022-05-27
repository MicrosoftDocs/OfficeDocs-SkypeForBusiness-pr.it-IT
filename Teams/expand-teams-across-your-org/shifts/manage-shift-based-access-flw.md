---
title: Gestire l'accesso basato sui turni per gli operatori in prima linea in Teams
author: SerdarSoysal
ms.author: serdars
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come gestire l'accesso basato sui turni in Teams per gli operatori in prima linea nell'organizzazione.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9cb488dfb95647079b51269059ee5c0b120cb9cc
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65675218"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Gestire l'accesso basato sui turni per gli operatori in prima linea in Teams
## <a name="overview"></a>Panoramica

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

La presenza in Microsoft Teams indica ad altri utenti la disponibilità corrente e lo stato di un utente. La presenza di personale in prima linea è spesso meno prevedibile rispetto ad altri dipendenti, in quanto il loro orario di lavoro in genere non è identico ogni giorno. Gli amministratori possono configurare Teams in modo che mostrino un set di stati presenza basati sui turni per gli operatori in prima linea dell'organizzazione per indicare quando si trovano su e fuori turno.

Questi stati&mdash;![presenza basati su turno Segno di spunta verde fisso indica Al turno.](../../media/flw-presence-on-shift.png) **In MAIUSC**, ![cerchio grigio con x indica Disattivato turno.](../../media/flw-presence-off-shift.png) **Disattivato maiusc**, ![cerchio rosso fisso, indica che](../../media/flw-presence-busy.png)&mdash; **occupato è separato** dal [set predefinito di stati presenza](../../presence-admins.md) in Teams. Con questi due set di stati presenza, è possibile configurare esperienze diverse per gli utenti dell'organizzazione in base al loro ruolo.

Con l'accesso basato sui turni, è possibile gestire l'accesso ai Teams quando i dipendenti in prima linea sono fuori turno. Ad esempio, è possibile impostare Teams in modo da visualizzare un messaggio che i lavoratori in prima linea devono confermare prima di poter usare Teams quando non si trovano in un turno pianificato.  

## <a name="scenario"></a>Scenario

Ecco un esempio di come l'organizzazione può gestire l'accesso basato sui turni.

Nell'organizzazione sono presenti personale in prima linea che deve essere pagato solo per le ore lavorate su un turno pianificato e approvato dal responsabile. Non devono essere pagati per il tempo trascorso al di fuori di un turno pianificato, incluso l'uso dell'app Teams. È stato impostato un messaggio personalizzato che indica che il tempo trascorso Teams quando è fuori turno non viene conteggiato per le ore di pagabilità", che viene visualizzato quando i lavoratori in prima linea tentano di accedere a Teams quando si disattiva il turno. Se sceglie di usare Teams, fa clic su **Accetto**, accettando che non verrà pagato per questo periodo.

Ci sono anche information worker dell'organizzazione che sono salariati e che non lavorano a turni. È possibile configurare gli information worker in modo da usare gli stati presenza predefiniti in Teams, fornendo al contempo la presenza basata sui turni dei dipendenti in prima linea.

## <a name="shift-based-presence-states"></a>Stati presenza basati su maiusc

Ecco gli stati presenza basati su turno.

|App configurata |Utente configurato  |Altre informazioni  |
|---------|---------|---------|
|![Segno di spunta verde fisso, indica Al turno.](../../media/flw-presence-on-shift.png) In turno     |         |Impostazione automatica all'inizio di un turno         |
|![Cerchio grigio con x, indica Disattivato maiusc](../../media/flw-presence-off-shift.png) Fuori turno     |         |Impostazione automatica alla fine di un turno         |
|![Cerchio rosso pieno, indica Non disponibile.](../../media/flw-presence-busy.png) Non disponibile      | ![Cerchio rosso pieno, indica Non disponibile](../../media/flw-presence-busy.png) Non disponibile         |Impostato automaticamente. Può anche essere impostato manualmente quando il frontline worker è in turno.|

## <a name="off-shift-access-to-teams"></a>Off shift access to Teams

Questa funzionalità consente di gestire l'accesso a Teams quando i dipendenti in prima linea sono fuori turno. È possibile impostare Teams in modo da visualizzare un messaggio agli operatori in prima linea se accedono Teams quando si disattiva il turno. I frontline worker devono fare clic su **Accetto** per confermare il messaggio prima di poter usare Teams.

È possibile usare il messaggio predefinito, scegliere da un set di messaggi predefiniti o personalizzare il messaggio in modo da visualizzare il testo desiderato. Ecco il messaggio predefinito:

![Screenshot del messaggio predefinito.](../../media/shifts-presence-message.png)

È anche possibile impostare la frequenza quando viene visualizzato il messaggio e impostare un periodo di tolleranza tra l'inizio o la fine del primo turno e quando l'accesso a Teams è limitato.

## <a name="manage-shift-based-access"></a>Gestire l'accesso in base ai turni

Gli amministratori usano i criteri per controllare la presenza basata sui turni per gli operatori in prima linea nell'organizzazione. Per gestire questi criteri, usare i cmdlet di PowerShell seguenti:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

Usare il cmdlet New-CsTeamsShiftsPolicy per creare un nuovo criterio, impostare le impostazioni desiderate e quindi usare il cmdlet Grant-CsTeamsShiftsPolicy per assegnare il criterio agli utenti.

Ecco alcuni esempi. Per informazioni dettagliate su ogni impostazione e parametro dei criteri, incluso l'elenco dei messaggi disattivati predefiniti tra cui è possibile scegliere, vedere [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-1"></a>Esempio 1

In questo esempio viene creato un nuovo criterio denominato Off Shift Teams Access Default Message. In questo criterio la presenza basata su turno è attivata e il messaggio predefinito viene visualizzato ogni volta che un utente a cui è assegnato questo criterio accede Teams quando non è attivo maiusc. L'utente può usare Teams quando è disattivato il turno se accetta il messaggio e il periodo di tolleranza tra l'inizio o la fine del primo turno e quando l'accesso è limitato è di 10 minuti.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Usare il parametro **ShiftNoticeMessageType** per impostare il messaggio da visualizzare. Per visualizzare un elenco dei messaggi predefiniti tra cui è possibile scegliere per questo parametro, vedere [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-2"></a>Esempio 2 

In questo esempio viene creato un nuovo criterio denominato Off Shift Teams Access Custom Message. In questo criterio, la presenza basata su turno è attivata e viene visualizzato un messaggio personalizzato ogni volta che un utente a cui è assegnato questo criterio accede Teams quando non è attivo. L'utente può usare Teams quando è disattivato il turno se accetta il messaggio e il periodo di tolleranza tra l'inizio o la fine del primo turno e quando l'accesso è limitato è di 15 minuti.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Usare il parametro **ShiftNoticeMessageType** per impostare il messaggio da visualizzare. Per ulteriori informazioni, vedi [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-3"></a>Esempio 3

In questo esempio viene creato un nuovo criterio denominato Off Shift Teams Access Message1. In questo criterio, la presenza basata su turno è attivata e viene visualizzato il messaggio predefinito seguente ogni volta che un utente a cui è assegnato questo criterio accede Teams quando non è attivo.

  "Il datore di lavoro non autorizza o approva l'uso della rete, delle applicazioni, dei sistemi o degli strumenti da parte di dipendenti non esenti o orari durante i loro orari non lavorativi. Accettando, l'utente riconosce che l'uso di Teams mentre è fuori turno non è autorizzato e non sarà risarcito". 

L'utente può usare Teams quando è disattivato il turno se accetta il messaggio e il periodo di tolleranza tra l'inizio o la fine del primo turno e quando l'accesso è limitato è di tre minuti.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Usare il parametro **ShiftNoticeMessageType** per impostare il messaggio da visualizzare. Per visualizzare un elenco dei messaggi predefiniti tra cui è possibile scegliere per questo parametro, vedere [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-4"></a>Esempio 4

In questo esempio viene assegnato un criterio denominato Off Shift Teams Access Custom Message a un utente denominato remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Argomenti correlati

- [Gestire l'app Turni per l'organizzazione in Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Panoramica di PowerShell per Teams](../../teams-powershell-overview.md)