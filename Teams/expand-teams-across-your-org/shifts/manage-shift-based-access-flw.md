---
title: Gestire l'accesso in base ai turni per i frontline worker in Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come gestire l'accesso basato su turni in Teams per Frontline Workers nell'organizzazione.
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
appliesto:
- Microsoft Teams
ms.openlocfilehash: c69f5678b2a3884f52dd3dc676fce21e2ee67f4f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092544"
---
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Gestire l'accesso in base ai turni per i frontline worker in Teams

> [!IMPORTANT]
> A partire dal 30 giugno 2020, Microsoft StaffHub è stato ritirato. Stiamo creando funzionalità di StaffHub in Microsoft Teams. Al momento, Teams include l’app Turni per la gestione delle pianificazioni. Altre funzionalità verranno implementate nel corso del tempo. StaffHub ha smesso di funzionare per tutti gli utenti il 30 giugno 2020. Chiunque provi ad aprire StaffHub visualizza un messaggio che invita a scaricare Teams. Per altre informazioni, vedere [Microsoft StaffHub è stato ritirato](microsoft-staffhub-to-be-retired.md).  

## <a name="overview"></a>Panoramica

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

Presenza in Microsoft Teams indica la disponibilità e lo stato correnti di un utente per gli altri utenti. La presenza di Frontline Workers è spesso meno prevedibile rispetto ad altri dipendenti, in quanto le ore lavorative non sono in genere uguali ogni giorno. Gli amministratori possono configurare Teams in modo che mostri un set di stati di presenza basati su turni per i Frontline Worker dell'organizzazione per indicare quando sono in turno o fuori turno.

Questi stati di presenza basati sul turno indicano un segno di spunta verde a tinta unita, che indica Il turno al turno, il cerchio grigio con x, indica Off &mdash; ![ shift Off ](../../media/flw-presence-on-shift.png) shift , solid red ![ ](../../media/flw-presence-off-shift.png)  ![ circle, indicates Busy ](../../media/flw-presence-busy.png)  &mdash; [](../../presence-admins.md) are separate from the default set of presence states in Teams. Con questi due set di stati di presenza, è possibile configurare esperienze diverse per le persone dell'organizzazione in base al loro ruolo.

Con l'accesso basato su turni, è possibile gestire l'accesso a Teams quando i Frontline Workers sono fuori turno. Ad esempio, è possibile impostare Teams in modo che venga visualizzato un messaggio che i frontline worker devono confermare prima di poter usare Teams quando non sono in un turno pianificato.  

## <a name="scenario"></a>Scenario

Ecco un esempio di come l'organizzazione può gestire l'accesso basato su turni.

Nell'organizzazione sono presenti lavoratori frontline che devono essere pagati solo per le ore in cui lavorano in un turno programmato e approvato dal responsabile. Non devono essere pagati per il tempo trascorso al di fuori di un turno programmato, che include l'uso dell'app Teams. È stato impostato un messaggio personalizzato che indica che il tempo a cui si è in servizio Teams quando si è fuori turno non viene conteggiato per le ore pagabili, che viene visualizzato quando i frontline worker provano ad accedere a Teams quando si è fuori turno. Se scelgono di usare Teams, fanno clic **su** Accetto con la comprensione che non verranno pagati per questo periodo.

Nell'organizzazione sono presenti anche information worker con stipendi e che non lavorano a turni. È possibile configurare gli information worker in modo che usino gli stati di presenza predefiniti in Teams, fornendo allo stesso tempo la presenza basata sui turni dei Frontline Workers.

## <a name="shift-based-presence-states"></a>Stati presenza basati su turni

Ecco gli stati di presenza basati sui turni.

|App configurata |Utente configurato  |Altre informazioni  |
|---------|---------|---------|
|![Segno di spunta verde a tinta unita, indica Al turno](../../media/flw-presence-on-shift.png) A turno     |         |Impostazione automatica all'inizio di un turno         |
|![Cerchio grigio con x, indica Spostamento disattivato](../../media/flw-presence-off-shift.png) Turno disattivato     |         |Impostazione automatica alla fine di un turno         |
|![Cerchio rosso pieno, indica Non disponibile](../../media/flw-presence-busy.png) Non disponibile      | ![Cerchio rosso pieno, indica Non disponibile](../../media/flw-presence-busy.png) Non disponibile         |Imposta automaticamente. Può anche essere impostato manualmente quando il frontline worker è in turno.|

