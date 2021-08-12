---
title: Distribuire Microsoft Teams Rooms con Skype for Business Server
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
description: Leggere questo argomento per informazioni su come distribuire Microsoft Teams Rooms con Skype for Business Server.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 14d942e041d11cfd95b38f4cdcc18ad614c135df9d88b3a3e55261236144bffd
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54296643"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Distribuire Microsoft Teams Rooms con Skype for Business Server
  
Questo argomento spiega come aggiungere un account del dispositivo per Microsoft Teams Rooms una distribuzione locale a foresta singola.
  
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

   Si noti che $strExchangeServer è il nome di dominio completo (FQDN) del server Exchange e $strLyncFQDN è il nome di dominio completo della distribuzione Skype for Business Server.

2. Dopo aver stabilito una sessione, si creerà una nuova cassetta postale e la si abiliterà come RoomMailboxAccount oppure si modificheranno le impostazioni per una cassetta postale della chat room esistente. In questo modo l'account verrà autenticato per Microsoft Teams Rooms.

    Se si sta modificando una cassetta postale delle risorse esistente:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Se si sta creando una nuova cassetta postale per le risorse:

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. È possibile impostare varie proprietà Exchange nell'account del dispositivo per migliorare l'esperienza di riunione per gli utenti. È possibile vedere quali proprietà devono essere impostate nella Exchange delle proprietà.

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Se si decide di non impostare la password in scadenza, è possibile impostarla anche con Windows PowerShell cmdlet. Per altre informazioni, vedere Gestione delle password.

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Abilitare l'account in Active Directory in modo che eseere autenticato Microsoft Teams Rooms.

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Abilitare l'account del dispositivo con Skype for Business Server abilitando l'account Microsoft Teams Rooms Active Directory in un pool di Skype for Business Server:

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    È necessario usare l'indirizzo SIP (Session Initiation Protocol) e il controller di dominio per il Project

7. **Facoltativo.** È anche possibile Microsoft Teams Rooms effettuare e ricevere chiamate PSTN (Public Switched Telephone Network) abilitando VoIP aziendale per l'account. VoIP aziendale non è un requisito per Microsoft Teams Rooms, ma se si vuole la funzionalità di composizione PSTN per il client di Microsoft Teams Rooms, ecco come abilitarla:

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   Anche in questo caso, è necessario sostituire il controller di dominio e gli esempi di numeri di telefono forniti con le proprie informazioni. Il valore del $true rimane lo stesso.

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

[Configurare gli account per Microsoft Teams Rooms](rooms-configure-accounts.md)

[Piano per Microsoft Teams Rooms](rooms-plan.md)
  
[Distribuire Microsoft Teams Rooms](rooms-deploy.md)
  
[Configurare una console per Microsoft Teams Rooms](console.md)
  
[Gestire Microsoft Teams Rooms](rooms-manage.md).
