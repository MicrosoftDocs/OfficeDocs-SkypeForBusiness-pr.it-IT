---
title: Impostare la lunghezza del PIN per le riunioni di audioconferenza in Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Per informazioni sui parametri relativi alla lunghezza e ai requisiti di un PIN, vedere come impostare la lunghezza delle riunioni in Microsoft teams.
ms.openlocfilehash: 938e8096cf39c482a2de9f143174e6c261c652d8
ms.sourcegitcommit: 30995da65ff6a9b33534c3818833cf0ae1952ab9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/22/2019
ms.locfileid: "36183439"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="0758c-103">Impostare la lunghezza del PIN per le riunioni di audioconferenza in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0758c-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="0758c-104">Quando si configura una conferenza audio per Microsoft teams, si otterrà un Bridge per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="0758c-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="0758c-105">Un Bridge per i servizi di conferenza può contenere uno o più numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="0758c-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="0758c-106">Il numero di telefono impostato verrà incluso nell'invito alla riunione per l'app Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="0758c-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="0758c-107">Il Bridge per i servizi di audioconferenza risponde a una chiamata per gli utenti che accedono a una riunione tramite telefono.</span><span class="sxs-lookup"><span data-stu-id="0758c-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="0758c-108">Risponde al chiamante con le richieste vocali di un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre le notifiche e chiedere ai chiamanti di registrare il proprio nome.</span><span class="sxs-lookup"><span data-stu-id="0758c-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="0758c-109">**Impostazioni bridge Microsoft** consentono di modificare le impostazioni per le notifiche di riunione e l'esperienza di iscrizione alla riunione e impostare la lunghezza del PIN che vengono utilizzati per gli organizzatori delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="0758c-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="0758c-110">Gli organizzatori della riunione usano i pin per avviare le riunioni se non possono partecipare alla riunione usando l'app Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="0758c-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="0758c-111">Impostazione della lunghezza del PIN</span><span class="sxs-lookup"><span data-stu-id="0758c-111">Setting the PIN length</span></span>

<span data-ttu-id="0758c-112">![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="0758c-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="0758c-113">Nella barra di spostamento sinistra, vai a**Bridge conferenza** **riunioni** > .</span><span class="sxs-lookup"><span data-stu-id="0758c-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="0758c-114">Nella parte superiore della pagina **ponti conferenza** fare clic su **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="0758c-114">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="0758c-115">Nel riquadro **Impostazioni Bridge** , in **lunghezza PIN**, selezionare il numero di cifre desiderato per il PIN.</span><span class="sxs-lookup"><span data-stu-id="0758c-115">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="0758c-116">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0758c-116">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="0758c-117">Un PIN è diverso da un ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="0758c-117">A PIN is different from a conference ID.</span></span> <span data-ttu-id="0758c-118">Gli ID conferenza vengono utilizzati dai chiamanti quando partecipano alla riunione.</span><span class="sxs-lookup"><span data-stu-id="0758c-118">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="0758c-119">Vengono utilizzati per identificare la riunione.</span><span class="sxs-lookup"><span data-stu-id="0758c-119">They are used to identify the meeting.</span></span> <span data-ttu-id="0758c-120">Il PIN viene utilizzato per autenticare un chiamante come organizzatore della riunione.</span><span class="sxs-lookup"><span data-stu-id="0758c-120">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="0758c-121">Vuoi saperne di più sulle impostazioni del PIN?</span><span class="sxs-lookup"><span data-stu-id="0758c-121">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="0758c-122">I pin possono essere da 4 a 12 cifre; il valore predefinito è 5.</span><span class="sxs-lookup"><span data-stu-id="0758c-122">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="0758c-123">Solo i numeri vengono utilizati quando si creano dei PIN.</span><span class="sxs-lookup"><span data-stu-id="0758c-123">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="0758c-124">Lettere e caratteri speciali non vengono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="0758c-124">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="0758c-125">Un PIN è necessario solo per l'organizzatore della riunione quando un utente di Microsoft teams non ha già avviato la riunione.</span><span class="sxs-lookup"><span data-stu-id="0758c-125">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="0758c-126">L'organizzatore della riunione ha bisogno di un PIN soltanto quando un utente di Skype for Business non ha già avviato la riunione.</span><span class="sxs-lookup"><span data-stu-id="0758c-126">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="0758c-127">Le impostazioni di sicurezza del PIN vengono applicate a tutti i numeri di telefono associati a un bridge Microsoft.</span><span class="sxs-lookup"><span data-stu-id="0758c-127">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="0758c-128">Vengono applicate a tutte le riunioni che utilizzano i numeri di telefono associati a un ponte specificato.</span><span class="sxs-lookup"><span data-stu-id="0758c-128">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="0758c-129">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0758c-129">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="0758c-p107">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="0758c-p107">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="0758c-133">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="0758c-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="0758c-134">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="0758c-134">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="0758c-135">Per altre informazioni su Windows PowerShell, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="0758c-135">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="0758c-136">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0758c-136">Related topics</span></span>

[<span data-ttu-id="0758c-137">Provare o acquistare le audioconferenze in Office 365</span><span class="sxs-lookup"><span data-stu-id="0758c-137">Try or purchase Audio Conferencing in Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
