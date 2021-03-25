---
title: E-mail inviate automaticamente agli utenti in caso di modifica delle impostazioni
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Informazioni sulle informazioni che vengono inviate automaticamente agli utenti tramite posta elettronica quando le impostazioni dei servizi di conferenza telefonica con accesso esterno cambiano in Microsoft Teams. '
ms.openlocfilehash: a9ca30e7e701afca2e42eccfaef4f3d45660cd3a
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120757"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a><span data-ttu-id="5646a-103">Messaggi di posta elettronica inviati agli utenti quando le impostazioni cambiano in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5646a-103">Emails sent to users when their settings change in Microsoft Teams</span></span>

<span data-ttu-id="5646a-104">I messaggi di posta elettronica vengono inviati automaticamente agli utenti che sono [abilitati per le audioconferenze](set-up-audio-conferencing-in-teams.md) tramite Microsoft come provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="5646a-104">Emails will be automatically sent to users who are [enabled for Audio Conferencing](set-up-audio-conferencing-in-teams.md) using Microsoft as the audio conferencing provider.</span></span>

<span data-ttu-id="5646a-105">Per impostazione predefinita, sono disponibili quattro tipi di posta elettronica inviata agli utenti abilitati per le audioconferenze.</span><span class="sxs-lookup"><span data-stu-id="5646a-105">By default, there are four types of email that will be sent to your users who are enabled for Audio Conferencing.</span></span> <span data-ttu-id="5646a-106">Tuttavia, se desideri limitare il numero di messaggi di posta elettronica inviati agli utenti, puoi disabilitare l'opzione.</span><span class="sxs-lookup"><span data-stu-id="5646a-106">However, if you want to limit the number of emails sent to users, you can turn it off.</span></span> <span data-ttu-id="5646a-107">Le audioconferenze in Microsoft 365 o Office 365 invieranno posta elettronica ai messaggi di posta elettronica degli utenti quando:</span><span class="sxs-lookup"><span data-stu-id="5646a-107">Audio Conferencing in Microsoft 365 or Office 365 will send email to your users' email when:</span></span>

