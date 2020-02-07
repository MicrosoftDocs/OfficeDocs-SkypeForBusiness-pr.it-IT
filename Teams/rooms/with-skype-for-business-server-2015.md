---
title: Distribuire le sale di Microsoft teams con Skype for Business Server
ms.author: v-lanac
author: lanachin
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
ms.custom: ''
ms.assetid: a038e34d-8bc8-4a59-8ed2-3fc00ec33dd7
description: Leggere questo argomento per informazioni su come distribuire le sale di Microsoft teams con Skype for Business Server.
ms.openlocfilehash: ecea3e21181371ec22446c54b449ae7424517d4e
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41827884"
---
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a>Distribuire le sale di Microsoft teams con Skype for Business Server
  
Questo argomento illustra come aggiungere un account di dispositivo per le sale di Microsoft teams quando si dispone di una distribuzione locale con una sola foresta.
  
Se si dispone di una distribuzione locale con una sola foresta, con Exchange 2013 SP1 o versioni successive e Skype for Business Server 2015 o versione successiva, è possibile usare gli script di Windows PowerShell forniti per creare account di dispositivo. Se si usa una distribuzione con più insiemi di strutture, è possibile usare i cmdlet equivalenti che produrranno gli stessi risultati. Questi cmdlet sono descritti in questa sezione.

  
Prima di iniziare a distribuire le sale di Microsoft teams, assicurarsi di avere le autorizzazioni appropriate per eseguire i cmdlet associati.
  

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

   Tieni presente che $strExchangeServer è il nome di dominio completo (FQDN) del server Exchange e $strLyncFQDN è l'FQDN della distribuzione di Skype for Business Server.

2. Dopo aver stabilito una sessione, è possibile creare una nuova cassetta postale e abilitarla come RoomMailboxAccount o modificare le impostazioni per una cassetta postale della sala esistente. In questo modo l'account verrà autenticato in Microsoft teams rooms.

    Se si sta modificando una cassetta postale di risorse esistente:

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   Se si sta creando una nuova cassetta postale per le risorse:

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. È possibile impostare diverse proprietà di Exchange nell'account del dispositivo per migliorare l'esperienza di riunione per gli utenti. Puoi vedere quali proprietà devono essere impostate nella sezione proprietà di Exchange.

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. Se si decide di non avere la password in scadenza, è possibile impostarla anche con i cmdlet di Windows PowerShell. Per altre informazioni, vedere Gestione delle password.

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. Abilitare l'account in Active Directory in modo che venga autenticato in Microsoft teams rooms.

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. Abilitare l'account del dispositivo con Skype for Business Server abilitando l'account di Microsoft teams Rooms Active Directory in un pool di Skype for Business Server:

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    È necessario usare l'indirizzo SIP (Session Initiation Protocol) e il controller di dominio per il progetto

7. **Opzionale.** È anche possibile consentire a Microsoft teams Rooms di effettuare e ricevere chiamate telefoniche PSTN (Public Switched Telephone Network) abilitando VoIP aziendale per il proprio account. Enterprise Voice non è un requisito per le sale di Microsoft teams, ma se si vuole usare la funzionalità di chiamata PSTN per il client Microsoft teams rooms, ecco come abilitarlo:

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   Anche in questo caso, è necessario sostituire gli esempi di Domain controller e numero di telefono forniti con le proprie informazioni. Il valore del parametro $true rimane invariato.

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a>Esempio: configurazione dell'account room in Exchange e Skype for Business Server in locale

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

## <a name="see-also"></a>Vedere anche

[Configurare gli account per le sale di Microsoft Teams](rooms-configure-accounts.md)

[Pianificare le sale di Microsoft Teams](rooms-plan.md)
  
[Distribuire le sale di Microsoft Teams](rooms-deploy.md)
  
[Configurare una console Microsoft teams rooms](console.md)
  
[Gestire le sale di Microsoft Teams](rooms-manage.md)
