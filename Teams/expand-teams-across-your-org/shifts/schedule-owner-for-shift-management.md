---
title: Gestire i proprietari della pianificazione per la gestione dei turni
author: lanachin
ms.author: v-lanachin
ms.reviewer: aaku
manager: samanro
ms.topic: article
audience: admin
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
description: Informazioni su come gestire i proprietari dei turni per la gestione della pianificazione. È possibile impostare un criterio per elevare l'autorizzazione di un membro del team a un proprietario della pianificazione.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 9c0bc75e15439cf5fa7c3989bb0854521a1c45b8
ms.sourcegitcommit: 97c2faab08ec9b8fc9967827883308733ec162ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/13/2021
ms.locfileid: "58235752"
---
# <a name="schedule-owner-for-shift-management"></a>Proprietario pianificazione per la gestione dei turni

## <a name="overview"></a>Panoramica

Proprietario pianificazione è una caratteristica che consente di elevare le autorizzazioni di un membro del team a un proprietario della pianificazione senza rendere il dipendente proprietario del team. Questo significa che il dipendente è autorizzato a gestire la pianificazione del team senza poter modificare altre proprietà del team, ad esempio l'aggiornamento, la modifica o l'eliminazione dei canali del team.

Cosa può fare un utente con autorizzazioni di proprietario della pianificazione?

- Creare, modificare e pubblicare pianificazioni per gestire le assegnazioni dei turni del team.
- Visualizzare e approvare le richieste di turno, incluse le richieste di scambio di turni e turni aperti.
- Gestire le impostazioni in Turni per abilitare determinate funzionalità per il team.
- Visualizzare e modificare la scheda attività del team per elaborare le retribuzioni dei dipendenti.

## <a name="why-schedule-owner"></a>Perché il proprietario della pianificazione?

Senza la caratteristica Proprietario pianificazione, le funzioni aziendali quotidiane potrebbero essere interrotte. Anche se il proprietario del team aiuta a eseguire il team, potrebbe non essere necessariamente il responsabile della pianificazione quotidiana. In questo caso, il trasferimento solo della responsabilità di gestione della pianificazione a un altro membro del team semplifica le operazioni quotidiane all'interno del team ed elimina la confusione di due membri del team con gli stessi privilegi di accesso.

## <a name="scenario"></a>Scenario

Ecco un esempio di come l'organizzazione può usare la caratteristica Pianifica proprietario.

Si lavora in un'organizzazione di grandi dimensioni in cui i responsabili dei reparti segnalano direttamente al responsabile del negozio. Il responsabile del negozio ha più autorità all'interno dell'azienda ed è il proprietario del team in Turni. I responsabili di reparto, invece, vengono aggiunti ai turni solo come membri del team. Anche se i responsabili dei negozi hanno più anzianità rispetto ai responsabili di reparto, è più logico che i responsabili di reparto gestino la pianificazione quotidiana dei dipendenti del team.

*Senza Il proprietario della pianificazione,* i responsabili di reparto devono avere gli stessi privilegi del proprietario del team. Di recente, i responsabili di reparto spostano le informazioni e modificano il nome dei canali, causando complicazioni con il lavoro del responsabile del negozio. Il responsabile del negozio vuole che i responsabili del reparto siano in grado di organizzare le pianificazioni, ma non vuole che possano modificare altri elementi del team, all'esterno dei turni.

*Con Schedule Owner*, i responsabili di reparto possono avere privilegi di pianificazione, senza altri privilegi di proprietario del team.

## <a name="manage-schedule-ownership"></a>Gestire la proprietà della pianificazione

Gli amministratori usano i criteri per controllare la proprietà della gestione della pianificazione nell'organizzazione. Per gestire questi criteri, usare i cmdlet di PowerShell seguenti:

- [New-CsTeamsShiftsPolicy](/powershell/module/teams/new-csteamsshiftspolicy?view=teams-ps)
- [Get-CsTeamsShiftsPolicy](/powershell/module/teams/get-csteamsshiftspolicy?view=teams-ps)
- [Set-CsTeamsShiftsPolicy](/powershell/module/teams/set-csteamsshiftspolicy?view=teams-ps)
- [Grant-CsTeamsShiftsPolicy](/powershell/module/teams/grant-csteamsshiftspolicy?view=teams-ps)
- [Remove-CsTeamsShiftsPolicy](/powershell/module/teams/remove-csteamsshiftspolicy?view=teams-ps)

### <a name="example-1"></a>Esempio 1

In questo caso viene creato un nuovo criterio denominato ScheduleOwnerPolicy con la caratteristica Proprietario pianificazione attivata.

```powershell
New-CsTeamsShiftsPolicy –Identity ScheduleOwnerPolicy  -EnableScheduleOwnerPermissions $true -AccessType UnrestrictedAccess_TeamsApp
```

### <a name="example-2"></a>Esempio 2

In questo esempio viene assegnato un criterio denominato ScheduleOwnerPolicy a un utente denominato remy@contoso.com.

```powershell
Grant-CsTeamsShiftsPolicy -Identity remy@contoso.com -PolicyName ScheduleOwnerPolicy
```

## <a name="related-articles"></a>Articoli correlati

- [Gestire l'app Turni per l'organizzazione in Teams](manage-the-shifts-app-for-your-organization-in-teams.md)
- [Gestire l'accesso a turni per i lavoratori in prima linea in Teams](manage-shift-based-access-flw.md) 
