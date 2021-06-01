---
title: Messaggi di posta elettronica inviati agli utenti quando le loro impostazioni cambiano in Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
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
description: 'Scopri quali informazioni vengono inviate automaticamente agli utenti tramite posta elettronica quando modificano le impostazioni di conferenza telefonica in Skype for Business online. '
ms.openlocfilehash: 75ed80ef7d686ecb649bc1d21f30a43fd115f1a3
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237342"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-skype-for-business-online"></a><span data-ttu-id="19f4d-103">Messaggi di posta elettronica inviati agli utenti quando le loro impostazioni cambiano in Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="19f4d-103">Emails sent to users when their settings change in Skype for Business Online</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> <span data-ttu-id="19f4d-104">Se desideri informazioni relative alla posta elettronica automatica in Microsoft Teams, consulta[Messaggi di posta elettronica inviati agli utenti quando le loro impostazioni cambiano in Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).</span><span class="sxs-lookup"><span data-stu-id="19f4d-104">If you're looking for automatic email information in Microsoft Teams, see [Emails sent to users when their settings change in Microsoft Teams](/MicrosoftTeams/emails-sent-to-users-when-their-settings-change-in-teams).</span></span>

<span data-ttu-id="19f4d-105">I messaggi di posta elettronica vengono inviati automaticamente agli utenti che sono [abilitati per le audioconferenze](set-up-audio-conferencing.md) tramite Microsoft come provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="19f4d-105">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing.md) using Microsoft as the audio conferencing provider.</span></span>
  
<span data-ttu-id="19f4d-106">Per impostazione predefinita, sono disponibili quattro tipi di posta elettronica inviata agli utenti abilitati per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="19f4d-106">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="19f4d-107">Tuttavia, se desideri limitare il numero di messaggi di posta elettronica inviati agli utenti, puoi disabilitare l'opzione.</span><span class="sxs-lookup"><span data-stu-id="19f4d-107">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="19f4d-108">Le audioconferenze Microsoft 365 o Office 365 invieranno posta elettronica ai messaggi di posta elettronica degli utenti quando:</span><span class="sxs-lookup"><span data-stu-id="19f4d-108">Audio Conferencing in Microsoft 365 or Office 365 will send email to your users' email when:</span></span>
  
