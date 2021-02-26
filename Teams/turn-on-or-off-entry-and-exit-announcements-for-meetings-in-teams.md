---
title: Attivare o disattivare gli annunci di entrata e di uscita per le riunioni di Teams.
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: f2c7b5ea-07b6-4b77-8023-bec9596fcc32
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-apr2020
description: Informazioni per gli amministratori su come attivare o disattivare gli annunci di entrata e di uscita per le riunioni di Microsoft Teams.
ms.openlocfilehash: 145965f3ff2737b21c8fcb13c144e07e969fbeef
ms.sourcegitcommit: 3e5cac88911611c94c0330bf50af9c34db308cdf
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 07/22/2020
ms.locfileid: "45372205"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="f3055-103">Attivare o disattivare gli annunci di entrata e di uscita per le riunioni di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f3055-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="f3055-104">Quando viene impostata Audioconferenza in Microsoft 365 o Office 365, si ottieni un bridge di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="f3055-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="f3055-105">Un bridge di audioconferenza può contenere uno o più numeri di telefono che le persone utilizzano per partecipare a una riunione Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f3055-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span>
  
<span data-ttu-id="f3055-106">Il ponte per audioconferenze risponde a una chiamata di un utente che si collega a una riunione utilizzando un telefono.</span><span class="sxs-lookup"><span data-stu-id="f3055-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="f3055-107">Il ponte per audioconferenze risponde al chiamante con istruzioni vocali da un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre notifiche, chiedere ai chiamanti di registrare il proprio nome e impostare un PIN di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f3055-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="f3055-108">Viene assegnato un PIN all’organizzatore della riunione di Microsoft Teams, che permette di avviare la riunione se i partecipanti non possono farlo tramite l'app di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f3055-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="f3055-109">È possibile impostarla, tuttavia, in modo che non sia richiesto un PIN per avviare una riunione.</span><span class="sxs-lookup"><span data-stu-id="f3055-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="f3055-110">Impostazione delle opzioni di partecipazione alla riunione</span><span class="sxs-lookup"><span data-stu-id="f3055-110">Setting meeting join options</span></span>

<span data-ttu-id="f3055-111">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="f3055-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="f3055-112">Per apportare queste modifiche, è necessario essere un amministratore del servizio Teams.</span><span class="sxs-lookup"><span data-stu-id="f3055-112">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="f3055-113">Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) per informazioni su come ottenere ruoli e autorizzazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="f3055-113">See [Use Teams administrator roles to manage Teams](https://docs.microsoft.com/microsoftteams/using-admin-roles) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="f3055-114">Accedere all'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="f3055-114">Log in to the admin center.</span></span>

2. <span data-ttu-id="f3055-115">Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="f3055-115">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span>

3. <span data-ttu-id="f3055-116">Nella parte superiore della pagina **Bridge di conferenza** fare clic su **Impostazioni bridge**.</span><span class="sxs-lookup"><span data-stu-id="f3055-116">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span>

4. <span data-ttu-id="f3055-117">Nel riquadro **Impostazioni bridge**, abilitare o disabilitare **Notifiche di entrata e di uscita per le riunioni**.</span><span class="sxs-lookup"><span data-stu-id="f3055-117">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="f3055-118">Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f3055-118">This is selected by default.</span></span> <span data-ttu-id="f3055-119">Se si deseleziona l’opzione, gli utenti che partecipano alla riunione non verranno avvisati quando un utente entra o esce dalla riunione.</span><span class="sxs-lookup"><span data-stu-id="f3055-119">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>

5. <span data-ttu-id="f3055-120">Su **Tipo di annuncio di entrata/uscita**, seleziona **Nomi o numeri di telefono** oppure **Suoni**.</span><span class="sxs-lookup"><span data-stu-id="f3055-120">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f3055-121">Per impostazione predefinita, i partecipanti esterni non possono vedere i numeri di telefono dei partecipanti che hanno eseguito l'accesso tramite telefono.</span><span class="sxs-lookup"><span data-stu-id="f3055-121">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="f3055-122">Se si vuole mantenere la privacy di tali numeri di telefono, selezionare **Toni** per **Tipo di annuncio in entrata/uscita**, in modo da evitare che i numeri vengano letti da Teams.</span><span class="sxs-lookup"><span data-stu-id="f3055-122">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>

6. <span data-ttu-id="f3055-123">Se si è scelto **Nomi o numeri di telefono**, abilitare o disabilitare **Chiedere ai chiamanti di registrarne il nome prima di partecipare alla riunione**.</span><span class="sxs-lookup"><span data-stu-id="f3055-123">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>

7. <span data-ttu-id="f3055-124">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f3055-124">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f3055-125">Per altre informazioni su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f3055-125">Want to know more about Windows PowerShell</span></span>

<span data-ttu-id="f3055-126">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="f3055-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f3055-127">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare.</span><span class="sxs-lookup"><span data-stu-id="f3055-127">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="f3055-128">Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f3055-128">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="f3055-129">Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f3055-129">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

- [<span data-ttu-id="f3055-130">Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore</span><span class="sxs-lookup"><span data-stu-id="f3055-130">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

<span data-ttu-id="f3055-131">Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="f3055-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f3055-132">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f3055-132">Related topics</span></span>

[<span data-ttu-id="f3055-133">Domande ricorrenti sulle audioconferenze</span><span class="sxs-lookup"><span data-stu-id="f3055-133">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
