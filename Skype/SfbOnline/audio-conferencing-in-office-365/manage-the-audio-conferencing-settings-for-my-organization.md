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
description: 'See steps to assign a dial-in conferencing license and conference ID to a user, set up a third party conferencing provider, and many other dial-in conferencing settings. '
ms.openlocfilehash: b2759e4ee1f8e8cac2f753eb5afecbf13642abb0
ms.sourcegitcommit: 2c084358844f02fbf7953f2ea49ed6d710cbf06f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/08/2018
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a><span data-ttu-id="5391d-103">Gestire le impostazioni di conferenze Audio per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="5391d-103">Manage the Audio Conferencing settings for my organization</span></span>

<span data-ttu-id="5391d-104">Potrebbe risultare più semplice per poter visualizzare tutte le impostazioni di audioconferenza per Skype per le aziende e Teams Microsoft in un unico sito.</span><span class="sxs-lookup"><span data-stu-id="5391d-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="5391d-105">Assegnare una licenza di conferenze Audio</span><span class="sxs-lookup"><span data-stu-id="5391d-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="5391d-106">È possibile assegnare licenze utilizzando **Skype per interfaccia di amministrazione di Business**.</span><span class="sxs-lookup"><span data-stu-id="5391d-106">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="5391d-107">È necessario utilizzare l'interfaccia di amministrazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="5391d-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="5391d-108">Vedi [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="5391d-108">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="5391d-109">**Per assegnare una licenza per un utente**</span><span class="sxs-lookup"><span data-stu-id="5391d-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="5391d-110">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5391d-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5391d-111">Nel riquadro di spostamento sinistro dell' **interfaccia di amministrazione di Office 365**, passare a **utenti** > **utenti attivi**e quindi selezionare l'utente o gli utenti dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="5391d-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5391d-112">Per assegnare licenze a un massimo di 20 utenti contemporaneamente, puoi ricorrere all'elenco a discesa **Selezionare una visualizzazione** e scegliere una delle opzioni oppure creare una visualizzazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="5391d-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="5391d-113">Quindi fai clic su **Modifica**, due volte su **Avanti**, seleziona la licenza e fai clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="5391d-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="5391d-114">Puoi anche assegnare licenze a più utenti con Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="5391d-114">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="5391d-115">Per istruzioni ed esempi di script PowerShell, vedere [Assegnare Skype per le licenze aziendali e team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="5391d-115">For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="5391d-116">Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="5391d-116">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="5391d-117">Nella pagina **Licenze per i prodotti** , attivare **Servizi di conferenza Audio** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5391d-117">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="5391d-118">Per ulteriori informazioni sulle licenze, vedere [Skype di licenza di componente aggiuntivo Business e i team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="5391d-118">For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="5391d-119">Dopo aver assegnato alla licenza, Microsoft potrebbe non viene inizialmente visualizzato nell'elenco come provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="5391d-119">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="5391d-120">In questa eventualità, esegui la disconnessione dall'interfaccia di amministrazione di Office 365 oppure premi CTRL+F5 per aggiornare la finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="5391d-120">If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="assign-a-conference-id-for-a-user"></a><span data-ttu-id="5391d-121">Un ID conferenza viene assegnato automaticamente ad un utente quando gli ID vengono configurati per le audioconferenze utilizzando Microsoft come provider. L'ID conferenza assegnato può essere statico o dinamico e viene inviato nell'invito alla conferenza al momento della pianificazione della conferenza stessa.</span><span class="sxs-lookup"><span data-stu-id="5391d-121">Assign a conference ID for a user</span></span>

<span data-ttu-id="5391d-122">Un ID conferenza viene automaticamente assegnato a un utente quando sono configurati per l'audioconferenza tramite Microsoft come provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="5391d-122">A conference ID is automatically assigned to a user when they are set up for audio conferencing using Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="5391d-123">L'ID conferenza viene inviato nell'invito alla riunione durante la riunione pianificata.</span><span class="sxs-lookup"><span data-stu-id="5391d-123">The conference ID is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="5391d-124">Ogni riunione che un utente pianifica verrà viene assegnato un ID conferenza univoco.</span><span class="sxs-lookup"><span data-stu-id="5391d-124">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>
  
<span data-ttu-id="5391d-125">Per impostare l'ID conferenza per un utente, esegui:</span><span class="sxs-lookup"><span data-stu-id="5391d-125">The Skype for Business admin center can't be used to assign a conference ID to a user, but you can use the Windows PowerShell cmdlet to do this.</span></span>
  
<span data-ttu-id="5391d-126">Un ID conferenza deve contenere 7 cifre e non può essere modificato nell'interfaccia di amministrazione di Skype for Business o tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5391d-126">To set the conference ID for a user, run:</span></span>
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> <span data-ttu-id="5391d-127">Un ID conferenza deve contenere 7 cifre e non è possibile modificare in Skype for Business admin center o utilizzando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5391d-127">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
<span data-ttu-id="5391d-128">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span><span class="sxs-lookup"><span data-stu-id="5391d-128">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="5391d-129">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="5391d-129">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="5391d-130">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="5391d-130">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="5391d-131">Gli utenti possono utilizzare Skype per strumento di migrazione di riunioni Business per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="5391d-131">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="5391d-132">Per informazioni su come scaricare, installare ed eseguire il Skype per strumento di aggiornamento riunione Business, vedere: [Strumento di aggiornamento di riunione per Skype per le aziende e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype online Business dello strumento di migrazione di riunioni (64 bit)](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype online Business riunione Strumento di migrazione (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="5391d-132">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="5391d-133">Modificare il provider di servizi di audioconferenza da Microsoft a un provider di terze parti</span><span class="sxs-lookup"><span data-stu-id="5391d-133">See [See, change, and reset a conference ID assigned to a user](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span></span>
    
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="5391d-134">Attivare o disattivare i messaggi di posta elettronica inviati agli utenti di audioconferenze con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="5391d-134">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="5391d-135">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="5391d-135">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="5391d-136">Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**.</span><span class="sxs-lookup"><span data-stu-id="5391d-136">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="5391d-137">Nella parte superiore della pagina **Ponti di conferenza** , fare clic su **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="5391d-137">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="5391d-138">Nel riquadro **Impostazioni Bridge** , abilitare o disabilitare **automaticamente inviare messaggi di posta elettronica per gli utenti di modificare le relative impostazioni di connessione**.</span><span class="sxs-lookup"><span data-stu-id="5391d-138">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="5391d-139">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5391d-139">Click **Save**.</span></span>

<span data-ttu-id="5391d-140">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="5391d-140">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="5391d-141">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5391d-141">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5391d-142">Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.</span><span class="sxs-lookup"><span data-stu-id="5391d-142">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="5391d-143">Nella pagina **Impostazioni bridge Microsoft** , selezionare o deselezionare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="5391d-143">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="5391d-144">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5391d-144">Click **Save**.</span></span>
    
    <span data-ttu-id="5391d-145">È anche possibile inviare messaggi di posta elettronica all'utente con le impostazioni di conferenza audio verranno le proprietà dell'utente per conferenze audio e facendo clic su **Invia informazioni conferenza tramite posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="5391d-145">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="5391d-146">L'ID e imposta come predefinito audioconferenza numero di telefono conferenza è inclusi nell'invito alla riunione, ma non il PIN.</span><span class="sxs-lookup"><span data-stu-id="5391d-146">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="5391d-147">[Uso di Windows PowerShell](send-an-email-to-a-user-with-their-dial-in-information.md)</span><span class="sxs-lookup"><span data-stu-id="5391d-147">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
 <span data-ttu-id="5391d-148">**Utilizzo di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="5391d-148">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="5391d-149">You can also use the Windows PowerShell and run:</span><span class="sxs-lookup"><span data-stu-id="5391d-149">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="5391d-150">È possibile utilizzare [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, inclusa la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5391d-150">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="5391d-151">Modificare le informazioni di contatto del mittente nei messaggi di posta elettronica inviato agli utenti</span><span class="sxs-lookup"><span data-stu-id="5391d-151">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="5391d-152">È possibile apportare modifiche alla posta elettronica inviato automaticamente agli utenti, tra cui l'indirizzo di posta elettronica e il nome visualizzato di informazioni di contatto del mittente.</span><span class="sxs-lookup"><span data-stu-id="5391d-152">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="5391d-153">Per impostazione predefinita, il mittente dei messaggi di posta elettronica è Office 365, ma è possibile modificare l'indirizzo di posta elettronica e viene visualizzato il nome utilizzando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .</span><span class="sxs-lookup"><span data-stu-id="5391d-153">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="5391d-154">Per apportare modifiche all'indirizzo di posta elettronica che invia messaggio di posta elettronica agli utenti, è necessario:</span><span class="sxs-lookup"><span data-stu-id="5391d-154">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="5391d-155">Immettere l'indirizzo di posta elettronica nel parametro _SendEmailFromAddress_ .</span><span class="sxs-lookup"><span data-stu-id="5391d-155">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="5391d-156">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span><span class="sxs-lookup"><span data-stu-id="5391d-156">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="5391d-157">Il parametro _SendEmailOverride_ impostato su _True_.</span><span class="sxs-lookup"><span data-stu-id="5391d-157">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="5391d-158">Se desideri modificare le informazioni relative all'indirizzo di posta elettronica, devi verificare che i criteri di posta elettronica in ingresso dell'organizzazione consentano i messaggi in arrivo dall'indirizzo di posta elettronica personalizzato.</span><span class="sxs-lookup"><span data-stu-id="5391d-158">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="5391d-159">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span><span class="sxs-lookup"><span data-stu-id="5391d-159">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="5391d-160">È possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, inclusa la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="5391d-160">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="5391d-161">Vedere [messaggi di posta elettronica che vengono inviati automaticamente agli utenti quando modificano le impostazioni di conferenza Audio](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="5391d-161">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="5391d-162">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5391d-162">Reset the meeting conference ID</span></span>

<span data-ttu-id="5391d-163">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="5391d-163">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="5391d-164">Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="5391d-164">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="5391d-165">Nella parte superiore della pagina, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="5391d-165">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="5391d-166">In **Servizi di conferenza Audio**, fare clic su **Reimposta ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="5391d-166">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

4. <span data-ttu-id="5391d-167">Nella **reimpostare ID conferenza?** finestra, fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="5391d-167">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="5391d-168">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="5391d-168">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="5391d-169">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="5391d-169">It's enabled by default.</span></span>

<span data-ttu-id="5391d-170">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="5391d-170">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="5391d-171">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5391d-171">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5391d-172">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="5391d-172">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="5391d-173">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio**e nel riquadro azioni in **ID conferenza**, fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="5391d-173">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="5391d-174">Nella **reimpostare ID conferenza?** finestra, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="5391d-174">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="5391d-175">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="5391d-175">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="5391d-176">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="5391d-176">It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="5391d-177">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="5391d-177">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="5391d-178">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="5391d-178">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="5391d-179">Gli utenti possono utilizzare Skype per strumento di migrazione di riunioni Business per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="5391d-179">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="5391d-180">Per informazioni su come scaricare, installare ed eseguire il Skype per strumento di aggiornamento riunione Business, vedere: [Strumento di aggiornamento di riunione per Skype per le aziende e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype online Business dello strumento di migrazione di riunioni (64 bit)](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype online Business riunione Strumento di migrazione (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="5391d-180">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="5391d-181">Reimpostare il PIN dell'organizzatore della conferenza</span><span class="sxs-lookup"><span data-stu-id="5391d-181">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="5391d-182">Reimpostare il PIN dell'organizzatore della conferenza</span><span class="sxs-lookup"><span data-stu-id="5391d-182">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="5391d-183">Ogni riunione che un utente pianifica verrà viene assegnato un ID conferenza univoco.</span><span class="sxs-lookup"><span data-stu-id="5391d-183">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="5391d-184">Benché un ID conferenza viene automaticamente creato e assegnato a un utente, è possibile quando non da un utente di utilizzare questo e si desidera impostare per un determinato numero o gli utenti non possono ricordare o sono persa loro ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="5391d-184">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="5391d-185">È possibile utilizzare Skype per interfaccia di amministrazione di Business e Windows PowerShell per visualizzare, modificare e ripristinare gli ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="5391d-185">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="5391d-186">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="5391d-186">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="5391d-187">Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="5391d-187">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="5391d-188">Nella parte superiore della pagina, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="5391d-188">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="5391d-189">In **Servizi di conferenza Audio**, fare clic su **Reimposta PIN**e quindi fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="5391d-189">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="5391d-190">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="5391d-190">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="5391d-191">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5391d-191">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5391d-192">Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.</span><span class="sxs-lookup"><span data-stu-id="5391d-192">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="5391d-193">Fare clic su **utenti**e quindi selezionare l'utente che si desidera reimpostare il PIN per.</span><span class="sxs-lookup"><span data-stu-id="5391d-193">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="5391d-194">Nel riquadro azioni, in **PIN**, fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="5391d-194">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="5391d-195">Gli utenti riceveranno un messaggio di posta elettronica con il proprio PIN quando questi vengono attivati per conferenze audio o quando viene reimpostato il PIN.</span><span class="sxs-lookup"><span data-stu-id="5391d-195">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="5391d-196">Ma se è stata disabilitata automaticamente l'invio di messaggi di posta elettronica, non verrà inviato un messaggio di posta elettronica Reimpostazione PIN e sarà necessario inviare manualmente il PIN all'utente.</span><span class="sxs-lookup"><span data-stu-id="5391d-196">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="5391d-197">The PIN will only be shown once after it has been reset.</span><span class="sxs-lookup"><span data-stu-id="5391d-197">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="5391d-198">Dopo che viene visualizzata immediatamente dopo la reimpostazione, il PIN non verrà visualizzato più nella proprietà utente. in realtà, \* \* \* verranno visualizzati.</span><span class="sxs-lookup"><span data-stu-id="5391d-198">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="5391d-199">Vedere [reimpostare il PIN per conferenze Audio](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="5391d-199">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="5391d-200">Inviare un messaggio di posta elettronica con informazioni di audioconferenza a un utente</span><span class="sxs-lookup"><span data-stu-id="5391d-200">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="5391d-201">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="5391d-201">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="5391d-202">Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="5391d-202">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="5391d-203">Nella parte superiore della pagina, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="5391d-203">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="5391d-204">In **Servizi di conferenza Audio**, fare clic su **Invia le informazioni di conferenza nel messaggio di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="5391d-204">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="5391d-205">A tale scopo, conferenze audio PIN non viene inviato all'utente.</span><span class="sxs-lookup"><span data-stu-id="5391d-205">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="5391d-206">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="5391d-206">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="5391d-207">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5391d-207">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5391d-208">Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.</span><span class="sxs-lookup"><span data-stu-id="5391d-208">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="5391d-209">Fare clic su **utenti**e quindi selezionare l'utente che si desidera reimpostare il PIN per.</span><span class="sxs-lookup"><span data-stu-id="5391d-209">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="5391d-210">Nel riquadro Azioni fai clic su **Invia informazioni sulla conferenza tramite posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="5391d-210">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="5391d-211">A tale scopo, conferenze audio PIN non viene inviato all'utente.</span><span class="sxs-lookup"><span data-stu-id="5391d-211">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="5391d-212">[Uso di Windows PowerShell](send-an-email-to-a-user-with-their-dial-in-information.md)</span><span class="sxs-lookup"><span data-stu-id="5391d-212">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a><span data-ttu-id="5391d-213">Impostazione del numero di telefono audioconferenza predefinito per gli organizzatori delle riunioni</span><span class="sxs-lookup"><span data-stu-id="5391d-213">Setting the default audio conferencing phone number for meeting organizers</span></span>

 <span data-ttu-id="5391d-214">**Per impostare il numero di telefono di audioconferenza predefinito per gli organizzatori delle riunioni quando un utente si sta abilitando per le conferenze Audio**</span><span class="sxs-lookup"><span data-stu-id="5391d-214">**To set the default audio conferencing phone number for meeting organizers when you are enabling a user for Audio Conferencing**</span></span>
  
1. <span data-ttu-id="5391d-215">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5391d-215">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5391d-216">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="5391d-216">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="5391d-217">Nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="5391d-217">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="5391d-218">Selezionare l'utente che si desidera abilitare per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="5391d-218">Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="5391d-219">Nel riquadro azioni, nella finestra delle proprietà dell'utente, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="5391d-219">In the Action pane, in the user's properties, click **Edit**.</span></span>
    
5. <span data-ttu-id="5391d-220">Nella pagina **proprietà** sotto il **nome del Provider**, utilizzare l'elenco a discesa per selezionare il provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="5391d-220">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="5391d-221">Se si seleziona Microsoft come provider di servizi di conferenza audio, è possibile scegliere il numero di telefono di audioconferenza predefinito dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="5391d-221">If you select Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="5391d-222">Se si seleziona un'AUDIOCONFERENZA di terze parti come provider di servizi di conferenza audio, è necessario immettere manualmente le tariffe e, se necessario, il numero verde.</span><span class="sxs-lookup"><span data-stu-id="5391d-222">If you select a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span> <span data-ttu-id="5391d-223">Questi numeri di telefono sarà il numero di telefono predefinito.</span><span class="sxs-lookup"><span data-stu-id="5391d-223">These phone numbers will be the default phone number.</span></span>
    
    <span data-ttu-id="5391d-224">Il numero di telefono predefinito audioconferenze con accesso esterno di un utente è il numero visualizzato nella invito alla riunione quando si pianifica una riunione.</span><span class="sxs-lookup"><span data-stu-id="5391d-224">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
6. <span data-ttu-id="5391d-225">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5391d-225">Click **Save**.</span></span> 
    
<span data-ttu-id="5391d-226">Vedere [impostare telefono numeri incluso nel invita](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="5391d-226">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
 <span data-ttu-id="5391d-227">**Per impostare il numero di telefono di audioconferenza predefinito per gli organizzatori delle riunioni dopo aver abilitato un utente per le conferenze audio**</span><span class="sxs-lookup"><span data-stu-id="5391d-227">**To set the default audio conferencing phone number for meeting organizers after you have enabled a user for audio conferencing**</span></span>
  
1. <span data-ttu-id="5391d-228">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5391d-228">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5391d-229">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="5391d-229">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="5391d-230">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **gli utenti**, selezionare l'utente desiderato e nella pagina azione fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="5391d-230">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, select the user you want, and in the Action page, click **Edit**.</span></span>
    
4. <span data-ttu-id="5391d-231">Nella pagina **proprietà** sotto il **nome del Provider**, utilizzare l'elenco a discesa per selezionare il provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="5391d-231">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="5391d-232">Se l'utente utilizza Microsoft come provider di servizi di conferenza audio, è possibile scegliere il numero di telefono di audioconferenza predefinito dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="5391d-232">If the user uses Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="5391d-233">Se l'utente viene utilizzata un'AUDIOCONFERENZA di terze parti come provider di servizi di conferenza audio, sarà necessario immettere manualmente le tariffe e, se necessario, il numero verde.</span><span class="sxs-lookup"><span data-stu-id="5391d-233">If the user uses a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span>
    
    <span data-ttu-id="5391d-234">Il numero di telefono predefinito audioconferenze con accesso esterno di un utente è il numero visualizzato nella invito alla riunione quando si pianifica una riunione.</span><span class="sxs-lookup"><span data-stu-id="5391d-234">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
5. <span data-ttu-id="5391d-235">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5391d-235">Click **Save**.</span></span> 
    
<span data-ttu-id="5391d-236">Vedere [impostare telefono numeri incluso nel invita](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="5391d-236">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="5391d-237">La scelta delle impostazioni di ponte conferenza</span><span class="sxs-lookup"><span data-stu-id="5391d-237">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="5391d-238">**Impostare l'esperienza di riunione quando i chiamanti di partecipare a una riunione**</span><span class="sxs-lookup"><span data-stu-id="5391d-238">**Set the meeting experience when callers join a meeting**</span></span>

 <span data-ttu-id="5391d-239">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="5391d-239">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="5391d-240">Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**.</span><span class="sxs-lookup"><span data-stu-id="5391d-240">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="5391d-241">Nella parte superiore della pagina **Ponti di conferenza** , fare clic su **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="5391d-241">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="5391d-242">Nel riquadro **Impostazioni Bridge** , abilitare o disabilitare **voce della riunione e chiudere le notifiche**.</span><span class="sxs-lookup"><span data-stu-id="5391d-242">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="5391d-243">Questa opzione è attivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5391d-243">This is enabled by default.</span></span> <span data-ttu-id="5391d-244">Se si disabilita questa opzione, gli utenti che già sono uniti alla riunione per impostazione predefinita non vengono informati quando un utente si unisce o abbandona la riunione.</span><span class="sxs-lookup"><span data-stu-id="5391d-244">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="5391d-245">In **tipo di annunci di entrata/uscita**scegliere **toni** o **i nomi o numeri di telefono**.</span><span class="sxs-lookup"><span data-stu-id="5391d-245">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="5391d-246">Se si sceglie **nomi o numeri di telefono**, è anche possibile scegliere di attivare o disattivare **i chiamanti Ask per registrare il proprio nome prima di partecipare alla riunione**.</span><span class="sxs-lookup"><span data-stu-id="5391d-246">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

1. <span data-ttu-id="5391d-247">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5391d-247">Click **Save**.</span></span>

<span data-ttu-id="5391d-248">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="5391d-248">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="5391d-249">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5391d-249">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5391d-250">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="5391d-250">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="5391d-251">Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="5391d-251">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="5391d-252">Nella sezione **esperienza di partecipazione alle riunioni**, selezionare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="5391d-252">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="5391d-253">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span><span class="sxs-lookup"><span data-stu-id="5391d-253">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="5391d-254">Se si deseleziona la casella di controllo, gli utenti che già sono uniti alla riunione per impostazione predefinita non vengono informati quando un utente si unisce o abbandona la riunione.</span><span class="sxs-lookup"><span data-stu-id="5391d-254">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="5391d-255">Ciò può essere impostata in base a una riunione per riunioni quando un utente partecipa a una riunione con un Skype per applicazioni aziendali o Microsoft Teams e cui modificare l'impostazione di **annuncio quando vengono inclusi o esclusi** dal menu riunione Skype o Microsoft Teams **le opzioni** del riunione.</span><span class="sxs-lookup"><span data-stu-id="5391d-255">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="5391d-256">**Chiamanti ASK per registrare il proprio nome prima di partecipare alla riunione** Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="5391d-256">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="5391d-257">Se si deseleziona la casella di controllo, i chiamanti non verranno richiesto di registrare il proprio nome prima che partecipano a una riunione.</span><span class="sxs-lookup"><span data-stu-id="5391d-257">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="5391d-258">Vedi **Modificare le impostazioni per un bridge per audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="5391d-258">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="5391d-259">Vedere [modificare le impostazioni per un ponte per conferenze Audio](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="5391d-259">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="5391d-260">**Impostare la lunghezza del PIN per le riunioni**</span><span class="sxs-lookup"><span data-stu-id="5391d-260">**Set the PIN length for meetings**</span></span>

 <span data-ttu-id="5391d-261">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="5391d-261">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="5391d-262">Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**.</span><span class="sxs-lookup"><span data-stu-id="5391d-262">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="5391d-263">Nella parte superiore della pagina **Ponti di conferenza** , fare clic su **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="5391d-263">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="5391d-264">Nel riquadro **Impostazioni Bridge** immettere il numero di cifre che si desidera utilizzare per il PIN nell'elenco **lunghezza del PIN** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5391d-264">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="5391d-265">Il codice PIN deve essere compreso tra 4 e 12 cifre.</span><span class="sxs-lookup"><span data-stu-id="5391d-265">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="5391d-266">The default is 5.</span><span class="sxs-lookup"><span data-stu-id="5391d-266">The default is 5.</span></span>

<span data-ttu-id="5391d-267">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="5391d-267">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="5391d-268">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5391d-268">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5391d-269">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="5391d-269">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="5391d-270">Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="5391d-270">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="5391d-271">In **protezione**, immettere il numero di cifre che si desidera utilizzare per il PIN nell'elenco **lunghezza del PIN** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5391d-271">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="5391d-272">Il codice PIN deve essere compreso tra 4 e 12 cifre.</span><span class="sxs-lookup"><span data-stu-id="5391d-272">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="5391d-273">The default is 5.</span><span class="sxs-lookup"><span data-stu-id="5391d-273">The default is 5.</span></span>
    
<span data-ttu-id="5391d-274">Vedere [modificare le impostazioni per un ponte per conferenze Audio](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="5391d-274">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="5391d-275">**Attivare o disattivare la posta elettronica non verrà inviato agli utenti audio**</span><span class="sxs-lookup"><span data-stu-id="5391d-275">**Enable or disable email from being sent to audio users**</span></span>

 <span data-ttu-id="5391d-276">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="5391d-276">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="5391d-277">Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**.</span><span class="sxs-lookup"><span data-stu-id="5391d-277">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="5391d-278">Nella parte superiore della pagina **Ponti di conferenza** , fare clic su **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="5391d-278">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="5391d-279">Nel riquadro **Impostazioni Bridge** , abilitare o disabilitare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="5391d-279">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="5391d-280">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5391d-280">Click **Save**.</span></span> 
 
    <span data-ttu-id="5391d-281">Inoltre, è possibile inviare posta elettronica all'utente con le impostazioni di conferenza audio, quindi facendo clic su **Invia le informazioni di conferenza nel messaggio di posta elettronica**per le proprietà dell'utente per conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="5391d-281">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="5391d-282">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="5391d-282">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="5391d-283">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="5391d-283">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="5391d-284">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5391d-284">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5391d-285">Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.</span><span class="sxs-lookup"><span data-stu-id="5391d-285">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="5391d-286">Nella pagina **Impostazioni bridge Microsoft** , selezionare o deselezionare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="5391d-286">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="5391d-287">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5391d-287">Click **Save**.</span></span>
    
    <span data-ttu-id="5391d-288">Inoltre, è possibile inviare posta elettronica all'utente con le impostazioni di conferenza audio, quindi facendo clic su **Invia informazioni conferenza tramite posta elettronica**per le proprietà dell'utente per conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="5391d-288">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="5391d-289">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="5391d-289">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="5391d-290">Visualizzare e impostare la lingua principale e le lingue secondarie in un bridge di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="5391d-290">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="5391d-291">Visualizzare e impostare il primario (impostazione predefinita) e lingue secondarie (alternative) su un ponte per conferenze audio</span><span class="sxs-lookup"><span data-stu-id="5391d-291">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

 <span data-ttu-id="5391d-292">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="5391d-292">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="5391d-293">Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**.</span><span class="sxs-lookup"><span data-stu-id="5391d-293">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="5391d-294">Selezionare un numero di telefono dall'elenco e fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="5391d-294">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="5391d-295">Selezionare le lingue desiderate nella sezione **lingua predefinita** e le relative **lingue alternative (facoltative)**.</span><span class="sxs-lookup"><span data-stu-id="5391d-295">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

<span data-ttu-id="5391d-296">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="5391d-296">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="5391d-297">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5391d-297">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5391d-298">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="5391d-298">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="5391d-299">Nel **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio**e quindi **bridge di Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="5391d-299">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="5391d-300">Selezionare un numero di telefono dall'elenco, fare clic su **Imposta lingue** nel riquadro azioni e quindi nella pagina **gruppo** di lingue, fare clic sull'utilizzo nell'elenco **lingua principale** per visualizzare l'elenco completo delle lingue supportate.</span><span class="sxs-lookup"><span data-stu-id="5391d-300">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="5391d-301">È inoltre possibile impostare le lingue principale e secondarie supportate quando si seleziona Microsoft come provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="5391d-301">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="5391d-302">L'ordine selezionato negli elenchi è lo stesso ordine in cui verranno visualizzate lingue per i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="5391d-302">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="5391d-303">Visualizzare i numeri di accesso esterno per i servizi l'audioconferenza</span><span class="sxs-lookup"><span data-stu-id="5391d-303">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png--see-audio-conferencing-dial-in-numbers"></a>![30x30.png di logo sfb](../images/sfb-logo-30x30.png)  <span data-ttu-id="5391d-305">Vedere audioconferenza numeri di accesso</span><span class="sxs-lookup"><span data-stu-id="5391d-305">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="5391d-306">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5391d-306">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5391d-307">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="5391d-307">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="5391d-308">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **bridge di Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="5391d-308">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="5391d-309">È possibile:</span><span class="sxs-lookup"><span data-stu-id="5391d-309">Here you can:</span></span>
    
  - <span data-ttu-id="5391d-310">Visualizzare i numeri di telefono che sono specificati per Office 365 da utilizzare per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="5391d-310">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="5391d-311">Visualizzare il percorso e le lingue principale e secondarie che verranno utilizzate per l'operatore automatico di conferenze Audio.</span><span class="sxs-lookup"><span data-stu-id="5391d-311">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="5391d-312">Selezionare il numero di telefono predefinito che verrà assegnato agli utenti quando vengono abilitati per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="5391d-312">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="5391d-313">Tuttavia, se viene modificato il numero di telefono predefinito di ponte per conferenze audio, non modifica il numero di telefono predefinito per gli utenti esistenti.</span><span class="sxs-lookup"><span data-stu-id="5391d-313">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="5391d-314">È possibile accedere ai **servizi di conferenza Audio** > **utenti** e selezionare le proprietà dell'utente per modificare il valore predefinito dei numeri per un utente di scegliere un nuovo numero dall'elenco di numeri che sono disponibili all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5391d-314">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="5391d-315">[Visualizzare un elenco di numeri di conferenza Audio](see-a-list-of-audio-conferencing-numbers.md), vedere.</span><span class="sxs-lookup"><span data-stu-id="5391d-315">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-see-a-list-of-users-that-are-enabled"></a>![30x30.png di logo sfb](../images/sfb-logo-30x30.png) <span data-ttu-id="5391d-317">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5391d-317">See a list of users that are enabled</span></span>

1. <span data-ttu-id="5391d-318">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="5391d-318">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="5391d-319">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="5391d-319">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="5391d-320">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio**> e quindi **utenti**.</span><span class="sxs-lookup"><span data-stu-id="5391d-320">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="5391d-321">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5391d-321">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="5391d-322">Sono disponibili diverse impostazioni per gestire le impostazioni a livello dell'organizzazione tramite Windows PowerShell. In questo modo puoi applicare con facilità tali impostazioni a tutti gli utenti. Ecco le impostazioni a livello dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="5391d-322">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="5391d-323">Sono disponibili diverse impostazioni che è possibile gestire a livello di organizzazione tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5391d-323">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="5391d-324">In questo modo semplice applicare le impostazioni per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="5391d-324">This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="5391d-325">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="5391d-325">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="5391d-326">Di seguito sono le impostazioni a livello di organizzazione:</span><span class="sxs-lookup"><span data-stu-id="5391d-326">Here are the organization-level settings:</span></span> 
> 
- <span data-ttu-id="5391d-327">**Impostazione delle notifiche di ingresso/uscita** Il valore predefinito è _$true_.</span><span class="sxs-lookup"><span data-stu-id="5391d-327">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="5391d-328">**L'impostazione di registrazione del nome** Il valore predefinito è _$true_.</span><span class="sxs-lookup"><span data-stu-id="5391d-328">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="5391d-329">**Impostazione della lunghezza PIN** Il valore predefinito è 5.</span><span class="sxs-lookup"><span data-stu-id="5391d-329">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="5391d-330">**Impostazione solo dial-in riunioni da un telefono** Predefinito _$false_.</span><span class="sxs-lookup"><span data-stu-id="5391d-330">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="5391d-331">**L'impostazione se si desidera inviare la posta elettronica agli utenti** Il valore predefinito è _$true_.</span><span class="sxs-lookup"><span data-stu-id="5391d-331">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="5391d-332">**L'impostazione se si desidera inviare posta elettronica da un account diverso** Il valore predefinito è _$false_.</span><span class="sxs-lookup"><span data-stu-id="5391d-332">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="5391d-333">**Impostazione dell'indirizzo di mittente nel messaggio di posta elettronica inviato agli utenti** Il valore predefinito è _$null_.</span><span class="sxs-lookup"><span data-stu-id="5391d-333">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="5391d-334">**Se il nome visualizzato per il posta elettronica inviato agli utenti** Il valore predefinito è _$null_.</span><span class="sxs-lookup"><span data-stu-id="5391d-334">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5391d-335">Per ulteriori informazioni su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5391d-335">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="5391d-p125">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="5391d-p125">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="5391d-339">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="5391d-339">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="5391d-340">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="5391d-340">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="5391d-p126">Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="5391d-p126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="5391d-343">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5391d-343">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="5391d-344">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5391d-344">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="5391d-345">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="5391d-345">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="5391d-p127">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="5391d-p127">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="5391d-348">See also</span><span class="sxs-lookup"><span data-stu-id="5391d-348">Related topics</span></span>

[<span data-ttu-id="5391d-349">Gestire le impostazioni di audioconferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="5391d-349">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


