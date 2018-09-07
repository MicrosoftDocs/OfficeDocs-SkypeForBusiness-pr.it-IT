---
title: Reimpostare il PIN per audioconferenze in Skype for Business
mms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 67866a47-89c1-4593-8766-3a68777e2be6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Scoprire che cosa è necessario sapere sul PIN e come reimpostarlo in Skype for Business online. '
ms.openlocfilehash: 57431b51607f963f6dbd6da688e9bf7bd2758b53
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23854296"
---
# <a name="reset-the-audio-conferencing-pin-in-skype-for-business-online"></a><span data-ttu-id="7ca1c-103">Reimpostare il PIN per audioconferenze in Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7ca1c-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="7ca1c-104">Per informazioni sulla reimpostazione del PIN di audioconferenza in Microsoft Teams, vedere [reimpostare il PIN di audioconferenza di Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span><span class="sxs-lookup"><span data-stu-id="7ca1c-104">For information about resetting Audio Conferencing PINs in Microsoft Teams, see [Reset the Audio Conferencing PIN in Microsoft Teams](/MicrosoftTeams/reset-the-audio-conferencing-pin-in-teams).</span></span>

<span data-ttu-id="7ca1c-105">Un PIN è un codice numerico che viene creato per ogni utente Skype for Business abilitato alle audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-105">A PIN is a code made up of numbers that is created for each user who is enabled for dial-in conferencing.</span></span> <span data-ttu-id="7ca1c-106">Il PIN di audioconferenza viene utilizzato dall'organizzatore della riunione per dimostrare di essere l'organizzatore della stessa e poter avviare la riunione tramite telefono.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-106">Dial-in conferencing PINs are used by meeting organizers to identify that they are the meeting organizer and allow them to start a meeting over the phone.</span></span> <span data-ttu-id="7ca1c-107">Se per avviare la riunione l'organizzatore utilizza il client Skype for Business,  il PIN non è necessario.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-107">If they use the Skype for Business client to start the meeting, a PIN isn't required.</span></span> <span data-ttu-id="7ca1c-108">Se gli utenti dimenticano il PIN e non ritrovano la posta elettronica in cui è stato inviato quando sono stati abilitati per le audioconferenze, un amministratore o loro stessi possono reimpostare il PIN.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-108">If users forget their PIN and they can't find it in the email that was sent to them when they were enabled for dial-in conferencing, an administrator will need to reset their PIN.</span></span>
  
<span data-ttu-id="7ca1c-109">Le riunioni possono iniziare quando un utente autenticato partecipa utilizzando un client Skype for Business o quando l'organizzatore partecipa con il proprio PIN tramite telefono.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-109">Meetings can be started when an authenticated user joins using a Skype for Business client or when the organizer joins with his or her PIN over the phone.</span></span> <span data-ttu-id="7ca1c-110">Se è richiesto un PIN per avviare la riunione tramite telefono, per impostazione predefinita tutti gli utenti che partecipano alla riunione tramite telefono prima dell'inizio della riunione dovranno rimanere nella sala di attesa ascoltando musica fino all'inizio della riunione.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-110">When a meeting requires a PIN to start, users who join over the phone will be placed in the lobby and will listen to music on hold until the meeting starts.</span></span> <span data-ttu-id="7ca1c-111">Se l'organizzatore di una riunione non richiede il PIN per avviare la riunione tramite telefono, quando un chiamante tenta di partecipare alla riunione, non dovrà specificare un PIN.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-111">If the organizer of a meeting doesn't require a PIN to start the meeting over the phone, then callers won't be asked to provide a PIN when they join the meeting.</span></span>
  
## <a name="reset-a-users-pin"></a><span data-ttu-id="7ca1c-112">Reimpostare il PIN dell'utente</span><span class="sxs-lookup"><span data-stu-id="7ca1c-112">Reset a user's PIN</span></span>

1. <span data-ttu-id="7ca1c-113">Accedi a Office 365 con il tuo account aziendale o scolastico.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-113">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="7ca1c-114">Vai a**Centro di amministrazione di Office 365** > **Skype for Business**e nel riquadro di navigazione sinistro fai clic su **Audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-114">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation click **Dial-in conferencing**.</span></span>
    
3. <span data-ttu-id="7ca1c-115">Fai clic su **Utenti** e quindi seleziona l'utente a cui desideri reimpostare il PIN.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-115">Click on **Dial-in users**, select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="7ca1c-116">Nel riquadro Azioni, alla voce **PIN**, fai clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-116">In the Action pane, click **Reset PIN**.</span></span>
 
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
   
## <a name="have-a-user-reset-his-or-her-own-pin"></a><span data-ttu-id="7ca1c-117">Reimpostazione del PIN da parte dell'utente</span><span class="sxs-lookup"><span data-stu-id="7ca1c-117">Have a user reset his or her own PIN</span></span>

