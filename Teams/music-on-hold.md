---
title: Musica in attesa
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
audience: Admin
ms.reviewer: roykuntz
appliesto:
- Microsoft Teams
ms.localizationpriority: medium
ms.custom: ''
description: Informazioni su come gestire la funzionalità Musica in attesa in Sistema telefonico.
ms.openlocfilehash: 3f5121e72436966a82b38917453bcd21d8efa10f
ms.sourcegitcommit: 296862e02b548f0212c9c70504e65b467d459cc3
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65674418"
---
# <a name="music-on-hold"></a>Musica in attesa

Quando un utente Microsoft Teams mette in attesa una chiamata in arrivo, il chiamante può ascoltare la musica selezionata.

La musica che viene riprodotta è la musica predefinita fornita da Microsoft o la musica personalizzata che carichi e configuri. L'amministratore del tenant può configurare la disponibilità di Musica in attesa creando un criterio di chiamata Teams e assegnando il criterio all'utente Teams.

La musica predefinita fornita negli scenari di chiamata Microsoft Teams è priva di royalty e può essere pagata dall'organizzazione.

Si noti che i chiamanti possono ascoltare Musica in attesa anche in altri scenari, ad esempio quando chiamano una coda di chiamata cloud o quando la chiamata è parcheggiata da un utente Microsoft Teams. Questi scenari non sono coperti o controllati dalle funzionalità descritte in questo articolo.

## <a name="configure-music-on-hold"></a>Configurare Musica in attesa

Per configurare Musica in attesa:

1. Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Teams vai a Criteri per le **chiamate > vocali**.

2. Nella scheda **Gestisci criteri** selezionare uno dei criteri esistenti o crearne uno nuovo.

3. Nel campo **Musica in attesa per i chiamanti PSTN** selezionare **Abilitato** nel menu a discesa.

È anche possibile configurare Musica in attesa usando il modulo Teams PowerShell. In TeamsCallingPolicy, modificare il parametro MusicOnHoldEnabledType su Enabled e quindi concedere l'istanza del criterio a uno o più utenti.

Se un utente Teams ha un criterio di chiamata Teams con Musica in attesa impostato su Disabilitato, non verrà riprodotta musica quando l'utente Teams mette la chiamata in attesa.

## <a name="configure-custom-music"></a>Configurare musica personalizzata

Oltre a riprodurre musica predefinita per i chiamanti, è possibile caricare un file audio personalizzato con musica o altro contenuto audio e configurare tale file audio da riprodurre al chiamante.
Ad esempio, un reparto o un'organizzazione potrebbe voler riprodurre un annuncio personalizzato o musica personalizzata quando i chiamanti PSTN esterni vengono messi in attesa.  

> [!NOTE]
> L'utente è responsabile della cancellazione e della protezione indipendenti di tutti i diritti e le autorizzazioni necessarie per l'uso di musica o file audio con il servizio Microsoft Teams. Ciò può includere la proprietà intellettuale e altri diritti di tutti i titolari dei diritti relativi a musica, effetti sonori, audio, marchi, nomi e altri contenuti del file audio. I titolari possono includere artisti, attori, artisti, artisti, musicisti, cantautori, compositori, etichette discografica, editori musicali, sindacati, gilde, società per i diritti, organizzazioni di gestione collettiva e qualsiasi altra parte che possiede, controlla o concede in licenza i copyright musicali, gli effetti sonori, l'audio e altri diritti di proprietà intellettuale.

Per configurare Musica personalizzati in attesa, usare i cmdlet di PowerShell New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy e Import/Get/Remove/Export-CsOnlineAudioFile in Teams modulo di PowerShell 3.0.0 o versione successiva.

