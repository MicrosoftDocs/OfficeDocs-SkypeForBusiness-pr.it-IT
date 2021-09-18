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
ms.custom: Learn how to manage the Music on Hold feature in Phone System.
ms.openlocfilehash: 845e85fbf7fb4fa9f5ee70769c6a66f49cd8bb4e
ms.sourcegitcommit: 9364f4fdf3dcd5ab6805360ff913d4e2e7ca9cfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/17/2021
ms.locfileid: "59432789"
---
# <a name="music-on-hold"></a>Musica blocco

Quando un Microsoft Teams un utente mette in attesa una chiamata in arrivo dalla rete PSTN (Public Switched Telephone Network), il chiamante PSTN può ascoltare la musica selezionata.

La musica riprodotta è la musica predefinita fornita da Microsoft o la musica personalizzata caricata e configurata. L'amministratore tenant può configurare se Musica blocco è disponibile usando i criteri di chiamata di Teams e assegnando il criterio all'Teams utente. 

Si noti che i chiamanti PSTN possono ascoltare Musica in attesa anche in altri scenari. ad esempio, quando chiamano in una coda di chiamata cloud o quando la chiamata è parcheggiata da un Microsoft Teams utente. Questi scenari non sono coperti o controllati dalle funzionalità menzionate in questo articolo. 

## <a name="configure-music-on-hold"></a>Configurare Musica blocco

Per configurare Musica blocco:

1.  Nel riquadro di spostamento sinistro dell'interfaccia Teams di amministrazione passare a Criteri **> chiamate vocali**.

2.  Nella scheda **Gestisci criteri** selezionare uno dei criteri esistenti o crearne uno nuovo.

3.  Nel campo Musica blocco per **i chiamanti PSTN** selezionare **Abilitato** nel menu a discesa.

È anche possibile configurare Musica blocco usando il modulo Teams PowerShell. In TeamsCallingPolicy modificare il parametro MusicOnHoldEnabledType su Enabled e quindi concedere l'istanza del criterio a uno o più utenti.

Se un utente Teams ha un criterio di chiamata Teams con Musica in attesa impostato su Disabilitato, non verrà riprodotta musica quando l'utente Teams mette in attesa la chiamata.

## <a name="configure-custom-music"></a>Configurare musica personalizzata

> [!NOTE]
> Questa funzionalità è disponibile come versione di anteprima pubblica.

Oltre a riprodurre musica predefinita per i chiamanti PSTN, è possibile caricare un file audio personalizzato con musica o altro contenuto audio e configurare il file audio per la riproduzione al chiamante PSTN.
Ad esempio, un reparto o un'organizzazione potrebbe voler riprodurre un annuncio personalizzato o musica personalizzata quando i chiamanti PSTN esterni vengono messi in attesa.  

> [!NOTE]
> L'utente è responsabile della cancellazione e della protezione indipendente di tutti i diritti e le autorizzazioni necessari per l'uso di qualsiasi file musicale o audio con il Microsoft Teams servizio. Questo può includere proprietà intellettuale e altri diritti in qualsiasi musica, effetti audio, audio, marchi, nomi e altri contenuti nel file audio di tutti i titolari di diritti pertinenti. I titolari possono includere artisti, attori, interpreti, musicisti, cantautori, compositori, etichette di registrazione, editori di musica, unioni, gilde, società di diritti, organizzazioni di gestione collettiva e qualsiasi altra parte che possiede, controlla o licenze i diritti di copyright della musica, gli effetti sonori, l'audio e altri diritti di proprietà intellettuale.

Per configurare il blocco Musica personalizzato, usare i cmdlet di PowerShell New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy e Import/Get/Remove-CsOnlineAudioFile Teams nel modulo di PowerShell 2.5.0 o versione successiva.


1. Assicurarsi che l Teams'utente abbia Musica blocco per i chiamanti PSTN impostato su Abilitato nei criteri Teams chiamate. 

2. Upload file audio personalizzato.

3. Creare un Teams di blocco chiamata che fa riferimento al file audio personalizzato e assegnarlo all'Teams utente.

### <a name="upload-the-custom-audio-file"></a>Upload file audio personalizzato

La configurazione dei file Musica blocco inizia con il caricamento del file audio. A questo scopo, si usa il cmdlet di PowerShell Import-CsOnlineAudioFile a questo scopo. Di seguito è riportato un esempio di caricamento di un file audio MP3 con l'interfaccia di PowerShell:

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Fare riferimento al file audio in un criterio Teams di blocco chiamata

Dopo aver caricato il file audio, è necessario fare riferimento al file in un criterio di blocco chiamate di Teams usando l'ID del file quando si crea o si imposta un criterio di blocco chiamata Teams chiamata. Ad esempio:

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

Dopo aver creato il nuovo criterio di blocco Teams chiamata, è possibile concederlo agli utenti usando Grant-CsTeamsCallHoldPolicy come indicato di seguito:

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

Per ottenere informazioni sui file audio caricati, usare il cmdlet Get-CsOnlineAudioFile.

Per rimuovere un file audio caricato, usare il cmdlet Remove-CsOnlineAudioFile caricamento. Prima di rimuovere un file audio, verificare di non usarlo in teamsCallHoldPolicy.

## <a name="restrictions"></a>Restrizioni

- Musica Il blocco è disponibile solo nel cloud commerciale.

- Musica Il blocco è disponibile solo quando l'utente è in Teams modalità Solo blocco.

- Musica Il blocco non è disponibile quando l'Teams utente esegue un trasferimento consultivo.

- Se l'utente Teams è abilitato per Location-Based routing, Musica non può essere riprodotto al chiamante.

-   Musica Il blocco è disponibile solo quando l Teams utente chiamato usa una delle versioni seguenti del client Teams:
    -   Microsoft Teams per Windows
    -   Microsoft Teams per Mac
    -   Microsoft Teams sul Web
    -   Microsoft Teams per iOS
    - Microsoft Teams per Android
<br>
- Non è possibile esportare il file audio dopo il caricamento. puoi solo rimuoverlo.

- Il Musica blocco non è disponibile per gli utenti configurati per l'aspetto della linea condivisa (delega) e quando viene usato Il parcheggio di chiamata. Verrà riprodotta Musica blocco standard.

- In alcuni scenari, una chiamata media bypass direct routing verrà convertita in bypass non multimediale per la riproduzione Musica in attesa e la chiamata rimarrà come bypass non multimediale finché la chiamata non viene terminata.



## <a name="related-topics"></a>Argomenti correlati

- [Assegnare criteri agli utenti](assign-policies.md)

- [Get-CsTeamsCallingPolicy](/powershell/module/skype/get-csteamscallingpolicy?view=skype-ps)

- [Set-CsTeamsCallingPolicy](/powershell/module/skype/set-csteamscallingpolicy?view=skype-ps)

- [Get-CsOnlineAudioFile](/powershell/module/skype/get-csonlineaudiofile?view=skype-ps)

- [Remove-CsOnlineAudioFile](/powershell/module/skype/remove-csonlineaudiofile?view=skype-ps)

- [New-CsTeamsCallHoldPolicy](/powershell/module/skype/new-csteamscallholdpolicy?view=skype-ps)

- [Get-CsTeamsCallHoldPolicy](/powershell/module/skype/get-csteamscallholdpolicy?view=skype-ps)

- [Grant-CsTeamsCallHoldPolicy](/powershell/module/skype/grant-csteamscallholdpolicy?view=skype-ps)

- [Remove-CsTeamsCallHoldPolicy](/powershell/module/skype/remove-csteamscallholdpolicy?view=skype-ps)

- [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile?view=skype-ps)





