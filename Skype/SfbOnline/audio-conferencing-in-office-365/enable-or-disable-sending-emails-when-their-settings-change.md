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
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: "Informazioni su come abilitare o disabilitare Skype dall'invio di messaggi di posta elettronica agli utenti quando cambiano le impostazioni, quali ad esempio le modifiche del pin o del numero predefinito della conferenza. "
ms.openlocfilehash: f6596e3e5c52dd82f4f61ad176ae4d656a5f146c
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237322"
---
# <a name="enable-or-disable-sending-emails-when-audio-conferencing-settings-change-in-skype-for-business-online"></a><span data-ttu-id="d5af2-103">Abilitare o disabilitare l'invio di messaggi di posta elettronica quando vengono modificate le impostazioni di Audioconferenza in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="d5af2-103">Enable or disable sending emails when Audio Conferencing settings change in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="d5af2-104">Se si desidera abilitare o disabilitare l'invio di messaggi di posta elettronica in Microsoft Teams, consulta [Abilitare o disabilitare l'invio di messaggi di posta elettronica quando vengono modificate le impostazioni di Audioconferenza in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span><span class="sxs-lookup"><span data-stu-id="d5af2-104">If you want to enable or disable sending emails in Microsoft Teams, see [Enable or disable sending emails when Audio Conferencing settings change in Microsoft Teams](/MicrosoftTeams/enable-or-disable-sending-emails-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="d5af2-105">Gli utenti vengono informati automaticamente tramite posta elettronica quando sono abilitati per l'Audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="d5af2-105">Users are automatically notified by email when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="d5af2-106">A volte, tuttavia, si vuole ridurre il numero di messaggi di posta elettronica inviati Skype for Business utenti.</span><span class="sxs-lookup"><span data-stu-id="d5af2-106">There may be times, however, when you want to reduce the number of emails that are sent to Skype for Business users.</span></span> <span data-ttu-id="d5af2-107">In tal caso, puoi disabilitare l'invio dei messaggi posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="d5af2-107">In such cases, you can disable sending email.</span></span>
  
<span data-ttu-id="d5af2-108">Se si disabilita l'invio di messaggi di posta elettronica, i messaggi di posta elettronica per i servizi di audioconferenza non verranno inviati agli utenti, inclusi i messaggi di posta elettronica per i quali gli utenti sono abilitati o disabilitati per le audioconferenze, quando il PIN viene reimpostato e quando cambia l'ID conferenza e il numero di telefono di conferenza predefinito.</span><span class="sxs-lookup"><span data-stu-id="d5af2-108">If you disable sending emails, Audio Conferencing emails won't be sent to your users, including emails for when users are enabled or disabled for audio conferencing, when their PIN is reset, and when the conference ID and the default conferencing phone number changes.</span></span>
  
<span data-ttu-id="d5af2-109">Ecco un esempio del messaggio di posta elettronica inviato agli utenti quando sono abilitati per le audioconferenze:</span><span class="sxs-lookup"><span data-stu-id="d5af2-109">Here is an example of the email that is sent to users when they are enabled for Audio Conferencing:</span></span>
  
![Posta elettronica per Audioconferenza](../images/audio-conferencing-user-enabled.png)
  
## <a name="when-are-emails-being-sent-to-your-users"></a><span data-ttu-id="d5af2-111">I messaggi di posta elettronica quando vengono inviati agli utenti?</span><span class="sxs-lookup"><span data-stu-id="d5af2-111">When are emails being sent to your users?</span></span>

