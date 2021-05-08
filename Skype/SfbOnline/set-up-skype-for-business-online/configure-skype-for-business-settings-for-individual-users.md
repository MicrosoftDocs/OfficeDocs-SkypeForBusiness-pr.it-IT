---
title: Amministratori Configurare le Skype for Business per singoli utenti
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Setup
- LIL_Placement
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
description: 'Informazioni su come modificare le impostazioni Skype for Business per singoli utenti, ad esempio audio e videoconferenze, registrazione di chiamate e riunioni. '
ms.openlocfilehash: 0123f285101b8d7190dd7450ddb876a136de13ce
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52237532"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="453b8-103">Amministratori: Configurare le impostazioni di Skype for Business online per singoli utenti</span><span class="sxs-lookup"><span data-stu-id="453b8-103">Admins: Configure Skype for Business settings for individual users</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!IMPORTANT]
> <span data-ttu-id="453b8-104">L Microsoft Teams di amministrazione ha sostituito l'Skype for Business di amministrazione (portale legacy).</span><span class="sxs-lookup"><span data-stu-id="453b8-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="453b8-105">Tutte le impostazioni per la Skype for Business sono ora disponibili nell'Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="453b8-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="453b8-106">È necessario avere il ruolo di amministratore di [Azure AD](/azure/active-directory/roles/permissions-reference) di Amministratore globale o amministratore Skype for Business per gestire Skype for Business funzionalità di Teams di amministrazione.</span><span class="sxs-lookup"><span data-stu-id="453b8-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="453b8-107">Per altre informazioni vedere [Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="453b8-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="453b8-108">Questo articolo spiega come gli amministratori configurano Skype for Business per un numero limitato di utenti.</span><span class="sxs-lookup"><span data-stu-id="453b8-108">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="453b8-109">Per eseguire questa procedura in blocco, sono stati inclusi collegamenti ai Windows PowerShell cmdlet che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="453b8-109">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="453b8-110">Per consentire (o bloccare) a tutti gli utenti dell'azienda di comunicare con persone esterne, vedere:</span><span class="sxs-lookup"><span data-stu-id="453b8-110">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="453b8-111">Consentire agli utenti di contattare utenti Skype for Business [esterni:](allow-users-to-contact-external-skype-for-business-users.md)è possibile consentire all'organizzazione di usare funzionalità avanzate di Skype for Business (condividere desktop, cercare utenti online e così via) per comunicare con persone in una specifica azienda attendibile (federata).</span><span class="sxs-lookup"><span data-stu-id="453b8-111">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="453b8-112">L'articolo spiega anche come bloccare la comunicazione con domini specifici.</span><span class="sxs-lookup"><span data-stu-id="453b8-112">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="453b8-113">[Consentire Skype for Business utenti di aggiungere Skype contatti](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="453b8-113">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="453b8-114">È possibile consentire all'organizzazione di usare Skype for Business per la ricerca e la messaggistica istantanea di persone che usano Skype, l'app gratuita.</span><span class="sxs-lookup"><span data-stu-id="453b8-114">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="453b8-115">Configurare le impostazioni generali per un utente</span><span class="sxs-lookup"><span data-stu-id="453b8-115">Configure general settings for one user</span></span>
<span data-ttu-id="453b8-116"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="453b8-116"><a name="__toc325019204"> </a></span></span>

<span data-ttu-id="453b8-117">Per eseguire questa [procedura, è](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) necessario disporre delle autorizzazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="453b8-117">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="453b8-118">![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="453b8-118">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="453b8-119">Accedere con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="453b8-119">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="453b8-120">Scegli **Interfaccia di amministrazione** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="453b8-120">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="453b8-121">Scegli **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="453b8-121">Choose **Users**.</span></span>
    
    ![Nell'Skype for Business di amministrazione scegliere Utenti.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="453b8-123">Scegliere gli utenti da modificare.</span><span class="sxs-lookup"><span data-stu-id="453b8-123">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="453b8-124">Nel riquadro destro, scegli **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="453b8-124">In the right panel, choose **Edit**.</span></span>
    
    ![Scegli l'icona di modifica.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="453b8-126">Nella pagina **Opzioni** generali selezionare o deselezionare la casella di controllo accanto alle caratteristiche da modificare e quindi scegliere **Salva.**</span><span class="sxs-lookup"><span data-stu-id="453b8-126">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="453b8-127">**Opzione**</span><span class="sxs-lookup"><span data-stu-id="453b8-127">**Option**</span></span>|<span data-ttu-id="453b8-128">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="453b8-128">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="453b8-129">Audio e video HD</span><span class="sxs-lookup"><span data-stu-id="453b8-129">Audio and HD video</span></span>  <br/> |<span data-ttu-id="453b8-130">Consentire a questa persona di registrare riunioni audio, riunioni audio e video o non consentire loro di pianificare riunioni (nessuna).</span><span class="sxs-lookup"><span data-stu-id="453b8-130">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="453b8-131">Registrare conversazioni e riunioni</span><span class="sxs-lookup"><span data-stu-id="453b8-131">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="453b8-132">Scegli cosa può registrare questa persona.</span><span class="sxs-lookup"><span data-stu-id="453b8-132">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="453b8-133">Questa opzione non è disponibile con Skype for Business Basic.</span><span class="sxs-lookup"><span data-stu-id="453b8-133">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="453b8-134">Per la conformità, disattivare le caratteristiche non archiviate</span><span class="sxs-lookup"><span data-stu-id="453b8-134">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="453b8-135">Scegliere questa opzione se si è tenuti per legge a conservare le informazioni archiviate elettronicamente.</span><span class="sxs-lookup"><span data-stu-id="453b8-135">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="453b8-136">Se si seleziona questa opzione, le funzionalità [](/exchange/security-and-compliance/in-place-and-litigation-holds) che non vengono acquisite quando è configurato un blocco sul posto nell'interfaccia di amministrazione Exchange locale.</span><span class="sxs-lookup"><span data-stu-id="453b8-136">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](/exchange/security-and-compliance/in-place-and-litigation-holds) set up in the Exchange admin center.</span></span> <span data-ttu-id="453b8-137">Disattiva le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="453b8-137">It turns off the following features:</span></span> <br/>  <span data-ttu-id="453b8-138">Trasferimento di file tramite messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="453b8-138">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="453b8-139">Pagine condivise di OneNote</span><span class="sxs-lookup"><span data-stu-id="453b8-139">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="453b8-140">Annotazioni di PowerPoint</span><span class="sxs-lookup"><span data-stu-id="453b8-140">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="453b8-141">Per configurare queste impostazioni in blocco, usare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="453b8-141">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="453b8-142">Vedere [Configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="453b8-142">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="453b8-143">Bloccare le comunicazioni esterne</span><span class="sxs-lookup"><span data-stu-id="453b8-143">Block external communications</span></span>
<span data-ttu-id="453b8-144"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="453b8-144"><a name="__toc325019206"> </a></span></span>

<span data-ttu-id="453b8-145">Dopo aver [Skype for Business](let-skype-for-business-users-add-skype-contacts.md) utenti di aggiungere Skype contatti per tutti gli utenti dell'azienda, è possibile bloccare in modo selettivo le comunicazioni esterne per utenti specifici usando questa procedura.</span><span class="sxs-lookup"><span data-stu-id="453b8-145">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="453b8-146">Scegliere **Utenti**, selezionare gli utenti di cui si vogliono disabilitare le impostazioni e quindi scegliere **Modifica** ![ modifica ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .</span><span class="sxs-lookup"><span data-stu-id="453b8-146">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="453b8-147">Scegliere **Comunicazioni esterne** e quindi deselezionare le opzioni appropriate:</span><span class="sxs-lookup"><span data-stu-id="453b8-147">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="453b8-148">**Utenti Skype for Business** esterni: deselezionare questa casella se non si vuole che l'utente sia in grado di comunicare con Skype for Business utenti nei domini federati.</span><span class="sxs-lookup"><span data-stu-id="453b8-148">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="453b8-149">**Utenti Skype** esterni: deselezionare questa casella se non si vuole che l'utente sia in grado di comunicare con le persone che usano l'app freeSkype.</span><span class="sxs-lookup"><span data-stu-id="453b8-149">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="453b8-150">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="453b8-150">Click **Save**.</span></span>
    
<span data-ttu-id="453b8-151">Per configurare queste impostazioni in blocco, usare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="453b8-151">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="453b8-152">Vedere [Configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="453b8-152">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="453b8-153">Modificare le impostazioni dei servizi di audioconferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="453b8-153">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="453b8-154"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="453b8-154"><a name="__toc314837483"> </a></span></span>

1. <span data-ttu-id="453b8-155">Scegliere **Utenti**, selezionare l'utente di cui si desidera modificare le impostazioni di audioconferenza e quindi scegliere **Modifica** ![ modifica ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .</span><span class="sxs-lookup"><span data-stu-id="453b8-155">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="453b8-156">Scegliere **Audioconferenza,** selezionare il provider di servizi di audioconferenza, digitare o modificare le informazioni richieste e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="453b8-156">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="453b8-157">**Impostazioni delle audioconferenze**</span><span class="sxs-lookup"><span data-stu-id="453b8-157">**Audio conferencing setting**</span></span>|<span data-ttu-id="453b8-158">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="453b8-158">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="453b8-159">**Nome del provider**</span><span class="sxs-lookup"><span data-stu-id="453b8-159">**Provider name**</span></span> <br/> |<span data-ttu-id="453b8-160">Scegliere il provider nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="453b8-160">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="453b8-161">**Numero a pagamento** (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="453b8-161">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="453b8-162">Per un provider di servizi di audioconferenza di terze parti, questi numeri di telefono sono quelli ricevuti dal provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="453b8-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="453b8-163">Se l'utente sta utilizzando Microsoft come provider di servizi di audioconferenza, questi saranno i numeri impostati sul ponte per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="453b8-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="453b8-164">Formattare i numeri come si vuole che vengano visualizzati nelle convocazioni di riunione Skype for Business e Microsoft Teams riunione.</span><span class="sxs-lookup"><span data-stu-id="453b8-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="453b8-165">**Numero verde**</span><span class="sxs-lookup"><span data-stu-id="453b8-165">**Toll-free number**</span></span> <br/> |<span data-ttu-id="453b8-166">Per un provider di servizi di audioconferenza di terze parti, questi numeri di telefono sono quelli ricevuti dal provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="453b8-166">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="453b8-167">Se l'utente sta utilizzando Microsoft come provider di servizi di audioconferenza, questi saranno i numeri impostati sul ponte per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="453b8-167">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="453b8-168">Formattare i numeri come si vuole che vengano visualizzati nelle convocazioni di riunione Skype for Business e Microsoft Teams riunione.</span><span class="sxs-lookup"><span data-stu-id="453b8-168">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="453b8-169">**ID conferenza e PIN** (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="453b8-169">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="453b8-170">Il PIN del partecipante, o codice conferenza, usato per partecipare alle riunioni pianificate da questo utente e fornite da un provider di servizi di audioconferenza di terze parti.</span><span class="sxs-lookup"><span data-stu-id="453b8-170">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="453b8-171">Se l'utente usa Microsoft come provider di servizi di audioconferenza, non sarà necessario.</span><span class="sxs-lookup"><span data-stu-id="453b8-171">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="453b8-172">Per configurare queste impostazioni in blocco, usare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="453b8-172">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="453b8-173">Vedere [Impostare i numeri di telefono inclusi in Inviti](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) Configurare il computer per [Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="453b8-173">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="453b8-174">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="453b8-174">Related topics</span></span> 

[<span data-ttu-id="453b8-175">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="453b8-175">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

<span data-ttu-id="453b8-176">[Licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="453b8-176">[Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>
  
  
