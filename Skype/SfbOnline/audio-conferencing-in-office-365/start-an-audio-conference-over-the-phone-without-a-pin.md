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
ms.openlocfilehash: 655f61c449554a9044095a5b8ef8bd8ef2940bc4
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237592"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-skype-for-business-online"></a><span data-ttu-id="c2c4b-103">Avviare un'audioconferenza tramite telefono senza un PIN in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="c2c4b-103">Start an Audio Conference over the phone without a PIN in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="c2c4b-104">Per informazioni sull'avvio di un'audioconferenza senza un PIN in Microsoft Teams, consulta [Avviare un'audioconferenza tramite telefono senza un PIN in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span><span class="sxs-lookup"><span data-stu-id="c2c4b-104">For information about starting an Audio Conference without a PIN in Microsoft Teams, see [Start an Audio Conference over the phone without a PIN  in Microsoft Teams](/MicrosoftTeams/start-an-audio-conference-over-the-phone-without-a-pin-in-teams).</span></span>

<span data-ttu-id="c2c4b-105">Può essere frustrante per gli utenti che a una riunione a una riunione si svolgono nella sala d'attesa della riunione che ascoltano musica perché l'organizzatore della riunione Skype for Business non ha avviato la riunione.</span><span class="sxs-lookup"><span data-stu-id="c2c4b-105">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Skype for Business meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="c2c4b-106">Se l'organizzatore della riunione chiama per impostazione predefinita, è necessario un PIN per avviare una riunione.</span><span class="sxs-lookup"><span data-stu-id="c2c4b-106">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="c2c4b-107">È possibile configurarla in modo che chiunque possa accedere a una riunione e non venga richiesto un PIN per avviare la riunione.</span><span class="sxs-lookup"><span data-stu-id="c2c4b-107">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="c2c4b-108">Puoi usare l'interfaccia di amministrazione di Skype for Business per abilitare o disabilitare questa impostazione per un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="c2c4b-108">You can use the Skype for Business admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="c2c4b-109">Non è necessario un PIN per l'organizzatore della riunione se qualcuno ha avviato la riunione dall'app Skype for Business riunione.</span><span class="sxs-lookup"><span data-stu-id="c2c4b-109">A PIN isn't required for the meeting organizer if someone has started the meeting from the Skype for Business app.</span></span> <span data-ttu-id="c2c4b-110">Il PIN è necessario solo quando l'organizzatore della riunione partecipa alla riunione tramite telefono.</span><span class="sxs-lookup"><span data-stu-id="c2c4b-110">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="c2c4b-111">Il PIN per le riunioni viene inviato all'utente audio quando gli viene assegnata la licenza **di audioconferenza** e viene abilitato per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="c2c4b-111">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="c2c4b-112">Vedere [Inviare un messaggio di posta](send-an-email-to-a-user-with-their-dial-in-information.md) elettronica a un utente con le informazioni relative alle audioconferenze e i messaggi di posta elettronica che vengono inviati automaticamente agli utenti quando cambiano le [impostazioni di audioconferenza.](emails-sent-to-users-when-their-settings-change.md)</span><span class="sxs-lookup"><span data-stu-id="c2c4b-112">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="c2c4b-113">Abilitare o disabilitare la partecipazione dei chiamanti anonimi a una riunione</span><span class="sxs-lookup"><span data-stu-id="c2c4b-113">Enable or disable anonymous callers from joining a meeting</span></span>
    
1. <span data-ttu-id="c2c4b-114">**Nell'Skype for Business di amministrazione,** nel riquadro di spostamento sinistro, passare a **Utenti di servizi di audioconferenza.**  >  </span><span class="sxs-lookup"><span data-stu-id="c2c4b-114">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**.</span></span> 
    
2. <span data-ttu-id="c2c4b-115">Nell'elenco selezionare l'utente e nel riquadro Azioni fare clic su **Modifica.**</span><span class="sxs-lookup"><span data-stu-id="c2c4b-115">In the list, select the user and in the Action pane click **Edit**.</span></span> 
    
