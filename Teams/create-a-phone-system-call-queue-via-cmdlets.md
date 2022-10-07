---
title: Creare una coda di chiamata tramite cmdlet
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview
- Phone System
- seo-marvel-apr2020
description: Informazioni su come configurare le code di chiamata tramite i cmdlet
ms.openlocfilehash: 7654d59b66643b0eebf137af8aed0a9c672aea70
ms.sourcegitcommit: fc87f4300f53abf7a049936944abb21d0cade0d9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/06/2022
ms.locfileid: "68481218"
---
# <a name="create-a-call-queue-via-cmdlets"></a>Creare una coda di chiamata tramite cmdlet

## <a name="assumptions"></a>Ipotesi

1. PowerShell è installato nel computer
   - Configurare il computer per [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
   - Modulo MSTeams installato

     ```powershell
     Install-Module -Name MicrosoftTeams -Force -AllowClobber
     ```

   - Modulo MSOnline installato

     ```powershell
     Install-Module -Name MSOnline -Force -AllowClobber
     ```

2. Hai i diritti di amministrazione tenant
3. Hai acquistato Telefono di Microsoft Teams
4. Gli agenti, le liste di distribuzione e i canali di Teams indicati di seguito sono già stati creati

Nota: il cmdlet Teams Channel usato di seguito fa parte della versione di anteprima pubblica del modulo PowerShell di Teams.  Per altre informazioni, vedere [Installare l'anteprima pubblica di PowerShell di Teams](teams-powershell-install.md) e vedere anche [Note sulla versione di Microsoft Teams PowerShell](teams-powershell-release-notes.md).

Gli utenti che hanno già installato il modulo MicrosoftTeams devono `Update-Module MicrosoftTeams` assicurarsi che sia installata la versione più aggiornata.

## <a name="scenario"></a>Scenario

Verranno create le tre code di chiamata seguenti:

Informazioni sulla coda di chiamata di vendita:

- Davanti all'operatore automatico: Sì
- Chiamate dirette da PSTN: No
- Lingua: inglese (Stati Uniti)
- Messaggio di saluto: Nessuno
- Musica in attesa: riprodurre un file audio
  - Nome file: sales-hold-in-queue-music.wav
- Risposta alle chiamate: utenti
  - Bill@contoso.com
  - Mary@contoso.com
- Modalità conferenza: attivata
- Metodo di routing: Attendant
- Routing basato sulla presenza: disattivato
- Gli agenti di chiamata possono rifiutare esplicitamente di effettuare chiamate: Sì
- Ora avviso agente di chiamata: 15
- Gestione dell'overflow delle chiamate: 200
  - Reindirizza a: Adele@contoso.com
- Gestione del timeout di chiamata: 120 secondi
  - Reindirizza a: Adele@contoso.com

Informazioni sulla coda di chiamata di supporto:

- Davanti all'operatore automatico: Sì
- Chiamate dirette da PSTN: No
- Lingua: inglese (Regno Unito)
- Messaggio di saluto: riprodurre un file audio
  - Nome file: support-greeting.wav
- Musica in attesa: riprodurre un file audio
  - Nome file: support-hold-in-queue-music.wav
- Risposta alle chiamate: lista di distribuzione del supporto
  - Support@contoso.com
- Modalità conferenza: attivata
- Metodo di routing: inattività più lunga
- Routing basato sulla presenza: N/D – attivato per impostazione predefinita a causa dell'inattività più lunga
- Gli agenti di chiamata possono rifiutare esplicitamente di effettuare chiamate: No
- Ora avviso agente di chiamata: 15
- Gestione dell'overflow delle chiamate: 200
  - Reindirizzamento: supportare la segreteria telefonica condivisa
    - Riprodurre un file audio (support-shared-voicemail-greeting.wav)
    - Trascrizione abilitata
- Gestione del timeout di chiamata: 45 minuti
  - Reindirizzamento: supportare la segreteria telefonica condivisa
    - Sintesi vocale: "Siamo spiacenti di averti fatto aspettare e stiamo trasferendo la chiamata alla segreteria telefonica".
    - Trascrizione abilitata

Strutture Informazioni sulla coda di chiamata collaborativa:

- Fronted by Auto Attendant: No
- Chiamate dirette da PSTN: No (solo chiamate interne)
- Lingua: francese FR
- Messaggio di saluto: Nessuno
- Musica in attesa: impostazione predefinita
- Risposta alle chiamate: Team: Strutture
- Canale di risposta alle chiamate: Help Desk
  - Proprietario del canale: Fred@contoso.com
- Modalità conferenza: attivata
- Metodo di routing: Round Robin
- Routing basato sulla presenza: attivato
- Gli agenti di chiamata possono rifiutare esplicitamente di effettuare chiamate: No
- Ora avviso agente di chiamata: 15
- Gestione dell'overflow delle chiamate: 200
  - Disconnetti
- Gestione del timeout di chiamata: 45 minuti
  - Disconnetti

## <a name="login"></a>Login

Verrà richiesto di immettere le credenziali di amministratore di Teams.

```powershell
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
```

## <a name="sales-queue"></a>Coda di vendita

### <a name="create-audio-files"></a>Creare file audio

Sostituire "d:\\" con il percorso in cui sono archiviati i file wav nel computer.

```powershell
$content = [System.IO.File]::ReadAllBytes('d:\sales-hold-in-queue-music.wav')
$audioFileSalesHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "sales-hold-in-queue-music.wav" -Content $content).ID
```

### <a name="get-users-id"></a>Ottieni ID utenti

```powershell
$userAdeleID = (Get-CsOnlineUser -Identity "sip:adele@contoso.com").Identity
$userSalesBillID = (Get-CsOnlineUser -Identity "sip:bill@contoso.com").Identity
$userSalesMaryID = (Get-CsOnlineUser -Identity "sip:mary@contoso.com").Identity
```

### <a name="get-list-of-supported-languages"></a>Ottenere l'elenco delle lingue supportate

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### <a name="create-call-queue"></a>Crea coda di chiamata

```powershell
New-CsCallQueue -Name "Sales" -AgentAlertTime 15 -AllowOptOut $true -MusicOnHoldAudioFileID $audioFileSalesHoldInQueueMusicID -OverflowAction Forward -OverflowActionTarget $userAdeleID -OverflowThreshold 200 -TimeoutAction Forward -TimeoutActionTarget $userAdeleID -TimeoutThreshold 120 -RoutingMethod Attendant -ConferenceMode $true -User @($userSalesBillID, $userSalesMaryID) -LanguageID "en-US"
```

### <a name="get-license-types"></a>Ottenere i tipi di licenza

```powershell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>Creare e assegnare un account di risorsa

Nota: il numero di telefono non è necessario perché la coda di chiamata è front-end terminata da un operatore automatico

- Applicationid
  - Operatore automatico: ce933385-9390-45d1-9512-c8d228074e07
  - Coda di chiamata: 11cd3e2e-fccb-42ad-ad00-878b93575e07

Nota: il tipo di licenza mostrato di seguito (PHONESYSTEM_VIRTUALUSER) deve essere elencato dal cmdlet Get-MsolAccountSku precedente.

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName Sales-RA@contoso.com -DisplayName "Sales" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Sales-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "Sales-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Sales-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Sales").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
```

## <a name="support-queue"></a>Coda di supporto

### <a name="create-audio-files"></a>Creare file audio

Sostituire "d:\\" con il percorso in cui sono archiviati i file wav nel computer.

```powershell
$content1 = [System.IO.File]::ReadAllBytes('d:\support-greeting.wav')
$audioFileSupportGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-greeting.wav" -Content $content1).ID

$content2 = [System.IO.File]::ReadAllBytes('d:\support-hold-in-queue-music.wav')
$audioFileSupportHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-hold-in-queue-music.wav" -Content $content2).ID

$content3 = [System.IO.File]::ReadAllBytes('d:\support-shared-voicemail-greeting.wav')
$audioFileSupportSharedVoicemailGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-shared-voicemail-greeting.wav" -Content $content3).ID
```

### <a name="get-support-team-group-id"></a>Ottenere l'ID del gruppo del team di supporto

```powershell
$teamSupportID = (Get-Team -DisplayName "Support").GroupID
```

### <a name="get-list-of-supported-languages"></a>Ottenere l'elenco delle lingue supportate

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### <a name="create-call-queue"></a>Crea coda di chiamata

```powershell
New-CsCallQueue -Name "Support" -AgentAlertTime 15 -AllowOptOut $false -DistributionLists $teamSupportID -WelcomeMusicAudioFileID $audioFileSupportGreetingID -MusicOnHoldAudioFileID $audioFileSupportHoldInQueueMusicID -OverflowAction SharedVoicemail -OverflowActionTarget $teamSupportID -OverflowThreshold 200 -OverflowSharedVoicemailAudioFilePrompt $audioFileSupportSharedVoicemailGreetingID -EnableOverflowSharedVoicemailTranscription $true -TimeoutAction SharedVoicemail -TimeoutActionTarget $teamSupportID -TimeoutThreshold 2700 -TimeoutSharedVoicemailTextToSpeechPrompt "We're sorry to have kept you waiting and are now transferring your call to voicemail." -EnableTimeoutSharedVoicemailTranscription $true -RoutingMethod LongestIdle -ConferenceMode $true -LanguageID "en-US"
```

### <a name="get-license-types"></a>Ottenere i tipi di licenza

```powershell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>Creare e assegnare un account di risorsa

Nota: il numero di telefono non è necessario qui perché la coda di chiamata è front-ended da un operatore automatico

- Applicationid
  - Operatore automatico: ce933385-9390-45d1-9512-c8d228074e07
  - Coda di chiamata: 11cd3e2e-fccb-42ad-ad00-878b93575e07

Nota: il tipo di licenza mostrato di seguito (PHONESYSTEM_VIRTUALUSER) deve essere elencato dal cmdlet Get-MsolAccountSku precedente.

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Support" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Support-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "Support-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Support-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Support").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
```

## <a name="facilities-collaborative-calling-queue"></a>Coda di chiamate collaborativa strutture

### <a name="get-facilities-team-group-id"></a>Ottieni l'ID del gruppo del team Strutture

```powershell
$teamFacilitiesGroupID = (Get-Team -DisplayName "Facilities").GroupID
```

### <a name="get-facilities-help-desk-team-channel-id"></a>Ottieni l'ID canale del team Help Desk per le strutture

```powershell
Get-TeamChannel -GroupId $teamFacilitiesGroupID
$teamFacilitiesHelpDeskChannelID = "{assign ID from output of above command}"
```

### <a name="get-facilities-help-desk-channel-owner-user-id"></a>Ottieni l'ID utente del canale Help Desk per le strutture

```powershell
$teamFacilitiesHelpDeskChannelUserID = (Get-TeamChannelUser -GroupId $teamFacilitiesGroupID -DisplayName "Help Desk" -Role Owner).UserId
```

### <a name="get-on-behalf-of-calling-resource-account-id"></a>Ottieni per conto di Calling Resource Account ID

```powershell
$oboResourceAccountID = (Get-CsOnlineUser -Identity "MainAA-RA@contoso.com").Identity
```

### <a name="get-list-of-supported-languages"></a>Ottenere l'elenco delle lingue supportate

```powershell
Get-CsAutoAttendantSupportedLanguage
```

### <a name="create-call-queue"></a>Crea coda di chiamata

```powershell
New-CsCallQueue -Name "Facilities" -AgentAlertTime 15 -AllowOptOut $false -ChannelId $teamFacilitiesHelpDeskChannelID -ChannelUserObjectId $teamFacilitiesHelpDeskChannelUserID  -ConferenceMode $true -DistributionList $teamFacilitiesGroupID -LanguageID "fr-FR" -OboResourceAccountIds $oboResourceAccountID -OverflowAction DisconnectWithBusy -OverflowThreshold 200 -RoutingMethod RoundRobin -TimeoutAction Disconnect -TimeoutThreshold 2700 -UseDefaultMusicOnHold $true 
```

### <a name="get-license-types"></a>Ottenere i tipi di licenza

```powershell
Get-MsolAccountSku
```

### <a name="create-and-assign-resource-account"></a>Creare e assegnare un account di risorsa

**Nota**: il numero di telefono non è necessario qui perché la coda di chiamata è front-ended da un operatore automatico

- Applicationid
  - Operatore automatico: ce933385-9390-45d1-9512-c8d228074e07
  - Coda di chiamata: 11cd3e2e-fccb-42ad-ad00-878b93575e07

Nota: il tipo di licenza mostrato di seguito (PHONESYSTEM_VIRTUALUSER) deve essere elencato dal cmdlet Get-MsolAccountSku precedente.

```powershell
New-CsOnlineApplicationInstance -UserPrincipalName Facilities-RA@contoso.com -DisplayName "Facilities" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Facilities-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName "Facilities-RA@contoso.com" -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Facilities-RA@contoso.com").Identity
$callQueueID = (Get-CsCallQueue -NameFilter "Facilities").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
```
