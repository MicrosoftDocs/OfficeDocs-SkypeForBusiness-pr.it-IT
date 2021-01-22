---
title: Modificare le impostazioni per un bridge per audioconferenza
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: Modificare le impostazioni del bridge per i servizi di audioconferenza, incluse le notifiche di accesso e uscita, riprodurre nomi o numeri di telefono, toni e chiedere ai chiamanti di registrare il proprio nome.
ms.openlocfilehash: 9694ac0cddecc5b00c0df133c5c494e4b5bc0d17
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918708"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="82013-103">Modificare le impostazioni per un bridge per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="82013-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="82013-104">Quando si configurano le audioconferenze in Microsoft 365 o Office 365, si riceveranno i numeri di telefono per gli utenti da un bridge per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="82013-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="82013-105">Un bridge di conferenza può contenere uno o più numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="82013-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="82013-106">Questi numeri di telefono vengono utilizzati per l'accesso esterno a una riunione.</span><span class="sxs-lookup"><span data-stu-id="82013-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="82013-107">Il numero di telefono è incluso nella parte inferiore dell'invito alla riunione di Skype for Business o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="82013-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="82013-108">Il bridge risponde a una chiamata e richiede al chiamante comandi vocali utilizzando un operatore automatico della riunione e quindi, a seconda delle impostazioni, può riprodurre notifiche, chiedere ai chiamanti di registrare il proprio nome e controllare le impostazioni del PIN.</span><span class="sxs-lookup"><span data-stu-id="82013-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="82013-109">I PIN vengono regalati agli organizzatori della riunione per consentire loro di avviare una riunione quando non usano un'app di Skype for Business o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="82013-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="82013-110">Il PIN è necessario solo per l'organizzatore della riunione quando un utente dell'app Skype for Business o Microsoft Teams non ha già avviato la riunione.</span><span class="sxs-lookup"><span data-stu-id="82013-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="82013-111">Se tutti i partecipanti stanno componendo il numero per la riunione, il PIN è necessario per l'avvio della riunione da parte dell'organizzatore.</span><span class="sxs-lookup"><span data-stu-id="82013-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="82013-113">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="82013-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="82013-114">Nella barra di spostamento sinistra, passa **a Bridge**  >  **conferenza riunioni.**</span><span class="sxs-lookup"><span data-stu-id="82013-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="82013-115">Nella parte superiore della pagina **Bridge conferenza** fare clic su **Impostazioni bridge.**</span><span class="sxs-lookup"><span data-stu-id="82013-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="82013-116">Nel riquadro **Impostazioni bridge** seleziona:</span><span class="sxs-lookup"><span data-stu-id="82013-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="82013-117">**Notifiche di accesso e uscita da una riunione** Se si disattiva questa opzione, gli utenti che hanno già partecipato alla riunione non verranno avvisati quando qualcuno entra o esce dalla riunione.</span><span class="sxs-lookup"><span data-stu-id="82013-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="82013-118">Quando si attivano le **notifiche di accesso e uscita da** una riunione, è possibile selezionare queste opzioni:</span><span class="sxs-lookup"><span data-stu-id="82013-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="82013-119">**Nomi o numeri di telefono** Quando un utente partecipa a una riunione tramite telefono, il suo numero di telefono viene riprodotto al momento dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="82013-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="82013-120">**Toni** Quando un utente partecipa a una riunione tramite telefono, viene riprodotto un tono audio quando un utente si unisce alla riunione.</span><span class="sxs-lookup"><span data-stu-id="82013-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="82013-121">**Chiedere ai chiamanti di registrare il proprio nome prima di partecipare alla riunione** Se si disattiva questa opzione, ai chiamanti non verrà chiesto di registrare il proprio nome prima di partecipare a una riunione.</span><span class="sxs-lookup"><span data-stu-id="82013-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="82013-122">Per impostare la lunghezza del PIN per le riunioni, selezionare il numero di cifre desiderato per il PIN **nell'elenco di lunghezza del PIN.**</span><span class="sxs-lookup"><span data-stu-id="82013-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="82013-123">Per specificare se inviare e-mail agli utenti, abilita o disabilita Invia automaticamente e-mail agli utenti in caso di modifiche alla configurazione delle **audioconferenze.**</span><span class="sxs-lookup"><span data-stu-id="82013-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="82013-124">Per [ulteriori informazioni,](emails-sent-to-users-when-their-settings-change-in-teams.md) vedi E-mail inviate automaticamente agli utenti quando le impostazioni di audioconferenza vengono modificate in Microsoft Teams o E-mail inviate agli utenti quando le impostazioni vengono modificate [in Skype for Business online.](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)</span><span class="sxs-lookup"><span data-stu-id="82013-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="82013-125">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="82013-125">Click **Save**.</span></span> 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="82013-126">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="82013-126">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="82013-127">Per risparmiare tempo o automatizzare questo processo, è possibile usare il cmdlet [Set-CsDialinConferencingBridge.](https://go.microsoft.com/fwlink/?LinkId=617686)</span><span class="sxs-lookup"><span data-stu-id="82013-127">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](https://go.microsoft.com/fwlink/?LinkId=617686) cmdlet.</span></span>
    
- <span data-ttu-id="82013-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="82013-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="82013-129">Con Windows PowerShell, è possibile gestire Microsoft 365 o Office 365 tramite un unico punto di amministrazione, che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="82013-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="82013-130">Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="82013-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="82013-131">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="82013-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="82013-132">Modi migliori per gestire Microsoft 365 o Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="82013-132">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="82013-133">Windows PowerShell offre molti vantaggi in termini di rapidità, semplicità e produttività rispetto all'uso della sola interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="82013-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="82013-134">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="82013-134">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="82013-135">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="82013-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="82013-136">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="82013-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="82013-137">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="82013-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="82013-p107">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="82013-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="82013-140">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="82013-140">Related topics</span></span>

[<span data-ttu-id="82013-141">Configurare Audioconferenza per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="82013-141">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="82013-142">Configurare le audioconferenze per Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="82013-142">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
