---
title: Configurare la segreteria telefonica cloud
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
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Informazioni su come configurare la segreteria telefonica cloud per gli utenti. '
ms.openlocfilehash: 8417d8338f8ba25b9f3c92d9fc4547ed861f8b8e
ms.sourcegitcommit: 4fb1c691f0f84d47e215c9c1775da9bdba875f61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/26/2019
ms.locfileid: "36184426"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="8e56a-103">Configurare la segreteria telefonica cloud</span><span class="sxs-lookup"><span data-stu-id="8e56a-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="8e56a-104">Questo articolo riguarda l' [amministratore di Office 365](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) che vuole configurare la funzionalità per il cloud Voicemail per tutti gli utenti dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="8e56a-104">This article is for the [Office 365 admin](https://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="8e56a-105">Cloud Voicemail supporta il deposito dei messaggi della segreteria telefonica solo in una cassetta postale di Exchange e non supporta sistemi di posta elettronica di terze parti.</span><span class="sxs-lookup"><span data-stu-id="8e56a-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

## <a name="cloud-only-environments-set-up-cloud-voicemail"></a><span data-ttu-id="8e56a-106">Ambienti solo cloud: configurare la segreteria telefonica cloud</span><span class="sxs-lookup"><span data-stu-id="8e56a-106">Cloud-only environments: Set up Cloud Voicemail</span></span>

<span data-ttu-id="8e56a-107">Per gli utenti di Skype for business online e per i piani di chiamata, cloud Voicemail viene configurato automaticamente e provisionato per gli utenti dopo l'assegnazione di una licenza per il **sistema telefonico** e di un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="8e56a-107">For Skype for Business Online and Calling Plans users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="8e56a-108">Se la funzione Sistema telefonico non è inclusa nel tuo piano, può essere necessario acquistare licenze per il componente aggiuntivo **Sistema telefonico**.</span><span class="sxs-lookup"><span data-stu-id="8e56a-108">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="8e56a-109">Inoltre è necessario acquistare una licenza Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8e56a-109">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="8e56a-110">Vedere [licenze per i componenti aggiuntivi Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="8e56a-110">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="8e56a-111">[Assegnare o rimuovere licenze per Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [assegnare le licenze di Microsoft teams](assign-teams-licenses.md)e le licenze di Exchange Online agli utenti della propria azienda.</span><span class="sxs-lookup"><span data-stu-id="8e56a-111">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span> <span data-ttu-id="8e56a-112">Terminate queste operazioni, potranno ricevere i messaggi vocali.</span><span class="sxs-lookup"><span data-stu-id="8e56a-112">After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="8e56a-p103">Il supporto per la trascrizione segreteria telefonica è stato aggiunto a partire da marzo 2017 ed è attivato per impostazione predefinita per tutte le organizzazioni e gli utenti. Puoi disattivare la trascrizione per la tua organizzazione usando Windows PowerShell e attenendoti alle seguenti istruzioni.</span><span class="sxs-lookup"><span data-stu-id="8e56a-p103">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="8e56a-115">Sistema telefonico con ambienti locali</span><span class="sxs-lookup"><span data-stu-id="8e56a-115">Phone System with on-premises environments</span></span>

