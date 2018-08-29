---
title: Gestire le impostazioni di Audioconferenza per l'organizzazione in Skype for Business Online
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
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Consulta passi per Skype for Business Online per assegnare una licenza e un ID conferenza per un utente e molte altre impostazioni di conferenza telefonica. '
ms.openlocfilehash: d8fc38929e059d0c8fdaf0babec5f8b6fb72856a
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2018
ms.locfileid: "23255729"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="4c1ee-103">Gestire le impostazioni di Audioconferenza per l'organizzazione in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4c1ee-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="4c1ee-104">Se desideri gestire le impostazioni in Teama, consulta [gestire le impostazioni di Audioconferenze per l'organizzazione in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span><span class="sxs-lookup"><span data-stu-id="4c1ee-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="4c1ee-105">Potrebbe risultare più semplice poter visualizzare tutte le impostazioni di Audioconferenza per Skype for Business in un unico sito.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-105">It might be easier for you to see all of the dial-in conferencing settings in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="4c1ee-106">Assegnare una licenza di Audioconferenza</span><span class="sxs-lookup"><span data-stu-id="4c1ee-106">Assign an Audio Conferencing license to your users.</span></span>

> [!NOTE]
> <span data-ttu-id="4c1ee-107">Non è possibile assegnare licenze utilizzando la **interfaccia di amministrazione Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-107">You can't assign licenses using the **Skype for Business admin center**, you must use the Office 365 admin center.</span></span> <span data-ttu-id="4c1ee-108">È necessario utilizzare l'interfaccia di amministrazione di Office 365.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-108">You can't assign licenses using the Skype for Business admin center, you must use the Office 365 admin center.</span></span> <span data-ttu-id="4c1ee-109">Consulta [Assegnare licenze Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="4c1ee-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="4c1ee-110">**Assegnare una licenza per un utente**</span><span class="sxs-lookup"><span data-stu-id="4c1ee-110">**** To assign a license for a user</span></span>

