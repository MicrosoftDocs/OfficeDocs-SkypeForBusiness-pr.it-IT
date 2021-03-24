---
title: Provisioning degli account di Sistema sala Skype in Microsoft 365 e Office 365
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
ms.assetid: c36150bb-461c-4f1c-877b-fac7fb232f7c
description: Leggere questo argomento per informazioni sul provisioning degli account di Sistema sala Skype in Microsoft 365 o Office 365.
ms.openlocfilehash: 94390effb246a37745d797289c1146ed3d347604
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093520"
---
# <a name="provisioning-skype-room-system-accounts-in-microsoft-365-and-office-365"></a><span data-ttu-id="15da2-103">Provisioning degli account di Sistema sala Skype in Microsoft 365 e Office 365</span><span class="sxs-lookup"><span data-stu-id="15da2-103">Provisioning Skype Room System accounts in Microsoft 365 and Office 365</span></span>
 
<span data-ttu-id="15da2-104">Leggere questo argomento per informazioni sul provisioning degli account di Sistema sala Skype in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="15da2-104">Read this topic to learn about provisioning Skype Room System accounts in Microsoft 365 or Office 365.</span></span>
  
<span data-ttu-id="15da2-105">La sezione seguente illustra il provisioning dell'account skype room system.</span><span class="sxs-lookup"><span data-stu-id="15da2-105">The following section covers Skype Room System account provisioning.</span></span>
  
## <a name="microsoft-365-and-office-365-prerequisites"></a><span data-ttu-id="15da2-106">Prerequisiti di Microsoft 365 e Office 365</span><span class="sxs-lookup"><span data-stu-id="15da2-106">Microsoft 365 and Office 365 prerequisites</span></span>

<span data-ttu-id="15da2-107">Il tenant online deve soddisfare i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="15da2-107">Your online tenant must meet the following requirements:</span></span>
  
- <span data-ttu-id="15da2-108">Il piano di Microsoft 365 o Office 365 deve includere Skype for Business Online Piano 2 o Office 365 E1, E3 o E5.</span><span class="sxs-lookup"><span data-stu-id="15da2-108">The Microsoft 365 or Office 365 plan must include Skype for Business Online Plan 2, or Office 365 E1, E3 or E5.</span></span> <br/><span data-ttu-id="15da2-109">Per informazioni dettagliate sui piani di Skype for Business Online, vedere Descrizione [del servizio Skype for Business online.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description)</span><span class="sxs-lookup"><span data-stu-id="15da2-109">For details on Skype for Business Online Plans, see the [Skype for Business Online Service Description](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-service-description).</span></span>
    
- <span data-ttu-id="15da2-110">Il tenant deve avere la funzionalità di conferenza di Skype for Business abilitata.</span><span class="sxs-lookup"><span data-stu-id="15da2-110">Your tenant must have the conferencing capability of Skype for Business enabled.</span></span>
    
- <span data-ttu-id="15da2-111">Nel tenant deve essere abilitato Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="15da2-111">Your tenant must have Exchange Online enabled.</span></span> 
    
- <span data-ttu-id="15da2-112">L'amministratore remoto tenant deve disporre dell'accesso PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="15da2-112">Your tenant remote administrator must have the following PowerShell access:</span></span>
    
  - <span data-ttu-id="15da2-113">Accesso remoto a PowerShell di Exchange</span><span class="sxs-lookup"><span data-stu-id="15da2-113">Exchange Remote PowerShell access</span></span>
    
  - <span data-ttu-id="15da2-114">Accesso remoto a PowerShell di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="15da2-114">Skype for Business Online Remote PowerShell access</span></span>
    
  - <span data-ttu-id="15da2-115">Windows Azure Active Directory Module per Windows PowerShell accesso alla directory di Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="15da2-115">Windows Azure Active Directory Module for Windows PowerShell to access Microsoft 365 or Office 365 directory access</span></span>
    
<span data-ttu-id="15da2-116">Per l'account sala Skype, sono necessarie le licenze seguenti:</span><span class="sxs-lookup"><span data-stu-id="15da2-116">For the Skype Room account, the following licensing is required:</span></span>
  
- <span data-ttu-id="15da2-117">Per abilitare le riunioni Skype for Business online, è necessaria una licenza Skype for Business Online Piano 2 o Office 365 E1 o E3.</span><span class="sxs-lookup"><span data-stu-id="15da2-117">A Skype for Business Online Plan 2 or Office 365 E1 or E3 license is required to enable Skype Meetings.</span></span>
    