- <span data-ttu-id="d5af2-112">Sono disponibili diversi messaggi di posta elettronica inviati agli utenti dell'organizzazione dopo che sono stati abilitati per le audioconferenze:</span><span class="sxs-lookup"><span data-stu-id="d5af2-112">There are several emails that are sent to users in your organization after they are enabled for audio conferencing:</span></span>
    
  - <span data-ttu-id="d5af2-113">Quando una licenza di **Audioconferenza** viene loro assegnata.</span><span class="sxs-lookup"><span data-stu-id="d5af2-113">When an **Audio Conferencing** license is assigned to them.</span></span>
    
  - <span data-ttu-id="d5af2-114">Quando si reimposta manualmente il PIN di audioconferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d5af2-114">When you manually reset the user's audio conferencing PIN.</span></span>
    
  - <span data-ttu-id="d5af2-115">Quando reimposti manualmente l'ID conferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d5af2-115">When you manually reset the user's conference ID.</span></span>
    
  - <span data-ttu-id="d5af2-116">Quando la licenza di **Audioconferenza** viene loro rimossa.</span><span class="sxs-lookup"><span data-stu-id="d5af2-116">When the **Audio Conferencing** license is removed from them.</span></span>
    
  - <span data-ttu-id="d5af2-117">Quando il provider di servizi di audioconferenza di un utente viene modificato da Microsoft a un altro provider o **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="d5af2-117">When the audio conferencing provider of a user is changed from Microsoft to another provider or **None**.</span></span>
    
  - <span data-ttu-id="d5af2-118">Quando il provider di servizi di audioconferenza di un utente viene modificato in Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d5af2-118">When the audio conferencing provider of a user is changed to Microsoft.</span></span>


## <a name="enable-or-disable-email-from-being-sent-to-users"></a><span data-ttu-id="d5af2-119">Abilitare o disabilitare l'invio di posta elettronica agli utenti</span><span class="sxs-lookup"><span data-stu-id="d5af2-119">Enable or disable email from being sent to users</span></span>

