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
description: Modificare le impostazioni del bridge di audioconferenza, incluse le notifiche di entrata e uscita, riprodurre nomi o numeri di telefono, toni e chiedere ai chiamanti di registrare il proprio nome.
ms.openlocfilehash: 7609ac7639012eb29d6d6cab4b482c1502d27c51
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51102643"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a><span data-ttu-id="c409c-103">Modificare le impostazioni per un bridge per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="c409c-103">Change the settings for an Audio Conferencing bridge</span></span>

<span data-ttu-id="c409c-104">Quando si configurano le audioconferenze in Microsoft 365 o Office 365, si riceveranno numeri di telefono per gli utenti da quello che viene chiamato bridge di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="c409c-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers for your users from what is called an audio conferencing bridge.</span></span> <span data-ttu-id="c409c-105">Un bridge di conferenza può contenere uno o più numeri di telefono.</span><span class="sxs-lookup"><span data-stu-id="c409c-105">A conferencing bridge can contain one or more phone numbers.</span></span> <span data-ttu-id="c409c-106">Questi numeri di telefono vengono usati quando i chiamanti a una riunione con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="c409c-106">These phone numbers are used when callers dial in to a meeting.</span></span> <span data-ttu-id="c409c-107">Il numero di telefono è incluso nella parte inferiore dell'invito alla riunione Skype for Business o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c409c-107">The phone number is included at the bottom of the Skype for Business or Microsoft Teams meeting invite.</span></span>
  
<span data-ttu-id="c409c-108">Il bridge di conferenza risponde a una chiamata e chiede al chiamante di usare un operatore automatico della riunione e quindi, a seconda delle impostazioni, può riprodurre notifiche, chiedere ai chiamanti di registrare il proprio nome e controllare le impostazioni del PIN.</span><span class="sxs-lookup"><span data-stu-id="c409c-108">The conferencing bridge answers a call and prompts the caller with voice prompts using a meeting auto attendant, and then, depending on your settings, it can play notifications, ask callers to record their name, and control the PIN settings.</span></span> <span data-ttu-id="c409c-109">I PIN vengono dati agli organizzatori della riunione per consentire loro di avviare una riunione quando non usano un'app Skype for Business o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c409c-109">PINs are given to meeting organizers to allow them to start a meeting when they are aren't using a Skype for Business or Microsoft Teams app.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="c409c-110">Un PIN è necessario per l'organizzatore della riunione solo quando un utente dell'app Skype for Business o Microsoft Teams non ha ancora avviato la riunione.</span><span class="sxs-lookup"><span data-stu-id="c409c-110">A PIN is only required for the meeting organizer when a Skype for Business or Microsoft Teams app user hasn't already started the meeting.</span></span> <span data-ttu-id="c409c-111">Se tutti gli utenti stanno per accedere alla riunione, il PIN è necessario per l'organizzatore della riunione per avviare la riunione.</span><span class="sxs-lookup"><span data-stu-id="c409c-111">If everyone is dialing in to the meeting, the PIN is required for the meeting organizer to start the meeting.</span></span> 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) <span data-ttu-id="c409c-113">Usando l'interfaccia di amministrazione di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c409c-113">Using the Microsoft Teams admin center</span></span>

1. <span data-ttu-id="c409c-114">Nel riquadro di spostamento sinistro passare a **Ponti**  >  **conferenza riunioni**.</span><span class="sxs-lookup"><span data-stu-id="c409c-114">In the left navigation, go to **Meetings** > **Conference bridges**.</span></span> 

