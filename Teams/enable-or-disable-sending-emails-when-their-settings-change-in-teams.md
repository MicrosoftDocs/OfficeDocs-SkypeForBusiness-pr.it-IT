---
title: Opzioni di posta elettronica quando le impostazioni di audioconferenza cambiano
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
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
- seo-marvel-mar2020
description: "Informazioni su come abilitare o disabilitare Skype l'invio di messaggi di posta elettronica agli utenti quando vengono apportate modifiche a impostazioni come il pin o il numero di conferenza predefinito in Microsoft Teams. "
ms.openlocfilehash: 17c2864703eafa2c70709da0381f870abba58ad0
ms.sourcegitcommit: 8c2093f7a048a9a56b36e4a3b4c48ae1206c52f6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/17/2021
ms.locfileid: "53004168"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="464f5-103">Abilitare o disabilitare l'invio di messaggi di posta elettronica quando le impostazioni di audioconferenza cambiano in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="464f5-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="464f5-104">Gli utenti vengono informati automaticamente tramite posta elettronica quando sono abilitati per l'Audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="464f5-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="464f5-105">A volte, tuttavia, può essere necessario ridurre il numero di messaggi di posta elettronica inviati Microsoft Teams utenti.</span><span class="sxs-lookup"><span data-stu-id="464f5-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="464f5-106">In tal caso, puoi disabilitare l'invio dei messaggi posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="464f5-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="464f5-107">Se si disabilita l'invio di messaggi di posta elettronica, i messaggi di posta elettronica per i servizi di audioconferenza non verranno inviati agli utenti, inclusi i messaggi di posta elettronica per i quali gli utenti sono abilitati o disabilitati per le audioconferenze, quando il PIN viene reimpostato e quando cambia l'ID conferenza e il numero di telefono di conferenza predefinito.</span><span class="sxs-lookup"><span data-stu-id="464f5-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="464f5-108">Ecco un esempio del messaggio di posta elettronica inviato agli utenti quando sono abilitati per le audioconferenze:</span><span class="sxs-lookup"><span data-stu-id="464f5-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Esempio di messaggio di posta elettronica per audioconferenze](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="464f5-110">I messaggi di posta elettronica quando vengono inviati agli utenti?</span><span class="sxs-lookup"><span data-stu-id="464f5-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="464f5-111">Sono disponibili diversi messaggi di posta elettronica inviati agli utenti dell'organizzazione dopo che sono stati abilitati per le audioconferenze:</span><span class="sxs-lookup"><span data-stu-id="464f5-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="464f5-112">Quando una licenza di **Audioconferenza** viene loro assegnata.</span><span class="sxs-lookup"><span data-stu-id="464f5-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="464f5-113">Quando si reimposta manualmente il PIN di audioconferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="464f5-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="464f5-114">Quando reimposti manualmente l'ID conferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="464f5-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="464f5-115">Quando la licenza di **Audioconferenza** viene loro rimossa.</span><span class="sxs-lookup"><span data-stu-id="464f5-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="464f5-116">Quando il provider di servizi di audioconferenza di un utente viene modificato da Microsoft a un altro provider o **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="464f5-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="464f5-117">Quando il provider di servizi di audioconferenza di un utente viene modificato in Microsoft.</span><span class="sxs-lookup"><span data-stu-id="464f5-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="464f5-118">Abilitare o disabilitare l'invio di posta elettronica agli utenti</span><span class="sxs-lookup"><span data-stu-id="464f5-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="464f5-119">È possibile usare le Microsoft Teams o Windows PowerShell per abilitare o disabilitare la posta elettronica inviata agli utenti.</span><span class="sxs-lookup"><span data-stu-id="464f5-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="464f5-120">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="464f5-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="464f5-121">Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="464f5-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="464f5-122">Nella parte superiore della pagina **Bridge di conferenza** fare clic su Impostazioni **bridge.**</span><span class="sxs-lookup"><span data-stu-id="464f5-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="464f5-123">Nel riquadro **Impostazioni bridge** abilitare o disabilitare Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di accesso **remoto cambiano.**</span><span class="sxs-lookup"><span data-stu-id="464f5-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="464f5-124">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="464f5-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="464f5-125">**Uso di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="464f5-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="464f5-126">È anche possibile usare il modulo Microsoft Teams PowerShell ed eseguire:</span><span class="sxs-lookup"><span data-stu-id="464f5-126">You can also use the Microsoft Teams PowerShell module and run:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

<span data-ttu-id="464f5-127">È possibile usare [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) per gestire altre impostazioni per l'organizzazione, tra cui la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="464f5-127">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="464f5-128">Per altre [informazioni, Microsoft Teams informazioni di riferimento su PowerShell.](/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="464f5-128">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="464f5-129">Vuoi saperne di più su Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="464f5-129">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="464f5-130">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="464f5-130">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="464f5-131">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare.</span><span class="sxs-lookup"><span data-stu-id="464f5-131">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="464f5-132">Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="464f5-132">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="464f5-133">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="464f5-133">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="464f5-134">[Modi migliori per gestire Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="464f5-134">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
<span data-ttu-id="464f5-135">Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="464f5-135">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="464f5-136">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="464f5-136">Related topics</span></span>

[<span data-ttu-id="464f5-137">Messaggi di posta elettronica inviati agli utenti quando cambiano le impostazioni di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="464f5-137">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="464f5-138">Inviare un messaggio di posta elettronica a un utente con le sue informazioni di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="464f5-138">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
