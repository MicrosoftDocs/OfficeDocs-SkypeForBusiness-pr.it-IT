---
title: Gestire l'accesso basato su turni per i lavoratori Frontline in teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come gestire l'accesso basato su turni in teams per i lavoratori Frontline nell'organizzazione.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 437902136bf72685dabf5bd6359dd6221c7467de
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909470"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Gestire l'accesso basato su turni per i lavoratori Frontline in teams

> [!IMPORTANT]
> Efficace il 30 giugno 2020, Microsoft StaffHub è stato ritirato. Stiamo costruendo funzionalità di StaffHub in Microsoft teams. Oggi teams include l'app turni per la gestione della pianificazione e le funzionalità aggiuntive verranno distribuite nel tempo. StaffHub ha smesso di funzionare per tutti gli utenti il 30 giugno 2020. Chiunque tenti di aprire StaffHub viene visualizzato un messaggio che li indirizza a scaricare teams. Per altre informazioni, vedere [Microsoft StaffHub è stato ritirato](microsoft-staffhub-to-be-retired.md).  

## <a name="overview"></a>Panoramica

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

La presenza in Microsoft teams indica la disponibilità e lo stato corrente di un utente per gli altri utenti. La presenza di lavoratori in prima linea è spesso meno prevedibile rispetto ad altri membri del personale perché le ore lavorative in genere non sono le stesse ogni giorno. Come amministratore, puoi configurare teams per mostrare un set di Stati di presenza basati su turni per gli operatori di Frontline nell'organizzazione per indicare quando sono attivati e spenti il turno.

Questi stati di presenza basati &mdash; ![ su Shift segnano un segno di spunta verde, indica che il turno di spostamento ](../../media/flw-presence-on-shift.png) , il cerchio grigio con x, indica il disattivazione del turno ![ ](../../media/flw-presence-off-shift.png) , ![ il cerchio rosso fisso, indica che occupato occupato ](../../media/flw-presence-busy.png)  &mdash; è separato dal [set predefinito di Stati di presenza](../../presence-admins.md) in teams. Con questi due set di Stati di presenza, puoi configurare esperienze diverse per gli utenti dell'organizzazione in base al loro ruolo.

Con l'accesso basato su turni, puoi gestire l'accesso ai team quando i lavoratori Frontline sono spenti. Ad esempio, puoi impostare teams per visualizzare un messaggio che i dipendenti Frontline devono riconoscere prima di poter usare i team quando non hanno un turno programmato.  

## <a name="scenario"></a>Scenario

Ecco un esempio di come l'organizzazione può gestire l'accesso basato su turni.

I dipendenti della prima linea dell'organizzazione devono essere pagati solo per ore lavorative su un turno che il loro manager ha programmato e approvato. Non dovrebbero essere pagati per il tempo trascorso lavorando all'esterno di un turno programmato, che include l'uso dell'app teams. Si configura un messaggio personalizzato che indica che "il tempo necessario per i team quando il turno di disattivazione non viene conteggiato per le ore da pagare", che viene visualizzato quando i dipendenti in prima linea provano ad accedere ai team durante il turno. Se si sceglie di usare teams, si fa clic su **Accetto** con la consapevolezza che non verranno pagati per questa volta.

Gli addetti alle informazioni sono anche dipendenti dell'organizzazione che hanno salariato e che non lavorano in turni. Puoi configurare i tuoi Information Worker per usare gli Stati di presenza predefiniti in teams mentre conferivi la presenza basata sul turno dei lavoratori Frontline.

## <a name="shift-based-presence-states"></a>Stati di presenza basati su Shift

Ecco gli Stati di presenza basati su turni.

|App configurata |Utente configurato  |Altre informazioni  |
|---------|---------|---------|
|![Segno di spunta verde fisso, indica il turno](../../media/flw-presence-on-shift.png) In turno     |         |Impostato automaticamente all'inizio di un turno         |
|![Cerchio grigio con x, indica OFF Shift](../../media/flw-presence-off-shift.png) Fuori turno     |         |Impostato automaticamente alla fine di un turno         |
|![Cerchio rosso pieno, indica Non disponibile](../../media/flw-presence-busy.png) Non disponibile      | ![Cerchio rosso pieno, indica Non disponibile](../../media/flw-presence-busy.png) Non disponibile         |Impostare automaticamente. Può essere impostato anche manualmente quando il lavoratore Frontline è in turno.|

