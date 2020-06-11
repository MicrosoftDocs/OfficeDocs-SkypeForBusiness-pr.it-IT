---
title: Configurare Cloud Voicemail
author: dstrome
ms.author: dstrome
manager: serdars
ms.reviewer: wasseemh, phans
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Informazioni su come configurare la segreteria telefonica cloud per gli utenti. '
ms.openlocfilehash: 62729794ff1e23ce29b3e3aad86fa09b63a428e5
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691052"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="2a8b1-103">Configurare Cloud Voicemail</span><span class="sxs-lookup"><span data-stu-id="2a8b1-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="2a8b1-104">Questo articolo riguarda l'amministratore di Microsoft 365 o Office 365, come descritto in [informazioni sui ruoli di amministratore](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) che vogliono configurare la funzionalità per la segreteria telefonica cloud per tutti gli utenti dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="2a8b1-105">Cloud Voicemail supporta il deposito dei messaggi della segreteria telefonica solo in una cassetta postale di Exchange e non supporta sistemi di posta elettronica di terze parti.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="2a8b1-106">Quando un delegato risponde a una chiamata per conto di un delegante, le notifiche non sono disponibili nel cloud Voicemail.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="2a8b1-107">Gli utenti possono ricevere notifiche per le chiamate perse.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="2a8b1-108">Ambienti solo cloud: configurare la segreteria telefonica cloud per gli utenti del sistema telefonico online</span><span class="sxs-lookup"><span data-stu-id="2a8b1-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="2a8b1-109">Per gli utenti del sistema telefonico online, cloud Voicemail viene configurato automaticamente e provisionato per gli utenti dopo l'assegnazione di una licenza per il **sistema telefonico** agli utenti.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="2a8b1-110">Per gli utenti di sistemi telefonici Skype for business online con numeri di telefono forniti in locale, potrebbe essere necessario abilitare la segreteria telefonica ospitata con [Set-CsUser-HostedVoicemail $true](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="2a8b1-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="2a8b1-111">Configurare cloud Voicemail per gli utenti di cassette postali di Exchange Server</span><span class="sxs-lookup"><span data-stu-id="2a8b1-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="2a8b1-112">Le informazioni seguenti includono la configurazione della segreteria telefonica cloud per l'utilizzo con gli utenti online per il sistema telefonico, ma con la cassetta postale in Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="2a8b1-113">I messaggi della segreteria telefonica vengono recapitati alla cassetta postale di Exchange degli utenti tramite SMTP instradato tramite Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="2a8b1-114">Per consentire il corretto recapito di questi messaggi, verificare che i connettori di Exchange siano configurati correttamente tra i server Exchange e la protezione di Exchange Online. [Usare i connettori per configurare il flusso di posta](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="2a8b1-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="2a8b1-115">Per abilitare le caratteristiche della segreteria telefonica, ad esempio la personalizzazione dei messaggi di saluto e la segreteria telefonica visiva nei client Skype for business, è necessaria la connettività da Microsoft 365 o Office 365 alla cassetta postale di Exchange Server tramite servizi Web Exchange.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="2a8b1-116">Per abilitare questa connettività, è necessario configurare il nuovo protocollo di autenticazione OAuth di Exchange descritto in [configurare l'autenticazione OAuth tra le organizzazioni Exchange e Exchange Online](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)oppure eseguire la procedura guidata ibrida di Exchange da Exchange 2013 CU5 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="2a8b1-117">Inoltre, è necessario configurare Integration e OAuth tra Skype for business online ed Exchange Server descritto in [configurare Integration e OAuth tra Skype for business online ed Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span><span class="sxs-lookup"><span data-stu-id="2a8b1-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="2a8b1-118">Configurare cloud Voicemail per gli utenti di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="2a8b1-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="2a8b1-119">Per configurare gli utenti di Skype for Business Server per la segreteria telefonica cloud, vedere [pianificare il servizio di segreteria cloud per gli utenti locali](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail).</span><span class="sxs-lookup"><span data-stu-id="2a8b1-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](https://docs.microsoft.com/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="2a8b1-120">Abilitazione della segreteria telefonica protetta nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="2a8b1-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="2a8b1-121">Quando qualcuno lascia un messaggio vocale per un utente dell'organizzazione, la segreteria telefonica viene recapitata alla cassetta postale dell'utente come allegato di un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="2a8b1-122">Uso delle regole del flusso di posta per applicare la crittografia dei messaggi, è possibile impedire che i messaggi della segreteria telefonica vengano inoltrati ad altri destinatari.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="2a8b1-123">Quando si Abilita la segreteria telefonica protetta, gli utenti possono ascoltare i messaggi vocali protetti chiamandoli nella cassetta postale della segreteria telefonica o aprendo il messaggio in Outlook, Outlook sul Web o in Outlook per Android o iOS.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="2a8b1-124">Non è possibile aprire messaggi vocali protetti in Skype for business.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-124">Protected voicemail messages can't be opened in Skype for Business.</span></span>

<span data-ttu-id="2a8b1-125">Per altre informazioni sulla crittografia dei messaggi, vedere [crittografia della posta elettronica](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="2a8b1-125">For more information about message encryption, see [Email encryption](https://docs.microsoft.com/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="2a8b1-126">Per configurare la segreteria telefonica protetta, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a8b1-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="2a8b1-127">Accedere https://admin.microsoft.com e accedere usando un account con autorizzazioni di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="2a8b1-128">Selezionare **Mostra tutto** e quindi vai a interfaccia di **Amministrazione**di  >  **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="2a8b1-129">Nell'interfaccia di amministrazione di Exchange selezionare **regole flusso di posta**  >  **Rules**.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="2a8b1-130">Selezionare **+** **Aggiungi**e quindi applicare la **crittografia dei messaggi di Office 365 e i diritti di protezione ai messaggi**.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-130">Select **+** **Add**, and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="2a8b1-131">Specificare un nome per la nuova regola del flusso di posta e quindi in **applica questa regola se**selezionare **le proprietà del messaggio**  >  **includono il tipo di messaggio**segreteria  >  **telefonica**.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-131">Provide a name for the new mail flow rule and then under **Apply this rule if**, select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="2a8b1-132">Selezionare **OK**.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-132">Select **OK**.</span></span>
6. <span data-ttu-id="2a8b1-133">In **eseguire le operazioni seguenti**selezionare **Applica crittografia messaggi di Office 365 e protezione dei diritti al messaggio con** e quindi selezionare **selezionarne uno**.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-133">Under **Do the following**, select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="2a8b1-134">In **modello RMS**selezionare non **inoltrare**.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-134">Under **RMS template**, select **Do not forward**.</span></span> <span data-ttu-id="2a8b1-135">Selezionare **OK** e quindi **Salva**.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="2a8b1-136">Se l'elenco di **modelli RMS** è vuoto, è necessario configurare la crittografia dei messaggi.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="2a8b1-137">Per altre informazioni sulla configurazione della crittografia dei messaggi, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="2a8b1-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="2a8b1-138">Configurare nuove funzionalità di crittografia messaggi</span><span class="sxs-lookup"><span data-stu-id="2a8b1-138">Set up new Message Encryption capabilities</span></span>](https://docs.microsoft.com/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="2a8b1-139">Configurazione e gestione di modelli per la protezione delle informazioni di Azure</span><span class="sxs-lookup"><span data-stu-id="2a8b1-139">Configuring and managing templates for Azure Information Protection</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-templates)
    > - [<span data-ttu-id="2a8b1-140">Opzione non inoltra per i messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="2a8b1-140">Do Not Forward option for emails</span></span>](https://docs.microsoft.com/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="2a8b1-141">Impostazione dei criteri di segreteria telefonica dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="2a8b1-141">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="2a8b1-142">Per i clienti Skype for business, la disabilitazione della segreteria telefonica tramite un criterio di chiamata di Microsoft teams può anche disabilitare il servizio di segreteria telefonica per gli utenti di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-142">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="2a8b1-143">La trascrizione della segreteria telefonica è abilitata per impostazione predefinita e il mascheramento di volgarità è disabilitato per impostazione predefinita per tutte le organizzazioni e utenti. Tuttavia, è possibile controllarli utilizzando il cmdlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) e [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="2a8b1-143">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="2a8b1-144">I messaggi della segreteria telefonica ricevuti dagli utenti dell'organizzazione vengono trascritti nell'area geografica in cui è ospitata l'organizzazione Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-144">Voicemail messages received by users in your organization are transcribed in the region where your Microsoft 365 or Office 365 organization is hosted.</span></span> <span data-ttu-id="2a8b1-145">L'area in cui è ospitato il tenant potrebbe non essere la stessa area in cui si trova l'utente che riceve il messaggio della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-145">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="2a8b1-146">Per visualizzare l'area geografica in cui è ospitato il tenant, accedere alla pagina del [profilo dell'organizzazione](https://go.microsoft.com/fwlink/p/?linkid=2067339) e quindi fare clic su **Visualizza dettagli** accanto a **posizione dati**.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-146">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a8b1-147">Non è possibile creare una nuova istanza di criteri per la trascrizione e la trascrizione delle maschere profane usando il cmdlet **New-CsOnlineVoiceMailPolicy** e non è possibile rimuovere un'istanza di criteri esistente usando il cmdlet **Remove-CsOnlineVoiceMailPolicy** .</span><span class="sxs-lookup"><span data-stu-id="2a8b1-147">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="2a8b1-148">È possibile gestire le impostazioni di trascrizione per gli utenti che utilizzano i criteri segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-148">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="2a8b1-149">Per visualizzare tutte le istanze dei criteri di segreteria telefonica disponibili, è possibile usare il cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="2a8b1-149">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="2a8b1-150">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="2a8b1-150">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy finestra risultati.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="2a8b1-152">Disattivare la trascrizione per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="2a8b1-152">Turning off transcription for your organization</span></span>

<span data-ttu-id="2a8b1-p110">Dato che l'impostazione predefinita per la trascrizione è attiva per la propria organizzazione, si consiglia di disabilitarla utilizzando il cmdlet [set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2a8b1-p110">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="2a8b1-155">Attivazione del mascheramento di volgarità sulla trascrizione per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="2a8b1-155">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="2a8b1-156">Il mascheramento di volgarità sulla trascrizione è disabilitato per impostazione predefinita per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-156">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="2a8b1-157">Se non vi è un requisito aziendale per abilitarlo, è possibile abilitare il mascheramento di volgarità sulla trascrizione tramite [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="2a8b1-157">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="2a8b1-158">Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="2a8b1-158">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="2a8b1-159">Disattivare la trascrizione per un utente</span><span class="sxs-lookup"><span data-stu-id="2a8b1-159">Turning off transcription for a user</span></span>

<span data-ttu-id="2a8b1-160">I criteri utente vengono valutati prima delle impostazioni predefinite dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-160">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="2a8b1-161">Ad esempio, se la trascrizione della segreteria telefonica è abilitata per tutti gli utenti, puoi assegnare un criterio per disabilitare la trascrizione per un utente specifico usando il cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="2a8b1-161">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="2a8b1-162">Per disabilitare la trascrizione per un singolo utente, eseguire:</span><span class="sxs-lookup"><span data-stu-id="2a8b1-162">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="2a8b1-163">Attivazione del mascheramento di volgarità sulla trascrizione per un utente</span><span class="sxs-lookup"><span data-stu-id="2a8b1-163">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="2a8b1-164">Per abilitare il mascheramento di volgarità sulla trascrizione per un utente specifico, è possibile assegnare un criterio per abilitare il mascheramento di volgarità sulla trascrizione per un utente specifico utilizzando il cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="2a8b1-164">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="2a8b1-165">Per abilitare il mascheramento di volgarità sulla trascrizione per un singolo utente, eseguire:</span><span class="sxs-lookup"><span data-stu-id="2a8b1-165">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="2a8b1-166">Il servizio di segreteria telefonica in Microsoft 365 e Office 365 memorizza nella cache i criteri della segreteria telefonica e aggiorna la cache ogni 4 ore.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-166">The voicemail service in Microsoft 365 and Office 365 caches voicemail policies and updates the cache every 4 hours.</span></span> <span data-ttu-id="2a8b1-167">Perciò le modifiche apportate ai criteri possono impiegare fino a 4 ore per essere applicate.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-167">So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="2a8b1-168">Aiutare gli utenti a conoscere le caratteristiche della segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="2a8b1-168">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="2a8b1-169">Per gli utenti sono disponibili le informazioni seguenti per gestire le impostazioni della segreteria telefonica e altre funzionalità di chiamata in teams:</span><span class="sxs-lookup"><span data-stu-id="2a8b1-169">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="2a8b1-170">[Gestire le impostazioni delle chiamate in teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span><span class="sxs-lookup"><span data-stu-id="2a8b1-170">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="2a8b1-171">Questo articolo illustra come gestire tutti i team di utenti finali che chiamano le funzionalità.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-171">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="2a8b1-172">Aiutare gli utenti a imparare le funzioni della segreteria telefonica Skype for Business</span><span class="sxs-lookup"><span data-stu-id="2a8b1-172">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="2a8b1-p115">Abbiamo informazioni e articoli di formazione per aiutare gli utenti a usare con successo la segreteria telefonica Skype for Business. Questi sono gli articoli che gli utenti vorranno consultare:</span><span class="sxs-lookup"><span data-stu-id="2a8b1-p115">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="2a8b1-175">[Controllare le opzioni e la segreteria telefonica di Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Questo articolo illustra come ascoltare i messaggi vocali in Skype for Business e ascoltare i messaggi vocali a velocità diverse.</span><span class="sxs-lookup"><span data-stu-id="2a8b1-175">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="2a8b1-176">Formazione per Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="2a8b1-176">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="2a8b1-177">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="2a8b1-177">Related topics</span></span>
[<span data-ttu-id="2a8b1-178">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="2a8b1-178">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="2a8b1-179">Vantaggi offerti dal Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="2a8b1-179">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="2a8b1-180">Pianificare la migrazione per Skype for Business Server ed Exchange Server</span><span class="sxs-lookup"><span data-stu-id="2a8b1-180">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)