<span data-ttu-id="d5af2-120">È possibile usare l'interfaccia Skype for Business di amministrazione o Windows PowerShell per abilitare o disabilitare la posta elettronica inviata agli utenti.</span><span class="sxs-lookup"><span data-stu-id="d5af2-120">You can use the Skype for Business admin center or Windows PowerShell to enable or disable email sent to users.</span></span>

 
<span data-ttu-id="d5af2-121">![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="d5af2-121">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="d5af2-122">**Nell'Skype for Business di amministrazione fare** clic su Audioconferenza nel riquadro di spostamento **sinistro.**</span><span class="sxs-lookup"><span data-stu-id="d5af2-122">In the **Skype for Business admin center**, in the left navigation, click **Audio conferencing**.</span></span>
    
2. <span data-ttu-id="d5af2-123">Nella pagina **Impostazioni ponte Microsoft**, seleziona o deseleziona **Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di audioconferenza vengono modificate**.</span><span class="sxs-lookup"><span data-stu-id="d5af2-123">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
3. <span data-ttu-id="d5af2-124">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="d5af2-124">Click **Save**.</span></span>
    
    > [!TIP]
    > <span data-ttu-id="d5af2-125">È inoltre possibile inviare un messaggio di posta elettronica a un utente con le impostazioni di Audioconferenza facendo clic su **Audioconferenza** > **Utenti**, selezionando l'utente e facendo clic su **Invia informazioni conferenza tramite posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="d5af2-125">You can also send email to a user with the audio conferencing settings by going to **Audio conferencing** > **Users**, selecting the user, and clicking **Send conference info via email**.</span></span>  <span data-ttu-id="d5af2-126">In questo caso, verrà inviato un messaggio di posta elettronica che include solo l'ID conferenza e il numero di telefono della conferenza, ma non il PIN.</span><span class="sxs-lookup"><span data-stu-id="d5af2-126">If you do this, an email will be sent that only includes conference ID and conference phone number, but not the PIN.</span></span>  <span data-ttu-id="d5af2-127">Per [altre informazioni, vedere Inviare un messaggio di](send-an-email-to-a-user-with-their-dial-in-information.md) posta elettronica a un utente con le informazioni relative ai servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="d5af2-127">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md) for more information.</span></span>
  
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="d5af2-128">**Uso di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="d5af2-128">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="d5af2-129">Esegui il seguente comando per disabilitare l'invio di messaggi di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="d5af2-129">Run the following to disable sending emails:</span></span> 
    
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $false
  ```

    <span data-ttu-id="d5af2-130">Per assistenza su questo cmdlet, vedi [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).</span><span class="sxs-lookup"><span data-stu-id="d5af2-130">For help with this cmdlet, see [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).</span></span>
    
## <a name="what-else-should-you-know"></a><span data-ttu-id="d5af2-131">Informazioni aggiuntive</span><span class="sxs-lookup"><span data-stu-id="d5af2-131">What else should you know?</span></span>

- <span data-ttu-id="d5af2-132">Quando i messaggi di posta elettronica automatici sono disabilitati, è comunque possibile attivare manualmente l'invio di un messaggio di posta elettronica con l'ID conferenza e il numero di telefono usando l'Skype for Business di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="d5af2-132">When automatic emails are disabled, you can still manually trigger sending an email with the conference ID and phone number using the Skype for Business admin center.</span></span> <span data-ttu-id="d5af2-133">Tuttavia, in questo caso, il PIN non verrà incluso.</span><span class="sxs-lookup"><span data-stu-id="d5af2-133">However, if you do this, the PIN won't be included.</span></span> <span data-ttu-id="d5af2-134">Se si vuole reimpostare il PIN di audioconferenza e l'invio di messaggi di posta elettronica è disabilitato, è necessario inviarlo all'utente in un altro modo.</span><span class="sxs-lookup"><span data-stu-id="d5af2-134">If you want to reset the audio conferencing PIN and sending emails is disabled, you will need to send it to the user in another way.</span></span>
    
- <span data-ttu-id="d5af2-135">L'invio dei messaggi di posta elettronica agli utenti può essere disabilitato tramite l'interfaccia di amministrazione di Skype for Business o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d5af2-135">Sending email to your users can be disabled using the Skype for Business admin center or the Windows PowerShell.</span></span>
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="d5af2-136">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="d5af2-136">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="d5af2-137">È possibile utilizzare questi cmdlet per risparmiare tempo o automatizzare questa operazione.</span><span class="sxs-lookup"><span data-stu-id="d5af2-137">You can use these cmdlets to save time or automate this.</span></span>
    
  - [<span data-ttu-id="d5af2-138">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="d5af2-138">Get-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
  - [<span data-ttu-id="d5af2-139">Remove-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="d5af2-139">Remove-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Remove-CsOnlineDialInConferencingTenantSettings)
    
  - [<span data-ttu-id="d5af2-140">Get-CsOnlineDialinConferencingTenantConfiguration</span><span class="sxs-lookup"><span data-stu-id="d5af2-140">Get-CsOnlineDialinConferencingTenantConfiguration</span></span>](/powershell/module/skype/Get-CsOnlineDialinConferencingTenantConfiguration)
    
  - [<span data-ttu-id="d5af2-141">Get-CsOnlineDialInConferencingTenantSettings</span><span class="sxs-lookup"><span data-stu-id="d5af2-141">Get-CsOnlineDialInConferencingTenantSettings</span></span>](/powershell/module/skype/Get-CsOnlineDialInConferencingTenantSettings)
    
- <span data-ttu-id="d5af2-142">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="d5af2-142">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="d5af2-143">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare.</span><span class="sxs-lookup"><span data-stu-id="d5af2-143">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="d5af2-144">Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="d5af2-144">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="d5af2-145">Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d5af2-145">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="d5af2-146">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="d5af2-146">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="d5af2-147">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="d5af2-147">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="d5af2-148">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="d5af2-148">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="d5af2-149">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="d5af2-149">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="d5af2-150">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="d5af2-150">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="d5af2-151">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="d5af2-151">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="d5af2-p106">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="d5af2-p106">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="d5af2-154">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="d5af2-154">Related topics</span></span>

[<span data-ttu-id="d5af2-155">Messaggi di posta elettronica inviati agli utenti quando cambiano le impostazioni di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="d5af2-155">Emails sent to users when their Audio Conferencing settings change</span></span>](emails-sent-to-users-when-their-settings-change.md)

[<span data-ttu-id="d5af2-156">Inviare un messaggio di posta elettronica a un utente con le sue informazioni di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="d5af2-156">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)
