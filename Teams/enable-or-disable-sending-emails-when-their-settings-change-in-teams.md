---
title: Opzioni di posta elettronica durante la modifica delle impostazioni del audioconferenza
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
description: "Informazioni su come abilitare o disabilitare Skype dall'invio di messaggi di posta elettronica agli utenti in caso di impostazioni come le modifiche ai pin o le modifiche dei numeri di conferenza predefiniti in Microsoft teams. "
ms.openlocfilehash: 36c7e9dce17de1e6f9bbf8b812d62ddd91bc6ffe
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691602"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="fc663-103">Abilitare o disabilitare l'invio di messaggi di posta elettronica quando le impostazioni di conferenza audio cambiano in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="fc663-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="fc663-104">Gli utenti vengono informati automaticamente tramite posta elettronica quando sono abilitati per l'Audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="fc663-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="fc663-105">In alcuni casi, tuttavia, è possibile ridurre il numero di messaggi di posta elettronica inviati agli utenti di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="fc663-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="fc663-106">In tal caso, puoi disabilitare l'invio dei messaggi posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="fc663-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="fc663-107">Se si disabilita l'invio di messaggi di posta elettronica, i messaggi di audioconferenza non verranno inviati agli utenti, inclusi i messaggi di posta elettronica per quando gli utenti sono abilitati o disabilitati per i servizi di audioconferenza, quando il PIN viene reimpostato e quando viene modificato l'ID conferenza e il numero di telefono delle conferenze</span><span class="sxs-lookup"><span data-stu-id="fc663-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="fc663-108">Ecco un esempio di messaggio di posta elettronica inviato agli utenti quando sono abilitati per i servizi di audioconferenza:</span><span class="sxs-lookup"><span data-stu-id="fc663-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Esempio di messaggio di posta elettronica per i servizi di audioconferenza](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="fc663-110">I messaggi di posta elettronica quando vengono inviati agli utenti?</span><span class="sxs-lookup"><span data-stu-id="fc663-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="fc663-111">Ci sono diversi messaggi di posta elettronica inviati agli utenti dell'organizzazione dopo che sono stati abilitati per i servizi di audioconferenza:</span><span class="sxs-lookup"><span data-stu-id="fc663-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="fc663-112">Quando una licenza di **Audioconferenza** viene loro assegnata.</span><span class="sxs-lookup"><span data-stu-id="fc663-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="fc663-113">Quando si reimposta manualmente il PIN per i servizi di audioconferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fc663-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="fc663-114">Quando reimposti manualmente l'ID conferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="fc663-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="fc663-115">Quando la licenza di **Audioconferenza** viene loro rimossa.</span><span class="sxs-lookup"><span data-stu-id="fc663-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="fc663-116">Quando il provider di servizi di audioconferenza di un utente viene modificato da Microsoft a un altro provider o **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="fc663-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="fc663-117">Quando il provider di servizi di audioconferenza di un utente viene modificato in Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fc663-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="fc663-118">Abilitare o disabilitare l'invio di messaggi di posta elettronica agli utenti</span><span class="sxs-lookup"><span data-stu-id="fc663-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="fc663-119">Puoi usare Microsoft teams o Windows PowerShell per abilitare o disabilitare l'invio di messaggi di posta elettronica agli utenti.</span><span class="sxs-lookup"><span data-stu-id="fc663-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="fc663-120">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Usare l'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="fc663-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="fc663-121">Nella barra di spostamento sinistra, Vai **Meetings**a  >  **Bridge conferenza**riunioni.</span><span class="sxs-lookup"><span data-stu-id="fc663-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="fc663-122">Nella parte superiore della pagina **ponti conferenza** fare clic su **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="fc663-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="fc663-123">Nel riquadro **Impostazioni Bridge** abilitare o disabilitare **Invia automaticamente i messaggi di posta elettronica agli utenti in caso di modifica delle impostazioni di accesso**esterno.</span><span class="sxs-lookup"><span data-stu-id="fc663-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="fc663-124">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="fc663-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="fc663-125">**Uso di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="fc663-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="fc663-126">Per altre informazioni, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .</span><span class="sxs-lookup"><span data-stu-id="fc663-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="fc663-127">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc663-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="fc663-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span><span class="sxs-lookup"><span data-stu-id="fc663-128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="fc663-129">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 usando un unico punto di amministrazione che consente di semplificare il lavoro quotidiano quando si hanno più attività da eseguire.</span><span class="sxs-lookup"><span data-stu-id="fc663-129">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="fc663-130">Per iniziare a usare Windows PowerShell, vedere i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="fc663-130">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="fc663-131">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="fc663-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="fc663-132">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="fc663-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="fc663-133">Per altre informazioni su Windows PowerShell, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="fc663-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="fc663-134">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="fc663-134">Related topics</span></span>

[<span data-ttu-id="fc663-135">Messaggi di posta elettronica inviati agli utenti quando cambiano le impostazioni dei servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="fc663-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="fc663-136">Inviare un messaggio di posta elettronica a un utente con le sue informazioni di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="fc663-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