Per i formati audio supportati e le dimensioni massime dei file, vedi [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

1. Assicurarsi che l'utente Teams abbia Musica in attesa per i chiamanti PSTN impostato su Abilitato nel criterio di chiamata Teams. 

2. Upload il file audio personalizzato.

3. Creare un criterio di blocco delle chiamate Teams che fa riferimento al file audio personalizzato e assegnarlo all'utente Teams.

### <a name="upload-the-custom-audio-file"></a>Upload il file audio personalizzato

La configurazione dei Musica personalizzati in attesa inizia con il caricamento del file audio. A questo scopo, utilizza il cmdlet di PowerShell [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile) .

Di seguito è illustrato un esempio di caricamento di un file audio MP3 con Windows PowerShell 5.1. Per altri esempi, vedi [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile).

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Fare riferimento al file audio in un criterio di blocco delle chiamate Teams

Dopo aver caricato il file audio, è necessario fare riferimento al file in un criterio di blocco delle chiamate Teams usando l'ID del file quando si crea o si imposta un Teams criterio di blocco delle chiamate. Ad esempio:

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

Dopo aver creato il nuovo criterio di blocco delle chiamate Teams, è possibile concederlo agli utenti usando Grant-CsTeamsCallHoldPolicy come segue:

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

Per ottenere informazioni sui file audio caricati, usare il cmdlet Get-CsOnlineAudioFile.

Per rimuovere un file audio caricato, usare il cmdlet Remove-CsOnlineAudioFile. Prima di rimuovere un file audio, verificare di non usare il file audio in teamsCallHoldPolicy.

Per esportare un file audio caricato, usare il cmdlet Export-CsOnlineAudioFile.

## <a name="feature-availability"></a>Disponibilità delle funzionalità

La tabella seguente indica le funzionalità per i client e i dispositivi che supportano Musica in attesa e le Musica personalizzate in attesa. Microsoft continua ad aggiungere il supporto delle funzionalità, quindi controlla spesso se sono disponibili altre funzionalità.

| Funzionalità | Desktop <br> Windows/Mac OS | Browser | Dispositivi mobili <br> iOS | Dispositivi mobili <br> Android | Teams Telefono |
| :------------| :------- | :------- | :------- | :------- | :------- |
| Mettere in attesa una chiamata PSTN 1:1 | -Musica in attesa<br>-Custom Musica on Hold | -Musica in attesa<br>-Custom Musica on Hold | -Musica in attesa<br>-Custom Musica on Hold | -Musica in attesa<br>-Custom Musica on Hold | -Musica in attesa<br>-Custom Musica on Hold |
| Attesa Teams chiamata 1:1 | -Musica in attesa<br>-Custom Musica on Hold | -Musica in attesa<br>-Custom Musica on Hold | -Musica in attesa<br>-Custom Musica on Hold | -Musica in attesa<br>-Custom Musica on Hold | -Musica in attesa<br>-Custom Musica on Hold |
| Mettere in attesa il trasferimento suggerito su una chiamata PSTN 1:1 |-Musica in attesa<br>-Custom Musica on Hold || -Musica in attesa<br>-Custom Musica on Hold | -Musica in attesa<br>-Custom Musica on Hold | -Musica in attesa<br>-Custom Musica on Hold |
| Mettere in attesa il trasferimento di consulenza il 1:1 Teams chiamata |-Musica in attesa<br>-Custom Musica on Hold || -Musica in attesa<br>-Custom Musica on Hold | -Musica in attesa<br>-Custom Musica on Hold | -Musica in attesa<br>-Custom Musica on Hold |

## <a name="restrictions"></a>Restrizioni

- Musica in attesa è disponibile solo in istanze commerciali e GCC cloud.

- Musica in attesa è disponibile solo quando l'utente è in modalità TeamsOnly.

- Se l'utente chiamato Teams è abilitato per il routing Location-Based, non è possibile riprodurre Musica in attesa al chiamante.

- I Musica personalizzati in attesa non sono disponibili per gli utenti configurati per l'aspetto della linea condivisa (delega) e quando viene utilizzato il parcheggio di chiamata. Verrà riprodotta la Musica standard in attesa.

- In alcuni scenari, una chiamata di bypass multimediale direct routing verrà convertita in bypass non multimediale per la riproduzione di Musica in attesa e la chiamata rimarrà come bypass non multimediale fino al termine della chiamata.

## <a name="related-topics"></a>Argomenti correlati

- [Assegnare criteri agli utenti](policy-assignment-overview.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

- [Export-CsOnlineAudioFile](/powershell/module/skype/export-csonlineaudiofile)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy)
