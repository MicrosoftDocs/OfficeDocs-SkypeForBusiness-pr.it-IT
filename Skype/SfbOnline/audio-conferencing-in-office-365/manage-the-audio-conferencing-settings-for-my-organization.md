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
ms.openlocfilehash: db355e71ff90a43c46900ad2b95b9e8593a9094d
ms.sourcegitcommit: fa61d0b380a6ee559ad78e06bba85bc28d1045a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/03/2018
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization"></a><span data-ttu-id="858f1-103">Gestire le impostazioni di conferenze Audio per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="858f1-103">Manage the Audio Conferencing settings for my organization</span></span>

<span data-ttu-id="858f1-104">Potrebbe risultare più semplice per poter visualizzare tutte le impostazioni di audioconferenza per Skype per le aziende e Teams Microsoft in un unico sito.</span><span class="sxs-lookup"><span data-stu-id="858f1-104">It might be easier for you to see all of the audio conferencing settings for Skype for Business and Microsoft Teams in one place.</span></span> 
  
## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="858f1-105">Assegnare una licenza di conferenze Audio</span><span class="sxs-lookup"><span data-stu-id="858f1-105">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="858f1-106">È possibile assegnare licenze utilizzando **Skype per interfaccia di amministrazione di Business**.</span><span class="sxs-lookup"><span data-stu-id="858f1-106">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="858f1-107">È necessario utilizzare l'interfaccia di amministrazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="858f1-107">You must use the Office 365 admin center.</span></span> <span data-ttu-id="858f1-108">Vedi [Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="858f1-108">See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
 <span data-ttu-id="858f1-109">**Per assegnare una licenza per un utente**</span><span class="sxs-lookup"><span data-stu-id="858f1-109">**To assign a license for a user**</span></span>
  
1. <span data-ttu-id="858f1-110">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="858f1-110">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="858f1-111">Nel riquadro di spostamento sinistro dell' **interfaccia di amministrazione di Office 365**, passare a **utenti** > **utenti attivi**e quindi selezionare l'utente o gli utenti dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="858f1-111">In the left navigation of the **Office 365 admin center**, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="858f1-112">Per assegnare licenze a un massimo di 20 utenti contemporaneamente, puoi ricorrere all'elenco a discesa **Selezionare una visualizzazione** e scegliere una delle opzioni oppure creare una visualizzazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="858f1-112">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="858f1-113">Quindi fai clic su **Modifica**, due volte su **Avanti**, seleziona la licenza e fai clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="858f1-113">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="858f1-114">Puoi anche assegnare licenze a più utenti con Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="858f1-114">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="858f1-115">Per istruzioni ed esempi di script PowerShell, vedere [Assegnare Skype per le licenze aziendali e team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="858f1-115">For instructions and sample PowerShell scripts, see [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> 
  
3. <span data-ttu-id="858f1-116">Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="858f1-116">In the Action pane under **Product licenses**, click **Edit**.</span></span> 
    
