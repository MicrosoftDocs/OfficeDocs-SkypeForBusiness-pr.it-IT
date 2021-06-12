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
- m365initiative-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Phone System
description: 'Informazioni su come configurare i Cloud Voicemail per gli utenti. '
ms.openlocfilehash: c6fbd02e30c5be0280b05088a1cec281c2534039
ms.sourcegitcommit: 31c5b9cd3d4f500e1f9d7823052dae8f8c298b1e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/11/2021
ms.locfileid: "52901913"
---
# <a name="set-up-cloud-voicemail"></a><span data-ttu-id="c4962-103">Configurare Cloud Voicemail</span><span class="sxs-lookup"><span data-stu-id="c4962-103">Set up Cloud Voicemail</span></span>

<span data-ttu-id="c4962-104">Questo articolo è per l'amministratore Microsoft 365 o Office 365, come descritto [in](/microsoft-365/admin/add-users/about-admin-roles) Informazioni sui ruoli di amministratore che vogliono configurare la caratteristica Cloud Voicemail per tutti gli utenti dell'azienda.</span><span class="sxs-lookup"><span data-stu-id="c4962-104">This article is for the Microsoft 365 or Office 365 admin as described in [About admin roles](/microsoft-365/admin/add-users/about-admin-roles) who wants to set up the Cloud Voicemail feature for everyone in the business.</span></span>

> [!NOTE]
> <span data-ttu-id="c4962-105">Cloud Voicemail supporta il deposito dei messaggi della segreteria telefonica solo in una cassetta postale Exchange e non supporta sistemi di posta elettronica di terze parti.</span><span class="sxs-lookup"><span data-stu-id="c4962-105">Cloud Voicemail supports depositing voicemail messages only in an Exchange mailbox and doesn't support any third-party email systems.</span></span> 

> [!NOTE]
> <span data-ttu-id="c4962-106">Quando un delegato risponde a una chiamata per conto di un delegato, le notifiche non sono disponibili Cloud Voicemail.</span><span class="sxs-lookup"><span data-stu-id="c4962-106">When a delegate answers a call on behalf of a delegator, notifications are not available in Cloud Voicemail.</span></span> <span data-ttu-id="c4962-107">Gli utenti possono ricevere notifiche per le chiamate perse.</span><span class="sxs-lookup"><span data-stu-id="c4962-107">Users can receive notifications for missed calls.</span></span>

## <a name="cloud-only-environments-set-up-cloud-voicemail-for-online-phone-system-users"></a><span data-ttu-id="c4962-108">Ambienti solo cloud: configurare le Cloud Voicemail per gli utenti Sistema telefonico online</span><span class="sxs-lookup"><span data-stu-id="c4962-108">Cloud-only environments: Set up Cloud Voicemail for Online Phone System users</span></span>

<span data-ttu-id="c4962-109">Per gli utenti Sistema telefonico online, Cloud Voicemail viene automaticamente configurato ed eseguito  il provisioning per gli utenti dopo l'assegnazione di una licenza Sistema telefonico agli utenti.</span><span class="sxs-lookup"><span data-stu-id="c4962-109">For Online Phone System users, Cloud Voicemail is automatically set up and provisioned for users after you assign a **Phone System** license to the users.</span></span> 

