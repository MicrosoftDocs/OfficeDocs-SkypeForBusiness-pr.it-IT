---
title: Configurazione di sistema telefonico segreteria telefonica
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: 9c590873-b014-4df3-9e27-1bb97322a79d
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
description: 'Learn how to set up the phone system (Cloud PBX) voicemail for your Skype for Business users. '
ms.openlocfilehash: 847d0f962b25ca54d7cd1ed86e8ac53b1d544f3a
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2018
---
# <a name="set-up-phone-system-voicemail"></a><span data-ttu-id="19827-103">Configurazione di sistema telefonico segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="19827-103">Set up Phone System voicemail</span></span>

<span data-ttu-id="19827-104">In questo articolo è per l' [amministratore di Office 365](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) che si desidera configurare la funzionalità di segreteria telefonica sistema telefonico per tutti gli utenti nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="19827-104">This article is for the [Office 365 admin](http://support.office.com/article/da585eea-f576-4f55-a1e0-87090b6aaa9d) who wants to set up the Phone System voicemail feature for everyone in the business.</span></span>
  
> [!NOTE]
> <span data-ttu-id="19827-p101">La segreteria telefonica del Sistema telefonico supporta la registrazione di messaggi vocali solo in una casella Exchange e non supporta i sistemi e-mail di terze parti. Come meccanismo di fallback, la segreteria telefonica del Sistema telefonico può reinviare messaggi tramite SMTP, quindi gli utenti con una casella di posta su un sistema e-mail di terze parti riceveranno i messaggi vocali senza tempo di attività del servizio garantito o altre funzionalità della segreteria telefonica come la modifica del messaggio di saluto e altre impostazioni.</span><span class="sxs-lookup"><span data-stu-id="19827-p101">Phone System voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems. As a fallback mechanism, Phone System voicemail can resend messages using SMTP, which means users with a mailbox on a third-party email system will receive their voicemail messages with no guaranteed service uptime or other voicemail features, such as changing their greetings and other settings.</span></span> 
  
## <a name="cloud-only-environments-set-up-phone-system-voicemail"></a><span data-ttu-id="19827-107">Ambienti solo su cloud: Impostare la segreteria telefonica del Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="19827-107">Cloud-only environments: Set up Phone System voicemail</span></span>

<span data-ttu-id="19827-108">Per gli utenti Skype for Business online e Piani per chiamate, la segreteria telefonica del Sistema telefonico viene configurata e messa in servizio automaticamente per gli utenti una volta assegnata una licenza **Sistema telefonico** e un numero di telefono.</span><span class="sxs-lookup"><span data-stu-id="19827-108">For Skype for Business Online and Calling Plans users, Phone System voicemail is automatically set up and provisioned for users after you assign a **Phone System** license and a phone number to them.</span></span>
  
