---
title: Script di configurazione delle chat room di Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: a66067d2-22b0-48f1-a5d0-e0cd0ece2e5a
description: Leggi questo argomento per trovare script di esempio per il provisioning degli account di Skype Room System.
ms.openlocfilehash: 93a97b42f3b800011030787ea39cfb503767e42c
ms.sourcegitcommit: 1613e08da482ff142c990c9c9951abeb873ad964
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2021
ms.locfileid: "50569368"
---
# <a name="skype-room-system-room-setup-scripts"></a><span data-ttu-id="449a5-103">Script di configurazione delle chat room di Skype Room System</span><span class="sxs-lookup"><span data-stu-id="449a5-103">Skype Room System room setup scripts</span></span>
 
<span data-ttu-id="449a5-104">Leggi questo argomento per trovare script di esempio per il provisioning degli account di Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="449a5-104">Read this topic to find sample scripts for provisioning Skype Room System accounts.</span></span>
  
<span data-ttu-id="449a5-105">Questa sezione illustra gli script di esempio che possono essere usati per effettuare il provisioning degli account di Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="449a5-105">This section illustrates sample scripts that can be used to provision Skype Room System accounts.</span></span> <span data-ttu-id="449a5-106">Questi script sono solo a scopo illustrativo.</span><span class="sxs-lookup"><span data-stu-id="449a5-106">These scripts are only for illustrative purposes.</span></span> <span data-ttu-id="449a5-107">Devono essere utilizzati solo dopo aver consultato l'esperto IT o l'amministratore di dominio.</span><span class="sxs-lookup"><span data-stu-id="449a5-107">They should be used only after you consult with your IT expert or domain administrator.</span></span>
  
## <a name="example-setup-script-skype-for-business-and-exchange-server-on-premises"></a><span data-ttu-id="449a5-108">Script di installazione di esempio: Skype for Business e Exchange Server (locale)</span><span class="sxs-lookup"><span data-stu-id="449a5-108">Example Setup Script: Skype for Business and Exchange Server (On Premises)</span></span>

```powershell
# On Exchange 
Set-Mailbox -Identity confroom@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a 
Lync Meeting to take advantage of enhanced meeting experience from LRS"

Set-CalendarProcessing -id confroom@contoso.com -RemovePrivateProperty $false -AddOrganizerToSubject $false -AddAdditionalResponse 
$true -AdditionalResponse "This is an LRS room!" -DeleteSubject $false -AutomateProcessing AutoAccept 
# The following is used to preserve the Lync Meeting invitations - so create these based on your Lync Federated partners# Per Lync Federated Partner as a Recommended Practice to ensure Meetings show in Lync with Join#New-RemoteDomain -DomainName Microsoft.com -Name Microsoft$true#Set-RemoteDomain -Identity Microsoft -TNEFEnabled $true
Set-ADAccountPassword -Identity "conference room"# Paste the next command on its own. Enter a blank password first, then enter the new password "password" twiceEnable-ADAccount -Identity "confroom"# On LyncEnable-CsMeetingRoom -SipAddress "sip:confroom@contoso.com" -RegistrarPool cie-srv-02.contoso.com -Identity 'conference room' 
Set-CsMeetingRoom -Identity "conference room" -LineURI "tel:+14255551669;ext=1669" -EnterpriseVoiceEnabled $true
```

## <a name="example-setup-script-skype-for-business-and-exchange-server-online"></a><span data-ttu-id="449a5-109">Script di installazione di esempio: Skype for Business e Exchange Server Online</span><span class="sxs-lookup"><span data-stu-id="449a5-109">Example Setup Script: Skype for Business and Exchange Server Online</span></span>

<span data-ttu-id="449a5-110">Prima di eseguire lo script, verificare di aver esaminato i prerequisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="449a5-110">Make sure you've reviewed the following prerequisites before running the script:</span></span>
  
- <span data-ttu-id="449a5-111">Microsoft Online Services Sign-In Assistant for IT Professionals BETA</span><span class="sxs-lookup"><span data-stu-id="449a5-111">Microsoft Online Services Sign-In Assistant for IT Professionals BETA</span></span>
    
- <span data-ttu-id="449a5-112">Windows Azure Modulo di Active Directory per Windows PowerShell (versione a 64 bit) o (versione a 32 bit)</span><span class="sxs-lookup"><span data-stu-id="449a5-112">Windows Azure Active Directory Module for Windows PowerShell (64-bit version) or (32-bit version)</span></span>
    
- <span data-ttu-id="449a5-113">Modulo PowerShell di Teams</span><span class="sxs-lookup"><span data-stu-id="449a5-113">Teams PowerShell Module</span></span>
    
- <span data-ttu-id="449a5-114">Riavvia se necessario</span><span class="sxs-lookup"><span data-stu-id="449a5-114">Reboot if needed</span></span>
    
```powershell
# Note you have to enter each command one at a time and update any bold fields for your environment
$rm="LyncRoom"
$org='YourTenantName.onmicrosoft.com'
$rmURI="$rm@$org"$newpass='MyPass@word1'# This Section Signs into Remote PowerShell
$cred=Get-Credential admin@$org
$sess=New-PSSession -ConfigurationName microsoft.exchange -Credential $cred -AllowRedirection -Authentication basic -ConnectionUri https://ps.outlook.com/powershell
Import-PSSession $sess
Import-Module MicrosoftTeams
$credential = Get-Credential
Connect-MicrosoftTeams -Credential $credential
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

