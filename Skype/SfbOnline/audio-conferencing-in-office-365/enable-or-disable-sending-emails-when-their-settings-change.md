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
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: "Informazioni su come abilitare o disabilitare Skype dall'invio di messaggi di posta elettronica agli utenti quando cambiano le impostazioni, quali ad esempio le modifiche del pin o del numero predefinito della conferenza. "
ms.openlocfilehash: 28da70d829972a7b9d3659290652c2482d409364
ms.sourcegitcommit: 4c041e8a7c39bd6517605ed7fc9aab18cf466596
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/18/2019
ms.locfileid: "35792329"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="f1133-103">Abilitare o disabilitare l'invio di messaggi di posta elettronica quando vengono modificate le impostazioni di Audioconferenza in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="f1133-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

> [!Note]
> <span data-ttu-id="f1133-104">Se si desidera abilitare o disabilitare l'invio di messaggi di posta elettronica in Microsoft Teams, consulta [Abilitare o disabilitare l'invio di messaggi di posta elettronica quando vengono modificate le impostazioni di Audioconferenza in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span><span class="sxs-lookup"><span data-stu-id="f1133-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="f1133-p101">Users are automatically notified by email when they are enabled for Audio Conferencing. There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users. In such cases, you can disable sending email.</span><span class="sxs-lookup"><span data-stu-id="f1133-p101">Users are automatically notified by email when they are enabled for Audio Conferencing. There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users. In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="f1133-108">Se si disabilita l'invio di messaggi di posta elettronica, i messaggi di audioconferenza non verranno inviati agli utenti, inclusi i messaggi di posta elettronica per quando gli utenti sono abilitati o disabilitati per i servizi di audioconferenza, quando il PIN viene reimpostato e quando l'ID conferenza e il numero di telefono delle conferenze predefinite cambiano .</span><span class="sxs-lookup"><span data-stu-id="f1133-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="f1133-109">Ecco un esempio di messaggio di posta elettronica inviato agli utenti quando sono abilitati per i servizi di audioconferenza:</span><span class="sxs-lookup"><span data-stu-id="f1133-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Posta elettronica per Audioconferenza](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="f1133-111">I messaggi di posta elettronica quando vengono inviati agli utenti?</span><span class="sxs-lookup"><span data-stu-id="f1133-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="f1133-112">Ci sono diversi messaggi di posta elettronica inviati agli utenti dell'organizzazione dopo che sono stati abilitati per i servizi di audioconferenza:</span><span class="sxs-lookup"><span data-stu-id="f1133-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="f1133-113">Quando una licenza di **Audioconferenza** viene assegnata a loro.</span><span class="sxs-lookup"><span data-stu-id="f1133-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="f1133-114">Quando si reimposta manualmente il PIN per i servizi di audioconferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f1133-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="f1133-115">Quando reimposti manualmente l'ID conferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="f1133-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="f1133-116">Quando la licenza di **Audioconferenza** viene loro rimossa.</span><span class="sxs-lookup"><span data-stu-id="f1133-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="f1133-117">Quando il provider di servizi di audioconferenza di un utente viene modificato da Microsoft a un altro provider o **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="f1133-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="f1133-118">Quando il provider di servizi di audioconferenza di un utente viene modificato in Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f1133-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="f1133-119">Abilitare o disabilitare l'invio di messaggi di posta elettronica agli utenti</span><span class="sxs-lookup"><span data-stu-id="f1133-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="f1133-120">Puoi usare l'interfaccia di amministrazione di Skype for business o Windows PowerShell per abilitare o disabilitare l'invio di messaggi di posta elettronica agli utenti.</span><span class="sxs-lookup"><span data-stu-id="f1133-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="f1133-121">![Icona che mostra il logo](../images/sfb-logo-30x30.png) di Skype for business **con l'interfaccia di amministrazione di Skype for business**</span><span class="sxs-lookup"><span data-stu-id="f1133-121">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="f1133-122">Nell'interfaccia di **amministrazione di Skype for business**, nella barra di spostamento sinistra, fare clic su **audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="f1133-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="f1133-123">Nella pagina **Impostazioni ponte Microsoft**, seleziona o deseleziona **Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di audioconferenza vengono modificate**.</span><span class="sxs-lookup"><span data-stu-id="f1133-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="f1133-124">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="f1133-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="f1133-p102">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.  If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.  See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span><span class="sxs-lookup"><span data-stu-id="f1133-p102">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.  If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.  See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="f1133-128">**Uso di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="f1133-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="f1133-129">Esegui il seguente comando per disabilitare l'invio di messaggi di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="f1133-129">Run the following to disable sending emails:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="f1133-130">Per assistenza su questo cmdlet, vedi [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span><span class="sxs-lookup"><span data-stu-id="f1133-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="f1133-131">Quali altre informazioni devi conoscere?</span><span class="sxs-lookup"><span data-stu-id="f1133-131">What else should you know?</span></span>

- <span data-ttu-id="f1133-p103">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center. However, if you do this, the PIN won't be included. If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span><span class="sxs-lookup"><span data-stu-id="f1133-p103">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center. However, if you do this, the PIN won't be included. If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="f1133-135">L'invio dei messaggi di posta elettronica agli utenti può essere disabilitato tramite l'interfaccia di amministrazione di Skype for Business o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f1133-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="f1133-136">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="f1133-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="f1133-137">È possibile utilizzare questi cmdlet per risparmiare tempo o automatizzare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="f1133-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="f1133-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="f1133-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
  - [<span data-ttu-id="f1133-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="f1133-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715759)
    
  - [<span data-ttu-id="f1133-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="f1133-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](https://go.microsoft.com/fwlink/?LinkId=715758)
    
  - [<span data-ttu-id="f1133-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="f1133-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](https://go.microsoft.com/fwlink/?LinkId=715760)
    
- <span data-ttu-id="f1133-p104">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="f1133-p104">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="f1133-145">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="f1133-145">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="f1133-146">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="f1133-146">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="f1133-147">Windows PowerShell offre numerosi vantaggi in termini di velocità, semplicità e produttività solo con l'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche all'impostazione per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="f1133-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="f1133-148">Learn about these advantages in the following topics:</span><span class="sxs-lookup"><span data-stu-id="f1133-148">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="f1133-149">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f1133-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="f1133-150">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f1133-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="f1133-151">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="f1133-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > <span data-ttu-id="f1133-p106">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="f1133-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="f1133-154">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="f1133-154">Related topics</span></span>

[<span data-ttu-id="f1133-155">Messaggi di posta elettronica inviati agli utenti quando cambiano le impostazioni dei servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="f1133-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="f1133-156">Inviare un messaggio di posta elettronica a un utente con le informazioni relative ai servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="f1133-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)


