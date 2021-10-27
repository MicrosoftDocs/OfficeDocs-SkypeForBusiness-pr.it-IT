---
title: Routing delle chiamate a numeri non assegnati
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: jenstr
ms.topic: article
ms.assetid: aa2ec464-3481-4bbb-8c14-e13e18093df5
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Informazioni su come instradare le chiamate a numeri non assegnati nell'organizzazione.
ms.openlocfilehash: 2574a0ac734ed6caee1eadf5a5ee006111713055
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536997"
---
# <a name="routing-calls-to-unassigned-numbers"></a>Routing delle chiamate a numeri non assegnati

> [!NOTE]
> Questa funzionalità è disponibile come versione di anteprima pubblica.

L'amministratore può instradare le chiamate a numeri non assegnati nell'organizzazione. Ad esempio, è possibile instradare le chiamate a numeri non assegnati nel modo seguente: 

- Instradare tutte le chiamate a un determinato numero non assegnato a un annuncio personalizzato.

- Instradare tutte le chiamate a un determinato numero non assegnato al switchboard principale.

È possibile instradare le chiamate a numeri non assegnati a un utente, a un account della risorsa associato a un Operatore automatico o a una coda di chiamata o a un servizio di annuncio che riproduca un file audio personalizzato per il chiamante.

## <a name="configuration"></a>Configurazione

Per instradare le chiamate a un numero non assegnato, usare il cmdlet New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment disponibile Teams nel modulo di PowerShell 2.5.1 o versione successiva.

È necessario specificare il numero o l'intervallo di numeri chiamati e il routing associato per le chiamate a questi numeri. Ad esempio, il comando seguente specifica che tutte le chiamate al numero +1 (555) 222-3333 verranno instradati all'account della risorsa aa@contoso.com:

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId


New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

L'esempio successivo specifica che tutte le chiamate all'intervallo di numeri +1 (555) da 333-0000 a +1 (555) 333-9999 verranno instradate al servizio di annuncio, che riproduce il file audio MainAnnouncement.wav al chiamante.

```PowerShell
$Content = Get-Content "C:\Media\MainAnnoucement.wav" -Encoding byte -ReadCount 0

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>Note

- Se si instrada a un annuncio, il file audio verrà riprodotto una volta al chiamante.

- Per instradare le chiamate ai numeri di abbonato al Piano chiamate Microsoft non assegnato, il tenant deve avere crediti [comunicazioni disponibili.](what-are-communications-credits.md)

- Per instradare le chiamate a numeri di servizio del piano chiamate Microsoft non assegnato, il tenant deve avere almeno una licenza Sistema telefonico - Utente virtuale.

## <a name="related-topics"></a>Argomenti correlati

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)