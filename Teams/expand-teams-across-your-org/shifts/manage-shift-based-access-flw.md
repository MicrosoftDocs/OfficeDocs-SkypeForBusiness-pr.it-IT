---
title: Gestire l'accesso a turni per i lavoratori in prima linea in Teams
author: HowlinWolf-92
ms.author: v-mahoffman
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come gestire l'accesso a turni in Teams per i frontline worker dell'organizzazione.
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: 708ce6158cd799bed506751006d94679eedcd950
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/08/2021
ms.locfileid: "60842598"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Gestire l'accesso a turni per i lavoratori in prima linea in Teams

> [!IMPORTANT]
> A partire dal 30 giugno 2020, Microsoft StaffHub è stato ritirato. Stiamo creando funzionalità di StaffHub in Microsoft Teams. Al momento, Teams include l’app Turni per la gestione delle pianificazioni. Altre funzionalità verranno implementate nel corso del tempo. StaffHub ha smesso di funzionare per tutti gli utenti il 30 giugno 2020. Chiunque provi ad aprire StaffHub visualizza un messaggio che invita a scaricare Teams. Per altre informazioni, vedere [Microsoft StaffHub è stato ritirato](microsoft-staffhub-to-be-retired.md).  

## <a name="overview"></a>Panoramica

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

La presenza Microsoft Teams indica la disponibilità e lo stato correnti di un utente per gli altri utenti. La presenza di lavoratori in prima linea è spesso meno prevedibile rispetto ad altri dipendenti, in quanto le ore lavorative in genere non sono uguali ogni giorno. Gli amministratori possono configurare il Teams per visualizzare un set di stati di presenza basati su turni per i lavoratori in prima linea dell'organizzazione per indicare quando sono in turno o fuori turno.

Questi stati di presenza basati sul turno indicano un segno di spunta verde a tinta &mdash; ![ unita, che indica Il turno.](../../media/flw-presence-on-shift.png) **In turno**, ![ cerchio grigio con x, indica Turno disattivato.](../../media/flw-presence-off-shift.png) **Fuori turno**, ![ cerchio rosso a tinta unita, indica che Occupato è separato dal set predefinito di stati presenza in ](../../media/flw-presence-busy.png)  &mdash; Teams. [](../../presence-admins.md) Con questi due set di stati di presenza, è possibile configurare esperienze diverse per le persone dell'organizzazione in base al loro ruolo.

Con l'accesso a turni, è possibile gestire l'accesso Teams quando i lavoratori in prima linea sono fuori turno. Ad esempio, è possibile impostare Teams visualizzare un messaggio che i lavoratori in prima linea devono confermare prima di poter usare Teams quando non sono in un turno programmato.  

## <a name="scenario"></a>Scenario

Ecco un esempio di come l'organizzazione può gestire l'accesso basato su turni.

Nell'organizzazione sono presenti lavoratori in prima linea che devono essere pagati solo per le ore in cui lavorano in un turno programmato e approvato dal responsabile. Non devono essere retribuiti per il tempo trascorso al di fuori di un turno programmato, che include l'uso dell'app Teams lavoro. È stato configurato un messaggio personalizzato che indica che il tempo a Teams quando si è fuori turno non viene conteggiato per le ore pagabili, che viene visualizzato quando i lavoratori in prima linea provano ad accedere Teams quando si è fuori turno. Se scelgono di usare Teams,  fanno clic su Accetto con la comprensione che non verranno pagati per questo periodo.

Nell'organizzazione sono presenti anche information worker con stipendi e che non lavorano a turni. È possibile configurare gli information worker in modo che usino gli stati di presenza predefiniti in Teams, fornendo al contempo ai dipendenti in prima linea la presenza basata sul turno.

## <a name="shift-based-presence-states"></a>Stati presenza basati sui turni

Ecco gli stati di presenza basati sui turni.

|App configurata |Utente configurato  |Altre informazioni  |
|---------|---------|---------|
|![Segno di spunta verde a tinta unita, indica Al turno.](../../media/flw-presence-on-shift.png) A turno     |         |Impostazione automatica all'inizio di un turno         |
|![Cerchio grigio con x, indica Spostamento disattivato](../../media/flw-presence-off-shift.png) Turno disattivato     |         |Impostazione automatica alla fine di un turno         |
|![Cerchio rosso pieno, indica Non disponibile.](../../media/flw-presence-busy.png) Non disponibile      | ![Cerchio rosso pieno, indica Non disponibile](../../media/flw-presence-busy.png) Non disponibile         |Imposta automaticamente. Può anche essere impostato manualmente quando il lavoratore in prima linea è in turno.|

