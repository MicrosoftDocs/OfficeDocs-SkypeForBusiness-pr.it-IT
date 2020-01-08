---
title: Inviare un messaggio di posta elettronica a un utente con Audioconferenza in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 7440d3e2-1b49-4258-bd2c-79e9072f8c8d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Inviare agli utenti un messaggio di posta elettronica con le loro informazioni di audioconferenza su Skype for Business online.
ms.openlocfilehash: 08e1f67f042d9497854f6d96643ff41e9bf528ed
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "40962574"
---
# <a name="send-an-email-to-a-user-with-their-audio-conferencing-information-in-skype-for-business-online"></a><span data-ttu-id="e1cbe-103">Inviare un messaggio di posta elettronica a un utente con le informazioni relative ai servizi di audioconferenza in Skype for business online</span><span class="sxs-lookup"><span data-stu-id="e1cbe-103">Send an email to a user with their Audio Conferencing information in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="e1cbe-104">Per informazioni sull'invio di informazioni di Audioconferenza agli utenti su Microsoft Teams, consulta [Inviare un messaggio di posta elettronica a un utente con le informazioni di Audioconferenza su Microsoft Teams](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams).</span><span class="sxs-lookup"><span data-stu-id="e1cbe-104">For information about sending Audio Conferencing information to users in Microsoft Teams, see [Send an email to a user with their Audio Conferencing information in Microsoft Teasms](/MicrosoftTeams/send-an-email-to-a-user-with-their-dial-in-information-in-teams).</span></span>

<span data-ttu-id="e1cbe-p101">Sometimes Skype for Business users may need you to send them their Audio Conferencing information. You can do this by using the **Skype for Business admin center** and clicking **Send conference info via email** under the properties for a user. When you send this email, it will contain all of the audio conferencing information, including:</span><span class="sxs-lookup"><span data-stu-id="e1cbe-p101">Sometimes Skype for Business users may need you to send them their Audio Conferencing information. You can do this by using the **Skype for Business admin center** and clicking **Send conference info via email** under the properties for a user. When you send this email, it will contain all of the audio conferencing information, including:</span></span>
  
- <span data-ttu-id="e1cbe-108">Il numero di telefono per le conferenze o per l'accesso esterno dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e1cbe-108">The conference phone or dial-in phone number for the user.</span></span>
    
- <span data-ttu-id="e1cbe-109">L'ID conferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e1cbe-109">The user's conference ID.</span></span>
    
   
<span data-ttu-id="e1cbe-110">Ecco un esempio di messaggio di posta elettronica inviato:</span><span class="sxs-lookup"><span data-stu-id="e1cbe-110">Here is an example of the email that is sent:</span></span>
  
