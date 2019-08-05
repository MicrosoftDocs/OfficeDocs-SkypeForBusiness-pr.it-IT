---
title: Avviare una conferenza audio tramite telefono senza PIN in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: d5b1f775-d7ed-4d30-853a-1d49f81e8fde
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Informazioni su come abilitare o disabilitare i chiamanti anonimi che partecipano a una riunione dall'interfaccia di amministrazione di teams. "
ms.openlocfilehash: 522970533565673b3fc68bcd5138006a6f6cf9d0
ms.sourcegitcommit: 4fb1c691f0f84d47e215c9c1775da9bdba875f61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2019
ms.locfileid: "36184429"
---
# <a name="start-an-audio-conference-over-the-phone-without-a-pin-in-microsoft-teams"></a><span data-ttu-id="f725e-103">Avviare una conferenza audio tramite telefono senza PIN in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f725e-103">Start an Audio Conference over the phone without a PIN in Microsoft Teams</span></span>

<span data-ttu-id="f725e-104">Potrebbe essere frustrante per gli utenti che accedono a una riunione che si terrà nella sala di attesa della riunione che ascolta la musica perché l'organizzatore della riunione Microsoft teams non ha avviato la riunione.</span><span class="sxs-lookup"><span data-stu-id="f725e-104">It might be frustrating for users who dial in to a meeting to be held in the meeting's lobby listening to music because the Microsoft Teams meeting organizer hasn't started the meeting.</span></span> 
  
<span data-ttu-id="f725e-105">Se un organizzatore della riunione chiama alla riunione, per impostazione predefinita è necessario un PIN per avviare una riunione.</span><span class="sxs-lookup"><span data-stu-id="f725e-105">If a meeting organizer calls in to the meeting, by default, a PIN is required to start a meeting.</span></span> <span data-ttu-id="f725e-106">È possibile configurarlo in modo che chiunque possa effettuare la chiamata a una riunione e non venga richiesto un PIN per avviare la riunione.</span><span class="sxs-lookup"><span data-stu-id="f725e-106">You can set it up so that anyone can dial in to a meeting and not be prompted for a PIN to start the meeting.</span></span> <span data-ttu-id="f725e-107">È possibile usare l'interfaccia di amministrazione per abilitare o disabilitare questa impostazione per un singolo utente.</span><span class="sxs-lookup"><span data-stu-id="f725e-107">You can use the admin center to enable or disable this setting for a single user.</span></span>
  
