---
title: Distribuzioni locali di Skype room System Single Forest
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 80da9d71-3dcd-4ca4-8bd1-6d8196823206
description: Leggere questo argomento per informazioni su come distribuire Skype room System in un unico ambiente della foresta locale.
ms.openlocfilehash: 107d4724defa11cbe506dcfa1b4f3c4725ee9910
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2019
ms.locfileid: "36245868"
---
# <a name="skype-room-system-single-forest-on-premises-deployments"></a><span data-ttu-id="c3aa5-103">Distribuzioni locali di Skype room System Single Forest</span><span class="sxs-lookup"><span data-stu-id="c3aa5-103">Skype Room System single forest on-premises deployments</span></span>
 
<span data-ttu-id="c3aa5-104">Leggere questo argomento per informazioni su come distribuire Skype room System in un unico ambiente della foresta locale.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-104">Read this topic to learn how to deploy Skype Room System in a single forest on-premises environment.</span></span>
  
<span data-ttu-id="c3aa5-105">Questa sezione offre una panoramica dei passaggi per il provisioning dell'account di sistema room Skype su Exchange Server e Skype for Business Server ospitato in una singola distribuzione locale della foresta.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-105">This section provides an overview of the steps for provisioning the Skype Room System account on Exchange Server and Skype for Business Server hosted in a single forest on-premises deployment.</span></span>
  
## <a name="single-forest-on-premises-deployments"></a><span data-ttu-id="c3aa5-106">Distribuzioni locali singole della foresta</span><span class="sxs-lookup"><span data-stu-id="c3aa5-106">Single forest on-premises deployments</span></span>

