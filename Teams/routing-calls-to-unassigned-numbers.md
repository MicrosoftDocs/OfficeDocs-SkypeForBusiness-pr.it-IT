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
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
description: Informazioni su come instradare le chiamate a numeri non assegnati nell'organizzazione.
ms.openlocfilehash: 810c6b1547586d5494dbba3d0ddbdfc8d5d3c5e1
ms.sourcegitcommit: ffcc4c7d5688fee28f5fdc8bb8e6b78afb1ee626
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2022
ms.locfileid: "68795518"
---
# <a name="routing-calls-to-unassigned-numbers"></a>Routing delle chiamate a numeri non assegnati

L'amministratore può instradare le chiamate a numeri non assegnati nell'organizzazione. Ad esempio, è possibile instradare le chiamate a numeri non assegnati nel modo seguente: 

- Instradare tutte le chiamate a un determinato numero non assegnato a un annuncio personalizzato.

- Instrada tutte le chiamate a un determinato numero non assegnato al pannello comandi principale.

È possibile instradare le chiamate a numeri non assegnati a un utente, a un account di risorse associato a un operatore automatico o a una coda di chiamata oppure a un servizio di annuncio che riprodurrà un file audio personalizzato al chiamante.

È possibile configurare il routing dei numeri non assegnati usando l'interfaccia di amministrazione di Teams o PowerShell.

## <a name="use-teams-admin-center"></a>Usare l'interfaccia di amministrazione di Teams

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams passare a **Numeri di telefono** **vocali** > .

2. Nella scheda **Regole routing** fare clic su **Aggiungi**.

3. Assegnare un nome alla regola, una descrizione e specificare l'ordine di valutazione per la regola.

4. Decidere il tipo di regola da aggiungere. È possibile selezionare le regole in cui il tipo di modello di numero di telefono è preconfigurato e si completano i criteri e l'opzione di routing. È anche possibile selezionare la configurazione avanzata, in cui immettere direttamente l'espressione regolare per il modello di numero di telefono e l'opzione di routing.

5. Selezionare **Salva**.

È anche possibile creare una regola di routing direttamente per un numero di telefono non assegnato.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams passare a **Numeri di telefono** **vocali** > .

2. Nella scheda **Numeri** selezionare un numero di telefono non assegnato e fare clic su **Instrada** nella parte superiore della visualizzazione

4. Assegnare un nome alla regola, una descrizione e specificare l'ordine di valutazione per la regola.

4. Selezionare l'opzione di routing.

5. Selezionare **Salva**.

È possibile testare le regole di routing usando la funzionalità Numero di test.

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Microsoft Teams passare a **Numeri di telefono** **vocali** > .

2. Nella scheda **Regole routing** fare clic su **Numero di test**.

3. Immetti direttamente un numero di telefono oppure fai clic su **Seleziona un numero** e seleziona uno dei numeri di telefono non assegnati nell'elenco a discesa.

4. Selezionare **Test**.


## <a name="use-powershell"></a>Usare PowerShell

Per instradare le chiamate a un numero non assegnato, usare il cmdlet New/Get/Set/Remove-CsTeamsUnassignedNumberTreatment disponibile nel modulo Di PowerShell di Teams 2.5.1 o versione successiva.

È necessario specificare il numero o l'intervallo di numeri chiamati e il routing associato per le chiamate a questi numeri. Ad esempio, il comando seguente specifica che tutte le chiamate al numero +1 (555) 222-3333 verranno instradate all'account della risorsa aa@contoso.com:

``` PowerShell
$RAObjectId = (Get-CsOnlineApplicationInstance -Identity aa@contoso.com).ObjectId

New-CsTeamsUnassignedNumberTreatment -Identity MainAA -Pattern "^\+15552223333$" -TargetType ResourceAccount -Target $RAObjectId -TreatmentPriority 1
```

L'esempio successivo specifica che tutte le chiamate all'intervallo di numeri +1 (555) da 333-0000 a +1 (555) 333-9999 verranno instradate al servizio di annuncio, che riprodurrà il file audio MainAnnouncement.wav al chiamante.

```PowerShell
$Content = [System.IO.File]::ReadAllBytes('C:\Media\MainAnnouncement.wav')

$AudioFile = Import-CsOnlineAudioFile -FileName "MainAnnouncement.wav" -Content $Content

$fid = [System.Guid]::Parse($AudioFile.Id)

New-CsTeamsUnassignedNumberTreatment -Identity TR1 -Pattern "^\+1555333\d{4}$" -TargetType Announcement -Target $fid.Guid -TreatmentPriority 2
```

## <a name="notes"></a>Note

- Se il routing a un annuncio, il file audio verrà riprodotto una volta al chiamante.

- Per instradare le chiamate a numeri di abbonati al Piano per chiamate Microsoft non assegnati, il tenant deve avere [crediti comunicazioni](what-are-communications-credits.md) disponibili.

- Per instradare le chiamate a numeri di servizio del piano per chiamate Microsoft non assegnati, il tenant deve avere almeno un **Telefono di Microsoft Teams licenza Account risorsa**.

- I formati supportati per i file audio personalizzati sono WAV (non compresso, PCM lineare con profondità di 16/8/32 bit in mono o stereo), WMA (solo mono) e MP3. Il contenuto del file audio non può essere superiore a 5 MB.

> [!NOTE]
> L'utente è responsabile della cancellazione e della protezione indipendenti di tutti i diritti e le autorizzazioni necessarie per l'uso di qualsiasi file musicale o audio con il servizio Microsoft Teams. Ciò può includere la proprietà intellettuale e altri diritti di tutti i titolari dei diritti relativi a musica, effetti sonori, audio, marchi, nomi e altri contenuti del file audio. I titolari possono includere artisti, attori, artisti, artisti, musicisti, cantautori, compositori, etichette discografica, editori musicali, sindacati, gilde, società per i diritti, organizzazioni di gestione collettiva e qualsiasi altra parte che possiede, controlla o concede in licenza i copyright musicali, gli effetti sonori, l'audio e altri diritti di proprietà intellettuale.

- Sia le chiamate in ingresso a Microsoft Teams che le chiamate in uscita da Microsoft Teams avranno il numero chiamato controllato rispetto all'intervallo di numeri non assegnati.

- Se un modello/intervallo specificato contiene numeri di telefono assegnati a un account utente o di risorse nel tenant, le chiamate a questi numeri di telefono verranno indirizzate alla destinazione appropriata e non verranno indirizzate al trattamento dei numeri non assegnati specificati. Non ci sono altri controlli dei numeri nell'intervallo. Se l'intervallo contiene un numero di telefono esterno valido, le chiamate in uscita da Microsoft Teams a quel numero di telefono verranno instradate in base al trattamento.


## <a name="related-topics"></a>Argomenti correlati

- [Get-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/get-csteamsunassignednumbertreatment)

- [New-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/new-csteamsunassignednumbertreatment)

- [Set-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/set-csteamsunassignednumbertreatment)

- [Remove-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/remove-csteamsunassignednumbertreatment)

- [Test-CsTeamsUnassignedNumberTreatment](/powershell/module/teams/test-csteamsunassignednumbertreatment)
