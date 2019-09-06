---
title: Provisioning degli account di Skype room System in Office 365
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Leggere questo argomento per informazioni sul provisioning degli account di Skype room System in Office 365.
ms.openlocfilehash: d247983647641c91376c99bed3a13606027a7e11
ms.sourcegitcommit: a2deac5e8308fc58aba34060006bffad2b19abed
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 09/06/2019
ms.locfileid: "36775390"
---
# <a name="provisioning-skype-room-system-accounts-in-office-365"></a><span data-ttu-id="dbe93-103">Provisioning degli account di Skype room System in Office 365</span><span class="sxs-lookup"><span data-stu-id="dbe93-103">Provisioning Skype Room System accounts in Office 365</span></span>
 
<span data-ttu-id="dbe93-104">Leggere questo argomento per informazioni sul provisioning degli account di Skype room System in Office 365.</span><span class="sxs-lookup"><span data-stu-id="dbe93-104">Read this topic to learn about provisioning Skype Room System accounts in Office 365.</span></span>
  
<span data-ttu-id="dbe93-105">La sezione seguente illustra il provisioning degli account di Skype room System per un tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="dbe93-105">The following section covers Skype Room System account provisioning for an Office 365 tenant.</span></span>
  
## <a name="office-365-prerequisites"></a><span data-ttu-id="dbe93-106">Prerequisiti di Office 365</span><span class="sxs-lookup"><span data-stu-id="dbe93-106">Office 365 prerequisites</span></span>

