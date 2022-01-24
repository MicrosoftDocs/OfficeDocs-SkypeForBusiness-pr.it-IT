---
title: Creare un operatore automatico tramite cmdlet
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: colongma
ms.topic: article
ms.assetid: 6fc2687c-0abf-43b8-aa54-7c3b2a84b67c
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
- Phone System
description: Informazioni su come configurare gli operatori automatici tramite cmdlet
ms.openlocfilehash: 1a8a105da3cfeaad0b6bc4069d877d2d8ad95796
ms.sourcegitcommit: bc686eedb37e565148d0c7a61ffa865aaca37d20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/24/2022
ms.locfileid: "62181173"
---
# <a name="create-an-auto-attendant-via-cmdlets"></a>Creare un operatore automatico tramite cmdlet

## <a name="assumptions"></a>Presupposti
1)  PowerShell è installato nel computer
- Configurare il computer per [Windows PowerShell](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
- Modulo MSTeams installato ````  (Install-Module -Name MicrosoftTeams -Force -AllowClobber) ````
- Modulo MSOnline installato ```` Install-Module -Name MSOnline -Force -AllowClobber ````
2)  Si hanno diritti di amministrazione tenant
3)  Hai acquistato Microsoft Teams Telefono
4)  Le code di chiamata a cui si fa riferimento di seguito sono già state configurate seguendo la guida alla creazione di code [di chiamata con i cmdlet di PowerShell.](create-a-phone-system-call-queue-via-cmdlets.md)
                                                                                               
Nota: Alcuni dei cmdlet a cui si fa riferimento di seguito possono far parte della versione di anteprima pubblica di Teams modulo di PowerShell.  Per altre informazioni, vedere Installare Teams anteprima pubblica di [PowerShell](teams-powershell-install.md) e vedere anche Microsoft Teams [note sulla versione di PowerShell.](teams-powershell-release-notes.md)

Gli utenti che hanno già installato il modulo MicrosoftTeams devono verificare che sia installata la versione più ````Update-Module MicrosoftTeams```` aggiornata.

## <a name="scenario"></a>Scenario

Verrà creato il flusso di chiamata dell'operatore automatico seguente:

![Diagramma del flusso delle chiamate automatico automatico creato con i cmdlet.](media/create-a-phone-system-auto-attendant-via-cmdlets.png)

Altre informazioni di configurazione:

- Operatore automatico: Contso Main
- - Operatore: Adele Vance
- - Abilita input vocali: disattivato
- - Ricerca nella directory: Nessuna
- - Festività:
- - - 1 gennaio 2022
- - - 24 dicembre 2022
- - - 25 dicembre 2022

- Operatore automatico: Chiamata contoso per nome
- - Operatore: Adele Vance
- - Fuso orario: UTC
- - Lingua: Inglese Stati Uniti
- - Abilita input vocali: attivato
- - Messaggio di saluto: Nessuno
- - Menu: TTS, "Pronuncia o immetti il nome della persona che desideri raggiungere. Per tornare al menu precedente, premere 9"
- - Ricerca nella directory: Comporre per nome
- - Ambito di chiamata: membri del supporto & vendite

