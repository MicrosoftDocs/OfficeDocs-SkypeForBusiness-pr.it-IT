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
description: Informazioni su come abilitare o disabilitare se gli utenti possono registrare i loro nomi quando aderiscono a una riunione in Microsoft Teams.Learn how to enable or disable whether your users can record their names when they join a meeting in Microsoft Teams.
ms.openlocfilehash: 8b92e0d4a73cc18ceaf374f1a05102e51752c083
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092694"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-microsoft-teams"></a><span data-ttu-id="94346-103">Consentire agli utenti di registrare il proprio nome quando si uniscono a una riunione in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="94346-103">Enable users to record their name when they join a meeting in Microsoft Teams</span></span>

<span data-ttu-id="94346-104">Quando si configurano le audioconferenze in Microsoft 365 o Office 365, si riceveranno i numeri di telefono e il cosiddetto bridge di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="94346-104">When you are setting up Audio Conferencing in Microsoft 365 or Office 365, you will receive phone numbers and what is called an audio conferencing bridge.</span></span> <span data-ttu-id="94346-105">Un bridge di conferenza può contenere uno o più numeri di telefono che possono essere un numero di telefono dedicato o condiviso.</span><span class="sxs-lookup"><span data-stu-id="94346-105">A conferencing bridge can contain one or more phone numbers that can be a dedicated or shared phone number.</span></span>
  
<span data-ttu-id="94346-p102">Il bridge di conferenza risponde alla chiamata di un utente che sta eseguendo l'accesso a una riunione con il telefono. Il bridge risponde con i comandi vocali di un operatore automatico e quindi, a seconda delle impostazioni, può riprodurre notifiche, richiedere ai chiamanti di registrare il proprio nome e configurare le opzioni di sicurezza del PIN per gli organizzatori della riunione. I PIN sono assegnati a un organizzatore della riunione per consentire l'avvio della stessa. Puoi comunque configurarla in modo tale che non sia richiesto il PIN per l'avvio.</span><span class="sxs-lookup"><span data-stu-id="94346-p102">The conferencing bridge answers a call for a user who is dialing in to a meeting using a phone. The conferencing bridge answers the caller with voice prompts from an auto attendant, and then, depending on their settings, can play notifications, ask callers to record their name, and set up the PIN security for meeting organizers. PINs are given to meeting organizers to allow them to start a meeting. However, you can set it up so a PIN isn't required to start a meeting.</span></span>

  
## <a name="set-whether-callers-should-record-their-name"></a><span data-ttu-id="94346-110">Impostare se i chiamanti devono registrare il proprio nome</span><span class="sxs-lookup"><span data-stu-id="94346-110">Set whether callers should record their name</span></span>

<span data-ttu-id="94346-111">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="94346-111">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="94346-112">Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="94346-112">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="94346-113">Nella parte superiore della pagina **Bridge di conferenza** fare clic su Impostazioni **bridge.**</span><span class="sxs-lookup"><span data-stu-id="94346-113">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="94346-114">Abilitare o disabilitare **le notifiche di entrata e uscita dalla riunione**.</span><span class="sxs-lookup"><span data-stu-id="94346-114">Enable or disable **Meeting entry and exit notifications**.</span></span>

4. <span data-ttu-id="94346-115">Se si abilitano le notifiche, scegliere Nomi o numeri di telefono **in** Tipo di annuncio di **entrata/uscita** e quindi attivare Chiedi ai chiamanti di registrare il proprio nome prima di partecipare **a una riunione.**</span><span class="sxs-lookup"><span data-stu-id="94346-115">If enabling notifications, choose **Names or phone numbers** under **Entry/exit announcement type**, and then turn on **Ask callers to record their name before joining a meeting.**</span></span>

6. <span data-ttu-id="94346-116">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="94346-116">Click **Save**.</span></span>
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="94346-117">Per saperne di più sulle Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="94346-117">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="94346-118">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="94346-118">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="94346-119">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare.</span><span class="sxs-lookup"><span data-stu-id="94346-119">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="94346-120">Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="94346-120">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="94346-121">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="94346-121">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="94346-122">[Modi migliori per gestire Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="94346-122">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="94346-123">Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="94346-123">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="94346-124">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="94346-124">Related topics</span></span>

[<span data-ttu-id="94346-125">Provare o acquistare audioconferenze</span><span class="sxs-lookup"><span data-stu-id="94346-125">Try or purchase Audio Conferencing</span></span>](/SkypeForBusiness/audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365)