4. <span data-ttu-id="858f1-117">Nella pagina **Licenze per i prodotti** , attivare **Servizi di conferenza Audio** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="858f1-117">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="858f1-118">Per ulteriori informazioni sulle licenze, vedere [Skype di licenza di componente aggiuntivo Business e i team di Microsoft](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="858f1-118">For more on licensing, see [Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
> [!NOTE]
> <span data-ttu-id="858f1-119">Dopo aver assegnato alla licenza, Microsoft potrebbe non viene inizialmente visualizzato nell'elenco come provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="858f1-119">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="858f1-120">In questa eventualità, esegui la disconnessione dall'interfaccia di amministrazione di Office 365 oppure premi CTRL+F5 per aggiornare la finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="858f1-120">If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span> 
  
## <a name="assign-a-conference-id-for-a-user"></a><span data-ttu-id="858f1-121">Un ID conferenza viene assegnato automaticamente ad un utente quando gli ID vengono configurati per le audioconferenze utilizzando Microsoft come provider. L'ID conferenza assegnato può essere statico o dinamico e viene inviato nell'invito alla conferenza al momento della pianificazione della conferenza stessa.</span><span class="sxs-lookup"><span data-stu-id="858f1-121">Assign a conference ID for a user</span></span>

<span data-ttu-id="858f1-122">Un ID conferenza viene automaticamente assegnato a un utente quando sono configurati per l'audioconferenza tramite Microsoft come provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="858f1-122">A conference ID is automatically assigned to a user when they are set up for audio conferencing using Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="858f1-123">L'ID conferenza viene inviato nell'invito alla riunione durante la riunione pianificata.</span><span class="sxs-lookup"><span data-stu-id="858f1-123">The conference ID is sent in the meeting invite when the meeting is scheduled.</span></span> <span data-ttu-id="858f1-124">Ogni riunione che un utente pianifica verrà viene assegnato un ID conferenza univoco.</span><span class="sxs-lookup"><span data-stu-id="858f1-124">Each meeting that a user schedules will get assigned a unique conference ID.</span></span>
  
<span data-ttu-id="858f1-125">Per impostare l'ID conferenza per un utente, esegui:</span><span class="sxs-lookup"><span data-stu-id="858f1-125">The Skype for Business admin center can't be used to assign a conference ID to a user, but you can use the Windows PowerShell cmdlet to do this.</span></span>
  
<span data-ttu-id="858f1-126">Un ID conferenza deve contenere 7 cifre e non può essere modificato nell'interfaccia di amministrazione di Skype for Business o tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="858f1-126">To set the conference ID for a user, run:</span></span>
  
```
Set-CsOnlineDialInConferencingUser -Identity "Amos Marble"  -ConferenceId 8271964 
```

> [!IMPORTANT]
> <span data-ttu-id="858f1-127">Un ID conferenza deve contenere 7 cifre e non è possibile modificare in Skype for Business admin center o utilizzando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="858f1-127">A conference ID must contain 7 digits, and you can't change it in the Skype for Business admin center or by using Windows PowerShell.</span></span> 
  
<span data-ttu-id="858f1-128">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span><span class="sxs-lookup"><span data-stu-id="858f1-128">See [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688 ) to learn more about the cmdlet.</span></span>
  
> [!IMPORTANT]
>  <span data-ttu-id="858f1-129">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="858f1-129">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="858f1-130">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="858f1-130">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="858f1-131">Gli utenti possono utilizzare Skype per strumento di migrazione di riunioni Business per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="858f1-131">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="858f1-132">Per informazioni su come scaricare, installare ed eseguire il Skype per strumento di aggiornamento riunione Business, vedere: [Strumento di aggiornamento di riunione per Skype per le aziende e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype online Business dello strumento di migrazione di riunioni (64 bit)](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype online Business riunione Strumento di migrazione (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="858f1-132">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="858f1-133">Modificare il provider di servizi di audioconferenza da Microsoft a un provider di terze parti</span><span class="sxs-lookup"><span data-stu-id="858f1-133">See [See, change, and reset a conference ID assigned to a user](see-change-and-reset-a-conference-id-assigned-to-a-user.md).</span></span>
  
## <a name="change-the-audio-conferencing-provider-from-microsoft-to-a-third-party-provider"></a><span data-ttu-id="858f1-134">Modificare il provider di servizi di conferenza audio da Microsoft a un provider di terze parti</span><span class="sxs-lookup"><span data-stu-id="858f1-134">Change the audio conferencing provider from Microsoft to a third-party provider</span></span>

<span data-ttu-id="858f1-135">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="858f1-135">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="858f1-136">Sign in to Office 365 with your work or school account.</span><span class="sxs-lookup"><span data-stu-id="858f1-136">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="858f1-137">Go to the **Office 365 admin center** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="858f1-137">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="858f1-138">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **gli utenti**e quindi selezionare l'utente che si desidera modificare il provider di servizi di conferenza audio per.</span><span class="sxs-lookup"><span data-stu-id="858f1-138">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, and then and select the user you want to change the audio conferencing provider for.</span></span>
    
4. <span data-ttu-id="858f1-139">In the Action pane, click **Edit**.</span><span class="sxs-lookup"><span data-stu-id="858f1-139">In the Action pane, click **Edit**.</span></span> 
    
5. <span data-ttu-id="858f1-140">Nella pagina **proprietà** sotto il **nome del Provider**, scegliere il provider di servizi di conferenza audio per l'utente.</span><span class="sxs-lookup"><span data-stu-id="858f1-140">On the **Properties** page, under **Provider name**, choose the audio conferencing provider for the user.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="858f1-141">È possibile selezionare Microsoft come provider di servizi di conferenza audio o **Nessuno** solo se sono stati selezionati più utenti.</span><span class="sxs-lookup"><span data-stu-id="858f1-141">You can only select Microsoft as the audio conferencing provider or **None** if you have selected multiple users.</span></span>
  
6. <span data-ttu-id="858f1-142">Consulta **Modificare il provider di servizi di conferenza telefonica con accesso esterno per gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="858f1-142">Click **Save**.</span></span> 
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="858f1-143">Attivare o disattivare i messaggi di posta elettronica inviati agli utenti di audioconferenze con accesso esterno</span><span class="sxs-lookup"><span data-stu-id="858f1-143">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="858f1-144">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="858f1-144">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="858f1-145">Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**.</span><span class="sxs-lookup"><span data-stu-id="858f1-145">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="858f1-146">Nella parte superiore della pagina **Ponti di conferenza** , fare clic su **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="858f1-146">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="858f1-147">Nel riquadro **Impostazioni Bridge** , abilitare o disabilitare **automaticamente inviare messaggi di posta elettronica per gli utenti di modificare le relative impostazioni di connessione**.</span><span class="sxs-lookup"><span data-stu-id="858f1-147">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="858f1-148">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="858f1-148">Click **Save**.</span></span>

<span data-ttu-id="858f1-149">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="858f1-149">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="858f1-150">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="858f1-150">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="858f1-151">Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.</span><span class="sxs-lookup"><span data-stu-id="858f1-151">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="858f1-152">Nella pagina **Impostazioni bridge Microsoft** , selezionare o deselezionare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="858f1-152">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="858f1-153">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="858f1-153">Click **Save**.</span></span>
    
    <span data-ttu-id="858f1-154">È anche possibile inviare messaggi di posta elettronica all'utente con le impostazioni di conferenza audio verranno le proprietà dell'utente per conferenze audio e facendo clic su **Invia informazioni conferenza tramite posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="858f1-154">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="858f1-155">L'ID e imposta come predefinito audioconferenza numero di telefono conferenza è inclusi nell'invito alla riunione, ma non il PIN.</span><span class="sxs-lookup"><span data-stu-id="858f1-155">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>
    
    <span data-ttu-id="858f1-156">[Uso di Windows PowerShell](send-an-email-to-a-user-with-their-dial-in-information.md)</span><span class="sxs-lookup"><span data-stu-id="858f1-156">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
 <span data-ttu-id="858f1-157">**Utilizzo di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="858f1-157">**Using Windows PowerShell**</span></span>
  
- <span data-ttu-id="858f1-158">You can also use the Windows PowerShell and run:</span><span class="sxs-lookup"><span data-stu-id="858f1-158">You can also use the Windows PowerShell and run:</span></span> 
    
  ```
  Set-CsOnlineDialInConferencingTenantSetting -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="858f1-159">È possibile utilizzare [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, inclusa la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="858f1-159">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization, including email.</span></span>
    
## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="858f1-160">Modificare le informazioni di contatto del mittente nei messaggi di posta elettronica inviato agli utenti</span><span class="sxs-lookup"><span data-stu-id="858f1-160">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="858f1-161">È possibile apportare modifiche alla posta elettronica inviato automaticamente agli utenti, tra cui l'indirizzo di posta elettronica e il nome visualizzato di informazioni di contatto del mittente.</span><span class="sxs-lookup"><span data-stu-id="858f1-161">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="858f1-162">Per impostazione predefinita, il mittente dei messaggi di posta elettronica è Office 365, ma è possibile modificare l'indirizzo di posta elettronica e viene visualizzato il nome utilizzando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) .</span><span class="sxs-lookup"><span data-stu-id="858f1-162">By default, the sender of the emails is Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="858f1-163">Per apportare modifiche all'indirizzo di posta elettronica che invia messaggio di posta elettronica agli utenti, è necessario:</span><span class="sxs-lookup"><span data-stu-id="858f1-163">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="858f1-164">Immettere l'indirizzo di posta elettronica nel parametro _SendEmailFromAddress_ .</span><span class="sxs-lookup"><span data-stu-id="858f1-164">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="858f1-165">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span><span class="sxs-lookup"><span data-stu-id="858f1-165">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="858f1-166">Il parametro _SendEmailOverride_ impostato su _True_.</span><span class="sxs-lookup"><span data-stu-id="858f1-166">Set the _SendEmailOverride_ parameter to _True_.</span></span>
    
<span data-ttu-id="858f1-167">Se desideri modificare le informazioni relative all'indirizzo di posta elettronica, devi verificare che i criteri di posta elettronica in ingresso dell'organizzazione consentano i messaggi in arrivo dall'indirizzo di posta elettronica personalizzato.</span><span class="sxs-lookup"><span data-stu-id="858f1-167">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>
  
```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="858f1-168">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span><span class="sxs-lookup"><span data-stu-id="858f1-168">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>
  
<span data-ttu-id="858f1-169">È possibile utilizzare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per l'organizzazione, inclusa la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="858f1-169">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet to manage other settings for your organization, including email.</span></span>
  
<span data-ttu-id="858f1-170">Vedere [messaggi di posta elettronica che vengono inviati automaticamente agli utenti quando modificano le impostazioni di conferenza Audio](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="858f1-170">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>
  
## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="858f1-171">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="858f1-171">Reset the meeting conference ID</span></span>

<span data-ttu-id="858f1-172">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="858f1-172">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="858f1-173">Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="858f1-173">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="858f1-174">Nella parte superiore della pagina, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="858f1-174">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="858f1-175">In **Servizi di conferenza Audio**, fare clic su **Reimposta ID conferenza**.</span><span class="sxs-lookup"><span data-stu-id="858f1-175">Under **Audio Conferencing**, click **Reset conference ID**.</span></span>  

4. <span data-ttu-id="858f1-176">Nella **reimpostare ID conferenza?** finestra, fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="858f1-176">In the **Reset conference ID?** window, click **Reset**.</span></span> <span data-ttu-id="858f1-177">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="858f1-177">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="858f1-178">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="858f1-178">It's enabled by default.</span></span>

<span data-ttu-id="858f1-179">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="858f1-179">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="858f1-180">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="858f1-180">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="858f1-181">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="858f1-181">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="858f1-182">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio**e nel riquadro azioni in **ID conferenza**, fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="858f1-182">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>
    
4. <span data-ttu-id="858f1-183">Nella **reimpostare ID conferenza?** finestra, fare clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="858f1-183">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="858f1-184">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span><span class="sxs-lookup"><span data-stu-id="858f1-184">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="858f1-185">It's enabled by default.</span><span class="sxs-lookup"><span data-stu-id="858f1-185">It's enabled by default.</span></span>
    
    > [!IMPORTANT]
    >  <span data-ttu-id="858f1-186">After a new conference ID is created, the old conference ID can't be used by callers.</span><span class="sxs-lookup"><span data-stu-id="858f1-186">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="858f1-187">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="858f1-187">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="858f1-188">Gli utenti possono utilizzare Skype per strumento di migrazione di riunioni Business per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="858f1-188">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="858f1-189">Per informazioni su come scaricare, installare ed eseguire il Skype per strumento di aggiornamento riunione Business, vedere: [Strumento di aggiornamento di riunione per Skype per le aziende e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype online Business dello strumento di migrazione di riunioni (64 bit)](http://go.microsoft.com/fwlink/?LinkID=626047)e [Skype online Business riunione Strumento di migrazione (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="858f1-189">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](http://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span></span>
  
<span data-ttu-id="858f1-190">Reimpostare il PIN dell'organizzatore della conferenza</span><span class="sxs-lookup"><span data-stu-id="858f1-190">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
  
## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="858f1-191">Reimpostare il PIN dell'organizzatore della conferenza</span><span class="sxs-lookup"><span data-stu-id="858f1-191">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="858f1-192">Ogni riunione che un utente pianifica verrà viene assegnato un ID conferenza univoco.</span><span class="sxs-lookup"><span data-stu-id="858f1-192">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="858f1-193">Benché un ID conferenza viene automaticamente creato e assegnato a un utente, è possibile quando non da un utente di utilizzare questo e si desidera impostare per un determinato numero o gli utenti non possono ricordare o sono persa loro ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="858f1-193">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="858f1-194">È possibile utilizzare Skype per interfaccia di amministrazione di Business e Windows PowerShell per visualizzare, modificare e ripristinare gli ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="858f1-194">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>

<span data-ttu-id="858f1-195">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="858f1-195">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="858f1-196">Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="858f1-196">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="858f1-197">Nella parte superiore della pagina, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="858f1-197">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="858f1-198">In **Servizi di conferenza Audio**, fare clic su **Reimposta PIN**e quindi fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="858f1-198">Under **Audio Conferencing**, click **Reset PIN**, and then click **Reset**.</span></span> 
  
<span data-ttu-id="858f1-199">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="858f1-199">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="858f1-200">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="858f1-200">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="858f1-201">Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.</span><span class="sxs-lookup"><span data-stu-id="858f1-201">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="858f1-202">Fare clic su **utenti**e quindi selezionare l'utente che si desidera reimpostare il PIN per.</span><span class="sxs-lookup"><span data-stu-id="858f1-202">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="858f1-203">Nel riquadro azioni, in **PIN**, fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="858f1-203">In the Action pane, under **PIN**, click **Reset**.</span></span>
    
<span data-ttu-id="858f1-204">Gli utenti riceveranno un messaggio di posta elettronica con il proprio PIN quando questi vengono attivati per conferenze audio o quando viene reimpostato il PIN.</span><span class="sxs-lookup"><span data-stu-id="858f1-204">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="858f1-205">Ma se è stata disabilitata automaticamente l'invio di messaggi di posta elettronica, non verrà inviato un messaggio di posta elettronica Reimpostazione PIN e sarà necessario inviare manualmente il PIN all'utente.</span><span class="sxs-lookup"><span data-stu-id="858f1-205">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="858f1-206">The PIN will only be shown once after it has been reset.</span><span class="sxs-lookup"><span data-stu-id="858f1-206">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="858f1-207">Dopo che viene visualizzata immediatamente dopo la reimpostazione, il PIN non verrà visualizzato più nella proprietà utente. in realtà, \* \* \* verranno visualizzati.</span><span class="sxs-lookup"><span data-stu-id="858f1-207">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span> 
  
<span data-ttu-id="858f1-208">Vedere [reimpostare il PIN per conferenze Audio](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="858f1-208">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
  
## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="858f1-209">Inviare un messaggio di posta elettronica con informazioni di audioconferenza a un utente</span><span class="sxs-lookup"><span data-stu-id="858f1-209">Send an email with Audio Conferencing information to a user</span></span>

<span data-ttu-id="858f1-210">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="858f1-210">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="858f1-211">Nel riquadro di spostamento sinistra fare clic su **utenti**e quindi selezionare l'utente dall'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="858f1-211">In the left navigation, click **Users**, and then select the user from the list of available users.</span></span>

2. <span data-ttu-id="858f1-212">Nella parte superiore della pagina, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="858f1-212">At the top of the page, click **Edit**.</span></span>

3. <span data-ttu-id="858f1-213">In **Servizi di conferenza Audio**, fare clic su **Invia le informazioni di conferenza nel messaggio di posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="858f1-213">Under **Audio Conferencing**, click **Send conference info in email**.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="858f1-214">A tale scopo, conferenze audio PIN non viene inviato all'utente.</span><span class="sxs-lookup"><span data-stu-id="858f1-214">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 

<span data-ttu-id="858f1-215">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="858f1-215">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>  

1. <span data-ttu-id="858f1-216">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="858f1-216">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="858f1-217">Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.</span><span class="sxs-lookup"><span data-stu-id="858f1-217">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="858f1-218">Fare clic su **utenti**e quindi selezionare l'utente che si desidera reimpostare il PIN per.</span><span class="sxs-lookup"><span data-stu-id="858f1-218">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>
    
4. <span data-ttu-id="858f1-219">Nel riquadro Azioni fai clic su **Invia informazioni sulla conferenza tramite posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="858f1-219">In the Action pane, click **Send conference info via email**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="858f1-220">A tale scopo, conferenze audio PIN non viene inviato all'utente.</span><span class="sxs-lookup"><span data-stu-id="858f1-220">When you do this, the audio conferencing PIN isn't sent to the user.</span></span> 
  
<span data-ttu-id="858f1-221">[Uso di Windows PowerShell](send-an-email-to-a-user-with-their-dial-in-information.md)</span><span class="sxs-lookup"><span data-stu-id="858f1-221">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
  
## <a name="setting-the-default-audio-conferencing-phone-number-for-meeting-organizers"></a><span data-ttu-id="858f1-222">Impostazione del numero di telefono audioconferenza predefinito per gli organizzatori delle riunioni</span><span class="sxs-lookup"><span data-stu-id="858f1-222">Setting the default audio conferencing phone number for meeting organizers</span></span>

 <span data-ttu-id="858f1-223">**Per impostare il numero di telefono di audioconferenza predefinito per gli organizzatori delle riunioni quando un utente si sta abilitando per le conferenze Audio**</span><span class="sxs-lookup"><span data-stu-id="858f1-223">**To set the default audio conferencing phone number for meeting organizers when you are enabling a user for Audio Conferencing**</span></span>
  
1. <span data-ttu-id="858f1-224">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="858f1-224">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="858f1-225">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="858f1-225">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="858f1-226">Nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **gli utenti**.</span><span class="sxs-lookup"><span data-stu-id="858f1-226">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="858f1-227">Selezionare l'utente che si desidera abilitare per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="858f1-227">Select the user that you want to enable for Audio Conferencing.</span></span>
    
4. <span data-ttu-id="858f1-228">Nel riquadro azioni, nella finestra delle proprietà dell'utente, fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="858f1-228">In the Action pane, in the user's properties, click **Edit**.</span></span>
    
5. <span data-ttu-id="858f1-229">Nella pagina **proprietà** sotto il **nome del Provider**, utilizzare l'elenco a discesa per selezionare il provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="858f1-229">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="858f1-230">Se si seleziona Microsoft come provider di servizi di conferenza audio, è possibile scegliere il numero di telefono di audioconferenza predefinito dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="858f1-230">If you select Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="858f1-231">Se si seleziona un'AUDIOCONFERENZA di terze parti come provider di servizi di conferenza audio, è necessario immettere manualmente le tariffe e, se necessario, il numero verde.</span><span class="sxs-lookup"><span data-stu-id="858f1-231">If you select a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span> <span data-ttu-id="858f1-232">Questi numeri di telefono sarà il numero di telefono predefinito.</span><span class="sxs-lookup"><span data-stu-id="858f1-232">These phone numbers will be the default phone number.</span></span>
    
    <span data-ttu-id="858f1-233">Il numero di telefono predefinito audioconferenze con accesso esterno di un utente è il numero visualizzato nella invito alla riunione quando si pianifica una riunione.</span><span class="sxs-lookup"><span data-stu-id="858f1-233">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
6. <span data-ttu-id="858f1-234">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="858f1-234">Click **Save**.</span></span> 
    
<span data-ttu-id="858f1-235">Vedere [impostare telefono numeri incluso nel invita](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="858f1-235">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
 <span data-ttu-id="858f1-236">**Per impostare il numero di telefono di audioconferenza predefinito per gli organizzatori delle riunioni dopo aver abilitato un utente per le conferenze audio**</span><span class="sxs-lookup"><span data-stu-id="858f1-236">**To set the default audio conferencing phone number for meeting organizers after you have enabled a user for audio conferencing**</span></span>
  
1. <span data-ttu-id="858f1-237">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="858f1-237">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="858f1-238">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="858f1-238">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="858f1-239">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **gli utenti**, selezionare l'utente desiderato e nella pagina azione fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="858f1-239">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Users**, select the user you want, and in the Action page, click **Edit**.</span></span>
    
4. <span data-ttu-id="858f1-240">Nella pagina **proprietà** sotto il **nome del Provider**, utilizzare l'elenco a discesa per selezionare il provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="858f1-240">On the **Properties** page, under **Provider name**, use the drop-down list to select the audio conferencing provider.</span></span>
    
  - <span data-ttu-id="858f1-241">Se l'utente utilizza Microsoft come provider di servizi di conferenza audio, è possibile scegliere il numero di telefono di audioconferenza predefinito dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="858f1-241">If the user uses Microsoft as the audio conferencing provider, you can choose the default audio conferencing phone number from the list.</span></span>  
    
  - <span data-ttu-id="858f1-242">Se l'utente viene utilizzata un'AUDIOCONFERENZA di terze parti come provider di servizi di conferenza audio, sarà necessario immettere manualmente le tariffe e, se necessario, il numero verde.</span><span class="sxs-lookup"><span data-stu-id="858f1-242">If the user uses a third-party ACP as the audio conferencing provider, you will need to manually enter the Toll and if required, the Toll-free phone number.</span></span>
    
    <span data-ttu-id="858f1-243">Il numero di telefono predefinito audioconferenze con accesso esterno di un utente è il numero visualizzato nella invito alla riunione quando si pianifica una riunione.</span><span class="sxs-lookup"><span data-stu-id="858f1-243">The default audio conferencing phone number of a user is the number that is shown on the meeting invite when they schedule a meeting.</span></span>
    
5. <span data-ttu-id="858f1-244">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="858f1-244">Click **Save**.</span></span> 
    
<span data-ttu-id="858f1-245">Vedere [impostare telefono numeri incluso nel invita](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="858f1-245">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>
  
## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="858f1-246">La scelta delle impostazioni di ponte conferenza</span><span class="sxs-lookup"><span data-stu-id="858f1-246">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="858f1-247">**Impostare l'esperienza di riunione quando i chiamanti di partecipare a una riunione**</span><span class="sxs-lookup"><span data-stu-id="858f1-247">**Set the meeting experience when callers join a meeting**</span></span>

 <span data-ttu-id="858f1-248">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="858f1-248">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="858f1-249">Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**.</span><span class="sxs-lookup"><span data-stu-id="858f1-249">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="858f1-250">Nella parte superiore della pagina **Ponti di conferenza** , fare clic su **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="858f1-250">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="858f1-251">Nel riquadro **Impostazioni Bridge** , abilitare o disabilitare **voce della riunione e chiudere le notifiche**.</span><span class="sxs-lookup"><span data-stu-id="858f1-251">In the **Bridge settings** pane, enable or disable **Meeting entry and exit notifications**.</span></span>

    <span data-ttu-id="858f1-252">Questa opzione è attivata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="858f1-252">This is enabled by default.</span></span> <span data-ttu-id="858f1-253">Se si disabilita questa opzione, gli utenti che già sono uniti alla riunione per impostazione predefinita non vengono informati quando un utente si unisce o abbandona la riunione.</span><span class="sxs-lookup"><span data-stu-id="858f1-253">If you disable this option, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

4. <span data-ttu-id="858f1-254">In **tipo di annunci di entrata/uscita**scegliere **toni** o **i nomi o numeri di telefono**.</span><span class="sxs-lookup"><span data-stu-id="858f1-254">Under **Entry/exit announcement type**, choose either **Tones** or **Names or phone numbers**.</span></span> 

    <span data-ttu-id="858f1-255">Se si sceglie **nomi o numeri di telefono**, è anche possibile scegliere di attivare o disattivare **i chiamanti Ask per registrare il proprio nome prima di partecipare alla riunione**.</span><span class="sxs-lookup"><span data-stu-id="858f1-255">If you choose **Names or phone numbers**, you can also choose to enable or disable **Ask callers to record their name before joining the meeting**.</span></span> 

1. <span data-ttu-id="858f1-256">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="858f1-256">Click **Save**.</span></span>

<span data-ttu-id="858f1-257">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="858f1-257">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="858f1-258">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="858f1-258">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="858f1-259">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="858f1-259">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="858f1-260">Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="858f1-260">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="858f1-261">Nella sezione **esperienza di partecipazione alle riunioni**, selezionare le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="858f1-261">Under **Meeting join experience**, select the following actions:</span></span>
    
  - <span data-ttu-id="858f1-262">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span><span class="sxs-lookup"><span data-stu-id="858f1-262">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="858f1-263">Se si deseleziona la casella di controllo, gli utenti che già sono uniti alla riunione per impostazione predefinita non vengono informati quando un utente si unisce o abbandona la riunione.</span><span class="sxs-lookup"><span data-stu-id="858f1-263">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>
    
    <span data-ttu-id="858f1-264">Ciò può essere impostata in base a una riunione per riunioni quando un utente partecipa a una riunione con un Skype per applicazioni aziendali o Microsoft Teams e cui modificare l'impostazione di **annuncio quando vengono inclusi o esclusi** dal menu riunione Skype o Microsoft Teams **le opzioni** del riunione.</span><span class="sxs-lookup"><span data-stu-id="858f1-264">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business or Microsoft Teams app and they modify the **Announce when people enter or leave** setting in the Skype Meeting or Microsoft Teams **Options** menu of the meeting.</span></span>
    
  - <span data-ttu-id="858f1-265">**Chiamanti ASK per registrare il proprio nome prima di partecipare alla riunione** Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="858f1-265">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="858f1-266">Se si deseleziona la casella di controllo, i chiamanti non verranno richiesto di registrare il proprio nome prima che partecipano a una riunione.</span><span class="sxs-lookup"><span data-stu-id="858f1-266">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>
    
5. <span data-ttu-id="858f1-267">Vedi **Modificare le impostazioni per un bridge per audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="858f1-267">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="858f1-268">Vedere [modificare le impostazioni per un ponte per conferenze Audio](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="858f1-268">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="858f1-269">**Impostare la lunghezza del PIN per le riunioni**</span><span class="sxs-lookup"><span data-stu-id="858f1-269">**Set the PIN length for meetings**</span></span>

 <span data-ttu-id="858f1-270">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="858f1-270">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="858f1-271">Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**.</span><span class="sxs-lookup"><span data-stu-id="858f1-271">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="858f1-272">Nella parte superiore della pagina **Ponti di conferenza** , fare clic su **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="858f1-272">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="858f1-273">Nel riquadro **Impostazioni Bridge** immettere il numero di cifre che si desidera utilizzare per il PIN nell'elenco **lunghezza del PIN** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="858f1-273">In the **Bridge settings** pane, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="858f1-274">Il codice PIN deve essere compreso tra 4 e 12 cifre.</span><span class="sxs-lookup"><span data-stu-id="858f1-274">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="858f1-275">The default is 5.</span><span class="sxs-lookup"><span data-stu-id="858f1-275">The default is 5.</span></span>

<span data-ttu-id="858f1-276">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="858f1-276">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="858f1-277">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="858f1-277">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="858f1-278">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="858f1-278">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="858f1-279">Nell' **Interfaccia di amministrazione di Skype for Business**, nella barra di spostamento sinistra, passa a **Servizi di conferenza telefonica con accesso esterno** > **Impostazioni bridge Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="858f1-279">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
4. <span data-ttu-id="858f1-280">In **protezione**, immettere il numero di cifre che si desidera utilizzare per il PIN nell'elenco **lunghezza del PIN** e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="858f1-280">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>
    
    <span data-ttu-id="858f1-281">Il codice PIN deve essere compreso tra 4 e 12 cifre.</span><span class="sxs-lookup"><span data-stu-id="858f1-281">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="858f1-282">The default is 5.</span><span class="sxs-lookup"><span data-stu-id="858f1-282">The default is 5.</span></span>
    
<span data-ttu-id="858f1-283">Vedere [modificare le impostazioni per un ponte per conferenze Audio](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="858f1-283">See [Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md).</span></span>
  
 <span data-ttu-id="858f1-284">**Attivare o disattivare la posta elettronica non verrà inviato agli utenti audio**</span><span class="sxs-lookup"><span data-stu-id="858f1-284">**Enable or disable email from being sent to audio users**</span></span>

 <span data-ttu-id="858f1-285">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="858f1-285">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="858f1-286">Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**.</span><span class="sxs-lookup"><span data-stu-id="858f1-286">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="858f1-287">Nella parte superiore della pagina **Ponti di conferenza** , fare clic su **Impostazioni Bridge**.</span><span class="sxs-lookup"><span data-stu-id="858f1-287">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="858f1-288">Nel riquadro **Impostazioni Bridge** , abilitare o disabilitare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="858f1-288">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="858f1-289">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="858f1-289">Click **Save**.</span></span> 
 
    <span data-ttu-id="858f1-290">Inoltre, è possibile inviare posta elettronica all'utente con le impostazioni di conferenza audio, quindi facendo clic su **Invia le informazioni di conferenza nel messaggio di posta elettronica**per le proprietà dell'utente per conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="858f1-290">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info in email**.</span></span>
    
    <span data-ttu-id="858f1-291">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="858f1-291">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

<span data-ttu-id="858f1-292">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="858f1-292">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 
  
1. <span data-ttu-id="858f1-293">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="858f1-293">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="858f1-294">Vai al **Centro di amministrazione di Office 365** > **Skype per le aziende** e nel riquadro di spostamento sinistra fare clic su **servizi di conferenza Audio**.</span><span class="sxs-lookup"><span data-stu-id="858f1-294">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>
    
3. <span data-ttu-id="858f1-295">Nella pagina **Impostazioni bridge Microsoft** , selezionare o deselezionare **automaticamente inviare messaggi di posta elettronica agli utenti se modificare le impostazioni di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="858f1-295">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>
    
4. <span data-ttu-id="858f1-296">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="858f1-296">Click **Save**.</span></span>
    
    <span data-ttu-id="858f1-297">Inoltre, è possibile inviare posta elettronica all'utente con le impostazioni di conferenza audio, quindi facendo clic su **Invia informazioni conferenza tramite posta elettronica**per le proprietà dell'utente per conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="858f1-297">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>
    
    <span data-ttu-id="858f1-298">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span><span class="sxs-lookup"><span data-stu-id="858f1-298">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>
    
    <span data-ttu-id="858f1-299">Visualizzare e impostare la lingua principale e le lingue secondarie in un bridge di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="858f1-299">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>
    
## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="858f1-300">Visualizzare e impostare il primario (impostazione predefinita) e lingue secondarie (alternative) su un ponte per conferenze audio</span><span class="sxs-lookup"><span data-stu-id="858f1-300">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>

 <span data-ttu-id="858f1-301">![i team-logo-30x30.png](../images/teams-logo-30x30.png) **utilizzando il team di Microsoft e Skype per Business Admin Center**</span><span class="sxs-lookup"><span data-stu-id="858f1-301">![teams-logo-30x30.png](../images/teams-logo-30x30.png) **Using the Microsoft Teams and Skype for Business Admin Center**</span></span>

1. <span data-ttu-id="858f1-302">Nel riquadro di spostamento sinistro, passare a **riunioni** > **Bridge conferenza**.</span><span class="sxs-lookup"><span data-stu-id="858f1-302">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="858f1-303">Selezionare un numero di telefono dall'elenco e fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="858f1-303">Select a phone number from the list and click **Edit**.</span></span>

3. <span data-ttu-id="858f1-304">Selezionare le lingue desiderate nella sezione **lingua predefinita** e le relative **lingue alternative (facoltative)**.</span><span class="sxs-lookup"><span data-stu-id="858f1-304">Choose the languages you want under **Default language** and **Alternate languages (optional)**.</span></span>

<span data-ttu-id="858f1-305">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="858f1-305">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span> 

1. <span data-ttu-id="858f1-306">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="858f1-306">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="858f1-307">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="858f1-307">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="858f1-308">Nel **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio**e quindi **bridge di Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="858f1-308">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>
    
4. <span data-ttu-id="858f1-309">Selezionare un numero di telefono dall'elenco, fare clic su **Imposta lingue** nel riquadro azioni e quindi nella pagina **gruppo** di lingue, fare clic sull'utilizzo nell'elenco **lingua principale** per visualizzare l'elenco completo delle lingue supportate.</span><span class="sxs-lookup"><span data-stu-id="858f1-309">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>
    
    <span data-ttu-id="858f1-310">È inoltre possibile impostare le lingue principale e secondarie supportate quando si seleziona Microsoft come provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="858f1-310">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="858f1-311">L'ordine selezionato negli elenchi è lo stesso ordine in cui verranno visualizzate lingue per i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="858f1-311">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>
    
<span data-ttu-id="858f1-312">Visualizzare i numeri di accesso esterno per i servizi l'audioconferenza</span><span class="sxs-lookup"><span data-stu-id="858f1-312">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png--see-audio-conferencing-dial-in-numbers"></a>![30x30.png di logo sfb](../images/sfb-logo-30x30.png)  <span data-ttu-id="858f1-314">Vedere audioconferenza numeri di accesso</span><span class="sxs-lookup"><span data-stu-id="858f1-314">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="858f1-315">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="858f1-315">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="858f1-316">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="858f1-316">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="858f1-317">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio** > **bridge di Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="858f1-317">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="858f1-318">È possibile:</span><span class="sxs-lookup"><span data-stu-id="858f1-318">Here you can:</span></span>
    
  - <span data-ttu-id="858f1-319">Visualizzare i numeri di telefono che sono specificati per Office 365 da utilizzare per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="858f1-319">View the phone numbers that are set by Office 365 to be used for Audio Conferencing.</span></span> 
    
  - <span data-ttu-id="858f1-320">Visualizzare il percorso e le lingue principale e secondarie che verranno utilizzate per l'operatore automatico di conferenze Audio.</span><span class="sxs-lookup"><span data-stu-id="858f1-320">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>
    
  - <span data-ttu-id="858f1-321">Selezionare il numero di telefono predefinito che verrà assegnato agli utenti quando vengono abilitati per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="858f1-321">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="858f1-322">Tuttavia, se viene modificato il numero di telefono predefinito di ponte per conferenze audio, non modifica il numero di telefono predefinito per gli utenti esistenti.</span><span class="sxs-lookup"><span data-stu-id="858f1-322">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>
    
<span data-ttu-id="858f1-323">È possibile accedere ai **servizi di conferenza Audio** > **utenti** e selezionare le proprietà dell'utente per modificare il valore predefinito dei numeri per un utente di scegliere un nuovo numero dall'elenco di numeri che sono disponibili all'interno dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="858f1-323">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>
  
<span data-ttu-id="858f1-324">[Visualizzare un elenco di numeri di conferenza Audio](see-a-list-of-audio-conferencing-numbers.md), vedere.</span><span class="sxs-lookup"><span data-stu-id="858f1-324">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>
  
## <a name="sfb-logo-30x30pngimagessfb-logo-30x30png-see-a-list-of-users-that-are-enabled"></a>![30x30.png di logo sfb](../images/sfb-logo-30x30.png) <span data-ttu-id="858f1-326">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="858f1-326">See a list of users that are enabled</span></span>

1. <span data-ttu-id="858f1-327">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="858f1-327">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="858f1-328">Passa all' **interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="858f1-328">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="858f1-329">Nella **Skype per interfaccia di amministrazione di Business**, nel riquadro di spostamento sinistro, passare a **conferenze Audio**> e quindi **utenti**.</span><span class="sxs-lookup"><span data-stu-id="858f1-329">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>
    
<span data-ttu-id="858f1-330">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="858f1-330">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="858f1-331">Sono disponibili diverse impostazioni per gestire le impostazioni a livello dell'organizzazione tramite Windows PowerShell. In questo modo puoi applicare con facilità tali impostazioni a tutti gli utenti. Ecco le impostazioni a livello dell'organizzazione:</span><span class="sxs-lookup"><span data-stu-id="858f1-331">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="858f1-332">Sono disponibili diverse impostazioni che è possibile gestire a livello di organizzazione tramite Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="858f1-332">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="858f1-333">In questo modo semplice applicare le impostazioni per tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="858f1-333">This makes it easy to apply settings to all of your users.</span></span> 
    
<span data-ttu-id="858f1-334">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="858f1-334">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="858f1-335">Di seguito sono le impostazioni a livello di organizzazione:</span><span class="sxs-lookup"><span data-stu-id="858f1-335">Here are the organization-level settings:</span></span> 
> 
- <span data-ttu-id="858f1-336">**Impostazione delle notifiche di ingresso/uscita** Il valore predefinito è _$true_.</span><span class="sxs-lookup"><span data-stu-id="858f1-336">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false 
  ```

- <span data-ttu-id="858f1-337">**L'impostazione di registrazione del nome** Il valore predefinito è _$true_.</span><span class="sxs-lookup"><span data-stu-id="858f1-337">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="858f1-338">**Impostazione della lunghezza PIN** Il valore predefinito è 5.</span><span class="sxs-lookup"><span data-stu-id="858f1-338">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="858f1-339">**Impostazione solo dial-in riunioni da un telefono** Predefinito _$false_.</span><span class="sxs-lookup"><span data-stu-id="858f1-339">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="858f1-340">**L'impostazione se si desidera inviare la posta elettronica agli utenti** Il valore predefinito è _$true_.</span><span class="sxs-lookup"><span data-stu-id="858f1-340">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="858f1-341">**L'impostazione se si desidera inviare posta elettronica da un account diverso** Il valore predefinito è _$false_.</span><span class="sxs-lookup"><span data-stu-id="858f1-341">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="858f1-342">**Impostazione dell'indirizzo di mittente nel messaggio di posta elettronica inviato agli utenti** Il valore predefinito è _$null_.</span><span class="sxs-lookup"><span data-stu-id="858f1-342">**Setting the From address on email that is sent to users** The default is _$null_.</span></span> 
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="858f1-343">**Se il nome visualizzato per il posta elettronica inviato agli utenti** Il valore predefinito è _$null_.</span><span class="sxs-lookup"><span data-stu-id="858f1-343">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="858f1-344">Per ulteriori informazioni su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="858f1-344">Want to know more about Windows PowerShell</span></span>   
- <span data-ttu-id="858f1-p125">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="858f1-p125">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="858f1-348">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="858f1-348">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [<span data-ttu-id="858f1-349">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="858f1-349">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- <span data-ttu-id="858f1-p126">Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="858f1-p126">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="858f1-352">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="858f1-352">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="858f1-353">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="858f1-353">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="858f1-354">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="858f1-354">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    <span data-ttu-id="858f1-p127">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="858f1-p127">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
    
## <a name="related-topics"></a><span data-ttu-id="858f1-357">See also</span><span class="sxs-lookup"><span data-stu-id="858f1-357">Related topics</span></span>

[<span data-ttu-id="858f1-358">Gestire le impostazioni di audioconferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="858f1-358">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


