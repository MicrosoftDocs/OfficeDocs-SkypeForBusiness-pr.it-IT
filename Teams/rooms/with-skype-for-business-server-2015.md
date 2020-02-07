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
# <a name="deploy-microsoft-teams-rooms-with-skype-for-business-server"></a><span data-ttu-id="2b084-103">Distribuire le sale di Microsoft teams con Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2b084-103">Deploy Microsoft Teams Rooms with Skype for Business Server</span></span>
  
<span data-ttu-id="2b084-104">Questo argomento illustra come aggiungere un account di dispositivo per le sale di Microsoft teams quando si dispone di una distribuzione locale con una sola foresta.</span><span class="sxs-lookup"><span data-stu-id="2b084-104">This topic explains how you add a device account for Microsoft Teams Rooms when you have a single-forest, on-premises deployment.</span></span>
  
<span data-ttu-id="2b084-105">Se si dispone di una distribuzione locale con una sola foresta, con Exchange 2013 SP1 o versioni successive e Skype for Business Server 2015 o versione successiva, è possibile usare gli script di Windows PowerShell forniti per creare account di dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2b084-105">If you have a single-forest, on-premises deployment with Exchange 2013 SP1 or later and Skype for Business Server 2015 or later, then you can use the provided Windows PowerShell scripts to create device accounts.</span></span> <span data-ttu-id="2b084-106">Se si usa una distribuzione con più insiemi di strutture, è possibile usare i cmdlet equivalenti che produrranno gli stessi risultati.</span><span class="sxs-lookup"><span data-stu-id="2b084-106">If you're using a multi-forest deployment, you can use equivalent cmdlets that will produce the same results.</span></span> <span data-ttu-id="2b084-107">Questi cmdlet sono descritti in questa sezione.</span><span class="sxs-lookup"><span data-stu-id="2b084-107">Those cmdlets are described in this section.</span></span>

  
<span data-ttu-id="2b084-108">Prima di iniziare a distribuire le sale di Microsoft teams, assicurarsi di avere le autorizzazioni appropriate per eseguire i cmdlet associati.</span><span class="sxs-lookup"><span data-stu-id="2b084-108">Before you begin to deploy Microsoft Teams Rooms, be sure you have the right permissions to run the associated cmdlets.</span></span>
  

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

   <span data-ttu-id="2b084-109">Tieni presente che $strExchangeServer è il nome di dominio completo (FQDN) del server Exchange e $strLyncFQDN è l'FQDN della distribuzione di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="2b084-109">Note that $strExchangeServer is the fully qualified domain name (FQDN) of your Exchange server, and $strLyncFQDN is the FQDN of your Skype for Business Server deployment.</span></span>

2. <span data-ttu-id="2b084-110">Dopo aver stabilito una sessione, è possibile creare una nuova cassetta postale e abilitarla come RoomMailboxAccount o modificare le impostazioni per una cassetta postale della sala esistente.</span><span class="sxs-lookup"><span data-stu-id="2b084-110">After establishing a session, you'll either create a new mailbox and enable it as a RoomMailboxAccount, or change the settings for an existing room mailbox.</span></span> <span data-ttu-id="2b084-111">In questo modo l'account verrà autenticato in Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="2b084-111">This will allow the account to authenticate to Microsoft Teams Rooms.</span></span>

    <span data-ttu-id="2b084-112">Se si sta modificando una cassetta postale di risorse esistente:</span><span class="sxs-lookup"><span data-stu-id="2b084-112">If you're changing an existing resource mailbox:</span></span>

   ``` Powershell
   Set-Mailbox -Identity 'PROJECTRIGEL01' -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password>
   -AsPlainText -Force)
   ```

   <span data-ttu-id="2b084-113">Se si sta creando una nuova cassetta postale per le risorse:</span><span class="sxs-lookup"><span data-stu-id="2b084-113">If you're creating a new resource mailbox:</span></span>

   ``` Powershell
   New-Mailbox -UserPrincipalName PROJECTRIGEL01@contoso.com -Alias PROJECTRIGEL01 -Name "Project-Rigel-01" -Room
   -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

3. <span data-ttu-id="2b084-114">È possibile impostare diverse proprietà di Exchange nell'account del dispositivo per migliorare l'esperienza di riunione per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="2b084-114">You can set various Exchange properties on the device account to improve the meeting experience for people.</span></span> <span data-ttu-id="2b084-115">Puoi vedere quali proprietà devono essere impostate nella sezione proprietà di Exchange.</span><span class="sxs-lookup"><span data-stu-id="2b084-115">You can see which properties need to be set in the Exchange properties section.</span></span>

   ``` Powershell
   Set-CalendarProcessing -Identity $acctUpn -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -AllowConflicts $false -DeleteComments
   $false -DeleteSubject $false -RemovePrivateProperty $false
   Set-CalendarProcessing -Identity $acctUpn -AddAdditionalResponse $true -AdditionalResponse "This is a Skype Meeting room!"
   ```

4. <span data-ttu-id="2b084-116">Se si decide di non avere la password in scadenza, è possibile impostarla anche con i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="2b084-116">If you decide to have the password not expire, you can set that with Windows PowerShell cmdlets too.</span></span> <span data-ttu-id="2b084-117">Per altre informazioni, vedere Gestione delle password.</span><span class="sxs-lookup"><span data-stu-id="2b084-117">See Password management for more information.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -PasswordNeverExpires $true
   ```