- <span data-ttu-id="15da2-118">Per autorizzare la sala con la funzionalità VoIP aziendale in modo che la sala possa essere abilitata con un numero di telefono, è necessario un Skype for Business Online Piano 2 con licenza sistema telefonico o Office 365 E5 (1).</span><span class="sxs-lookup"><span data-stu-id="15da2-118">To entitle the room with the Enterprise Voice capability so the room can be enabled with a phone number, a Skype for Business Online Plan 2 with the Phone System license or Office 365 E5 is required (1).</span></span>
    
- <span data-ttu-id="15da2-119">Se sono necessarie funzionalità di accesso esterno da una riunione, è necessaria una licenza per audioconferenza e sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="15da2-119">If you need dial-in capabilities from a meeting, you will need an audio conferencing and Phone System license.</span></span>  <span data-ttu-id="15da2-120">Se sono necessarie funzionalità di chiamata in uscita da una riunione, è necessario un piano per chiamate nazionali o nazionali e internazionali.</span><span class="sxs-lookup"><span data-stu-id="15da2-120">If you need dial-out capabilities from a meeting, you will need a domestic or domestic and international Calling Plan.</span></span> 
    
- <span data-ttu-id="15da2-121">Non è necessaria una licenza di Exchange Online per l'account sala Skype perché l'account deve essere configurato come account della cassetta postale delle risorse.</span><span class="sxs-lookup"><span data-stu-id="15da2-121">An Exchange Online license is not required for the Skype Room account because the account should be configured as a resource mailbox account.</span></span>
    
## <a name="provisioning-overview"></a><span data-ttu-id="15da2-122">Panoramica del provisioning</span><span class="sxs-lookup"><span data-stu-id="15da2-122">Provisioning overview</span></span>

<span data-ttu-id="15da2-123">Nel diagramma seguente viene fornita una panoramica del flusso di provisioning dell'account di sistema sala Skype.</span><span class="sxs-lookup"><span data-stu-id="15da2-123">The following diagram provides an overview of the Skype Room System account provisioning flow.</span></span>
  
![Passaggi per il provisioning del sistema skype room](../../media/354c5659-317b-4e85-a1bc-c60c07f305a4.png)
  
## <a name="identify-a-new-conference-room"></a><span data-ttu-id="15da2-125">Identificare una nuova sala riunioni</span><span class="sxs-lookup"><span data-stu-id="15da2-125">Identify a new conference room</span></span>

<span data-ttu-id="15da2-126">È possibile che in Exchange sia già disponibile una cassetta postale sala risorse che fornisce la funzionalità di pianificazione oppure che si crei per la prima volta una cassetta postale per le risorse per facilitare la distribuzione di Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="15da2-126">You may already have a resource room mailbox in Exchange that provides the scheduling feature, or you may be creating a resource mailbox for the first time to facilitate Skype Room System deployment.</span></span> <span data-ttu-id="15da2-127">In ogni caso, è necessario identificare un account sala da utilizzare nel tenant.</span><span class="sxs-lookup"><span data-stu-id="15da2-127">In any case, you must identify a room account to be used in your tenant.</span></span> <span data-ttu-id="15da2-128">Le sezioni Provisioning di Exchange Online e Provisioning di Skype for Business forniscono indicazioni per entrambi i tipi di account.</span><span class="sxs-lookup"><span data-stu-id="15da2-128">The Exchange Online Provision and Skype for Business Provision sections provide guidance for both kinds of accounts.</span></span> <span data-ttu-id="15da2-129">Ad esempio, supponiamo che tu abbia le due sale seguenti e che desideri distribuire Skype Room System per entrambe:</span><span class="sxs-lookup"><span data-stu-id="15da2-129">For example, let's say you have the following two rooms, and you would like to deploy Skype Room System for both of them:</span></span>
  
- <span data-ttu-id="15da2-130">Account cassetta postale risorsa esistente: confrm1@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="15da2-130">Existing Resource Mailbox Account: confrm1@contoso.onmicrosoft.com</span></span>
    
- <span data-ttu-id="15da2-131">Nuovo account cassetta postale risorsa: confrm2@contoso.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="15da2-131">New Resource Mailbox Account: confrm2@contoso.onmicrosoft.com</span></span>
    
## <a name="exchange-online-provisioning"></a><span data-ttu-id="15da2-132">Provisioning di Exchange Online</span><span class="sxs-lookup"><span data-stu-id="15da2-132">Exchange Online provisioning</span></span>

<span data-ttu-id="15da2-133">Prima di tutto, connettersi a PowerShell di Exchange Online seguendo le istruzioni nell'argomento Connect [to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="15da2-133">First, connect to Exchange Online PowerShell by following the instructions in the topic, [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
  
