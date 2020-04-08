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
ms.openlocfilehash: 5f975eac51cf3787ac5a1dde9b76b80b0912478d
ms.sourcegitcommit: a610bfe9c0192432744dfaf8d5ff5c2bb5a16b00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2020
ms.locfileid: "43190833"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="c93e2-103">Configurare Cloud Voicemail</span><span class="sxs-lookup"><span data-stu-id="c93e2-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="c93e2-104">Questo articolo riguarda l' [amministratore di Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) che vuole configurare la funzionalità per il cloud Voicemail per tutti gli utenti dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="c93e2-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="c93e2-105">Cloud Voicemail supporta il deposito dei messaggi della segreteria telefonica solo in una cassetta postale di Exchange e non supporta sistemi di posta elettronica di terze parti.</span><span class="sxs-lookup"><span data-stu-id="c93e2-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="c93e2-106">Ambienti solo cloud: configurare la segreteria telefonica cloud</span><span class="sxs-lookup"><span data-stu-id="c93e2-106">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="c93e2-107">Per gli utenti di Skype for business online e per i piani di chiamata, cloud Voicemail viene configurato automaticamente e provisionato per gli utenti dopo l'assegnazione di una licenza per il **sistema telefonico** e di un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="c93e2-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="c93e2-108">Se la funzione Sistema telefonico non è inclusa nel tuo piano, può essere necessario acquistare licenze per il componente aggiuntivo **Sistema telefonico**.</span><span class="sxs-lookup"><span data-stu-id="c93e2-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="c93e2-109">Inoltre è necessario acquistare una licenza Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c93e2-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="c93e2-110">Vedere [licenze per i componenti aggiuntivi Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="c93e2-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="c93e2-111">[Assegnare o rimuovere licenze per Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [assegnare le licenze di Microsoft teams](assign-teams-licenses.md)e le licenze di Exchange Online agli utenti della propria azienda.</span><span class="sxs-lookup"><span data-stu-id="c93e2-111">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="c93e2-112">Terminate queste operazioni, potranno ricevere i messaggi vocali.</span><span class="sxs-lookup"><span data-stu-id="c93e2-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="c93e2-p103">Il supporto per la trascrizione segreteria telefonica è stato aggiunto a partire da marzo 2017 ed è attivato per impostazione predefinita per tutte le organizzazioni e gli utenti. Puoi disattivare la trascrizione per la tua organizzazione usando Windows PowerShell e attenendoti alle seguenti istruzioni.</span><span class="sxs-lookup"><span data-stu-id="c93e2-p103">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="c93e2-115">Sistema telefonico con ambienti locali</span><span class="sxs-lookup"><span data-stu-id="c93e2-115">Phone System with on-premises environments</span></span>

<span data-ttu-id="c93e2-116">Le informazioni seguenti includono la configurazione della segreteria telefonica cloud per l'utilizzo con ambienti di piano chiamante locali.</span><span class="sxs-lookup"><span data-stu-id="c93e2-116">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="c93e2-117">Se la funzione Sistema telefonico non è inclusa nel tuo piano, può essere necessario acquistare licenze per il componente aggiuntivo **Sistema telefonico**.</span><span class="sxs-lookup"><span data-stu-id="c93e2-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="c93e2-118">Inoltre è necessario acquistare una licenza Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="c93e2-118">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="c93e2-119">Vedere [licenze per i componenti aggiuntivi Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="c93e2-119">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="c93e2-120">[Assegnare o rimuovere licenze per Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [assegnare le licenze di Microsoft teams](assign-teams-licenses.md)e le licenze di Exchange Online agli utenti della propria azienda.</span><span class="sxs-lookup"><span data-stu-id="c93e2-120">[Assign or remove licenses for Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="c93e2-121">Seguire le istruzioni corrispondenti alla soluzione di chiamate PSTN locale distribuita per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="c93e2-121">Follow instructions matching on-premises PSTN calling solution deployed for your users.</span></span> <span data-ttu-id="c93e2-122">Per Cloud Connector Edition, seguire le istruzioni nella sezione **Enable Users for Phone System Voice and voicemail Services** della [Guida alla configurazione di Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="c93e2-122">For Cloud Connector Edition, follow instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span> <span data-ttu-id="c93e2-123">Per le chiamate PSTN con Skype for Business Server, seguire [consentire agli utenti di VoIP aziendale in locale](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span><span class="sxs-lookup"><span data-stu-id="c93e2-123">For PSTN calling with Skype for Business Server, follow [Enable the users for Enterprise Voice on premises](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span></span> <span data-ttu-id="c93e2-124">Per il routing diretto di teams, seguire la sezione **configurare il numero di telefono e abilitare l'organizzazione vocale e la segreteria telefonica** di [Configura routing diretto](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span><span class="sxs-lookup"><span data-stu-id="c93e2-124">For Teams Direct Routing, follow  the **Configure the phone number and enable enterprise voice and voicemail** section of [Configure Direct Routing](https://docs.microsoft.com/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span></span>

4. <span data-ttu-id="c93e2-p106">Il supporto per la trascrizione segreteria telefonica è stato aggiunto a partire da marzo 2017 ed è attivato per impostazione predefinita per tutte le organizzazioni e gli utenti. Puoi disattivare la trascrizione per la tua organizzazione usando Windows PowerShell e attenendoti alle seguenti istruzioni.</span><span class="sxs-lookup"><span data-stu-id="c93e2-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="c93e2-127">I messaggi della segreteria telefonica vengono recapitati alla cassetta postale di Exchange degli utenti tramite SMTP instradato tramite Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="c93e2-127">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="c93e2-128">Per consentire il corretto recapito di questi messaggi, verificare che i connettori di Exchange siano configurati correttamente tra i server Exchange e la protezione di Exchange Online. [Usare i connettori per configurare il flusso di posta](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="c93e2-128">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

6. <span data-ttu-id="c93e2-129">Per abilitare le caratteristiche della segreteria telefonica, ad esempio la personalizzazione dei messaggi di saluto e la segreteria telefonica visiva nei client Skype for business, è necessaria la connettività da Office 365 alla cassetta postale di Exchange Server tramite servizi Web Exchange.</span><span class="sxs-lookup"><span data-stu-id="c93e2-129">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="c93e2-130">Per abilitare questa connettività, è necessario configurare il nuovo protocollo di autenticazione OAuth di Exchange descritto in [configurare l'autenticazione OAuth tra le organizzazioni Exchange e Exchange Online](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx)oppure eseguire la procedura guidata ibrida di Exchange da Exchange 2013 CU5 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="c93e2-130">To enable this connectivity you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="c93e2-131">Inoltre, è necessario configurare Integration e OAuth tra Skype for business online ed Exchange Server descritto in [configurare Integration e OAuth tra Skype for business online ed Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span><span class="sxs-lookup"><span data-stu-id="c93e2-131">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

> [!NOTE]
> <span data-ttu-id="c93e2-132">Quando un delegato risponde a una chiamata per conto di un delegante, le notifiche non sono disponibili nel cloud Voicemail.</span><span class="sxs-lookup"><span data-stu-id="c93e2-132">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="c93e2-133">Gli utenti possono ricevere notifiche per le chiamate perse.</span><span class="sxs-lookup"><span data-stu-id="c93e2-133">Users can receive notifications for missed calls.</span></span>

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="c93e2-134">Impostazione dei criteri di segreteria telefonica dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="c93e2-134">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="c93e2-135">Per i clienti Skype for business, la disabilitazione della segreteria telefonica tramite un criterio di chiamata di Microsoft teams può anche disabilitare il servizio di segreteria telefonica per gli utenti di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="c93e2-135">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="c93e2-136">La trascrizione della segreteria telefonica è abilitata per impostazione predefinita e il mascheramento di volgarità è disabilitato per impostazione predefinita per tutte le organizzazioni e utenti. Tuttavia, è possibile controllarli utilizzando il cmdlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) e [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="c93e2-136">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="c93e2-137">I messaggi della segreteria telefonica ricevuti dagli utenti dell'organizzazione vengono trascritti nell'area geografica in cui è ospitato il tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="c93e2-137">Voicemail messages received by users in your organization are transcribed in the region where your Office 365 tenant is hosted.</span></span> <span data-ttu-id="c93e2-138">L'area in cui è ospitato il tenant potrebbe non essere la stessa area in cui si trova l'utente che riceve il messaggio della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="c93e2-138">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="c93e2-139">Per visualizzare l'area geografica in cui è ospitato il tenant, accedere alla pagina del [profilo dell'organizzazione](https://go.microsoft.com/fwlink/p/?linkid=2067339) e quindi fare clic su **Visualizza dettagli** accanto a **posizione dati**.</span><span class="sxs-lookup"><span data-stu-id="c93e2-139">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c93e2-140">Non è possibile creare una nuova istanza di criteri per la trascrizione e la trascrizione delle maschere profane usando il cmdlet **New-CsOnlineVoiceMailPolicy** e non è possibile rimuovere un'istanza di criteri esistente usando il cmdlet **Remove-CsOnlineVoiceMailPolicy** .</span><span class="sxs-lookup"><span data-stu-id="c93e2-140">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="c93e2-141">È possibile gestire le impostazioni di trascrizione per gli utenti che utilizzano i criteri segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="c93e2-141">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="c93e2-142">Per visualizzare tutte le istanze dei criteri di segreteria telefonica disponibili, è possibile usare il cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="c93e2-142">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="c93e2-143">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="c93e2-143">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy finestra risultati.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="c93e2-145">Disattivare la trascrizione per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="c93e2-145">Turning off transcription for your organization</span></span>

<span data-ttu-id="c93e2-p112">Dato che l'impostazione predefinita per la trascrizione è attiva per la propria organizzazione, si consiglia di disabilitarla utilizzando il cmdlet [set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c93e2-p112">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="c93e2-148">Attivazione del mascheramento di volgarità sulla trascrizione per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="c93e2-148">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="c93e2-149">Il mascheramento di volgarità sulla trascrizione è disabilitato per impostazione predefinita per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c93e2-149">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="c93e2-150">Se non vi è un requisito aziendale per abilitarlo, è possibile abilitare il mascheramento di volgarità sulla trascrizione tramite [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="c93e2-150">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="c93e2-151">Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="c93e2-151">To do this, run:</span></span>

```PowerShell
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="c93e2-152">Disattivare la trascrizione per un utente</span><span class="sxs-lookup"><span data-stu-id="c93e2-152">Turning off transcription for a user</span></span>

<span data-ttu-id="c93e2-153">I criteri utente vengono valutati prima delle impostazioni predefinite dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="c93e2-153">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="c93e2-154">Ad esempio, se la trascrizione della segreteria telefonica è abilitata per tutti gli utenti, puoi assegnare un criterio per disabilitare la trascrizione per un utente specifico usando il cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="c93e2-154">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="c93e2-155">Per disabilitare la trascrizione per un singolo utente, eseguire:</span><span class="sxs-lookup"><span data-stu-id="c93e2-155">To disable transcription for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="c93e2-156">Attivazione del mascheramento di volgarità sulla trascrizione per un utente</span><span class="sxs-lookup"><span data-stu-id="c93e2-156">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="c93e2-157">Per abilitare il mascheramento di volgarità sulla trascrizione per un utente specifico, è possibile assegnare un criterio per abilitare il mascheramento di volgarità sulla trascrizione per un utente specifico utilizzando il cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="c93e2-157">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="c93e2-158">Per abilitare il mascheramento di volgarità sulla trascrizione per un singolo utente, eseguire:</span><span class="sxs-lookup"><span data-stu-id="c93e2-158">To enable transcription profanity masking for a single user, run:</span></span>

```PowerShell
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="c93e2-p115">Il servizio di segreteria telefonica in Office 365 memorizza in cache i criteri di segreteria telefonica e aggiorna la cache ogni 4 ore. Perciò le modifiche apportate ai criteri possono impiegare fino a 4 ore per essere applicate.</span><span class="sxs-lookup"><span data-stu-id="c93e2-p115">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="c93e2-161">Aiutare gli utenti a imparare le funzioni della segreteria telefonica Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c93e2-161">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="c93e2-p116">Abbiamo informazioni e articoli di formazione per aiutare gli utenti a usare con successo la segreteria telefonica Skype for Business. Questi sono gli articoli che gli utenti vorranno consultare:</span><span class="sxs-lookup"><span data-stu-id="c93e2-p116">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="c93e2-164">[Controllare le opzioni e la segreteria telefonica di Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Questo articolo illustra come ascoltare i messaggi vocali in Skype for Business e ascoltare i messaggi vocali a velocità diverse.</span><span class="sxs-lookup"><span data-stu-id="c93e2-164">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="c93e2-165">Formazione per Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="c93e2-165">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="c93e2-166">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c93e2-166">Related topics</span></span>
[<span data-ttu-id="c93e2-167">Configurare Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c93e2-167">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="c93e2-168">Ecco cosa offre il Sistema telefonico in Office 365</span><span class="sxs-lookup"><span data-stu-id="c93e2-168">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="c93e2-169">Pianificare la migrazione per Skype for Business Server ed Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c93e2-169">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/SkypeForBusiness/hybrid/plan-um-migration)

