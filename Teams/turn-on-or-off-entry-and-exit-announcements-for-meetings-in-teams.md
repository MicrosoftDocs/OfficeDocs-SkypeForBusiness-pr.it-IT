---
title: Attivare o disattivare gli annunci di entrata e uscita per le riunioni in teams
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
description: L'amministratore può scoprire come attivare o disattivare gli annunci di entrata e uscita in una riunione di Microsoft teams.
ms.openlocfilehash: 824949ea1c212f514830dfad3926444944ac099c
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44690982"
---
# <a name="turn-on-or-off-entry-and-exit-announcements-for-meetings-in-microsoft-teams"></a><span data-ttu-id="bf7c4-103">Attivare o disattivare gli annunci di entrata e uscita per le riunioni in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bf7c4-103">Turn on or off entry and exit announcements for meetings in Microsoft Teams</span></span>

<span data-ttu-id="bf7c4-104">Quando si configura una conferenza audio in Microsoft 365 o Office 365, si otterrà un Bridge per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="bf7c4-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will get an audio conferencing bridge.</span></span> <span data-ttu-id="bf7c4-105">Un Bridge per i servizi di conferenza può contenere uno o più numeri di telefono che gli utenti useranno per chiamare una riunione di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="bf7c4-105">A conferencing bridge can contain one or more phone numbers that people will use to call in to a Microsoft Teams meeting.</span></span> 
  
<span data-ttu-id="bf7c4-106">Il ponte per audioconferenze risponde a una chiamata di un utente che si collega a una riunione utilizzando un telefono.</span><span class="sxs-lookup"><span data-stu-id="bf7c4-106">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone.</span></span> <span data-ttu-id="bf7c4-107">Il ponte per audioconferenze risponde al chiamante con istruzioni vocali da un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre notifiche, chiedere ai chiamanti di registrare il proprio nome e impostare un PIN di sicurezza.</span><span class="sxs-lookup"><span data-stu-id="bf7c4-107">The conferencing bridge answers the caller with voice prompts from a conferencing auto attendant, and then, depending on your settings, can play notifications, ask callers to record their name, and set up the PIN security.</span></span> <span data-ttu-id="bf7c4-108">Un PIN viene assegnato a un organizzatore della riunione di Microsoft teams e consente loro di avviare una riunione se non è possibile avviare la riunione con l'app Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="bf7c4-108">A PIN is given to a Microsoft Teams meeting organizer, and it allows them to start a meeting if they can't start the meeting using the Microsoft Teams app.</span></span> <span data-ttu-id="bf7c4-109">È possibile impostarla, tuttavia, in modo che non sia richiesto un PIN per avviare una riunione.</span><span class="sxs-lookup"><span data-stu-id="bf7c4-109">You can, however, set it so that a PIN isn't required to start a meeting.</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]
  
## <a name="setting-meeting-join-options"></a><span data-ttu-id="bf7c4-110">Impostazione delle opzioni di partecipazione alla riunione</span><span class="sxs-lookup"><span data-stu-id="bf7c4-110">Setting meeting join options</span></span>

<span data-ttu-id="bf7c4-111">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="bf7c4-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

<span data-ttu-id="bf7c4-112">Per apportare queste modifiche, è necessario essere un amministratore.</span><span class="sxs-lookup"><span data-stu-id="bf7c4-112">You must be an admin to make these changes.</span></span>

1. <span data-ttu-id="bf7c4-113">Accedere all'interfaccia di amministrazione di  <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .</span><span class="sxs-lookup"><span data-stu-id="bf7c4-113">Log in to the admin center at <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.</span></span>

2. <span data-ttu-id="bf7c4-114">Nella barra di spostamento sinistra, Vai **Meetings**a  >  **Bridge conferenza**riunioni.</span><span class="sxs-lookup"><span data-stu-id="bf7c4-114">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

3. <span data-ttu-id="bf7c4-115">Nella parte superiore della pagina **ponti conferenza** fare clic su **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="bf7c4-115">At the top of the **Conference Bridges** page, click **Bridge Settings**.</span></span> 

4. <span data-ttu-id="bf7c4-116">Nel riquadro **Impostazioni Bridge** abilitare o disabilitare le **notifiche di entrata e uscita delle riunioni**.</span><span class="sxs-lookup"><span data-stu-id="bf7c4-116">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span> <span data-ttu-id="bf7c4-117">Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="bf7c4-117">This is selected by default.</span></span> <span data-ttu-id="bf7c4-118">Se lo si deseleziona, gli utenti che hanno già partecipato alla riunione non verranno informati quando qualcuno entra o esce dalla riunione.</span><span class="sxs-lookup"><span data-stu-id="bf7c4-118">If you clear it, users who have already joined the meeting won't be notified when someone enters or leaves the meeting.</span></span>
    
5. <span data-ttu-id="bf7c4-119">Su **Tipo di annuncio di entrata/uscita**, seleziona **Nomi o numeri di telefono** oppure **Suoni**.</span><span class="sxs-lookup"><span data-stu-id="bf7c4-119">Under **Entry/exit announcement type**, select **Names or phone numbers** or **Tones**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="bf7c4-120">Per impostazione predefinita, i partecipanti esterni non possono visualizzare i numeri di telefono dei partecipanti con accesso esterno.</span><span class="sxs-lookup"><span data-stu-id="bf7c4-120">By default, external participants can't see the phone numbers of dialed-in participants.</span></span> <span data-ttu-id="bf7c4-121">Se si vuole mantenere la privacy di questi numeri di telefono, selezionare **toni** per il **tipo di annuncio di entrata/uscita** (questo impedisce che i numeri vengano letti dalle squadre).</span><span class="sxs-lookup"><span data-stu-id="bf7c4-121">If you want to maintain the privacy of these phone numbers, select **Tones** for **Entry/exit announcement type** (this prevents the numbers from being read out by Teams).</span></span>
    
6. <span data-ttu-id="bf7c4-122">Se si sceglie **nomi o numeri di telefono**, abilitare o disabilitare i **chiamanti per registrare il nome prima di partecipare alla riunione**.</span><span class="sxs-lookup"><span data-stu-id="bf7c4-122">If you chose **Names or phone numbers**, enable or disable **Ask callers to record their name before joining the meeting**.</span></span>
    
7. <span data-ttu-id="bf7c4-123">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="bf7c4-123">Click **Save**.</span></span>

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="bf7c4-124">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf7c4-124">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="bf7c4-125">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="bf7c4-125">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="bf7c4-126">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="bf7c4-126">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="bf7c4-127">Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="bf7c4-127">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="bf7c4-128">Perché è necessario usare Microsoft 365 o Office 365 PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf7c4-128">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="bf7c4-129">Procedure consigliate per gestire Microsoft 365 o Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bf7c4-129">Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="bf7c4-130">Per altre informazioni su Windows PowerShell, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="bf7c4-130">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="bf7c4-131">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="bf7c4-131">Related topics</span></span>

[<span data-ttu-id="bf7c4-132">Domande ricorrenti sulle audioconferenze</span><span class="sxs-lookup"><span data-stu-id="bf7c4-132">Audio Conferencing common questions</span></span>](audio-conferencing-common-questions.md)
