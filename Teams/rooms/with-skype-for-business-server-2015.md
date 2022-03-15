---
title: Distribuire Microsoft Teams Rooms con Skype for Business Server
ms.author: czawideh
author: cazawideh
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms con Skype for Business Server.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 358fa9295ec150f9c57a18252c76d309078b8e29
ms.sourcegitcommit: a894e9397050e09bfaab02e700e943a3bbeb1302
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2022
ms.locfileid: "63503483"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Distribuire Microsoft Teams Rooms con Skype for Business Server
  
Questo argomento spiega come aggiungere un account di risorsa per Microsoft Teams Rooms una distribuzione locale a foresta singola.
  
Se si ha una distribuzione a foresta singola e locale con Exchange 2013 SP1 o versione successiva e Skype for Business Server 2015 o versione successiva, è possibile usare gli script di Windows PowerShell forniti per creare gli account dei dispositivi. Se si usa una distribuzione a più foreste, è possibile usare cmdlet equivalenti che produrranno gli stessi risultati. Questi cmdlet sono descritti in questa sezione.
  
Prima di iniziare a distribuire Microsoft Teams Rooms, assicurarsi di avere le autorizzazioni appropriate per eseguire i cmdlet associati.
  

   ``` Powershell
   Set-ExecutionPolicy Unrestricted
   $org='contoso.com'
   $cred=Get-Credential $admin@$org
   $sessExchange = New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication Kerberos -ConnectionUri
   "http://$strExchangeServer/powershell" -WarningAction SilentlyContinue
   $sessLync = New-PSSession -Credential $cred -ConnectionURI "https://$strLyncFQDN/OcsPowershell" -AllowRedirection -WarningAction SilentlyContinue
   Import-PSSession $sessExchange
   Import-PSSession $sessLync
   ```

   Si noti che $strExchangeServer è il nome di dominio completo (FQDN) del server di Exchange e $strLyncFQDN è l'FQDN della distribuzione Skype for Business Server.

2. Dopo aver stabilito una sessione, si creerà una nuova cassetta postale e la si abiliterà come RoomMailboxAccount oppure si modificheranno le impostazioni per una cassetta postale della chat room esistente. In questo modo l'account verrà autenticato per Microsoft Teams Rooms.

    Se si sta modificando una cassetta postale delle risorse esistente:

   ``` Powershell
   Set-Mailbox -Identity 'ConferenceRoome01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Se si sta creando una nuova cassetta postale per le risorse:

   ``` Powershell
   New-Mailbox -UserPrincipalName ConferenceRoom01@contoso.com -Alias ConferenceRoom01 -Name "Conference Room 01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. È possibile impostare varie proprietà Exchange di riunione nell'account Teams Rooms risorsa per migliorare l'esperienza della riunione per gli utenti. È possibile vedere quali proprietà devono essere impostate nella sezione Exchange proprietà.

   ``` Powershell
   Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"
   ```

4. Disattivare la scadenza della password per l'account della risorsa.

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -PasswordNeverExpires $true
   ```

5. Abilitare l'account della risorsa in Active Directory in modo che eseere autenticato Microsoft Teams Rooms.

   ``` Powershell
   Set-AdUser ConferenceRoom01@contoso.com -Enabled $true
   ```

6. Abilitare l'account delle risorse con Skype for Business Server abilitando l'account di Active Directory Microsoft Teams Rooms in un pool Skype for Business Server:

   ``` Powershell
   Enable-CsMeetingRoom -Identity ConferenceRoom01 -SipAddress sip:ConferenceRoom01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com 
   ```

    Modificare gli `-DomainController` attributi e `-RegistrarPool` in valori appropriati per l'ambiente.

7. **Facoltativo.** È anche possibile Microsoft Teams Rooms effettuare e ricevere chiamate PSTN (Public Switched Telephone Network) abilitando VoIP aziendale per l'account. VoIP aziendale non è un requisito per Microsoft Teams Rooms, ma se si vuole la funzionalità di composizione PSTN per Microsoft Teams Rooms, ecco come abilitarla:

   ``` Powershell
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -Identity ConferenceRoom01 -DomainController DC-ND-001.contoso.com -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName VP1
   Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName DP1
   ```

   Anche in questo caso, è necessario sostituire il controller di dominio e gli esempi di numeri di telefono forniti con le proprie informazioni. Il valore del $true rimane lo stesso. Sarà anche necessario sostituire i nomi dei criteri vocali e dei criteri del piano di chiamata.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Esempio: configurazione dell'account della sala in Exchange e Skype for Business Server locale

``` Powershell
New-Mailbox -Alias ConferenceRoom01 -Name "Conference Room 01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force) -UserPrincipalName ConferenceRoom01@contoso.com

Set-CalendarProcessing -Identity ConferenceRoom01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false -RemovePrivateProperty $false
Set-CalendarProcessing -Identity ConferenceRoom01 -AddAdditionalResponse $true -AdditionalResponse "This is a Microsoft Teams and Skype for Business meeting room!"

Enable-CsMeetingRoom -Identity ConferenceRoom01@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity ConferenceRoom01 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -Identity ConferenceRoom01 -PolicyName dk
Grant-CsDialPlan -Identity ConferenceRoom01 -PolicyName e15dp2.contoso.com
```

## <a name="related-topics"></a>Argomenti correlati

[Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Distribuire Microsoft Teams Rooms](rooms-deploy.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).