<span data-ttu-id="f725e-108">Un PIN non è necessario per l'organizzatore della riunione se qualcuno ha avviato la riunione dall'app Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="f725e-108">A PIN isn't required for the meeting organizer if someone has started the meeting from the Microsoft Teams app.</span></span> <span data-ttu-id="f725e-109">Il PIN è necessario solo quando l'organizzatore della riunione partecipa alla riunione tramite telefono.</span><span class="sxs-lookup"><span data-stu-id="f725e-109">A PIN is only required when a meeting organizer joins their meeting over a phone.</span></span> <span data-ttu-id="f725e-110">Il PIN per le riunioni viene inviato all'utente audio quando viene assegnata la \*\*\*\* licenza di audioconferenza e abilitata per l'audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="f725e-110">The PIN for meetings is sent to the audio user when they are assigned the **Audio Conferencing** license and are enabled for Audio Conferencing.</span></span> <span data-ttu-id="f725e-111">Vedere [inviare un messaggio di posta elettronica a un utente con le informazioni di audioconferenza e i](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) [messaggi di posta elettronica inviati automaticamente agli utenti quando cambiano le impostazioni dei](emails-sent-to-users-when-their-settings-change-in-teams.md)servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="f725e-111">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md) and [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change-in-teams.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-anonymous-callers-from-joining-a-meeting"></a><span data-ttu-id="f725e-112">Abilitare o disabilitare la partecipazione dei chiamanti anonimi a una riunione</span><span class="sxs-lookup"><span data-stu-id="f725e-112">Enable or disable anonymous callers from joining a meeting</span></span>

<span data-ttu-id="f725e-113">![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="f725e-113">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="f725e-114">Nella barra di spostamento sinistra fare clic su **utenti**.</span><span class="sxs-lookup"><span data-stu-id="f725e-114">In the left navigation, click **Users**.</span></span> 

2. <span data-ttu-id="f725e-115">Selezionare un utente nell'elenco e quindi fare clic su **modifica** nella parte superiore della pagina.</span><span class="sxs-lookup"><span data-stu-id="f725e-115">Select a user in the list, and then click **Edit** at the top of the page.</span></span> 

3. <span data-ttu-id="f725e-116">Accanto a servizi di **audioconferenza**fare clic su **modifica**.</span><span class="sxs-lookup"><span data-stu-id="f725e-116">Next to **Audio Conferencing**, click **Edit**.</span></span>

4. <span data-ttu-id="f725e-117">Nel riquadro **audioconferenza** abilitare o disabilitare **i chiamanti non autenticati può essere la prima persona di una riunione**.</span><span class="sxs-lookup"><span data-stu-id="f725e-117">In the **Audio Conferencing** pane, enable or disable **Unauthenticated callers can be the first person in a meeting**.</span></span>
    
4. <span data-ttu-id="f725e-118">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f725e-118">Click **Save**.</span></span> 

<span data-ttu-id="f725e-119">**Tramite Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f725e-119">**Using Windows Powershell**</span></span>
  
<span data-ttu-id="f725e-120">Per altre informazioni, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .</span><span class="sxs-lookup"><span data-stu-id="f725e-120">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-else-should-you-know"></a><span data-ttu-id="f725e-121">Quali altre informazioni devi conoscere?</span><span class="sxs-lookup"><span data-stu-id="f725e-121">What else should you know?</span></span>

- <span data-ttu-id="f725e-122">Se si vuole reimpostare il PIN, vedere [reimpostare il pin per la conferenza audio](reset-the-audio-conferencing-pin-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="f725e-122">If you want to reset the PIN, see [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
- <span data-ttu-id="f725e-123">Se l'accesso anonimo o non richiede un PIN per avviare una riunione, è disabilitato:</span><span class="sxs-lookup"><span data-stu-id="f725e-123">If anonymous access, or not requiring a PIN to start a meeting, is disabled:</span></span>
    
  - <span data-ttu-id="f725e-124">Se la riunione non è ancora iniziata (non c'è nessuno nella riunione): A un chiamante verrà richiesto se è l'organizzatore; Se dice sì, verrà richiesto il PIN e, dopo aver inserito il PIN, verrà avviata la riunione e l'utente parteciperà alla riunione.</span><span class="sxs-lookup"><span data-stu-id="f725e-124">If the meeting hasn't started (there's no one in the meeting yet): A caller will be prompted if he's the organizer; if he says yes, he'll be prompted for his PIN, and after he inputs the PIN, the meeting will start and the user will join the meeting.</span></span>
    
  - <span data-ttu-id="f725e-125">Se la riunione è già iniziata (qualcun altro è già nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN; la riunione è già iniziata e il chiamante potrà parteciparvi.</span><span class="sxs-lookup"><span data-stu-id="f725e-125">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if he's the organizer and he'll never be prompted for the PIN; the meeting is already started, and the caller will join it.</span></span>
    
- <span data-ttu-id="f725e-126">Se l'accesso anonimo o non richiede un PIN per avviare una riunione, è abilitato:</span><span class="sxs-lookup"><span data-stu-id="f725e-126">If anonymous access, or not requiring a PIN to start a meeting, is enabled:</span></span>
    
  - <span data-ttu-id="f725e-127">Se la riunione non è iniziata (non c'è ancora nessuno nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN.</span><span class="sxs-lookup"><span data-stu-id="f725e-127">If the meeting hasn't started (there's no one in the meeting yet): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN.</span></span> <span data-ttu-id="f725e-128">Dato che l'impostazione dell'organizzatore è impostata su disattivato, la riunione verrà avviata e i chiamanti anonimi si uniranno alla riunione.</span><span class="sxs-lookup"><span data-stu-id="f725e-128">Because the setting of the organizer is set to off, the meeting will start and the anonymous callers will join the meeting.</span></span>
    
  - <span data-ttu-id="f725e-129">Se la riunione è già iniziata (qualcun altro è già nella riunione): al chiamante non verrà chiesto se è l'organizzatore e non gli verrà mai richiesto il PIN; la riunione è già iniziata e il chiamante potrà parteciparvi.</span><span class="sxs-lookup"><span data-stu-id="f725e-129">If the meeting already started (someone else is already in the meeting): A caller won't be prompted if she's the organizer, and she'll never be prompted for the PIN,;the meeting is already started, and the caller will join it.</span></span>
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f725e-130">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f725e-130">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="f725e-p104">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="f725e-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f725e-134">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="f725e-134">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="f725e-135">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f725e-135">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="f725e-136">Per altre informazioni su Windows PowerShell, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="f725e-136">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f725e-137">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f725e-137">Related topics</span></span>

[<span data-ttu-id="f725e-138">Provare o acquistare le audioconferenze in Office 365</span><span class="sxs-lookup"><span data-stu-id="f725e-138">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