<span data-ttu-id="dbe93-107">Il tenant online deve soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="dbe93-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="dbe93-108">Il piano di Office 365 deve includere Skype for business online Plan 2 o Office 365 E1, E3 o E5.</span><span class="sxs-lookup"><span data-stu-id="dbe93-108">The Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="dbe93-109">Per informazioni dettagliate sui piani di Skype for business online, vedere la [Descrizione del servizio Skype for business online](https://technet.microsoft.com/library/jj822172.aspx).</span><span class="sxs-lookup"><span data-stu-id="dbe93-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](https://technet.microsoft.com/library/jj822172.aspx).</span></span>
    
- <span data-ttu-id="dbe93-110">Il tenant deve avere la funzionalità di conferenza di Skype for business abilitata.</span><span class="sxs-lookup"><span data-stu-id="dbe93-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="dbe93-111">Il tenant deve avere abilitato Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="dbe93-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="dbe93-112">L'amministratore remoto del tenant deve avere l'accesso di PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="dbe93-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="dbe93-113">Accesso remoto a PowerShell di Exchange</span><span class="sxs-lookup"><span data-stu-id="dbe93-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="dbe93-114">Accesso remoto a PowerShell per Skype for business online</span><span class="sxs-lookup"><span data-stu-id="dbe93-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="dbe93-115">Modulo di Windows Azure Active Directory per Windows PowerShell per accedere alla directory di Office 365 Access</span><span class="sxs-lookup"><span data-stu-id="dbe93-115">Windows Azure Active Directory Module for Windows PowerShell to access Office 365 directory access</span></span>
    
<span data-ttu-id="dbe93-116">Per l'account della sala Skype è necessaria la licenza seguente:</span><span class="sxs-lookup"><span data-stu-id="dbe93-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="dbe93-117">Per abilitare le riunioni Skype è necessaria una licenza di Skype for business online Plan 2 o Office 365 E1 o E3.</span><span class="sxs-lookup"><span data-stu-id="dbe93-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="dbe93-118">Per autorizzare la chat room con la funzionalità VoIP aziendale in modo che la chat room possa essere abilitata con un numero di telefono, è necessario un piano 2 Skype for business online con la licenza per il sistema telefonico o Office 365 E5 (1).</span><span class="sxs-lookup"><span data-stu-id="dbe93-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="dbe93-119">Se sono necessarie funzionalità di accesso esterno da una riunione, è necessaria una licenza per l'audioconferenza e il sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="dbe93-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="dbe93-120">Se sono necessarie funzionalità di chiamata in uscita da una riunione, è necessario un piano per chiamate nazionali o nazionali e internazionali.</span><span class="sxs-lookup"><span data-stu-id="dbe93-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="dbe93-121">Una licenza di Exchange Online non è necessaria per l'account della sala Skype perché l'account deve essere configurato come account di cassetta postale per le risorse.</span><span class="sxs-lookup"><span data-stu-id="dbe93-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="dbe93-122">Panoramica del provisioning</span><span class="sxs-lookup"><span data-stu-id="dbe93-122">Provisioning overview</span></span>

<span data-ttu-id="dbe93-123">Il diagramma seguente offre una panoramica del flusso di provisioning degli account di Skype room System in Office 365.</span><span class="sxs-lookup"><span data-stu-id="dbe93-123">The following diagram provides an overview of the Skype Room System account provisioning flow in Office 365.</span></span>
  
![Procedura per il provisioning di Skype room System per Office 365](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="dbe93-125">Identificare una nuova sala riunioni</span><span class="sxs-lookup"><span data-stu-id="dbe93-125">Identify a new conference room</span></span>

<span data-ttu-id="dbe93-126">Potrebbe essere già presente una cassetta postale della sala risorse in Exchange che fornisce la funzionalità di pianificazione oppure creare una cassetta postale per la prima volta per facilitare la distribuzione di Skype room System.</span><span class="sxs-lookup"><span data-stu-id="dbe93-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="dbe93-127">In ogni caso, devi identificare un account room da usare nel tenant.</span><span class="sxs-lookup"><span data-stu-id="dbe93-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="dbe93-128">Le sezioni Exchange Online Provision e Skype for business promettono indicazioni per entrambi i tipi di account.</span><span class="sxs-lookup"><span data-stu-id="dbe93-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="dbe93-129">Supponiamo, ad esempio, di avere le due sale seguenti e si vuole distribuire Skype room System per entrambi:</span><span class="sxs-lookup"><span data-stu-id="dbe93-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="dbe93-130">Account delle cassette postali delle risorse esistenti: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="dbe93-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="dbe93-131">Nuovo account di cassetta postale per le risorse: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="dbe93-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="dbe93-132">Provisioning di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="dbe93-132">Exchange Online provisioning</span></span>

<span data-ttu-id="dbe93-133">Prima di tutto, connettersi a PowerShell di Exchange Online seguendo le istruzioni dell'argomento [connettersi a PowerShell di Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="dbe93-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
  
<span data-ttu-id="dbe93-134">Per impostare un account della cassetta postale della sala risorse esistente per Skype room System, eseguire i comandi seguenti in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="dbe93-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="dbe93-135">Per creare un nuovo account delle cassette postali di Exchange per Skype room System, eseguire i comandi seguenti in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="dbe93-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="dbe93-136">I comandi precedenti configurano o creano un nuovo account di cassetta postale di Exchange per l'utilizzo di Skype room System abilitando l'account.</span><span class="sxs-lookup"><span data-stu-id="dbe93-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="dbe93-137">Dopo aver creato la cassetta postale, è possibile usare il cmdlet Set-CalendarProcessing in PowerShell di Exchange Online per configurare la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="dbe93-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="dbe93-138">Vedere i passaggi da 3 a 6 in distribuzioni locali di una singola foresta per altre informazioni</span><span class="sxs-lookup"><span data-stu-id="dbe93-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="dbe93-139">Assegnazione di una licenza Skype for business online</span><span class="sxs-lookup"><span data-stu-id="dbe93-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="dbe93-140">Ora è possibile assegnare una licenza di Skype for business online (piano 2) o Skype for business online (piano 3) usando il portale amministrativo di Office 365, come descritto in [assegnare o rimuovere licenze per Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) o nel [componente aggiuntivo Skype for business licenze](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span><span class="sxs-lookup"><span data-stu-id="dbe93-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Office 365 administrative portal as described in [Assign or remove licenses for Office 365 for business](https://support.office.com/en-us/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/en-US/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="dbe93-141">Dopo aver assegnato una licenza per Skype for business online, è possibile effettuare l'accesso e verificare che l'account sia attivo usando qualsiasi client Skype for business.</span><span class="sxs-lookup"><span data-stu-id="dbe93-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="dbe93-142">Provisioning di Skype for business online</span><span class="sxs-lookup"><span data-stu-id="dbe93-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="dbe93-143">Dopo aver creato e abilitato un account della cassetta postale della sala risorse, come illustrato in precedenza, e aver concesso in licenza l'account per Skype for business online, l'account verrà sincronizzato dalla foresta di Exchange Online alla foresta di Skype for business online usando il Foresta di Windows Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="dbe93-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="dbe93-144">I passaggi seguenti sono necessari per eseguire il provisioning dell'account di sistema room Skype nel pool Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="dbe93-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="dbe93-145">Questi passaggi sono identici sia per un account di cassetta postale delle risorse esistente che per un account appena creato (confrm1 o confrm2), perché una volta abilitati in Exchange Online, entrambi gli account verranno sincronizzati con Skype for business online nello stesso modo:</span><span class="sxs-lookup"><span data-stu-id="dbe93-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="dbe93-146">Creare una sessione remota di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dbe93-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="dbe93-147">Tieni presente che dovrai scaricare il modulo Connector di Skype for business online e l'assistente per l'accesso ai Microsoft Online Services e verificare che il computer sia configurato.</span><span class="sxs-lookup"><span data-stu-id="dbe93-147">Note that you will need to download Skype for Business Online Connector Module and Microsoft Online Services Sign-In Assistant and make sure that your computer is configured.</span></span> <span data-ttu-id="dbe93-148">Per altre informazioni, vedere [configurare il computer per Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="dbe93-148">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
    
   ```
   Import-Module LyncOnlineConnector
   $cssess=New-CsOnlineSession -Credential $cred
   Import-PSSession $cssess -AllowClobber
   ```

2. <span data-ttu-id="dbe93-149">Per abilitare un account di sistema room Skype per Skype for business, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="dbe93-149">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="dbe93-150">Puoi ottenere l'indirizzo RegistrarPool in cui gli utenti di Skype for business si trovano in uno degli account esistenti usando il comando seguente per restituire questa proprietà:</span><span class="sxs-lookup"><span data-stu-id="dbe93-150">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

  
## <a name="password-expiration"></a><span data-ttu-id="dbe93-151">Scadenza password</span><span class="sxs-lookup"><span data-stu-id="dbe93-151">Password expiration</span></span>

<span data-ttu-id="dbe93-152">In Office 365 i criteri di scadenza della password predefiniti per tutti gli account utente sono di 90 giorni, a meno che non vengano configurati criteri di scadenza della password diversi.</span><span class="sxs-lookup"><span data-stu-id="dbe93-152">In Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="dbe93-153">Per gli account di sistema Skype room, è possibile selezionare la password non scade mai con i passaggi seguenti.</span><span class="sxs-lookup"><span data-stu-id="dbe93-153">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="dbe93-154">Creare una sessione di Windows Azure Active Directory usando le credenziali di amministratore globale del tenant.</span><span class="sxs-lookup"><span data-stu-id="dbe93-154">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="dbe93-155">Impostare la password non scade mai l'impostazione per l'account della sala di Skype room System creato in precedenza usando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="dbe93-155">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="dbe93-156">Per altre informazioni, vedere [configurare il computer per Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="dbe93-156">For more information, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  
## <a name="validate"></a><span data-ttu-id="dbe93-157">Convalidare</span><span class="sxs-lookup"><span data-stu-id="dbe93-157">Validate</span></span>

<span data-ttu-id="dbe93-158">Per la convalida, dovresti essere in grado di usare qualsiasi client Skype for business per accedere all'account creato.</span><span class="sxs-lookup"><span data-stu-id="dbe93-158">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>