<span data-ttu-id="8e56a-116">Le informazioni seguenti includono la configurazione della segreteria telefonica cloud per l'utilizzo con ambienti di piano chiamante locali.</span><span class="sxs-lookup"><span data-stu-id="8e56a-116">The following information is about configuring Cloud Voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="8e56a-117">Se la funzione Sistema telefonico non è inclusa nel tuo piano, può essere necessario acquistare licenze per il componente aggiuntivo **Sistema telefonico**.</span><span class="sxs-lookup"><span data-stu-id="8e56a-117">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="8e56a-118">Inoltre è necessario acquistare una licenza Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="8e56a-118">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="8e56a-119">Vedere [licenze per i componenti aggiuntivi Microsoft teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="8e56a-119">See [Microsoft Teams add-on licensing](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="8e56a-120">[Assegnare o rimuovere licenze per Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), [assegnare le licenze di Microsoft teams](assign-teams-licenses.md)e le licenze di Exchange Online agli utenti della propria azienda.</span><span class="sxs-lookup"><span data-stu-id="8e56a-120">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Microsoft Teams licenses](assign-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="8e56a-121">Seguire le istruzioni corrispondenti alla soluzione di chiamate PSTN locale distribuita per gli utenti.</span><span class="sxs-lookup"><span data-stu-id="8e56a-121">Follow instructions matching on-premises PSTN calling solution deployed for your users.</span></span> <span data-ttu-id="8e56a-122">Per Cloud Connector Edition, seguire le istruzioni nella sezione **Enable Users for Phone System Voice and voicemail Services** della [Guida alla configurazione di Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="8e56a-122">For Cloud Connector Edition, follow instructions in the **Enable users for Phone System voice and voicemail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/library/mt605228.aspx).</span></span> <span data-ttu-id="8e56a-123">Per le chiamate PSTN con Skype for Business Server, seguire [consentire agli utenti di VoIP aziendale in locale](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span><span class="sxs-lookup"><span data-stu-id="8e56a-123">For PSTN calling with Skype for Business Server, follow [Enable the users for Enterprise Voice on premises](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-the-users-for-enterprise-voice-on-premises).</span></span> <span data-ttu-id="8e56a-124">Per il routing diretto di teams, seguire la sezione **configurare il numero di telefono e abilitare l'organizzazione vocale e la segreteria telefonica** di [Configura routing diretto](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span><span class="sxs-lookup"><span data-stu-id="8e56a-124">For Teams Direct Routing, follow  the **Configure the phone number and enable enterprise voice and voicemail** section of [Configure Direct Routing](https://docs.microsoft.com/en-us/microsoftteams/direct-routing-configure#configure-the-phone-number-and-enable-enterprise-voice-and-voicemail).</span></span>

4. <span data-ttu-id="8e56a-p106">Il supporto per la trascrizione segreteria telefonica è stato aggiunto a partire da marzo 2017 ed è attivato per impostazione predefinita per tutte le organizzazioni e gli utenti. Puoi disattivare la trascrizione per la tua organizzazione usando Windows PowerShell e attenendoti alle seguenti istruzioni.</span><span class="sxs-lookup"><span data-stu-id="8e56a-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>

5. <span data-ttu-id="8e56a-127">I messaggi della segreteria telefonica vengono recapitati alla cassetta postale di Exchange degli utenti tramite SMTP instradato tramite Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="8e56a-127">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="8e56a-128">Per consentire il corretto recapito di questi messaggi, verificare che i connettori di Exchange siano configurati correttamente tra i server Exchange e la protezione di Exchange Online. [Usare i connettori per configurare il flusso di posta](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="8e56a-128">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](https://docs.microsoft.com/en-us/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

6. <span data-ttu-id="8e56a-129">Per abilitare le caratteristiche della segreteria telefonica, ad esempio la personalizzazione dei messaggi di saluto e la segreteria telefonica visiva nei client Skype for business, è necessaria la connettività da Office 365 alla cassetta postale di Exchange Server tramite servizi Web Exchange.</span><span class="sxs-lookup"><span data-stu-id="8e56a-129">To enable Voicemail features such as customizing greetings, and visual voicemail in Skype for Business clients, connectivity from Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="8e56a-130">Per abilitare questa connettività, è necessario configurare il nuovo protocollo di autenticazione OAuth di Exchange descritto in [configurare l'autenticazione OAuth tra le organizzazioni Exchange e Exchange Online](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx)oppure eseguire la procedura guidata ibrida di Exchange da Exchange 2013 CU5 o maggiore.</span><span class="sxs-lookup"><span data-stu-id="8e56a-130">To enable this connectivity you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](https://technet.microsoft.com/en-us/library/dn594521(v=exchg.150).aspx), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="8e56a-131">Inoltre, è necessario configurare Integration e OAuth tra Skype for business online ed Exchange Server descritto in [configurare Integration e OAuth tra Skype for business online ed Exchange Server](https://docs.microsoft.com/en-us/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span><span class="sxs-lookup"><span data-stu-id="8e56a-131">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](https://docs.microsoft.com/en-us/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="8e56a-132">Impostazione dei criteri di segreteria telefonica dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="8e56a-132">Setting voicemail policies in your organization</span></span>

> [!WARNING]
> <span data-ttu-id="8e56a-133">Per i clienti Skype for business, la disabilitazione della segreteria telefonica tramite un criterio di chiamata di Microsoft teams può anche disabilitare il servizio di segreteria telefonica per gli utenti di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="8e56a-133">For Skype for Business customers, disabling voicemail through a Microsoft Teams calling policy might also disable the voicemail service for your Skype for Business users.</span></span>

<span data-ttu-id="8e56a-134">La trascrizione della segreteria telefonica è abilitata per impostazione predefinita e il mascheramento di volgarità è disabilitato per impostazione predefinita per tutte le organizzazioni e utenti. Tuttavia, è possibile controllarli utilizzando il cmdlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) e [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx).</span><span class="sxs-lookup"><span data-stu-id="8e56a-134">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlets.</span></span>

<span data-ttu-id="8e56a-135">I messaggi della segreteria telefonica ricevuti dagli utenti dell'organizzazione vengono trascritti nell'area geografica in cui è ospitato il tenant di Office 365.</span><span class="sxs-lookup"><span data-stu-id="8e56a-135">Voicemail messages received by users in your organization are transcribed in the region where your Office 365 tenant is hosted.</span></span> <span data-ttu-id="8e56a-136">L'area in cui è ospitato il tenant potrebbe non essere la stessa area in cui si trova l'utente che riceve il messaggio della segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="8e56a-136">The region where your tenant is hosted might not be the same region where the user receiving the voicemail message is located.</span></span> <span data-ttu-id="8e56a-137">Per visualizzare l'area geografica in cui è ospitato il tenant, accedere alla pagina del [profilo dell'organizzazione](https://go.microsoft.com/fwlink/p/?linkid=2067339) e quindi fare clic su **Visualizza dettagli** accanto a **posizione dati**.</span><span class="sxs-lookup"><span data-stu-id="8e56a-137">To view the region where your tenant is hosted, go to the [Organization profile](https://go.microsoft.com/fwlink/p/?linkid=2067339) page and then click **View details** next to **Data location**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e56a-138">Non è possibile creare una nuova istanza di criteri per la trascrizione e la trascrizione delle maschere profane usando il cmdlet **New-CsOnlineVoiceMailPolicy** e non è possibile rimuovere un'istanza di criteri esistente usando il cmdlet **Remove-CsOnlineVoiceMailPolicy** .</span><span class="sxs-lookup"><span data-stu-id="8e56a-138">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>

<span data-ttu-id="8e56a-139">È possibile gestire le impostazioni di trascrizione per gli utenti che utilizzano i criteri segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="8e56a-139">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="8e56a-140">Per visualizzare tutte le istanze dei criteri di segreteria telefonica disponibili, è possibile usare il cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="8e56a-140">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>

 <span data-ttu-id="8e56a-141">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="8e56a-141">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy finestra risultati.](media/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="8e56a-143">Disattivare la trascrizione per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="8e56a-143">Turning off transcription for your organization</span></span>

<span data-ttu-id="8e56a-p111">Dato che l'impostazione predefinita per la trascrizione è attiva per la propria organizzazione, si consiglia di disabilitarla utilizzando il cmdlet [set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8e56a-p111">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx). To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="8e56a-146">Attivazione del mascheramento di volgarità sulla trascrizione per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="8e56a-146">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="8e56a-147">Il mascheramento di volgarità sulla trascrizione è disabilitato per impostazione predefinita per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8e56a-147">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="8e56a-148">Se non vi è un requisito aziendale per abilitarlo, è possibile abilitare il mascheramento di volgarità sulla trascrizione tramite [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="8e56a-148">If there is a business requirement to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798310.aspx).</span></span> <span data-ttu-id="8e56a-149">Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="8e56a-149">To do this, run:</span></span>

```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="8e56a-150">Disattivare la trascrizione per un utente</span><span class="sxs-lookup"><span data-stu-id="8e56a-150">Turning off transcription for a user</span></span>

<span data-ttu-id="8e56a-151">I criteri utente vengono valutati prima delle impostazioni predefinite dell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="8e56a-151">User policies are evaluated before the organizational default settings.</span></span> <span data-ttu-id="8e56a-152">Ad esempio, se la trascrizione della segreteria telefonica è abilitata per tutti gli utenti, puoi assegnare un criterio per disabilitare la trascrizione per un utente specifico usando il cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="8e56a-152">For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="8e56a-153">Per disabilitare la trascrizione per un singolo utente, eseguire:</span><span class="sxs-lookup"><span data-stu-id="8e56a-153">To disable transcription for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="8e56a-154">Attivazione del mascheramento di volgarità sulla trascrizione per un utente</span><span class="sxs-lookup"><span data-stu-id="8e56a-154">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="8e56a-155">Per abilitare il mascheramento di volgarità sulla trascrizione per un utente specifico, è possibile assegnare un criterio per abilitare il mascheramento di volgarità sulla trascrizione per un utente specifico utilizzando il cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="8e56a-155">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user by using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>

<span data-ttu-id="8e56a-156">Per abilitare il mascheramento di volgarità sulla trascrizione per un singolo utente, eseguire:</span><span class="sxs-lookup"><span data-stu-id="8e56a-156">To enable transcription profanity masking for a single user, run:</span></span>

```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="8e56a-p114">Il servizio di segreteria telefonica in Office 365 memorizza in cache i criteri di segreteria telefonica e aggiorna la cache ogni 4 ore. Perciò le modifiche apportate ai criteri possono impiegare fino a 4 ore per essere applicate.</span><span class="sxs-lookup"><span data-stu-id="8e56a-p114">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span>

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="8e56a-159">Aiutare gli utenti a imparare le funzioni della segreteria telefonica Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8e56a-159">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="8e56a-p115">Abbiamo informazioni e articoli di formazione per aiutare gli utenti a usare con successo la segreteria telefonica Skype for Business. Questi sono gli articoli che gli utenti vorranno consultare:</span><span class="sxs-lookup"><span data-stu-id="8e56a-p115">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="8e56a-162">[Controllare le opzioni e la segreteria telefonica di Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Questo articolo illustra come ascoltare i messaggi vocali in Skype for Business e ascoltare i messaggi vocali a velocità diverse.</span><span class="sxs-lookup"><span data-stu-id="8e56a-162">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="8e56a-163">Formazione per Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="8e56a-163">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="8e56a-164">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="8e56a-164">Related topics</span></span>
[<span data-ttu-id="8e56a-165">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="8e56a-165">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="8e56a-166">Ecco cosa offre il Sistema telefonico in Office 365</span><span class="sxs-lookup"><span data-stu-id="8e56a-166">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="8e56a-167">Pianificare la migrazione a Skype for Business Server e Exchange Server</span><span class="sxs-lookup"><span data-stu-id="8e56a-167">Plan for Skype for Business Server and Exchange Server migration</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/hybrid/plan-um-migration)


