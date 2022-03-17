---
title: Musica blocco
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
description: Informazioni su come gestire la funzionalità Musica blocco in Sistema telefonico.
ms.openlocfilehash: a1e2662c04cfa9300d034aaaf8d7975e44e63f69
ms.sourcegitcommit: dafe48cea1643e1bd79390482da9b002d7e9e0bb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/16/2022
ms.locfileid: "63514783"
---
# <a name="music-on-hold"></a>Musica blocco

Quando un Microsoft Teams un utente mette in attesa una chiamata in arrivo dalla rete PSTN (Public Switched Telephone Network), il chiamante PSTN può ascoltare la musica selezionata.

La musica riprodotta è la musica predefinita fornita da Microsoft o la musica personalizzata caricata e configurata. L'amministratore tenant può configurare se Musica blocco è disponibile creando un criterio di chiamata Teams e assegnando il criterio all'Teams utente.

La musica predefinita fornita negli scenari Microsoft Teams chiamate PSTN è gratuita di eventuali royalty pagate dall'organizzazione.

Si noti che i chiamanti PSTN possono ascoltare Musica in attesa anche in altri scenari, ad esempio quando chiamano in una coda di chiamate cloud o quando la chiamata è parcheggiata da un Microsoft Teams utente. Questi scenari non sono coperti o controllati dalle funzionalità menzionate in questo articolo.

## <a name="configure-music-on-hold"></a>Configurare Musica blocco

Per configurare Musica blocco:

1.  Nel riquadro di spostamento sinistro dell'interfaccia Teams di amministrazione, passare a Criteri > **chiamate vocali**.

2.  Nella scheda **Gestisci criteri** selezionare uno dei criteri esistenti o crearne uno nuovo.

3.  Nel campo **Musica blocco per i chiamanti PSTN** selezionare **Abilitato** nel menu a discesa.

È anche possibile configurare Musica blocco usando il modulo Teams PowerShell. In TeamsCallingPolicy modificare il parametro MusicOnHoldEnabledType su Enabled e quindi concedere l'istanza del criterio a uno o più utenti.

Se un utente Teams ha un criterio di chiamata Teams con Musica in attesa impostato su Disabilitato, non verrà riprodotta musica quando l'utente Teams mette in attesa la chiamata.

## <a name="configure-custom-music"></a>Configurare musica personalizzata

Oltre a riprodurre musica predefinita per i chiamanti PSTN, è possibile caricare un file audio personalizzato con musica o altro contenuto audio e configurare il file audio per la riproduzione al chiamante PSTN.
Ad esempio, un reparto o un'organizzazione potrebbe voler riprodurre un annuncio personalizzato o musica personalizzata quando i chiamanti PSTN esterni vengono messi in attesa.  

> [!NOTE]
> L'utente è responsabile della cancellazione e della protezione indipendente di tutti i diritti e le autorizzazioni necessari per l'uso di qualsiasi file musicale o audio con il Microsoft Teams servizio. Questo può includere proprietà intellettuale e altri diritti in qualsiasi musica, effetti audio, audio, marchi, nomi e altri contenuti nel file audio di tutti i titolari di diritti pertinenti. I titolari possono includere artisti, attori, interpreti, musicisti, cantautori, compositori, etichette di registrazione, editori di musica, unioni, gilde, società di diritti, organizzazioni di gestione collettiva e qualsiasi altra parte che possiede, controlla o licenze i diritti di copyright della musica, gli effetti sonori, l'audio e altri diritti di proprietà intellettuale.

Per configurare il blocco Musica personalizzato, usare i cmdlet di PowerShell New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy e Import/Get/Remove/Export-CsOnlineAudioFile nel modulo di PowerShell 3.0.0 o versione successiva di Teams.

Per i formati audio supportati e le dimensioni massime del file, vedere [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)


1. Assicurarsi che l Teams'utente abbia Musica blocco per i chiamanti PSTN impostato su Abilitato nel criterio Teams chiamate. 

2. Upload file audio personalizzato.

3. Creare un Teams di blocco chiamata che faccia riferimento al file audio personalizzato e assegnarlo all'Teams utente.

### <a name="upload-the-custom-audio-file"></a>Upload file audio personalizzato

La configurazione dei file Musica blocco inizia con il caricamento del file audio. A questo scopo si usa il cmdlet di PowerShell [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile) .

Di seguito è riportato un esempio di caricamento di un file audio MP3 con l'interfaccia di PowerShell:

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Fare riferimento al file audio in un criterio Teams di blocco chiamata

Dopo aver caricato il file audio, è necessario fare riferimento al file in un criterio di blocco delle chiamate di Teams usando l'ID del file quando si crea o si imposta un criterio di blocco chiamata Teams chiamata. Ad esempio:

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

Dopo aver creato il nuovo criterio di blocco Teams chiamata, è possibile concederlo agli utenti usando Grant-CsTeamsCallHoldPolicy come indicato di seguito:

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

Per ottenere informazioni sui file audio caricati, usare il cmdlet Get-CsOnlineAudioFile.

Per rimuovere un file audio caricato, usare il cmdlet Remove-CsOnlineAudioFile caricamento. Prima di rimuovere un file audio, verificare di non usarlo in teamsCallHoldPolicy.

Per esportare un file audio caricato, usare il cmdlet Export-CsOnlineAudioFile.

## <a name="feature-availability"></a>Disponibilità delle funzionalità

La tabella seguente indica le funzionalità in cui i client e i dispositivi supportano Musica blocco e Musica blocco. Microsoft continua ad aggiungere il supporto per le funzionalità, quindi controlla spesso la disponibilità aggiuntiva.


| Funzionalità | Desktop <br> Windows/Mac OS | Browser | Dispositivi mobili <br> iOS | Dispositivi mobili <br> Android | Teams Telefono |
| :------------| :------- | :------- | :------- | :------- | :------- |
| Blocco alla chiamata PSTN 1:1 | -Musica blocco<br>-Blocco Musica personalizzato | -Musica blocco<br>-Blocco Musica personalizzato | -Musica blocco<br>-Blocco Musica personalizzato | -Musica blocco<br>-Blocco Musica personalizzato | -Musica blocco<br>-Blocco Musica personalizzato |
| Blocco del trasferimento consultivo in data 1:1 chiamata PSTN |-Musica blocco<br>-Blocco Musica personalizzato | | -Musica blocco<br>-Blocco Musica personalizzato | -Musica blocco<br>-Blocco Musica personalizzato | |

## <a name="restrictions"></a>Restrizioni

- Musica blocco è disponibile solo nelle istanze commerciali e GCC cloud.

- Musica blocco è disponibile solo quando l'utente è in modalità TeamsOnly.

- Se l'utente Teams è abilitato per Location-Based routing, Musica non può essere riprodotto al chiamante.

- Le Musica di blocco non sono disponibili per gli utenti configurati per l'aspetto della linea condivisa (delega) e quando viene usato Il parcheggio di chiamata. Verrà riprodotta Musica blocco standard.

- In alcuni scenari, una chiamata di bypass multimediale direct routing verrà convertita in bypass non multimediale per la riproduzione di Musica in attesa e la chiamata rimarrà come bypass non multimediale finché la chiamata non viene terminata.

## <a name="related-topics"></a>Argomenti correlati

- [Assegnare criteri agli utenti](policy-assignment-overview.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

- [Export-CsOnlineAudioFile](/powershell/module/skype/export-csonlineaudiofile)