![Posta elettronica di conferenza telefonica con accesso esterno](../images/audio-conferencing-info.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="e1cbe-112">Inviare un messaggio di posta elettronica con informazioni di audioconferenza a un utente</span><span class="sxs-lookup"><span data-stu-id="e1cbe-112">Send an email with audio conferencing information to a user</span></span>

1. <span data-ttu-id="e1cbe-113">Nella barra di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente nell'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="e1cbe-113">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="e1cbe-114">Nella parte superiore della pagina, fai clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="e1cbe-114">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="e1cbe-115">Su **Audioconferenza**, fai clic su **Invia informazioni sulla conferenza nel messaggio di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="e1cbe-115">Under **Audio Conferencing**, click **Send conference info in email**.</span></span>

1. <span data-ttu-id="e1cbe-116">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="e1cbe-116">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="e1cbe-117">Accedere all'interfaccia di amministrazione > **Skype for business**e, nella barra di spostamento sinistra, fare clic su **audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="e1cbe-117">Go to the admin center > **Skype for Business**, and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="e1cbe-118">Fare clic su **utenti**e quindi selezionare l'utente.</span><span class="sxs-lookup"><span data-stu-id="e1cbe-118">Click **Users**, and then select the user.</span></span>
    
4. <span data-ttu-id="e1cbe-119">In the Action pane, click **Send conference info via email**.</span><span class="sxs-lookup"><span data-stu-id="e1cbe-119">In the Action pane, click **Send conference info via email**.</span></span>
    
> [!TIP]
> <span data-ttu-id="e1cbe-120">È anche possibile inviare messaggi di posta elettronica all'utente con le impostazioni di audioconferenza modificando le proprietà dell'utente e quindi facendo clic su servizi di **audioconferenza** > **Invia informazioni sulla conferenza tramite posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="e1cbe-120">You can also send email to the user with the audio conferencing settings by editing the user's properties and then clicking **Audio conferencing** > **Send conference info via email**.</span></span> 

## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="e1cbe-121">Cos'altro occorre sapere su questo messaggio di posta elettronica?</span><span class="sxs-lookup"><span data-stu-id="e1cbe-121">What else should you know about this email?</span></span>

- <span data-ttu-id="e1cbe-122">Ci sono diversi messaggi di posta elettronica inviati agli utenti dell'organizzazione dopo che sono stati abilitati per i servizi di audioconferenza:</span><span class="sxs-lookup"><span data-stu-id="e1cbe-122">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="e1cbe-123">Quando una licenza di **Audioconferenza** viene loro assegnata.</span><span class="sxs-lookup"><span data-stu-id="e1cbe-123">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="e1cbe-124">Quando si reimposta manualmente il PIN per i servizi di audioconferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e1cbe-124">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="e1cbe-125">Quando reimposti manualmente l'ID conferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="e1cbe-125">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="e1cbe-126">Quando una licenza di **Audioconferenza** è rimossa a loro.</span><span class="sxs-lookup"><span data-stu-id="e1cbe-126">When an **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="e1cbe-127">Quando il provider di servizi di audioconferenza per un utente viene modificato da Microsoft a un altro provider o **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="e1cbe-127">When the audio conferencing provider for a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="e1cbe-128">Quando il provider di servizi di audioconferenza per un utente viene modificato in Microsoft.</span><span class="sxs-lookup"><span data-stu-id="e1cbe-128">When the audio conferencing provider for a user is changed to Microsoft.</span></span>
    
- <span data-ttu-id="e1cbe-p102">By default, the sender of the emails will be from Office 365, but you can change the email address and display name by using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) cmdlet. To make changes to the email address that is sending the email to users, you must:</span><span class="sxs-lookup"><span data-stu-id="e1cbe-p102">By default, the sender of the emails will be from Office 365, but you can change the email address and display name by using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=708983) cmdlet. To make changes to the email address that is sending the email to users, you must:</span></span>
    
  - <span data-ttu-id="e1cbe-131">Immettere l'indirizzo di posta elettronica nel parametro SendEmailFromAddress.</span><span class="sxs-lookup"><span data-stu-id="e1cbe-131">Enter the email address in the SendEmailFromAddress parameter.</span></span>
    
  - <span data-ttu-id="e1cbe-132">Imposta il parametro SendEmailOverride su True.</span><span class="sxs-lookup"><span data-stu-id="e1cbe-132">Set the SendEmailOverride parameter to True.</span></span>
    
  - <span data-ttu-id="e1cbe-133">Immettere il nome visualizzato del messaggio di posta elettronica nel parametro SendEmailFromDisplayName.</span><span class="sxs-lookup"><span data-stu-id="e1cbe-133">Enter the email display name in the SendEmailFromDisplayName parameter.</span></span>
    
     `Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"`
    
    > [!NOTE]
    > <span data-ttu-id="e1cbe-134">Se desideri modificare le informazioni relative all'indirizzo di posta elettronica, devi verificare che i criteri di posta elettronica in ingresso dell'organizzazione consentano i messaggi in arrivo dall'indirizzo di posta elettronica personalizzato.</span><span class="sxs-lookup"><span data-stu-id="e1cbe-134">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address that is set.</span></span> 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="e1cbe-135">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="e1cbe-135">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="e1cbe-136">Per renderle automatiche o per risparmiare tempo, puoi utilizzare il cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ).</span><span class="sxs-lookup"><span data-stu-id="e1cbe-136">To save time or automate this, you can use the [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) cmdlet.</span></span>
    
    <span data-ttu-id="e1cbe-137">Per inviare un messaggio di posta elettronica all'utente con le informazioni relative ai servizi di audioconferenza, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1cbe-137">To send an email to the user with their audio conferencing information, run the following:</span></span>
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUser -id amos.marble@contoso.com  -SendEmail
  ```

- <span data-ttu-id="e1cbe-p103">Per quanto riguarda Windows PowerShell, è possibile gestire gli utenti di Skype for Business online e le azioni che sono autorizzati a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="e1cbe-p103">When it comes to Windows PowerShell, Skype for Business Online is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="e1cbe-141">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="e1cbe-141">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="e1cbe-142">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e1cbe-142">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="e1cbe-p104">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo con l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente. Per informazioni su questi vantaggi, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1cbe-p104">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="e1cbe-145">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e1cbe-145">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
    [<span data-ttu-id="e1cbe-146">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e1cbe-146">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="e1cbe-147">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="e1cbe-147">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="e1cbe-p105">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="e1cbe-p105">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="e1cbe-150">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="e1cbe-150">Related topics</span></span>

[<span data-ttu-id="e1cbe-151">Provare o acquistare le audioconferenze in Office 365</span><span class="sxs-lookup"><span data-stu-id="e1cbe-151">Try or purchase Audio Conferencing in Office 365</span></span>](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