- <span data-ttu-id="19f4d-109">**Viene assegnata loro una licenza di Audioconferenza o quando cambi il provider di audioconferenza e passi a Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="19f4d-109">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>
    
     <span data-ttu-id="19f4d-110">Questo messaggio di posta elettronica include l'ID conferenza, il numero di telefono predefinito per le riunioni, il PIN per le audioconferenze dell'utente e le istruzioni e il collegamento per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business online che consente di aggiornare riunioni esistenti per l'utente.</span><span class="sxs-lookup"><span data-stu-id="19f4d-110">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="19f4d-111">Consultare [Assegnare licenze Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) o [Assegnare Microsoft come provider di servizi di audioconferenza](assign-microsoft-as-the-audio-conferencing-provider.md).</span><span class="sxs-lookup"><span data-stu-id="19f4d-111">See [Assign Skype for Business licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft as the audio conferencing provider](assign-microsoft-as-the-audio-conferencing-provider.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="19f4d-112">Se l'organizzazione è stata abilitata per gli ID conferenza dinamici, tutte le riunioni dell'utente pianificate avranno ID conferenza univoci.</span><span class="sxs-lookup"><span data-stu-id="19f4d-112">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="19f4d-113">È possibile impostare [gli ID audioconferenza dinamici all'interno dell'organizzazione](./reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="19f4d-113">You can set up [Audio Conferencing dynamic IDs in your organization](./reset-a-conference-id-for-a-user.md).</span></span> 
  
    <span data-ttu-id="19f4d-114">Di seguito è riportato un esempio di questo messaggio di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="19f4d-114">Here is an example of this email:</span></span>
    
     ![Verificare la licenza Skype for Business](../images/audio-conferencing-user-enabled.png)
  
    <span data-ttu-id="19f4d-116">È possibile trovare ulteriori informazioni sulla licenza Skype for Business visualizzando [Licenze per i componenti aggiuntivi Skype for Business](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="19f4d-116">You can find out more about Skype for Business licensing by seeing [Skype for Business add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
- <span data-ttu-id="19f4d-117">**L'ID conferenza o il numero di telefono per le conferenze predefinito di un utente cambia.**</span><span class="sxs-lookup"><span data-stu-id="19f4d-117">**The conference ID or default conference phone number of a user changes.**</span></span>
    
    <span data-ttu-id="19f4d-118">Questo messaggio di posta elettronica contiene l'ID conferenza, il numero di telefono di conferenza predefinito, le istruzioni e il collegamento per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business online che consente di aggiornare riunioni esistenti per l'utente.</span><span class="sxs-lookup"><span data-stu-id="19f4d-118">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="19f4d-119">Tuttavia, questo messaggio di posta elettronica non include il PIN per l'audioconferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="19f4d-119">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="19f4d-120">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="19f4d-120">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="19f4d-121">Se l'organizzazione è stata abilitata per gli ID conferenza dinamici, tutte le riunioni dell'utente pianificate avranno ID conferenza univoci.</span><span class="sxs-lookup"><span data-stu-id="19f4d-121">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="19f4d-122">È possibile impostare [gli ID audioconferenza dinamici all'interno dell'organizzazione](./reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="19f4d-122">You can set up [Audio Conferencing dynamic IDs in your organization](./reset-a-conference-id-for-a-user.md).</span></span> 
  
    <span data-ttu-id="19f4d-123">Di seguito è riportato un esempio di questo messaggio di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="19f4d-123">Here is an example of this email:</span></span>
    
     ![Le informazioni sulle conferenze telefoniche sono state modificate.](../images/audio-conferencing-info-change.png)
  
- <span data-ttu-id="19f4d-125">**Viene reimpostato il PIN di audioconferenza di un utente.**</span><span class="sxs-lookup"><span data-stu-id="19f4d-125">**The audio conferencing PIN of a user is reset.**</span></span>
    
    <span data-ttu-id="19f4d-126">Questo messaggio di posta elettronica contiene il PIN di audioconferenza dell'organizzatore, l'ID conferenza esistente e il numero di telefono di conferenza predefinito per l'utente.</span><span class="sxs-lookup"><span data-stu-id="19f4d-126">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="19f4d-127">Vedere [Reimpostare il PIN dei servizi di audioconferenza.](reset-the-audio-conferencing-pin.md)</span><span class="sxs-lookup"><span data-stu-id="19f4d-127">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="19f4d-128">Se l'organizzazione è stata abilitata per gli ID conferenza dinamici, tutte le riunioni dell'utente pianificate avranno ID conferenza univoci.</span><span class="sxs-lookup"><span data-stu-id="19f4d-128">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="19f4d-129">È possibile impostare [gli ID audioconferenza dinamici all'interno dell'organizzazione](./reset-a-conference-id-for-a-user.md).</span><span class="sxs-lookup"><span data-stu-id="19f4d-129">You can set up [Audio Conferencing dynamic IDs in your organization](./reset-a-conference-id-for-a-user.md).</span></span> 
  
    <span data-ttu-id="19f4d-130">Di seguito è riportato un esempio di questo messaggio di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="19f4d-130">Here is an example of this email:</span></span>
    
     ![PIN di conferenza telefonica modificato.](../images/audio-conferencing-pin-has-changed.png)
  
- <span data-ttu-id="19f4d-132">**Una licenza dell'utente è stata rimossa o quando il provider di servizi di audioconferenza viene modificato da Microsoft a altri provider o nessuno.**</span><span class="sxs-lookup"><span data-stu-id="19f4d-132">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>
    
    <span data-ttu-id="19f4d-133">Si verifica quando la licenza di **Audioconferenza** viene rimossa da un utente o quando si modifica il provider di servizi di audioconferenza di un utente da Microsoft a un provider di servizi di audioconferenza di terze parti o quando si imposta il provider su **Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="19f4d-133">This happens when the **Audio Conferencing** license is removed from a user or when changing the audio conferencing provider of a user from Microsoft to a third-party audio conferencing provider or when setting the provider to **None**.</span></span> <span data-ttu-id="19f4d-134">Questo messaggio di posta elettronica contiene le istruzioni e informazioni che consentono all'utente di utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business online per rimuovere informazioni specifiche di audioconferenze, ad esempio il numero di telefono di conferenza predefinito o l'ID conferenza.</span><span class="sxs-lookup"><span data-stu-id="19f4d-134">This email contains the instructions and information for the user to use the Skype for Business Online Meeting Update Tool to remove audio conferencing specific information, such as the default conference phone number or conference ID.</span></span>
    
    <span data-ttu-id="19f4d-135">Vedere [Assegnare o rimuovere licenze per Microsoft 365 Apps for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span><span class="sxs-lookup"><span data-stu-id="19f4d-135">See [Assign or remove licenses for Microsoft 365 Apps for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>
    
    <span data-ttu-id="19f4d-136">Di seguito è riportato un esempio di questo messaggio di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="19f4d-136">Here is an example of this email:</span></span>
    
     ![Conferenza telefonica disattivata.](../images/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="19f4d-138">Apportare modifiche ai messaggi di posta elettronica inviati</span><span class="sxs-lookup"><span data-stu-id="19f4d-138">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="19f4d-139">È possibile apportare modifiche al messaggio di posta elettronica che viene inviato automaticamente agli utenti, inclusi l'indirizzo di posta elettronica e il nome visualizzato incluso nelle informazioni *di* contatto Da.</span><span class="sxs-lookup"><span data-stu-id="19f4d-139">You can make changes to the email that is automatically sent to users including the email address and the display name that is included in the *From* contact information.</span></span> <span data-ttu-id="19f4d-140">Per impostazione predefinita, il mittente dei messaggi di posta elettronica viene inviato da Microsoft 365 o Office 365, ma è possibile modificare l'indirizzo di posta elettronica e il nome visualizzato usando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/previous-versions//mt228132(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="19f4d-140">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet.</span></span> <span data-ttu-id="19f4d-141">Per apportare modifiche all'indirizzo di posta elettronica che invia il messaggio agli utenti, è necessario:</span><span class="sxs-lookup"><span data-stu-id="19f4d-141">To make changes to the email address that is sending the email to the users, you must:</span></span>
  
- <span data-ttu-id="19f4d-142">Immetti il nome visualizzato nel parametro  _SendEmailFromDisplayName_.</span><span class="sxs-lookup"><span data-stu-id="19f4d-142">Enter the email address in the  _SendEmailFromAddress_ parameter.</span></span>
    
- <span data-ttu-id="19f4d-143">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span><span class="sxs-lookup"><span data-stu-id="19f4d-143">Enter the email display name in the  _SendEmailFromDisplayName_ parameter.</span></span>
    
- <span data-ttu-id="19f4d-144">Impostare il  _parametro SendEmailOverride_ su  _True_.</span><span class="sxs-lookup"><span data-stu-id="19f4d-144">Set the  _SendEmailOverride_ parameter to  _True_.</span></span>
    
<span data-ttu-id="19f4d-145">È possibile apportare modifiche al messaggio di posta elettronica inviato agli utenti, ad esempio l'indirizzo di posta elettronica da cui viene inviato il messaggio e il nome visualizzato del messaggio, eseguendo:</span><span class="sxs-lookup"><span data-stu-id="19f4d-145">You can make changes to the email sent to users, such as the email address that the email is sent from and the display name for the email, by running:</span></span>
  
```PowerShell
Set-CsOnlineDialInConferencingTenantSetting -SendEmailOverride $true -SendEmailFromAddress amos.marble -SendEmailFromDisplayName "Amos Marble"
```

> [!NOTE]
>  <span data-ttu-id="19f4d-146">Se si vogliono modificare le informazioni sull'indirizzo di posta elettronica, è necessario assicurarsi che i criteri di posta elettronica in ingresso dell'ambiente consentano i messaggi di posta elettronica provenienti dall'indirizzo personalizzato specificato da.</span><span class="sxs-lookup"><span data-stu-id="19f4d-146">If you want to change the email address information, you need to make sure that the inbound email policies of your environment allow emails that come from the custom specified from address.</span></span> <span data-ttu-id="19f4d-147">Se decidi di sostituire le informazioni di contatto *Da*, devi verificare che i messaggi di posta elettronica vengano inviati correttamente agli utenti.</span><span class="sxs-lookup"><span data-stu-id="19f4d-147">If you decide to override the *From* contact information, you should verify that the emails are correctly sent to users.</span></span> <span data-ttu-id="19f4d-148">Puoi farlo facendo un test con un utente della tua organizzazione.</span><span class="sxs-lookup"><span data-stu-id="19f4d-148">You can do this by testing this with one user in your organization.</span></span>
  
<span data-ttu-id="19f4d-149">È possibile usare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) per gestire altre impostazioni per l'organizzazione, tra cui la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="19f4d-149">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="19f4d-150">E se non vuoi che la posta elettronica venga inviata a loro?</span><span class="sxs-lookup"><span data-stu-id="19f4d-150">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="19f4d-151">Quando disattivi l'invio di messaggi di posta elettronica agli utenti, la posta elettronica non verrà inviata anche quando un utente riceve una licenza.</span><span class="sxs-lookup"><span data-stu-id="19f4d-151">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="19f4d-152">In questo caso, l'ID conferenza, il numero di telefono per conferenze predefinito e, soprattutto, il PIN di audioconferenza non verranno inviati all'utente.</span><span class="sxs-lookup"><span data-stu-id="19f4d-152">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="19f4d-153">In questo caso, devi informare l'utente inviandogli un messaggio di posta elettronica separato o chiamandolo.</span><span class="sxs-lookup"><span data-stu-id="19f4d-153">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>
  
<span data-ttu-id="19f4d-154">Per impostazione predefinita, verranno inviati messaggi di posta elettronica agli utenti, ma se desideri impedire loro di ricevere posta elettronica per le audioconferenze, puoi utilizzare l'interfaccia di amministrazione di Skype for Business o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="19f4d-154">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use the Skype for Business admin center or Windows PowerShell.</span></span> 
 
<span data-ttu-id="19f4d-155">![Icona che mostra il logo Skype for Business ](../images/sfb-logo-30x30.png) **con l'interfaccia Skype for Business di amministrazione**  </span><span class="sxs-lookup"><span data-stu-id="19f4d-155">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png)  **Using the Skype for Business admin center**</span></span>
    
1. <span data-ttu-id="19f4d-156">**Nell'Skype for Business di amministrazione,** nel riquadro di spostamento sinistro, passare a Impostazioni bridge Microsoft **per audioconferenze.**  >  </span><span class="sxs-lookup"><span data-stu-id="19f4d-156">In the **Skype for Business admin center**, in the left navigation, go to **Audio conferencing** > **Microsoft bridge settings**.</span></span>
    
2. <span data-ttu-id="19f4d-157">Nella pagina **Impostazioni bridge Microsoft** selezionare o deselezionare Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di **audioconferenza cambiano.**</span><span class="sxs-lookup"><span data-stu-id="19f4d-157">On the **Microsoft bridge settings** page, select or clear **Automatically send emails to users if their audio conferencing settings change**.</span></span> 
    
3. <span data-ttu-id="19f4d-158">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="19f4d-158">Click **Save**.</span></span> 

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
<span data-ttu-id="19f4d-159">**Uso di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="19f4d-159">**Using Windows PowerShell**</span></span>
  
1. <span data-ttu-id="19f4d-160">Esegui le operazioni seguenti per disabilitare l'invio di posta elettronica a tutti gli utenti:</span><span class="sxs-lookup"><span data-stu-id="19f4d-160">Run the following to disable sending all of your users email:</span></span>
    
   ```PowerShell
   Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $false
   ```

<span data-ttu-id="19f4d-161">È possibile usare il cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) per gestire altre impostazioni per l'organizzazione, tra cui la posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="19f4d-161">You can use the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet to manage other settings for your organization, including email.</span></span>
  
## <a name="what-else-should-you-know-about-this-email"></a><span data-ttu-id="19f4d-162">Cos'altro occorre sapere su questo messaggio di posta elettronica?</span><span class="sxs-lookup"><span data-stu-id="19f4d-162">What else should you know about this email?</span></span>

- <span data-ttu-id="19f4d-163">Per ulteriori informazioni su come abilitare e disabilitare automaticamente l'invio di posta elettronica agli utenti, consulta [Attivare o disattivare l'invio messaggi di posta elettronica quando le impostazioni di Audioconferenza vengono modificate](enable-or-disable-sending-emails-when-their-settings-change.md).</span><span class="sxs-lookup"><span data-stu-id="19f4d-163">For more on enabling and disabling automatically sending email to your users, see [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).</span></span>
    
- <span data-ttu-id="19f4d-164">In alcuni casi, gli utenti perdono le informazioni audio e devi riuscire a inviare loro tutte le informazioni audio.</span><span class="sxs-lookup"><span data-stu-id="19f4d-164">Sometimes users lose their audio information and you need to be able to send them all of their audio information to them.</span></span> <span data-ttu-id="19f4d-165">A questo scopo, usare l'interfaccia di  amministrazione Skype for Business e fare clic su Invia informazioni conferenza tramite posta elettronica nelle proprietà di audioconferenza per un utente.</span><span class="sxs-lookup"><span data-stu-id="19f4d-165">You can do this by using the Skype for Business admin center and clicking **Send conference info via email** under the audio conferencing properties for a user.</span></span> <span data-ttu-id="19f4d-166">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span><span class="sxs-lookup"><span data-stu-id="19f4d-166">See [Send an email to a user with their Audio Conferencing information](send-an-email-to-a-user-with-their-dial-in-information.md).</span></span> <span data-ttu-id="19f4d-167">Tuttavia, queste informazioni non includono il PIN di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="19f4d-167">However, this information doesn't include the audio conferencing PIN.</span></span>
    
    <span data-ttu-id="19f4d-168">Di seguito è riportato un esempio del messaggio di posta elettronica che verrà inviato:</span><span class="sxs-lookup"><span data-stu-id="19f4d-168">Here is an example of this email that will be sent to them:</span></span>
    
     ![Posta elettronica di conferenza telefonica con accesso esterno](../images/81fe4e09-a346-4469-8cc5-c6d65f739b73.png)
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a><span data-ttu-id="19f4d-170">Vuoi sapere come gestire queste operazioni con Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="19f4d-170">Want to know how to manage with Windows PowerShell?</span></span>

- <span data-ttu-id="19f4d-171">Per impostazione predefinita, il mittente dei messaggi di posta elettronica viene inviato da Microsoft 365 o Office 365, ma è possibile modificare l'indirizzo di posta elettronica e il nome visualizzato usando Windows PowerShell e il cmdlet [Set-CsOnlineDialInConferencingTenantSettings.](/previous-versions//mt228132(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="19f4d-171">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell and the [Set-CsOnlineDialInConferencingTenantSettings](/previous-versions//mt228132(v=technet.10)) cmdlet.</span></span>
    
- <span data-ttu-id="19f4d-172">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="19f4d-172">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="19f4d-173">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare.</span><span class="sxs-lookup"><span data-stu-id="19f4d-173">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="19f4d-174">Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="19f4d-174">To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="19f4d-175">Perché occorre Windows PowerShell per gestire Office 365 o Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="19f4d-175">Why you need to use Microsoft 365 or Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - <span data-ttu-id="19f4d-176">[Gestire Office 365 o Microsoft 365 con Windows PowerShell nel modo migliore](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="19f4d-176">[Best ways to manage Microsoft 365 or Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>
    
- <span data-ttu-id="19f4d-177">Windows PowerShell offre molti vantaggi in termini di velocità, semplicità e produttività rispetto all'uso dell'interfaccia di amministrazione di Microsoft 365, ad esempio quando si apportano modifiche alle impostazioni per molti utenti contemporaneamente.</span><span class="sxs-lookup"><span data-stu-id="19f4d-177">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft 365 admin center, such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="19f4d-178">Per informazioni su questi vantaggi, consulta i seguenti argomenti:</span><span class="sxs-lookup"><span data-stu-id="19f4d-178">Learn about these advantages in the following topics:</span></span> 
    
  - [<span data-ttu-id="19f4d-179">Introduzione a Windows Powershell e Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="19f4d-179">An introduction to Windows PowerShell and Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="19f4d-180">Uso di Windows PowerShell per gestire Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="19f4d-180">Using Windows PowerShell to manage Skype for Business Online</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [<span data-ttu-id="19f4d-181">Uso di Windows PowerShell per eseguire le più comuni attività di gestione di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="19f4d-181">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > <span data-ttu-id="19f4d-p115">Il modulo Windows PowerShell per Skype for Business online consente di creare una sessione di Windows PowerShell remota che si connette a Skype for Business online. Questo modulo, supportato solo nei computer a 64 bit, può essere scaricato dall'Area download Microsoft nel [modulo Windows PowerShell per Skype for Business online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span><span class="sxs-lookup"><span data-stu-id="19f4d-p115">The Windows PowerShell module for Skype for Business Online enables you to create a remote Windows PowerShell session that connects to Skype for Business Online. This module, which is supported only on 64-bit computers, can be downloaded from the Microsoft Download Center at [Windows PowerShell Module for Skype for Business Online.](https://go.microsoft.com/fwlink/?LinkId=294688)</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="19f4d-184">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="19f4d-184">Related topics</span></span>

[<span data-ttu-id="19f4d-185">Abilitare o disabilitare l'invio di messaggi di posta elettronica in caso di modifica delle impostazioni di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="19f4d-185">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change.md)
  
[<span data-ttu-id="19f4d-186">Inviare un messaggio di posta elettronica a un utente con le sue informazioni di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="19f4d-186">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information.md)