<span data-ttu-id="c3aa5-107">Se si dispone già di un account di cassetta postale delle risorse per la sala conferenze, è possibile usarlo.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-107">If you already have a resource mailbox account for the conferencing room, you can use it.</span></span> <span data-ttu-id="c3aa5-108">In caso contrario, sarà necessario crearne uno nuovo.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-108">Otherwise, you will need to create a new one.</span></span> <span data-ttu-id="c3aa5-109">È possibile usare Exchange Management Shell (PowerShell) o Exchange Management Console per creare un nuovo account di cassetta postale per la risorsa.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-109">You can use either Exchange Management Shell (PowerShell) or Exchange Management Console to create a new resource mailbox account.</span></span> <span data-ttu-id="c3aa5-110">È consigliabile usare una nuova cassetta postale delle risorse (Elimina vecchia cassetta postale e ricrea) per Skype room System.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-110">We recommend using a new (delete old mailbox and re-create) resource mailbox for Skype Room System.</span></span> <span data-ttu-id="c3aa5-111">Assicurarsi di eseguire il backup dei dati delle cassette postali prima di eliminarli e quindi di esportarli nella cassetta postale ricreata usando il client Outlook (vedere esportare o eseguire il backup di messaggi, calendario, attività e contatti per altre informazioni).</span><span class="sxs-lookup"><span data-stu-id="c3aa5-111">Make sure to back up mailbox data before deleting and then export it back to the re-created mailbox using the Outlook client (see Export or back up messages, calendar, tasks, and contacts for more information).</span></span> <span data-ttu-id="c3aa5-112">Per ripristinare le riunioni perse eliminando la cassetta postale, vedere [connettere o ripristinare una cassetta postale eliminata](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="c3aa5-112">To restore the meetings lost by deleting the mailbox, see [Connect or restore a deleted mailbox](https://technet.microsoft.com/library/jj863438%28v=exchg.150%29.aspx).</span></span> 
  
<span data-ttu-id="c3aa5-113">Per usare un account della cassetta postale delle risorse esistente, ad esempio LRS-01, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="c3aa5-113">To use an existing resource mailbox account (for example, LRS-01) follow the steps below:</span></span>
  
1. <span data-ttu-id="c3aa5-114">Eseguire il comando di PowerShell di Exchange Management seguente:</span><span class="sxs-lookup"><span data-stu-id="c3aa5-114">Run the following Exchange Management PowerShell command:</span></span>
    
   ```
   Set-Mailbox -Name 'LRS-01' -Alias 'LRS01' -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

2. <span data-ttu-id="c3aa5-115">Se si prevede di creare una nuova cassetta postale, eseguire il comando seguente per una singola organizzazione di Exchange locale della foresta:</span><span class="sxs-lookup"><span data-stu-id="c3aa5-115">If you plan to create a new mailbox, then, for a single forest on-premises Exchange organization, run the following command:</span></span>
    
   ```
   New-Mailbox -UserPrincipalName LRS01@contoso.com -Alias LRS01 -Name "LRS-01" -Room -EnableRoomMailboxAccount $true -RoomMailboxPassword (ConvertTo-SecureString -String <password> -AsPlainText -Force)
   ```

   <span data-ttu-id="c3aa5-116">Nell'esempio precedente viene creato un account utente abilitato in Active Directory e una cassetta postale della sala per una sala riunioni in un'organizzazione di Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-116">The above example creates an enabled user account in Active Directory and a room mailbox for a conference room in an on-premises Exchange organization.</span></span> <span data-ttu-id="c3aa5-117">Il parametro RoomMailboxPassword specifica la password per l'account utente.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-117">The RoomMailboxPassword parameter specifies the password for the user account.</span></span>
    
3. <span data-ttu-id="c3aa5-118">Configurare l'account per risolvere automaticamente i conflitti accettando o rifiutando le riunioni.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-118">Configure the account to automatically resolve conflicts by accepting/rejecting meetings.</span></span> <span data-ttu-id="c3aa5-119">Skype room System-attrezzato account sala conferenze in Exchange può essere gestito da singoli utenti, ma tenere presente che finché l'utente non accetta una riunione non verrà visualizzata nel calendario della schermata iniziale di Skype room System.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-119">Skype Room System-equipped conference room accounts in Exchange can be managed by individuals, but note that until the individual accepts a meeting it will not appear on the Skype Room System home screen calendar.</span></span>
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AutomateProcessing AutoAccept -AddOrganizerToSubject $false -DeleteSubject $false -RemovePrivateProperty $false
   ```

   <span data-ttu-id="c3aa5-120">Per un set completo di comandi disponibili, vedere Set-CalendarProcessing.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-120">For a complete set of commands available, see Set-CalendarProcessing.</span></span>
    
   <span data-ttu-id="c3aa5-121">Per ricordare agli organizzatori della riunione di partecipare a una riunione Skype for business online in Outlook, eseguire il comando seguente per configurare un MailTip per il nuovo account:</span><span class="sxs-lookup"><span data-stu-id="c3aa5-121">To remind meeting organizers to make the meeting an online Skype for Business meeting in Outlook, run the following command to set up a MailTip for the new account:</span></span> 
    
   ```
   Set-Mailbox -Identity LRS01@contoso.com -MailTip "This room is equipped with Lync Meeting Room (LRS), please make it a Lync Meeting to take advantage of the enhanced meeting experience from LRS"
   ```
4. <span data-ttu-id="c3aa5-122">Usare i comandi seguenti per configurare le stringhe localizzate.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-122">Use the following commands to configure localized strings.</span></span> <span data-ttu-id="c3aa5-123">Se richiesto dall'organizzazione, è anche possibile aggiungere traduzioni personalizzate:</span><span class="sxs-lookup"><span data-stu-id="c3aa5-123">If required by your organization, you can also add custom translations:</span></span> 
   ```
   $Temp = Get-Mailbox  LRS01@ contoso.com 
   $Temp.MailTipTranslations += "ES: Spanish translation of the message"
   Set-Mailbox -Identity LRS01@contoso.com -MailTipTranslations $Temp.MailTipTranslations
   ```

5. <span data-ttu-id="c3aa5-124">Facoltativo: configurare il testo di accettazione della riunione che fornisce agli utenti informazioni sulla sala riunioni di Skype for business e cosa aspettarsi quando pianificano e partecipano alle riunioni.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-124">Optional: Configure meeting acceptance text that provides users with information about Skype for Business Meeting Room, and what to expect when they schedule and join meetings.</span></span> 
    
   ```
   Set-CalendarProcessing -Identity LRS01 -AddAdditionalResponse $TRUE -AdditionalResponse "This is the Additional Response Text"
   ```

## <a name="check-resource-mailbox-account-in-active-directory"></a><span data-ttu-id="c3aa5-125">Controllare l'account delle cassette postali in Active Directory</span><span class="sxs-lookup"><span data-stu-id="c3aa5-125">Check Resource Mailbox Account in Active Directory</span></span>

<span data-ttu-id="c3aa5-126">L'account delle cassette postali della sala riunioni creato da Exchange nel passaggio 1 potrebbe essere un oggetto utente disabilitato in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-126">The conference room mailbox account created by Exchange in step 1 above might be a disabled user object in Active Directory.</span></span> <span data-ttu-id="c3aa5-127">Skype room System non è in grado di accedere o eseguire l'autenticazione tramite Kerberos/NTLM se l'account è disabilitato in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-127">Skype Room System cannot sign in or authenticate by using Kerberos/NTLM authentication if the account is disabled in Active Directory.</span></span> <span data-ttu-id="c3aa5-128">Il client di sistema room Skype deve essere in grado di eseguire l'autenticazione con i servizi Web di Exchange per recuperare le impostazioni del calendario e deve anche essere in grado di inviare messaggi di posta elettronica con il contenuto della lavagna.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-128">The Skype Room System client must be able to authenticate against Exchange Web Services to retrieve calendar settings, and must also be able to send email with whiteboard contents.</span></span> 
  
<span data-ttu-id="c3aa5-129">Pertanto, se l'account è disabilitato, è necessario abilitare questo account in Active Directory eseguendo le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c3aa5-129">Therefore, if the account is disabled, you must enable this account in Active Directory by doing the following:</span></span> 
  
1. <span data-ttu-id="c3aa5-130">In Active Directory eseguire il comando seguente per abilitare l'accesso all'account:</span><span class="sxs-lookup"><span data-stu-id="c3aa5-130">In Active Directory, run the following command to enable account log on:</span></span> 
    
   ```
   Set-ADAccountPassword -Identity LRS01
   ```

   <span data-ttu-id="c3aa5-131">In questo comando verrà chiesto di immettere la password corrente e quindi di immettere di nuovo la password due volte per la conferma.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-131">Running this command will prompt you to enter the current password, and then to re-enter the password twice for confirmation.</span></span>
    
2. <span data-ttu-id="c3aa5-132">Dopo aver impostato la password, eseguire il comando seguente per abilitare l'account:</span><span class="sxs-lookup"><span data-stu-id="c3aa5-132">Once the password is set, run the following command to enable the account:</span></span> 
    
   ```
   Enable-ADAccount -Identity LRS01
   ```

## <a name="enabling-skype-room-system-accounts-for-skype-for-business"></a><span data-ttu-id="c3aa5-133">Abilitazione degli account di Skype room System per Skype for business</span><span class="sxs-lookup"><span data-stu-id="c3aa5-133">Enabling Skype Room System Accounts for Skype for Business</span></span>

<span data-ttu-id="c3aa5-134">Questa sezione fornisce una panoramica dei passaggi necessari per abilitare Skype for business per l'account della sala riunioni, che sarà configurato in Skype room System.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-134">This section provides an overview of the steps required to enable Skype for Business for your conference room account, which will be configured on Skype Room System.</span></span> 
  
<span data-ttu-id="c3aa5-135">Dopo aver creato un account per le cassette postali per le sale conferenza, usare Skype for Business Server Management Shell per abilitare gli account di Skype for business room System.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-135">After you create a resource mailbox account for the conferencing rooms, use Skype for Business Server Management Shell to enable Skype Room System accounts for Skype for Business services.</span></span>
  
> [!NOTE]
> <span data-ttu-id="c3aa5-136">La procedura seguente presuppone che l'account di sistema della sala Skype sia stato abilitato in Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-136">The following procedure assumes that you have enabled the Skype Room System account in Active Directory.</span></span> 
  
1. <span data-ttu-id="c3aa5-137">Eseguire il comando seguente per abilitare l'account di sistema room Skype in un pool di Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="c3aa5-137">Run the following command to enable the Skype Room System account on a Skype for Business Server pool:</span></span>
    
   ```
   Enable-CsMeetingRoom -SipAddress "sip:LRS01@contoso.com" -domaincontroller DC-ND-001.contoso.com -RegistrarPool LYNCPool15.contoso.com -Identity LRS01
   ```

2. <span data-ttu-id="c3aa5-138">Facoltativo: consentire a questo account di effettuare e ricevere chiamate telefoniche PSTN abilitando l'account per VoIP aziendale.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-138">Optional: Allow this account to make and receive PSTN phone calls by enabling the account for Enterprise Voice.</span></span> <span data-ttu-id="c3aa5-139">Enterprise Voice non è necessaria per Skype room System, ma se non è abilitato per VoIP aziendale, il client di sistema room Skype non sarà in grado di specificare la funzionalità di chiamata PSTN:</span><span class="sxs-lookup"><span data-stu-id="c3aa5-139">Enterprise Voice is not required for Skype Room System, but if you do not enable it for Enterprise Voice, the Skype Room System client won't be able to provide PSTN dialing functionality:</span></span>
    
   ```
   Set-CsMeetingRoom LRS01 -domaincontroller DC-ND-001.contoso.com -LineURItel: +14255550555;ext=50555"
   Set-CsMeetingRoom -domaincontroller DC-ND-001.contoso.com -Identity LRS01 -EnterpriseVoiceEnabled $true
   ```

> [!NOTE]
> <span data-ttu-id="c3aa5-140">Se si Abilita Enterprise Voice per l'account della sala riunioni di Skype room System, assicurarsi di configurare un criterio vocale con restrizioni appropriato per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-140">If you enable Enterprise Voice for the Skype Room System conference room account, make sure to configure a restricted Voice Policy suitable for your organization.</span></span> <span data-ttu-id="c3aa5-141">Se la sala riunioni di Skype for business è una risorsa disponibile pubblicamente, chiunque può usarla per partecipare a una riunione, programmata o ad hoc.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-141">If the Skype for Business Meeting Room is a publicly available resource, anyone could use it to join a meeting, either scheduled or ad hoc.</span></span> <span data-ttu-id="c3aa5-142">Dopo aver partecipato a una riunione, la persona può effettuare la chiamata a qualsiasi numero.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-142">After joining a meeting, the person could dial out to any number.</span></span> <span data-ttu-id="c3aa5-143">In Skype for Business Server, la funzionalità di chiamata in uscita dalle conferenze usa il criterio vocale dell'utente, in questo caso l'account di sistema room Skype usato per partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-143">In Skype for Business Server, the dial-out from conferences feature uses the voice policy of the user, in this case the Skype Room System account used to join the meeting.</span></span> <span data-ttu-id="c3aa5-144">Nelle versioni precedenti di Lync Server viene usato il criterio vocale dell'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-144">In earlier versions of Lync Server, the voice policy of the organizer is used.</span></span> <span data-ttu-id="c3aa5-145">Pertanto, se un utente di una versione precedente di Lync Server pianifica una sala riunioni e invita l'account della sala di Skype room System, chiunque può usare la sala riunioni di Skype for business per partecipare alla riunione e può chiamare qualsiasi telefono nazionale/regionale o internazionale numero, purché l'organizzatore sia autorizzato a chiamare questi numeri.</span><span class="sxs-lookup"><span data-stu-id="c3aa5-145">Therefore, if a user of an earlier version of Lync Server schedules a meeting room and invites the Skype Room System room account, anyone could use the Skype for Business Meeting Room to join the meeting and could dial any national/regional or international phone number, as long as the organizer is allowed to dial those numbers.</span></span> 
  