## <a name="off-shift-access-to-teams"></a>Off Shift Access to Teams

Questa funzionalità consente di gestire l'accesso ai team quando i lavoratori Frontline sono spenti. Puoi impostare teams in grado di visualizzare un messaggio per i lavoratori in prima linea se accedono ai team quando si disattiva il turno. I lavoratori Frontline devono fare clic su **Accetto** per riconoscere il messaggio prima che possano usare teams.

È possibile usare il messaggio predefinito, scegliere da un set di messaggi predefiniti oppure personalizzare il messaggio per visualizzare il testo desiderato. Ecco il messaggio predefinito:

![Screenshot del messaggio predefinito](../../media/shifts-presence-message.png)

È anche possibile impostare la frequenza quando il messaggio viene visualizzato e impostare un periodo di tolleranza tra la fine del primo turno o l'ultimo turno e quando l'accesso ai team è limitato.

## <a name="manage-shift-based-access"></a>Gestire l'accesso basato su turni

Come amministratore, puoi usare i criteri per controllare la presenza basata su turni per i lavoratori Frontline nell'organizzazione. Per gestire questi criteri, usare i cmdlet di PowerShell seguenti:

- [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

Utilizzare il cmdlet New-CsTeamsShiftsPolicy per creare un nuovo criterio, impostare le impostazioni dei criteri desiderate e quindi utilizzare il cmdlet Grant-CsTeamsShiftsPolicy per assegnare i criteri agli utenti.

Ecco alcuni esempi. Per informazioni dettagliate su ogni impostazione e parametro del criterio, incluso l'elenco dei messaggi predefiniti fuori turno da cui è possibile scegliere, vedere [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-1"></a>Esempio 1

In questo esempio creiamo un nuovo criterio denominato off Shift teams Access default Message. In questo criterio viene attivata la presenza basata su maiuscole e viene visualizzato il messaggio predefinito ogni volta che un utente a cui è assegnato questo criterio accede ai team quando è disattivato. L'utente può usare teams quando è disattivato se accetta il messaggio e il periodo di tolleranza tra la fine del primo turno o l'ultimo turno e quando l'accesso è limitato è di 10 minuti.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Usa il parametro **ShiftNoticeMessageType** per impostare il messaggio che vuoi visualizzare. Per visualizzare un elenco dei messaggi predefiniti che è possibile scegliere per questo parametro, vedere [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-2"></a>Esempio 2 

In questo esempio creiamo un nuovo criterio denominato off Shift teams Access Message Custom. In questo criterio viene attivata la presenza basata su turni e viene visualizzato un messaggio personalizzato ogni volta che un utente a cui viene assegnato questo criterio accede ai team quando è disattivato. L'utente può usare teams quando è disattivato se accetta il messaggio e il periodo di tolleranza tra la fine del primo turno o l'ultimo turno e quando l'accesso è limitato è di 15 minuti.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Usa il parametro **ShiftNoticeMessageType** per impostare il messaggio che vuoi visualizzare. Per altre informazioni, vedere [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-3"></a>Esempio 3

In questo esempio creiamo un nuovo criterio denominato off Shift teams Access Message1. In questo criterio viene attivata la presenza basata su turni e viene visualizzato il messaggio predefinito seguente ogni volta che un utente a cui viene assegnato questo criterio accede ai team quando non è disponibile.

  "Il proprio datore di lavoro non autorizza o approva l'uso della rete, delle applicazioni, dei sistemi o degli strumenti da parte di dipendenti non esenti o orari durante le ore non lavorative. Accettando, riconosci che l'uso di teams durante il disorientamento non è autorizzato e non sarai risarcito ". 

L'utente può usare i team quando si disattiva il turno se accetta il messaggio e il periodo di tolleranza tra la fine del primo turno o l'ultimo turno e quando l'accesso è limitato è di tre minuti.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Usa il parametro **ShiftNoticeMessageType** per impostare il messaggio che vuoi visualizzare. Per visualizzare un elenco dei messaggi predefiniti che è possibile scegliere per questo parametro, vedere [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy).

### <a name="example-4"></a>Esempio 4

In questo esempio, assegniamo un criterio denominato off Shift teams Access Message Custom a un utente denominato remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Argomenti correlati

- [Gestire l'app Turni per l'organizzazione in Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Panoramica di PowerShell per Teams](../../teams-powershell-overview.md)