## <a name="off-shift-access-to-teams"></a>Disattivare l'accesso a Teams

Questa caratteristica consente di gestire l'accesso ai Teams quando i lavoratori in prima linea sono fuori turno. È possibile impostare Teams visualizzare un messaggio ai lavoratori in prima linea se accedono Teams fuori turno. I dipendenti in prima linea devono fare **clic su** Accetto per confermare il messaggio prima che possano usare Teams.

È possibile usare il messaggio predefinito, scegliere tra un set di messaggi predefiniti o personalizzare il messaggio in modo da visualizzare il testo desiderato. Ecco il messaggio predefinito:

![Screenshot del messaggio predefinito.](../../media/shifts-presence-message.png)

È anche possibile impostare la frequenza di visualizzazione del messaggio e impostare un periodo di tolleranza tra l'inizio del primo turno o l'ultimo turno e il momento in cui l'accesso a Teams è limitato.

## <a name="manage-shift-based-access"></a>Gestire l'accesso in base al turno

Gli amministratori usano i criteri per controllare la presenza basata sui turni per i lavoratori in prima linea nell'organizzazione. Per gestire questi criteri, usare i cmdlet di PowerShell seguenti:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

Usare il cmdlet New-CsTeamsShiftsPolicy per creare un nuovo criterio, impostare le impostazioni dei criteri desiderate e quindi usare il cmdlet Grant-CsTeamsShiftsPolicy per assegnare il criterio agli utenti.

Ecco alcuni esempi. Per informazioni dettagliate su ogni impostazione e parametro dei criteri, incluso l'elenco dei messaggi fuori turno predefiniti tra cui è possibile scegliere, vedere [New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-1"></a>Esempio 1

In questo esempio viene creato un nuovo criterio denominato Fuori turno Teams messaggio predefinito di Access. In questo criterio la presenza basata sui turni è attivata e il messaggio predefinito viene visualizzato ogni volta che un utente a cui è assegnato questo criterio accede Teams quando è disattivato. L'utente può usare Teams turno disattivato se accetta il messaggio e il periodo di tolleranza tra l'inizio del primo turno o l'ultimo turno e il momento in cui l'accesso è limitato è di 10 minuti.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Usare il **parametro ShiftNoticeMessageType** per impostare il messaggio da visualizzare. Per visualizzare un elenco dei messaggi predefiniti tra cui è possibile scegliere per questo parametro, vedere [New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-2"></a>Esempio 2 

In questo esempio viene creato un nuovo criterio denominato Fuori turno Teams messaggio personalizzato di Access. In questo criterio la presenza basata sui turni è attivata e viene visualizzato un messaggio personalizzato ogni volta che un utente a cui è assegnato questo criterio accede Teams quando è disattivato. L'utente può usare Teams turno disattivato se accetta il messaggio e il periodo di tolleranza tra l'inizio del primo turno o l'ultimo turno e il momento in cui l'accesso è limitato è di 15 minuti.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Usare il **parametro ShiftNoticeMessageType** per impostare il messaggio da visualizzare. Per altre informazioni, vedere [New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-3"></a>Esempio 3

In questo esempio viene creato un nuovo criterio denominato Off SHIFT Teams Access Message1. In questo criterio la presenza basata sui turni è attivata e il messaggio predefinito seguente viene visualizzato ogni volta che un utente a cui è assegnato questo criterio accede Teams quando si è fuori turno.

  "Il datore di lavoro non autorizza o approva l'uso della rete, delle applicazioni, dei sistemi o degli strumenti da parte di dipendenti non esenti o orari durante le ore non lavorative. Accettando, l'utente riconosce che l'uso Teams durante il turno non è autorizzato e che non si riceverà un compenso". 

L'utente può usare Teams turno di inalazione se accetta il messaggio e il periodo di tolleranza tra l'inizio del primo turno o l'ultimo turno e il momento in cui l'accesso è limitato è di tre minuti.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Usare il **parametro ShiftNoticeMessageType** per impostare il messaggio da visualizzare. Per visualizzare un elenco dei messaggi predefiniti tra cui è possibile scegliere per questo parametro, vedere [New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-4"></a>Esempio 4

In questo esempio viene assegnato un criterio denominato Fuori turno Teams messaggio personalizzato di Access a un utente denominato remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Argomenti correlati

- [Gestire l'app Turni per l'organizzazione in Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Panoramica di PowerShell per Teams](../../teams-powershell-overview.md)