2. <span data-ttu-id="c409c-115">Nella parte superiore della pagina **Bridge di conferenza** fare clic su Impostazioni **bridge.**</span><span class="sxs-lookup"><span data-stu-id="c409c-115">At the top of the **Conference bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="c409c-116">Nel riquadro **Impostazioni bridge** selezionare:</span><span class="sxs-lookup"><span data-stu-id="c409c-116">In the **Bridge settings** pane, select:</span></span> 
   - <span data-ttu-id="c409c-117">**Notifiche di entrata e uscita dalla riunione** Se si disattiva questa opzione, gli utenti che hanno già partecipato alla riunione non verranno avvisati quando un utente entra o esce dalla riunione.</span><span class="sxs-lookup"><span data-stu-id="c409c-117">**Meeting entry and exit notifications** If you turn this off, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
     <span data-ttu-id="c409c-118">Quando si attivano le **notifiche di entrata e uscita dalla** riunione, è possibile selezionare queste opzioni:</span><span class="sxs-lookup"><span data-stu-id="c409c-118">When you turn on **Meeting entry and exit notifications**, you can select these options:</span></span>
    
   - <span data-ttu-id="c409c-119">**Nomi o numeri di telefono** Quando gli utenti aderiscono a una riunione, il loro numero di telefono verrà riprodotto al momento dell'accesso.</span><span class="sxs-lookup"><span data-stu-id="c409c-119">**Names or phone numbers** When users dial in to a meeting, their phone number will be played when they join it.</span></span>
    
   - <span data-ttu-id="c409c-120">**Toni** Quando gli utenti aderiscono a una riunione, viene riprodotto un segnale audio quando aderiscono a una riunione.</span><span class="sxs-lookup"><span data-stu-id="c409c-120">**Tones** When users dial in to a meeting, an audio tone will be played when they join it.</span></span>
      
   - <span data-ttu-id="c409c-121">**Chiedere ai chiamanti di registrare il proprio nome prima di partecipare alla riunione** Se si disattiva questa opzione, ai chiamanti non verrà chiesto di registrare il nome prima di partecipare a una riunione.</span><span class="sxs-lookup"><span data-stu-id="c409c-121">**Ask callers to record their name before joining the meeting** If you turn this off, callers won't be asked to record their name before they join a meeting.</span></span>

4. <span data-ttu-id="c409c-122">Per impostare la lunghezza del PIN per le riunioni, selezionare il numero di cifre desiderato per il PIN **nell'elenco Lunghezza PIN.**</span><span class="sxs-lookup"><span data-stu-id="c409c-122">To set the PIN length for meetings, select the number of digits you want for the PIN in the **PIN length** list.</span></span>

5. <span data-ttu-id="c409c-123">Per specificare se inviare messaggi di posta elettronica agli utenti, abilitare o disabilitare Invia automaticamente messaggi di posta elettronica agli utenti se la configurazione delle **audioconferenze cambia.**</span><span class="sxs-lookup"><span data-stu-id="c409c-123">To specify whether to send email to your users, enable or disable **Automatically send emails to users if their audio conferencing configuration changes**.</span></span>
    <span data-ttu-id="c409c-124">Per altre [informazioni,](emails-sent-to-users-when-their-settings-change-in-teams.md) vedere Messaggi di posta elettronica inviati automaticamente agli utenti quando le impostazioni di audioconferenza cambiano in Microsoft Teams o Messaggi di posta elettronica inviati agli utenti quando le impostazioni cambiano [in Skype for Business online.](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change)</span><span class="sxs-lookup"><span data-stu-id="c409c-124">See [Emails automatically sent to users when their Audio Conferencing settings change in Microsoft Teams](emails-sent-to-users-when-their-settings-change-in-teams.md) or [Emails sent to users when their settings change in Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) for more information.</span></span>
 
6. <span data-ttu-id="c409c-125">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c409c-125">Click **Save**.</span></span> 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="c409c-126">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="c409c-126">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="c409c-127">Per risparmiare tempo o automatizzare questo processo, è possibile usare il cmdlet [Set-CsDialinConferencingBridge.](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge)</span><span class="sxs-lookup"><span data-stu-id="c409c-127">To save time or automate this process, you can use the [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) cmdlet.</span></span>
    
- <span data-ttu-id="c409c-128">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="c409c-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c409c-129">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare.</span><span class="sxs-lookup"><span data-stu-id="c409c-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="c409c-130">Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="c409c-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="c409c-131">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="c409c-131">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="c409c-132">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="c409c-132">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="c409c-133">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto solo all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="c409c-133">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="c409c-134">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="c409c-134">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="c409c-135">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="c409c-135">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="c409c-136">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="c409c-136">Using Windows PowerShell to manage Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
  - [<span data-ttu-id="c409c-137">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="c409c-137">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)
    
    > [!NOTE]
    > <span data-ttu-id="c409c-p107">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="c409c-p107">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c409c-140">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c409c-140">Related topics</span></span>

[<span data-ttu-id="c409c-141">Configurare Audioconferenza per Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c409c-141">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

[<span data-ttu-id="c409c-142">Configurare audioconferenze per Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="c409c-142">Set up Audio Conferencing for Skype for Business Online</span></span>](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)