---
title: Gli amministratori configurare Skype per le impostazioni di Business per singoli utenti
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 77b26eac-8228-4161-ba9f-733b187bd836
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1_keywords:
- ms.lync.lac.UsersExternalAccess
- ms.lync.lac.UsersGeneralOptions
- ms.lync.lac.UsersLyncToPhoneMoreInfo
ms.custom:
- Setup
- LIL_Placement
description: 'Informazioni su come modificare Skype per le impostazioni di Business per singoli utenti, ad esempio: conferenze Audio e video, la registrazione delle chiamate e riunioni. '
ms.openlocfilehash: e686e42771b22d7c8d8b21ac05998bbbd5f9ad7e
ms.sourcegitcommit: 7d65eafd5b0163ece91deb7801458c7a45fcc4f7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/29/2018
ms.locfileid: "25838952"
---
# <a name="admins-configure-skype-for-business-settings-for-individual-users"></a><span data-ttu-id="91d88-103">Amministratori: Configurare le impostazioni di Skype for Business online per singoli utenti</span><span class="sxs-lookup"><span data-stu-id="91d88-103">Admins: Configure Skype for Business settings for individual users</span></span>

<span data-ttu-id="91d88-104">In questo articolo viene illustrato come gli amministratori configurare Skype for Business per un numero limitato di utenti.</span><span class="sxs-lookup"><span data-stu-id="91d88-104">This article explains how admins configure Skype for Business for a small number of users.</span></span> <span data-ttu-id="91d88-105">Per eseguire la procedura seguente in blocco, è stata inclusa collegamenti a è possibile utilizzare i cmdlet di Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91d88-105">To do these steps in bulk, we've included links to the Windows PowerShell cmdlets you can use.</span></span>
  
<span data-ttu-id="91d88-106">Per consentire o bloccare tutti gli utenti nell'organizzazione di comunicare con utenti esterni, vedere:</span><span class="sxs-lookup"><span data-stu-id="91d88-106">To allow (or block) everyone in your business to communicate with external people, see:</span></span>
  
- <span data-ttu-id="91d88-107">[Consenti agli utenti di contatti esterni Skype per gli utenti aziendali](allow-users-to-contact-external-skype-for-business-users.md): È possibile consentire all'organizzazione di utilizzare avanzate Skype per le funzionalità di Business (condivisione desktop, interfaccia per chi è in linea, ecc) comunicare con persone in una determinata attendibili business (federati).</span><span class="sxs-lookup"><span data-stu-id="91d88-107">[Allow users to contact external Skype for Business users](allow-users-to-contact-external-skype-for-business-users.md): You can let your organization use advanced Skype for Business features (share desktops, look for who's online, etc.) to communicate with people in a specific trusted (federated) business.</span></span> <span data-ttu-id="91d88-108">L'articolo viene inoltre illustrato come bloccare la comunicazione con i domini specifici.</span><span class="sxs-lookup"><span data-stu-id="91d88-108">The article also explains how to block communication with specific domains.</span></span>
    
- <span data-ttu-id="91d88-109">[Consentire Skype per gli utenti aziendali di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md).</span><span class="sxs-lookup"><span data-stu-id="91d88-109">[Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md).</span></span> <span data-ttu-id="91d88-110">È possibile consentire l'organizzazione utilizza Skype per cercare di lavoro e utenti di messaggistica immediata che utilizzano Skype, gratuitamente l'app.</span><span class="sxs-lookup"><span data-stu-id="91d88-110">You can let your organization use Skype for Business to search for and IM people who use Skype, the free app.</span></span>
    
## <a name="configure-general-settings-for-one-user"></a><span data-ttu-id="91d88-111">Configurare le impostazioni generali per un utente</span><span class="sxs-lookup"><span data-stu-id="91d88-111">Configure general settings for one user</span></span>
<span data-ttu-id="91d88-112"><a name="__toc325019204"> </a></span><span class="sxs-lookup"><span data-stu-id="91d88-112"></span></span>

