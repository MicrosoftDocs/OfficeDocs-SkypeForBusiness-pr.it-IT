---
title: Gli amministratori configurare Skype per le impostazioni di Business per singoli utenti
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: 'Informazioni su come modificare Skype per le impostazioni di Business per singoli utenti, ad esempio: conferenze Audio e video, la registrazione delle chiamate e riunioni. '
ms.openlocfilehash: 0623c6dd913316584bd38e4076317c050c4a2812
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/15/2017
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="29ae3-103">Gli amministratori: Configurare Skype per le impostazioni di Business per singoli utenti</span><span class="sxs-lookup"><span data-stu-id="29ae3-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="29ae3-104">In questo articolo viene illustrato come gli amministratori configurare Skype for Business per un numero limitato di utenti.</span><span class="sxs-lookup"><span data-stu-id="29ae3-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="29ae3-105">Per eseguire la procedura seguente in blocco, è stata inclusa collegamenti a è possibile utilizzare i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29ae3-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="29ae3-106">Per consentire o bloccare tutti gli utenti nell'organizzazione di comunicare con utenti esterni, vedere:</span><span class="sxs-lookup"><span data-stu-id="29ae3-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="29ae3-107">[Consenti agli utenti di contatti esterni Skype per gli utenti aziendali](allow-users-to-contact-external-skype-for-business-users.md): È possibile consentire all'organizzazione di utilizzare avanzate Skype per le funzionalità di Business (condivisione desktop, interfaccia per chi è in linea, ecc) comunicare con persone in una determinata attendibili business (federati).</span><span class="sxs-lookup"><span data-stu-id="29ae3-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="29ae3-108">L'articolo viene inoltre illustrato come bloccare la comunicazione con i domini specifici.</span><span class="sxs-lookup"><span data-stu-id="29ae3-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="29ae3-109">[Consentire Skype per gli utenti aziendali di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="29ae3-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="29ae3-110">È possibile consentire l'organizzazione utilizza Skype per cercare di lavoro e utenti di messaggistica immediata che utilizzano Skype, gratuitamente l'app.</span><span class="sxs-lookup"><span data-stu-id="29ae3-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="29ae3-111">Configurare le impostazioni generali per un utente</span><span class="sxs-lookup"><span data-stu-id="29ae3-111">Configure general settings for one user</span></span>
<span data-ttu-id="29ae3-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="29ae3-112"></span></span>

<span data-ttu-id="29ae3-113">È necessario disporre [delle autorizzazioni di amministratore](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) per eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="29ae3-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>
  
1. <span data-ttu-id="29ae3-114">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="29ae3-114">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="29ae3-115">Scegliere **Admin Center** > **Skype per le aziende**.</span><span class="sxs-lookup"><span data-stu-id="29ae3-115">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="29ae3-116">Scegliere **utenti**.</span><span class="sxs-lookup"><span data-stu-id="29ae3-116">Choose **Users**.</span></span>
    
    ![Skype per interfaccia di amministrazione di Business, scegliere utenti.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="29ae3-118">Scegliere gli utenti che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="29ae3-118">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="29ae3-119">Riquadro destro fare clic su **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="29ae3-119">In the right panel, choose **Edit**.</span></span>
    
    ![Scegliere l'icona di modifica.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="29ae3-121">Nella pagina Opzioni **Generale** , selezionare o deselezionare la casella di controllo accanto alle funzionalità che si desidera modificare e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="29ae3-121">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="29ae3-122">**Opzione**</span><span class="sxs-lookup"><span data-stu-id="29ae3-122">**Option**</span></span>|<span data-ttu-id="29ae3-123">**Ulteriori informazioni**</span><span class="sxs-lookup"><span data-stu-id="29ae3-123">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="29ae3-124">Audio e video HD</span><span class="sxs-lookup"><span data-stu-id="29ae3-124">Audio and HD video</span></span>  <br/> |<span data-ttu-id="29ae3-125">Consentire questa persona di registrare le riunioni audio, audio e video alle riunioni o non consentire loro di pianificare qualsiasi meeetings (nessuno).</span><span class="sxs-lookup"><span data-stu-id="29ae3-125">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meeetings (none).</span></span>  <br/> |
|<span data-ttu-id="29ae3-126">Registrare conversazioni e riunioni</span><span class="sxs-lookup"><span data-stu-id="29ae3-126">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="29ae3-127">Scegliere quali questa persona è consentita registrare.</span><span class="sxs-lookup"><span data-stu-id="29ae3-127">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="29ae3-128">Questa opzione non è disponibile con Skype per Business Basic.</span><span class="sxs-lookup"><span data-stu-id="29ae3-128">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="29ae3-129">Per motivi di conformità, disattivare le funzionalità non archiviate</span><span class="sxs-lookup"><span data-stu-id="29ae3-129">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="29ae3-130">Scegliere questa opzione se si è obbligate per legge a conservare le informazioni archiviate in formato elettronico.</span><span class="sxs-lookup"><span data-stu-id="29ae3-130">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="29ae3-131">Se si seleziona questa opzione viene disattivata la funzionalità che non sono state acquisite in presenza di un' [Archiviazione sul posto](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) configurato nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="29ae3-131">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in in the Exchange admin center.</span></span> <span data-ttu-id="29ae3-132">Disattiva le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="29ae3-132">It turns off the following features:</span></span> <br/>  <span data-ttu-id="29ae3-133">Trasferimento di file tramite messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="29ae3-133">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="29ae3-134">Pagine condivise di OneNote</span><span class="sxs-lookup"><span data-stu-id="29ae3-134">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="29ae3-135">Annotazioni di PowerPoint</span><span class="sxs-lookup"><span data-stu-id="29ae3-135">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="29ae3-136">Per configurare queste impostazioni in blocco, utilizzare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29ae3-136">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="29ae3-137">Vedere [gestione dei criteri in Skype Business online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="29ae3-137">See [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="29ae3-138">Blocca comunicazioni esterne</span><span class="sxs-lookup"><span data-stu-id="29ae3-138">Block external communications</span></span>
<span data-ttu-id="29ae3-139"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="29ae3-139"></span></span>

<span data-ttu-id="29ae3-140">Dopo aver [Skype consente agli utenti aziendali aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md) per tutti gli utenti della società, è possibile bloccare in modo selettivo comunicazioni esterne per specifici utenti attenendosi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="29ae3-140">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="29ae3-141">Selezione **utenti**, selezionare gli utenti il cui si desidera disabilitare le impostazioni e quindi fare clic su **Modifica** ![modifica](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="29ae3-141">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="29ae3-142">Scegliere **comunicazioni esterne**e quindi deselezionare le opzioni desiderate:</span><span class="sxs-lookup"><span data-stu-id="29ae3-142">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
  - <span data-ttu-id="29ae3-143">**Skype esterna per gli utenti aziendali**: deselezionare questa casella se non si desidera che l'utente di comunicare con Skype per utenti Business nei domini federati.</span><span class="sxs-lookup"><span data-stu-id="29ae3-143">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
  - <span data-ttu-id="29ae3-144">**Gli utenti esterni Skype**: deselezionare questa casella se non si desidera che l'utente di comunicare con persone che utilizzano l'app freeSkype.</span><span class="sxs-lookup"><span data-stu-id="29ae3-144">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="29ae3-145">Fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="29ae3-145">Click **Save**.</span></span>
    
<span data-ttu-id="29ae3-146">Per configurare queste impostazioni in blocco, utilizzare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29ae3-146">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="29ae3-147">Vedere [gestione delle comunicazioni in Skype Business online con organizzazioni e agli utenti esterni](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="29ae3-147">See [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="29ae3-148">Modificare le impostazioni di conferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="29ae3-148">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="29ae3-149"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="29ae3-149"></span></span>

1. <span data-ttu-id="29ae3-150">Selezione **utenti**, selezionare l'utente di cui si desidera per modificare, le impostazioni di audioconferenza e quindi fare clic su **Modifica** ![modifica](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="29ae3-150">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="29ae3-151">Scegliere **servizi di conferenza Audio**, selezionare il provider di servizi di conferenza audio, digitare o modificare le informazioni richieste e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="29ae3-151">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="29ae3-152">**Impostazioni delle audioconferenze**</span><span class="sxs-lookup"><span data-stu-id="29ae3-152">**Audio conferencing setting**</span></span>|<span data-ttu-id="29ae3-153">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="29ae3-153">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="29ae3-154">**Nome del provider**</span><span class="sxs-lookup"><span data-stu-id="29ae3-154">**Provider name**</span></span> <br/> |<span data-ttu-id="29ae3-155">Scegliere il provider dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="29ae3-155">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="29ae3-156">**Numero a pagamento** (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="29ae3-156">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="29ae3-157">Per un'AUDIOCONFERENZA di terze parti, questi numeri di telefono sono forniti dal provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="29ae3-157">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="29ae3-158">Se l'utente sta utilizzando Microsoft come provider di servizi di conferenza audio, queste saranno numeri che vengono impostati su ponte per conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="29ae3-158">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="29ae3-159">Formattare i numeri che si desidera che vengano visualizzate in Skype per Business e Microsoft Teams convocazioni di riunione.</span><span class="sxs-lookup"><span data-stu-id="29ae3-159">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="29ae3-160">**Numero verde**</span><span class="sxs-lookup"><span data-stu-id="29ae3-160">**Toll-free number**</span></span> <br/> |<span data-ttu-id="29ae3-161">Per un'AUDIOCONFERENZA di terze parti, questi numeri di telefono sono forniti dal provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="29ae3-161">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="29ae3-162">Se l'utente sta utilizzando Microsoft come provider di servizi di conferenza audio, queste saranno numeri che vengono impostati su ponte per conferenze audio.</span><span class="sxs-lookup"><span data-stu-id="29ae3-162">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="29ae3-163">Formattare i numeri che si desidera che vengano visualizzate in Skype per Business e Microsoft Teams convocazioni di riunione.</span><span class="sxs-lookup"><span data-stu-id="29ae3-163">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="29ae3-164">**ID conferenza e PIN** (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="29ae3-164">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="29ae3-165">Il partecipante PIN o conferenza codice, utilizzato per partecipare a riunioni pianificate dall'utente e vengono fornite da un provider di servizi di conferenza audio di terze parti.</span><span class="sxs-lookup"><span data-stu-id="29ae3-165">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="29ae3-166">Se l'utente sta utilizzando Microsoft come provider di servizi di conferenza audio, questo non sarà necessario.</span><span class="sxs-lookup"><span data-stu-id="29ae3-166">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="29ae3-167">Per configurare queste impostazioni in blocco, utilizzare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="29ae3-167">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="29ae3-168">Vedere [impostare telefono numeri incluso nel invita](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="29ae3-168">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="29ae3-169">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="29ae3-169">Related topics</span></span> 

[<span data-ttu-id="29ae3-170">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="29ae3-170">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

<span data-ttu-id="29ae3-171">Per ulteriori informazioni, consulta [Servizi di conferenza telefonica con accesso esterno in Office 365](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="29ae3-171">[Skype for Business and Microsoft Teams add-on licensing](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)</span></span>
  
