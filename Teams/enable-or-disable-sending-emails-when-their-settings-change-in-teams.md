---
title: Abilitare o disabilitare l'invio di messaggi di posta elettronica quando le impostazioni di conferenza audio cambiano in Microsoft Teams
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
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Informazioni su come abilitare o disabilitare Skype dall'invio di messaggi di posta elettronica agli utenti in caso di impostazioni come le modifiche ai pin o le modifiche dei numeri di conferenza predefiniti in Microsoft teams. "
ms.openlocfilehash: 906781f79f10500fc8808a579abe9707f0f736ac
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573064"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-microsoft-teams"></a><span data-ttu-id="b07e5-103">Abilitare o disabilitare l'invio di messaggi di posta elettronica quando le impostazioni di conferenza audio cambiano in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b07e5-103">Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams</span></span>

<span data-ttu-id="b07e5-104">Gli utenti vengono informati automaticamente tramite posta elettronica quando sono abilitati per l'Audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="b07e5-104">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="b07e5-105">In alcuni casi, tuttavia, è possibile ridurre il numero di messaggi di posta elettronica inviati agli utenti di Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="b07e5-105">There may be times, however, when you want to reduce the number of emails that are sent to Microsoft Teams users.</span></span> <span data-ttu-id="b07e5-106">In tal caso, puoi disabilitare l'invio dei messaggi posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="b07e5-106">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="b07e5-107">Se si disabilita l'invio di messaggi di posta elettronica, i messaggi di audioconferenza non verranno inviati agli utenti, inclusi i messaggi di posta elettronica per quando gli utenti sono abilitati o disabilitati per i servizi di audioconferenza, quando il PIN viene reimpostato e quando l'ID conferenza e il numero di telefono delle conferenze predefinite cambiano .</span><span class="sxs-lookup"><span data-stu-id="b07e5-107">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="b07e5-108">Ecco un esempio di messaggio di posta elettronica inviato agli utenti quando sono abilitati per i servizi di audioconferenza:</span><span class="sxs-lookup"><span data-stu-id="b07e5-108">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Esempio di messaggio di posta elettronica per i servizi di audioconferenza](media/teams-emails-sent-to-users-when-settings-change-image1.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="b07e5-110">I messaggi di posta elettronica quando vengono inviati agli utenti?</span><span class="sxs-lookup"><span data-stu-id="b07e5-110">When are emails being sent to your users?</span></span>

- <span data-ttu-id="b07e5-111">Ci sono diversi messaggi di posta elettronica inviati agli utenti dell'organizzazione dopo che sono stati abilitati per i servizi di audioconferenza:</span><span class="sxs-lookup"><span data-stu-id="b07e5-111">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="b07e5-112">Quando una licenza di **Audioconferenza** viene loro assegnata.</span><span class="sxs-lookup"><span data-stu-id="b07e5-112">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="b07e5-113">Quando si reimposta manualmente il PIN per i servizi di audioconferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b07e5-113">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="b07e5-114">Quando reimposti manualmente l'ID conferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="b07e5-114">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="b07e5-115">Quando la licenza di **Audioconferenza** viene loro rimossa.</span><span class="sxs-lookup"><span data-stu-id="b07e5-115">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="b07e5-116">Quando il provider di servizi di audioconferenza di un utente viene modificato da Microsoft a un altro provider o **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="b07e5-116">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="b07e5-117">Quando il provider di servizi di audioconferenza di un utente viene modificato in Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b07e5-117">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="b07e5-118">Abilitare o disabilitare l'invio di messaggi di posta elettronica agli utenti</span><span class="sxs-lookup"><span data-stu-id="b07e5-118">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="b07e5-119">Puoi usare Microsoft teams o Windows PowerShell per abilitare o disabilitare l'invio di messaggi di posta elettronica agli utenti.</span><span class="sxs-lookup"><span data-stu-id="b07e5-119">You can use Microsoft Teams or Windows PowerShell to enable or disable email sent to users.</span></span>

<span data-ttu-id="b07e5-120">![Icona che mostra il logo](media/teams-logo-30x30.png) di Microsoft teams **con l'interfaccia di amministrazione di Microsoft teams**</span><span class="sxs-lookup"><span data-stu-id="b07e5-120">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="b07e5-121">Nella barra di spostamento sinistra, vai a**Bridge conferenza** **riunioni** > .</span><span class="sxs-lookup"><span data-stu-id="b07e5-121">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="b07e5-122">Nella parte superiore della pagina **ponti conferenza** fare clic su **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="b07e5-122">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="b07e5-123">Nel riquadro **Impostazioni Bridge** abilitare o disabilitare **Invia automaticamente i messaggi di posta elettronica agli utenti in caso di modifica delle impostazioni di accesso**esterno.</span><span class="sxs-lookup"><span data-stu-id="b07e5-123">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="b07e5-124">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="b07e5-124">Click **Save**.</span></span>

  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="b07e5-125">**Uso di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="b07e5-125">**Using Windows PowerShell**</span></span>
  
<span data-ttu-id="b07e5-126">Per altre informazioni, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) .</span><span class="sxs-lookup"><span data-stu-id="b07e5-126">See the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>

    
## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="b07e5-127">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b07e5-127">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="b07e5-p102">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="b07e5-p102">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="b07e5-131">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="b07e5-131">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="b07e5-132">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b07e5-132">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
<span data-ttu-id="b07e5-133">Per altre informazioni su Windows PowerShell, vedere la pagina di [riferimento di PowerShell per Microsoft teams](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) per altre informazioni.</span><span class="sxs-lookup"><span data-stu-id="b07e5-133">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) for more information.</span></span>
    
  
## <a name="related-topics"></a><span data-ttu-id="b07e5-134">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="b07e5-134">Related topics</span></span>

[<span data-ttu-id="b07e5-135">Messaggi di posta elettronica inviati agli utenti quando cambiano le impostazioni dei servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="b07e5-135">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change-in-teams.md)

[<span data-ttu-id="b07e5-136">Inviare un messaggio di posta elettronica a un utente con le informazioni relative ai servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="b07e5-136">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)


