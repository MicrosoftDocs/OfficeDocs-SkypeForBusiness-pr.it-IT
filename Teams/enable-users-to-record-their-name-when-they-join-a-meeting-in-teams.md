---
title: Consentire agli utenti di registrare il proprio nome per una riunione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
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
description: Informazioni su come abilitare o disabilitare se gli utenti possono registrare i loro nomi quando partecipano a una riunione in Microsoft teams.
ms.openlocfilehash: d7cab4fca4ad3e7732704da9837522d51314061d
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691582"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="af748-103">Consentire agli utenti di registrare il proprio nome quando partecipano a una riunione in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="af748-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="af748-104">Quando si configurano i servizi di audioconferenza in Microsoft 365 o Office 365, si riceveranno i numeri di telefono e il cosiddetto Bridge di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="af748-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="af748-105">Un Bridge per i servizi di conferenza può contenere uno o più numeri di telefono che possono essere un numero di telefono dedicato o condiviso.</span><span class="sxs-lookup"><span data-stu-id="af748-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="af748-p102">Il bridge di conferenza risponde alla chiamata di un utente che sta eseguendo l'accesso a una riunione con il telefono. Il bridge risponde con i comandi vocali di un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre notifiche, richiedere ai chiamanti di registrare il proprio nome e configurare le opzioni di sicurezza del PIN per gli organizzatori della riunione. I PIN sono assegnati a un organizzatore della riunione per consentire l'avvio della stessa. Puoi comunque configurarla in modo tale che non sia richiesto il PIN per l'avvio.</span><span class="sxs-lookup"><span data-stu-id="af748-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="af748-110">Impostare se i chiamanti devono registrare il nome</span><span class="sxs-lookup"><span data-stu-id="af748-110">Set whether callers should record their name</span></span>

<span data-ttu-id="af748-111">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="af748-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="af748-112">Nella barra di spostamento sinistra, Vai **Meetings**a  >  **Bridge conferenza**riunioni.</span><span class="sxs-lookup"><span data-stu-id="af748-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="af748-113">Nella parte superiore della pagina **ponti conferenza** fare clic su **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="af748-113">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="af748-114">Abilitare o disabilitare **le notifiche di entrata e uscita delle riunioni**.</span><span class="sxs-lookup"><span data-stu-id="af748-114">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="af748-115">Se si abilitano le notifiche, scegliere **nomi o numeri di telefono** in **tipo di annuncio di entrata/uscita**e quindi attivare **Chiedi ai chiamanti di registrare il proprio nome prima di partecipare a una riunione.**</span><span class="sxs-lookup"><span data-stu-id="af748-115">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="af748-116">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="af748-116">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="af748-117">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="af748-117">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="af748-118">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="af748-118">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="af748-119">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="af748-119">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="af748-120">Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="af748-120">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="af748-121">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="af748-121">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="af748-122">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="af748-122">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="af748-123">Per altre informazioni su Windows PowerShell, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="af748-123">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="af748-124">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="af748-124">Related topics</span></span>

[<span data-ttu-id="af748-125">Provare o acquistare servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="af748-125">Try or purchase Audio Conferencing</span></span>](https://docs.microsoft.com/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)
