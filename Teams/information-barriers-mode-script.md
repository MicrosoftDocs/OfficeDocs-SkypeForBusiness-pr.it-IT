---
title: Modificare le modalità di protezione delle informazioni con uno script di PowerShell
author: robmazz
ms.author: robmazz
manager: laurawi
ms.topic: article
ms.reviewer: smahadevan
ms.service: msteams
audience: admin
description: Usare questo script di PowerShell dopo aver distribuito le barriere di informazioni per aggiornare la modalità da aperta a implicita per tutti i gruppi nel tenant.
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3030f40ed61eb2e0e86967132d9575de8334a6c6
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2022
ms.locfileid: "61767657"
---
# <a name="change-information-barriers-modes-with-a-powershell-script"></a>Modificare le modalità di protezione delle informazioni con uno script di PowerShell

Usare questo script di PowerShell per aggiornare la modalità information barriers (IB) per tutti i Teams connessi al tenant. Dopo aver distribuito le barriere alle informazioni, sarà necessario aggiornare la modalità per questi gruppi. Ai gruppi di cui è stato eseguito il provisioning prima di abilitare IB viene assegnata la *modalità Apri.* In *modalità* di apertura non sono presenti criteri IB applicabili. Dopo aver abilitato IB, *Implicito* diventa la modalità predefinita per tutti i nuovi gruppi creati. Tuttavia, i gruppi esistenti mantengono comunque *la configurazione in* modalità aperta. Eseguire questo script per impostare questi gruppi esistenti in *modalità implicita.*

In questo script si userà il cmdlet [Get-UnifiedGroup,](/powershell/module/exchange/Set-UnifiedGroup) che si trova nel modulo Exchange Online PowerShell per aggiornare la modalità. Per altre informazioni sulla gestione dei Teams con PowerShell, vedere panoramica Teams [PowerShell.](./teams-powershell-overview.md)

## <a name="sample-script"></a>Script di esempio

Per eseguire questo script, è necessario usare un account aziendale o dell'istituto di istruzione a cui è stato assegnato il ruolo di amministratore globale per il tenant.

```powershell
<#
.SYNOPSIS
This script updates the information barrier mode for all Teams-connected groups in your tenant at the same time.
.DESCRIPTION
Use this script to update the info barrier mode from open to implicit across the groups in your tenant.
#>

$teams = Get-UnifiedGroup -Filter {ResourceProvisioningOptions -eq "Team"} -ResultSize Unlimited

Write-Output ([string]::Format("Number of Teams = {0}", @($teams).Length))

$teamsToUpdate = New-Object System.Collections.ArrayList

foreach($team in $teams)
{
  if ($team.InformationBarrierMode -eq "Open")
  {
    $teamsToUpdate.Add($team.ExternalDirectoryObjectId) | out-null
  }
}

Write-Output ([string]::Format("Number of Teams to be backfilled = {0}", @($teamsToUpdate).Length))

$outfile = "BackfillFailedTeams.csv"

if (!(Test-Path "$outfile"))
{
  $newcsv = {} | Select "ExternalDirectoryObjectId", "ExceptionDetails" | Export-Csv $outfile -NoTypeInformation  
}
else
{
  $dateTime = Get-Date
  $newEntry = "{0},{1}" -f "New session started", $dateTime
  $newEntry | add-content $outfile
}

$SuccessfullyBackfilledGroup = 0

for($i = 0; $i -lt @($teamsToUpdate).Length; $i++)
{
  Invoke-Command { Set-UnifiedGroup $teamsToUpdate[$i] -InformationBarrierMode "Implicit" } -ErrorVariable ErrorOutput

  if ($ErrorOutput)
  {
    # saving the errors in a csv file
    $errorBody = $ErrorOutput[0].ToString() -replace "`n"," " -replace "`r"," " -replace ",", " "
    $newEntry = "{0},{1}" -f $teamsToUpdate[$i].ToString(), '"' + $errorBody + '"'
    $newEntry | add-content $outfile
  }
  else
  {
    $SuccessfullyBackfilledGroup++
  }

  if (($i+1) % 100 -eq 0)
  {
    # print the number of teams backfilled after the batch of 100 updates
    Write-Output ([string]::Format("Number of Teams processed= {0}", $i+1)) 
  }
}

Write-Output ([string]::Format("Backfill completed. Groups backfilled: {0}, Groups failed to backfill: {1}", $SuccessfullyBackfilledGroup, @($teamsToUpdate).Length - $SuccessfullyBackfilledGroup))

if (!($SuccessfullyBackfilledGroup -eq @($teamsToUpdate).Length))
{
  Write-Output ([string]::Format("Check the failed teams in BackfillFailedTeams.csv, retry to backfill the failed teams.")) 
}

```