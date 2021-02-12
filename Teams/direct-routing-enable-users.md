---
title: Abilitare gli utenti per il routing diretto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Scopri come abilitare l'instradamento diretto del Sistema telefonico Microsoft.
ms.openlocfilehash: 5739797649c639e3259c6972da665ae0ced4b4bf
ms.sourcegitcommit: 0a9c5c01b37a93eecc369ca0ed49ae18f6a5065b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2020
ms.locfileid: "48655483"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="3cf60-103">Abilitare gli utenti per l'instradamento diretto, la voce e la segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="3cf60-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="3cf60-104">Questo articolo descrive come abilitare gli utenti per l'instradamento diretto del sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="3cf60-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="3cf60-105">Questo è il passaggio 2 della procedura seguente per la configurazione del routing diretto:</span><span class="sxs-lookup"><span data-stu-id="3cf60-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="3cf60-106">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="3cf60-106">Step 1.</span></span> [<span data-ttu-id="3cf60-107">Collegare il servizio SBC al Sistema telefonico Microsoft e convalidare la connessione</span><span class="sxs-lookup"><span data-stu-id="3cf60-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="3cf60-108">**Passaggio 2. Abilitare gli utenti per l'instradamento diretto, la voce e la segreteria**   telefonica (questo articolo)</span><span class="sxs-lookup"><span data-stu-id="3cf60-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="3cf60-109">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="3cf60-109">Step 3.</span></span> [<span data-ttu-id="3cf60-110">Configurare il routing vocale</span><span class="sxs-lookup"><span data-stu-id="3cf60-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="3cf60-111">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="3cf60-111">Step 4.</span></span> [<span data-ttu-id="3cf60-112">Convertire i numeri in un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="3cf60-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="3cf60-113">Per informazioni su tutti i passaggi necessari per configurare il routing diretto, vedere [Configurare l'instradamento diretto.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="3cf60-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="3cf60-114">Quando si è pronti ad abilitare gli utenti per il routing diretto, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="3cf60-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="3cf60-115">Creare un utente in Microsoft 365 o Office 365 e assegnare una licenza Sistema telefonico.</span><span class="sxs-lookup"><span data-stu-id="3cf60-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="3cf60-116">Assicurarsi che l'utente sia disponibile in Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="3cf60-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="3cf60-117">Configura il numero di telefono e abilita la segreteria telefonica aziendale.</span><span class="sxs-lookup"><span data-stu-id="3cf60-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="3cf60-118">Assegnare la modalità Solo Teams agli utenti.</span><span class="sxs-lookup"><span data-stu-id="3cf60-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="3cf60-119">Creare un utente e assegnare la licenza</span><span class="sxs-lookup"><span data-stu-id="3cf60-119">Create a user and assign the license</span></span> 

<span data-ttu-id="3cf60-120">Sono disponibili due opzioni per creare un nuovo utente in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="3cf60-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="3cf60-121">Tuttavia, Microsoft consiglia all'organizzazione di scegliere una delle opzioni per evitare problemi di routing:</span><span class="sxs-lookup"><span data-stu-id="3cf60-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="3cf60-122">Creare l'utente in Active Directory locale e sincronizzare l'utente con il cloud.</span><span class="sxs-lookup"><span data-stu-id="3cf60-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="3cf60-123">Vedere [Integrare le directory locali con Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect)</span><span class="sxs-lookup"><span data-stu-id="3cf60-123">See [Integrate your on-premises directories with Azure Active Directory](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="3cf60-124">Creare l'utente direttamente nell'interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="3cf60-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="3cf60-125">Vedere [Aggiungere utenti singolarmente o in blocco a Microsoft 365 o Office 365 - Guida per l'amministratore.](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</span><span class="sxs-lookup"><span data-stu-id="3cf60-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="3cf60-126">Se la distribuzione di Skype for Business online coesiste con Skype for Business 2015 o Lync 2010 o 2013 locale, l'unica opzione supportata è creare l'utente in Active Directory locale e sincronizzare l'utente con il cloud (opzione 1).</span><span class="sxs-lookup"><span data-stu-id="3cf60-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="3cf60-127">Per informazioni sui requisiti di licenza, vedere [licenze e altri requisiti](direct-routing-plan.md#licensing-and-other-requirements) in Pianificare il routing [diretto.](direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="3cf60-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a><span data-ttu-id="3cf60-128">Assicurarsi che l'utente sia ospitata online e che il numero di telefono non venga sincronizzato dalla distribuzione locale (applicabile per gli utenti abilitati per Skype for Business Server VoIP aziendale in fase di migrazione a Routing diretto di Teams)</span><span class="sxs-lookup"><span data-stu-id="3cf60-128">Ensure that the user is homed online and phone number is not being synced from on-premises (applicable for Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing)</span></span>

<span data-ttu-id="3cf60-129">L'instradamento diretto richiede che l'utente sia ospitata online.</span><span class="sxs-lookup"><span data-stu-id="3cf60-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="3cf60-130">È possibile verificare esaminando il parametro RegistrarPool, che deve avere un valore nel infra.lync.com dominio.</span><span class="sxs-lookup"><span data-stu-id="3cf60-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="3cf60-131">Anche il parametro OnPremLineUriManuallySet deve essere impostato su True.</span><span class="sxs-lookup"><span data-stu-id="3cf60-131">OnPremLineUriManuallySet parameter should also to be set to True.</span></span> <span data-ttu-id="3cf60-132">Questa operazione si ottiene configurando il numero di telefono e abilitando la segreteria telefonica e la voce aziendale con PowerShell di Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="3cf60-132">This is achieved by configuring the phone number and enable enterprise voice and voicemail using Skype for Business Online PowerShell.</span></span>

1. <span data-ttu-id="3cf60-133">Connettere una sessione di PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="3cf60-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="3cf60-134">Eseguire il comando:</span><span class="sxs-lookup"><span data-stu-id="3cf60-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="3cf60-135">Se OnPremLineUriManuallySet è impostato su False e LineUri viene popolato con un> di numero di telefono <E.164, pulisci i parametri usando Skype for Business Management Shell locale prima di configurare il numero di telefono con PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="3cf60-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, please clean the parameters using on-premises Skype for Business Management Shell, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="3cf60-136">Da Skype for Business Management Shell emettere il comando:</span><span class="sxs-lookup"><span data-stu-id="3cf60-136">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   <span data-ttu-id="3cf60-137">Dopo la sincronizzazione delle modifiche con Office 365, l'output previsto `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` sarà:</span><span class="sxs-lookup"><span data-stu-id="3cf60-137">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="3cf60-138">Configurare il numero di telefono e abilitare voIP aziendale e segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="3cf60-138">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="3cf60-139">Dopo aver creato l'utente e aver assegnato una licenza, il passaggio successivo consiste nel configurare il numero di telefono e la casella vocale dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3cf60-139">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="3cf60-140">Per aggiungere il numero di telefono e abilitare la segreteria telefonica:</span><span class="sxs-lookup"><span data-stu-id="3cf60-140">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="3cf60-141">Connettere una sessione di PowerShell di Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="3cf60-141">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="3cf60-142">Eseguire il comando:</span><span class="sxs-lookup"><span data-stu-id="3cf60-142">Issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    <span data-ttu-id="3cf60-143">Ad esempio, per aggiungere un numero di telefono per l'utente "In basso", immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3cf60-143">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    <span data-ttu-id="3cf60-144">Se gli utenti "Low" e "Stacy Quinn" condividono lo stesso numero di base con estensioni univoche, immetti quanto segue:</span><span class="sxs-lookup"><span data-stu-id="3cf60-144">If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following</span></span>
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388701;ext=1001 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI tel:+14255388701;ext=1002 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="3cf60-145">È consigliabile, ma non obbligatorio, che il numero di telefono utilizzato sia configurato come numero di telefono E.164 completo con codice paese.</span><span class="sxs-lookup"><span data-stu-id="3cf60-145">It's recommended, but not required, that the phone number used is configured as a full E.164 phone number with country code.</span></span> <span data-ttu-id="3cf60-146">È supportato per configurare i numeri di telefono con estensioni che verranno usate per cercare gli utenti quando la ricerca rispetto al numero di base restituisce più di un risultato.</span><span class="sxs-lookup"><span data-stu-id="3cf60-146">It is supported to configure phone numbers with extensions which will be used to lookup users when the lookup against the base number returns more than one result.</span></span> <span data-ttu-id="3cf60-147">In questo modo le aziende possono configurare i numeri di telefono con lo stesso numero di base e estensioni univoche.</span><span class="sxs-lookup"><span data-stu-id="3cf60-147">This allows companies to configure phone numbers with the same base number and unique extensions.</span></span> <span data-ttu-id="3cf60-148">Per eseguire correttamente la ricerca, l'invito deve includere il numero completo con l'interno nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="3cf60-148">For lookup to be successful, the invite must include the full number with extension as follows:</span></span>
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > <span data-ttu-id="3cf60-149">Se il numero di telefono dell'utente è gestito in locale, usare la versione locale di Skype for Business Management Shell o il Pannello di controllo per configurare il numero di telefono dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3cf60-149">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="3cf60-150">Configurazione dell'invio di chiamate direttamente alla segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="3cf60-150">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="3cf60-151">L'instradamento diretto consente di terminare la chiamata a un utente e inviarla direttamente alla segreteria telefonica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3cf60-151">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="3cf60-152">Se desideri inviare la chiamata direttamente alla segreteria telefonica, allega opaque=app:voicemail all'intestazione dell'URI di richiesta.</span><span class="sxs-lookup"><span data-stu-id="3cf60-152">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="3cf60-153">Ad esempio, "sip:user@yourdomain.com;opaque=app:voicemail".</span><span class="sxs-lookup"><span data-stu-id="3cf60-153">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="3cf60-154">In questo caso, l'utente di Teams non riceverà la notifica di chiamata, la chiamata sarà collegata direttamente alla segreteria telefonica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="3cf60-154">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="3cf60-155">Assegnare la modalità Solo Teams agli utenti per assicurarsi che le chiamate siano disponibili in Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3cf60-155">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="3cf60-156">L'instradamento diretto richiede che gli utenti siano in modalità Solo teams per fare in modo che le chiamate in arrivo siano sul client di Teams.</span><span class="sxs-lookup"><span data-stu-id="3cf60-156">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="3cf60-157">Per impostare gli utenti in modalità Solo teams, assegnare loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="3cf60-157">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="3cf60-158">Per altre informazioni, vedere Le [istruzioni per l'aggiornamento per gli amministratori IT.](upgrade-to-teams-on-prem-overview.md)</span><span class="sxs-lookup"><span data-stu-id="3cf60-158">For more information, see [Upgrade guidance for IT administrators](upgrade-to-teams-on-prem-overview.md).</span></span> <span data-ttu-id="3cf60-159">Se la tua organizzazione utilizza Skype for Business Server o Skype for Business online, consulta il seguente articolo sull'interoperabilità tra Skype e Teams: Migrazione e interoperabilità con [Skype for Business.](migration-interop-guidance-for-teams-with-skype.md)</span><span class="sxs-lookup"><span data-stu-id="3cf60-159">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="3cf60-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="3cf60-160">See also</span></span>

[<span data-ttu-id="3cf60-161">Pianificare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="3cf60-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="3cf60-162">Configurare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="3cf60-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