1. <span data-ttu-id="4c1ee-111">Accedi a Office 365 con l'account aziendale o scolastico.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-111">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4c1ee-112">Nella barra di navigazione sinistra dell'**interfaccia di amministrazione di Office 365**, vai su **Utenti** > **Utenti attivi**, e seleziona l'utente nella lista di utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-112">In the left navigation of the Office 365 admin center, go to Users  Active users > and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4c1ee-113">Per assegnare licenze a un massimo di 20 utenti contemporaneamente, puoi ricorrere all'elenco a discesa **Selezionare una visualizzazione** e scegliere una delle opzioni oppure creare una visualizzazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="4c1ee-114">Quindi fai clic su **Modifica**, due volte su **Avanti**, seleziona la licenza e fai clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="4c1ee-115">Puoi anche assegnare licenze a più utenti con Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="4c1ee-116">Per istruzioni ed esempi di script per PowerShell, consulta [Assegnare licenze per Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="4c1ee-116">For for instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="4c1ee-117">Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="4c1ee-118">Nella pagina **Licenze per i prodotti**, attiva **Servizi di Audioconferenza** e quindi fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="4c1ee-119">Per ulteriori informazioni sulle licenze, consulta [Licenze per i componenti aggiuntivi di Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="4c1ee-119">For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="4c1ee-120">Dopo aver assegnato la licenza, Microsoft potrebbe non apparire inizialmente nell'elenco come provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-120">After you assign the license, Microsoft might not appear initially in the drop-down as a dial-in conferencing provider.</span></span> <span data-ttu-id="4c1ee-121">In questa eventualità, esegui la disconnessione dall'interfaccia di amministrazione di Office 365 oppure premi CTRL+F5 per aggiornare la finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-121">If this happens, either log out of the Office 365 admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="4c1ee-122">Attivare o disattivare i messaggi di posta elettronica inviati agli utenti di audioconferenze</span><span class="sxs-lookup"><span data-stu-id="4c1ee-122">Enable or disable emails from being sent to dial-in users</span></span>

<span data-ttu-id="4c1ee-123">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Tramite l'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="4c1ee-123">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) Assign a phone number to the user using the **Skype for Business admin center**</span></span>

1. <span data-ttu-id="4c1ee-124">Accedi a Office 365 con l'account aziendale o scolastico.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-124">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4c1ee-125">Vai su **Interfaccia di amministrazione di Office 365** > **Skype for Business** e sulla barra di navigazione sinistra fai clic su **Audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-125">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation click **Dial-in conferencing**.</span></span>

3. <span data-ttu-id="4c1ee-126">Nella pagina **Impostazioni ponte Microsoft**, seleziona o deseleziona **Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di audioconferenza vengono modificate**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="4c1ee-127">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-127">Click **Save**.</span></span>

    <span data-ttu-id="4c1ee-128">È anche possibile inviare messaggi di posta elettronica all'utente con le impostazioni di audioconferenza facendo clic su **Invia informazioni conferenza tramite posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-128">You can also send emails to the user with the dial-in conferencing settings, by going to the user's properties > **Dial-in conferencingSend conference info via email**.</span></span> <span data-ttu-id="4c1ee-129">L'ID e il numero di conferenza predefinito sono inclusi nell'invito alla riunione, ma non il PIN.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-129">The conference ID and default dial-in conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="4c1ee-130">Consulta [Inviare un messaggio di posta elettronica a un utente con le informazioni di Audioconferenza](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="4c1ee-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="4c1ee-131">**Tramite Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="4c1ee-131">**Using Windows PowerShell to manage Lync Online**</span></span>

- <span data-ttu-id="4c1ee-132">Puoi anche usare Windows PowerShell ed eseguire:</span><span class="sxs-lookup"><span data-stu-id="4c1ee-132">You can also use the Windows PowerShell and run:</span></span>

  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="4c1ee-133">Puoi usare il [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per la tua organizzazione, inclusa la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="4c1ee-134">Modificare le informazioni di contatto del mittente nei messaggi di posta elettronica inviato agli utenti</span><span class="sxs-lookup"><span data-stu-id="4c1ee-134">Change the senders contact information of email messages sent to users</span></span>

<span data-ttu-id="4c1ee-135">È possibile apportare modifiche al messaggio di posta elettronica inviato automaticamente agli utenti, tra cui l'indirizzo di posta elettronica e il nome visualizzato di informazioni di contatto del mittente.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-135">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="4c1ee-136">Per impostazione predefinita, il mittente sarà Office 365, ma puoi modificare l'indirizzo di posta elettronica e il nome visualizzato utilizzando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285).</span><span class="sxs-lookup"><span data-stu-id="4c1ee-136">By default, the sender of the emails will be from Office 365 but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) cmdlet.</span></span> <span data-ttu-id="4c1ee-137">Per apportare modifiche all'indirizzo di posta elettronica da cui viene inviato il messaggio agli utenti, procedi come segue:</span><span class="sxs-lookup"><span data-stu-id="4c1ee-137">To make changes to the email address that is sending the email to the users you must:</span></span>

- <span data-ttu-id="4c1ee-138">Inserisci l'indirizzo di posta elettronica nel parametro _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-138">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="4c1ee-139">Inserisci il nome di posta elettronica visualizzato nel parametro _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="4c1ee-140">Imposta il parametro _SendEmailOverride_ su _True_.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="4c1ee-141">Se desideri modificare le informazioni relative all'indirizzo di posta elettronica, devi verificare che i criteri di posta elettronica in ingresso dell'organizzazione consentano i messaggi in arrivo dall'indirizzo di posta elettronica personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="4c1ee-142">Se desideri modificare le informazioni dell'indirizzo di posta elettronica, devi assicurarti che le politiche interne di posta elettronica della tua organizzazione consentono i messaggi che arrivano da un indirizzo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="4c1ee-143">Puoi usare il [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) per gestire altre impostazioni per la tua organizzazione, inclusa la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=627285) to manage other settings for your organization including email.</span></span>

<span data-ttu-id="4c1ee-144">Consulta [Messaggi di posta elettronica che vengono inviati automaticamente agli utenti quando le loro impostazioni di Audioconferenza vengono modificate](emails-sent-to-users-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="4c1ee-144">See [Emails that are automatically sent to users when their dial-in conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="4c1ee-145">Reimpostare l'ID conferenza della riunione</span><span class="sxs-lookup"><span data-stu-id="4c1ee-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="4c1ee-146">Accedi a Office 365 con l'account aziendale o scolastico.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-146">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4c1ee-147">Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-147">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="4c1ee-148">Nella **Interfaccia di amministrazione di Skype for Business**, nel riquadro di navigazione sinistro, vai su **Audioconferenza** e nel riquadro Azioni alla voce **ID conferenza**, fai clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="4c1ee-149">Nella finestra **Reimpostare ID conferenza?**, fai clic su **Sì**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-149">In the ** Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="4c1ee-150">Un ID conferenza verrà creato automaticamente e un messaggio di posta elettronica verrà inviato all'utente con il nuovo ID conferenza se i messaggi di posta elettronica ai tuoi utenti sono abilitati.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-150">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="4c1ee-151">Questa impostazione è abilitata in modo predefinito</span><span class="sxs-lookup"><span data-stu-id="4c1ee-151">It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="4c1ee-152">Una volta creato un nuovo ID conferenza, il vecchio ID conferenza non potrà più essere utilizzato dai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-152">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="4c1ee-153">È necessario informare gli utenti di pianificare di nuovo gli inviti alle riunioni esistenti per assicurarsi che il nuovo ID conferenza venga aggiunto agli inviti.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="4c1ee-154">Gli utenti possono utilizzare lo strumento di migrazione delle riunioni di Skype for Business per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-154">The users can use Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="4c1ee-155">Per informazioni su come scaricare, installare ed eseguire lo strumento, vedere: [Strumento di aggiornamento delle riunioni per Skype for Business e Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business online, strumento di migrazione delle riunioni (64 bit)](https://go.microsoft.com/fwlink/?LinkID=626047)e [Skype for Business online, strumento di migrazione delle riunioni (32 bit)](https://www.microsoft.com/en-us/download/details.aspx?id=54079).</span><span class="sxs-lookup"><span data-stu-id="4c1ee-155">To see how to download, install and run the Lync Meeting Update Tool, see:> Meeting Update Tool for Skype for Business and Lync  Skype for Business Online, Meeting Migration Tool (64-bit)  Skype for Business Online, Meeting Migration Tool (32-bit)</span></span>

<span data-ttu-id="4c1ee-156">Consulta [Reimpostare l'ID conferenza per un utente](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="4c1ee-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="4c1ee-157">Reimpostare il PIN dell'organizzatore della conferenza</span><span class="sxs-lookup"><span data-stu-id="4c1ee-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="4c1ee-158">A ogni riunione che un utente pianifica viene assegnato un ID conferenza univoco.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-158">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="4c1ee-159">Benché un ID conferenza venga automaticamente creato e assegnato a un utente, può succedere che un utente non desideri utilizzarlo o voglia impostare un determinato numero o che non se lo ricordi o perda l'ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-159">Although a static conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number or if your users can't remember or have lost their conference ID, you can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span> <span data-ttu-id="4c1ee-160">È possibile utilizzare l'interfaccia di amministrazione di Skype for Business e Windows PowerShell per visualizzare, modificare e ripristinare gli ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="4c1ee-161">Accedi a Office 365 con l'account aziendale o scolastico.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-161">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4c1ee-162">Vai su **Interfaccia di amministrazione di Office 365** > **Skype for Business** e sulla barra di navigazione sinistra fai clic su **Audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-162">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation click **Dial-in conferencing**.</span></span>

3. <span data-ttu-id="4c1ee-163">Fai clic su **Utenti** e quindi seleziona l'utente a cui desideri reimpostare il PIN.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-163">Click on **Dial-in users**, select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="4c1ee-164">Nel riquadro Azioni, alla voce **PIN**, fai clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-164">In the Action pane, click **Reset PIN**.</span></span>

<span data-ttu-id="4c1ee-165">Gli utenti riceveranno un messaggio di posta elettronica con il nuovo PIN quando essi sono abilitati a entrare nella conferenza o quando il PIN viene reimpostato.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-165">Users will receive an email with their PIN when they're enabled for dial-in conferencing or when the PIN is reset.</span></span> <span data-ttu-id="4c1ee-166">Ma se hai disabilitato l'invio automatico di messaggi di posta elettronica, allora il messaggio di posta elettronica di reimpostazione del PIN non verrà inviato agli utenti e dovrai inviare il PIN manualmente.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-166">But if you have disabled automatically sending emails, then a PIN reset email won't be sent to a user and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="4c1ee-167">Il PIN verrà visualizzato solo una volta reimpostato.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-167">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="4c1ee-168">Una volta visualizzato dopo essere stato reimpostato, il PIN non verrà più visualizzato nelle proprietà dell'utente bensì apparirà come \*\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-168">Once it's displayed just after being reset, the PIN won't be shown anymore on the user properties and instead \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="4c1ee-169">Consulta [Reimpostare il PIN di Audioconferenza](reset-the-audio-conferencing-pin.md).</span><span class="sxs-lookup"><span data-stu-id="4c1ee-169">See [Reset the Audio Conferencing PIN for a user](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="4c1ee-170">Inviare un messaggio di posta elettronica con informazioni di Audioconferenza a un utente</span><span class="sxs-lookup"><span data-stu-id="4c1ee-170">Send an email to a user with their Audio Conferencing information</span></span>

1. <span data-ttu-id="4c1ee-171">Accedi a Office 365 con l'account aziendale o scolastico.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-171">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4c1ee-172">Vai su **interfaccia di amministrazione di Office 365** > **Skype for Business** e sulla barra di navigazione sinistra fai clic su **Audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-172">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation click **Dial-in conferencing**.</span></span>

3. <span data-ttu-id="4c1ee-173">Fai clic su **Utenti** e quindi seleziona l'utente a cui desideri reimpostare il PIN.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-173">Click on **Dial-in users**, select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="4c1ee-174">Nel riquadro Azioni fai clic su **Invia informazioni sulla conferenza tramite posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="4c1ee-175">Quando fai ciò, il PIN per accedere alla conferenza non viene inviato all'utente.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-175">When you do this, the dial-in conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="4c1ee-176">Consulta [Inviare un messaggio di posta elettronica a un utente con le informazioni di Audioconferenza](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="4c1ee-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="4c1ee-177">Impostare i numeri di telefono inclusi negli inviti</span><span class="sxs-lookup"><span data-stu-id="4c1ee-177">Set the phone numbers included on invites</span></span>

1. <span data-ttu-id="4c1ee-178">Accedi a Office 365 con l'account aziendale o scolastico.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-178">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4c1ee-179">Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-179">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="4c1ee-180">Nel riquadro di navigazione sinistro, vai su  **Audioconferenza** > **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-180">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="4c1ee-181">Seleziona l'utente che desideri abilitare per le Audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-181">Select the user that you want to enable for dial-in conferencing.</span></span>

4. <span data-ttu-id="4c1ee-182">Nel riquadro Azioni, è possibile impostare il **Numero a pagamento** e, se permesso, il **Numero verde**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="4c1ee-183">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-183">Click **Save**.</span></span>

<span data-ttu-id="4c1ee-184">Consulta [Impostare i numeri di telefono inclusi negli inviti](set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="4c1ee-184">[Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md)</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="4c1ee-185">La scelta delle impostazioni di ponte per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="4c1ee-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="4c1ee-186">**Impostare l'esperienza di riunione quando i chiamanti vi partecipano**</span><span class="sxs-lookup"><span data-stu-id="4c1ee-186">**** Set the meeting experience when callers join a meeting</span></span>


1. <span data-ttu-id="4c1ee-187">Accedi a Office 365 con l'account aziendale o scolastico.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-187">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4c1ee-188">Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-188">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="4c1ee-189">Nella **Interfaccia di amministrazione di Skype for Business**, nella barra di navigazione sinistra, vai su **Audioconferenza** > **Impostazioni ponte Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="4c1ee-190">Alla voce **esperienza di partecipazione alle riunioni**, seleziona le seguenti operazioni:</span><span class="sxs-lookup"><span data-stu-id="4c1ee-190">Under **Meeting join experience** select the following actions:</span></span>

  - <span data-ttu-id="4c1ee-191">**Abilita notifiche quando ci si unisce e si abbandona la riunione** Questa impostazione è selezionata in modo predefinito.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-191">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="4c1ee-192">Se si deseleziona la casella di controllo, gli utenti che già sono uniti alla riunione per impostazione predefinita non vengono informati quando un utente si unisce o abbandona la riunione.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-192">However if you uncheck it, users that have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

    <span data-ttu-id="4c1ee-193">Questo può essere impostato per ogni riunione quando un utente si unisce usando l'app Skype for Business e modifica l'impostazione **Annuncia quando qualcuno si unisce o abbandona** nelle menu delle **Opzioni** della riunione in Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business client and they modify the **Announce when people enter or leave** setting in the Skype Meeting Options menu of the meeting.</span></span>

  - <span data-ttu-id="4c1ee-194">**Chiedi agli utenti di registrare il proprio nome prima di partecipare alla riunione** Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-194">**Ask callers to record their name before joining the meeting** This is selected by default. However, if you uncheck it, callers won't be asked to record their name before they join a meeting.</span></span> <span data-ttu-id="4c1ee-195">Se si deseleziona la casella di controllo, ai chiamanti non verrà richiesto di registrare il proprio nome prima che partecipino a una riunione.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-195">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="4c1ee-196">Una volta fatti i tuoi cambiamenti, fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-196">After you make your changes, click **Save**.</span></span>

<span data-ttu-id="4c1ee-197">Consulta [Modificare le impostazioni per un ponte per Audioconferenza](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="4c1ee-197">[Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)</span></span>

 <span data-ttu-id="4c1ee-198">**Impostare la lunghezza del PIN per le riunioni**</span><span class="sxs-lookup"><span data-stu-id="4c1ee-198">**** Set the PIN length for meetings</span></span>

1. <span data-ttu-id="4c1ee-199">Accedi a Office 365 con l'account aziendale o scolastico.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-199">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4c1ee-200">Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-200">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="4c1ee-201">Nell'**Interfaccia di amministrazione di Skype for Business**, nella barra di navigazione sinistra, vai su **Audioconferenza** > **Impostazioni ponte Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="4c1ee-202">Alla voce **Protezione**, immetti il numero di cifre che si desidera utilizzare per il PIN nel campo **Lunghezza del PIN** e quindi fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-202">Under **Security**PIN length > enter the number of digits you want for the PIN and then click **Save**.</span></span>

    <span data-ttu-id="4c1ee-203">Il codice PIN deve essere compreso tra 4 e 12 cifre.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-203">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="4c1ee-204">Il numero di cifre predefinito è 5.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-204">The default is 5.</span></span>

<span data-ttu-id="4c1ee-205">Consulta [Modificare le impostazioni per un ponte per audioconferenze](change-the-settings-for-an-audio-conferencing-bridge.md).</span><span class="sxs-lookup"><span data-stu-id="4c1ee-205">[Change the settings for an Audio Conferencing bridge](change-the-settings-for-an-audio-conferencing-bridge.md)</span></span>

 <span data-ttu-id="4c1ee-206">**Abilitare o disabilitare l'invio di messaggi di posta elettronica agli utenti audio**</span><span class="sxs-lookup"><span data-stu-id="4c1ee-206">**** Enable or disable email from being sent to dial-in users</span></span>

1. <span data-ttu-id="4c1ee-207">Accedi a Office 365 con l'account aziendale o scolastico.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-207">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4c1ee-208">Vai su **interfaccia di amministrazione di Office 365** > **Skype for Business** e sulla barra di navigazione sinistra fai clic su **Audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-208">Go to the **Office 365 admin center** > **Skype for Business** and in the left navigation click **Dial-in conferencing**.</span></span>

3. <span data-ttu-id="4c1ee-209">Nella pagina **Impostazioni ponte Microsoft**, seleziona o deseleziona **Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di audioconferenza vengono modificate**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="4c1ee-210">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-210">Click **Save**.</span></span>

    <span data-ttu-id="4c1ee-211">È anche possibile inviare messaggi di posta elettronica all'utente con le impostazioni di audioconferenza facendo clic su **Invia informazioni conferenza tramite posta elettronica**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-211">You can also send email to the user with the dial-in conferencing settings, by going to the user's properties > **Dial-in conferencingSend conference info via email**.</span></span>

    <span data-ttu-id="4c1ee-212">Facendo ciò, verrà inviato  un messaggio di posta elettronica contenente solo il numero di telefono e l'ID conferenza, ma il PIN non verrà incluso.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="4c1ee-213">Consulta [Inviare un messaggio di posta elettronica a un utente con le informazioni di Audioconferenza](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="4c1ee-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="4c1ee-214">Visualizzare e impostare la lingua principale (impostazione predefinita) e secondaria (alternativa) su un ponte per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="4c1ee-214">See and set the primary and secondary languages on a dial-in conferencing bridge</span></span>


1. <span data-ttu-id="4c1ee-215">Accedi a Office 365 con l'account aziendale o scolastico.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-215">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4c1ee-216">Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-216">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="4c1ee-217">|||UNTRANSLATED_CONTENT_START|||In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.|||UNTRANSLATED_CONTENT_END|||</span><span class="sxs-lookup"><span data-stu-id="4c1ee-217">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing** and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="4c1ee-218">Seleziona un numero di telefono dall'elenco, fai clic su **Imposta lingue** nel riquadro Azioni e quindi nella pagina **Imposta lingue**, fai clic sull'elenco **Lingua principale** per visualizzare l'elenco completo delle lingue supportate.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-218">In the Action pane, select the phone number from the list, click **Set languages** and then on the **Set languages** page, click the drop-down under **Primary language** to view the complete list of supported languages.</span></span>

    <span data-ttu-id="4c1ee-219">Puoi anche impostare la lingua principale e secondaria supportate quando selezioni Microsoft come fornitore della conferenza.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-219">You can also set the primary and secondary languages that are supported when you select Microsoft as the dial-in conferencing provider.</span></span> <span data-ttu-id="4c1ee-220">L'ordine selezionato negli elenchi è lo stesso ordine in cui verranno visualizzate le lingue per i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-220">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="4c1ee-221">Consulta [Impostare lingue di operatore automatico per Audioconferenza](set-auto-attendant-languages-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="4c1ee-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="4c1ee-222">Vedere numeri di accesso audioconferenza</span><span class="sxs-lookup"><span data-stu-id="4c1ee-222">See dial-in conferencing dial-in numbers</span></span>

1. <span data-ttu-id="4c1ee-223">Accedi a Office 365 con l'account aziendale o scolastico.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-223">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4c1ee-224">Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-224">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="4c1ee-225">Nell'**Interfaccia di amministrazione di Skype for Business**, nella barra di navigazione sinistra, vai su **Audioconferenza** > **Ponte Microsoft**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-225">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span> <span data-ttu-id="4c1ee-226">Qui puoi:</span><span class="sxs-lookup"><span data-stu-id="4c1ee-226">Here you can:</span></span>

  - <span data-ttu-id="4c1ee-227">Visualizzare i numeri di telefono che sono specificati per Office 365 da utilizzare per le Audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-227">You can view the phone numbers that are set by Office 365 to be used for dial-in conferencing.</span></span>

  - <span data-ttu-id="4c1ee-228">Visualizzare il percorso e le lingue principale e secondaria che verranno utilizzate per l'operatore automatico di Audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-228">You can also view the location, and the primary and secondary languages that will be used by the dial-in conferencing auto attendant.</span></span>

  - <span data-ttu-id="4c1ee-229">Selezionare il numero di telefono predefinito che verrà assegnato agli utenti quando vengono abilitati per le Audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-229">You can select the dial-in conferencing default phone number that will be given to users when they are enabled for dial-in conferencing.</span></span> <span data-ttu-id="4c1ee-230">Ad ogni modo, se il numero telefonico predefinito per il ponte per audioconferenza viene modificato, il numero telefonico predefinito per gli utenti esistenti non verrà modificato.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-230">However, if the default phone number of the dial-in conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="4c1ee-231">Puoi andare su **Audioconferenza** > **Utenti** e selezionare le proprietà dell'utente per modificare il numero predefinito per un utente scegliendo un nuovo numero dall'elenco di numeri disponibili nella tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-231">You can go to **Dial-in conferencing** > **Dial-in users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="4c1ee-232">Consulta [Consultare un elenco di numeri di Audioconferenza](see-a-list-of-audio-conferencing-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="4c1ee-232">[See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md)</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="4c1ee-233">Vedere un elenco di utenti abilitati</span><span class="sxs-lookup"><span data-stu-id="4c1ee-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="4c1ee-234">Accedi a Office 365 con l'account aziendale o scolastico.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-234">Sign in to Office 365 with your work or school account.</span></span>

2. <span data-ttu-id="4c1ee-235">Passa all'**Interfaccia di amministrazione di Office 365** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-235">Go to the **Office 365 admin center** > **Skype for Business**.</span></span>

3. <span data-ttu-id="4c1ee-236">Nella **Interfaccia di amministrazione di Skype for Business**, nella barra di navigazione sinistra, vai su **Audioconferenza** e poi **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-236">In the **Skype for Business admin center**, in the left navigation go to **Dial-in conferencing**> and then **Dial-in users**.</span></span>

<span data-ttu-id="4c1ee-237">Consulta [Vedere un elenco di utenti abilitati per Audioconferenza](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="4c1ee-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="4c1ee-238">Vuoi sapere come gestire Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="4c1ee-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="4c1ee-239">Ci sono diverse impostazioni che puoi gestire a livello di organizzazione utilizzando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-239">There are several settings that you can manage settings at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="4c1ee-240">In questo modo puoi applicare facilmente le impostazioni a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-240">This makes it easy to make these settings and have them apply to all of your users.</span></span>

<span data-ttu-id="4c1ee-241">Per ottenere ulteriore aiuto su ogni cmdlet, consulta [Cmdlet di Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=627324).</span><span class="sxs-lookup"><span data-stu-id="4c1ee-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](https://go.microsoft.com/fwlink/?LinkId=627324).</span></span>

<span data-ttu-id="4c1ee-242">Di seguito trovi le impostazioni a livello di organizzazione:</span><span class="sxs-lookup"><span data-stu-id="4c1ee-242">Here are the organization level settings:</span></span>

- <span data-ttu-id="4c1ee-243">**Impostazione delle notifiche di ingresso/uscita** Il valore predefinito è _$true_.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="4c1ee-244">**Impostazione di registrazione del nome** Il valore predefinito è _$true_.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-244">**Setting name recording** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="4c1ee-245">**Impostazione della lunghezza del PIN** Il valore predefinito è 5.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-245">**Setting the PIN length** The default is 5.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="4c1ee-246">**Impostazione solo partecipazione a riunioni da un telefono** Il valore predefinito è _$false_.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="4c1ee-247">**Impostazione se si desidera inviare messaggi di posta elettronica agli utenti** Il valore predefinito è _$true_.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="4c1ee-248">**Impostazione se si desidera inviare posta elettronica da un account diverso** Il valore predefinito è _$false_.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="4c1ee-249">**Impostazione dell'indirizzo di mittente nel messaggio di posta elettronica inviato agli utenti** Il valore predefinito è _$null_.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="4c1ee-250">**Impostazione del nome visualizzato per il messaggio di posta elettronica inviato agli utenti** Il valore predefinito è _$null_.</span><span class="sxs-lookup"><span data-stu-id="4c1ee-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

 ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="4c1ee-251">Per saperne di più su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c1ee-251">Want to know more about Windows PowerShell?</span></span>
- <span data-ttu-id="4c1ee-p119">Windows PowerShell riguarda la gestione degli utenti e le azioni che sono autorizzati o meno a eseguire. Con Windows PowerShell puoi gestire Office 365 tramite un unico punto di amministrazione, che ti agevola il lavoro quotidiano quando hai molte attività da svolgere. Per iniziare a usare Windows PowerShell, vedi i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="4c1ee-p119">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="4c1ee-255">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="4c1ee-255">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [<span data-ttu-id="4c1ee-256">Modi migliori per gestire Office 365 con Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4c1ee-256">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)

- <span data-ttu-id="4c1ee-p120">Rispetto all'utilizzo dell'interfaccia di amministrazione di Office 365, Windows PowerShell presenta molti vantaggi in termini di rapidità, semplicità e produttività, ad esempio quando modifichi contemporaneamente le impostazioni di molti utenti. Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="4c1ee-p120">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center, such as when you are making settings changes for many users at one time. Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="4c1ee-259">Introduzione a Windows Powershell e Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4c1ee-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)

  - [<span data-ttu-id="4c1ee-260">Uso di Windows PowerShell per gestire Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4c1ee-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)

  - [<span data-ttu-id="4c1ee-261">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4c1ee-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)

    <span data-ttu-id="4c1ee-p121">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="4c1ee-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="4c1ee-264">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="4c1ee-264">Related topics</span></span>

[<span data-ttu-id="4c1ee-265">Gestire le impostazioni di Audioconferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="4c1ee-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)