3. <span data-ttu-id="c2c4b-116">Nella pagina delle proprietà dell'utente, in Opzioni **riunione,** selezionare o deselezionare Consenti ai chiamanti non autenticati di essere i primi **utenti di una riunione. In caso contrario, attenderà nella sala d'attesa finché un utente autenticato non si unisce**.</span><span class="sxs-lookup"><span data-stu-id="c2c4b-116">On the user's properties page, under **Meeting options**, select or clear **Allow unauthenticated callers to be the first people in a meeting. If not, then they will wait in the lobby until an authenticated user joins**.</span></span>
    
4. <span data-ttu-id="c2c4b-117">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c2c4b-117">Click **Save**.</span></span> 


    
 <span data-ttu-id="c2c4b-118">**Tramite Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c2c4b-118">**Using Windows Powershell**</span></span>
  
- <span data-ttu-id="c2c4b-119">Esegui il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="c2c4b-119">Run the following:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true | $false
  ```

## <a name="what-else-should-you-know"></a><span data-ttu-id="c2c4b-120">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="c2c4b-120">What else should you know?</span></span>

- <span data-ttu-id="c2c4b-121">Per reimpostare il PIN, vedere Reimpostare [il PIN dei servizi di audioconferenza.](reset-the-audio-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="c2c4b-121">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
- <span data-ttu-id="c2c4b-122">Se l'accesso anonimo o la richiesta di un PIN per avviare una riunione è disabilitata:</span><span class="sxs-lookup"><span data-stu-id="c2c4b-122">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="c2c4b-123">Se la riunione non è iniziata (non c'è ancora nessuno nella riunione): un chiamante riceverà una richiesta se è l'organizzatore; se dice sì, gli verrà richiesto il PIN e, dopo aver immesso il PIN, la riunione verrà avviata e l'utente si unirà alla riunione.</span><span class="sxs-lookup"><span data-stu-id="c2c4b-123">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="c2c4b-124">Se la riunione è già iniziata (qualcun altro è già nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN; la riunione è già iniziata e il chiamante potrà parteciparvi.</span><span class="sxs-lookup"><span data-stu-id="c2c4b-124">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="c2c4b-125">Se l'accesso anonimo, o non richiede un PIN per avviare una riunione, è abilitato:</span><span class="sxs-lookup"><span data-stu-id="c2c4b-125">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="c2c4b-126">Se la riunione non è iniziata (non c'è ancora nessuno nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN.</span><span class="sxs-lookup"><span data-stu-id="c2c4b-126">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="c2c4b-127">Poiché l'impostazione dell'organizzatore è disattivata, la riunione verrà avviata e i chiamanti anonimi si uniranno alla riunione.</span><span class="sxs-lookup"><span data-stu-id="c2c4b-127">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="c2c4b-128">Se la riunione è già iniziata (qualcun altro è già nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN; la riunione è già iniziata e il chiamante potrà parteciparvi.</span><span class="sxs-lookup"><span data-stu-id="c2c4b-128">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="c2c4b-129">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c2c4b-129">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="c2c4b-130">Per renderle automatiche per più di un utente o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).</span><span class="sxs-lookup"><span data-stu-id="c2c4b-130">To save time or automate this for more than one user, you can use the [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) cmdlet.</span></span>
    
- <span data-ttu-id="c2c4b-131">Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire.</span><span class="sxs-lookup"><span data-stu-id="c2c4b-131">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c2c4b-132">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare.</span><span class="sxs-lookup"><span data-stu-id="c2c4b-132">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="c2c4b-133">Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c2c4b-133">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c2c4b-134">Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c2c4b-134">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="c2c4b-135">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="c2c4b-135">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="c2c4b-136">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="c2c4b-136">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="c2c4b-137">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="c2c4b-137">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="c2c4b-138">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="c2c4b-138">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [<span data-ttu-id="c2c4b-139">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="c2c4b-139">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="c2c4b-140">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="c2c4b-140">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="c2c4b-p106">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="c2c4b-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c2c4b-143">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c2c4b-143">Related topics</span></span>

[<span data-ttu-id="c2c4b-144">Provare o acquistare audioconferenze in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="c2c4b-144">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
