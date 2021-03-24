---
title: Amministratori Configurare le impostazioni di Skype for Business per singoli utenti
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
description: 'Scopri come modificare le impostazioni di Skype for Business per singoli utenti, ad esempio: audio e videoconferenze, registrazione di chiamate e riunioni. '
ms.openlocfilehash: 5ddad9b1502d0a271c20c412731c9872e247be1b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093390"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="6b5fe-103">Amministratori: Configurare le impostazioni di Skype for Business online per singoli utenti</span><span class="sxs-lookup"><span data-stu-id="6b5fe-103">Admins: Configure Skype for Business settings for individual users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6b5fe-104">L'interfaccia di amministrazione di Microsoft Teams ha sostituito l'interfaccia di amministrazione di Skype for Business (portale legacy).</span><span class="sxs-lookup"><span data-stu-id="6b5fe-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="6b5fe-105">Tutte le impostazioni per la gestione di Skype for Business sono ora disponibili nell'interfaccia di amministrazione di Teams.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="6b5fe-106">Per gestire le funzionalità di Skype for Business nell'interfaccia di amministrazione di Teams, è necessario avere il ruolo di amministratore di [Azure AD](/azure/active-directory/roles/permissions-reference) dell'amministratore globale o dell'amministratore di Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-106">You must be assigned the [Azure AD admin role](/azure/active-directory/roles/permissions-reference) of Global admin or Skype for Business admin to manage Skype for Business features in the Teams admin center.</span></span> <span data-ttu-id="6b5fe-107">Per altre informazioni vedere [Gestire le impostazioni di Skype for Business nell'interfaccia di amministrazione di Microsoft Teams](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span><span class="sxs-lookup"><span data-stu-id="6b5fe-107">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](/MicrosoftTeams/skype-for-business-settings?bc=%2fskypeforbusiness%2fbreadcrumb%2ftoc.json&toc=%2fskypeforbusiness%2fsfbotoc%2ftoc.json).</span></span>

<span data-ttu-id="6b5fe-108">Questo articolo spiega come gli amministratori configurano Skype for Business per un numero limitato di utenti.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-108">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="6b5fe-109">Per eseguire questa procedura in blocco, sono stati inclusi collegamenti ai cmdlet Windows PowerShell che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-109">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="6b5fe-110">Per consentire (o bloccare) a tutti gli utenti dell'azienda di comunicare con persone esterne, vedere:</span><span class="sxs-lookup"><span data-stu-id="6b5fe-110">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="6b5fe-111">Consenti agli utenti di contattare utenti esterni di [Skype for Business:](allow-users-to-contact-external-skype-for-business-users.md)puoi consentire alla tua organizzazione di usare le funzionalità avanzate di Skype for Business (condividere desktop, cercare chi è online e così via) per comunicare con persone in una specifica azienda attendibile (federata).</span><span class="sxs-lookup"><span data-stu-id="6b5fe-111">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="6b5fe-112">L'articolo spiega anche come bloccare la comunicazione con domini specifici.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-112">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="6b5fe-113">[Consenti agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="6b5fe-113">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="6b5fe-114">Puoi consentire alla tua organizzazione di usare Skype for Business per cercare e istantanee persone che usano Skype, l'app gratuita.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-114">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="6b5fe-115">Configurare le impostazioni generali per un utente</span><span class="sxs-lookup"><span data-stu-id="6b5fe-115">Configure general settings for one user</span></span>
<span data-ttu-id="6b5fe-116"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="6b5fe-116"><a name="__toc325019204"> </a></span></span>

<span data-ttu-id="6b5fe-117">Per eseguire questa [procedura, è](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) necessario disporre delle autorizzazioni di amministratore.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-117">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="6b5fe-118">![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="6b5fe-118">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="6b5fe-119">Accedere con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-119">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="6b5fe-120">Scegli **Interfaccia di amministrazione** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-120">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="6b5fe-121">Scegli **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-121">Choose **Users**.</span></span>
    
    ![Nell'interfaccia di amministrazione di Skype for Business scegliere Utenti.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="6b5fe-123">Scegliere gli utenti da modificare.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-123">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="6b5fe-124">Nel riquadro destro, scegli **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-124">In the right panel, choose **Edit**.</span></span>
    
    ![Scegli l'icona di modifica.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="6b5fe-126">Nella pagina **Opzioni** generali selezionare o deselezionare la casella di controllo accanto alle caratteristiche da modificare e quindi scegliere **Salva.**</span><span class="sxs-lookup"><span data-stu-id="6b5fe-126">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="6b5fe-127">**Opzione**</span><span class="sxs-lookup"><span data-stu-id="6b5fe-127">**Option**</span></span>|<span data-ttu-id="6b5fe-128">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="6b5fe-128">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6b5fe-129">Audio e video HD</span><span class="sxs-lookup"><span data-stu-id="6b5fe-129">Audio and HD video</span></span>  <br/> |<span data-ttu-id="6b5fe-130">Consentire a questa persona di registrare riunioni audio, riunioni audio e video o non consentire loro di pianificare riunioni (nessuna).</span><span class="sxs-lookup"><span data-stu-id="6b5fe-130">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="6b5fe-131">Registrare conversazioni e riunioni</span><span class="sxs-lookup"><span data-stu-id="6b5fe-131">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="6b5fe-132">Scegli cosa può registrare questa persona.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-132">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="6b5fe-133">Questa opzione non è disponibile con Skype for Business Basic.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-133">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="6b5fe-134">Per la conformità, disattivare le caratteristiche non archiviate</span><span class="sxs-lookup"><span data-stu-id="6b5fe-134">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="6b5fe-135">Scegliere questa opzione se si è tenuti per legge a conservare le informazioni archiviate elettronicamente.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-135">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="6b5fe-136">Se si seleziona questa opzione, vengono disattivate [](/exchange/security-and-compliance/in-place-and-litigation-holds) le funzionalità che non vengono acquisite quando è configurato un blocco sul posto nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-136">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](/exchange/security-and-compliance/in-place-and-litigation-holds) set up in the Exchange admin center.</span></span> <span data-ttu-id="6b5fe-137">Disattiva le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="6b5fe-137">It turns off the following features:</span></span> <br/>  <span data-ttu-id="6b5fe-138">Trasferimento di file tramite messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="6b5fe-138">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="6b5fe-139">Pagine condivise di OneNote</span><span class="sxs-lookup"><span data-stu-id="6b5fe-139">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="6b5fe-140">Annotazioni di PowerPoint</span><span class="sxs-lookup"><span data-stu-id="6b5fe-140">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="6b5fe-141">Per configurare queste impostazioni in blocco, usare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-141">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="6b5fe-142">Vedere [Configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="6b5fe-142">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="6b5fe-143">Bloccare le comunicazioni esterne</span><span class="sxs-lookup"><span data-stu-id="6b5fe-143">Block external communications</span></span>
<span data-ttu-id="6b5fe-144"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="6b5fe-144"><a name="__toc325019206"> </a></span></span>

<span data-ttu-id="6b5fe-145">Dopo aver [lasciato che gli utenti di Skype for Business](let-skype-for-business-users-add-skype-contacts.md) aggiungessi contatti Skype per tutti gli utenti della tua azienda, puoi bloccare in modo selettivo le comunicazioni esterne per specifici utenti usando questa procedura.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-145">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="6b5fe-146">Scegliere **Utenti**, selezionare gli utenti di cui si vogliono disabilitare le impostazioni e quindi scegliere **Modifica** ![ modifica ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .</span><span class="sxs-lookup"><span data-stu-id="6b5fe-146">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="6b5fe-147">Scegliere **Comunicazioni esterne** e quindi deselezionare le opzioni appropriate:</span><span class="sxs-lookup"><span data-stu-id="6b5fe-147">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="6b5fe-148">**Utenti skype for business** esterni: deselezionare questa casella se non si vuole che l'utente sia in grado di comunicare con gli utenti Skype for Business nei domini federati.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-148">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="6b5fe-149">**Utenti Skype esterni:** deselezionare questa casella se non si vuole che l'utente sia in grado di comunicare con le persone che usano l'app freeSkype.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-149">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="6b5fe-150">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-150">Click **Save**.</span></span>
    
<span data-ttu-id="6b5fe-151">Per configurare queste impostazioni in blocco, usare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-151">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="6b5fe-152">Vedere [Configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="6b5fe-152">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="6b5fe-153">Modificare le impostazioni dei servizi di audioconferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="6b5fe-153">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="6b5fe-154"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="6b5fe-154"><a name="__toc314837483"> </a></span></span>

1. <span data-ttu-id="6b5fe-155">Scegliere **Utenti**, selezionare l'utente di cui si desidera modificare le impostazioni di audioconferenza e quindi scegliere **Modifica** ![ modifica ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .</span><span class="sxs-lookup"><span data-stu-id="6b5fe-155">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="6b5fe-156">Scegliere **Audioconferenza,** selezionare il provider di servizi di audioconferenza, digitare o modificare le informazioni richieste e quindi fare clic su **Salva.**</span><span class="sxs-lookup"><span data-stu-id="6b5fe-156">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="6b5fe-157">**Impostazioni delle audioconferenze**</span><span class="sxs-lookup"><span data-stu-id="6b5fe-157">**Audio conferencing setting**</span></span>|<span data-ttu-id="6b5fe-158">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="6b5fe-158">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6b5fe-159">**Nome del provider**</span><span class="sxs-lookup"><span data-stu-id="6b5fe-159">**Provider name**</span></span> <br/> |<span data-ttu-id="6b5fe-160">Scegliere il provider nell'elenco.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-160">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="6b5fe-161">**Numero a pagamento** (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6b5fe-161">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="6b5fe-162">Per un provider di servizi di audioconferenza di terze parti, questi numeri di telefono sono quelli ricevuti dal provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="6b5fe-163">Se l'utente sta utilizzando Microsoft come provider di servizi di audioconferenza, questi saranno i numeri impostati sul ponte per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="6b5fe-164">Formattare i numeri come si vuole che vengano visualizzati nelle convocazioni riunione Skype for Business e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="6b5fe-165">**Numero verde**</span><span class="sxs-lookup"><span data-stu-id="6b5fe-165">**Toll-free number**</span></span> <br/> |<span data-ttu-id="6b5fe-166">Per un provider di servizi di audioconferenza di terze parti, questi numeri di telefono sono quelli ricevuti dal provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-166">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="6b5fe-167">Se l'utente sta utilizzando Microsoft come provider di servizi di audioconferenza, questi saranno i numeri impostati sul ponte per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-167">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="6b5fe-168">Formattare i numeri come si vuole che vengano visualizzati nelle convocazioni riunione Skype for Business e Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-168">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="6b5fe-169">**ID conferenza e PIN** (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="6b5fe-169">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="6b5fe-170">Il PIN del partecipante, o codice conferenza, usato per partecipare alle riunioni pianificate da questo utente e fornite da un provider di servizi di audioconferenza di terze parti.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-170">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="6b5fe-171">Se l'utente usa Microsoft come provider di servizi di audioconferenza, non sarà necessario.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-171">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="6b5fe-172">Per configurare queste impostazioni in blocco, usare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="6b5fe-172">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="6b5fe-173">Vedere [Impostare i numeri di telefono inclusi in Inviti](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) Configurare il computer per [Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="6b5fe-173">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="6b5fe-174">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="6b5fe-174">Related topics</span></span> 

[<span data-ttu-id="6b5fe-175">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="6b5fe-175">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

<span data-ttu-id="6b5fe-176">[Licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="6b5fe-176">[Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>
  
  
