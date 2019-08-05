---
title: Script di configurazione della sala di Skype room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a66067d2-22b0-48f1-a5d0-e0cd0ece2e5a
description: Leggere questo argomento per trovare gli script di esempio per il provisioning degli account di Skype room System.
ms.openlocfilehash: e4b146346d7afe69746cf7046c0ee156ee9ff0da
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192047"
---
# <a name="skype-room-system-room-setup-scripts"></a><span data-ttu-id="85b42-103">Script di configurazione della sala di Skype room System</span><span class="sxs-lookup"><span data-stu-id="85b42-103">Skype Room System room setup scripts</span></span>
 
<span data-ttu-id="85b42-104">Leggere questo argomento per trovare gli script di esempio per il provisioning degli account di Skype room System.</span><span class="sxs-lookup"><span data-stu-id="85b42-104">Read this topic to find sample scripts for provisioning Skype Room System accounts.</span></span>
  
<span data-ttu-id="85b42-105">Questa sezione illustra gli script di esempio che possono essere usati per eseguire il provisioning degli account di sistema room Skype.</span><span class="sxs-lookup"><span data-stu-id="85b42-105">This section illustrates sample scripts that can be used to provision Skype Room System accounts.</span></span> <span data-ttu-id="85b42-106">Questi script sono solo per scopi illustrativi e devono essere usati solo dopo aver consultato l'esperto IT o l'amministratore del dominio.</span><span class="sxs-lookup"><span data-stu-id="85b42-106">These scripts are for illustrative purposes only and should be used only after consulting with your IT expert or domain administrator.</span></span>
  
## <a name="example-setup-script-skype-for-business-and-exchange-server-on-premises"></a><span data-ttu-id="85b42-107">Script di configurazione di esempio: Skype for business ed Exchange Server (locale)</span><span class="sxs-lookup"><span data-stu-id="85b42-107">Example Setup Script: Skype for Business and Exchange Server (On Premises)</span></span>

```
# On Exchange 
Set-Mailbox -Identity confroom@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a 
Lync Meeting to take advantage of enhanced meeting experience from LRS"

Set-CalendarProcessing -id confroom@contoso.com -RemovePrivateProperty $false -AddOrganizerToSubject $false -AddAdditionalResponse 
$true -AdditionalResponse "This is an LRS room!" -DeleteSubject $false -AutomateProcessing AutoAccept 
# The following is used to preserve the Lync Meeting invitations - so create these based on your Lync Federated partners# Per Lync Federated Partner as a Recommended Practice to ensure Meetings show in Lync with Join#New-RemoteDomain -DomainName Microsoft.com -Name Microsoft$true#Set-RemoteDomain -Identity Microsoft -TNEFEnabled $true
Set-ADAccountPassword -Identity "conference room"# Paste the next command on its own. Enter a blank password first, then enter the new password "password" twiceEnable-ADAccount -Identity "confroom"# On LyncEnable-CsMeetingRoom -SipAddress "sip:confroom@contoso.com" -RegistrarPool cie-srv-02.contoso.com -Identity 'conference room' 
Set-CsMeetingRoom -Identity "conference room" -LineURI "tel:+14255551669;ext=1669" -EnterpriseVoiceEnabled $true
```

## <a name="example-setup-script-skype-for-business-and-exchange-server-online"></a><span data-ttu-id="85b42-108">Script di configurazione di esempio: Skype for business ed Exchange Server online</span><span class="sxs-lookup"><span data-stu-id="85b42-108">Example Setup Script: Skype for Business and Exchange Server Online</span></span>

<span data-ttu-id="85b42-109">Verificare di avere esaminato i prerequisiti seguenti prima di eseguire lo script:</span><span class="sxs-lookup"><span data-stu-id="85b42-109">Make sure you've reviewed the following prerequisites before running the script:</span></span>
  
- <span data-ttu-id="85b42-110">Assistente per l'accesso ai Microsoft Online Services per professionisti IT BETA</span><span class="sxs-lookup"><span data-stu-id="85b42-110">Microsoft Online Services Sign-In Assistant for IT Professionals BETA</span></span>
    
- <span data-ttu-id="85b42-111">Modulo di Windows Azure Active Directory per Windows PowerShell (versione a 64 bit) o (versione 32 bit)</span><span class="sxs-lookup"><span data-stu-id="85b42-111">Windows Azure Active Directory Module for Windows PowerShell (64-bit version) or (32-bit version)</span></span>
    
- <span data-ttu-id="85b42-112">Modulo di Windows PowerShell per Lync Online</span><span class="sxs-lookup"><span data-stu-id="85b42-112">Windows PowerShell Module for Lync Online</span></span>
    
- <span data-ttu-id="85b42-113">Riavviare se necessario</span><span class="sxs-lookup"><span data-stu-id="85b42-113">Reboot if needed</span></span>
    
```
# Note you have to enter each command one at a time and update any bold fields for your environment
$rm="LyncRoom"
$org='YourTenantName.onmicrosoft.com'
$rmURI="$rm@$org"$newpass='MyPass@word1'# This Section Signs into Remote PowerShell
$cred=Get-Credential admin@$org
$sess=New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication basic -ConnectionUri https://ps.outlook.com/powershell
Import-PSSession $sess
Import-Module LyncOnlineConnector
$cssess=New-CsOnlineSession -Credential $cred
Import-PSSession $cssess -AllowClobber
Connect-MsolService -Credential $cred# This Section Create the Calendar Mailbox and Enables it for Lync
New-Mailbox -MicrosoftOnlineServicesID $rmURI -room -Name $rm -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
 -EnableRoomMailboxAccount $true

Set-CalendarProcessing -Identity $rmURI -DeleteSubject $false -AutomateProcessing AutoAccept 
Set-CalendarProcessing -Identity $rmURI -RemovePrivateProperty $false -AddOrganizerToSubject $false -AddAdditionalResponse $true -AdditionalResponse
 "This is an LRS room!"# Configure the Account to Not Expire
Set-MsolUser -UserPrincipalName $rm -PasswordNeverExpires $true# You need to detect your Lync Pool Registrar name. Using a normal Offic365/LyncOnline user account from your tenant, run the next command and update the RegistrarPool value for the second command coming up
Get-CsOnlineUser -Identity 'admin@YourTenantName.onmicrosoft.com' | fl *registrar*# Update with above result
Enable-CsMeetingRoom -Identity $rmURI -RegistrarPool "sippoolsn20a07.infra.lync.com" -SipAddressType EmailAddress
# If the previous command fails with an error regarding the account name not being found you might need to wait and try again in a few minutes. If you wait too long, you'll need to sign in again to remote PowerShell as detailed above.
```