<span data-ttu-id="7ca1c-118">Un utente può reimpostare un PIN utilizzando l'opzione **Reimposta PIN** nella pagina **conferenza telefonica** .</span><span class="sxs-lookup"><span data-stu-id="7ca1c-118">A user can reset a PIN by using the **Reset PIN** option on the **Dial-in Conferencing** page.</span></span> <span data-ttu-id="7ca1c-119">Questa pagina è accessibile in uno dei tre modi seguenti:</span><span class="sxs-lookup"><span data-stu-id="7ca1c-119">This page can be accessed in one of three ways:</span></span>

* <span data-ttu-id="7ca1c-120">In un browser, accedere a [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span><span class="sxs-lookup"><span data-stu-id="7ca1c-120">In a browser, go to [https://mysettings.lync.com/pstncalling](https://mysettings.lync.com/pstncalling).</span></span>
* <span data-ttu-id="7ca1c-121">Skype for Business, fare clic sulla freccia **Mostra Menu** accanto al pulsante **Opzioni**e quindi fare clic su **Strumenti** > **Impostazioni di conferenza telefonica**.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-121">In Skype for Business, click the **Show Menu** arrow next to **Options**, and then click **Tools** > **Dial-in Conference Settings**.</span></span>
* <span data-ttu-id="7ca1c-122">In Skype for Business, fare clic su **Opzioni**, fare clic su **Inoltro di chiamata** nel menu a sinistra e quindi nella sezione **Altre impostazioni di chiamata** , fare clic su **Modifica impostazioni online**.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-122">In Skype for Business, click **Options**, click **Call Forwarding** in the left menu, and then in the **More Call Settings** section, click **Edit settings online**.</span></span> 

## <a name="what-else-should-you-know-about-pins"></a><span data-ttu-id="7ca1c-123">Quali sono le altre informazioni utili sul PIN?</span><span class="sxs-lookup"><span data-stu-id="7ca1c-123">What else should you know about PINs?</span></span>

- <span data-ttu-id="7ca1c-124">Ai fini della sicurezza, il PIN viene visualizzato solo una volta dall'amministratore, alla reimpostazione del PIN.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-124">For security purposes, the PIN is only shown to an administrator on one time, when the PIN is reset.</span></span> <span data-ttu-id="7ca1c-125">Dopo la reimpostazione del PIN da parte dell'amministratore, il PIN sarà visualizzato come \*\*\*\*\*\*\*\*\*\*\* nell'interfaccia di amministrazione di Skype for Business e nei risultati quando si utilizza **Get-CsCsOnlineDialInConfencingUser** in Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-125">After the PIN is reset by an administrator, the PIN will be listed as \*\*\*\*\*\*\*\*\*\*\* in the Skype for Business admin center and in the results when they use **Get-CsCsOnlineDialInConfencingUser** in the Windows PowerShell.</span></span>
    
- <span data-ttu-id="7ca1c-126">L'invio automatico dei messaggi di posta elettronica agli utenti è abilitato per impostazione predefinita e gli utenti riceveranno un messaggio di posta elettronica con il PIN al momento dell'abilitazione per i servizi di audioconferenza con accesso esterno o della reimpostazione del PIN.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-126">Automatically sending emails to users is enabled by default and users will receive an email with their PIN when they're enabled for dial-in conferencing or when the PIN is reset.</span></span> <span data-ttu-id="7ca1c-127">Se invece disabiliti l'invio automatico dei messaggi di posta elettronica, all'utente non verrà inviato un messaggio di posta elettronica di reimpostazione del PIN e dovrai inviare manualmente all'utente le informazioni relative al PIN.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-127">But if you have disabled automatically sending emails, then a PIN reset email won't be sent to a user and you will have to manually send the PIN information to the user.</span></span>
    
- <span data-ttu-id="7ca1c-p106">Quando la riunione inizia, tutti gli utenti nella sala di attesa si uniranno automaticamente. Se ad esempio due partecipanti tentano di partecipare a una riunione prima che questa inizi, dovranno rimanere nella sala di attesa ascoltando musica e quando l'organizzatore della riunione si unirà usando il proprio PIN tramite telefono, la riunione avrà inizio e i partecipanti nella sala di attesa potranno partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-p106">When a meeting starts, all of the users in the lobby will automatically join it. For example, if two participants try to join a meeting before it has been started, they will be put in the lobby and will listen to music on hold, and when the meeting organizer joins using his PIN via phone, the meeting will start and the participants in the lobby will join the meeting.</span></span>
    
- <span data-ttu-id="7ca1c-130">L'impostazione predefinita non consente a un chiamante anonimo di avviare una riunione.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-130">The default setting isn't to allow a meeting to be started by an anonymous callers.</span></span>
    
- <span data-ttu-id="7ca1c-131">Quando si attiva un utente per le audioconferenze, per impostazione predefinita vengono inviati i messaggi di posta elettronica che includono informazioni sulle conferenze e il proprio PIN.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-131">When you enable a user for dial-in conferencing, by default they are sent emails that includes conferencing information and their PIN.</span></span> <span data-ttu-id="7ca1c-132">L'utente deve disporre di una cassetta postale di Office 365, perché quando il PIN viene reimpostato, all'utente verrà inviato un nuovo PIN tramite messaggio di posta elettronica all'indirizzo SMTP primario (alias) impostato per l'utente.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-132">The user must have an Office 365 mailbox because when a PIN is reset, a new PIN will be sent to the user in email to their primary SMTP address (alias) that is set for the user.</span></span>
    
- <span data-ttu-id="7ca1c-133">Quando si imposta una audioconferenza, impostare le cifre necessari per il PIN nella propria organizzazione.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-133">When you set up audio conferencing, you set the digits that are required for the PINs in your organization.</span></span> <span data-ttu-id="7ca1c-134">I PIN possono essere composti da 4 fino a 12 cifre; il valore predefinito è 5.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-134">The PIN can only be from 4 to 12 digits. The default is 5.</span></span> <span data-ttu-id="7ca1c-135">Se si modifica l'impostazione della lunghezza del PIN, l'impostazione viene applicata solo sui PIN generati successivamente e non viene applicata per l'impostazione del PIN degli utenti precedetemente abilitati per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-135">If you change the PIN length setting, the setting is only applied on newly generated PINs and isn't applied to the PIN setting for existing users that are enabled for audio conferencing.</span></span> <span data-ttu-id="7ca1c-136">Vedere [impostare la lunghezza del PIN per le riunioni in audioconferenze](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span><span class="sxs-lookup"><span data-stu-id="7ca1c-136">See [Set the length of the PIN for Audio Conferencing meetings](Set-the-PIN-length-for-Audio-Conferencing-meetings.md).</span></span>
    
- <span data-ttu-id="7ca1c-137">Il messaggio di posta elettronica verrà inviato per impostazione predefinita all'indirizzo SMTP primario di Office 365 dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-137">The email by default will be set to the Office 365 primary SMTP address of the user you can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="7ca1c-138">È possibile inviare un messaggio di posta elettronica a un indirizzo non Office 365, ad esempio Hotmail o indirizzo di posta elettronica MSN.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-138">The email by default will be set to the Office 365 primary SMTP address of the user you can send an email to a non-Office 365 address such as a Hotmail or MSN email address.</span></span> <span data-ttu-id="7ca1c-139">È possibile sostituire l'indirizzo di posta elettronica predefinito tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-139">You can override the default email address by using Windows PowerShell.</span></span> <span data-ttu-id="7ca1c-140">Questa opzione è particolarmente utile se gli utenti non dispongono di una cassetta postale di Exchange in Office 365.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-140">This is useful if the users don't have an Exchange mailbox in Office 365.</span></span>
    
- <span data-ttu-id="7ca1c-141">Per sostituire l'indirizzo predefinito  a cui viene inviato il messaggio di posta elettronica, l'amministratore tenant può utilizzare il cmdlet seguente: Set-CsOnlineDialInConferencingUser-amos.marble - ResetLeaderPIN - SendEmail - SendEmailToAddress "u@hotmail.com".</span><span class="sxs-lookup"><span data-stu-id="7ca1c-141">To override the default user address where the email is sent to, the tenant admin can use the following cmdlet:  .</span></span> <span data-ttu-id="7ca1c-142">È necessario il parametro  SendEmail per sostituire l'indirizzo di posta elettronica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="7ca1c-142">The  SendEmail parameter is required to override the email address of the user.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="7ca1c-143">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="7ca1c-143">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="7ca1c-144">Per renderle automatiche o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="7ca1c-144">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="7ca1c-145">Puoi impostare il PIN per Amos Marble eseguendo:</span><span class="sxs-lookup"><span data-stu-id="7ca1c-145">You can set the PIN for Amos Marble by running:</span></span>
    
  ```
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com -ResetLeaderPIN
  ```

- <span data-ttu-id="7ca1c-p111">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="7ca1c-p111">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="7ca1c-149">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="7ca1c-149">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="7ca1c-150">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7ca1c-150">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="7ca1c-p112">Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="7ca1c-p112">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="7ca1c-153">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7ca1c-153">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="7ca1c-154">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7ca1c-154">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="7ca1c-155">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="7ca1c-155">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="7ca1c-p113">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="7ca1c-p113">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="7ca1c-158">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="7ca1c-158">Related topics</span></span>

[<span data-ttu-id="7ca1c-159">Reimpostare un ID conferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="7ca1c-159">Reset a conference ID for a user</span></span>](reset-a-conference-id-for-a-user.md)
