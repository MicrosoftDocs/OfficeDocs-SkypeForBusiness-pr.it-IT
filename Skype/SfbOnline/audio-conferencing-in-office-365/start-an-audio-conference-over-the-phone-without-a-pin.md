---
title: Avviare una conferenza Audio nel telefono senza un PIN
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: 8a4b9c9cbb21c8a269e9d07285e4ecf68d2f2a7a
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin"></a><span data-ttu-id="12958-103">Avviare una conferenza Audio nel telefono senza un PIN</span><span class="sxs-lookup"><span data-stu-id="12958-103">Start an Audio Conference over the phone without a PIN</span></span>

<span data-ttu-id="12958-104">Può essere frustrante per gli utenti che accedono a una riunione per essere contenute nella sala d'attesa della riunione la musica di attesa perché Skype per Business o Microsoft Teams organizzatore della riunione non ha avviato la riunione.</span><span class="sxs-lookup"><span data-stu-id="12958-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business or Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="12958-105">Se un organizzatore della riunione chiama alla riunione, per impostazione predefinita, è necessario un PIN per avviare una riunione.</span><span class="sxs-lookup"><span data-stu-id="12958-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="12958-106">È possibile configurarlo in modo che tutti gli utenti possono connettersi a una riunione e non richiesto di immettere un PIN avviare la riunione.</span><span class="sxs-lookup"><span data-stu-id="12958-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="12958-107">Puoi usare l'interfaccia di amministrazione di Skype for Business per abilitare o disabilitare questa impostazione per un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="12958-107">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="12958-108">Se un utente ha avviato la riunione da Skype per applicazioni aziendali o Teams Microsoft non è necessario per l'organizzatore della riunione un PIN.</span><span class="sxs-lookup"><span data-stu-id="12958-108">A PIN isn't required for the meeting organizer if someone has started the meeting from a Skype for Business or Microsoft Teams app.</span></span> <span data-ttu-id="12958-109">Il PIN è necessario solo quando l'organizzatore della riunione partecipa alla riunione tramite telefono.</span><span class="sxs-lookup"><span data-stu-id="12958-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="12958-110">Il PIN per le riunioni viene inviato all'utente audio quando viene assegnati alla licenza di **Accesso esterno alle audioconferenze** e abilitati per le conferenze Audio.</span><span class="sxs-lookup"><span data-stu-id="12958-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="12958-111">Vedere [inviare un messaggio di posta elettronica a un utente con le loro informazioni di conferenze Audio](send-an-email-to-a-user-with-their-dial-in-information.md) e [messaggi di posta elettronica che vengono inviati automaticamente agli utenti quando modificano le impostazioni di conferenza Audio](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="12958-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="12958-112">Abilitare o disabilitare la partecipazione dei chiamanti anonimi a una riunione</span><span class="sxs-lookup"><span data-stu-id="12958-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="12958-113">**Utilizzo del team di Microsoft e Skype for Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="12958-113">**Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="12958-114">Nel riquadro di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="12958-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="12958-115">Selezionare un utente nell'elenco e quindi fare clic su **Modifica** nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="12958-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="12958-116">Fare clic sul menu accanto a **Ponti di conferenza**e quindi fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="12958-116">Click the menu next to **Conference Bridges**, and then click **Edit**.</span></span>

4. <span data-ttu-id="12958-117">Nel riquadro dei **provider di ponte conferenza** , abilitare o disabilitare i chiamanti Consenti non autenticato **diventi il prima persone a una riunione. Se non, quindi si attenderà nella sala di attesa fino a quando non si unisce a un utente autenticato**.</span><span class="sxs-lookup"><span data-stu-id="12958-117">In the **Conference bridge provider** pane, enable or disable **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="12958-118">Fare clic su **Applica**.</span><span class="sxs-lookup"><span data-stu-id="12958-118">Click **Apply**.</span></span> 

<span data-ttu-id="12958-119">**Utilizzo di Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="12958-119">**Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="12958-120">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="12958-120">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="12958-121">Nell'elenco, selezionare l'utente e nel riquadro azioni fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="12958-121">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="12958-122">Nella pagina proprietà dell'utente, in **Opzioni riunione**, selezionare o deselezionare i chiamanti Consenti non autenticato **diventi il prima persone a una riunione. Se non, quindi si attenderà nella sala di attesa fino a quando non si unisce a un utente autenticato**.</span><span class="sxs-lookup"><span data-stu-id="12958-122">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="12958-123">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="12958-123">Click **Save**.</span></span> 
    
 <span data-ttu-id="12958-124">**Utilizzo di Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="12958-124">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="12958-125">Esegui il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="12958-125">Run the following:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="12958-126">Quali altre informazioni devi conoscere?</span><span class="sxs-lookup"><span data-stu-id="12958-126">What else should you know?</span></span>

- <span data-ttu-id="12958-127">Se desideri reimpostare il PIN, vedi [Reimpostare il PIN di conferenza telefonica con accesso esterno per un utente](reset-the-audio-conferencing-pin-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="12958-127">If you want to reset the PIN, see [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin-for-a-user.md).</span></span>
    
- <span data-ttu-id="12958-128">Se è abilitato l'accesso anonimo o che non richiede un PIN avviare una riunione:</span><span class="sxs-lookup"><span data-stu-id="12958-128">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="12958-129">Se non ha avviato la riunione (esiste nessuno durante la riunione ancora): un chiamante viene richiesto se è l'organizzatore; Se afferma Sì, verrà richiesto per il PIN e dopo, inserisce il PIN, di inizio della riunione e l'utente verrà partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="12958-129">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="12958-130">Se la riunione già avviato (un'altra persona è già nella riunione): un chiamante non verrà richiesto se è l'organizzatore e mai, verrà richiesto per il PIN; la riunione è già stata avviata e il chiamante verrà accedervi.</span><span class="sxs-lookup"><span data-stu-id="12958-130">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="12958-131">Se l'accesso anonimo o che non richiede un PIN avviare una riunione è disabilitato:</span><span class="sxs-lookup"><span data-stu-id="12958-131">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="12958-132">Se non ha avviato la riunione (esiste nessuno durante la riunione ancora): un chiamante non verrà richiesto se quindi la collega è l'organizzatore e non verrà mai richiesto per il PIN.</span><span class="sxs-lookup"><span data-stu-id="12958-132">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="12958-133">Poiché l'impostazione dell'organizzatore viene impostato su off, di inizio della riunione e i chiamanti anonimi verranno aggiunto alla riunione.</span><span class="sxs-lookup"><span data-stu-id="12958-133">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="12958-134">Se la riunione già avviato (un'altra persona è già nella riunione): un chiamante non verrà richiesto se quindi la collega è l'organizzatore e non verrà mai richiesto per il PIN, la riunione è già stata avviata e il chiamante verrà accedervi.</span><span class="sxs-lookup"><span data-stu-id="12958-134">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="12958-135">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="12958-135">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="12958-136">Per renderle automatiche per più di un utente o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="12958-136">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
-  <span data-ttu-id="12958-p104">Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="12958-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="12958-140">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="12958-140">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="12958-141">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="12958-141">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="12958-p105">Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="12958-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="12958-144">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="12958-144">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="12958-145">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="12958-145">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="12958-146">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="12958-146">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="12958-p106">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="12958-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="12958-149">See also</span><span class="sxs-lookup"><span data-stu-id="12958-149">Related topics</span></span>

[<span data-ttu-id="12958-150">Provare o acquistare le audioconferenze in Office 365</span><span class="sxs-lookup"><span data-stu-id="12958-150">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