<span data-ttu-id="91d88-113">È necessario disporre [delle autorizzazioni di amministratore](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) per eseguire la procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="91d88-113">You must have [admin permissions](https://support.office.com/en-us/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) to perform these steps.</span></span>

<span data-ttu-id="91d88-114">![30x30.png di logo sfb](../images/sfb-logo-30x30.png) **utilizzando Skype per interfaccia di amministrazione di Business**</span><span class="sxs-lookup"><span data-stu-id="91d88-114">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>
  
1. <span data-ttu-id="91d88-115">Accedi a Office 365 con l'account aziendale o dell'istituto di istruzione.</span><span class="sxs-lookup"><span data-stu-id="91d88-115">Sign in to Office 365 with your work or school account.</span></span>
    
2. <span data-ttu-id="91d88-116">Scegli **Interfaccia di amministrazione** > **Skype for Business**.</span><span class="sxs-lookup"><span data-stu-id="91d88-116">Choose **Admin centers** > **Skype for Business**.</span></span>
    
3. <span data-ttu-id="91d88-117">Scegli **Utenti**.</span><span class="sxs-lookup"><span data-stu-id="91d88-117">Choose **Users**.</span></span>
    
    ![Skype per interfaccia di amministrazione di Business, scegliere utenti.](../images/7c80eeb3-6555-4fc8-91f4-61b493581e9e.png)
  
4. <span data-ttu-id="91d88-119">Scegliere gli utenti che si desidera modificare.</span><span class="sxs-lookup"><span data-stu-id="91d88-119">Choose which users you want to edit.</span></span>
    
5. <span data-ttu-id="91d88-120">Nel riquadro destro, scegli **Modifica**.</span><span class="sxs-lookup"><span data-stu-id="91d88-120">In the right panel, choose **Edit**.</span></span>
    
    ![Scegli l'icona di modifica.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. <span data-ttu-id="91d88-122">Nella pagina Opzioni **Generale** , selezionare o deselezionare la casella di controllo accanto alle funzionalità che si desidera modificare e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="91d88-122">On the **General** options page, select or clear the check box next to the features you want to change, and then choose **Save**.</span></span>
    
|<span data-ttu-id="91d88-123">**Opzione**</span><span class="sxs-lookup"><span data-stu-id="91d88-123">**Option**</span></span>|<span data-ttu-id="91d88-124">**Dettagli**</span><span class="sxs-lookup"><span data-stu-id="91d88-124">**Details**</span></span>|
|:-----|:-----|
|<span data-ttu-id="91d88-125">Audio e video HD</span><span class="sxs-lookup"><span data-stu-id="91d88-125">Audio and HD video</span></span>  <br/> |<span data-ttu-id="91d88-126">Consentire questa persona di registrare le riunioni audio, audio e video alle riunioni o non consentire loro di pianificare le riunioni (nessuno).</span><span class="sxs-lookup"><span data-stu-id="91d88-126">Allow this person to record audio meetings, audio and video meetings, or don't allow them to schedule any meetings (none).</span></span>  <br/> |
|<span data-ttu-id="91d88-127">Registrare conversazioni e riunioni</span><span class="sxs-lookup"><span data-stu-id="91d88-127">Record conversations and meetings</span></span>  <br/> |<span data-ttu-id="91d88-128">Scegliere quali questa persona è consentita registrare.</span><span class="sxs-lookup"><span data-stu-id="91d88-128">Choose what this person is allowed to record.</span></span>  <br/> <span data-ttu-id="91d88-129">Questa opzione non è disponibile con Skype per Business Basic.</span><span class="sxs-lookup"><span data-stu-id="91d88-129">This option is not available with Skype for Business Basic.</span></span>  <br/> |
|<span data-ttu-id="91d88-130">Per motivi di conformità, disattivare le funzionalità non archiviate</span><span class="sxs-lookup"><span data-stu-id="91d88-130">For compliance, turn off non-archived features</span></span>  <br/> | <span data-ttu-id="91d88-131">Scegliere questa opzione se si è obbligate per legge a conservare le informazioni archiviate in formato elettronico.</span><span class="sxs-lookup"><span data-stu-id="91d88-131">Choose this option if you're legally required to preserve electronically stored information.</span></span> <br/>  <span data-ttu-id="91d88-132">Se si seleziona questa opzione viene disattivata la funzionalità che non sono state acquisite in presenza di un' [Archiviazione sul posto](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) configurato nell'interfaccia di amministrazione di Exchange.</span><span class="sxs-lookup"><span data-stu-id="91d88-132">Selecting this option turns off features that aren't captured when you have an [In-Place Hold](https://technet.microsoft.com/en-us/library/ff637980%28v=exchg.150%29.aspx) set up in the Exchange admin center.</span></span> <span data-ttu-id="91d88-133">Disattiva le funzionalità seguenti:</span><span class="sxs-lookup"><span data-stu-id="91d88-133">It turns off the following features:</span></span> <br/>  <span data-ttu-id="91d88-134">Trasferimento di file tramite messaggistica istantanea</span><span class="sxs-lookup"><span data-stu-id="91d88-134">File transfer using instant messaging</span></span> <br/>  <span data-ttu-id="91d88-135">Pagine condivise di OneNote</span><span class="sxs-lookup"><span data-stu-id="91d88-135">Shared OneNote pages</span></span> <br/>  <span data-ttu-id="91d88-136">Annotazioni di PowerPoint</span><span class="sxs-lookup"><span data-stu-id="91d88-136">PowerPoint annotations</span></span> <br/> |
   
<span data-ttu-id="91d88-137">Per configurare queste impostazioni in blocco, utilizzare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91d88-137">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="91d88-138">Vedere [gestione dei criteri in Skype Business online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="91d88-138">See [Managing policies in Skype for Business Online](https://technet.microsoft.com/en-us/library/dn362826%28v=ocs.15%29.aspx).</span></span>
  
## <a name="block-external-communications"></a><span data-ttu-id="91d88-139">Blocca comunicazioni esterne</span><span class="sxs-lookup"><span data-stu-id="91d88-139">Block external communications</span></span>
<span data-ttu-id="91d88-140"><a name="__toc325019206"> </a></span><span class="sxs-lookup"><span data-stu-id="91d88-140"></span></span>

<span data-ttu-id="91d88-141">Dopo aver [Skype consente agli utenti aziendali aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md) per tutti gli utenti della società, è possibile bloccare in modo selettivo comunicazioni esterne per specifici utenti attenendosi alla procedura seguente.</span><span class="sxs-lookup"><span data-stu-id="91d88-141">After you [Let Skype for Business users add Skype contacts](let-skype-for-business-users-add-skype-contacts.md) for everyone in your company, you can selectively block external communications for specific individuals using these steps.</span></span>
  
1. <span data-ttu-id="91d88-142">Selezione **utenti**, selezionare gli utenti il cui si desidera disabilitare le impostazioni e quindi fare clic su **Modifica** ![modifica](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="91d88-142">Choose **Users**, select the users whose settings you want to disable, and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="91d88-143">Scegliere **comunicazioni esterne**e quindi deselezionare le opzioni desiderate:</span><span class="sxs-lookup"><span data-stu-id="91d88-143">Choose **External communications**, and then clear the options as appropriate:</span></span>
    
   - <span data-ttu-id="91d88-144">**Skype esterna per gli utenti aziendali**: deselezionare questa casella se non si desidera che l'utente di comunicare con Skype per utenti Business nei domini federati.</span><span class="sxs-lookup"><span data-stu-id="91d88-144">**External Skype for Business users**: Clear this box if you don't want the user to be able to communicate with Skype for Business users in federated domains.</span></span>
    
   - <span data-ttu-id="91d88-145">**Gli utenti esterni Skype**: deselezionare questa casella se non si desidera che l'utente di comunicare con persone che utilizzano l'app freeSkype.</span><span class="sxs-lookup"><span data-stu-id="91d88-145">**External Skype users**: Clear this box if you don't want the user to be able to communicate with people who are using the freeSkype app.</span></span>
    
3. <span data-ttu-id="91d88-146">Fai clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="91d88-146">Click **Save**.</span></span>
    
<span data-ttu-id="91d88-147">Per configurare queste impostazioni in blocco, utilizzare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91d88-147">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="91d88-148">Vedere [gestione delle comunicazioni in Skype Business online con organizzazioni e agli utenti esterni](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="91d88-148">See [Managing communications in Skype for Business Online with outside users and organizations](https://technet.microsoft.com/en-us/library/dn362813%28v=ocs.15%29.aspx).</span></span>
  
## <a name="edit-audio-conferencing-settings-for-one-user"></a><span data-ttu-id="91d88-149">Modificare le impostazioni di conferenza per un utente</span><span class="sxs-lookup"><span data-stu-id="91d88-149">Edit audio conferencing settings for one user</span></span>
<span data-ttu-id="91d88-150"><a name="__toc314837483"> </a></span><span class="sxs-lookup"><span data-stu-id="91d88-150"></span></span>

1. <span data-ttu-id="91d88-151">Selezione **utenti**, selezionare l'utente di cui si desidera per modificare, le impostazioni di audioconferenza e quindi fare clic su **Modifica** ![modifica](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span><span class="sxs-lookup"><span data-stu-id="91d88-151">Choose **Users**, select the user whose audio conferencing settings you wan to edit, ,and then choose **Edit** ![Edit](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).</span></span>
    
2. <span data-ttu-id="91d88-152">Scegliere **servizi di conferenza Audio**, selezionare il provider di servizi di conferenza audio, digitare o modificare le informazioni richieste e quindi fare clic su **Salva**.</span><span class="sxs-lookup"><span data-stu-id="91d88-152">Choose **Audio conferencing**, select your audio conferencing provider, type or change the requested information, and then click **Save**.</span></span>
    
|<span data-ttu-id="91d88-153">**Impostazioni delle audioconferenze**</span><span class="sxs-lookup"><span data-stu-id="91d88-153">**Audio conferencing setting**</span></span>|<span data-ttu-id="91d88-154">**Descrizione**</span><span class="sxs-lookup"><span data-stu-id="91d88-154">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="91d88-155">**Nome del provider**</span><span class="sxs-lookup"><span data-stu-id="91d88-155">**Provider name**</span></span> <br/> |<span data-ttu-id="91d88-156">Scegliere il provider dall'elenco.</span><span class="sxs-lookup"><span data-stu-id="91d88-156">Choose your provider from the list.</span></span>  <br/> |
|<span data-ttu-id="91d88-157">**Numero a pagamento** (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="91d88-157">**Toll number** (required)</span></span> <br/> |<span data-ttu-id="91d88-158">Per un'AUDIOCONFERENZA di terze parti, questi numeri di telefono sono forniti dal provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="91d88-158">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="91d88-159">Se l'utente sta utilizzando Microsoft come provider di servizi di audioconferenza, questi saranno i numeri impostati sul ponte per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="91d88-159">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="91d88-160">Formattare i numeri che si desidera che vengano visualizzate in Skype per Business e Microsoft Teams convocazioni di riunione.</span><span class="sxs-lookup"><span data-stu-id="91d88-160">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="91d88-161">**Numero verde**</span><span class="sxs-lookup"><span data-stu-id="91d88-161">**Toll-free number**</span></span> <br/> |<span data-ttu-id="91d88-162">Per un'AUDIOCONFERENZA di terze parti, questi numeri di telefono sono forniti dal provider di servizi di conferenza audio.</span><span class="sxs-lookup"><span data-stu-id="91d88-162">For a third-party ACP, these phone numbers are the ones you received from the audio conferencing provider.</span></span> <span data-ttu-id="91d88-163">Se l'utente sta utilizzando Microsoft come provider di servizi di audioconferenza, questi saranno i numeri impostati sul ponte per audioconferenza.</span><span class="sxs-lookup"><span data-stu-id="91d88-163">If the user is using Microsoft as the audio conferencing provider, these will be numbers that are set on the audio conferencing bridge.</span></span> <span data-ttu-id="91d88-164">Formattare i numeri che si desidera che vengano visualizzate in Skype per Business e Microsoft Teams convocazioni di riunione.</span><span class="sxs-lookup"><span data-stu-id="91d88-164">Format the numbers as you want them to appear in Skype for Business and Microsoft Teams meeting requests.</span></span>  <br/> |
|<span data-ttu-id="91d88-165">**ID conferenza e PIN** (obbligatorio)</span><span class="sxs-lookup"><span data-stu-id="91d88-165">**Conference ID and PIN** (required)</span></span> <br/> |<span data-ttu-id="91d88-166">Il partecipante PIN o conferenza codice, utilizzato per partecipare a riunioni pianificate dall'utente e vengono fornite da un provider di servizi di conferenza audio di terze parti.</span><span class="sxs-lookup"><span data-stu-id="91d88-166">The participant PIN, or conference code, used to join meetings that are scheduled by this user and are provided from a third-party audio conferencing provider.</span></span> <span data-ttu-id="91d88-167">Se l'utente sta utilizzando Microsoft come provider di servizi di conferenza audio, questo non sarà necessario.</span><span class="sxs-lookup"><span data-stu-id="91d88-167">If the user is using Microsoft as the audio conferencing provider, this won't be required.</span></span>  <br/> |
   
<span data-ttu-id="91d88-168">Per configurare queste impostazioni in blocco, utilizzare PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91d88-168">To configure these settings in bulk, use PowerShell.</span></span> <span data-ttu-id="91d88-169">Vedere [impostare telefono numeri incluso nel invita](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span><span class="sxs-lookup"><span data-stu-id="91d88-169">See [Set the phone numbers included on invites](../audio-conferencing-in-office-365/set-the-phone-numbers-included-on-invites.md).</span></span>


[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]
  
   
## <a name="related-topics"></a><span data-ttu-id="91d88-170">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="91d88-170">Related topics</span></span> 

[<span data-ttu-id="91d88-171">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="91d88-171">Set up Skype for Business Online</span></span>](set-up-skype-for-business-online.md)

[<span data-ttu-id="91d88-172">Licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="91d88-172">Skype for Business and Microsoft Teams add-on licensing</span></span>](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)
  
  
 