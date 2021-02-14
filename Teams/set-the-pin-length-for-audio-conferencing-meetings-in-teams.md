---
title: Impostare la lunghezza dei PIN per le riunioni in audioconferenza
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
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: Informazioni sui parametri per la lunghezza e i requisiti di un PIN e su come impostare la durata delle riunioni in Microsoft Teams.
ms.openlocfilehash: 7fab4d42846dd5289f3255710684b75fe6fb07bc
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691102"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-microsoft-teams"></a><span data-ttu-id="566d5-103">Impostare la lunghezza del PIN per le riunioni con audioconferenza in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="566d5-103">Set the PIN length for Audio Conferencing meetings in Microsoft Teams</span></span>

<span data-ttu-id="566d5-104">Quando si configurano le audioconferenze per Microsoft Teams, si ottiene un bridge per i servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="566d5-104">When you are setting up audio conferencing for Microsoft Teams, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="566d5-105">Un bridge di conferenza può contenere uno o più numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="566d5-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="566d5-106">Il numero di telefono impostato verrà incluso nelle convocazioni di riunione per l'app Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="566d5-106">The phone number you set will be included on the meeting invites for the Microsoft Teams app.</span></span>
  
<span data-ttu-id="566d5-107">Il bridge di conferenza risponde a una chiamata di un utente che partecipa a una riunione utilizzando un telefono.</span><span class="sxs-lookup"><span data-stu-id="566d5-107">The audio conferencing bridge answers a call for people who are dialing in to a meeting using a phone.</span></span> <span data-ttu-id="566d5-108">Risponde al chiamante con i comandi vocali di un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre notifiche e chiedere ai chiamanti di registrare il proprio nome.</span><span class="sxs-lookup"><span data-stu-id="566d5-108">It answers the caller with voice prompts from an auto attendant and then, depending on your settings, can play notifications and ask callers to record their name.</span></span> <span data-ttu-id="566d5-109">**Impostazioni bridge Microsoft** consentono di modificare le impostazioni per le notifiche di riunione e l'esperienza di iscrizione alla riunione e impostare la lunghezza del PIN che vengono utilizzati per gli organizzatori delle riunioni.</span><span class="sxs-lookup"><span data-stu-id="566d5-109">**Microsoft bridge settings** allow you to change the settings for meeting notifications and the meeting join experience, and set the length of the PINs that are used by meeting organizers.</span></span> <span data-ttu-id="566d5-110">Gli organizzatori delle riunioni usano i PIN per avviare le riunioni se non possono partecipare usando l'app Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="566d5-110">Meeting organizers use PINs to start meetings if they can't join the meeting using the Microsoft Teams app.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a><span data-ttu-id="566d5-111">Impostazione della lunghezza del PIN</span><span class="sxs-lookup"><span data-stu-id="566d5-111">Setting the PIN length</span></span>

<span data-ttu-id="566d5-112">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="566d5-112">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="566d5-113">Nella barra di spostamento sinistra, passa **a Riunioni**-  >  **Bridge conferenza.**</span><span class="sxs-lookup"><span data-stu-id="566d5-113">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="566d5-114">Nella parte superiore della pagina **Bridge di conferenza** fare clic su Impostazioni **bridge.**</span><span class="sxs-lookup"><span data-stu-id="566d5-114">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

3. <span data-ttu-id="566d5-115">Nel riquadro **Impostazioni bridge,** in **Lunghezza PIN,** selezionare il numero di cifre desiderato per il PIN.</span><span class="sxs-lookup"><span data-stu-id="566d5-115">In the **Bridge settings** pane, under **PIN length**, select the number of digits you want for the PIN.</span></span>

4. <span data-ttu-id="566d5-116">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="566d5-116">Click **Save**.</span></span>

> [!NOTE]
> <span data-ttu-id="566d5-117">Un PIN è diverso da un ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="566d5-117">A PIN is different from a conference ID.</span></span> <span data-ttu-id="566d5-118">Gli ID conferenza vengono utilizzati dai chiamanti quando partecipano alla riunione.</span><span class="sxs-lookup"><span data-stu-id="566d5-118">Conference IDs are used by callers when they join the meeting.</span></span> <span data-ttu-id="566d5-119">Vengono utilizzati per identificare la riunione.</span><span class="sxs-lookup"><span data-stu-id="566d5-119">They are used to identify the meeting.</span></span> <span data-ttu-id="566d5-120">Il PIN viene utilizzato per autenticare un chiamante come organizzatore della riunione.</span><span class="sxs-lookup"><span data-stu-id="566d5-120">The PIN is used to authenticate a caller as the meeting organizer.</span></span> 

## <a name="want-to-know-more-about-pin-settings"></a><span data-ttu-id="566d5-121">Vuoi saperne di più sulle impostazioni del PIN?</span><span class="sxs-lookup"><span data-stu-id="566d5-121">Want to know more about PIN settings?</span></span>

- <span data-ttu-id="566d5-122">I PIN possono contenere da 4 a 12 cifre; l'impostazione predefinita è 5.</span><span class="sxs-lookup"><span data-stu-id="566d5-122">PINs can be from 4 to 12 digits; the default is 5.</span></span> <span data-ttu-id="566d5-123">Solo i numeri vengono utilizati quando si creano dei PIN.</span><span class="sxs-lookup"><span data-stu-id="566d5-123">Numbers are only used when creating PINs.</span></span> <span data-ttu-id="566d5-124">Lettere e caratteri speciali non vengono utilizzati.</span><span class="sxs-lookup"><span data-stu-id="566d5-124">Letters and special characters aren't used.</span></span>
    
- <span data-ttu-id="566d5-125">Il PIN è necessario solo per l'organizzatore della riunione quando un utente di Microsoft Teams non ha già avviato la riunione.</span><span class="sxs-lookup"><span data-stu-id="566d5-125">A PIN is only required for the meeting organizer when a Microsoft Teams user hasn't already started the meeting.</span></span> <span data-ttu-id="566d5-126">L'organizzatore della riunione ha bisogno di un PIN soltanto quando un utente di Skype for Business non ha già avviato la riunione.</span><span class="sxs-lookup"><span data-stu-id="566d5-126">If everyone is dialing in to the meeting, then the PIN is required for the meeting organizer to start the meeting.</span></span>
    
- <span data-ttu-id="566d5-127">Le impostazioni di sicurezza del PIN vengono applicate a tutti i numeri di telefono associati a un bridge Microsoft.</span><span class="sxs-lookup"><span data-stu-id="566d5-127">PIN security settings are applied to all of the phone numbers that are associated with a Microsoft bridge.</span></span> <span data-ttu-id="566d5-128">Vengono applicate a tutte le riunioni che utilizzano i numeri di telefono associati a un ponte specificato.</span><span class="sxs-lookup"><span data-stu-id="566d5-128">They will be applied to all meetings that use the phone numbers associated with a given bridge.</span></span> 
    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="566d5-129">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="566d5-129">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="566d5-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="566d5-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="566d5-131">Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="566d5-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 by using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="566d5-132">Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="566d5-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="566d5-133">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="566d5-133">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="566d5-134">Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="566d5-134">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="566d5-135">Per altre informazioni sulle Windows PowerShell, vedere le informazioni di riferimento su [Microsoft Teams PowerShell.](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="566d5-135">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="566d5-136">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="566d5-136">Related topics</span></span>

[<span data-ttu-id="566d5-137">Provare o acquistare audioconferenze in Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="566d5-137">Try or purchase Audio Conferencing in Microsoft 365 or Office 365</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