- <span data-ttu-id="5646a-108">**Viene assegnata loro una licenza di Audioconferenza o quando cambi il provider di audioconferenza e passi a Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="5646a-108">**An Audio Conferencing license is assigned to them or when you are changing the audio conferencing provider to Microsoft.**</span></span>

     <span data-ttu-id="5646a-109">Questo messaggio di posta elettronica include l'ID conferenza, il numero di telefono predefinito per le riunioni, il PIN per le audioconferenze dell'utente e le istruzioni e il collegamento per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business online che consente di aggiornare riunioni esistenti per l'utente.</span><span class="sxs-lookup"><span data-stu-id="5646a-109">This email includes the conference ID, the default conference phone number for the meetings, the audio conferencing PIN for the user, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="5646a-110">Vedere [Assegnare licenze per i componenti](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) aggiuntivi di Microsoft Teams o [Assegnare Microsoft come provider di servizi di audioconferenza.](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider)</span><span class="sxs-lookup"><span data-stu-id="5646a-110">See [Assign Microsoft Teams add-on licenses](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) or [Assign Microsoft as the audio conferencing provider](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).</span></span>

    > [!NOTE]
    > <span data-ttu-id="5646a-111">Se l'organizzazione è stata abilitata per gli ID conferenza dinamici, tutte le riunioni dell'utente pianificate avranno ID conferenza univoci.</span><span class="sxs-lookup"><span data-stu-id="5646a-111">If your organization has been enabled for dynamic conference IDs, all of a user's meetings that they schedule will have unique conference IDs.</span></span> <span data-ttu-id="5646a-112">È possibile impostare [gli ID audioconferenza dinamici all'interno dell'organizzazione](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span><span class="sxs-lookup"><span data-stu-id="5646a-112">You can set up [Audio Conferencing dynamic IDs in your organization](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user).</span></span> 

    <span data-ttu-id="5646a-113">Di seguito è riportato un esempio di questo messaggio di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="5646a-113">Here is an example of this email:</span></span>

     ![Verificare la licenza Skype for Business](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    <span data-ttu-id="5646a-115">Per altre informazioni sulle licenze, vedere Licenze per i componenti aggiuntivi di [Microsoft Teams.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)</span><span class="sxs-lookup"><span data-stu-id="5646a-115">To find out more about licensing, see [Microsoft Teams add-on licensing](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>

- <span data-ttu-id="5646a-116">**L'ID conferenza o il numero di telefono per le conferenze predefinito di un utente cambia.**</span><span class="sxs-lookup"><span data-stu-id="5646a-116">**The conference ID or default conference phone number of a user changes.**</span></span>

    <span data-ttu-id="5646a-117">Questo messaggio di posta elettronica contiene l'ID conferenza, il numero di telefono di conferenza predefinito, le istruzioni e il collegamento per utilizzare lo strumento di aggiornamento delle riunioni di Skype for Business online che consente di aggiornare riunioni esistenti per l'utente.</span><span class="sxs-lookup"><span data-stu-id="5646a-117">This email contains the conference ID, default conference phone number, and the instructions and link to use the Skype for Business Online Meeting Update Tool that is used to update existing meetings for the user.</span></span> <span data-ttu-id="5646a-118">Tuttavia, questo messaggio di posta elettronica non include il PIN per l'audioconferenza dell'utente.</span><span class="sxs-lookup"><span data-stu-id="5646a-118">But this email doesn't include the user's audio conferencing PIN.</span></span> <span data-ttu-id="5646a-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="5646a-119">See [Reset a conference ID for a user](reset-a-conference-id-for-a-user-in-teams.md).</span></span>

    <span data-ttu-id="5646a-120">Di seguito è riportato un esempio di questo messaggio di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="5646a-120">Here is an example of this email:</span></span>

     ![Le informazioni sulle conferenze telefoniche sono state modificate.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- <span data-ttu-id="5646a-122">**Viene reimpostato il PIN di audioconferenza di un utente.**</span><span class="sxs-lookup"><span data-stu-id="5646a-122">**The audio conferencing PIN of a user is reset.**</span></span>

    <span data-ttu-id="5646a-123">Questo messaggio di posta elettronica contiene il PIN di audioconferenza dell'organizzatore, l'ID conferenza esistente e il numero di telefono di conferenza predefinito per l'utente.</span><span class="sxs-lookup"><span data-stu-id="5646a-123">This email contains the organizer's audio conferencing PIN, the existing conference ID, and default conference phone number for the user.</span></span> <span data-ttu-id="5646a-124">Vedere [Reimpostare il PIN dei servizi di audioconferenza.](reset-the-audio-conferencing-pin-in-teams.md)</span><span class="sxs-lookup"><span data-stu-id="5646a-124">See [Reset the Audio Conferencing PIN](reset-the-audio-conferencing-pin-in-teams.md).</span></span>
    
     <span data-ttu-id="5646a-125">Di seguito è riportato un esempio di questo messaggio di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="5646a-125">Here is an example of this email:</span></span>
    
     ![PIN di conferenza telefonica modificato.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- <span data-ttu-id="5646a-127">**Una licenza dell'utente è stata rimossa o quando il provider di servizi di audioconferenza viene modificato da Microsoft a altri provider o nessuno.**</span><span class="sxs-lookup"><span data-stu-id="5646a-127">**A user's license is removed or when audio conferencing provider changes from Microsoft to other provider or None.**</span></span>

    <span data-ttu-id="5646a-128">Questo problema si verifica quando la licenza **di audioconferenza** viene rimossa da un utente o quando si imposta il provider di servizi di audioconferenza **su Nessuno**.</span><span class="sxs-lookup"><span data-stu-id="5646a-128">This happens when the **Audio Conferencing** license is removed from a user or when setting the audio conferencing provider to **None**.</span></span>

    <span data-ttu-id="5646a-129">Vedere [Assegnare o rimuovere licenze per Microsoft 365 per le aziende.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)</span><span class="sxs-lookup"><span data-stu-id="5646a-129">See [Assign or remove licenses for Microsoft 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).</span></span>

    <span data-ttu-id="5646a-130">Di seguito è riportato un esempio di questo messaggio di posta elettronica:</span><span class="sxs-lookup"><span data-stu-id="5646a-130">Here is an example of this email:</span></span>

     ![Conferenza telefonica disattivata.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a><span data-ttu-id="5646a-132">Apportare modifiche ai messaggi di posta elettronica inviati</span><span class="sxs-lookup"><span data-stu-id="5646a-132">Make changes to the email messages that are sent to them</span></span>

<span data-ttu-id="5646a-133">È possibile apportare modifiche al messaggio di posta elettronica che viene inviato automaticamente agli utenti.</span><span class="sxs-lookup"><span data-stu-id="5646a-133">You can make changes to the email that is automatically sent to users.</span></span> <span data-ttu-id="5646a-134">Per impostazione predefinita, il mittente dei messaggi di posta elettronica viene da Microsoft 365 o Office 365, ma è possibile modificare il nome visualizzato usando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5646a-134">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the display name using Windows PowerShell.</span></span> <span data-ttu-id="5646a-135">Per altre informazioni, vedere le informazioni di riferimento su [Microsoft Teams PowerShell.](/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="5646a-135">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a><span data-ttu-id="5646a-136">E se non vuoi che la posta elettronica venga inviata a loro?</span><span class="sxs-lookup"><span data-stu-id="5646a-136">What if you don't want email to be sent to them?</span></span>

<span data-ttu-id="5646a-137">Quando disattivi l'invio di messaggi di posta elettronica agli utenti, la posta elettronica non verrà inviata anche quando un utente riceve una licenza.</span><span class="sxs-lookup"><span data-stu-id="5646a-137">When you disable sending emails to users, email won't be sent even when a user gets assigned a license.</span></span> <span data-ttu-id="5646a-138">In questo caso, l'ID conferenza, il numero di telefono per conferenze predefinito e, soprattutto, il PIN di audioconferenza non verranno inviati all'utente.</span><span class="sxs-lookup"><span data-stu-id="5646a-138">In this case, the conference ID, default conferencing phone number, and, more importantly, their audio conferencing PIN won't be sent to the user.</span></span> <span data-ttu-id="5646a-139">In questo caso, devi informare l'utente inviandogli un messaggio di posta elettronica separato o chiamandolo.</span><span class="sxs-lookup"><span data-stu-id="5646a-139">When this happens, you must tell the user by sending them a separate email or by calling them.</span></span>

<span data-ttu-id="5646a-140">Per impostazione predefinita, i messaggi di posta elettronica verranno inviati agli utenti, ma se si vuole impedire loro di ricevere posta elettronica per le audioconferenze, è possibile usare Microsoft Teams o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5646a-140">By default, emails will be sent to your users, but if you want to prevent them from receiving email for audio conferencing, you can use Microsoft Teams or Windows PowerShell.</span></span> 

<span data-ttu-id="5646a-141">![Icona che mostra il logo di Microsoft Teams](media/teams-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Microsoft Teams**</span><span class="sxs-lookup"><span data-stu-id="5646a-141">![An icon showing the Microsoft Teams logo](media/teams-logo-30x30.png) **Using the Microsoft Teams admin center**</span></span>

1. <span data-ttu-id="5646a-142">Nel riquadro di spostamento sinistro, passare a **Riunioni** > **Bridge di conferenza**.</span><span class="sxs-lookup"><span data-stu-id="5646a-142">In the left navigation, go to **Meetings** > **Conference Bridges**.</span></span> 

2. <span data-ttu-id="5646a-143">Nella parte superiore della pagina **Bridge di conferenza** fare clic su Impostazioni **bridge.**</span><span class="sxs-lookup"><span data-stu-id="5646a-143">At the top of the **Conference Bridges** page, click **Bridge settings**.</span></span> 

3. <span data-ttu-id="5646a-144">Nel riquadro **Impostazioni bridge** abilitare o disabilitare Invia automaticamente messaggi di posta elettronica agli utenti se le impostazioni di accesso **remoto cambiano.**</span><span class="sxs-lookup"><span data-stu-id="5646a-144">In the **Bridge settings** pane, enable or disable **Automatically send emails to users if their dial-in settings change**.</span></span>

4. <span data-ttu-id="5646a-145">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="5646a-145">Click **Save**.</span></span>

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

<span data-ttu-id="5646a-146">**Uso di Windows PowerShell**</span><span class="sxs-lookup"><span data-stu-id="5646a-146">**Using Windows PowerShell**</span></span>

<span data-ttu-id="5646a-147">Per altre informazioni, vedere le informazioni di riferimento su [Microsoft Teams PowerShell.](/powershell/module/teams/?view=teams-ps)</span><span class="sxs-lookup"><span data-stu-id="5646a-147">See the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="want-to-know-more-about-windows-powershell"></a><span data-ttu-id="5646a-148">Per saperne di più sulle Windows PowerShell?</span><span class="sxs-lookup"><span data-stu-id="5646a-148">Want to know more about Windows PowerShell?</span></span>

<span data-ttu-id="5646a-149">Per impostazione predefinita, il mittente dei messaggi di posta elettronica verrà inviato da Microsoft 365 o Office 365, ma è possibile modificare l'indirizzo di posta elettronica e il nome visualizzato usando Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5646a-149">By default, the sender of the emails will be from Microsoft 365 or Office 365, but you can change the email address and display name using Windows PowerShell.</span></span> 

<span data-ttu-id="5646a-150">Con Windows PowerShell è possibile gestire gli utenti e decidere quali operazioni sono autorizzati o meno a eseguire.</span><span class="sxs-lookup"><span data-stu-id="5646a-150">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="5646a-151">Con Windows PowerShell è possibile gestire Microsoft 365 o Office 365 tramite un'unica posizione di amministrazione, semplificando il lavoro quotidiano quando si hanno più attività da completare.</span><span class="sxs-lookup"><span data-stu-id="5646a-151">With Windows PowerShell, you can manage Microsoft 365 or Office 365 using a single point of administration that can simplify your daily work when you have multiple tasks to do.</span></span> <span data-ttu-id="5646a-152">Per iniziare a usare Windows PowerShell, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="5646a-152">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="5646a-153">Sei motivi per utilizzare Windows PowerShell per gestire Office 365</span><span class="sxs-lookup"><span data-stu-id="5646a-153">Why you need to use Office 365 PowerShell</span></span>](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - <span data-ttu-id="5646a-154">[Modi migliori per gestire Office 365 con Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span><span class="sxs-lookup"><span data-stu-id="5646a-154">[Best ways to manage Office 365 with Windows PowerShell](/previous-versions//dn568025(v=technet.10))</span></span>

<span data-ttu-id="5646a-155">Per altre informazioni su Windows PowerShell, vedere [Riferimenti su PowerShell in Microsoft Teams](/powershell/module/teams/?view=teams-ps).</span><span class="sxs-lookup"><span data-stu-id="5646a-155">For more information about Windows PowerShell, see the [Microsoft Teams PowerShell reference](/powershell/module/teams/?view=teams-ps) for more information.</span></span>


## <a name="related-topics"></a><span data-ttu-id="5646a-156">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="5646a-156">Related topics</span></span>

[<span data-ttu-id="5646a-157">Abilitare o disabilitare l'invio di messaggi di posta elettronica in caso di modifica delle impostazioni di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="5646a-157">Enable or disable sending emails when Audio Conferencing settings change</span></span>](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[<span data-ttu-id="5646a-158">Inviare un messaggio di posta elettronica a un utente con le sue informazioni di audioconferenza</span><span class="sxs-lookup"><span data-stu-id="5646a-158">Send an email to a user with their Audio Conferencing information</span></span>](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)