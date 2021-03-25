---
title: Distribuzioni locali a foresta singola di Skype Room System
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
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente locale a foresta singola.
ms.openlocfilehash: df213b24ef3400aa5551a090d2dd218d05794988
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120325"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="a3ab5-103">Distribuzioni locali a foresta singola di Skype Room System</span><span class="sxs-lookup"><span data-stu-id="a3ab5-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="a3ab5-104">Leggere questo argomento per informazioni su come distribuire Skype Room System in un ambiente locale a foresta singola.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="a3ab5-105">In questa sezione viene fornita una panoramica dei passaggi per il provisioning dell'account di sistema sala Skype in Exchange Server e Skype for Business Server ospitato in una distribuzione locale a foresta singola.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="a3ab5-106">Distribuzioni locali della singola foresta</span><span class="sxs-lookup"><span data-stu-id="a3ab5-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="a3ab5-107">Se si dispone già di un account cassetta postale della risorsa per la sala conferenze, è possibile utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="a3ab5-108">In caso contrario, sarà necessario crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="a3ab5-109">È possibile utilizzare Exchange Management Shell (PowerShell) o Exchange Management Console per creare un nuovo account cassetta postale per le risorse.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="a3ab5-110">È consigliabile usare una nuova cassetta postale (eliminare la cassetta postale precedente e ri-creare) per Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="a3ab5-111">Assicurarsi di eseguire il backup dei dati della cassetta postale prima di eliminarli ed esportarlo di nuovo nella cassetta postale ri-creata utilizzando il client Outlook (per ulteriori informazioni, vedere Esportare o eseguire il backup di messaggi, calendario, attività e contatti).</span><span class="sxs-lookup"><span data-stu-id="a3ab5-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="a3ab5-112">Per ripristinare le riunioni perse eliminando la cassetta postale, vedere [Connect or restore a deleted mailbox](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help).</span><span class="sxs-lookup"><span data-stu-id="a3ab5-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](/exchange/connect-or-restore-a-deleted-mailbox-exchange-2013-help).</span></span> 
  