1. <span data-ttu-id="19827-109">Se la funzione Sistema telefonico non è inclusa nel tuo piano, può essere necessario acquistare licenze per il componente aggiuntivo **Sistema telefonico**.</span><span class="sxs-lookup"><span data-stu-id="19827-109">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="19827-110">Inoltre è necessario acquistare una licenza Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="19827-110">You may also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="19827-111">Vedere [Skype di licenza di componente aggiuntivo Business e i team di Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="19827-111">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="19827-p103">[Assegnare o rimuovere licenze per Office 365 per le aziende](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) e le[Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) e le licenze Exchange Online ai dipendenti dell'azienda. Terminate queste operazioni, potranno ricevere i messaggi vocali.</span><span class="sxs-lookup"><span data-stu-id="19827-p103">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business. After you do that, they will be able to receive voicemail messages!</span></span>
    
3. <span data-ttu-id="19827-p104">Il supporto per la trascrizione segreteria telefonica è stato aggiunto a partire da marzo 2017 ed è attivato per impostazione predefinita per tutte le organizzazioni e gli utenti. Puoi disattivare la trascrizione per la tua organizzazione usando Windows PowerShell e attenendoti alle seguenti istruzioni.</span><span class="sxs-lookup"><span data-stu-id="19827-p104">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span>
    
## <a name="phone-system-with-on-premises-environments"></a><span data-ttu-id="19827-116">Sistema telefonico con ambienti locali</span><span class="sxs-lookup"><span data-stu-id="19827-116">Phone System with on-premises environments</span></span>

<span data-ttu-id="19827-117">Le seguenti informazioni indicano come configurare la segreteria telefonica del Sistema telefonico con ambienti con Piano per chiamate locale.</span><span class="sxs-lookup"><span data-stu-id="19827-117">The following information is about configuring Phone System voicemail to work with on-premises Calling Plan environments.</span></span>
  
1. <span data-ttu-id="19827-118">Se la funzione Sistema telefonico non è inclusa nel tuo piano, può essere necessario acquistare licenze per il componente aggiuntivo **Sistema telefonico**.</span><span class="sxs-lookup"><span data-stu-id="19827-118">If the Phone System feature isn't included in your plan, you may need to purchase **Phone System** add-on licenses.</span></span> <span data-ttu-id="19827-119">Inoltre è necessario acquistare una licenza Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="19827-119">You also need to purchase an Exchange Online license.</span></span> <span data-ttu-id="19827-120">Vedere [Skype di licenza di componente aggiuntivo Business e i team di Microsoft](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="19827-120">See [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
2. <span data-ttu-id="19827-121">[Assegnare o rimuovere licenze per Office 365 per le aziende](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc) e le[Assegnare le licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) e le licenze Exchange Online ai dipendenti dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="19827-121">[Assign or remove licenses for Office 365 for business](http://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc), the [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), and the Exchange Online licenses to the people in your business.</span></span>
    
3. <span data-ttu-id="19827-122">Seguire le istruzioni nella sezione **Abilitazione degli utenti per la voce di sistema telefonico e servizi di segreteria telefonica** di [Configurare Skype per la Guida alla Business Cloud connettore Edition](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span><span class="sxs-lookup"><span data-stu-id="19827-122">Follow the instructions in the **Enable users for Phone System voice and voice mail services** section of the [Configure Skype for Business Cloud Connector Edition guide](https://technet.microsoft.com/en-us/library/mt605228.aspx).</span></span>
    
4. <span data-ttu-id="19827-p106">Il supporto per la trascrizione segreteria telefonica è stato aggiunto a partire da marzo 2017 ed è attivato per impostazione predefinita per tutte le organizzazioni e gli utenti. Puoi disattivare la trascrizione per la tua organizzazione usando Windows PowerShell e attenendoti alle seguenti istruzioni.</span><span class="sxs-lookup"><span data-stu-id="19827-p106">Support for voicemail transcription has been added as of March 2017 and is enabled by default for all organizations and users. You can disable transcription for your organization by using Windows PowerShell and following the steps below.</span></span> 
    
5. <span data-ttu-id="19827-125">Puoi anche consultare l'[Assistenza per segreteria telefonica Azure PBX per Exchange Server](https://support.microsoft.com/en-us/kb/3195158) per sapere come configurare la consegna dei messaggi vocali Azure per gli utenti di Sistema telefonico con una cassetta postale locale.</span><span class="sxs-lookup"><span data-stu-id="19827-125">You can also see [Azure PBX voicemail support for Exchange Server](https://support.microsoft.com/en-us/kb/3195158) to learn how to configure delivery of Azure voicemail messages for Phone System users who have a on-premises mailboxes.</span></span>
    
## <a name="setting-voicemail-policies-in-your-organization"></a><span data-ttu-id="19827-126">Impostazione dei criteri di segreteria telefonica dell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="19827-126">Setting voicemail policies in your organization</span></span>

<span data-ttu-id="19827-127">La trascrizione di segreteria telefonica è abilitata per impostazione predefinita e il mascheramento volgari trascrizione è disabilitato per impostazione predefinita per tutte le organizzazioni e utenti. Tuttavia, è possibile controllare li utilizzando i cmdlet [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) e [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="19827-127">Voicemail transcription is enabled by default and transcription profanity masking is disabled by default for all organizations and users; however, you can control them by using the [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx) and [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798311.aspx) cmdlets.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="19827-128">Non è possibile creare una nuova istanza di criteri per la trascrizione e volgari trascrizione utilizzando il cmdlet **New-CsOnlineVoiceMailPolicy** per il mascheramento e non è possibile rimuovere un'istanza di criterio esistente utilizzando il cmdlet **Remove-CsOnlineVoiceMailPolicy** .</span><span class="sxs-lookup"><span data-stu-id="19827-128">You can't create a new policy instance for transcription and transcription profanity masking using the **New-CsOnlineVoiceMailPolicy** cmdlet, and you can't remove an existing policy instance using the **Remove-CsOnlineVoiceMailPolicy** cmdlet.</span></span>
  
<span data-ttu-id="19827-129">È possibile gestire le impostazioni di trascrizione per gli utenti che utilizzano i criteri segreteria telefonica.</span><span class="sxs-lookup"><span data-stu-id="19827-129">You can manage the transcription settings for your users using voicemail policies.</span></span> <span data-ttu-id="19827-130">Per visualizzare tutte le istanze di criteri di segreteria telefonica disponibile, è possibile utilizzare il cmdlet [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) .</span><span class="sxs-lookup"><span data-stu-id="19827-130">To see all available voicemail policy instances, you can use the [Get-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798311.aspx) cmdlet.</span></span>
  
 <span data-ttu-id="19827-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span><span class="sxs-lookup"><span data-stu-id="19827-131">**PS C:\\> Get-CsOnlineVoicemailPolicy**</span></span>
  
![Get-CsOnlineVoiceMailPolicy results window.](../../images/6cea8310-2d71-4b95-8d36-688472845727.png)
  
### <a name="turning-off-transcription-for-your-organization"></a><span data-ttu-id="19827-133">Disattivare la trascrizione per la propria organizzazione</span><span class="sxs-lookup"><span data-stu-id="19827-133">Turning off transcription for your organization</span></span>

<span data-ttu-id="19827-p108">Dato che l'impostazione predefinita per la trascrizione è attiva per la propria organizzazione, si consiglia di disabilitarla utilizzando il cmdlet [set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="19827-p108">Because the default setting for transcription is on for your organization, you may want to disable it by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx). To do this, run:</span></span>
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscription $false
```

### <a name="turning-on-transcription-profanity-masking-for-your-organization"></a><span data-ttu-id="19827-136">Attivazione della maschera volgari trascrizione per l'organizzazione</span><span class="sxs-lookup"><span data-stu-id="19827-136">Turning on transcription profanity masking for your organization</span></span>

<span data-ttu-id="19827-137">Il mascheramento volgari trascrizione è disabilitato per impostazione predefinita per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="19827-137">Transcription profanity masking is disabled by default for your organization.</span></span> <span data-ttu-id="19827-138">Se non esiste un requisiti aziendali per abilitarla, è possibile abilitare volgari trascrizione per il mascheramento tramite [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span><span class="sxs-lookup"><span data-stu-id="19827-138">If there is a business requirements to enable it, you can enable transcription profanity masking by using [Set-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798310.aspx).</span></span> <span data-ttu-id="19827-139">Per farlo, eseguire quanto segue:</span><span class="sxs-lookup"><span data-stu-id="19827-139">To do this, run:</span></span>
  
```
Set-CsOnlineVoicemailPolicy -EnableTranscriptionProfanityMasking $true
```

### <a name="turning-off-transcription-for-a-user"></a><span data-ttu-id="19827-140">Disattivare la trascrizione per un utente</span><span class="sxs-lookup"><span data-stu-id="19827-140">Turning off transcription for a user</span></span>

<span data-ttu-id="19827-p110">I criteri utente vengono valutati prima delle impostazioni predefinite dell'organizzazione. Ad esempio, se la trascrizione segreteria telefonica è abilitata per tutti gli utenti è possibile assegnare un criterio per disabilitare la trascrizione per un utente specifico utilizzando il cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx).</span><span class="sxs-lookup"><span data-stu-id="19827-p110">User policies are evaluated before the organizational default settings. For example, if voicemail transcription is enabled for all of your users, you can assign a policy to disable transcription for a specific user using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/library/mt798309.aspx) cmdlet.</span></span>
  
<span data-ttu-id="19827-143">Per disabilitare la trascrizione per un singolo utente, eseguire:</span><span class="sxs-lookup"><span data-stu-id="19827-143">To disable transcription for a single user, run:</span></span>
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionDisabled -Identity sip:amosmar@contoso.com
```

### <a name="turning-on-transcription-profanity-masking-for-a-user"></a><span data-ttu-id="19827-144">Attivazione della maschera volgari trascrizione per un utente</span><span class="sxs-lookup"><span data-stu-id="19827-144">Turning on transcription profanity masking for a user</span></span>

<span data-ttu-id="19827-145">Per attivare la trascrizione volgari mascheramento per un utente specifico, è possibile assegnare un criterio per attivare la trascrizione volgari mascheramento per un utente specifico utilizzando il cmdlet [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) .</span><span class="sxs-lookup"><span data-stu-id="19827-145">To enable transcription profanity masking for a specific user, you can assign a policy to enable transcription profanity masking for a specific user using the [Grant-CsOnlineVoicemailPolicy](https://technet.microsoft.com/EN-US/library/mt798309.aspx) cmdlet.</span></span>
  
<span data-ttu-id="19827-146">Per abilitare volgari trascrizione per il mascheramento per un singolo utente, eseguire:</span><span class="sxs-lookup"><span data-stu-id="19827-146">To enable transcription profanity masking for a single user, run:</span></span>
  
```
Grant-CsOnlineVoicemailPolicy -PolicyName TranscriptionProfanityMaskingEnabled -Identity sip:amosmar@contoso.com
```

> [!IMPORTANT]
> <span data-ttu-id="19827-p111">Il servizio di segreteria telefonica in Office 365 memorizza in cache i criteri di segreteria telefonica e aggiorna la cache ogni 4 ore. Perciò le modifiche apportate ai criteri possono impiegare fino a 4 ore per essere applicate.</span><span class="sxs-lookup"><span data-stu-id="19827-p111">The voicemail service in Office 365 caches voicemail policies and updates the cache every 4 hours. So, policy changes that you make can take up to 4 hours to be applied.</span></span> 
  
## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="19827-149">Aiutare gli utenti a imparare le funzioni della segreteria telefonica Skype for Business</span><span class="sxs-lookup"><span data-stu-id="19827-149">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="19827-p112">Abbiamo informazioni e articoli di formazione per aiutare gli utenti a usare con successo la segreteria telefonica Skype for Business. Questi sono gli articoli che gli utenti vorranno consultare:</span><span class="sxs-lookup"><span data-stu-id="19827-p112">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>
  
- <span data-ttu-id="19827-152">[Controllare le opzioni e la segreteria telefonica di Skype for Business](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Questo articolo illustra come ascoltare i messaggi vocali in Skype for Business e ascoltare i messaggi vocali a velocità diverse.</span><span class="sxs-lookup"><span data-stu-id="19827-152">[Check Skype for Business voicemail and options](http://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>
    
- [<span data-ttu-id="19827-153">Formazione per Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="19827-153">Skype for Business 2016 training</span></span>](http://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)
    
## <a name="related-topics"></a><span data-ttu-id="19827-154">See also</span><span class="sxs-lookup"><span data-stu-id="19827-154">Related topics</span></span>
[<span data-ttu-id="19827-155">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="19827-155">Set up Skype for Business Online</span></span>](../../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

[<span data-ttu-id="19827-156">Ecco cosa offre il Sistema telefonico in Office 365</span><span class="sxs-lookup"><span data-stu-id="19827-156">Here's what you get with Phone System in Office 365</span></span>](../../what-is-phone-system-in-office-365/here-s-what-you-get-with-phone-system.md)

  
 