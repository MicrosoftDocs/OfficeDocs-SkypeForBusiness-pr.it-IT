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
description: Informazioni su come rimuovere i criteri RestrictedAnonymousAccess Teams riunione dagli utenti dell'organizzazione.
ms.openlocfilehash: aab4b524ee0c9ab5cab3244a0897730fea0361a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121344"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>Rimuovere dagli utenti il criterio RestrictedAnonymousAccess per le riunioni di Teams

[I criteri](meeting-policies-in-teams.md) riunione in Microsoft Teams vengono usati per controllare le funzionalità disponibili per i partecipanti alla riunione per le riunioni pianificate dagli utenti dell'organizzazione. 

Teams include un criterio predefinito denominato RestrictedAnonymousAccess, che contiene impostazioni predefinite che includono la limitazione dell'avvio di una riunione da parte di utenti anonimi. Gli utenti anonimi sono utenti che non sono stati autenticati. Le impostazioni predefinite nei criteri riunione non possono essere modificate o modificate dagli amministratori.

Questo articolo illustra come usare PowerShell per rimuovere i criteri di riunione RestrictedAnonymousAccess dagli utenti a cui è assegnato questo criterio. Per altre informazioni su come gestire le Teams usando PowerShell, vedere panoramica Teams [PowerShell.](teams-powershell-overview.md)

## <a name="before-you-start"></a>Prima di iniziare

Installare e connettersi al [modulo Skype for Business PowerShell](/microsoft-365/enterprise/manage-skype-for-business-online-with-microsoft-365-powershell). Per istruzioni dettagliate, vedere Installare [Microsoft Teams PowerShell.](teams-powershell-install.md)

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>Ottenere le assegnazioni Teams criteri riunione per l'organizzazione

Eseguire le operazioni seguenti per ottenere le assegnazioni dei criteri Teams riunione per l'organizzazione.

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

In questo esempio viene restituito l'output seguente, che indica che a due utenti è assegnato il criterio di riunione RestrictedAnonymousAccess.

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>Annullare l'assegnazione dei criteri di riunione RestrictedAnonymous agli utenti

Per rimuovere i criteri riunione RestrictedAnonymous dagli utenti, è possibile usare il cmdlet [Grant-CSTeamsMeetingPolicy](/powershell/module/skype/grant-csteamsmeetingpolicy) se si ha un numero limitato di utenti, ad esempio meno di 100 utenti. Se si ha un numero elevato di utenti, ad esempio più di 100 utenti, è più efficiente usare il cmdlet  [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) per inviare un'operazione batch.

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Usare il cmdlet Grant-CsTeamsMeeting Policy

Eseguire le operazioni seguenti per rimuovere i criteri riunione RestrictedAnonymous dagli utenti.

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>Usare il cmdlet New-CsBatchPolicyAssignmentOperation

Con [l'assegnazione di](assign-policies.md#assign-a-policy-to-a-batch-of-users)criteri batch, il numero massimo di utenti per cui è possibile rimuovere o aggiornare i criteri è 5.000 alla volta. Ad esempio, se si hanno più di 5.000 utenti, sarà necessario inviare più batch. Per risultati ottimali, non inviare più batch contemporaneamente. Consentire ai batch di completare l'elaborazione prima di inviare altri batch.

> [!NOTE]
> Il cmdlet [New-CsBatchPolicyAssignmentOperation](/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) si trova nel Teams PowerShell. Prima di eseguire questa procedura, installare e connettersi al [modulo Teams PowerShell.](https://www.powershellgallery.com/packages/MicrosoftTeams) Per istruzioni dettagliate, vedere Installare [Microsoft Teams PowerShell.](teams-powershell-install.md)

Eseguire i comandi seguenti per rimuovere i criteri di riunione RestrictedAnonymousAccess da un batch di utenti.

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>Ottenere lo stato dell'assegnazione batch

Ogni assegnazione batch restituisce un ID operazione, che è possibile usare per tenere traccia dello stato e dello stato delle assegnazioni e identificare eventuali errori. Ad esempio, eseguire quanto segue:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

Assicurarsi che **ErrorCount** sia **0** (zero) e **OverallStatus** sia **Completed**.

## <a name="related-topics"></a>Argomenti correlati

- [Gestire i criteri di riunione in Teams](meeting-policies-in-teams.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Assegnare i criteri agli utenti in Teams](assign-policies.md)