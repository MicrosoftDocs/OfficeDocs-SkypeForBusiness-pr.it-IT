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
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.callqueues.overview"
- Phone System
- seo-marvel-apr2020
description: Informazioni su come configurare le code di chiamata tramite cmdlet
ms.openlocfilehash: aa3330af2a47c87fc71f63396b84f8ad017e19b5
ms.sourcegitcommit: 79dfda39db208cf943d0f7b4906883bb9d034281
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/09/2022
ms.locfileid: "62457446"
---
# <a name="create-a-call-queue-via-cmdlets"></a>Creare una coda di chiamata tramite cmdlet

## <a name="assumptions"></a>Presupposti
1)  PowerShell è installato nel computer
- Configurare il computer [per Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
- Modulo MSTeams installato ````  (Install-Module -Name MicrosoftTeams -Force -AllowClobber) ````
- Modulo MSOnline installato ```` Install-Module -Name MSOnline -Force -AllowClobber ````
2)  Si hanno diritti di amministrazione tenant
3)  Hai acquistato Microsoft Teams Telefono
4)  Gli agenti, le liste di distribuzione e i canali Teams a cui si fa riferimento di seguito sono già stati creati

Nota: il cmdlet Teams Channel usato di seguito fa parte della versione di anteprima pubblica di Teams modulo di PowerShell.  Per altre informazioni, vedere [Installare Teams anteprima pubblica di PowerShell](teams-powershell-install.md) e vedere anche Microsoft Teams [note sulla versione di PowerShell](teams-powershell-release-notes.md).

Gli utenti che hanno già installato il modulo MicrosoftTeams ````Update-Module MicrosoftTeams```` devono verificare che sia installata la versione più aggiornata.


## <a name="scenario"></a>Scenario

Verranno create le tre code di chiamata seguenti:

Informazioni sulla coda di chiamata di vendita:
- Davanti a Operatore automatico: Sì
- Chiamate dirette da PSTN: No
- Lingua: Inglese Stati Uniti
- Messaggio di saluto: Nessuno
- Musica blocco: Riprodurre un file audio
- - Nome file: sales-hold-in-queue-music.wav
- Rispondimento chiamata: Utenti
- - Bill@contoso.com
- - Mary@contoso.com
- Modalità conferenza: attivata
- Metodo di instradamento: Operatore
- Routing basato sulla presenza: disattivato
- Gli agenti di chiamata possono rifiutare esplicitamente di effettuare chiamate: Sì
- Tempo di avviso dell'agente di chiamata: 15
- Gestione dell'overflow delle chiamate: 200
- - Reindirizza a: Adele@contoso.com
- Gestione del timeout delle chiamate: 120 secondi
- - Reindirizza a: Adele@contoso.com

Informazioni sulla coda di chiamata di supporto:
- Davanti a Operatore automatico: Sì
- Chiamate dirette da PSTN: No
-   Lingua: Inglese Regno Unito
-   Messaggio di saluto: Riprodurre un file audio
-   - Nome file: support-greeting.wav
-   Musica blocco: Riprodurre un file audio
-   - Nome file: support-hold-in-queue-music.wav
-   Risposta alle chiamate: lista di distribuzione di supporto
-   - Support@contoso.com
-   Modalità conferenza: attivata
-   Metodo di routing: Inattività più lunga
-   Routing basato sulla presenza: N/D : inattivo per impostazione predefinita a causa dell'inattività più lunga
-   Gli agenti di chiamata possono rifiutare esplicitamente di effettuare chiamate: No
-   Tempo di avviso dell'agente di chiamata: 15
-   Gestione dell'overflow delle chiamate: 200
-   - Reindirizzamento: Supporto della segreteria telefonica condivisa
- - -   Riprodurre un file audio (support-shared-voicemail-greeting.wav)
- - -   Trascrizione abilitata
-   Gestione del timeout delle chiamate: 45 minuti
-   - Reindirizzamento: Supporto della segreteria telefonica condivisa
- - - TTS: "Siamo spiacenti di averti tenuto in attesa e ora stai trasferendo la chiamata alla segreteria telefonica".
- - - Trascrizione abilitata