<span data-ttu-id="15da2-134">Per impostare un account cassetta postale sala risorse esistente per Skype Room System, eseguire i comandi seguenti in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="15da2-134">To set an existing resource room mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm1@contoso.onmicrosoft.com"
$newpass='pass@word1'
Set-Mailbox -Identity $rm  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="15da2-135">Per creare un nuovo account cassetta postale delle risorse di Exchange per Skype Room System, eseguire i comandi seguenti in PowerShell di Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="15da2-135">To create a new Exchange resource mailbox account for Skype Room System, run the following commands in Exchange Online PowerShell:</span></span>
  
```powershell
$rm="confrm2@contoso.onmicrosoft.com"
$newpass='pass@word1'
New-Mailbox -Name "Conf Room 2" -MicrosoftOnlineServicesID $rm -Room  -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString $newpass -AsPlainText -Force)
```

<span data-ttu-id="15da2-136">I comandi precedenti configurano o creano un nuovo account della cassetta postale per le risorse di Exchange per l'utilizzo di Skype Room System abilitando l'account.</span><span class="sxs-lookup"><span data-stu-id="15da2-136">The previous commands set up or create a new Exchange resource mailbox account for Skype Room System usage by enabling the account.</span></span>
  
<span data-ttu-id="15da2-137">Dopo aver creato la cassetta postale, è possibile utilizzare il cmdlet Set-CalendarProcessing in PowerShell di Exchange Online per configurare la cassetta postale.</span><span class="sxs-lookup"><span data-stu-id="15da2-137">After creating the mailbox, you can use the Set-CalendarProcessing cmdlet in Exchange Online PowerShell to configure the mailbox.</span></span> <span data-ttu-id="15da2-138">Per ulteriori dettagli, vedere i passaggi da 3 a 6 in Distribuzioni locali a foresta singola</span><span class="sxs-lookup"><span data-stu-id="15da2-138">Refer to steps 3 through 6 under Single forest on-premises deployments for more details</span></span>

## <a name="assigning-a-skype-for-business-online-license"></a><span data-ttu-id="15da2-139">Assegnazione di una licenza di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="15da2-139">Assigning a Skype for Business Online license</span></span>

<span data-ttu-id="15da2-140">Ora è possibile assegnare una licenza skype for business online (piano 2) o Skype for Business online (Piano 3) utilizzando il portale amministrativo di Microsoft 365 come descritto in Assegnare o rimuovere licenze per [Microsoft 365 per](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) le aziende o in Licenze per componenti aggiuntivi [Skype for Business.](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7)</span><span class="sxs-lookup"><span data-stu-id="15da2-140">Now you can assign a Skype for Business Online (Plan 2) or Skype for Business Online (Plan 3) license by using the Microsoft 365 administrative portal as described in [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/Assign-or-remove-licenses-for-Office-365-for-business-997596b5-4173-4627-b915-36abac6786dc?ui=en-US&amp;rs=en-US&amp;ad=US) or in [Skype for Business add-on licensing](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7).</span></span> 
  
<span data-ttu-id="15da2-141">Dopo aver assegnato una licenza per Skype for Business online, potrai accedere e verificare che l'account sia attivo usando qualsiasi client Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="15da2-141">After you assign a license for Skype for Business Online, you will be able to log in and validate that the account is active using any Skype for Business client.</span></span>
  
## <a name="skype-for-business-online-provisioning"></a><span data-ttu-id="15da2-142">Provisioning di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="15da2-142">Skype for Business Online provisioning</span></span>

<span data-ttu-id="15da2-143">Dopo aver creato e abilitato un account della cassetta postale sala risorse come mostrato in precedenza e avere concesso in licenza l'account per Skype For Business Online, l'account verrà sincronizzato dalla foresta di Exchange Online a Skype for Business Online utilizzando la foresta di Active Directory di Windows Azure.</span><span class="sxs-lookup"><span data-stu-id="15da2-143">After a resource room mailbox account has been created and enabled as shown previously, and you have licensed the account for Skype For Business Online the account will synchronize from the Exchange Online forest to Skype for Business Online forest by using the Windows Azure Active Directory forest.</span></span> <span data-ttu-id="15da2-144">I passaggi seguenti sono necessari per eseguire il provisioning dell'account di sistema sala Skype nel pool skype for business online.</span><span class="sxs-lookup"><span data-stu-id="15da2-144">The following steps are required to provision the Skype Room System account in the Skype for Business Online pool.</span></span> <span data-ttu-id="15da2-145">Questi passaggi sono gli stessi per un account della cassetta postale delle risorse esistente o per un account appena creato (confrm1 o confrm2), perché una volta abilitati in Exchange Online, entrambi questi account verranno sincronizzati con Skype for Business Online nello stesso modo:</span><span class="sxs-lookup"><span data-stu-id="15da2-145">These steps are the same for both an existing resource mailbox account or a newly created account (confrm1 or confrm2), because once they are enabled in Exchange Online, both of these accounts will be synchronized to Skype for Business Online in the same way:</span></span>
  
