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
description: 'Consulta i passaggi di Skype for Business Online per assegnare una licenza di conferenza telefonica con accesso esterno e un ID conferenza a un utente e molte altre impostazioni per i servizi di conferenza telefonica con accesso esterno. '
ms.openlocfilehash: eb0212bcd7c03fac619efa2749a8308097f75505
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51114232"
---
# <a name="manage-the-audio-conferencing-settings-for-my-organization-in-skype-for-business-online"></a><span data-ttu-id="474e2-103">Gestire le impostazioni di Audioconferenza per l'organizzazione in Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="474e2-103">Manage the Audio Conferencing settings for my organization in Skype for Business Online</span></span>

> [!NOTE]
> <span data-ttu-id="474e2-104">Se desideri gestire le impostazioni in Teama, consulta [gestire le impostazioni di Audioconferenze per l'organizzazione in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span><span class="sxs-lookup"><span data-stu-id="474e2-104">If you want to manage these settings in Teams, see [Manage the Audio Conferencing settings for my organization in Microsoft Teams](/MicrosoftTeams/manage-the-audio-conferencing-settings-for-my-organization-in-teams).</span></span>

<span data-ttu-id="474e2-105">Potrebbe essere più facile visualizzare tutte le impostazioni di audioconferenza per Skype for Business in un'unica posizione.</span><span class="sxs-lookup"><span data-stu-id="474e2-105">It might be easier for you to see all of the audio conferencing settings for Skype for Business in one place.</span></span>


## <a name="assign-an-audio-conferencing-license"></a><span data-ttu-id="474e2-106">Assegnare una licenza di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="474e2-106">Assign an Audio Conferencing license</span></span>

> [!NOTE]
> <span data-ttu-id="474e2-107">Non è possibile assegnare licenze tramite **l'interfaccia di amministrazione di Skype for Business.**</span><span class="sxs-lookup"><span data-stu-id="474e2-107">You can't assign licenses using the **Skype for Business admin center**.</span></span> <span data-ttu-id="474e2-108">È necessario usare l'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="474e2-108">You must use the Microsoft 365 admin center.</span></span> <span data-ttu-id="474e2-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="474e2-109">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="474e2-110">**Per assegnare una licenza per un utente**</span><span class="sxs-lookup"><span data-stu-id="474e2-110">**To assign a license for a user**</span></span>

1. <span data-ttu-id="474e2-111">Accedere con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="474e2-111">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="474e2-112">Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione passare a **Utenti** utenti attivi e quindi selezionare l'utente o gli utenti  >  nell'elenco degli utenti disponibili.</span><span class="sxs-lookup"><span data-stu-id="474e2-112">In the left navigation of the admin center, go to **Users** > **Active users**, and then select the user or users from the list of available users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="474e2-113">Per assegnare licenze a un massimo di 20 utenti contemporaneamente, puoi ricorrere all'elenco a discesa **Selezionare una visualizzazione** e scegliere una delle opzioni oppure creare una visualizzazione personalizzata.</span><span class="sxs-lookup"><span data-stu-id="474e2-113">If you are assigning licenses to up to 20 users at the same time, you can use the **Select a view** drop-down then choose one of the options or create your own view.</span></span> <span data-ttu-id="474e2-114">Quindi fai clic su **Modifica**, due volte su **Avanti**, seleziona la licenza e fai clic su **Invia**.</span><span class="sxs-lookup"><span data-stu-id="474e2-114">Then click **Edit**, **Next** twice then select the license and click **Submit**.</span></span> <span data-ttu-id="474e2-115">Puoi anche assegnare licenze a più utenti con Windows Powershell.</span><span class="sxs-lookup"><span data-stu-id="474e2-115">You can also assign licenses to multiple users by using Windows Powershell.</span></span> <span data-ttu-id="474e2-116">Per istruzioni e script di Esempio di PowerShell, vedere [Assegnare licenze di Skype for Business.](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)</span><span class="sxs-lookup"><span data-stu-id="474e2-116">For instructions and sample PowerShell scripts, see [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

3. <span data-ttu-id="474e2-117">Nel riquadro Azioni, in **Licenze prodotti**, fai clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="474e2-117">In the Action pane under **Product licenses**, click **Edit**.</span></span>

4. <span data-ttu-id="474e2-118">Nella pagina **Licenze per i prodotti**, attiva **Servizi di Audioconferenza** e quindi fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="474e2-118">On the **Product Licenses** page, turn on **Audio Conferencing** and then click **Save**.</span></span> <span data-ttu-id="474e2-119">Per ulteriori informazioni sulle licenze, consulta [Licenze per i componenti aggiuntivi Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="474e2-119">For more on licensing, see [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

> [!NOTE]
> <span data-ttu-id="474e2-120">Dopo aver assegnato la licenza, Microsoft potrebbe non comparire inizialmente nell'elenco come provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="474e2-120">After you assign the license, Microsoft might not appear initially in the list as an audio conferencing provider.</span></span> <span data-ttu-id="474e2-121">In questo caso, disconnettersi dall'interfaccia di amministrazione o premere CTRL+F5 per aggiornare la finestra del browser.</span><span class="sxs-lookup"><span data-stu-id="474e2-121">If this happens, either log out of the admin center or press CTRL+F5 to refresh the browser window.</span></span>

## <a name="enable-or-disable-emails-sent-to-audio-conferencing-users"></a><span data-ttu-id="474e2-122">Abilitare o disabilitare i messaggi di posta elettronica inviati agli utenti di servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="474e2-122">Enable or disable emails sent to audio conferencing users</span></span>

<span data-ttu-id="474e2-123">![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="474e2-123">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

1. <span data-ttu-id="474e2-124">Accedere con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="474e2-124">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="474e2-125">Passare all'interfaccia di amministrazione > **Skype for Business** e nel riquadro di spostamento sinistro fare clic su **Audioconferenza.**</span><span class="sxs-lookup"><span data-stu-id="474e2-125">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="474e2-126">Nella pagina **Impostazioni ponte Microsoft**, seleziona o deseleziona **Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di audioconferenza vengono modificate**.</span><span class="sxs-lookup"><span data-stu-id="474e2-126">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="474e2-127">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="474e2-127">Click **Save**.</span></span>

    <span data-ttu-id="474e2-128">È anche possibile inviare messaggi di posta elettronica all'utente con le impostazioni di audioconferenza passando alle proprietà dei servizi di audioconferenza dell'utente e facendo clic su Invia informazioni conferenza **tramite posta elettronica.**</span><span class="sxs-lookup"><span data-stu-id="474e2-128">You can also send emails to the user with the audio conferencing settings by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span> <span data-ttu-id="474e2-129">L'ID conferenza e il numero di telefono predefinito per i servizi di audioconferenza sono inclusi nell'invito alla riunione, ma non nel PIN.</span><span class="sxs-lookup"><span data-stu-id="474e2-129">The conference ID and default audio conferencing phone number is included on the meeting invite but not the PIN.</span></span>

    <span data-ttu-id="474e2-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="474e2-130">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

<span data-ttu-id="474e2-131">**Uso di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="474e2-131">**Using Windows PowerShell**</span></span>

- <span data-ttu-id="474e2-132">You can also use the Windows PowerShell and run:</span><span class="sxs-lookup"><span data-stu-id="474e2-132">You can also use the Windows PowerShell and run:</span></span>

  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

    <span data-ttu-id="474e2-133">È possibile usare [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) per gestire altre impostazioni per l'organizzazione, tra cui la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="474e2-133">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) to manage other settings for your organization, including email.</span></span>

## <a name="change-the-senders-contact-information-in-email-messages-sent-to-users"></a><span data-ttu-id="474e2-134">Modificare le informazioni di contatto del mittente nei messaggi di posta elettronica inviati agli utenti</span><span class="sxs-lookup"><span data-stu-id="474e2-134">Change the sender's contact information in email messages sent to users</span></span>

<span data-ttu-id="474e2-135">È possibile apportare modifiche al messaggio di posta elettronica inviato automaticamente agli utenti, tra cui l'indirizzo di posta elettronica e il nome visualizzato di informazioni di contatto del mittente.</span><span class="sxs-lookup"><span data-stu-id="474e2-135">You can make changes to the email that is automatically sent to your users, including the actual email address and the display name of the sender's contact information.</span></span> <span data-ttu-id="474e2-136">Per impostazione predefinita, il mittente dei messaggi di posta elettronica è Microsoft 365 o Office 365, ma è possibile modificare l'indirizzo di posta elettronica e il nome visualizzato usando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="474e2-136">By default, the sender of the emails is Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet.</span></span> <span data-ttu-id="474e2-137">Per apportare modifiche all'indirizzo di posta elettronica che invia il messaggio agli utenti, è necessario:</span><span class="sxs-lookup"><span data-stu-id="474e2-137">To make changes to the email address that is sending the email to the users, you must:</span></span>

- <span data-ttu-id="474e2-138">Immettere l'indirizzo di posta elettronica nel _parametro SendEmailFromAddress._</span><span class="sxs-lookup"><span data-stu-id="474e2-138">Enter the email address in the _SendEmailFromAddress_ parameter.</span></span>

- <span data-ttu-id="474e2-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span><span class="sxs-lookup"><span data-stu-id="474e2-139">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>

- <span data-ttu-id="474e2-140">Imposta il parametro _SendEmailOverride_ su _True_.</span><span class="sxs-lookup"><span data-stu-id="474e2-140">Set the _SendEmailOverride_ parameter to _True_.</span></span>

<span data-ttu-id="474e2-141">Se desideri modificare le informazioni relative all'indirizzo di posta elettronica, devi verificare che i criteri di posta elettronica in ingresso dell'organizzazione consentano i messaggi in arrivo dall'indirizzo di posta elettronica personalizzato.</span><span class="sxs-lookup"><span data-stu-id="474e2-141">You can make changes to the email sent to users, such as the email address that the email is sent from or the display name for the email by running:</span></span>

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -SendEmailOverride $true -SendEmailFromAddress amos.marble@contoso.com -SendEmailFromDisplayName "Amos Marble"
```

<span data-ttu-id="474e2-142">Se desideri modificare le informazioni dell'indirizzo di posta elettronica, devi assicurarti che le politiche interne di posta elettronica della tua organizzazione consentono i messaggi che arrivano da un indirizzo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="474e2-142">If you want to change the email address information, you need to make sure that the inbound email policies of your organization allow emails that come from the custom email address.</span></span>

<span data-ttu-id="474e2-143">È possibile usare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) per gestire altre impostazioni per l'organizzazione, tra cui la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="474e2-143">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings?view=skype-ps) cmdlet to manage other settings for your organization, including email.</span></span>

<span data-ttu-id="474e2-144">Vedere [Messaggi di posta elettronica inviati automaticamente agli utenti quando cambiano le impostazioni di audioconferenza.](emails-sent-to-users-when-their-settings-change.md)</span><span class="sxs-lookup"><span data-stu-id="474e2-144">See [Emails that are automatically sent to users when their Audio Conferencing settings change](emails-sent-to-users-when-their-settings-change.md).</span></span>

## <a name="reset-the-meeting-conference-id"></a><span data-ttu-id="474e2-145">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="474e2-145">Reset the meeting conference ID</span></span>

1. <span data-ttu-id="474e2-146">Accedere con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="474e2-146">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="474e2-147">Passare all'interfaccia di amministrazione > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="474e2-147">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="474e2-148">Nella **Interfaccia di amministrazione di Skype for Business**, nel riquadro di navigazione sinistro, vai su **Audioconferenza** e nel riquadro Azioni alla voce **ID conferenza**, fai clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="474e2-148">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and in the Action pane under **Conference ID**, click **Reset**.</span></span>

4. <span data-ttu-id="474e2-149">Nella finestra **Reimposta ID conferenza?** fare clic su **Sì.**</span><span class="sxs-lookup"><span data-stu-id="474e2-149">In the **Reset conference ID?** window, click **Yes**.</span></span> <span data-ttu-id="474e2-150">Un ID conferenza verrà creato automaticamente e un messaggio di posta elettronica verrà inviato all'utente con il nuovo ID conferenza se i messaggi di posta elettronica ai tuoi utenti sono abilitati.</span><span class="sxs-lookup"><span data-stu-id="474e2-150">A conference ID will be automatically created and an email sent to the user with the new conference ID if sending email to your users is enabled.</span></span> <span data-ttu-id="474e2-151">Questa impostazione è abilitata in modo predefinito</span><span class="sxs-lookup"><span data-stu-id="474e2-151">It's enabled by default.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="474e2-152">Una volta creato un nuovo ID conferenza, il vecchio ID conferenza non potrà più essere utilizzato dai chiamanti.</span><span class="sxs-lookup"><span data-stu-id="474e2-152">After a new conference ID is created, the old conference ID can't be used by callers.</span></span> <span data-ttu-id="474e2-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span><span class="sxs-lookup"><span data-stu-id="474e2-153">You should notify users to reschedule their existing meeting invites to make sure the new conference ID is added to the invitations.</span></span> <span data-ttu-id="474e2-154">Gli utenti possono usare lo strumento di migrazione delle riunioni Skype for Business per aggiornare le riunioni esistenti.</span><span class="sxs-lookup"><span data-stu-id="474e2-154">The users can use the Skype for Business Meeting Migration Tool to update their existing meetings.</span></span> <span data-ttu-id="474e2-155">Per informazioni su come scaricare, installare ed eseguire lo strumento di aggiornamento delle riunioni Di Skype for Business, vedere: Strumento di aggiornamento delle riunioni per [Skype for Business e Lync,](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4)Skype for Business Online, Strumento di migrazione delle riunioni [(64 bit)](https://go.microsoft.com/fwlink/?LinkID=626047)e Skype for Business online, Strumento di migrazione delle riunioni [(32 bit).](https://www.microsoft.com/download/details.aspx?id=54079)</span><span class="sxs-lookup"><span data-stu-id="474e2-155">To see how to download, install, and run the Skype for Business Meeting Update Tool, see: [Meeting Update Tool for Skype for Business and Lync](https://support.office.com/article/2b525fe6-ed0f-4331-b533-c31546fcf4d4), [Skype for Business Online, Meeting Migration Tool (64-bit)](https://go.microsoft.com/fwlink/?LinkID=626047), and  [Skype for Business Online, Meeting Migration Tool (32-bit)](https://www.microsoft.com/download/details.aspx?id=54079).</span></span>

<span data-ttu-id="474e2-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="474e2-156">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>

## <a name="reset-a-conference-organizers-pin"></a><span data-ttu-id="474e2-157">Reset a conference organizer's PIN</span><span class="sxs-lookup"><span data-stu-id="474e2-157">Reset a conference organizer's PIN</span></span>

<span data-ttu-id="474e2-158">A ogni riunione che un utente pianifica viene assegnato un ID conferenza univoco.</span><span class="sxs-lookup"><span data-stu-id="474e2-158">Each meeting that a user schedules will get assigned a unique conference ID.</span></span> <span data-ttu-id="474e2-159">Anche se un ID conferenza verrà creato e assegnato automaticamente a un utente, a volte un utente non vuole usarlo e si vuole impostarlo su un determinato numero oppure gli utenti non ricordano o non hanno perso l'ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="474e2-159">Although a conference ID will be automatically created and assigned to a user, there may be times when a user doesn't want to use this one and you want to set it to a certain number, or your users can't remember or have lost their conference ID.</span></span> <span data-ttu-id="474e2-160">È possibile utilizzare l'interfaccia di amministrazione di Skype for Business e Windows PowerShell per visualizzare, modificare e ripristinare gli ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="474e2-160">You can use the Skype for Business admin center and Windows PowerShell to view, change, and reset their conference ID.</span></span>


1. <span data-ttu-id="474e2-161">Accedere con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="474e2-161">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="474e2-162">Passare all'interfaccia di amministrazione > **Skype for Business** e nel riquadro di spostamento sinistro fare clic su **Audioconferenza.**</span><span class="sxs-lookup"><span data-stu-id="474e2-162">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="474e2-163">Fare **clic su** Utenti e quindi selezionare l'utente per cui si vuole reimpostare il PIN.</span><span class="sxs-lookup"><span data-stu-id="474e2-163">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="474e2-164">Nel riquadro Azioni, in **PIN,** fare clic su **Reimposta**.</span><span class="sxs-lookup"><span data-stu-id="474e2-164">In the Action pane, under **PIN**, click **Reset**.</span></span>

<span data-ttu-id="474e2-165">Gli utenti riceveranno un messaggio di posta elettronica con il PIN quando sono abilitati per le audioconferenze o quando il PIN viene reimpostato.</span><span class="sxs-lookup"><span data-stu-id="474e2-165">Users will receive an email with their PIN when they're enabled for audio conferencing or when the PIN is reset.</span></span> <span data-ttu-id="474e2-166">Se però l'invio automatico dei messaggi di posta elettronica è stato disabilitato, non verrà inviato un messaggio di posta elettronica di reimpostazione del PIN e sarà necessario inviare manualmente il PIN all'utente.</span><span class="sxs-lookup"><span data-stu-id="474e2-166">But if you have disabled automatically sending emails, a PIN reset email won't be sent and you will have to manually send the PIN to the user.</span></span> <span data-ttu-id="474e2-167">The PIN will only be shown once after it has been reset.</span><span class="sxs-lookup"><span data-stu-id="474e2-167">The PIN will only be shown once after it has been reset.</span></span> <span data-ttu-id="474e2-168">Dopo essere stato visualizzato subito dopo la reimpostazione, il PIN non verrà più visualizzato nelle proprietà dell'utente. verrà invece visualizzato \*\*\*\*\*\*.</span><span class="sxs-lookup"><span data-stu-id="474e2-168">After it's displayed just after being reset, the PIN won't be shown anymore on the user properties; instead, \*\*\*\*\* will be shown.</span></span>

<span data-ttu-id="474e2-169">Vedere [Reimpostare il PIN dei servizi di audioconferenza.](reset-the-audio-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="474e2-169">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>

## <a name="send-an-email-with-audio-conferencing-information-to-a-user"></a><span data-ttu-id="474e2-170">Inviare un messaggio di posta elettronica con informazioni sui servizi di audioconferenza a un utente</span><span class="sxs-lookup"><span data-stu-id="474e2-170">Send an email with Audio Conferencing information to a user</span></span>

1. <span data-ttu-id="474e2-171">Accedere con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="474e2-171">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="474e2-172">Passare all'interfaccia di amministrazione > **Skype for Business** e nel riquadro di spostamento sinistro fare clic su **Audioconferenza.**</span><span class="sxs-lookup"><span data-stu-id="474e2-172">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="474e2-173">Fare **clic su** Utenti e quindi selezionare l'utente per cui si vuole reimpostare il PIN.</span><span class="sxs-lookup"><span data-stu-id="474e2-173">Click **Users**, and then select the user that you want to reset the PIN for.</span></span>

4. <span data-ttu-id="474e2-174">In the Action pane, click **Send conference info via email**.</span><span class="sxs-lookup"><span data-stu-id="474e2-174">In the Action pane, click **Send conference info via email**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="474e2-175">In questo caso, il PIN dei servizi di audioconferenza non viene inviato all'utente.</span><span class="sxs-lookup"><span data-stu-id="474e2-175">When you do this, the audio conferencing PIN isn't sent to the user.</span></span>

<span data-ttu-id="474e2-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="474e2-176">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="setting-the-phone-numbers-included-on-invites"></a><span data-ttu-id="474e2-177">Impostazione dei numeri di telefono inclusi per gli inviti</span><span class="sxs-lookup"><span data-stu-id="474e2-177">Setting the phone numbers included on invites</span></span>

1. <span data-ttu-id="474e2-178">Accedere con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="474e2-178">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="474e2-179">Passare all'interfaccia di amministrazione > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="474e2-179">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="474e2-180">Nel riquadro di navigazione sinistro, vai su  **Audioconferenza** > **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="474e2-180">In the left navigation, go to **Audio conferencing** > **Users**.</span></span> <span data-ttu-id="474e2-181">Selezionare l'utente da abilitare per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="474e2-181">Select the user that you want to enable for Audio Conferencing.</span></span>

4. <span data-ttu-id="474e2-182">Nel riquadro Azioni, è possibile impostare il **Numero a pagamento** e, se permesso, il **Numero verde**.</span><span class="sxs-lookup"><span data-stu-id="474e2-182">In the Action pane, you can set the **Toll number** and, if allowed, the **Toll-free number**.</span></span>

5. <span data-ttu-id="474e2-183">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="474e2-183">Click **Save**.</span></span>

<span data-ttu-id="474e2-184">Vedere [Impostare i numeri di telefono inclusi per gli inviti.](set-the-phone-numbers-included-on-invites.md)</span><span class="sxs-lookup"><span data-stu-id="474e2-184">See [Set the phone numbers included on invites](set-the-phone-numbers-included-on-invites.md).</span></span>


## <a name="choosing-audio-conferencing-bridge-settings"></a><span data-ttu-id="474e2-185">La scelta delle impostazioni di ponte per audioconferenza</span><span class="sxs-lookup"><span data-stu-id="474e2-185">Choosing audio conferencing bridge settings</span></span>

<span data-ttu-id="474e2-186">**Impostare l'esperienza della riunione quando i chiamanti aderiscono a una riunione**</span><span class="sxs-lookup"><span data-stu-id="474e2-186">**Set the meeting experience when callers join a meeting**</span></span>


1. <span data-ttu-id="474e2-187">Accedere con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="474e2-187">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="474e2-188">Passare all'interfaccia di amministrazione > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="474e2-188">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="474e2-189">**Nell'interfaccia di amministrazione di Skype for Business,** nel riquadro di spostamento sinistro, vai a Impostazioni bridge Microsoft per   >  **audioconferenze.**</span><span class="sxs-lookup"><span data-stu-id="474e2-189">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="474e2-190">In **Esperienza di partecipazione alla riunione** selezionare le azioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="474e2-190">Under **Meeting join experience**, select the following actions:</span></span>

   - <span data-ttu-id="474e2-191">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span><span class="sxs-lookup"><span data-stu-id="474e2-191">**Enable meeting entry and exit notifications to be turned on** This is selected by default.</span></span> <span data-ttu-id="474e2-192">Se si deseleziona questa casella di controllo, gli utenti che hanno già partecipato alla riunione per impostazione predefinita non verranno avvisati quando qualcuno entra o esce dalla riunione.</span><span class="sxs-lookup"><span data-stu-id="474e2-192">If you clear this check box, users who have already joined the meeting by default won't be notified when someone enters or leaves the meeting.</span></span>

     <span data-ttu-id="474e2-193">Questa impostazione può essere impostata su base riunione per riunione quando un utente partecipa  a una riunione con un'app Skype for Business e modifica l'impostazione Annuncia quando le persone entrano o abbandonano nel **menu** Opzioni riunione Skype della riunione.</span><span class="sxs-lookup"><span data-stu-id="474e2-193">This can be set on a meeting-by-meeting basis when a user joins a meeting using a Skype for Business app and they modify the **Announce when people enter or leave** setting in the Skype Meeting **Options** menu of the meeting.</span></span>

   - <span data-ttu-id="474e2-194">**Chiedere ai chiamanti di registrare il proprio nome prima di partecipare alla riunione** Questa opzione è selezionata per impostazione predefinita.</span><span class="sxs-lookup"><span data-stu-id="474e2-194">**Ask callers to record their name before joining the meeting** This is selected by default.</span></span> <span data-ttu-id="474e2-195">Se si deseleziona la casella di controllo, ai chiamanti non verrà richiesto di registrare il proprio nome prima che partecipino a una riunione.</span><span class="sxs-lookup"><span data-stu-id="474e2-195">If you clear this check box, callers won't be asked to record their name before they join a meeting.</span></span>

5. <span data-ttu-id="474e2-196">Vedi **Modificare le impostazioni per un bridge per audioconferenza**.</span><span class="sxs-lookup"><span data-stu-id="474e2-196">After you make your changes, click **Save**.</span></span>
    
<span data-ttu-id="474e2-197">Vedere [Modificare le impostazioni per un bridge di audioconferenza.](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)</span><span class="sxs-lookup"><span data-stu-id="474e2-197">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="474e2-198">**Impostare la lunghezza del PIN per le riunioni**</span><span class="sxs-lookup"><span data-stu-id="474e2-198">**Set the PIN length for meetings**</span></span>

1. <span data-ttu-id="474e2-199">Accedere con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="474e2-199">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="474e2-200">Passare all'interfaccia di amministrazione > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="474e2-200">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="474e2-201">**Nell'interfaccia di amministrazione di Skype for Business,** nel riquadro di spostamento sinistro, vai a Impostazioni bridge Microsoft per   >  **audioconferenze.**</span><span class="sxs-lookup"><span data-stu-id="474e2-201">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>

4. <span data-ttu-id="474e2-202">In **Sicurezza** immettere il numero di cifre desiderato per il PIN nell'elenco Lunghezza **PIN** e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="474e2-202">Under **Security**, enter the number of digits you want for the PIN in the **PIN length** list, and then click **Save**.</span></span>

    <span data-ttu-id="474e2-203">Il codice PIN deve essere compreso tra 4 e 12 cifre.</span><span class="sxs-lookup"><span data-stu-id="474e2-203">The PIN must be between 4 and 12 digits.</span></span> <span data-ttu-id="474e2-204">The default is 5.</span><span class="sxs-lookup"><span data-stu-id="474e2-204">The default is 5.</span></span>
    
<span data-ttu-id="474e2-205">Vedere [Modificare le impostazioni per un bridge di audioconferenza.](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge)</span><span class="sxs-lookup"><span data-stu-id="474e2-205">See [Change the settings for an Audio Conferencing bridge](/MicrosoftTeams/change-the-settings-for-an-audio-conferencing-bridge).</span></span>
  
 <span data-ttu-id="474e2-206">**Abilitare o disabilitare l'invio di posta elettronica agli utenti audio**</span><span class="sxs-lookup"><span data-stu-id="474e2-206">**Enable or disable email from being sent to audio users**</span></span>

1. <span data-ttu-id="474e2-207">Accedere con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="474e2-207">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="474e2-208">Passare all'interfaccia di amministrazione > **Skype for Business** e nel riquadro di spostamento sinistro fare clic su **Audioconferenza.**</span><span class="sxs-lookup"><span data-stu-id="474e2-208">Go to the admin center > **Skype for Business** and in the left navigation, click **Audio conferencing**.</span></span>

3. <span data-ttu-id="474e2-209">Nella pagina **Impostazioni ponte Microsoft**, seleziona o deseleziona **Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di audioconferenza vengono modificate**.</span><span class="sxs-lookup"><span data-stu-id="474e2-209">On the **Microsoft bridge settings** page, select or clear the **Automatically send emails to users if their audio conferencing settings change**.</span></span>

4. <span data-ttu-id="474e2-210">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="474e2-210">Click **Save**.</span></span>

    <span data-ttu-id="474e2-211">È anche possibile inviare messaggi di posta elettronica all'utente con le impostazioni di audioconferenza, passando alle proprietà dei servizi di audioconferenza dell'utente e facendo clic su Invia informazioni conferenza **tramite posta elettronica.**</span><span class="sxs-lookup"><span data-stu-id="474e2-211">You can also send email to the user with the audio conferencing settings, by going to the user's audio conferencing properties and clicking **Send conference info via email**.</span></span>

    <span data-ttu-id="474e2-212">Facendo ciò, verrà inviato  un messaggio di posta elettronica contenente solo il numero di telefono e l'ID conferenza, ma il PIN non verrà incluso.</span><span class="sxs-lookup"><span data-stu-id="474e2-212">If you do this, an email will be sent that only includes conference ID and conference phone number, but the PIN won't be included.</span></span>

    <span data-ttu-id="474e2-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="474e2-213">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span>

## <a name="see-and-set-the-primary-default-and-secondary-alternate-languages-on-an-audio-conferencing-bridge"></a><span data-ttu-id="474e2-214">Visualizzare e impostare le lingue principale (predefinita) e secondaria (alternativa) in un bridge di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="474e2-214">See and set the primary (default) and secondary (alternate) languages on an audio conferencing bridge</span></span>


1. <span data-ttu-id="474e2-215">Accedere con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="474e2-215">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="474e2-216">Passare all'interfaccia di amministrazione > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="474e2-216">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="474e2-217">**Nell'interfaccia di amministrazione di Skype for Business,** nel riquadro di spostamento sinistro, passare a **Audioconferenza** e quindi fare clic su **Bridge Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="474e2-217">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**, and then click **Microsoft bridge**.</span></span>

4. <span data-ttu-id="474e2-218">Selezionare un numero di telefono nell'elenco, fare clic su  Imposta lingue nel riquadro  Azioni e quindi nella pagina Imposta lingue fare clic sull'elenco Usa lingua principale per visualizzare l'elenco completo delle lingue supportate. </span><span class="sxs-lookup"><span data-stu-id="474e2-218">Select a phone number from the list, click **Set languages** in the Action pane, and then on the **Set languages** page, click the use the **Primary language** list to view the complete list of supported languages.</span></span>

    <span data-ttu-id="474e2-219">È anche possibile impostare le lingue principale e secondaria supportate quando si seleziona Microsoft come provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="474e2-219">You can also set the primary and secondary languages that are supported when you select Microsoft as the audio conferencing provider.</span></span> <span data-ttu-id="474e2-220">L'ordine selezionato negli elenchi è lo stesso ordine in cui verranno visualizzate le lingue per i chiamanti.</span><span class="sxs-lookup"><span data-stu-id="474e2-220">The order that you select in the lists is the same order in which languages will be presented to callers.</span></span>

<span data-ttu-id="474e2-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="474e2-221">See [Set auto attendant languages for Audio Conferencing](set-auto-attendant-languages-for-audio-conferencing.md).</span></span>

## <a name="see-audio-conferencing-dial-in-numbers"></a><span data-ttu-id="474e2-222">Visualizzare i numeri di accesso esterno per i servizi di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="474e2-222">See audio conferencing dial-in numbers</span></span>

1. <span data-ttu-id="474e2-223">Accedere con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="474e2-223">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="474e2-224">Passare all'interfaccia di amministrazione > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="474e2-224">Go to the admin center > **Skype for Business**.</span></span>
 
3. <span data-ttu-id="474e2-225">**Nell'interfaccia di amministrazione di Skype for Business,** nel riquadro di spostamento sinistro, passare a Bridge Microsoft per   >  **audioconferenze.**</span><span class="sxs-lookup"><span data-stu-id="474e2-225">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge**.</span></span> <span data-ttu-id="474e2-226">Qui puoi:</span><span class="sxs-lookup"><span data-stu-id="474e2-226">Here you can:</span></span>

   - <span data-ttu-id="474e2-227">Visualizzare i numeri di telefono impostati da Microsoft 365 o Office 365 per l'uso per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="474e2-227">View the phone numbers that are set by Microsoft 365 or Office 365 to be used for Audio Conferencing.</span></span>

   - <span data-ttu-id="474e2-228">Visualizzare la posizione e le lingue principale e secondaria che verranno usate dall'operatore automatico di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="474e2-228">View the location, and the primary and secondary languages, that will be used by the Audio Conferencing auto attendant.</span></span>

   - <span data-ttu-id="474e2-229">Selezionare il numero di telefono predefinito che verrà assegnato agli utenti quando sono abilitati per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="474e2-229">Select the default phone number that will be given to users when they are enabled for Audio Conferencing.</span></span> <span data-ttu-id="474e2-230">Tuttavia, se il numero di telefono predefinito del bridge di audioconferenza cambia, il numero di telefono predefinito per gli utenti esistenti non cambia.</span><span class="sxs-lookup"><span data-stu-id="474e2-230">However, if the default phone number of the audio conferencing bridge changes, the default phone number for existing users won't change.</span></span>

<span data-ttu-id="474e2-231">È possibile passare a Utenti di **audioconferenza** e selezionare le proprietà dell'utente per modificare il numero predefinito per un utente scegliendo un nuovo numero nell'elenco dei numeri disponibili  >   nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="474e2-231">You can go to **Audio conferencing** > **Users** and select the user's properties to change the default number for a user by choosing a new number from the list of numbers that are available in your organization.</span></span>

<span data-ttu-id="474e2-232">Vedere [Visualizzare un elenco di numeri di audioconferenza.](see-a-list-of-audio-conferencing-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="474e2-232">See [See a list of Audio Conferencing numbers](see-a-list-of-audio-conferencing-numbers.md).</span></span>

## <a name="see-a-list-of-users-that-are-enabled"></a><span data-ttu-id="474e2-233">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="474e2-233">See a list of users that are enabled</span></span>

1. <span data-ttu-id="474e2-234">Accedere con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="474e2-234">Sign in with your work or school account.</span></span>

2. <span data-ttu-id="474e2-235">Passare all'interfaccia di amministrazione > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="474e2-235">Go to the admin center > **Skype for Business**.</span></span>

3. <span data-ttu-id="474e2-236">**Nell'interfaccia di amministrazione di Skype for Business,** nel riquadro di spostamento sinistro, vai a **Audioconferenza**> e **quindi Utenti**.</span><span class="sxs-lookup"><span data-stu-id="474e2-236">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing**> and then **Users**.</span></span>

<span data-ttu-id="474e2-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="474e2-237">See [See a list of users that are enabled for Audio Conferencing](see-a-list-of-users-that-are-enabled-for-audio-conferencing.md).</span></span>

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="474e2-238">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="474e2-238">Want to know how to manage with Windows PowerShell?</span></span>

<span data-ttu-id="474e2-239">Esistono diverse impostazioni che è possibile gestire a livello di organizzazione usando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="474e2-239">There are several settings that you can manage at the organization level using Windows PowerShell.</span></span> <span data-ttu-id="474e2-240">In questo modo è facile applicare le impostazioni a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="474e2-240">This makes it easy to apply settings to all of your users.</span></span>

<span data-ttu-id="474e2-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](/previous-versions//mt228132(v=technet.10)).</span><span class="sxs-lookup"><span data-stu-id="474e2-241">To get more help on each cmdlet, see [Skype for Business Online cmdlets](/previous-versions//mt228132(v=technet.10)).</span></span>

<span data-ttu-id="474e2-242">Ecco le impostazioni a livello di organizzazione:</span><span class="sxs-lookup"><span data-stu-id="474e2-242">Here are the organization-level settings:</span></span>

- <span data-ttu-id="474e2-243">**Impostazione delle notifiche di ingresso/uscita** Il valore predefinito è _$true_.</span><span class="sxs-lookup"><span data-stu-id="474e2-243">**Setting entry/exit notifications** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableEntryExitNotifications $true|$false
  ```

- <span data-ttu-id="474e2-244">**Impostazione di registrazione del nome** Il valore predefinito è _$true_.</span><span class="sxs-lookup"><span data-stu-id="474e2-244">**Setting name recording** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -EnableNameRecording $true|false
  ```

- <span data-ttu-id="474e2-245">**Impostazione della lunghezza del PIN** Il valore predefinito è 5.</span><span class="sxs-lookup"><span data-stu-id="474e2-245">**Setting the PIN length** The default is 5.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -PinLength 7
  ```

- <span data-ttu-id="474e2-246">**Impostazione solo partecipazione a riunioni da un telefono** Il valore predefinito è _$false_.</span><span class="sxs-lookup"><span data-stu-id="474e2-246">**Setting only dial-in meetings from a phone** The default _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AllowPSTNOnlyMeetingsByDefault $true|$false
  ```

- <span data-ttu-id="474e2-247">**Impostazione se si desidera inviare messaggi di posta elettronica agli utenti** Il valore predefinito è _$true_.</span><span class="sxs-lookup"><span data-stu-id="474e2-247">**Setting whether to send email to users** The default is _$true_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
  ```

- <span data-ttu-id="474e2-248">**Impostazione se si desidera inviare posta elettronica da un account diverso** Il valore predefinito è _$false_.</span><span class="sxs-lookup"><span data-stu-id="474e2-248">**Setting whether to send email from a different account** The default is  _$false_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromOverride $true|$false
  ```

- <span data-ttu-id="474e2-249">**Impostazione dell'indirizzo di mittente nel messaggio di posta elettronica inviato agli utenti** Il valore predefinito è _$null_.</span><span class="sxs-lookup"><span data-stu-id="474e2-249">**Setting the From address on email that is sent to users** The default is _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromAddress
  ```

- <span data-ttu-id="474e2-250">**Impostazione del nome visualizzato per il messaggio di posta elettronica inviato agli utenti** Il valore predefinito è _$null_.</span><span class="sxs-lookup"><span data-stu-id="474e2-250">**Setting the display name for the email that is sent to users** The default is  _$null_.</span></span>
  ```PowerShell
  Set-CsOnlineDialInConferencingTenantSettings -SendEmailFromDisplayName
  ```

  ## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="474e2-251">Per altre informazioni su Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="474e2-251">Want to know more about Windows PowerShell</span></span>
- <span data-ttu-id="474e2-252">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="474e2-252">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="474e2-253">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare.</span><span class="sxs-lookup"><span data-stu-id="474e2-253">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="474e2-254">Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="474e2-254">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="474e2-255">Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="474e2-255">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - <span data-ttu-id="474e2-256">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="474e2-256">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

- <span data-ttu-id="474e2-257">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso solo dell'interfaccia di amministrazione, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="474e2-257">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the admin center, such as when you are making settings changes for many users at one time.</span></span> <span data-ttu-id="474e2-258">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="474e2-258">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="474e2-259">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="474e2-259">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="474e2-260">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="474e2-260">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

  - [<span data-ttu-id="474e2-261">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="474e2-261">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)

    <span data-ttu-id="474e2-p121">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="474e2-p121">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>

## <a name="related-topics"></a><span data-ttu-id="474e2-264">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="474e2-264">Related topics</span></span>

[<span data-ttu-id="474e2-265">Gestire le impostazioni di audioconferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="474e2-265">Manage the Audio Conferencing settings for a user</span></span>](manage-the-audio-conferencing-settings-for-a-user.md)