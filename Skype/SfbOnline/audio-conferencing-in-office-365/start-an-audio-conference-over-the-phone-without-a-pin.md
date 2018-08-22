---
title: Avviare una conferenza Audio nel telefono senza un PIN in Skype Business online
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Learn how to enable or disable anonymous callers from joining a meeting from the Skype for Business admin center or using a PowerShell script. '
ms.openlocfilehash: f0e65b3ea4ad5c989137307a1c41bc70bc092086
ms.sourcegitcommit: 6207b98e8395f6c640b61cfb3f6c85d96520e33b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/20/2018
ms.locfileid: "22490556"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a><span data-ttu-id="5a78c-103">Avviare una conferenza Audio nel telefono senza un PIN in Skype Business online</span><span class="sxs-lookup"><span data-stu-id="5a78c-103">Start an Audio Conference over the phone without a PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="5a78c-104">Per informazioni su Microsoft Teams a partire da una conferenza Audio senza un PIN, vedere [avviare una conferenza Audio nel telefono senza un PIN nel team di Microsoft](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span><span class="sxs-lookup"><span data-stu-id="5a78c-104">For information about starting an Audio Conference without a PIN in Microsoft Teams, see [Start an Audio Conference over the phone without a PIN  in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span></span>

<span data-ttu-id="5a78c-105">Può essere frustrante per gli utenti che accedono a una riunione per essere contenute nella sala d'attesa della riunione la musica di attesa perché Skype per l'organizzatore della riunione Business non ha avviato la riunione.</span><span class="sxs-lookup"><span data-stu-id="5a78c-105">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="5a78c-106">Se un organizzatore della riunione chiama alla riunione, per impostazione predefinita, è necessario un PIN per avviare una riunione.</span><span class="sxs-lookup"><span data-stu-id="5a78c-106">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="5a78c-107">È possibile configurarlo in modo che tutti gli utenti possono connettersi a una riunione e non richiesto di immettere un PIN avviare la riunione.</span><span class="sxs-lookup"><span data-stu-id="5a78c-107">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="5a78c-108">Puoi usare l'interfaccia di amministrazione di Skype for Business per abilitare o disabilitare questa impostazione per un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="5a78c-108">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="5a78c-109">Un PIN non è necessario per l'organizzatore della riunione se qualcuno ha avviato la riunione da Skype per applicazioni aziendali.</span><span class="sxs-lookup"><span data-stu-id="5a78c-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span></span> <span data-ttu-id="5a78c-110">Il PIN è necessario solo quando l'organizzatore della riunione partecipa alla riunione tramite telefono.</span><span class="sxs-lookup"><span data-stu-id="5a78c-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="5a78c-111">Il PIN per le riunioni viene inviato all'utente audio quando viene assegnati alla licenza di **Accesso esterno alle audioconferenze** e abilitati per le conferenze Audio.</span><span class="sxs-lookup"><span data-stu-id="5a78c-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="5a78c-112">Vedere [inviare un messaggio di posta elettronica a un utente con le loro informazioni di conferenze Audio](send-an-email-to-a-user-with-their-dial-in-information.md) e [messaggi di posta elettronica che vengono inviati automaticamente agli utenti quando modificano le impostazioni di conferenza Audio](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="5a78c-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="5a78c-113">Abilitare o disabilitare la partecipazione dei chiamanti anonimi a una riunione</span><span class="sxs-lookup"><span data-stu-id="5a78c-113">Enable or disable anonymous callers from joining a meeting</span></span>
    
1. <span data-ttu-id="5a78c-114">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="5a78c-114">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="5a78c-115">Nell'elenco, selezionare l'utente e nel riquadro azioni fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="5a78c-115">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="5a78c-116">Nella pagina proprietà dell'utente, in **Opzioni riunione**, selezionare o deselezionare i chiamanti Consenti non autenticato **diventi il prima persone a una riunione. Se non, quindi si attenderà nella sala di attesa fino a quando non si unisce a un utente autenticato**.</span><span class="sxs-lookup"><span data-stu-id="5a78c-116">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="5a78c-117">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5a78c-117">Click **Save**.</span></span> 


    
 <span data-ttu-id="5a78c-118">**Utilizzo di Windows Powershell**</span><span class="sxs-lookup"><span data-stu-id="5a78c-118">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="5a78c-119">Esegui il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="5a78c-119">Run the following:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="5a78c-120">Quali altre informazioni devi conoscere?</span><span class="sxs-lookup"><span data-stu-id="5a78c-120">What else should you know?</span></span>

- <span data-ttu-id="5a78c-121">Se si desidera reimpostare il PIN, vedere [reimpostare il PIN per le conferenze Audio](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="5a78c-121">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="5a78c-122">Se è abilitato l'accesso anonimo o che non richiede un PIN avviare una riunione:</span><span class="sxs-lookup"><span data-stu-id="5a78c-122">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="5a78c-123">Se non ha avviato la riunione (esiste nessuno durante la riunione ancora): un chiamante viene richiesto se è l'organizzatore; Se afferma Sì, verrà richiesto per il PIN e dopo, inserisce il PIN, di inizio della riunione e l'utente verrà partecipare alla riunione.</span><span class="sxs-lookup"><span data-stu-id="5a78c-123">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="5a78c-124">Se la riunione già avviato (un'altra persona è già nella riunione): un chiamante non verrà richiesto se è l'organizzatore e mai, verrà richiesto per il PIN; la riunione è già stata avviata e il chiamante verrà accedervi.</span><span class="sxs-lookup"><span data-stu-id="5a78c-124">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="5a78c-125">Se l'accesso anonimo o che non richiede un PIN avviare una riunione è disabilitato:</span><span class="sxs-lookup"><span data-stu-id="5a78c-125">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="5a78c-126">Se non ha avviato la riunione (esiste nessuno durante la riunione ancora): un chiamante non verrà richiesto se quindi la collega è l'organizzatore e non verrà mai richiesto per il PIN.</span><span class="sxs-lookup"><span data-stu-id="5a78c-126">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="5a78c-127">Poiché l'impostazione dell'organizzatore viene impostato su off, di inizio della riunione e i chiamanti anonimi verranno aggiunto alla riunione.</span><span class="sxs-lookup"><span data-stu-id="5a78c-127">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="5a78c-128">Se la riunione già avviato (un'altra persona è già nella riunione): un chiamante non verrà richiesto se quindi la collega è l'organizzatore e non verrà mai richiesto per il PIN, la riunione è già stata avviata e il chiamante verrà accedervi.</span><span class="sxs-lookup"><span data-stu-id="5a78c-128">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="5a78c-129">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5a78c-129">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="5a78c-130">Per renderle automatiche per più di un utente o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="5a78c-130">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
-  <span data-ttu-id="5a78c-p104">Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="5a78c-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5a78c-134">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="5a78c-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="5a78c-135">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5a78c-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="5a78c-p105">Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="5a78c-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="5a78c-138">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5a78c-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="5a78c-139">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5a78c-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="5a78c-140">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5a78c-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="5a78c-p106">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="5a78c-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="5a78c-143">See also</span><span class="sxs-lookup"><span data-stu-id="5a78c-143">Related topics</span></span>

[<span data-ttu-id="5a78c-144">Provare o acquistare le audioconferenze in Office 365</span><span class="sxs-lookup"><span data-stu-id="5a78c-144">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
