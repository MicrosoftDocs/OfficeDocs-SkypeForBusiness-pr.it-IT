---
title: Abilitare o disabilitare l'invio di messaggi di posta elettronica quando vengono modificate le impostazioni di Audioconferenza in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 26ea19d3-e420-4fc1-baa3-2692d17e5e1d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Informazioni su come abilitare o disabilitare Skype dall'invio di messaggi di posta elettronica agli utenti quando cambiano le impostazioni, quali ad esempio le modifiche del pin o del numero predefinito della conferenza. "
ms.openlocfilehash: 7c9c768dfc8bb01bdcbc8e9f20bec1bd980b1e0d
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/07/2018
ms.locfileid: "23864316"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="8fb74-103">Abilitare o disabilitare l'invio di messaggi di posta elettronica quando vengono modificate le impostazioni di Audioconferenza in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="8fb74-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="8fb74-104">Se si desidera abilitare o disabilitare l'invio di messaggi di posta elettronica in Microsoft Teams, consulta [Abilitare o disabilitare l'invio di messaggi di posta elettronica quando vengono modificate le impostazioni di Audioconferenza in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span><span class="sxs-lookup"><span data-stu-id="8fb74-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="8fb74-105">Gli utenti vengono informati automaticamente tramite posta elettronica quando sono abilitati per l'Audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="8fb74-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="8fb74-106">Tuttavia, talora può capitare di voler ridurre il numero di messaggi di posta elettronica inviati agli utenti di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="8fb74-106">There may be times though when you want to reduce the number of emails that are sent to users, and in that case you can disable this.</span></span> <span data-ttu-id="8fb74-107">In tal caso, puoi disabilitare l'invio dei messaggi posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="8fb74-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="8fb74-108">Se disabiliti l'invio dei messaggi di posta elettronica, agli utenti non verrà inviato alcun messaggio di Audioconferenza, tra cui i messaggi inviati quando gli utenti vengono abilitati o disabilitati per l'Audioconferenza, quando il PIN viene reimpostato e quando l'ID conferenza e il numero di telefono per le conferenze predefinito vengono modificati.</span><span class="sxs-lookup"><span data-stu-id="8fb74-108">If you disable sending emails, all dial-in conferencing emails won't be sent to your users including emails for when users are enabled or disabled for dial-in conferencing, when their PIN is reset, when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="8fb74-109">Di seguito è riportato un esempio di messaggio di posta elettronica inviato agli utenti quando vengono abilitati per l'Audioconferenza:</span><span class="sxs-lookup"><span data-stu-id="8fb74-109">Here is an example of the email that is sent to users that are enabled for dial-in conferencing:</span></span>
  
![Posta elettronica per Audioconferenza](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="8fb74-111">I messaggi di posta elettronica quando vengono inviati agli utenti?</span><span class="sxs-lookup"><span data-stu-id="8fb74-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="8fb74-112">Esistono diversi messaggi di posta elettronica inviati a utenti dell'organizzazione dopo che essi vengono abilitati per l'Audioconferenza:</span><span class="sxs-lookup"><span data-stu-id="8fb74-112">There are several emails that are sent to users in your organization after they are enabled for dial-in conferencing:</span></span>
    
  - <span data-ttu-id="8fb74-113">Quando una licenza di **Audioconferenza** viene assegnata a loro.</span><span class="sxs-lookup"><span data-stu-id="8fb74-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="8fb74-114">Quando reimposti manualmente il PIN di Audioconferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8fb74-114">When you manually reset the user's dial-in conferencing PIN.</span></span>
    
  - <span data-ttu-id="8fb74-115">Quando reimposti manualmente l'ID conferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="8fb74-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="8fb74-116">Quando la licenza di **Audioconferenza** viene loro rimossa.</span><span class="sxs-lookup"><span data-stu-id="8fb74-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="8fb74-117">Quando il provider di servizi di audioconferenza di un utente passa da Microsoft a un altro provider o viene impostato su **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="8fb74-117">When the dial-in conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="8fb74-118">Quando il provider di servizi di audioconferenza di un utente diventa Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8fb74-118">When the dial-in conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="8fb74-119">Abilitare o disabilitare l'invio di messaggi di posta elettronica agli utenti</span><span class="sxs-lookup"><span data-stu-id="8fb74-119">Enable or disable email from being sent to dial-in users</span></span>

<span data-ttu-id="8fb74-120">Puoi usare l'interfaccia di amministrazione di Skype for Business o Windows PowerShell per abilitare o disabilitare l'invio di messaggi di posta elettronica agli utenti.</span><span class="sxs-lookup"><span data-stu-id="8fb74-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email from being sent to users.</span></span>

 
<span data-ttu-id="8fb74-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Tramite l'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="8fb74-121">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="8fb74-122">Nell'**interfaccia di amministrazione di Skype for Business**, nel menu di navigazione a sinistra, vai su **Audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="8fb74-122">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**Microsoft bridge settings.</span></span>
    
2. <span data-ttu-id="8fb74-123">Nella pagina **Impostazioni ponte Microsoft**, seleziona o deseleziona **Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di audioconferenza vengono modificate**.</span><span class="sxs-lookup"><span data-stu-id="8fb74-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="8fb74-124">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="8fb74-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="8fb74-125">È inoltre possibile inviare un messaggio di posta elettronica a un utente con le impostazioni di Audioconferenza facendo clic su **Audioconferenza** > **Utenti**, selezionando l'utente e facendo clic su **Invia informazioni conferenza tramite posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="8fb74-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="8fb74-126">Facendo ciò, verrà inviato un messaggio di posta elettronica contenente solo il numero di telefono e l'ID conferenza, ma il PIN non verrà incluso.</span><span class="sxs-lookup"><span data-stu-id="8fb74-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>  <span data-ttu-id="8fb74-127">Per maggiori informazioni, consulta [Inviare un messaggio di posta elettronica a un utente con le informazioni di Audioconferenza](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="8fb74-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="8fb74-128">**Tramite Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="8fb74-128">**Using Windows PowerShell to manage Lync Online**</span></span>
  
- <span data-ttu-id="8fb74-129">Esegui il seguente comando per disabilitare l'invio di messaggi di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="8fb74-129">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="8fb74-130">Per assistenza su questo cmdlet, vedi [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="8fb74-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="8fb74-131">Quali altre informazioni ti servono?</span><span class="sxs-lookup"><span data-stu-id="8fb74-131">What else should you know?</span></span>

- <span data-ttu-id="8fb74-132">Quando i messaggi automatici sono disabilitati, puoi comunque attivare manualmente l'invio di un messaggio di posta elettronica con l'ID conferenza e il numero di telefono tramite l'interfaccia di amministrazione di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="8fb74-132">When automatic emails are disabled, you can still can manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="8fb74-133">Tuttavia, se scegli questa opzione il PIN non sarà incluso.</span><span class="sxs-lookup"><span data-stu-id="8fb74-133">However, if you do this the PIN won't be included.</span></span> <span data-ttu-id="8fb74-134">Se desideri reimpostare il PIN di Audioconferenza e l'invio dei messaggi di posta elettronica è disabilitato, dovrai optare per un'altra modalità di invio all'utente.</span><span class="sxs-lookup"><span data-stu-id="8fb74-134">If you want to reset the dial-in conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="8fb74-135">L'invio dei messaggi di posta elettronica agli utenti può essere disabilitato tramite l'interfaccia di amministrazione di Skype for Business o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8fb74-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="8fb74-136">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="8fb74-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="8fb74-137">È possibile utilizzare questi cmdlet per risparmiare tempo o automatizzare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="8fb74-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="8fb74-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="8fb74-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="8fb74-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="8fb74-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="8fb74-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="8fb74-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="8fb74-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="8fb74-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
-  <span data-ttu-id="8fb74-p104">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="8fb74-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="8fb74-145">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="8fb74-145">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="8fb74-146">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8fb74-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="8fb74-p105">Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="8fb74-p105">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="8fb74-149">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8fb74-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="8fb74-150">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8fb74-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="8fb74-151">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="8fb74-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="8fb74-p106">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="8fb74-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8fb74-154">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8fb74-154">Related topics</span></span>

[<span data-ttu-id="8fb74-155">Messaggi di posta elettronica inviati agli utenti in caso di modifica delle impostazioni di Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="8fb74-155">Emails sent to users when their settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

<span data-ttu-id="8fb74-156">[Inviare un messaggio di posta elettronica a un utente con le sue informazioni sull'audioconferenza](send-an-email-to-a-user-with-their-dial-in-information.md)</span><span class="sxs-lookup"><span data-stu-id="8fb74-156">[](send-an-email-to-a-user-with-their-dial-in-information.md)Send an email to a user with their Audio Conferencing information</span></span>