1. <span data-ttu-id="15da2-146">Creare una sessione remota di PowerShell.</span><span class="sxs-lookup"><span data-stu-id="15da2-146">Create a Remote PowerShell session.</span></span> <span data-ttu-id="15da2-147">Tenere presente che sarà necessario scaricare il [modulo di PowerShell di Teams.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="15da2-147">Note that you will need to download [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span>
    
  ```powershell
  # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
  ```

2. <span data-ttu-id="15da2-148">Per abilitare un account di sistema sala Skype per Skype for Business, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="15da2-148">To enable an Skype Room System account for Skype for Business, run the following command:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -Identity $rm -RegistrarPool "sippoolbl20a04.infra.lync.com" -SipAddressType EmailAddress
   ```

    <span data-ttu-id="15da2-149">È possibile ottenere l'indirizzo RegistrarPool in cui gli utenti di Skype for Business sono ospitati da uno degli account esistenti utilizzando il comando seguente per ottenere questa proprietà:</span><span class="sxs-lookup"><span data-stu-id="15da2-149">You can obtain the RegistrarPool address where your Skype for Business users are homed from one of your existing accounts by using the following command to returns this property:</span></span>
    
   ```powershell
   Get-CsOnlineUser -Identity 'alice@contoso.onmicrosoft.com'| fl *registrarpool*
   ```

>[!NOTE] 
><span data-ttu-id="15da2-150">Multi-Factor Authentication (MFA) non è supportato per gli account di sistema sala Skype.</span><span class="sxs-lookup"><span data-stu-id="15da2-150">Multi-Factor Authentication (MFA) isn't supported for Skype Room System accounts.</span></span> 

## <a name="password-expiration"></a><span data-ttu-id="15da2-151">Scadenza password</span><span class="sxs-lookup"><span data-stu-id="15da2-151">Password expiration</span></span>

<span data-ttu-id="15da2-152">In Microsoft 365 o Office 365, il criterio di scadenza delle password predefinito per tutti gli account utente è di 90 giorni, a meno che non si configurano criteri di scadenza delle password diversi.</span><span class="sxs-lookup"><span data-stu-id="15da2-152">In Microsoft 365 or Office 365, the default password expiration policy for all of your user accounts is 90 days unless you configure a different password expiration policy.</span></span> <span data-ttu-id="15da2-153">Per gli account di sistema sala Skype, è possibile selezionare l'impostazione Nessuna scadenza password con la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="15da2-153">For Skype Room System accounts, you can select the Password never expires setting with the following steps.</span></span>
  
1. <span data-ttu-id="15da2-154">Creare una Windows Azure di Active Directory utilizzando le credenziali di amministratore globale del tenant.</span><span class="sxs-lookup"><span data-stu-id="15da2-154">Create a Windows Azure Active Directory session by using your tenant global administrator credentials.</span></span>
    
    ```powershell
    $cred=Get-Credential admin@$org
    Connect-MsolService -Credential $cred
    ```

2. <span data-ttu-id="15da2-155">Impostare l'impostazione Nessuna scadenza password per l'account sala di sistema skype room creato in precedenza utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="15da2-155">Set the Password never expires setting for the Skype Room System room account created previously by using the following command:</span></span>
    
   ```powershell
   Set-MsolUser -UserPrincipalName confrm1@skypelrs.onmicrosoft.com -PasswordNeverExpires $true
   ```

<span data-ttu-id="15da2-156">Per ulteriori informazioni, vedere [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="15da2-156">For more information, see [Set up your computer for Windows PowerShell](../../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="validate"></a><span data-ttu-id="15da2-157">Convalida</span><span class="sxs-lookup"><span data-stu-id="15da2-157">Validate</span></span>

<span data-ttu-id="15da2-158">Per la convalida, dovresti essere in grado di usare qualsiasi client Skype for Business per accedere all'account creato.</span><span class="sxs-lookup"><span data-stu-id="15da2-158">For validation, you should be able to use any Skype for Business client to sign in to the account you created.</span></span>