5. <span data-ttu-id="2b084-118">Abilitare l'account in Active Directory in modo che venga autenticato in Microsoft teams rooms.</span><span class="sxs-lookup"><span data-stu-id="2b084-118">Enable the account in Active Directory so it will authenticate to Microsoft Teams Rooms.</span></span>

   ``` Powershell
   Set-AdUser $acctUpn -Enabled $true
   ```

6. <span data-ttu-id="2b084-119">Abilitare l'account del dispositivo con Skype for Business Server abilitando l'account di Microsoft teams Rooms Active Directory in un pool di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="2b084-119">Enable the device account with Skype for Business Server by enabling your Microsoft Teams Rooms Active Directory account on a Skype for Business Server pool:</span></span>

   ``` Powershell
   Enable-CsMeetingRoom -SipAddress sip:PROJECTRIGEL01@contoso.com -DomainController DC-ND-001.contoso.com
   -RegistrarPool LYNCPool15.contoso.com -Identity PROJECTRIGEL01
   ```

    <span data-ttu-id="2b084-120">È necessario usare l'indirizzo SIP (Session Initiation Protocol) e il controller di dominio per il progetto</span><span class="sxs-lookup"><span data-stu-id="2b084-120">You'll need to use the Session Initiation Protocol (SIP) address and domain controller for the Project</span></span>

7. <span data-ttu-id="2b084-121">**Opzionale.**</span><span class="sxs-lookup"><span data-stu-id="2b084-121">**Optional.**</span></span> <span data-ttu-id="2b084-122">È anche possibile consentire a Microsoft teams Rooms di effettuare e ricevere chiamate telefoniche PSTN (Public Switched Telephone Network) abilitando VoIP aziendale per il proprio account.</span><span class="sxs-lookup"><span data-stu-id="2b084-122">You can also allow Microsoft Teams Rooms to make and receive public switched telephone network (PSTN) phone calls by enabling Enterprise Voice for your account.</span></span> <span data-ttu-id="2b084-123">Enterprise Voice non è un requisito per le sale di Microsoft teams, ma se si vuole usare la funzionalità di chiamata PSTN per il client Microsoft teams rooms, ecco come abilitarlo:</span><span class="sxs-lookup"><span data-stu-id="2b084-123">Enterprise Voice isn't a requirement for Microsoft Teams Rooms, but if you want PSTN dialing functionality for the Microsoft Teams Rooms client, here's how to enable it:</span></span>

   ``` Powershell
   Set-CsMeetingRoom PROJECTRIGEL01 -DomainController DC-ND-001.contoso.com -LineURI "tel:+14255550555;ext=50555"
   Set-CsMeetingRoom -DomainController DC-ND-001.contoso.com -Identity PROJECTRIGEL01 -EnterpriseVoiceEnabled $true
   Grant-CsVoicePolicy -PolicyName VP1 -Identity PROJECTRIGEL01
   Grant-CsDialPlan -PolicyName DP1 -Identity PROJECTRIGEL01
   ```

   <span data-ttu-id="2b084-124">Anche in questo caso, è necessario sostituire gli esempi di Domain controller e numero di telefono forniti con le proprie informazioni.</span><span class="sxs-lookup"><span data-stu-id="2b084-124">Again, you'll need to replace the provided domain controller and phone number examples with your own information.</span></span> <span data-ttu-id="2b084-125">Il valore del parametro $true rimane invariato.</span><span class="sxs-lookup"><span data-stu-id="2b084-125">The parameter value $true stays the same.</span></span>

## <a name="sample-room-account-setup-in-exchange-and-skype-for-business-server-on-premises"></a><span data-ttu-id="2b084-126">Esempio: configurazione dell'account room in Exchange e Skype for Business Server in locale</span><span class="sxs-lookup"><span data-stu-id="2b084-126">Sample: room account setup in Exchange and Skype for Business Server on premises</span></span>

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

## <a name="see-also"></a><span data-ttu-id="2b084-127">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="2b084-127">See also</span></span>

[<span data-ttu-id="2b084-128">Configurare gli account per le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2b084-128">Configure accounts for Microsoft Teams Rooms</span></span>](rooms-configure-accounts.md)

[<span data-ttu-id="2b084-129">Pianificare le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2b084-129">Plan for Microsoft Teams Rooms</span></span>](rooms-plan.md)
  
[<span data-ttu-id="2b084-130">Distribuire le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2b084-130">Deploy Microsoft Teams Rooms</span></span>](rooms-deploy.md)
  
[<span data-ttu-id="2b084-131">Configurare una console Microsoft teams rooms</span><span class="sxs-lookup"><span data-stu-id="2b084-131">Configure a Microsoft Teams Rooms console</span></span>](console.md)
  
[<span data-ttu-id="2b084-132">Gestire le sale di Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2b084-132">Manage Microsoft Teams Rooms</span></span>](rooms-manage.md)
