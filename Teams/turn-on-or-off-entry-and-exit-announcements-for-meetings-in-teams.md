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
ms.openlocfilehash: 6be1c6dc86d8088b5ddb54b2141a10172ba13cc5
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51121334"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="f4290-103">Attivare o disattivare gli annunci di entrata e di uscita per le riunioni di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f4290-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="f4290-104">Quando viene impostata Audioconferenza in Microsoft 365 o Office 365, si ottieni un bridge di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="f4290-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="f4290-105">Un bridge di audioconferenza può contenere uno o più numeri di telefono che le persone utilizzano per partecipare a una riunione Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f4290-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span>
  
<span data-ttu-id="f4290-106">Il ponte per audioconferenze risponde a una chiamata di un utente che si collega a una riunione utilizzando un telefono.</span><span class="sxs-lookup"><span data-stu-id="f4290-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="f4290-107">Il ponte per audioconferenze risponde al chiamante con istruzioni vocali da un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre notifiche, chiedere ai chiamanti di registrare il proprio nome e impostare un PIN di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="f4290-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="f4290-108">Viene assegnato un PIN all’organizzatore della riunione di Microsoft Teams, che permette di avviare la riunione se i partecipanti non possono farlo tramite l'app di Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="f4290-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="f4290-109">È possibile impostarla, tuttavia, in modo che non sia richiesto un PIN per avviare una riunione.</span><span class="sxs-lookup"><span data-stu-id="f4290-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="f4290-110">Impostazione delle opzioni di partecipazione alla riunione</span><span class="sxs-lookup"><span data-stu-id="f4290-110">Setting meeting join options</span></span>

<span data-ttu-id="f4290-111">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="f4290-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="f4290-112">Per apportare queste modifiche, è necessario essere un amministratore del servizio Teams.</span><span class="sxs-lookup"><span data-stu-id="f4290-112">You must be a Teams service admin to make these changes.</span></span> <span data-ttu-id="f4290-113">Vedere [Usare i ruoli di amministratore di Teams per gestire Teams](./using-admin-roles.md) per informazioni su come ottenere ruoli e autorizzazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="f4290-113">See [Use Teams administrator roles to manage Teams](./using-admin-roles.md) to read about getting admin roles and permissions.</span></span>

1. <span data-ttu-id="f4290-114">Accedere all'interfaccia di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="f4290-114">Log in to the admin center.</span></span>

2. <span data-ttu-id="f4290-115">Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="f4290-115">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span>

3. <span data-ttu-id="f4290-116">Nella parte superiore della pagina **Bridge di conferenza** fare clic su **Impostazioni bridge**.</span><span class="sxs-lookup"><span data-stu-id="f4290-116">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span>

4. <span data-ttu-id="f4290-117">Nel riquadro **Impostazioni bridge**, abilitare o disabilitare **Notifiche di entrata e di uscita per le riunioni**.</span><span class="sxs-lookup"><span data-stu-id="f4290-117">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="f4290-118">Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="f4290-118">This is selected by default.</span></span> <span data-ttu-id="f4290-119">Se si deseleziona l’opzione, gli utenti che partecipano alla riunione non verranno avvisati quando un utente entra o esce dalla riunione.</span><span class="sxs-lookup"><span data-stu-id="f4290-119">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>

5. <span data-ttu-id="f4290-120">Su **Tipo di annuncio di entrata/uscita**, seleziona **Nomi o numeri di telefono** oppure **Suoni**.</span><span class="sxs-lookup"><span data-stu-id="f4290-120">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="f4290-121">Per impostazione predefinita, i partecipanti esterni non possono vedere i numeri di telefono dei partecipanti che hanno eseguito l'accesso tramite telefono.</span><span class="sxs-lookup"><span data-stu-id="f4290-121">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="f4290-122">Se si vuole mantenere la privacy di tali numeri di telefono, selezionare **Toni** per **Tipo di annuncio in entrata/uscita**, in modo da evitare che i numeri vengano letti da Teams.</span><span class="sxs-lookup"><span data-stu-id="f4290-122">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>

6. <span data-ttu-id="f4290-123">Se si è scelto **Nomi o numeri di telefono**, abilitare o disabilitare **Chiedere ai chiamanti di registrarne il nome prima di partecipare alla riunione**.</span><span class="sxs-lookup"><span data-stu-id="f4290-123">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>

7. <span data-ttu-id="f4290-124">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f4290-124">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="f4290-125">Per altre informazioni su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f4290-125">Want to know more about Windows PowerShell</span></span>

<span data-ttu-id="f4290-126">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="f4290-126">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="f4290-127">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare.</span><span class="sxs-lookup"><span data-stu-id="f4290-127">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="f4290-128">Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="f4290-128">To get started with Windows PowerShell, see these topics:</span></span>

- [<span data-ttu-id="f4290-129">Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f4290-129">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

- <span data-ttu-id="f4290-130">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="f4290-130">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

<span data-ttu-id="f4290-131">Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="f4290-131">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f4290-132">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f4290-132">Related topics</span></span>

[<span data-ttu-id="f4290-133">Domande ricorrenti sulle audioconferenze</span><span class="sxs-lookup"><span data-stu-id="f4290-133">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)