<span data-ttu-id="a3ab5-113">Per utilizzare un account cassetta postale delle risorse esistente (ad esempio, LRS-01) eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="a3ab5-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="a3ab5-114">Eseguire il comando di Exchange Management PowerShell seguente:</span><span class="sxs-lookup"><span data-stu-id="a3ab5-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="a3ab5-115">Se si prevede di creare una nuova cassetta postale, quindi, per un'organizzazione exchange locale a foresta singola, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="a3ab5-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="a3ab5-116">Nell'esempio precedente viene creato un account utente abilitato in Active Directory e una cassetta postale sala per una sala riunioni in un'organizzazione exchange locale.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-116">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization.</span></span> <span data-ttu-id="a3ab5-117">Il parametro RoomMailboxPassword consente di specificare la password per l'account utente.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-117">The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="a3ab5-118">Configurare l'account per risolvere automaticamente i conflitti accettando/rifiutando le riunioni.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="a3ab5-119">Gli account delle sale riunioni dotate di sistema skype in Exchange possono essere gestiti da singoli utenti, ma si noti che fino a quando l'utente non accetta una riunione non verrà visualizzata nel calendario della schermata iniziale del sistema Sala Skype.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="a3ab5-120">Per un set completo di comandi disponibili, vedere Set-CalendarProcessing.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="a3ab5-121">Per ricordare agli organizzatori della riunione di rendere la riunione una riunione Skype for Business online in Outlook, eseguire il comando seguente per configurare un suggerimento messaggio per il nuovo account:</span><span class="sxs-lookup"><span data-stu-id="a3ab5-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="a3ab5-122">Utilizzare i comandi seguenti per configurare le stringhe localizzate.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-122">Use the following commands to configure localized strings.</span></span> <span data-ttu-id="a3ab5-123">Se richiesto dall'organizzazione, è anche possibile aggiungere traduzioni personalizzate:</span><span class="sxs-lookup"><span data-stu-id="a3ab5-123">If required by your organization, you can also add custom translations:</span></span> 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="a3ab5-124">Facoltativo: configurare il testo di accettazione delle riunioni che fornisce agli utenti informazioni sulla sala riunioni skype for business e su cosa aspettarsi quando pianificano e aderiscono alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="a3ab5-125">Controllare l'account della cassetta postale della risorsa in Active Directory</span><span class="sxs-lookup"><span data-stu-id="a3ab5-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="a3ab5-126">L'account della cassetta postale della sala riunioni creato da Exchange nel passaggio 1 precedente potrebbe essere un oggetto utente disabilitato in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="a3ab5-127">Skype Room System non può accedere o eseguire l'autenticazione utilizzando l'autenticazione Kerberos/NTLM se l'account è disabilitato in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="a3ab5-128">Il client skype room system deve essere in grado di eseguire l'autenticazione con i servizi Web di Exchange per recuperare le impostazioni del calendario e deve anche essere in grado di inviare messaggi di posta elettronica con il contenuto della lavagna.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="a3ab5-129">Pertanto, se l'account è disabilitato, è necessario abilitare questo account in Active Directory eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="a3ab5-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="a3ab5-130">In Active Directory, eseguire il comando seguente per abilitare l'accesso all'account:</span><span class="sxs-lookup"><span data-stu-id="a3ab5-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="a3ab5-131">Eseguendo questo comando verrà richiesto di immettere la password corrente e quindi di immettere di nuovo la password due volte per la conferma.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="a3ab5-132">Dopo aver impostato la password, eseguire il comando seguente per abilitare l'account:</span><span class="sxs-lookup"><span data-stu-id="a3ab5-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="a3ab5-133">Abilitazione degli account di sistema sala Skype per Skype for Business</span><span class="sxs-lookup"><span data-stu-id="a3ab5-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="a3ab5-134">In questa sezione viene fornita una panoramica dei passaggi necessari per abilitare Skype for Business per l'account della sala riunioni, che verrà configurato in Skype Room System.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="a3ab5-135">Dopo aver creato un account della cassetta postale delle risorse per le sale conferenze, utilizzare Skype for Business Server Management Shell per abilitare gli account di sistema sala Skype per i servizi Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a3ab5-136">La procedura seguente presuppone che sia stato abilitato l'account di sistema sala Skype in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="a3ab5-137">Eseguire il comando seguente per abilitare l'account di sistema sala Skype in un pool di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="a3ab5-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="a3ab5-138">Facoltativo: consentire a questo account di effettuare e ricevere chiamate telefoniche PSTN abilitando l'account per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="a3ab5-139">VoIP aziendale non è necessario per Skype Room System, ma se non lo abiliti per VoIP aziendale, il client skype room system non sarà in grado di fornire la funzionalità di composizione PSTN:</span><span class="sxs-lookup"><span data-stu-id="a3ab5-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="a3ab5-140">Se abiliti VoIP aziendale per l'account della sala riunioni di Skype Room System, assicurati di configurare un criterio vocale con restrizioni adatto alla tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="a3ab5-141">Se la sala riunioni di Skype for Business è una risorsa disponibile pubblicamente, chiunque potrebbe usarla per partecipare a una riunione, pianificata o ad hoc.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="a3ab5-142">Dopo la partecipazione a una riunione, la persona potrebbe chiamare qualsiasi numero.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="a3ab5-143">In Skype for Business Server, la funzionalità di chiamata in uscita dalle conferenze utilizza i criteri vocali dell'utente, in questo caso l'account di sistema sala Skype utilizzato per partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="a3ab5-144">Nelle versioni precedenti di Lync Server viene utilizzato il criterio vocale dell'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="a3ab5-145">Pertanto, se un utente di una versione precedente di Lync Server pianifica una sala riunioni e invita l'account della sala di sistema sala skype, chiunque può usare la sala riunioni Skype for Business per partecipare alla riunione e può comporre qualsiasi numero di telefono nazionale/regionale o internazionale, purché l'organizzatore sia autorizzato a comporre tali numeri.</span><span class="sxs-lookup"><span data-stu-id="a3ab5-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
