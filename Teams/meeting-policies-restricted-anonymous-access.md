---
title: Rimuovere i criteri di riunione di RestrictedAnonymousAccess teams dagli utenti
author: LanaChin
ms.author: v-lanac
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
description: Informazioni su come rimuovere i criteri di riunione di RestrictedAnonymousAccess teams dagli utenti dell'organizzazione.
ms.openlocfilehash: 12224ec860552b17b6f7fe50396081943955a88c
ms.sourcegitcommit: b72bf3827e7145b9b6a95c84e88a7879c6e8c337
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/12/2020
ms.locfileid: "46640987"
---
# <a name="remove-the-restrictedanonymousaccess-teams-meeting-policy-from-users"></a>Rimuovere i criteri di riunione di RestrictedAnonymousAccess teams dagli utenti

I [criteri di riunione](meeting-policies-in-teams.md) in Microsoft teams vengono usati per controllare le caratteristiche disponibili per i partecipanti alla riunione per le riunioni pianificate dagli utenti dell'organizzazione. 

Teams include un criterio predefinito denominato RestrictedAnonymousAccess, che contiene impostazioni predefinite che includono la restrizione degli utenti anonimi all'avvio di una riunione. Gli utenti anonimi sono utenti che non sono stati autenticati. Le impostazioni predefinite nel criterio della riunione non possono essere modificate o modificate dagli amministratori.

Questo articolo illustra come usare PowerShell per rimuovere i criteri della riunione RestrictedAnonymousAccess dagli utenti a cui è stato assegnato questo criterio. Per altre informazioni su come gestire i team tramite PowerShell, vedere [Panoramica di PowerShell per Team](teams-powershell-overview.md).

## <a name="before-you-start"></a>Prima di iniziare

Installare e connettersi al [modulo di PowerShell per Skype for business](https://www.microsoft.com/download/details.aspx?id=39366). Per informazioni dettagliate, vedere [installare Microsoft teams PowerShell](teams-powershell-install.md).

## <a name="get-the-teams-meeting-policy-assignments-for-your-organization"></a>Ottenere le assegnazioni dei criteri per le riunioni dei team per l'organizzazione

Eseguire la procedura seguente per ottenere le assegnazioni dei criteri per le riunioni dei team per l'organizzazione.

```powershell
Get-CsOnlineUser | Select-Object objectid, TeamsMeetingPolicy | Group-Object TeamsMeetingPolicy
```

In questo esempio viene restituito l'output seguente, che indica che a due utenti sono assegnati i criteri per le riunioni di RestrictedAnonymousAccess.

```console
Count  Name                               Group
------ ----------                         ---------
233    Education_HigherEducationStudent   {@{ObjectId=755e0d21-0737-4219-b68a-23423497f61f; TeamsMeetingPolicy=Education_HigherEducationStudent...
20                                        {@{ObjectId=e27fdfb5-bb38-4032-bb33-8e8bdf086eff; TeamsMeetingPolicy=}, @{ObjectId=91c330...
2      RestrictedAnonymousAccess          {@{ObjectId=38b35ebf-cc8b-4b61-a2db-f6e67c3f614b; TeamsMeetingPolicy=RestrictedAnonymousAccess...
```

## <a name="unassign-the-restrictedanonymous-meeting-policy-from-users"></a>Annullare l'assegnazione del criterio della riunione RestrictedAnonymous dagli utenti

Per rimuovere i criteri della riunione RestrictedAnonymous dagli utenti, è possibile usare il cmdlet [Grant-CSTeamsMeetingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csteamsmeetingpolicy) se si dispone di un numero limitato di utenti (ad esempio, meno di 100 utenti). Se si ha un numero elevato di utenti, ad esempio più di 100 utenti, è più efficiente usare il cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) per inviare un'operazione batch.

### <a name="use-the-grant-csteamsmeeting-policy-cmdlet"></a>Usare il cmdlet Grant-CsTeamsMeeting Policy

Eseguire la procedura seguente per rimuovere i criteri della riunione RestrictedAnonymous dagli utenti.

```powershell
Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | Select-Object objectid | foreach {Grant-CsTeamsMeetingPolicy -Identity $_.ObjectId -PolicyName $null}
```

### <a name="use-the-new-csbatchpolicyassignmentoperation-cmdlet"></a>Usare il cmdlet New-CsBatchPolicyAssignmentOperation

Con l' [assegnazione dei criteri batch](assign-policies.md#assign-a-policy-to-a-batch-of-users), il numero massimo di utenti per cui è possibile rimuovere o aggiornare i criteri è 5.000 alla volta. Ad esempio, se si hanno più di 5.000 utenti, è necessario inviare più batch. Per ottenere risultati ottimali, non inviare più batch alla volta. Consentire ai batch di completare l'elaborazione prima di inviare più batch.

> [!NOTE]
> Il cmdlet [New-CsBatchPolicyAssignmentOperation](https://docs.microsoft.com/powershell/module/teams/new-csbatchpolicyassignmentoperation?view=teams-ps) è nel modulo di PowerShell teams. Prima di eseguire questa procedura, installare e connettersi al [modulo di PowerShell teams](https://www.powershellgallery.com/packages/MicrosoftTeams). Per informazioni dettagliate, vedere [installare Microsoft teams PowerShell](teams-powershell-install.md).

Eseguire i comandi seguenti per rimuovere i criteri della riunione RestrictedAnonymousAccess da un batch di utenti.

```powershell
$restrictedAnonymousUsers = @(Get-CsOnlineUser |? TeamsMeetingPolicy -eq "RestrictedAnonymousAccess" | %{ $_.ObjectId })
```

```powershell
New-CsBatchPolicyAssignmentOperation -PolicyType TeamsMeetingPolicy -PolicyName $null -Identity $restrictedAnonymousUsers -OperationName "Batch unassign meeting policy"
```

#### <a name="get-the-status-of-the-batch-assignment"></a>Ottenere lo stato dell'assegnazione batch

Ogni assegnazione batch restituisce un ID operazione, che è possibile usare per tenere traccia dello stato di avanzamento e dello stato delle assegnazioni e identificare gli eventuali errori che potrebbero verificarsi. Ad esempio, eseguire le operazioni seguenti:

```powershell
Get-CsBatchPolicyAssignmentOperation -OperationId 62557b78-e734-42d6-952f-41a454ed6115
```

Verificare che **ErrorCount** sia **0** (zero) e che **OverallStatus** sia **completato**.

## <a name="related-topics"></a>Argomenti correlati

- [Gestire i criteri di riunione in Teams](meeting-policies-in-teams.md)
- [Panoramica di PowerShell per Teams](teams-powershell-overview.md)
- [Assegnare criteri agli utenti in teams](assign-policies.md)
