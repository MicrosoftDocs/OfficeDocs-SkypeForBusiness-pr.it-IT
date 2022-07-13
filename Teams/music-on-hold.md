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
description: Scopri come gestire la funzionalità Musica in attesa nel sistema telefonico.
ms.openlocfilehash: 9d8fa247ffdc982c5d41777c68f6b620a92644e3
ms.sourcegitcommit: 8fc2d6a824e1e119f54ea2347bc5c10cc076956d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/13/2022
ms.locfileid: "66773755"
---
# <a name="music-on-hold"></a>Musica in attesa

Quando un utente di Microsoft Teams mette in attesa una chiamata in arrivo, il chiamante può ascoltare la musica selezionata.

La musica che viene riprodotta è la musica predefinita fornita da Microsoft o la musica personalizzata che carichi e configuri. L'amministratore del tenant può configurare se la musica in attesa è disponibile creando un criterio per le chiamate di Teams e assegnando il criterio all'utente di Teams.

La musica predefinita fornita negli scenari di chiamata di Microsoft Teams è priva di royalty.

Tieni presente che i chiamanti possono ascoltare musica in attesa anche in altri scenari; ad esempio, quando accedono a una coda di chiamata cloud o quando la chiamata è parcheggiata da un utente di Microsoft Teams. Questi scenari non sono coperti o controllati dalle funzionalità descritte in questo articolo.

## <a name="configure-music-on-hold"></a>Configurare la musica in attesa

Per configurare Musica in attesa:

1. Nella barra di spostamento sinistra dell'interfaccia di amministrazione di Teams, vai a **Criteri per le chiamate > vocali**.

2. Nella scheda **Gestisci criteri** selezionare uno dei criteri esistenti o crearne uno nuovo.

3. Nel campo **Musica in attesa per i chiamanti PSTN** selezionare **Abilitato** nel menu a discesa.

È anche possibile configurare Musica in attesa usando il modulo Di Teams PowerShell. In TeamsCallingPolicy, modificare il parametro MusicOnHoldEnabledType su Enabled e quindi concedere l'istanza del criterio a uno o più utenti.

Se un utente di Teams ha un criterio di chiamata di Teams con Musica in attesa impostata su Disabilitata, non verrà riprodotta musica quando l'utente di Teams mette la chiamata in attesa.

## <a name="configure-custom-music"></a>Configurare musica personalizzata

Oltre a riprodurre musica predefinita per i chiamanti, è possibile caricare un file audio personalizzato con musica o altro contenuto audio e configurare tale file audio da riprodurre al chiamante.
Ad esempio, un reparto o un'organizzazione potrebbe voler riprodurre un annuncio personalizzato o musica personalizzata quando i chiamanti PSTN esterni vengono messi in attesa.

La configurazione viene eseguita usando i criteri di blocco delle chiamate.

> [!NOTE]
> L'utente è responsabile della cancellazione e della protezione indipendenti di tutti i diritti e le autorizzazioni necessarie per l'uso di qualsiasi file musicale o audio con il servizio Microsoft Teams. Ciò può includere la proprietà intellettuale e altri diritti di tutti i titolari dei diritti relativi a musica, effetti sonori, audio, marchi, nomi e altri contenuti del file audio. I titolari possono includere artisti, attori, artisti, artisti, musicisti, cantautori, compositori, etichette discografica, editori musicali, sindacati, gilde, società per i diritti, organizzazioni di gestione collettiva e qualsiasi altra parte che possiede, controlla o concede in licenza i copyright musicali, gli effetti sonori, l'audio e altri diritti di proprietà intellettuale.

### <a name="use-the-teams-admin-center"></a>Usare l'interfaccia di amministrazione di Teams
È possibile usare l'interfaccia di amministrazione di Teams per configurare musica personalizzata in attesa per gli utenti creando o modificando i criteri di blocco delle chiamate.

Per configurare un nuovo criterio di blocco delle chiamate:

1. Nell'interfaccia di amministrazione di Teams passare a **Criteri di blocco delle chiamate vocali** > .

2. Selezionare la scheda **Aggiungi** .

3. Assegnare un nome e una descrizione al criterio.

4. Seleziona **Carica file** per caricare il file audio musicale personalizzato.

5. Selezionare **Applica**.

### <a name="assign-a-custom-call-hold-policy-to-users"></a>Assegnare criteri di blocco delle chiamate personalizzati agli utenti

[!INCLUDE [assign-policy](includes/assign-policy.md)]

### <a name="use-powershell"></a>Usare PowerShell
Per configurare musica personalizzata in attesa, usare i cmdlet di PowerShell New/Get/Set/Grant/Remove-CsTeamsCallHoldPolicy e Import/Get/Remove/Export-CsOnlineAudioFile nel modulo Di PowerShell di Teams 3.0.0 o versione successiva.

Per i formati audio supportati e le dimensioni massime dei file, vedi [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile)

1. Assicurarsi che l'utente di Teams abbia musica in attesa per i chiamanti PSTN impostata su Abilitato nei criteri di chiamata di Teams. 

2. Caricare il file audio personalizzato.

