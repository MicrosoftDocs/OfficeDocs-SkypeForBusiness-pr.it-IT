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
ms.openlocfilehash: cc464419375b6391d0d95d6e99441777a40da9cb
ms.sourcegitcommit: bc73017b4a3fe6271830bc8c5044bfd43eec80c0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2022
ms.locfileid: "65266924"
---
# <a name="routing-calls-to-unassigned-numbers"></a>Routing delle chiamate a numeri non assegnati

L'amministratore può instradare le chiamate a numeri non assegnati nell'organizzazione. Ad esempio, è possibile instradare le chiamate a numeri non assegnati nel modo seguente: 

- Instradare tutte le chiamate a un determinato numero non assegnato a un annuncio personalizzato.

- Instrada tutte le chiamate a un determinato numero non assegnato al pannello comandi principale.

È possibile instradare le chiamate a numeri non assegnati a un utente, a un account di risorse associato a un operatore automatico o a una coda di chiamata oppure a un servizio di annuncio che riprodurrà un file audio personalizzato al chiamante.

## <a name="configuration"></a>Configurazione

Per instradare le chiamate a un numero non assegnato, usare il cmdlet New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment disponibile in Teams modulo di PowerShell 2.5.1 o versione successiva.

È necessario specificare il numero o l'intervallo di numeri chiamati e il routing associato per le chiamate a questi numeri. Ad esempio, il comando seguente specifica che tutte le chiamate al numero +1 (555) 222-3333 verranno instradate all'account della risorsa aa@contoso.com:

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId


New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

L'esempio successivo specifica che tutte le chiamate all'intervallo di numeri +1 (555) da 333-0000 a +1 (555) 333-9999 verranno instradate al servizio di annuncio, che riprodurrà il file audio MainAnnouncement.wav al chiamante.

```PowerShell
$Content = Get-Content "C:\Media\MainAnnoucement.wav" -Encoding byte -ReadCount 0

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>Note

- Se il routing a un annuncio, il file audio verrà riprodotto una volta al chiamante.

- Per instradare le chiamate a numeri di abbonati al Piano per chiamate Microsoft non assegnati, il tenant deve avere [crediti comunicazioni](what-are-communications-credits.md) disponibili.

- Per instradare le chiamate a numeri di servizio del piano per chiamate Microsoft non assegnati, il tenant deve avere almeno un Sistema telefonico – Licenza utente virtuale.

- I formati supportati per i file audio personalizzati sono WAV (non compresso, PCM lineare con profondità di 16/8/32 bit in mono o stereo), WMA (solo mono) e MP3. Il contenuto del file audio non può essere superiore a 5 MB.

- Per entrambe le chiamate in ingresso a chiamate Microsoft Teams e in uscita da Microsoft Teams il numero chiamato verrà confrontato con l'intervallo di numeri non assegnati.

- Se un modello/intervallo specificato contiene numeri di telefono assegnati a un account utente o di risorse nel tenant, le chiamate a questi numeri di telefono verranno indirizzate alla destinazione appropriata e non verranno indirizzate al trattamento dei numeri non assegnati specificati. Non ci sono altri controlli dei numeri nell'intervallo. Se l'intervallo contiene un numero di telefono esterno valido, le chiamate in uscita da Microsoft Teams a quel numero di telefono verranno instradate in base al trattamento.

## <a name="related-topics"></a>Argomenti correlati

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)

- [Test-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/test-csteamsunassignednumbertreatment)