## <a name="login"></a>Accesso
Verrà richiesto di immettere le credenziali di Teams di amministratore.
```
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
Connect-MsolService -Credential $credential
````

## <a name="get-operator-information"></a>Ottenere informazioni sull'operatore
````
$operatorID = (Get-CsOnlineUser -Identity “sip:adele@contoso.com”).ObjectID

$operatorEntity = New-CsAutoAttendantCallableEntity -Identity $operatorID -Type User
````

## <a name="dial-by-name-auto-attendant---resource-account-creation"></a>Chiamata in base al nome Operatore automatico - Creazione dell'account della risorsa
Nota: qui è possibile creare un account della risorsa in modo che sia possibile farvi riferimento nell'operatore automatico principale.  L'effettivo operatore automatico Chiama per nome verrà creato in un secondo momento.

### <a name="get-license-types"></a>Ottenere i tipi di licenza
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Creare e assegnare l'account delle risorse
Nota: Telefono numero non richiesto qui perché la coda di chiamata è anteriore con un Operatore automatico
- APPLICATIONID
- - Operatore automatico: ce933385-9390-45d1-9512-c8d228074e07
- - Coda di chiamata: 11cd3e2e-fccb-42ad-ad00-878b93575e07
````
New-CsOnlineApplicationInstance -UserPrincipalName ContosoDialByNameAA-RA@contoso.com -DisplayName "Contoso Dial By Name AA" -ApplicationID "ce933385-9390-45d1-9512-c8d228074e07"

Set-MsolUser -UserPrincipalName "ContosoDialByNameAA-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “ContosoDialByNameAA-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$dialByNameApplicationInstanceID = (Get-CsOnlineUser "ContosoDialByNameAA-RA@contoso.com").ObjectID
````

## <a name="contoso-main-menu-auto-attendant"></a>Menu principale contoso Operatore automatico
### <a name="create-holiday-schedules"></a>Creare pianificazioni per le festività
````
$dtr = New-CsOnlineDateTimeRange -Start "24/12/2022" -End "25/12/2022"

$christmasSchedule = New-CsOnlineSchedule -Name "Christmas" -FixedSchedule -DateTimeRanges @($dtr)

$dtr = New-CsOnlineDateTimeRange -Start "01/01/2022" -End "02/01/2022"

$newyearSchedule = New-CsOnlineSchedule -Name "New Year" -FixedSchedule -DateTimeRanges @($dtr)
````

### <a name="create-address-fax-and-email-information-prompt"></a>Richiesta di creazione di indirizzi, FAX e informazioni di posta elettronica
````
$addressPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "To repeat this information at any time press the * key. Our mailing address is: 123 Main Street, Any town, Any Place, County. Our email address is: info@contoso.com. Our fax number is: 929-555-0151"
````

### <a name="create-holiday-prompts-and-menu-options"></a>Creare richieste di festività e opzioni di menu
````
$christmasGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Thank you for calling Contoso. Our offices ae currently closed for the Christmas holiday. Our Sales and Support teams will be happy to take your call on the next business day. Regular business hours are Monday through Friday from 8:30 am to 5:00 pm and Saturday from 10:00 am to 4:00 pm eastern time. Thank you for calling Contso."

$christmasMenuOption = New-CsAutoAttendantMenuOption -Action DisconnectCall -DtmfResponse Automatic

$christmasMenu = New-CsAutoAttendantMenu -Name "Christmas Menu" -MenuOptions @($christmasMenuOption)

$christmasCallFlow = New-CsAutoAttendantCallFlow -Name "Christmas" -Greetings @($christmasGreetingPrompt) -Menu $christmasMenu

$christmasCallHandlingAssociation = New-CsAutoAttendantCallHandlingAssociation -Type Holiday -ScheduleId $christmasSchedule.Id -CallFlowId $christmasCallFlow.Id

$newyearGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Thank you for calling Contoso. Our offices ae currently closed for the New Year’s holiday. Our Sales and Support teams will be happy to take your call on the next business day. Regular business hours are Monday through Friday from 8:30 am to 5:00 pm and Saturday from 10:00 am to 4:00 pm eastern time. Thank you for calling Contso."

$newyearMenuOption = New-CsAutoAttendantMenuOption -Action DisconnectCall -DtmfResponse Automatic

$newyearMenu = New-CsAutoAttendantMenu -Name "New Year Menu" -MenuOptions @($newyearMenuOption)

$newyearCallFlow = New-CsAutoAttendantCallFlow -Name "New Year" -Greetings @($newyearGreetingPrompt) -Menu $newyearMenu

$newyearCallHandlingAssociation = New-CsAutoAttendantCallHandlingAssociation -Type Holiday -ScheduleId $newyearSchedule.Id -CallFlowId $newyearCallFlow.Id
````

### <a name="create-after-hours-schedules"></a>Creare pianificazioni after hours
````
$timerangeMoFr = New-CsOnlineTimeRange -Start 08:30 -end 17:00

$timerangeSa = New-CsOnlineTimeRange -Start 10:00 -end 16:00

$afterHoursSchedule = New-CsOnlineSchedule -Name "After Hours Schedule" -WeeklyRecurrentSchedule -MondayHours @($timerangeMoFr) -TuesdayHours @($timerangeMoFr) -WednesdayHours @($timerangeMoFr) -ThursdayHours @($timerangeMoFr) -FridayHours @($timerangeMoFr) -SaturdayHours @($timerangeSa) -Complement
````

### <a name="create-after-hours-prompts-and-menu-options"></a>Creare messaggi di richiesta e opzioni di menu after hours
````
$afterHoursGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Thank you for calling Contoso. Our offices are now closed. Regular business hours are Monday through Friday from 8:30 am to 5:00 pm and Saturday from 10:00 am to 4:00 pm eastern time."

$afterHoursMenuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt “To leave a voicemail for our sales team press 1.To leave a message for our support team press 2.If you know the name of the person you would like to reach, press 3.For our address, email and fax information press 4.”

$afterHoursMenuOption1Target = (Get-Team -displayname "Sales").GroupID

$afterHoursMenuOption1Entity = New-CsAutoAttendantCallableEntity -Identity $afterHoursMenuOption1Target -Type SharedVoiceMail -EnableTranscription -EnableSharedVoicemailSystemPromptSuppression

$afterHoursMenuOption1 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone1 -CallTarget $afterHoursMenuOption1Entity

$afterHoursMenuOption2Target = (Get-Team -displayname "Support").GroupID

$afterHoursMenuOption2Entity = New-CsAutoAttendantCallableEntity -Identity $afterHoursMenuOption2Target -Type SharedVoicemail -EnableTranscription -EnableSharedVoicemailSystemPromptSuppression

$afterHoursMenuOption2 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone2 -CallTarget $afterHoursMenuOption2Entity

$dialbynameAAOption3Target = (Get-CsOnlineUser -Identity “ContosoDialByNameAA-RA@contso.com”).ObjectID

$dialbynameAAMenuOption3Entity = New-CsAutoAttendantCallableEntity -Identity $dialbynameAAOption3Target -Type applicationendpoint

$dialbynameAAMenuOption3 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone3 -CallTarget $dialbynameAAMenuOption3Entity

$afterHoursMenuOption4 = New-CsAutoAttendantMenuOption -Action Announcement -DtmfResponse Tone4 -Prompt $addressPrompt
````

### <a name="create-after-hours-menu-and-call-flow"></a>Menu Crea dopo l'ora e Flow
````
$afterHoursMenu = New-CsAutoAttendantMenu -Name "After Hours Menu" -MenuOptions @($afterHoursMenuOption1, $afterHoursMenuOption2, $dialbynameAAMenuOption3, $afterHoursMenuOption4) -Prompt $afterHoursMenuPrompt

$afterHoursCallFlow = New-CsAutoAttendantCallFlow -Name "After Hours Call Flow" -Greetings @($afterHoursGreetingPrompt) -Menu $afterHoursMenu

$afterHoursCallHandlingAssociation = New-CsAutoAttendantCallHandlingAssociation -Type AfterHours -ScheduleId $afterHoursSchedule.Id -CallFlowId $afterHoursCallFlow.Id
````

### <a name="create-open-hours-prompts-and-menu-options"></a>Creare prompt per l'orario di apertura e opzioni di menu
````
$openHoursGreetingPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt " Thank you for calling Contoso."

$openHoursMenuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt “For Sales press 1. For Support press 2. If you know the name of the person you would like to reach, press 3. For our address, email and fax information, press 4. For all other inquiries press 0 to speak with the operator.”

$openHoursMenuOption1Target = (Get-CsOnlineUser "Sales-RA@contoso.com").ObjectID

$openHoursMenuOption1Entity = New-CsAutoAttendantCallableEntity -Identity $openHoursMenuOption1Target -Type applicationendpoint

$openHoursMenuOption1 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone1 -CallTarget $openHoursMenuOption1Entity

$openHoursMenuOption2Target = (Get-CsOnlineUser "Support-RA@contoso.com").ObjectID

$openHoursMenuOption2Entity = New-CsAutoAttendantCallableEntity -Identity $openHoursMenuOption2Target -Type applicationendpoint

$openHoursMenuOption2 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone2 -CallTarget $openHoursMenuOption2Entity

$openHoursMenuOption4 = New-CsAutoAttendantMenuOption -Action Announcement -DtmfResponse Tone4 -Prompt $addressPrompt

$openHoursMenuOption0 = New-CsAutoAttendantMenuOption -Action TransferCallToOperator -DtmfResponse Tone0
````

### <a name="create-open-hours-menu"></a>Menu Crea orari aperti
````
$openHoursMenu = New-CsAutoAttendantMenu -Name "Open Hours Menu" -MenuOptions @($openHoursMenuOption1, $openHoursMenuOption2, $dialbynameAAMenuOption3, $openHoursMenuOption4, $openHoursMenuOption0) -Prompt $openHoursMenuPrompt

$openHoursCallFlow = New-CsAutoAttendantCallFlow -Name "Open Hours Call Flow" -Greetings @($openHoursGreetingPrompt) -Menu $openHoursMenu
````

### <a name="create-auto-attendant"></a>Creare Operatore automatico
````
$autoAttendant = New-CsAutoAttendant -Name “Contoso Main” -DefaultCallFlow $openHoursCallFlow -CallFlows @($afterHoursCallFlow, $christmasCallFlow, $newyearCallFlow) -CallHandlingAssociations @($afterHoursCallHandlingAssociation, $christmasCallHandlingAssociation, $newyearCallHandlingAssociation) -LanguageId “en-US” -TimeZoneId “Eastern Standard Time” -Operator $operatorEntity
````

### <a name="get-license-types"></a>Ottenere i tipi di licenza
````
Get-MsolAccountSku
````

### <a name="create-and-assign-resource-account"></a>Creare e assegnare l'account delle risorse
Nota: Telefono numero non richiesto qui perché la coda di chiamata è anteriore con un Operatore automatico
- APPLICATIONID
- - Operatore automatico: ce933385-9390-45d1-9512-c8d228074e07
- - Coda di chiamata: 11cd3e2e-fccb-42ad-ad00-878b93575e07
````
New-CsOnlineApplicationInstance -UserPrincipalName ContosoMainAA-RA@contoso.com -DisplayName "Contoso Main AA" -ApplicationID "ce933385-9390-45d1-9512-c8d228074e07"

Set-MsolUser -UserPrincipalName "ContosoMainAA-RA@contoso.com" -UsageLocation US

Set-MsolUserLicense -UserPrincipalName “ContosoMainAA-RA@contoso.com” -AddLicenses "contoso:PHONESYSTEM_VIRTUALUSER"

$applicationInstanceID = (Get-CsOnlineUser "ContosoMainAA-RA@contoso.com").ObjectID

$autoAttendantID = (Get-CsAutoAttendant -NameFilter "Contoso Main").Identity

New-CsOnlineApplicationInstanceAssociation -Identities @($applicationInstanceID) -ConfigurationID $autoAttendantID -ConfigurationType AutoAttendant
````

### <a name="get-list-of-unassigned-service-numbers"></a>Ottenere l'elenco dei numeri di servizio non assegnati
````
Get-CsOnlineTelephoneNumber -IsNotAssigned -InventoryType Service
````

#### <a name="assign-available-phone-number"></a>Assegnare il numero di telefono disponibile
Nota: la posizione di utilizzo assegnata al numero di telefono deve corrispondere alla posizione di utilizzo assegnata all'account della risorsa.

````
Set-CsPhoneNumberAssignment -Identity ContosoMainAA-RA@contoso.com -PhoneNumber +{spare number from output of above command} -PhoneNumberType CallingPlan
````

## <a name="dial-by-name-auto-attendant---completion"></a>Chiamata per nome Operatore automatico - Completamento
### <a name="create-dial-scope"></a>Creare l'ambito di chiamata
````
$salesGroupID = Find-CsGroup -SearchQuery "Sales" | % { $_.Id }

$supportGroupID = Find-CsGroup -SearchQuery "Support" | % { $_.Id }

$dialScope = New-CsAutoAttendantDialScope -GroupScope -GroupIds @($salesGroupID, $supportGroupID)
````

### <a name="create-prompts-and-menu-options"></a>Creare prompt e opzioni di menu
````
$dialByNameMenuPrompt = New-CsAutoAttendantPrompt -TextToSpeechPrompt "Please say or enter the name of the person you would like to reach. To return to the previous menu press 9”

$dialByNameMenuOption9Target = (Get-CsOnlineUser "ContosoMainAA-RA@contoso.com").ObjectID

$dialByNameMenuOption9Entity = New-CsAutoAttendantCallableEntity -Identity $dialByNameMenuOption9Target -Type applicationendpoint

$dialByNameMenuOption9 = New-CsAutoAttendantMenuOption -Action TransferCallToTarget -DtmfResponse Tone9 -CallTarget $dialByNameMenuOption9Entity

$dialByNameMenu = New-CsAutoAttendantMenu -Name "Contoso Dial By Name AA" -MenuOptions @($dialByNameMenuOption9) -Prompt $dialByNameMenuPrompt

$dialByNameMenu = New-CsAutoAttendantMenu -Name "Contoso Dial By Name AA" -MenuOptions @($dialByNameMenuOption9) -Prompt $dialByNameMenuPrompt -EnableDialByName -DirectorySearchMethod ByName

$dialByNameCallFlow = New-CsAutoAttendantCallFlow -Name "Contoso Dial By Name Call Flow" -Menu $dialByNameMenu

$dialByNameAutoAttendant = New-CsAutoAttendant -Name “Contoso Dial By Name” -DefaultCallFlow $dialByNameCallFlow -LanguageId “en-US” -TimeZoneId “UTC” -Operator $operatorEntity -EnableVoiceResponse -InclusionScope $dialScope
````

### <a name="assign-resource-account"></a>Assegna account risorsa
````
New-CsOnlineApplicationInstanceAssociation -Identities @($dialByNameApplicationInstanceID) -ConfigurationID $dialByNameAutoAttendant.Id -ConfigurationType AutoAttendant
````
