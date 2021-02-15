---
title: Gestire l'accesso basato su turno per i dipendenti in prima linea in Teams
author: cichur
ms.author: v-cichur
ms.reviewer: aaku
manager: serdars
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
description: Informazioni su come gestire l'accesso basato su turno in Teams per gli operatori in prima linea nell'organizzazione.
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
# <a name="manage-shift-based-access-for-frontline-workers-in-teams"></a>Gestire l'accesso basato su turno per i dipendenti in prima linea in Teams

> [!IMPORTANT]
> Microsoft StaffHub è stato ritirato il 30 giugno 2020. Stiamo creando funzionalità di StaffHub in Microsoft Teams. Oggi, Teams include l'app Turni per la gestione della pianificazione e altre funzionalità verranno implementazioni nel tempo. StaffHub ha smesso di funzionare per tutti gli utenti il 30 giugno 2020. Chiunque tenti di aprire StaffHub viene visualizzato un messaggio che li indirizza a scaricare Teams. Per altre informazioni, vedere [Microsoft StaffHub è stato ritirato.](microsoft-staffhub-to-be-retired.md)  

## <a name="overview"></a>Panoramica

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

La presenza in Microsoft Teams indica la disponibilità e lo stato correnti di un utente per gli altri utenti. La presenza dei dipendenti in prima linea è spesso meno prevedibile rispetto agli altri membri del personale perché le ore lavorative in genere non sono le stesse ogni giorno. Come amministratore, puoi configurare Teams in modo da visualizzare un set di stati presenza basati su turno per gli operatori sul campo nell'organizzazione per indicare quando sono in turno o fuori sede.

Questi stati presenza basati su turni, contrassegnati dal segno di spunta verde a tinta unita, indicano A turno su turno , Cerchio grigio con x, Indica Off Shift Off , Solid Red Circle, indica che Busy sono separati dal set predefinito di stati presenza &mdash; ![ ](../../media/flw-presence-on-shift.png)  ![ in ](../../media/flw-presence-off-shift.png)  ![ ](../../media/flw-presence-busy.png)  &mdash; Teams. [](../../presence-admins.md) Con questi due set di stati presenza, è possibile configurare esperienze diverse per gli utenti dell'organizzazione in base al loro ruolo.

Con l'accesso basato su turno, puoi gestire l'accesso a Teams quando gli operatori in prima linea sono fuori turno. Ad esempio, è possibile impostare Teams in modo da visualizzare un messaggio che gli operatori in prima linea devono riconoscere prima di poter usare Teams quando non sono in un turno pianificato.  

## <a name="scenario"></a>Scenario

Ecco un esempio di come l'organizzazione può gestire l'accesso basato su turno.

Gli operatori sul campo all'interno dell'organizzazione devono essere pagati solo per le ore in cui lavorano con un turno pianificato e approvato dal loro responsabile. Non devono essere pagati per il tempo trascorso al di fuori di un turno pianificato, incluso l'uso dell'app Teams. Puoi configurare un messaggio personalizzato che dice "Il tuo tempo in Teams quando è fuori turno non verrà conteggiato per le ore pagabili", che viene visualizzato quando gli operatori sul campo provano ad accedere a Teams quando sono fuori turno. Se scelgono di usare Teams, fanno clic **su Accetto** con la conferma che non verranno pagati per questo periodo.

Nell'organizzazione sono presenti anche information worker a pagamento e che non lavorano a turni. È possibile configurare gli information worker in modo che usino gli stati presenza predefiniti in Teams, fornendo allo stesso tempo la presenza basata sul turno degli information worker.

## <a name="shift-based-presence-states"></a>Stati presenza basati su maiusc

Ecco gli stati presenza basati sul turno.

|App configurata |Utente configurato  |Altre informazioni  |
|---------|---------|---------|
|![Segno di spunta verde tinta unita, che indica Il turno](../../media/flw-presence-on-shift.png) A turno     |         |Impostazione automatica all'inizio di un turno         |
|![Cerchio grigio con x, indica turno disattivato](../../media/flw-presence-off-shift.png) Turno non lavorativo     |         |Impostazione automatica alla fine di un turno         |
|![Cerchio rosso pieno, indica Non disponibile](../../media/flw-presence-busy.png) Non disponibile      | ![Cerchio rosso pieno, indica Non disponibile](../../media/flw-presence-busy.png) Non disponibile         |Imposta automaticamente. Può anche essere impostato manualmente quando l'assistente in prima linea è a turno.|

## <a name="off-shift-access-to-teams"></a>Off shift access to Teams

Questa funzione consente di gestire l'accesso a Teams quando gli operatori sul campo sono fuori turno. È possibile impostare Teams in modo da visualizzare un messaggio agli operatori in prima linea se accedono a Teams quando si è fuori turno. Gli operatori in prima linea devono fare **clic su Accetto** per confermare il messaggio prima di poter usare Teams.

È possibile usare il messaggio predefinito, scegliere da un set di messaggi predefiniti o personalizzare il messaggio in modo da visualizzare il testo desiderato. Ecco il messaggio predefinito:

