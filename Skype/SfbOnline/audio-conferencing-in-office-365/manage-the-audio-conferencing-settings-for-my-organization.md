---
title: Gestire le impostazioni di conferenze Audio per l'organizzazione
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: bc9bd328-c5b2-44e5-af15-e02bf00e1c81
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Vedere Procedura per assegnare un ID conferenza telefonica con licenza e di conferenza per un utente e molte altre impostazioni di conferenza telefonica. '
ms.openlocfilehash: 7a5f82a827049f591d012af7f752e26ac4f9d87b
ms.sourcegitcommit: b93d1a0012aacb164d700db0143683cb6f276bf4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2018
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a><span data-ttu-id="35e90-103">Gestire le impostazioni di conferenze Audio per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="35e90-103">Manage the Audio Conferencing settings for my organization</span></span>

<span data-ttu-id="35e90-104">Potrebbe risultare più semplice per poter visualizzare tutte le impostazioni di audioconferenza per Skype per le aziende e Teams Microsoft in un unico sito.</span><span class="sxs-lookup"><span data-stu-id="35e90-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="35e90-105">Assegnare una licenza di conferenze Audio</span><span class="sxs-lookup"><span data-stu-id="35e90-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="35e90-106">È possibile assegnare licenze utilizzando **Skype per interfaccia di amministrazione di Business**.</span><span class="sxs-lookup"><span data-stu-id="35e90-106">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="35e90-107">È necessario utilizzare l'interfaccia di amministrazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="35e90-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="35e90-108">Vedi [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="35e90-108">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="35e90-109">**Per assegnare una licenza per un utente**</span><span class="sxs-lookup"><span data-stu-id="35e90-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="35e90-110">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="35e90-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="35e90-111">Nel riquadro di spostamento sinistro dell' **interfaccia di amministrazione di Office 365**, passare a **utenti** > **utenti attivi**e quindi selezionare l'utente o gli utenti dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="35e90-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="35e90-112">Per assegnare licenze a un massimo di 20 utenti contemporaneamente, puoi ricorrere all'elenco a discesa **Selezionare una visualizzazione** e scegliere una delle opzioni oppure creare una visualizzazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="35e90-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="35e90-113">Quindi fai clic su **Modifica**, due volte su **Avanti**, seleziona la licenza e fai clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="35e90-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="35e90-114">Puoi anche assegnare licenze a più utenti con Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="35e90-114">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="35e90-115">Per istruzioni ed esempi di script PowerShell, vedere [Assegnare Skype per le licenze aziendali e team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="35e90-115">For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="35e90-116">Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="35e90-116">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="35e90-117">Nella pagina **Licenze per i prodotti** , attivare **Servizi di conferenza Audio** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="35e90-117">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="35e90-118">Per ulteriori informazioni sulle licenze, vedere [Skype di licenza di componente aggiuntivo Business e i team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="35e90-118">For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="35e90-119">Dopo aver assegnato alla licenza, Microsoft potrebbe non viene inizialmente visualizzato nell'elenco come provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="35e90-119">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="35e90-120">In questa eventualità, esegui la disconnessione dall'interfaccia di amministrazione di Office 365 oppure premi CTRL+F5 per aggiornare la finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="35e90-120">If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="35e90-121">Attivare o disattivare i messaggi di posta elettronica inviati agli utenti di audioconferenze con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="35e90-121">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="35e90-122">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="35e90-122">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="35e90-123">Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**.</span><span class="sxs-lookup"><span data-stu-id="35e90-123">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="35e90-124">Nella parte superiore della pagina **Ponti di conferenza** , fare clic su **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="35e90-124">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="35e90-125">Nel riquadro **Impostazioni Bridge** , abilitare o disabilitare **automaticamente inviare messaggi di posta elettronica per gli utenti di modificare le relative impostazioni di connessione**.</span><span class="sxs-lookup"><span data-stu-id="35e90-125">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="35e90-126">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="35e90-126">Click **Save**.</span></span>

<span data-ttu-id="35e90-127">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="35e90-127">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="35e90-128">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="35e90-128">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="35e90-129">Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.</span><span class="sxs-lookup"><span data-stu-id="35e90-129">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="35e90-130">Nella pagina **Impostazioni bridge Microsoft** , selezionare o deselezionare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="35e90-130">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="35e90-131">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="35e90-131">Click **Save**.</span></span>
    
    <span data-ttu-id="35e90-132">È anche possibile inviare messaggi di posta elettronica all'utente con le impostazioni di conferenza audio verranno le proprietà dell'utente per conferenze audio e facendo clic su **Invia informazioni conferenza tramite posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="35e90-132">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="35e90-133">L'ID e imposta come predefinito audioconferenza numero di telefono conferenza è inclusi nell'invito alla riunione, ma non il PIN.</span><span class="sxs-lookup"><span data-stu-id="35e90-133">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="35e90-134">[Uso di Windows PowerShell](send-an-email-to-a-user-with-their-dial-in-information.md)</span><span class="sxs-lookup"><span data-stu-id="35e90-134">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
 <span data-ttu-id="35e90-135">**Utilizzo di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="35e90-135">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="35e90-136">You can also use the Windows PowerShell and run:</span><span class="sxs-lookup"><span data-stu-id="35e90-136">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="35e90-137">È possibile utilizzare [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, inclusa la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="35e90-137">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="35e90-138">Modificare le informazioni di contatto del mittente nei messaggi di posta elettronica inviato agli utenti</span><span class="sxs-lookup"><span data-stu-id="35e90-138">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="35e90-139">È possibile apportare modifiche alla posta elettronica inviato automaticamente agli utenti, tra cui l'indirizzo di posta elettronica e il nome visualizzato di informazioni di contatto del mittente.</span><span class="sxs-lookup"><span data-stu-id="35e90-139">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="35e90-140">Per impostazione predefinita, il mittente dei messaggi di posta elettronica è Office 365, ma è possibile modificare l'indirizzo di posta elettronica e viene visualizzato il nome utilizzando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .</span><span class="sxs-lookup"><span data-stu-id="35e90-140">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="35e90-141">Per apportare modifiche all'indirizzo di posta elettronica che invia messaggio di posta elettronica agli utenti, è necessario:</span><span class="sxs-lookup"><span data-stu-id="35e90-141">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="35e90-142">Immettere l'indirizzo di posta elettronica nel parametro _SendEmailFromAddress_ .</span><span class="sxs-lookup"><span data-stu-id="35e90-142">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="35e90-143">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span><span class="sxs-lookup"><span data-stu-id="35e90-143">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="35e90-144">Il parametro _SendEmailOverride_ impostato su _True_.</span><span class="sxs-lookup"><span data-stu-id="35e90-144">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="35e90-145">Se desideri modificare le informazioni relative all'indirizzo di posta elettronica, devi verificare che i criteri di posta elettronica in ingresso dell'organizzazione consentano i messaggi in arrivo dall'indirizzo di posta elettronica personalizzato.</span><span class="sxs-lookup"><span data-stu-id="35e90-145">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="35e90-146">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span><span class="sxs-lookup"><span data-stu-id="35e90-146">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="35e90-147">È possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, inclusa la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="35e90-147">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="35e90-148">Vedere [messaggi di posta elettronica che vengono inviati automaticamente agli utenti quando modificano le impostazioni di conferenza Audio](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="35e90-148">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="35e90-149">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="35e90-149">Reset the meeting conference ID</span></span>

<span data-ttu-id="35e90-150">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="35e90-150">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="35e90-151">Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="35e90-151">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="35e90-152">Nella parte superiore della pagina, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="35e90-152">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="35e90-153">In **Servizi di conferenza Audio**, fare clic su **Reimposta ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="35e90-153">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

4. <span data-ttu-id="35e90-154">Nella **reimpostare ID conferenza?** finestra, fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="35e90-154">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="35e90-155">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="35e90-155">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="35e90-156">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="35e90-156">It's enabled by default.</span></span>

<span data-ttu-id="35e90-157">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="35e90-157">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="35e90-158">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="35e90-158">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="35e90-159">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="35e90-159">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="35e90-160">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio**e nel riquadro azioni in **ID conferenza**, fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="35e90-160">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="35e90-161">Nella **reimpostare ID conferenza?** finestra, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="35e90-161">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="35e90-162">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="35e90-162">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="35e90-163">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="35e90-163">It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="35e90-164">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="35e90-164">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="35e90-165">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="35e90-165">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="35e90-166">Gli utenti possono utilizzare Skype per strumento di migrazione di riunioni Business per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="35e90-166">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="35e90-167">Per informazioni su come scaricare, installare ed eseguire il Skype per strumento di aggiornamento riunione Business, vedere: [Strumento di aggiornamento di riunione per Skype per le aziende e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype online Business dello strumento di migrazione di riunioni (64 bit)](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype online Business riunione Strumento di migrazione (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="35e90-167">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="35e90-168">Reimpostare il PIN dell'organizzatore della conferenza</span><span class="sxs-lookup"><span data-stu-id="35e90-168">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="35e90-169">Reimpostare il PIN dell'organizzatore della conferenza</span><span class="sxs-lookup"><span data-stu-id="35e90-169">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="35e90-170">Ogni riunione che un utente pianifica verrà viene assegnato un ID conferenza univoco.</span><span class="sxs-lookup"><span data-stu-id="35e90-170">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="35e90-171">Benché un ID conferenza viene automaticamente creato e assegnato a un utente, è possibile quando non da un utente di utilizzare questo e si desidera impostare per un determinato numero o gli utenti non possono ricordare o sono persa loro ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="35e90-171">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="35e90-172">È possibile utilizzare Skype per interfaccia di amministrazione di Business e Windows PowerShell per visualizzare, modificare e ripristinare gli ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="35e90-172">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="35e90-173">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="35e90-173">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="35e90-174">Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="35e90-174">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="35e90-175">Nella parte superiore della pagina, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="35e90-175">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="35e90-176">In **Servizi di conferenza Audio**, fare clic su **Reimposta PIN**e quindi fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="35e90-176">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="35e90-177">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="35e90-177">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="35e90-178">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="35e90-178">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="35e90-179">Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.</span><span class="sxs-lookup"><span data-stu-id="35e90-179">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="35e90-180">Fare clic su **utenti**e quindi selezionare l'utente che si desidera reimpostare il PIN per.</span><span class="sxs-lookup"><span data-stu-id="35e90-180">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="35e90-181">Nel riquadro azioni, in **PIN**, fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="35e90-181">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="35e90-182">Gli utenti riceveranno un messaggio di posta elettronica con il proprio PIN quando questi vengono attivati per conferenze audio o quando viene reimpostato il PIN.</span><span class="sxs-lookup"><span data-stu-id="35e90-182">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="35e90-183">Ma se è stata disabilitata automaticamente l'invio di messaggi di posta elettronica, non verrà inviato un messaggio di posta elettronica Reimpostazione PIN e sarà necessario inviare manualmente il PIN all'utente.</span><span class="sxs-lookup"><span data-stu-id="35e90-183">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="35e90-184">The PIN will only be shown once after it has been reset.</span><span class="sxs-lookup"><span data-stu-id="35e90-184">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="35e90-185">Dopo che viene visualizzata immediatamente dopo la reimpostazione, il PIN non verrà visualizzato più nella proprietà utente. in realtà, \* \* \* verranno visualizzati.</span><span class="sxs-lookup"><span data-stu-id="35e90-185">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="35e90-186">Vedere [reimpostare il PIN per conferenze Audio](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="35e90-186">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="35e90-187">Inviare un messaggio di posta elettronica con informazioni di audioconferenza a un utente</span><span class="sxs-lookup"><span data-stu-id="35e90-187">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="35e90-188">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="35e90-188">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="35e90-189">Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="35e90-189">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="35e90-190">Nella parte superiore della pagina, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="35e90-190">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="35e90-191">In **Servizi di conferenza Audio**, fare clic su **Invia le informazioni di conferenza nel messaggio di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="35e90-191">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="35e90-192">A tale scopo, conferenze audio PIN non viene inviato all'utente.</span><span class="sxs-lookup"><span data-stu-id="35e90-192">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="35e90-193">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="35e90-193">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="35e90-194">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="35e90-194">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="35e90-195">Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.</span><span class="sxs-lookup"><span data-stu-id="35e90-195">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="35e90-196">Fare clic su **utenti**e quindi selezionare l'utente che si desidera reimpostare il PIN per.</span><span class="sxs-lookup"><span data-stu-id="35e90-196">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="35e90-197">Nel riquadro Azioni fai clic su **Invia informazioni sulla conferenza tramite posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="35e90-197">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="35e90-198">A tale scopo, conferenze audio PIN non viene inviato all'utente.</span><span class="sxs-lookup"><span data-stu-id="35e90-198">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="35e90-199">[Uso di Windows PowerShell](send-an-email-to-a-user-with-their-dial-in-information.md)</span><span class="sxs-lookup"><span data-stu-id="35e90-199">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="35e90-200">L'impostazione del telefono invita numeri incluso nel</span><span class="sxs-lookup"><span data-stu-id="35e90-200">Setting the phone numbers included on invites</span></span>

<span data-ttu-id="35e90-201">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="35e90-201">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="35e90-202">Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="35e90-202">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="35e90-203">Accanto a **Servizi di conferenza Audio**, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="35e90-203">Next to **Audio Conferencing**, click **Edit**.</span></span>
 
3. <span data-ttu-id="35e90-204">Nel riquadro di **Conferenze Audio** , è possibile impostare il **numero a pagamento** e, se abilitato, il **numero verde**.</span><span class="sxs-lookup"><span data-stu-id="35e90-204">In the **Audio Conferencing** pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

4. <span data-ttu-id="35e90-205">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="35e90-205">Click **Save**.</span></span>

<span data-ttu-id="35e90-206">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="35e90-206">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  
  
1. <span data-ttu-id="35e90-207">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="35e90-207">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="35e90-208">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="35e90-208">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="35e90-209">Nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="35e90-209">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="35e90-210">Selezionare l'utente che si desidera abilitare per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="35e90-210">Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="35e90-211">Nel riquadro azioni, è possibile impostare il **numero a pagamento** e, se abilitato, il **numero verde**.</span><span class="sxs-lookup"><span data-stu-id="35e90-211">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="35e90-212">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="35e90-212">Click **Save**.</span></span>
    
<span data-ttu-id="35e90-213">Vedere [impostare telefono numeri incluso nel invita](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="35e90-213">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
  
## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="35e90-214">La scelta delle impostazioni di ponte conferenza</span><span class="sxs-lookup"><span data-stu-id="35e90-214">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="35e90-215">**Impostare l'esperienza di riunione quando i chiamanti di partecipare a una riunione**</span><span class="sxs-lookup"><span data-stu-id="35e90-215">**Set the meeting experience when callers join a meeting**</span></span>

 <span data-ttu-id="35e90-216">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="35e90-216">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="35e90-217">Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**.</span><span class="sxs-lookup"><span data-stu-id="35e90-217">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="35e90-218">Nella parte superiore della pagina **Ponti di conferenza** , fare clic su **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="35e90-218">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="35e90-219">Nel riquadro **Impostazioni Bridge** , abilitare o disabilitare **voce della riunione e chiudere le notifiche**.</span><span class="sxs-lookup"><span data-stu-id="35e90-219">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="35e90-220">Questa opzione è attivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="35e90-220">This is enabled by default.</span></span> <span data-ttu-id="35e90-221">Se si disabilita questa opzione, gli utenti che già sono uniti alla riunione per impostazione predefinita non vengono informati quando un utente si unisce o abbandona la riunione.</span><span class="sxs-lookup"><span data-stu-id="35e90-221">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="35e90-222">In **tipo di annunci di entrata/uscita**scegliere **toni** o **i nomi o numeri di telefono**.</span><span class="sxs-lookup"><span data-stu-id="35e90-222">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="35e90-223">Se si sceglie **nomi o numeri di telefono**, è anche possibile scegliere di attivare o disattivare **i chiamanti Ask per registrare il proprio nome prima di partecipare alla riunione**.</span><span class="sxs-lookup"><span data-stu-id="35e90-223">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

1. <span data-ttu-id="35e90-224">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="35e90-224">Click **Save**.</span></span>

<span data-ttu-id="35e90-225">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="35e90-225">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="35e90-226">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="35e90-226">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="35e90-227">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="35e90-227">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="35e90-228">Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="35e90-228">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="35e90-229">Nella sezione **esperienza di partecipazione alle riunioni**, selezionare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="35e90-229">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="35e90-230">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span><span class="sxs-lookup"><span data-stu-id="35e90-230">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="35e90-231">Se si deseleziona la casella di controllo, gli utenti che già sono uniti alla riunione per impostazione predefinita non vengono informati quando un utente si unisce o abbandona la riunione.</span><span class="sxs-lookup"><span data-stu-id="35e90-231">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="35e90-232">Ciò può essere impostata in base a una riunione per riunioni quando un utente partecipa a una riunione con un Skype per applicazioni aziendali o Microsoft Teams e cui modificare l'impostazione di **annuncio quando vengono inclusi o esclusi** dal menu riunione Skype o Microsoft Teams **le opzioni** del riunione.</span><span class="sxs-lookup"><span data-stu-id="35e90-232">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="35e90-233">**Chiamanti ASK per registrare il proprio nome prima di partecipare alla riunione** Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="35e90-233">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="35e90-234">Se si deseleziona la casella di controllo, i chiamanti non verranno richiesto di registrare il proprio nome prima che partecipano a una riunione.</span><span class="sxs-lookup"><span data-stu-id="35e90-234">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="35e90-235">Vedi **Modificare le impostazioni per un bridge per audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="35e90-235">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="35e90-236">Vedere [modificare le impostazioni per un ponte per conferenze Audio](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="35e90-236">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="35e90-237">**Impostare la lunghezza del PIN per le riunioni**</span><span class="sxs-lookup"><span data-stu-id="35e90-237">**Set the PIN length for meetings**</span></span>

 <span data-ttu-id="35e90-238">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="35e90-238">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="35e90-239">Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**.</span><span class="sxs-lookup"><span data-stu-id="35e90-239">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="35e90-240">Nella parte superiore della pagina **Ponti di conferenza** , fare clic su **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="35e90-240">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="35e90-241">Nel riquadro **Impostazioni Bridge** immettere il numero di cifre che si desidera utilizzare per il PIN nell'elenco **lunghezza del PIN** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="35e90-241">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="35e90-242">Il codice PIN deve essere compreso tra 4 e 12 cifre.</span><span class="sxs-lookup"><span data-stu-id="35e90-242">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="35e90-243">The default is 5.</span><span class="sxs-lookup"><span data-stu-id="35e90-243">The default is 5.</span></span>

<span data-ttu-id="35e90-244">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="35e90-244">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="35e90-245">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="35e90-245">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="35e90-246">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="35e90-246">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="35e90-247">Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="35e90-247">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="35e90-248">In **protezione**, immettere il numero di cifre che si desidera utilizzare per il PIN nell'elenco **lunghezza del PIN** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="35e90-248">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="35e90-249">Il codice PIN deve essere compreso tra 4 e 12 cifre.</span><span class="sxs-lookup"><span data-stu-id="35e90-249">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="35e90-250">The default is 5.</span><span class="sxs-lookup"><span data-stu-id="35e90-250">The default is 5.</span></span>
    
<span data-ttu-id="35e90-251">Vedere [modificare le impostazioni per un ponte per conferenze Audio](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="35e90-251">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="35e90-252">**Attivare o disattivare la posta elettronica non verrà inviato agli utenti audio**</span><span class="sxs-lookup"><span data-stu-id="35e90-252">**Enable or disable email from being sent to audio users**</span></span>

 <span data-ttu-id="35e90-253">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="35e90-253">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="35e90-254">Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**.</span><span class="sxs-lookup"><span data-stu-id="35e90-254">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="35e90-255">Nella parte superiore della pagina **Ponti di conferenza** , fare clic su **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="35e90-255">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="35e90-256">Nel riquadro **Impostazioni Bridge** , abilitare o disabilitare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="35e90-256">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="35e90-257">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="35e90-257">Click **Save**.</span></span> 
 
    <span data-ttu-id="35e90-258">Inoltre, è possibile inviare posta elettronica all'utente con le impostazioni di conferenza audio, quindi facendo clic su **Invia le informazioni di conferenza nel messaggio di posta elettronica**per le proprietà dell'utente per conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="35e90-258">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="35e90-259">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="35e90-259">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="35e90-260">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="35e90-260">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="35e90-261">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="35e90-261">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="35e90-262">Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.</span><span class="sxs-lookup"><span data-stu-id="35e90-262">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="35e90-263">Nella pagina **Impostazioni bridge Microsoft** , selezionare o deselezionare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="35e90-263">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="35e90-264">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="35e90-264">Click **Save**.</span></span>
    
    <span data-ttu-id="35e90-265">Inoltre, è possibile inviare posta elettronica all'utente con le impostazioni di conferenza audio, quindi facendo clic su **Invia informazioni conferenza tramite posta elettronica**per le proprietà dell'utente per conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="35e90-265">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="35e90-266">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="35e90-266">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="35e90-267">Visualizzare e impostare la lingua principale e le lingue secondarie in un bridge di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="35e90-267">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="35e90-268">Visualizzare e impostare il primario (impostazione predefinita) e lingue secondarie (alternative) su un ponte per conferenze audio</span><span class="sxs-lookup"><span data-stu-id="35e90-268">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

 <span data-ttu-id="35e90-269">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="35e90-269">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="35e90-270">Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**.</span><span class="sxs-lookup"><span data-stu-id="35e90-270">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="35e90-271">Selezionare un numero di telefono dall'elenco e fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="35e90-271">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="35e90-272">Selezionare le lingue desiderate nella sezione **lingua predefinita** e le relative **lingue alternative (facoltative)**.</span><span class="sxs-lookup"><span data-stu-id="35e90-272">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

<span data-ttu-id="35e90-273">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="35e90-273">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="35e90-274">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="35e90-274">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="35e90-275">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="35e90-275">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="35e90-276">Nel **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio**e quindi **bridge di Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="35e90-276">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="35e90-277">Selezionare un numero di telefono dall'elenco, fare clic su **Imposta lingue** nel riquadro azioni e quindi nella pagina **gruppo** di lingue, fare clic sull'utilizzo nell'elenco **lingua principale** per visualizzare l'elenco completo delle lingue supportate.</span><span class="sxs-lookup"><span data-stu-id="35e90-277">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="35e90-278">È inoltre possibile impostare le lingue principale e secondarie supportate quando si seleziona Microsoft come provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="35e90-278">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="35e90-279">L'ordine selezionato negli elenchi è lo stesso ordine in cui verranno visualizzate lingue per i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="35e90-279">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="35e90-280">Visualizzare i numeri di accesso esterno per i servizi l'audioconferenza</span><span class="sxs-lookup"><span data-stu-id="35e90-280">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="35e90-281">Vedere audioconferenza numeri di accesso</span><span class="sxs-lookup"><span data-stu-id="35e90-281">See audio conferencing dial-in numbers</span></span>

<span data-ttu-id="35e90-282">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="35e90-282">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="35e90-283">Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**.</span><span class="sxs-lookup"><span data-stu-id="35e90-283">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="35e90-284">Selezionare un numero di telefono dall'elenco e fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="35e90-284">Select a phone number from the list and click **Edit**.</span></span> <span data-ttu-id="35e90-285">È possibile:</span><span class="sxs-lookup"><span data-stu-id="35e90-285">Here you can:</span></span>
    
  - <span data-ttu-id="35e90-286">Visualizzare i numeri di telefono che sono specificati per Office 365 da utilizzare per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="35e90-286">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="35e90-287">Visualizzare la posizione e la lingua principale, che verrà utilizzata per l'operatore automatico di conferenze Audio.</span><span class="sxs-lookup"><span data-stu-id="35e90-287">View the location, and the primary language, that will be used by the Audio Conferencing auto attendant.</span></span>


<span data-ttu-id="35e90-288">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="35e90-288">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="35e90-289">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="35e90-289">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="35e90-290">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="35e90-290">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="35e90-291">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **bridge di Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="35e90-291">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="35e90-292">È possibile:</span><span class="sxs-lookup"><span data-stu-id="35e90-292">Here you can:</span></span>
    
  - <span data-ttu-id="35e90-293">Visualizzare i numeri di telefono che sono specificati per Office 365 da utilizzare per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="35e90-293">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="35e90-294">Visualizzare il percorso e le lingue principale e secondarie che verranno utilizzate per l'operatore automatico di conferenze Audio.</span><span class="sxs-lookup"><span data-stu-id="35e90-294">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="35e90-295">Selezionare il numero di telefono predefinito che verrà assegnato agli utenti quando vengono abilitati per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="35e90-295">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="35e90-296">Tuttavia, se viene modificato il numero di telefono predefinito di ponte per conferenze audio, non modifica il numero di telefono predefinito per gli utenti esistenti.</span><span class="sxs-lookup"><span data-stu-id="35e90-296">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="35e90-297">È possibile accedere ai **servizi di conferenza Audio** > **utenti** e selezionare le proprietà dell'utente per modificare il valore predefinito dei numeri per un utente di scegliere un nuovo numero dall'elenco di numeri che sono disponibili all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="35e90-297">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="35e90-298">[Visualizzare un elenco di numeri di conferenza Audio](see-a-list-of-audio-conferencing-numbers.md), vedere.</span><span class="sxs-lookup"><span data-stu-id="35e90-298">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-see-a-list-of-users-that-are-enabled"></a>![30x30.png di logo sfb](../images/sfb-logo-30x30.png) <span data-ttu-id="35e90-300">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="35e90-300">See a list of users that are enabled</span></span>

1. <span data-ttu-id="35e90-301">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="35e90-301">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="35e90-302">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="35e90-302">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="35e90-303">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio**> e quindi **utenti**.</span><span class="sxs-lookup"><span data-stu-id="35e90-303">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="35e90-304">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="35e90-304">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="35e90-305">Sono disponibili diverse impostazioni per gestire le impostazioni a livello dell'organizzazione tramite Windows PowerShell. In questo modo puoi applicare con facilità tali impostazioni a tutti gli utenti. Ecco le impostazioni a livello dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="35e90-305">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="35e90-306">Sono disponibili diverse impostazioni che è possibile gestire a livello di organizzazione tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="35e90-306">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="35e90-307">In questo modo semplice applicare le impostazioni per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="35e90-307">This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="35e90-308">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="35e90-308">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="35e90-309">Di seguito sono le impostazioni a livello di organizzazione:</span><span class="sxs-lookup"><span data-stu-id="35e90-309">Here are the organization-level settings:</span></span> 
 
- <span data-ttu-id="35e90-310">**Impostazione delle notifiche di ingresso/uscita** Il valore predefinito è _$true_.</span><span class="sxs-lookup"><span data-stu-id="35e90-310">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="35e90-311">**L'impostazione di registrazione del nome** Il valore predefinito è _$true_.</span><span class="sxs-lookup"><span data-stu-id="35e90-311">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="35e90-312">**Impostazione della lunghezza PIN** Il valore predefinito è 5.</span><span class="sxs-lookup"><span data-stu-id="35e90-312">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="35e90-313">**Impostazione solo dial-in riunioni da un telefono** Predefinito _$false_.</span><span class="sxs-lookup"><span data-stu-id="35e90-313">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="35e90-314">**L'impostazione se si desidera inviare la posta elettronica agli utenti** Il valore predefinito è _$true_.</span><span class="sxs-lookup"><span data-stu-id="35e90-314">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="35e90-315">**L'impostazione se si desidera inviare posta elettronica da un account diverso** Il valore predefinito è _$false_.</span><span class="sxs-lookup"><span data-stu-id="35e90-315">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="35e90-316">**Impostazione dell'indirizzo di mittente nel messaggio di posta elettronica inviato agli utenti** Il valore predefinito è _$null_.</span><span class="sxs-lookup"><span data-stu-id="35e90-316">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="35e90-317">**Se il nome visualizzato per il posta elettronica inviato agli utenti** Il valore predefinito è _$null_.</span><span class="sxs-lookup"><span data-stu-id="35e90-317">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="35e90-318">Per ulteriori informazioni su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="35e90-318">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="35e90-p123">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="35e90-p123">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="35e90-322">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="35e90-322">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="35e90-323">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="35e90-323">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="35e90-p124">Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="35e90-p124">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="35e90-326">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="35e90-326">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="35e90-327">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="35e90-327">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="35e90-328">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="35e90-328">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="35e90-p125">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="35e90-p125">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="35e90-331">See also</span><span class="sxs-lookup"><span data-stu-id="35e90-331">Related topics</span></span>

[<span data-ttu-id="35e90-332">Gestire le impostazioni di audioconferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="35e90-332">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