## <a name="off-shift-access-to-teams"></a>Disattivare l'accesso turno a Teams

Questa funzionalità consente di gestire l'accesso a Teams quando i Frontline Workers sono fuori turno. È possibile impostare Teams in modo da visualizzare un messaggio su Frontline Workers se accedono a Teams quando si è fuori turno. I lavoratori in prima linea devono fare **clic su** Accetto per confermare il messaggio prima di poter usare Teams.

È possibile usare il messaggio predefinito, scegliere tra un set di messaggi predefiniti o personalizzare il messaggio in modo da visualizzare il testo desiderato. Ecco il messaggio predefinito:

![Screenshot del messaggio predefinito](../../media/shifts-presence-message.png)

È anche possibile impostare la frequenza di visualizzazione del messaggio e impostare un periodo di tolleranza tra l'inizio del primo turno o l'ultimo turno e il momento in cui l'accesso a Teams è limitato.

## <a name="manage-shift-based-access"></a>Gestire l'accesso in base al turno

Gli amministratori usano i criteri per controllare la presenza basata sui turni per i frontline worker dell'organizzazione. Per gestire questi criteri, usare i cmdlet di PowerShell seguenti:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy)

Usare il cmdlet New-CsTeamsShiftsPolicy per creare un nuovo criterio, impostare le impostazioni dei criteri desiderate e quindi usare il cmdlet Grant-CsTeamsShiftsPolicy per assegnare il criterio agli utenti.

Ecco alcuni esempi. Per informazioni dettagliate su ogni impostazione e parametro dei criteri, incluso l'elenco dei messaggi fuori turno predefiniti tra cui è possibile scegliere, vedere [New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-1"></a>Esempio 1

In questo esempio viene creato un nuovo criterio denominato Off Shift Teams Access Default Message. In questo criterio la presenza basata sui turni è attivata e il messaggio predefinito viene visualizzato ogni volta che un utente a cui è assegnato questo criterio accede a Teams quando non è in turno. L'utente può usare Teams quando è disattivato il turno se accetta il messaggio e il periodo di tolleranza tra l'inizio del primo turno o l'ultimo turno e il momento in cui l'accesso è limitato è di 10 minuti.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Usare il **parametro ShiftNoticeMessageType** per impostare il messaggio da visualizzare. Per visualizzare un elenco dei messaggi predefiniti tra cui è possibile scegliere per questo parametro, vedere [New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-2"></a>Esempio 2 

In questo esempio viene creato un nuovo criterio denominato Off Shift Teams Access Custom Message. In questo criterio la presenza basata sui turni è attivata e viene visualizzato un messaggio personalizzato ogni volta che un utente a cui è assegnato questo criterio accede a Teams quando non è in turno. L'utente può usare Teams quando è disattivato il turno se accetta il messaggio e il periodo di tolleranza tra l'inizio del primo turno o l'ultimo turno e il momento in cui l'accesso è limitato è di 15 minuti.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Usare il **parametro ShiftNoticeMessageType** per impostare il messaggio da visualizzare. Per altre informazioni, vedere [New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-3"></a>Esempio 3

In questo esempio viene creato un nuovo criterio denominato Off Shift Teams Access Message1. In questo criterio la presenza basata sul turno è attivata e il messaggio predefinito seguente viene visualizzato ogni volta che un utente a cui è assegnato questo criterio accede a Teams quando non è in turno.

  "Il datore di lavoro non autorizza o approva l'uso della rete, delle applicazioni, dei sistemi o degli strumenti da parte di dipendenti non esenti o orari durante le ore non lavorative. Accettando, l'utente riconosce che l'uso di Teams durante il turno non è autorizzato e che non verrà risarcito". 

L'utente può usare Teams quando si è fuori turno se accetta il messaggio e il periodo di tolleranza tra l'inizio del primo turno o l'ultimo turno e il momento in cui l'accesso è limitato è di tre minuti.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Usare il **parametro ShiftNoticeMessageType** per impostare il messaggio da visualizzare. Per visualizzare un elenco dei messaggi predefiniti tra cui è possibile scegliere per questo parametro, vedere [New-CsTeamsShiftsPolicy.](/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-4"></a>Esempio 4

In questo esempio viene assegnato un criterio denominato Off Shift Teams Access Custom Message a un utente denominato remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Argomenti correlati

- [Gestire l'app Turni per l'organizzazione in Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Panoramica di PowerShell per Teams](../../teams-powershell-overview.md)