![Screenshot del messaggio predefinito](../../media/shifts-presence-message.png)

È anche possibile impostare la frequenza di visualizzazione del messaggio e un periodo di tolleranza tra l'inizio del primo turno o l'ultimo turno e la data di limitazione dell'accesso a Teams.

## <a name="manage-shift-based-access"></a>Gestire l'accesso basato su turno

Gli amministratori possono usare i criteri per controllare la presenza basata sui turni per gli operatori sul campo nell'organizzazione. Per gestire questi criteri, usare i cmdlet di PowerShell seguenti:

- [New-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)
- [Get-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/get-csteamsshiftspolicy)
- [Set-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/set-csteamsshiftspolicy)
- [Grant-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/grant-csteamsshiftspolicy)
- [Remove-CsTeamsShiftsPolicy](https://docs.microsoft.com/powershell/module/teams/remove-csteamsshiftspolicy)

Usare il cmdlet New-CsTeamsShiftsPolicy per creare un nuovo criterio, impostare le impostazioni desiderate e quindi usare il cmdlet Grant-CsTeamsShiftsPolicy per assegnare il criterio agli utenti.

Ecco alcuni esempi. Per informazioni dettagliate su ogni impostazione e parametro dei criteri, incluso l'elenco dei messaggi fuori turno predefiniti tra cui è possibile scegliere, vedere [New-CsTeamsShiftsPolicy.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-1"></a>Esempio 1

In questo esempio viene creato un nuovo criterio denominato "Off Shift Teams Access Default Message". In questo criterio la presenza basata sui turni è attivata e il messaggio predefinito viene visualizzato ogni volta che un utente a cui è assegnato questo criterio accede a Teams quando si è fuori sede. L'utente può usare Teams quando non ha il turno se accetta il messaggio e il periodo di tolleranza tra l'inizio del primo turno o l'ultimo turno e la data di limitazione dell'accesso è di 10 minuti.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Default Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType DefaultMessage -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 10
```

> [!NOTE]
> Usare il **parametro ShiftNoticeMessageType** per impostare il messaggio da visualizzare. Per visualizzare un elenco dei messaggi predefiniti tra cui scegliere per questo parametro, vedere [New-CsTeamsShiftsPolicy.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-2"></a>Esempio 2 

In questo esempio viene creato un nuovo criterio denominato Messaggio personalizzato di off Shift Teams Access. In questo criterio la presenza basata sui turni è attivata e viene visualizzato un messaggio personalizzato ogni volta che un utente a cui è assegnato questo criterio accede a Teams quando si è fuori sede. L'utente può usare Teams quando non ha il turno se accetta il messaggio e il periodo di tolleranza tra l'inizio del primo turno o l'ultimo turno e la data di limitazione dell'accesso è di 15 minuti.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Custom Message" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType CustomMessage -ShiftNoticeMessageCustom "Your time on Teams when on off shift won't count toward payable hours" -AccessType UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 15
```

> [!NOTE]
> Usare il **parametro ShiftNoticeMessageType** per impostare il messaggio da visualizzare. Per ulteriori informazioni, consulta [New-CsTeamsShiftsPolicy.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-3"></a>Esempio 3

In questo esempio viene creato un nuovo criterio denominato Off Shift Teams Access Message1. In questo criterio la presenza basata su turno è attivata e il seguente messaggio predefinito viene visualizzato ogni volta che un utente a cui è assegnato questo criterio accede a Teams quando non si è in turno.

  "Il datore di lavoro non autorizza o approva l'uso della rete, delle applicazioni, dei sistemi o degli strumenti da parte di dipendenti non esenti o orari durante le ore non lavorative. Accettando, l'utente riconosce che l'uso di Teams durante il turno non è autorizzato e non sarà risarcito". 

L'utente può usare Teams quando non ha il turno se accetta il messaggio e il periodo di tolleranza tra l'inizio del primo turno o l'ultimo turno e la data di limitazione dell'accesso è di tre minuti.  

```powershell
New-CsTeamsShiftsPolicy -Identity "Off Shift Teams Access Message1" -EnableShiftPresence $true -ShiftNoticeFrequency always -ShiftNoticeMessageType Message1 -AccessType  UnrestrictedAccess_TeamsApp -AccessGracePeriodMinutes 3
```

> [!NOTE]
> Usare il **parametro ShiftNoticeMessageType** per impostare il messaggio da visualizzare. Per visualizzare un elenco dei messaggi predefiniti tra cui scegliere per questo parametro, vedere [New-CsTeamsShiftsPolicy.](https://docs.microsoft.com/powershell/module/teams/new-csteamsshiftspolicy)

### <a name="example-4"></a>Esempio 4

In questo esempio viene assegnato un criterio denominato Messaggio personalizzato di Off Shift Teams Access a un utente denominato remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName "Off Shift Teams Access Custom Message"
```

## <a name="related-topics"></a>Argomenti correlati

- [Gestire l'app Turni per l'organizzazione in Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Panoramica di PowerShell per Teams](../../teams-powershell-overview.md)
