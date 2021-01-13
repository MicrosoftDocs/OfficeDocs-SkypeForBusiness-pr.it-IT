---
title: Distribuzioni locali di Skype room System Single Forest
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
description: Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente locale in una foresta singola.
ms.openlocfilehash: 0449a5e909fa044df12766aec0a036bf97315386
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820756"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="2b405-103">Distribuzioni locali di Skype room System Single Forest</span><span class="sxs-lookup"><span data-stu-id="2b405-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="2b405-104">Leggere questo argomento per informazioni su come distribuire Skype room System in un ambiente locale in una foresta singola.</span><span class="sxs-lookup"><span data-stu-id="2b405-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="2b405-105">In questa sezione viene fornita una panoramica dei passaggi per il provisioning dell'account del sistema di chat room Skype su Exchange Server e Skype for Business Server ospitato in una distribuzione locale di una singola foresta.</span><span class="sxs-lookup"><span data-stu-id="2b405-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="2b405-106">Distribuzioni locali della singola foresta</span><span class="sxs-lookup"><span data-stu-id="2b405-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="2b405-107">Se si dispone già di un account della cassetta postale delle risorse per la sala conferenze, è possibile utilizzarlo.</span><span class="sxs-lookup"><span data-stu-id="2b405-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="2b405-108">In caso contrario, è necessario crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="2b405-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="2b405-109">È possibile utilizzare Exchange Management Shell (PowerShell) o Exchange Management Console per creare un nuovo account di cassetta postale per la risorsa.</span><span class="sxs-lookup"><span data-stu-id="2b405-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="2b405-110">Si consiglia di usare una nuova cassetta postale per la risorsa di Skype (Delete Old mailbox and ricreate) per il sistema in chat.</span><span class="sxs-lookup"><span data-stu-id="2b405-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="2b405-111">Assicurarsi di eseguire il backup dei dati delle cassette postali prima di eliminarlo e quindi di riesportarlo nella cassetta postale ricreata utilizzando il client Outlook (vedere esportare o eseguire il backup di messaggi, calendario, attività e contatti per altre informazioni).</span><span class="sxs-lookup"><span data-stu-id="2b405-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="2b405-112">Per ripristinare le riunioni perse eliminando la cassetta postale, vedere [connettere o ripristinare una cassetta postale eliminata](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="2b405-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="2b405-113">Per utilizzare un account di cassetta postale per la risorsa esistente (ad esempio, LRS-01), attenersi alla procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="2b405-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="2b405-114">Eseguire il seguente comando di Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="2b405-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```powershell
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="2b405-115">Se si prevede di creare una nuova cassetta postale, eseguire il comando riportato di seguito per una singola organizzazione di Exchange in una foresta locale.</span><span class="sxs-lookup"><span data-stu-id="2b405-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```powershell
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="2b405-116">Nell'esempio precedente viene creato un account utente abilitato in Active Directory e una cassetta postale sala per una sala riunioni in un'organizzazione di Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="2b405-116">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization.</span></span> <span data-ttu-id="2b405-117">Il parametro RoomMailboxPassword consente di specificare la password per l'account utente.</span><span class="sxs-lookup"><span data-stu-id="2b405-117">The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="2b405-118">Configurare l'account per risolvere automaticamente i conflitti accettando o rifiutando le riunioni.</span><span class="sxs-lookup"><span data-stu-id="2b405-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="2b405-119">Gli account delle sale riunioni attrezzate con Skype room System in Exchange possono essere gestiti da singoli utenti, ma si noti che fino a quando l'utente non accetta una riunione non verrà visualizzato nel calendario della schermata iniziale del sistema Skype room.</span><span class="sxs-lookup"><span data-stu-id="2b405-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="2b405-120">Per un set completo di comandi disponibili, vedere Set-CalendarProcessing.</span><span class="sxs-lookup"><span data-stu-id="2b405-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="2b405-121">Per ricordare agli organizzatori della riunione di rendere la riunione una riunione Skype for business online in Outlook, utilizzare il seguente comando per configurare un avviso messaggio per il nuovo account:</span><span class="sxs-lookup"><span data-stu-id="2b405-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```powershell
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="2b405-122">Utilizzare i seguenti comandi per configurare le stringhe localizzate.</span><span class="sxs-lookup"><span data-stu-id="2b405-122">Use the following commands to configure localized strings.</span></span> <span data-ttu-id="2b405-123">Se richiesto dall'organizzazione, è anche possibile aggiungere le traduzioni personalizzate:</span><span class="sxs-lookup"><span data-stu-id="2b405-123">If required by your organization, you can also add custom translations:</span></span> 
   ```powershell
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="2b405-124">Facoltativo: configurare il testo di accettazione della riunione che fornisce agli utenti informazioni sulla sala riunioni di Skype for business e cosa aspettarsi durante la pianificazione e la partecipazione alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="2b405-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```powershell
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="2b405-125">Controllare l'account della cassetta postale delle risorse in Active Directory</span><span class="sxs-lookup"><span data-stu-id="2b405-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="2b405-126">L'account della cassetta postale della sala riunioni creato da Exchange nel passaggio 1 potrebbe essere un oggetto utente disabilitato in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2b405-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="2b405-127">Skype room System non è in grado di eseguire l'accesso o l'autenticazione tramite Kerberos/NTLM se l'account è disabilitato in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2b405-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="2b405-128">Il client del sistema Skype Room deve essere in grado di eseguire l'autenticazione con i servizi Web di Exchange per recuperare le impostazioni del calendario e deve anche essere in grado di inviare messaggi di posta elettronica con il contenuto della lavagna.</span><span class="sxs-lookup"><span data-stu-id="2b405-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="2b405-129">Pertanto, se l'account è disabilitato, è necessario abilitare questo account in Active Directory eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2b405-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="2b405-130">In Active Directory, eseguire il comando riportato di seguito per abilitare l'accesso all'account:</span><span class="sxs-lookup"><span data-stu-id="2b405-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```powershell
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="2b405-131">Se si esegue questo comando, verrà richiesto di immettere la password corrente e quindi di immettere di nuovo la password due volte per la conferma.</span><span class="sxs-lookup"><span data-stu-id="2b405-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="2b405-132">Dopo aver impostato la password, eseguire il comando riportato di seguito per abilitare l'account:</span><span class="sxs-lookup"><span data-stu-id="2b405-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```powershell
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="2b405-133">Abilitazione degli account di sistema di Skype room per Skype for business</span><span class="sxs-lookup"><span data-stu-id="2b405-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="2b405-134">In questa sezione viene fornita una panoramica dei passaggi necessari per abilitare Skype for business per l'account della sala riunioni, che sarà configurato su Skype room System.</span><span class="sxs-lookup"><span data-stu-id="2b405-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="2b405-135">Dopo aver creato un account per le cassette postali delle risorse per le sale conferenze, utilizzare Skype for Business Server Management Shell per abilitare gli account Skype for business room System.</span><span class="sxs-lookup"><span data-stu-id="2b405-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="2b405-136">La procedura seguente presuppone che sia stato abilitato l'account Skype room System in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="2b405-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="2b405-137">Eseguire il seguente comando per abilitare l'account del sistema di chat room Skype su un pool di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="2b405-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```powershell
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="2b405-138">Facoltativo: consentire a questo account di effettuare e ricevere telefonate PSTN abilitando l'account per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="2b405-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="2b405-139">VoIP aziendale non è necessario per Skype room System, ma se non lo si Abilita per VoIP aziendale, il client del sistema Skype room non sarà in grado di fornire la funzionalità di composizione PSTN:</span><span class="sxs-lookup"><span data-stu-id="2b405-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```powershell
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="2b405-140">Se si Abilita VoIP aziendale per l'account della sala riunioni di Skype room System, assicurarsi di configurare un criterio vocale limitato appropriato per la propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2b405-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="2b405-141">Se la sala riunioni di Skype for business è una risorsa disponibile pubblicamente, chiunque può utilizzarla per partecipare a una riunione, pianificata o ad hoc.</span><span class="sxs-lookup"><span data-stu-id="2b405-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="2b405-142">Dopo aver partecipato a una riunione, la persona potrebbe comporre qualsiasi numero.</span><span class="sxs-lookup"><span data-stu-id="2b405-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="2b405-143">In Skype for Business Server, la funzionalità di accesso esterno per le conferenze utilizza il criterio vocale dell'utente, in questo caso l'account di sistema della sala Skype utilizzato per partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="2b405-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="2b405-144">Nelle versioni precedenti di Lync Server, viene utilizzato il criterio vocale dell'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="2b405-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="2b405-145">Pertanto, se un utente di una versione precedente di Lync Server pianifica una sala riunioni e invita l'account della sala di Skype room System, chiunque può utilizzare la sala riunioni di Skype for business per partecipare alla riunione e potrebbe comporre un numero di telefono nazionale/regionale o internazionale, purché l'organizzatore sia autorizzato a comporre tali numeri.</span><span class="sxs-lookup"><span data-stu-id="2b405-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
  

