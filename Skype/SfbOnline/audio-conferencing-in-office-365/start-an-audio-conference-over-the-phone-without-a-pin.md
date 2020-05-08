---
title: Avviare un'audioconferenza tramite telefono senza un PIN in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: "Informazioni su come abilitare o disabilitare la partecipazione dei chiamanti anonimi a una riunione dall'interfaccia di amministrazione di Skype for Business o utilizzando uno script di PowerShell. "
ms.openlocfilehash: f02d458450f07b64f3daf4d23b1c56aa2bb846a3
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2020
ms.locfileid: "44163875"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a><span data-ttu-id="b05bf-103">Avviare un'audioconferenza tramite telefono senza un PIN in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="b05bf-103">Start an Audio Conference over the phone without a PIN in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="b05bf-104">Per informazioni sull'avvio di un'audioconferenza senza un PIN in Microsoft Teams, consulta [Avviare un'audioconferenza tramite telefono senza un PIN in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span><span class="sxs-lookup"><span data-stu-id="b05bf-104">For information about starting an Audio Conference without a PIN in Microsoft Teams, see [Start an Audio Conference over the phone without a PIN  in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span></span>

<span data-ttu-id="b05bf-105">Potrebbe essere frustrante per gli utenti che accedono a una riunione che si terrà nella sala di attesa della riunione che ascolta la musica perché l'organizzatore della riunione Skype for business non ha avviato la riunione.</span><span class="sxs-lookup"><span data-stu-id="b05bf-105">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="b05bf-p101">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting. You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting. You can use the Skype for Business admin center to enable or disable this setting for a single user.</span><span class="sxs-lookup"><span data-stu-id="b05bf-p101">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting. You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting. You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="b05bf-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span><span class="sxs-lookup"><span data-stu-id="b05bf-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span></span> <span data-ttu-id="b05bf-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span><span class="sxs-lookup"><span data-stu-id="b05bf-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="b05bf-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span><span class="sxs-lookup"><span data-stu-id="b05bf-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="b05bf-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="b05bf-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="b05bf-113">Abilitare o disabilitare la partecipazione dei chiamanti anonimi a una riunione</span><span class="sxs-lookup"><span data-stu-id="b05bf-113">Enable or disable anonymous callers from joining a meeting</span></span>
    
1. <span data-ttu-id="b05bf-114">Nell'interfaccia di **amministrazione di Skype for business**, nella barra di spostamento sinistra, passa a**utenti**di servizi di **audioconferenza** > .</span><span class="sxs-lookup"><span data-stu-id="b05bf-114">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="b05bf-115">Nell'elenco selezionare l'utente e fare clic su **modifica**nel riquadro azioni.</span><span class="sxs-lookup"><span data-stu-id="b05bf-115">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="b05bf-116">Nella pagina delle proprietà dell'utente, in **Opzioni riunione**selezionare o deselezionare **Consenti ai chiamanti non autenticati di essere i primi partecipanti a una riunione. In caso contrario, aspetterà nella sala di attesa finché non si unisce un utente autenticato**.</span><span class="sxs-lookup"><span data-stu-id="b05bf-116">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="b05bf-117">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b05bf-117">Click **Save**.</span></span> 


    
 <span data-ttu-id="b05bf-118">**Tramite Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b05bf-118">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="b05bf-119">Esegui il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="b05bf-119">Run the following:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="b05bf-120">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="b05bf-120">What else should you know?</span></span>

- <span data-ttu-id="b05bf-121">Se si vuole reimpostare il PIN, vedere [reimpostare il pin per la conferenza audio](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="b05bf-121">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="b05bf-122">Se l'accesso anonimo o non richiede un PIN per avviare una riunione, è disabilitato:</span><span class="sxs-lookup"><span data-stu-id="b05bf-122">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="b05bf-123">Se la riunione non è ancora iniziata (non c'è nessuno nella riunione): A un chiamante verrà richiesto se è l'organizzatore; Se dice sì, verrà richiesto il PIN e, dopo aver inserito il PIN, verrà avviata la riunione e l'utente parteciperà alla riunione.</span><span class="sxs-lookup"><span data-stu-id="b05bf-123">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="b05bf-124">Se la riunione è già iniziata (qualcun altro è già nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN; la riunione è già iniziata e il chiamante potrà parteciparvi.</span><span class="sxs-lookup"><span data-stu-id="b05bf-124">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="b05bf-125">Se l'accesso anonimo o non richiede un PIN per avviare una riunione, è abilitato:</span><span class="sxs-lookup"><span data-stu-id="b05bf-125">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="b05bf-p103">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN. Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span><span class="sxs-lookup"><span data-stu-id="b05bf-p103">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN. Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="b05bf-128">Se la riunione è già iniziata (qualcun altro è già nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN; la riunione è già iniziata e il chiamante potrà parteciparvi.</span><span class="sxs-lookup"><span data-stu-id="b05bf-128">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="b05bf-129">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="b05bf-129">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="b05bf-130">Per renderle automatiche per più di un utente o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="b05bf-130">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
- <span data-ttu-id="b05bf-p104">Quando si tratta di Windows PowerShell, Skype for business online si occupa solo di gestire gli utenti e gli elementi consentiti o non consentiti. Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire. Per iniziare a usare Windows PowerShell, vedere questi argomenti:</span><span class="sxs-lookup"><span data-stu-id="b05bf-p104">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b05bf-134">Perché è necessario usare Microsoft 365 o Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="b05bf-134">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="b05bf-135">Procedure consigliate per gestire Microsoft 365 o Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b05bf-135">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="b05bf-p105">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo con l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="b05bf-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="b05bf-138">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="b05bf-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="b05bf-139">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="b05bf-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="b05bf-140">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="b05bf-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="b05bf-p106">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="b05bf-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="b05bf-143">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b05bf-143">Related topics</span></span>

[<span data-ttu-id="b05bf-144">Provare o acquistare servizi di audioconferenza in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="b05bf-144">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
