---
title: Distribuire sale di Microsoft Teams con Skype for Business Server
ms.author: dstrome
author: dstrome
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Leggere questo argomento per informazioni su come distribuire sale di Microsoft Teams con Skype for Business Server.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ee33ec1ded7e8461f629c4552236ee60828a168
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662261"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Distribuire sale di Microsoft Teams con Skype for Business Server
  
Questo argomento spiega come aggiungere un account dispositivo per le sale di Microsoft Teams quando si ha una distribuzione locale a un'unica foresta.
  
Se si ha una distribuzione locale a una foresta singola con Exchange 2013 SP1 o versione successiva e Skype for Business Server 2015 o versione successiva, è possibile usare gli script Windows PowerShell forniti per creare gli account dei dispositivi. Se si usa una distribuzione a più foreste, è possibile usare cmdlet equivalenti che produrranno gli stessi risultati. Questi cmdlet sono descritti in questa sezione.

  
Prima di iniziare a distribuire le sale di Microsoft Teams, assicurarsi di avere le autorizzazioni appropriate per eseguire i cmdlet associati.
  

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

   Si noti $strExchangeServer è il nome di dominio completo (FQDN) del server Exchange e $strLyncFQDN è l'FQDN della distribuzione di Skype for Business Server.

2. Dopo aver stabilito una sessione, è necessario creare una nuova cassetta postale e abilitarla come RoomMailboxAccount oppure modificare le impostazioni di una cassetta postale della sala esistente. In questo modo l'account verrà autenticato nelle sale di Microsoft Teams.

    Se si sta modificando una cassetta postale delle risorse esistente:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Se si sta creando una nuova cassetta postale delle risorse:

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. È possibile impostare varie proprietà di Exchange sull'account del dispositivo per migliorare l'esperienza di riunione per le persone. È possibile vedere quali proprietà devono essere impostate nella sezione Delle proprietà di Exchange.

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Se si decide di non scadere la password, è possibile impostarla anche con Windows PowerShell cmdlet. Per altre informazioni, vedere Gestione delle password.

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Abilitare l'account in Active Directory in modo che verrà autenticato nelle sale di Microsoft Teams.

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Abilitare l'account del dispositivo con Skype for Business Server abilitando l'account Microsoft Teams Rooms Active Directory in un pool Skype for Business Server:

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    È necessario usare l'indirizzo SIP (Session Initiation Protocol) e il controller di dominio per il

7. **Facoltativo.** È anche possibile consentire alle chat room di Microsoft Teams di effettuare e ricevere chiamate pstN (Public Switched Telephone Network), abilitando l VoIP aziendale per il proprio account. VoIP aziendale non è un requisito per Microsoft Teams Rooms, ma se si vuole la funzionalità di composizione PSTN per il client Sale di Microsoft Teams, ecco come abilitarla:

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   Anche in questo caso, è necessario sostituire gli esempi di controller di dominio e numeri di telefono forniti con le proprie informazioni. Il valore $true parametro rimane uguale.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Esempio: configurazione dell'account della sala in Exchange e Skype for Business Server locale

``` Powershell
New-Mailbox -Alias rigel1 -Name "Rigel 1" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String "" -AsPlainText -Force)
-UserPrincipalName rigel1@contoso.com

Set-CalendarProcessing -Identity rigel1 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments $false -DeleteSubject $false
-RemovePrivateProperty $false
Set-CalendarProcessing -Identity rigel1 -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"

Enable-CsMeetingRoom -Identity rigel1@contoso.com -RegistrarPool cs3.contoso.com -SipAddressType EmailAddress
Set-CsMeetingRoom -Identity rigel1 -EnterpriseVoiceEnabled $true -LineURI tel:+155555555555
Grant-CsVoicePolicy -PolicyName dk -Identity rigel1
Grant-CsDialPlan -PolicyName e15dp2.contoso.com -Identity rigel1
```

## <a name="related-topics"></a>Argomenti correlati

[Configurare gli account per le sale di Microsoft Teams](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Distribuire Microsoft Teams Rooms](rooms-deploy.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).