3. Creare un criterio di blocco chiamate di Teams che fa riferimento al file audio personalizzato e assegnarlo all'utente di Teams.

### <a name="upload-the-custom-audio-file"></a>Caricare il file audio personalizzato

La configurazione della musica in attesa personalizzata inizia con il caricamento del file audio. A questo scopo, utilizza il cmdlet di PowerShell [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile) .

Di seguito è illustrato un esempio di caricamento di un file audio MP3 con Windows PowerShell 5.1. Per altri esempi, vedi [Import-CsOnlineAudioFile](/powershell/module/skype/import-csonlineaudiofile).

```PowerShell
C:\> $content = Get-Content "C:\tmp\customMoH1.mp3" -Encoding byte -ReadCount 0
C:\> $AudioFile = Import-CsOnlineAudioFile -FileName "customMoH1.mp3" -Content $content
C:\> $AudioFile
Id            : 56a56961f2794f098a359885ec1454a1
FileName      : customMoH1.mp3
ApplicationId : TenantGlobal
```

### <a name="reference-the-audio-file-in-a-teams-call-hold-policy"></a>Fare riferimento al file audio in un criterio di blocco delle chiamate di Teams

Dopo aver caricato il file audio, è necessario fare riferimento al file in un criterio di blocco delle chiamate di Teams usando l'ID del file quando si crea o si imposta un criterio di blocco delle chiamate di Teams. Ad esempio:

```PowerShell
C:\> New-CsTeamsCallHoldPolicy -Identity "CustomMoH1" -Description "Custom MoH using CustomMoH1.mp3" -AudioFileId $AudioFile.Id
```

Dopo aver creato i nuovi criteri di blocco chiamate di Teams, è possibile concederli agli utenti usando Grant-CsTeamsCallHoldPolicy come segue:

```PowerShell
C:\> Grant-CsTeamsCallHoldPolicy -PolicyName "CustomMoH1" -Identity user1@contoso.com
```

Per ottenere informazioni sui file audio caricati, usare il cmdlet Get-CsOnlineAudioFile.

Per rimuovere un file audio caricato, usare il cmdlet Remove-CsOnlineAudioFile. Prima di rimuovere un file audio, verificare di non usare il file audio in teamsCallHoldPolicy.

Per esportare un file audio caricato, usare il cmdlet Export-CsOnlineAudioFile.

## <a name="feature-availability"></a>Disponibilità delle funzionalità

La tabella seguente indica le funzionalità in quali client e dispositivi supportano Musica in attesa e Musica personalizzata in attesa. Microsoft continua ad aggiungere il supporto delle funzionalità, quindi controlla spesso se sono disponibili altre funzionalità.

| Funzionalità | Desktop <br> Windows/Mac OS | Browser | Dispositivi mobili <br> iOS | Dispositivi mobili <br> Android | Telefono di Teams |
| :------------| :------- | :------- | :------- | :------- | :------- |
| Mettere in attesa una chiamata PSTN 1:1 | -Musica in attesa<br>-Musica personalizzata in attesa | -Musica in attesa<br>-Musica personalizzata in attesa | -Musica in attesa<br>-Musica personalizzata in attesa | -Musica in attesa<br>-Musica personalizzata in attesa | -Musica in attesa<br>-Musica personalizzata in attesa |
| Mettere in attesa la chiamata di Teams 1:1 | -Musica in attesa<br>-Musica personalizzata in attesa | -Musica in attesa<br>-Musica personalizzata in attesa | -Musica in attesa<br>-Musica personalizzata in attesa | -Musica in attesa<br>-Musica personalizzata in attesa | -Musica in attesa<br>-Musica personalizzata in attesa |
| Mettere in attesa il trasferimento suggerito su una chiamata PSTN 1:1 |-Musica in attesa<br>-Musica personalizzata in attesa || -Musica in attesa<br>-Musica personalizzata in attesa | -Musica in attesa<br>-Musica personalizzata in attesa | -Musica in attesa<br>-Musica personalizzata in attesa |
| Mettere in attesa il trasferimento suggerito su una chiamata di Teams 1:1 |-Musica in attesa<br>-Musica personalizzata in attesa || -Musica in attesa<br>-Musica personalizzata in attesa | -Musica in attesa<br>-Musica personalizzata in attesa | -Musica in attesa<br>-Musica personalizzata in attesa |

## <a name="restrictions"></a>Restrizioni

- La musica in attesa è disponibile solo nelle istanze cloud commerciali e GCC.

- La musica in attesa è disponibile solo quando l'utente è in modalità TeamsOnly.

- Se l'utente di Teams è abilitato per il routing Location-Based, la musica in attesa non può essere riprodotta al chiamante.

- La musica personalizzata in attesa non è disponibile per gli utenti configurati per l'aspetto della linea condivisa (delega) e quando viene utilizzato il parcheggio di chiamata. Verrà riprodotta la musica in attesa standard.

- In alcuni scenari, una chiamata di bypass multimediale direct routing verrà convertita in bypass non multimediale per la riproduzione di musica in attesa e la chiamata rimarrà come bypass non multimediale fino al termine della chiamata.

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
