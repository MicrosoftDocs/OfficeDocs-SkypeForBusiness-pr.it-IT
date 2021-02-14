---
title: Rimuovere dagli utenti il criterio RestrictedAnonymousAccess per le riunioni di Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: cebulnes, anyada
audience: admin
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords: ''
ms.custom: ''
description: Informazioni su come rimuovere i criteri di riunione di Teams RestrictedAnonymousAccess dagli utenti dell'organizzazione.
ms.openlocfilehash: 55385cdd47f6b6c9882f8d4e8dcadc848f13755d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806256"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>Rimuovere dagli utenti il criterio RestrictedAnonymousAccess per le riunioni di Teams

[I criteri di](meeting-policies-in-teams.md) riunione in Microsoft Teams vengono utilizzati per controllare le funzionalità disponibili per i partecipanti alle riunioni pianificate dagli utenti dell'organizzazione. 

Teams include un criterio predefinito denominato RestrictedAnonymousAccess, che contiene impostazioni predefinite che includono la limitazione dell'avvio di una riunione da parte di utenti anonimi. Gli utenti anonimi sono utenti che non sono stati autenticati. Le impostazioni predefinite nel criterio di riunione non possono essere modificate né modificate dagli amministratori.

Questo articolo illustra come usare PowerShell per rimuovere il criterio di riunione RestrictedAnonymousAccess dagli utenti a cui è assegnato questo criterio. Per altre informazioni su come gestire Teams con PowerShell, vedere La panoramica [di Teams su PowerShell.](teams-powershell-overview.md)

## <a name="before-you-start"></a>Prima di iniziare

Installare e connettersi al [modulo PowerShell di Skype for Business.](https://www.microsoft.com/download/details.aspx?id=39366) Per istruzioni dettagliate, vedere Installare [Microsoft Teams PowerShell.](teams-powershell-install.md)

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>Ottenere le assegnazioni dei criteri di riunione di Teams per l'organizzazione

Eseguire la procedura seguente per ottenere le assegnazioni dei criteri di riunione di Teams per l'organizzazione.

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

In questo esempio viene restituito l'output seguente, che indica che a due utenti è assegnato il criterio riunione RestrictedAnonymousAccess.

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>Annullare l'assegnazione dei criteri di riunione RestrictedAnonymous agli utenti

Per rimuovere il criterio di riunione RestrictedAnonymous dagli utenti, è possibile usare il cmdlet [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) se il numero di utenti è limitato (ad esempio meno di 100 utenti). Se il numero di utenti è elevato (ad esempio, più di 100 utenti), è più efficiente usare il cmdlet  [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) per inviare un'operazione batch.

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Usare il cmdlet Grant-CsTeamsMeeting per i criteri di accesso

Eseguire la procedura seguente per rimuovere il criterio di riunione RestrictedAnonymous dagli utenti.

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>Usare il cmdlet New-CsBatchPolicyAssignmentOperation

Con [l'assegnazione di](assign-policies.md#assign-a-policy-to-a-batch-of-users)criteri batch, il numero massimo di utenti per cui è possibile rimuovere o aggiornare i criteri è 5.000 alla volta. Ad esempio, se si hanno più di 5.000 utenti, è necessario inviare più batch. Per risultati ottimali, non inviare più batch alla volta. Consentire il completamento dell'elaborazione dei batch prima di inviare altri batch.

> [!NOTE]
> Il cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) si trova nel modulo PowerShell di Teams. Prima di eseguire questa procedura, installare e connettersi al modulo [Teams di PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams) Per istruzioni dettagliate, vedere Installare [Microsoft Teams PowerShell.](teams-powershell-install.md)

Eseguire i comandi seguenti per rimuovere il criterio di riunione RestrictedAnonymousAccess da un batch di utenti.

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>Ottenere lo stato dell'assegnazione batch

Ogni assegnazione batch restituisce un ID operazione, che è possibile usare per tenere traccia dell'avanzamento e dello stato delle assegnazioni e identificare gli eventuali errori. Ad esempio, eseguire:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

Verificare che **ErrorCount** sia **0** (zero) **e Che OverallStatus** sia **completato.**

## <a name="related-topics"></a>Argomenti correlati

- [Gestire i criteri di riunione in Teams](meeting-policies-in-teams.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Assegnare i criteri agli utenti in Teams](assign-policies.md)