> [!NOTE]
> <span data-ttu-id="c4962-110">Per gli utenti Skype for Business Sistema telefonico online con numeri di telefono locali forniti, potrebbe essere necessario abilitare la segreteria telefonica ospitata con [Set-CsUser -HostedVoicemail $True](/powershell/module/skype/set-csuser?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="c4962-110">For Online Skype for Business Phone System users with on-premises provided phone numbers, you may need to enable hosted voice mail with [Set-CsUser -HostedVoicemail $True](/powershell/module/skype/set-csuser?view=skype-ps).</span></span> 

## <a name="set-up-cloud-voicemail-for-exchange-server-mailbox-users"></a><span data-ttu-id="c4962-111">Configurare le Cloud Voicemail per gli utenti Exchange Server cassette postali</span><span class="sxs-lookup"><span data-stu-id="c4962-111">Set up Cloud Voicemail for Exchange Server Mailbox Users</span></span>

<span data-ttu-id="c4962-112">Le informazioni seguenti riguardano la configurazione di Cloud Voicemail per l'utilizzo con utenti online per Sistema telefonico ma che hanno la propria cassetta postale Exchange Server.</span><span class="sxs-lookup"><span data-stu-id="c4962-112">The following information is about configuring Cloud Voicemail to work with users who are online for Phone System but have their mailbox on Exchange Server.</span></span> 
  
1. <span data-ttu-id="c4962-113">I messaggi della segreteria telefonica vengono recapitati alla cassetta postale Exchange degli utenti tramite SMTP instradati tramite Exchange Online Protection.</span><span class="sxs-lookup"><span data-stu-id="c4962-113">Voicemail messages are delivered to users' Exchange mailbox via SMTP routed through Exchange Online Protection.</span></span> <span data-ttu-id="c4962-114">Per abilitare il recapito corretto di questi messaggi, assicurarsi che i connettori Exchange siano configurati correttamente tra i server di Exchange e Exchange Online Protection; [Usare Connettori per configurare la posta Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span><span class="sxs-lookup"><span data-stu-id="c4962-114">To enable successful delivery of these messages, please be sure that Exchange Connectors are configured correctly between your Exchange servers and Exchange Online Protection; [Use Connectors to Configure Mail Flow](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).</span></span> 

2. <span data-ttu-id="c4962-115">Per abilitare le funzionalità della segreteria telefonica, come la personalizzazione dei messaggi di saluto e della segreteria telefonica visiva nei client Skype for Business, è necessaria la connettività da Microsoft 365 o Office 365 alla cassetta postale del server Exchange tramite servizi Web Exchange.</span><span class="sxs-lookup"><span data-stu-id="c4962-115">To enable Voicemail features such as customizing greetings and visual voicemail in Skype for Business clients, connectivity from Microsoft 365 or Office 365 to the Exchange server mailbox via Exchange Web Services is required.</span></span> <span data-ttu-id="c4962-116">Per abilitare questa connettività, è necessario configurare il nuovo protocollo di autenticazione Oauth di Exchange descritto in Configurare l'autenticazione [OAuth](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help)tra organizzazioni di Exchange e Exchange Online oppure eseguire la procedura guidata ibrida di Exchange da Exchange 2013 CU5 o versione successiva.</span><span class="sxs-lookup"><span data-stu-id="c4962-116">To enable this connectivity, you must configure the new Exchange Oauth authentication protocol described in [Configure OAuth authentication between Exchange and Exchange Online organizations](/exchange/configure-oauth-authentication-between-exchange-and-exchange-online-organizations-exchange-2013-help), or run the Exchange Hybrid Wizard from Exchange 2013 CU5 or greater.</span></span> <span data-ttu-id="c4962-117">Inoltre, è necessario configurare l'integrazione e Oauth tra Skype for Business Online e il server Exchange descritto in Configurare l'integrazione e [OAuth](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises)tra Skype for Business Online e Exchange Server .</span><span class="sxs-lookup"><span data-stu-id="c4962-117">Additionally, you must configure integration and Oauth between Skype for Business Online and Exchange server described in [Configure Integration and OAuth between Skype for Business Online and Exchange Server](/skypeforbusiness/deploy/integrate-with-exchange-server/oauth-with-online-and-on-premises).</span></span> 

## <a name="set-up-cloud-voicemail-for-skype-for-business-server-users"></a><span data-ttu-id="c4962-118">Configurare i Cloud Voicemail per Skype for Business Server utenti</span><span class="sxs-lookup"><span data-stu-id="c4962-118">Set up Cloud Voicemail for Skype for Business Server Users</span></span>

<span data-ttu-id="c4962-119">Per configurare Skype for Business utenti del server per Cloud Voicemail, vedere Pianificare Cloud Voicemail per gli utenti [locali.](/skypeforbusiness/hybrid/plan-cloud-voicemail)</span><span class="sxs-lookup"><span data-stu-id="c4962-119">To configure Skype for Business server users for Cloud Voicemail, please see [Plan Cloud Voicemail service for on-premises users](/skypeforbusiness/hybrid/plan-cloud-voicemail).</span></span>

## <a name="enabling-protected-voicemail-in-your-organization"></a><span data-ttu-id="c4962-120">Abilitazione della segreteria telefonica protetta nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="c4962-120">Enabling protected voicemail in your organization</span></span>

<span data-ttu-id="c4962-121">Quando un utente lascia un messaggio della segreteria telefonica per un utente dell'organizzazione, la segreteria telefonica viene recapitata alla cassetta postale dell'utente come allegato di un messaggio di posta elettronica.</span><span class="sxs-lookup"><span data-stu-id="c4962-121">When someone leaves a voicemail message for a user in your organization, the voicemail is delivered to the user's mailbox as an email message attachment.</span></span> <span data-ttu-id="c4962-122">Usando le regole del flusso di posta per applicare la crittografia dei messaggi, è possibile impedire l'inoltro di tali messaggi della segreteria telefonica ad altri destinatari.</span><span class="sxs-lookup"><span data-stu-id="c4962-122">Using mail flow rules to apply message encryption, you can prevent those voicemail messages from being forwarded to other recipients.</span></span> <span data-ttu-id="c4962-123">Quando si abilita la segreteria telefonica protetta, gli utenti possono ascoltare i messaggi della segreteria telefonica protetti chiamando nella propria cassetta postale della segreteria telefonica o aprendo il messaggio in Outlook, Outlook sul Web o in Outlook per Android o iOS.</span><span class="sxs-lookup"><span data-stu-id="c4962-123">When you enable protected voicemail, users can listen to protected voicemail messages by calling into their voicemail mailbox or by opening the message in Outlook, Outlook on the web, or in Outlook for Android or iOS.</span></span> <span data-ttu-id="c4962-124">I messaggi della segreteria telefonica protetta non possono essere aperti in Skype for Business o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c4962-124">Protected voicemail messages can't be opened in Skype for Business or Microsoft Teams.</span></span>

<span data-ttu-id="c4962-125">Per altre informazioni sulla crittografia dei messaggi, vedere [Crittografia della posta elettronica](/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="c4962-125">For more information about message encryption, see [Email encryption](/microsoft-365/compliance/email-encryption?view=o365-worldwide).</span></span>

<span data-ttu-id="c4962-126">Per configurare la segreteria telefonica protetta, eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="c4962-126">To set up protected voicemail, do the following:</span></span>

1. <span data-ttu-id="c4962-127">Passare a https://admin.microsoft.com e accedere con un account con autorizzazioni di amministratore globale.</span><span class="sxs-lookup"><span data-stu-id="c4962-127">Go to https://admin.microsoft.com and sign in using an account with global administrator permissions.</span></span>
2. <span data-ttu-id="c4962-128">Selezionare **Mostra tutto** e quindi passare a Interfaccia di **amministrazione**  >  **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="c4962-128">Select **Show all** and then go to **Admin centers** > **Exchange**.</span></span>
3. <span data-ttu-id="c4962-129">Nell'Exchange di amministrazione selezionare **Regole flusso di**  >  **posta**.</span><span class="sxs-lookup"><span data-stu-id="c4962-129">In the Exchange Admin Center, select **Mail flow** > **Rules**.</span></span>
4. <span data-ttu-id="c4962-130">Selezionare **+** **Aggiungi** e quindi selezionare Applica Office 365 Message Encryption **protezione dei diritti ai messaggi**.</span><span class="sxs-lookup"><span data-stu-id="c4962-130">Select **+** **Add**, and then select **Apply Office 365 Message Encryption and rights protection to messages**.</span></span>
5. <span data-ttu-id="c4962-131">Specificare un nome per la nuova regola del flusso di posta e quindi in Applica questa regola **se** selezionare Le proprietà del messaggio Includono il tipo di messaggio  >    >  **Segreteria telefonica.**</span><span class="sxs-lookup"><span data-stu-id="c4962-131">Provide a name for the new mail flow rule and then under **Apply this rule if**, select **The message properties** > **Include the message type** > **Voice mail**.</span></span> <span data-ttu-id="c4962-132">Scegliere **OK**.</span><span class="sxs-lookup"><span data-stu-id="c4962-132">Select **OK**.</span></span>
6. <span data-ttu-id="c4962-133">In **Eseguire le operazioni seguenti** selezionare Applica Office 365 Message Encryption protezione dei diritti al **messaggio** con e quindi selezionare **Seleziona uno**.</span><span class="sxs-lookup"><span data-stu-id="c4962-133">Under **Do the following**, select **Apply Office 365 Message Encryption and rights protection to the message with** and then select **Select one**.</span></span> <span data-ttu-id="c4962-134">In **Modello RMS** selezionare Non **inoltrare**.</span><span class="sxs-lookup"><span data-stu-id="c4962-134">Under **RMS template**, select **Do not forward**.</span></span> <span data-ttu-id="c4962-135">Selezionare **OK** e quindi **Salva**.</span><span class="sxs-lookup"><span data-stu-id="c4962-135">Select **OK** and then **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="c4962-136">Se **l'elenco dei** modelli RMS è vuoto, è necessario configurare Crittografia messaggi.</span><span class="sxs-lookup"><span data-stu-id="c4962-136">If the **RMS template** list is empty, you need to set up Message Encryption.</span></span> <span data-ttu-id="c4962-137">Per altre informazioni sulla configurazione di Message Encryption, vedere gli articoli seguenti:</span><span class="sxs-lookup"><span data-stu-id="c4962-137">For more information about setting up Message Encryption, see the following articles:</span></span>
    > - [<span data-ttu-id="c4962-138">Configurare nuove funzionalità di Crittografia messaggi</span><span class="sxs-lookup"><span data-stu-id="c4962-138">Set up new Message Encryption capabilities</span></span>](/microsoft-365/compliance/set-up-new-message-encryption-capabilities?view=o365-worldwide)
    > - [<span data-ttu-id="c4962-139">Configurazione e gestione di modelli per Azure Information Protection</span><span class="sxs-lookup"><span data-stu-id="c4962-139">Configuring and managing templates for Azure Information Protection</span></span>](/information-protection/deploy-use/configure-policy-templates)
    > - [<span data-ttu-id="c4962-140">Opzione Non inoltrare per i messaggi di posta elettronica</span><span class="sxs-lookup"><span data-stu-id="c4962-140">Do Not Forward option for emails</span></span>](/information-protection/deploy-use/configure-usage-rights#do-not-forward-option-for-emails)

## <a name="help-your-users-learn-teams-voicemail-features"></a><span data-ttu-id="c4962-141">Aiutare gli utenti a imparare a Teams della segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="c4962-141">Help your users learn Teams voicemail features</span></span>

<span data-ttu-id="c4962-142">Per gli utenti sono disponibili le informazioni seguenti sulla gestione delle impostazioni della segreteria telefonica e su altre funzionalità per le chiamate in Teams:</span><span class="sxs-lookup"><span data-stu-id="c4962-142">We have the following information for your users on managing their voicemail settings as well as other calling features in Teams:</span></span>

- <span data-ttu-id="c4962-143">[Gestisci le impostazioni della chiamata in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span><span class="sxs-lookup"><span data-stu-id="c4962-143">[Manage your call settings in Teams](https://support.office.com/article/manage-your-call-settings-in-teams-456cb611-3477-496f-b31a-6ab752a7595f).</span></span> <span data-ttu-id="c4962-144">Questo articolo spiega come gestire tutte le funzionalità per le chiamate Teams per gli utenti finali.</span><span class="sxs-lookup"><span data-stu-id="c4962-144">This article explains how to manage all end-user Teams calling features.</span></span> 

## <a name="help-your-users-learn-skype-for-business-voicemail-features"></a><span data-ttu-id="c4962-145">Aiutare gli utenti a imparare le funzioni della segreteria telefonica Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c4962-145">Help your users learn Skype for Business voicemail features</span></span>

<span data-ttu-id="c4962-p109">Abbiamo informazioni e articoli di formazione per aiutare gli utenti a usare con successo la segreteria telefonica Skype for Business. Questi sono gli articoli che gli utenti vorranno consultare:</span><span class="sxs-lookup"><span data-stu-id="c4962-p109">We have training information and articles to help your users be successful with Skype for Business voicemail. Point them to the following articles:</span></span>

- <span data-ttu-id="c4962-148">[Controllare le opzioni e la segreteria telefonica di Skype for Business](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): Questo articolo illustra come ascoltare i messaggi vocali in Skype for Business e ascoltare i messaggi vocali a velocità diverse.</span><span class="sxs-lookup"><span data-stu-id="c4962-148">[Check Skype for Business voicemail and options](https://support.office.com/article/2deea7f8-831f-4e85-a0d4-b34da55945a8): This article explains how to listen to your voicemail in Skype for Business, change your voice mail greeting, change your voicemail settings, and listen to your voicemail at different speeds.</span></span>

- [<span data-ttu-id="c4962-149">Formazione per Skype for Business 2016</span><span class="sxs-lookup"><span data-stu-id="c4962-149">Skype for Business 2016 training</span></span>](https://support.office.com/article/eb2081bc-fd0a-4eda-94da-5a39f369ee74)

## <a name="related-topics"></a><span data-ttu-id="c4962-150">Argomenti correlati</span><span class="sxs-lookup"><span data-stu-id="c4962-150">Related topics</span></span>
[<span data-ttu-id="c4962-151">Configurare Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="c4962-151">Set up Skype for Business Online</span></span>](/skypeforbusiness/set-up-skype-for-business-online/set-up-skype-for-business-online)

[<span data-ttu-id="c4962-152">Vantaggi offerti dal Sistema telefonico</span><span class="sxs-lookup"><span data-stu-id="c4962-152">Here's what you get with Phone System</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="c4962-153">Pianificare la migrazione per Skype for Business Server ed Exchange Server</span><span class="sxs-lookup"><span data-stu-id="c4962-153">Plan for Skype for Business Server and Exchange Server migration</span></span>](/SkypeForBusiness/hybrid/plan-um-migration)