Informazioni sulla coda di chiamata collaborativa delle strutture:
- Davanti a Operatore automatico: No
- Chiamate dirette da PSTN: No (solo chiamate interne)
-   Lingua: francese FR
-   Messaggio di saluto: Nessuno
-   Musica blocco: impostazione predefinita
-   Risposta alle chiamate: Team: Strutture
-   Call Answering Channel: Help Desk
-   - Proprietario del canale: Fred@contoso.com
-   Modalità conferenza: attivata
-   Metodo di routing: Round Robin
-   Routing basato sulla presenza: on
-   Gli agenti di chiamata possono rifiutare esplicitamente di effettuare chiamate: No
-   Tempo di avviso dell'agente di chiamata: 15
-   Gestione dell'overflow delle chiamate: 200
-   - Disconnetti
-   Gestione del timeout delle chiamate: 45 minuti
-   - Disconnetti


## <a name="login"></a>Accesso
Verrà richiesto di immettere le credenziali di Teams di amministratore.
```
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
````

## <a name="sales-queue"></a>Coda di vendita
### <a name="create-audio-files"></a>Creare file audio
Sostituire "d:\\" con il percorso in cui sono archiviati i file wav nel computer.

````
$content = Get-Content “d:\sales-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSalesHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "sales-hold-in-queue-music.wav" -Content $content).ID
````

### <a name="get-users-id"></a>Ottenere l'ID utente
````
$userAdeleID = (Get-CsOnlineUser -Identity “sip:adele@contoso.com”).ObjectID
$userSalesBillID = (Get-CsOnlineUser -Identity “sip:bill@contoso.com”).ObectID
$userSalesMaryID = (Get-CsOnlineUser -Identity “sip:mary@contoso.com”).ObjectID
````

### <a name="get-list-of-supported-languages"></a>Ottenere l'elenco delle lingue supportate
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Crea coda di chiamata
````
New-CsCallQueue -Name “Sales” -AgentAlertTime 15 -AllowOptOut $true -MusicOnHoldAudioFileID $audioFileSalesHoldInQueueMusicID -OverflowAction Forward -OverflowActionTarget $userAdeleID -OverflowThreshold 200 -TimeoutAction Forward -TimeoutActionTarget $userAdeleID -TimeoutThreshold 120 -RoutingMethod Attendant -ConferenceMode $true -User @($userSalesBillID, $userSalesMaryID) -LanguageID “en-US”
````

### <a name="get-license-types"></a>Ottenere i tipi di licenza
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Creare e assegnare un account della risorsa
Nota: Telefono numero di telefono non richiesto qui perché la coda di chiamata è anteriore con un Operatore automatico
- APPLICATIONID
- - Operatore automatico: ce933385-9390-45d1-9512-c8d228074e07
- - Coda di chiamata: 11cd3e2e-fccb-42ad-ad00-878b93575e07

Nota: il tipo di licenza mostrato di seguito (PHONESYSTEM_VIRTUALUSER) deve essere elencato dal cmdlet Get-MsolAccountSku precedente.

````
New-CsOnlineApplicationInstance -UserPrincipalName Sales-RA@contoso.com -DisplayName "Sales" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Sales-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Sales-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Sales-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Sales").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="support-queue"></a>Coda di supporto
### <a name="create-audio-files"></a>Creare file audio
Sostituire "d:\\" con il percorso in cui sono archiviati i file wav nel computer.

````
$content = Get-Content “d:\support-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-greeting.wav" -Content $content).ID

$content = Get-Content “d:\support-hold-in-queue-music.wav” -Encoding byte -ReadCount 0
$audioFileSupportHoldInQueueMusicID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-hold-in-queue-music.wav" -Content $content).ID

$content = Get-Content “d:\support-shared-voicemail-greeting.wav” -Encoding byte -ReadCount 0
$audioFileSupportSharedVoicemailGreetingID = (Import-CsOnlineAudioFile -ApplicationID HuntGroup -FileName "support-shared-voicemail-greeting.wav" -Content $content).ID
````

### <a name="get-support-team-group-id"></a>Ottenere l'ID gruppo del team di supporto
````
$teamSupportID = (Get-Team -displayname "Support").GroupID
````

### <a name="get-list-of-supported-languages"></a>Ottenere l'elenco delle lingue supportate
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Crea coda di chiamata
````
New-CsCallQueue -Name “Support” -AgentAlertTime 15 -AllowOptOut $false -DistributionLists $teamSupportID -WelcomeMusicAudioFileID $audioFileSupportGreetingID -MusicOnHoldAudioFileID $audioFileSupportHoldInQueueMusicID -OverflowAction SharedVoicemail -OverflowActionTarget $teamSupportID -OverflowThreshold 200 -OverflowSharedVoicemailAudioFilePrompt $audioFileSupportSharedVoicemailGreetingID -EnableOverflowSharedVoicemailTranscription $true -TimeoutAction SharedVoicemail -TimeoutActionTarget $teamSupportID -TimeoutThreshold 2700 -TimeoutSharedVoicemailTextToSpeechPrompt "We're sorry to have kept you waiting and are now transferring your call to voicemail." -EnableTimeoutSharedVoicemailTranscription $true -RoutingMethod LongestIdle -ConferenceMode $true -LanguageID “en-US”
````

### <a name="get-license-types"></a>Ottenere i tipi di licenza
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Creare e assegnare un account della risorsa
Nota: Telefono numero non richiesto qui perché la coda di chiamata è front-ended da un Operatore automatico
- APPLICATIONID
- - Operatore automatico: ce933385-9390-45d1-9512-c8d228074e07
- - Coda di chiamata: 11cd3e2e-fccb-42ad-ad00-878b93575e07

Nota: il tipo di licenza mostrato di seguito (PHONESYSTEM_VIRTUALUSER) deve essere elencato dal cmdlet Get-MsolAccountSku precedente.

````
New-CsOnlineApplicationInstance -UserPrincipalName Support-RA@contoso.com -DisplayName "Support" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Support-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Support-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Support-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Support").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````


## <a name="facilities-collaborative-calling-queue"></a>Coda di chiamate collaborative per le strutture
### <a name="get-facilities-team-group-id"></a>ID del gruppo di team Get Facilities
````
$teamFacilitiesGroupID = (Get-Team -DisplayName "Facilities").GroupID
````

### <a name="get-facilities-help-desk-team-channel-id"></a>Ottenere l'ID del canale del team help desk di Facilities
````
Get-TeamChannel -GroupId $teamFacilitiesGroupID
$teamFacilitiesHelpDeskChannelID = "{assign ID from output of above command}"
````

### <a name="get-facilities-help-desk-channel-owner-user-id"></a>Ottenere l'ID utente del proprietario del canale Help Desk di Facilities
````
$teamFacilitiesHelpDeskChannelUserID = (Get-TeamChannelUser -GroupId $teamFacilitiesGroupID -DisplayName "Help Desk" -Role Owner).UserId
````

### <a name="get-on-behalf-of-calling-resource-account-id"></a>Ottenere per conto dell'ID account della risorsa chiamante
````
$oboResourceAccountID = (Get-CsOnlineUser -Identity "MainAA-RA@contoso.com").ObjectID
````

### <a name="get-list-of-supported-languages"></a>Ottenere l'elenco delle lingue supportate
````
Get-CsAutoAttendantSupportedLanguage
````

### <a name="create-call-queue"></a>Crea coda di chiamata
````
New-CsCallQueue -Name “Facilities” -AgentAlertTime 15 -AllowOptOut $false -ChannelId $teamFacilitiesHelpDeskChannelID -ChannelUserObjectId $teamFacilitiesHelpDeskChannelUserID  -ConferenceMode $true -DistributionList $teamFacilitiesGroupID -LanguageID “fr-FR” -OboResourceAccountIds $oboResourceAccountID -OverflowAction DisconnectWithBusy -OverflowThreshold 200 -RoutingMethod RoundRobin -TimeoutAction Disconnect -TimeoutThreshold 2700 -UseDefaultMusicOnHold $true 
````

### <a name="get-license-types"></a>Ottenere i tipi di licenza
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Creare e assegnare un account della risorsa
Nota: Telefono numero non richiesto qui perché la coda di chiamata è front-ended da un Operatore automatico
- APPLICATIONID
- - Operatore automatico: ce933385-9390-45d1-9512-c8d228074e07
- - Coda di chiamata: 11cd3e2e-fccb-42ad-ad00-878b93575e07

Nota: il tipo di licenza mostrato di seguito (PHONESYSTEM_VIRTUALUSER) deve essere elencato dal cmdlet Get-MsolAccountSku precedente.

````
New-CsOnlineApplicationInstance -UserPrincipalName Facilities-RA@contoso.com -DisplayName "Facilities" -ApplicationID "11cd3e2e-fccb-42ad-ad00-878b93575e07"

Set-MsolUser -UserPrincipalName "Facilities-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “Facilities-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser -Identity "Facilities-RA@contoso.com").ObjectID
$callQueueID = (Get-CsCallQueue -NameFilter "Facilities").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $callQueueID -ConfigurationType CallQueue
````
