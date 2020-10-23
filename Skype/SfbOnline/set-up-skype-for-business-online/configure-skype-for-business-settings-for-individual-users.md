---
title: Gli amministratori configurano le impostazioni di Skype for business per singoli utenti
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
description: 'Informazioni su come modificare le impostazioni di Skype for business per singoli utenti, ad esempio: conferenze audio e video, registrazione di chiamate e riunioni. '
ms.openlocfilehash: 546e693dd1fb6e9becf7119c35d7b00875eda99a
ms.sourcegitcommit: 1db39fde090809d9abc6d7346dda55814d88993a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/23/2020
ms.locfileid: "48739174"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="0f9eb-103">Amministratori: Configurare le impostazioni di Skype for Business online per singoli utenti</span><span class="sxs-lookup"><span data-stu-id="0f9eb-103">Admins: Configure Skype for Business settings for individual users</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f9eb-104">L'interfaccia di amministrazione di Microsoft Teams ha sostituito l'interfaccia di amministrazione di Skype for business (portale legacy).</span><span class="sxs-lookup"><span data-stu-id="0f9eb-104">The Microsoft Teams admin center has replaced the Skype for Business admin center (Legacy portal).</span></span> <span data-ttu-id="0f9eb-105">Tutte le impostazioni per la gestione di Skype for business si trovano ora nell'interfaccia di amministrazione di teams.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-105">All settings for managing Skype for Business are now in the Teams admin center.</span></span> <span data-ttu-id="0f9eb-106">Per altre informazioni, vedere [gestire le impostazioni di Skype for business nell'interfaccia di amministrazione di Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="0f9eb-106">To learn more, see [Manage Skype for Business settings in the Microsoft Teams admin center](https://docs.microsoft.com/MicrosoftTeams/skype-for-business-settings?toc=/skypeforbusiness/sfbotoc/toc.json&bc=/skypeforbusiness/breadcrumb/toc.json).</span></span>

<span data-ttu-id="0f9eb-107">Questo articolo spiega in che modo gli amministratori configurano Skype for business per un numero limitato di utenti.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-107">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="0f9eb-108">Per eseguire questa procedura in blocco, sono stati inclusi collegamenti ai cmdlet di Windows PowerShell che è possibile usare.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-108">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="0f9eb-109">Per consentire (o bloccare) tutti gli utenti dell'azienda di comunicare con persone esterne, vedere:</span><span class="sxs-lookup"><span data-stu-id="0f9eb-109">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="0f9eb-110">[Consentire agli utenti di contattare utenti Skype for business esterni](allow-users-to-contact-external-skype-for-business-users.md): è possibile consentire all'organizzazione di usare le funzionalità avanzate di Skype for business (condivisione di desktop, cercare chi è online e così via) per comunicare con persone in una specifica azienda attendibile (federata).</span><span class="sxs-lookup"><span data-stu-id="0f9eb-110">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="0f9eb-111">L'articolo spiega anche come bloccare la comunicazione con domini specifici.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-111">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="0f9eb-112">[Consentire agli utenti di Skype for business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="0f9eb-112">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="0f9eb-113">Puoi consentire all'organizzazione di usare Skype for business per cercare e inviare messaggi istantanei agli utenti che usano Skype, l'app gratuita.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-113">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="0f9eb-114">Configurare le impostazioni generali per un utente</span><span class="sxs-lookup"><span data-stu-id="0f9eb-114">Configure general settings for one user</span></span>
<span data-ttu-id="0f9eb-115"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="0f9eb-115"><a name="__toc325019204"> </a></span></span>

<span data-ttu-id="0f9eb-116">Per eseguire questa procedura, è necessario disporre [delle autorizzazioni di amministratore](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) .</span><span class="sxs-lookup"><span data-stu-id="0f9eb-116">You must have [admin permissions](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="0f9eb-117">![Icona che mostra il logo di Skype for Business](../images/sfb-logo-30x30.png) **Uso dell'interfaccia di amministrazione di Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="0f9eb-117">![An icon showing the Skype for Business logo](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="0f9eb-118">Accedere con l'account di lavoro o dell'Istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-118">Sign in with your work or school account.</span></span>
    
2. <span data-ttu-id="0f9eb-119">Scegli **Interfaccia di amministrazione** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-119">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="0f9eb-120">Scegli **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-120">Choose **Users**.</span></span>
    
    ![Nell'interfaccia di amministrazione di Skype for Business Scegli utenti.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="0f9eb-122">Scegliere gli utenti che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-122">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="0f9eb-123">Nel riquadro destro, scegli **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-123">In the right panel, choose **Edit**.</span></span>
    
    ![Scegli l'icona di modifica.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="0f9eb-125">Nella pagina Opzioni **generali** selezionare o deselezionare la casella di controllo accanto alle funzionalità che si desidera modificare e quindi scegliere **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-125">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="0f9eb-126">**Opzione**</span><span class="sxs-lookup"><span data-stu-id="0f9eb-126">**Option**</span></span>|<span data-ttu-id="0f9eb-127">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="0f9eb-127">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0f9eb-128">Audio e video HD</span><span class="sxs-lookup"><span data-stu-id="0f9eb-128">Audio and HD video</span></span>  <br/> |<span data-ttu-id="0f9eb-129">Consentire a questa persona di registrare riunioni audio, riunioni audio e video o non consentire loro di programmare riunioni (nessuna).</span><span class="sxs-lookup"><span data-stu-id="0f9eb-129">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="0f9eb-130">Registrare conversazioni e riunioni</span><span class="sxs-lookup"><span data-stu-id="0f9eb-130">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="0f9eb-131">Scegliere ciò che questa persona può registrare.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-131">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="0f9eb-132">Questa opzione non è disponibile con Skype for Business Basic.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-132">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="0f9eb-133">Per la conformità, disattivare le funzionalità non archiviate</span><span class="sxs-lookup"><span data-stu-id="0f9eb-133">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="0f9eb-134">Scegliere questa opzione se si è legalmente tenuti a conservare le informazioni archiviate elettronicamente.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-134">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="0f9eb-135">Se si seleziona questa opzione, vengono disattivate le funzionalità non acquisite quando si dispone di un [blocco sul posto](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-135">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/library/ff637980%28v=exchg.150%29.aspx) set up in the Exchange admin center.</span></span> <span data-ttu-id="0f9eb-136">Vengono disattivate le caratteristiche seguenti:</span><span class="sxs-lookup"><span data-stu-id="0f9eb-136">It turns off the following features:</span></span> <br/>  <span data-ttu-id="0f9eb-137">Trasferimento di file tramite messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="0f9eb-137">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="0f9eb-138">Pagine condivise di OneNote</span><span class="sxs-lookup"><span data-stu-id="0f9eb-138">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="0f9eb-139">Annotazioni di PowerPoint</span><span class="sxs-lookup"><span data-stu-id="0f9eb-139">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="0f9eb-140">Per configurare queste impostazioni in blocco, usare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-140">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="0f9eb-141">Vedere [configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="0f9eb-141">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="0f9eb-142">Bloccare le comunicazioni esterne</span><span class="sxs-lookup"><span data-stu-id="0f9eb-142">Block external communications</span></span>
<span data-ttu-id="0f9eb-143"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="0f9eb-143"><a name="__toc325019206"> </a></span></span>

<span data-ttu-id="0f9eb-144">Dopo aver [lasciato gli utenti di Skype for business ad aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md) per tutti i membri della società, è possibile bloccare selettivamente le comunicazioni esterne per individui specifici con questi passaggi.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-144">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="0f9eb-145">Scegliere **utenti**, selezionare gli utenti di cui si vogliono disabilitare le impostazioni e quindi scegliere **modifica** ![ modifica ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .</span><span class="sxs-lookup"><span data-stu-id="0f9eb-145">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="0f9eb-146">Scegliere **comunicazioni esterne**e quindi deselezionare le opzioni appropriate:</span><span class="sxs-lookup"><span data-stu-id="0f9eb-146">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="0f9eb-147">**Utenti Skype for business esterni**: deselezionare questa casella se non si vuole che l'utente possa comunicare con gli utenti di Skype for business nei domini federati.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-147">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="0f9eb-148">**Utenti Skype esterni**: deselezionare questa casella se non si vuole che l'utente possa comunicare con utenti che usano l'app freeSkype.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-148">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="0f9eb-149">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-149">Click **Save**.</span></span>
    
<span data-ttu-id="0f9eb-150">Per configurare queste impostazioni in blocco, usare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-150">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="0f9eb-151">Vedere [configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="0f9eb-151">See [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="0f9eb-152">Modificare le impostazioni dei servizi di audioconferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="0f9eb-152">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="0f9eb-153"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="0f9eb-153"><a name="__toc314837483"> </a></span></span>

1. <span data-ttu-id="0f9eb-154">Scegliere **utenti**, selezionare l'utente di cui si desidera modificare le impostazioni di conferenza audio da usare e quindi scegliere **modifica** ![ modifica ](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png) .</span><span class="sxs-lookup"><span data-stu-id="0f9eb-154">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="0f9eb-155">Scegliere **audioconferenza**, selezionare il proprio provider di servizi di audioconferenza, digitare o modificare le informazioni richieste e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-155">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="0f9eb-156">**Impostazioni delle audioconferenze**</span><span class="sxs-lookup"><span data-stu-id="0f9eb-156">**Audio conferencing setting**</span></span>|<span data-ttu-id="0f9eb-157">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="0f9eb-157">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0f9eb-158">**Nome del provider**</span><span class="sxs-lookup"><span data-stu-id="0f9eb-158">**Provider name**</span></span> <br/> |<span data-ttu-id="0f9eb-159">Scegliere il provider dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-159">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="0f9eb-160">**Numero a pagamento** (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="0f9eb-160">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="0f9eb-161">Per gli ACP di terze parti, questi numeri di telefono sono quelli ricevuti dal provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-161">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="0f9eb-162">Se l'utente sta utilizzando Microsoft come provider di servizi di audioconferenza, questi saranno i numeri impostati sul ponte per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-162">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="0f9eb-163">Formattare i numeri che si desidera vengano visualizzati in richieste di riunione di Skype for business e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-163">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="0f9eb-164">**Numero verde**</span><span class="sxs-lookup"><span data-stu-id="0f9eb-164">**Toll-free number**</span></span> <br/> |<span data-ttu-id="0f9eb-165">Per gli ACP di terze parti, questi numeri di telefono sono quelli ricevuti dal provider di servizi di audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-165">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="0f9eb-166">Se l'utente sta utilizzando Microsoft come provider di servizi di audioconferenza, questi saranno i numeri impostati sul ponte per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-166">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="0f9eb-167">Formattare i numeri che si desidera vengano visualizzati in richieste di riunione di Skype for business e Microsoft teams.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-167">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="0f9eb-168">**ID conferenza e pin** (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="0f9eb-168">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="0f9eb-169">Il PIN partecipante o il codice conferenza usato per partecipare alle riunioni pianificate da questo utente e fornite da un provider di servizi di audioconferenza di terze parti.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-169">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="0f9eb-170">Se l'utente usa Microsoft come provider di servizi di audioconferenza, non sarà necessario.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-170">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="0f9eb-171">Per configurare queste impostazioni in blocco, usare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f9eb-171">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="0f9eb-172">Vedere [impostare i numeri di telefono inclusi in invita](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [configurare il computer per Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="0f9eb-172">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md) [Set up your computer for Windows PowerShell](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="0f9eb-173">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="0f9eb-173">Related topics</span></span> 

[<span data-ttu-id="0f9eb-174">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="0f9eb-174">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

<span data-ttu-id="0f9eb-175">[Licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="0f9eb-175">[Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>
  
  
 
