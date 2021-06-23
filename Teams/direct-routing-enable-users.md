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
description: Informazioni su come abilitare gli utenti Telefono Microsoft Routing diretto di sistema.
ms.openlocfilehash: 7d2b7c4b5d6268d1498a47537e0edbbf892198aa
ms.sourcegitcommit: cae94cd5761baafde51aea1137e6d164722eead9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/23/2021
ms.locfileid: "53075369"
---
# <a name="enable-users-for-direct-routing-voice-and-voicemail"></a><span data-ttu-id="60a4a-103">Abilitare gli utenti per routing diretto, segreteria telefonica e segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="60a4a-103">Enable users for Direct Routing, voice, and voicemail</span></span>

<span data-ttu-id="60a4a-104">Questo articolo descrive come abilitare gli utenti per Sistema telefonico routing diretto.</span><span class="sxs-lookup"><span data-stu-id="60a4a-104">This article describes how to enable users for Phone System Direct Routing.</span></span>  <span data-ttu-id="60a4a-105">Questo è il passaggio 2 della procedura seguente per la configurazione del routing diretto:</span><span class="sxs-lookup"><span data-stu-id="60a4a-105">This is step 2 of the following steps for configuring Direct Routing:</span></span>

- <span data-ttu-id="60a4a-106">Passaggio 1.</span><span class="sxs-lookup"><span data-stu-id="60a4a-106">Step 1.</span></span> [<span data-ttu-id="60a4a-107">Connessione SBC con Telefono Microsoft sistema e convalidare la connessione</span><span class="sxs-lookup"><span data-stu-id="60a4a-107">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md) 
- <span data-ttu-id="60a4a-108">**Passaggio 2. Abilitare gli utenti per routing diretto, segreteria telefonica**   e segreteria telefonica (questo articolo)</span><span class="sxs-lookup"><span data-stu-id="60a4a-108">**Step 2. Enable users for Direct Routing, voice, and voicemail**   (this article)</span></span>
- <span data-ttu-id="60a4a-109">Passaggio 3.</span><span class="sxs-lookup"><span data-stu-id="60a4a-109">Step 3.</span></span> [<span data-ttu-id="60a4a-110">Configurare il routing vocale</span><span class="sxs-lookup"><span data-stu-id="60a4a-110">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="60a4a-111">Passaggio 4.</span><span class="sxs-lookup"><span data-stu-id="60a4a-111">Step 4.</span></span> [<span data-ttu-id="60a4a-112">Tradurre i numeri in un formato alternativo</span><span class="sxs-lookup"><span data-stu-id="60a4a-112">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 


<span data-ttu-id="60a4a-113">Per informazioni su tutti i passaggi necessari per configurare il routing diretto, vedere [Configurare il routing diretto.](direct-routing-configure.md)</span><span class="sxs-lookup"><span data-stu-id="60a4a-113">For information on all the steps required for setting up Direct Routing, see [Configure Direct Routing](direct-routing-configure.md).</span></span>

<span data-ttu-id="60a4a-114">Quando si è pronti per abilitare gli utenti per il routing diretto, seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="60a4a-114">When you are ready to enable users for Direct Routing, follow these steps:</span></span> 

1. <span data-ttu-id="60a4a-115">Creare un utente in Microsoft 365 o Office 365 e assegnare una Sistema telefonico licenza.</span><span class="sxs-lookup"><span data-stu-id="60a4a-115">Create a user in Microsoft 365 or Office 365 and assign a Phone System license.</span></span> 
2. <span data-ttu-id="60a4a-116">Verificare che l'utente sia disponibile in Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="60a4a-116">Ensure that the user is homed in Skype for Business Online.</span></span> 
3. <span data-ttu-id="60a4a-117">Configurare il numero di telefono e abilitare la segreteria telefonica e la segreteria telefonica aziendale.</span><span class="sxs-lookup"><span data-stu-id="60a4a-117">Configure the phone number and enable enterprise voice and voicemail.</span></span> 
4. <span data-ttu-id="60a4a-118">Assegnare Teams solo agli utenti.</span><span class="sxs-lookup"><span data-stu-id="60a4a-118">Assign Teams Only mode to users.</span></span>

## <a name="create-a-user-and-assign-the-license"></a><span data-ttu-id="60a4a-119">Creare un utente e assegnare la licenza</span><span class="sxs-lookup"><span data-stu-id="60a4a-119">Create a user and assign the license</span></span> 

<span data-ttu-id="60a4a-120">Sono disponibili due opzioni per creare un nuovo utente in Microsoft 365 o Office 365.</span><span class="sxs-lookup"><span data-stu-id="60a4a-120">There are two options for creating a new user in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="60a4a-121">Tuttavia, Microsoft consiglia all'organizzazione di scegliere un'opzione per evitare problemi di routing:</span><span class="sxs-lookup"><span data-stu-id="60a4a-121">However, Microsoft recommends that your organization choose one option to avoid routing issues:</span></span> 

- <span data-ttu-id="60a4a-122">Creare l'utente in Active Directory locale e sincronizzare l'utente con il cloud.</span><span class="sxs-lookup"><span data-stu-id="60a4a-122">Create the user in on-premises Active Directory and sync the user to the cloud.</span></span> <span data-ttu-id="60a4a-123">Vedere [Integrare le directory locali](/azure/active-directory/connect/active-directory-aadconnect)con Azure Active Directory .</span><span class="sxs-lookup"><span data-stu-id="60a4a-123">See [Integrate your on-premises directories with Azure Active Directory](/azure/active-directory/connect/active-directory-aadconnect).</span></span>
- <span data-ttu-id="60a4a-124">Creare l'utente direttamente nel interfaccia di amministrazione di Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="60a4a-124">Create the user directly in the Microsoft 365 admin center.</span></span> <span data-ttu-id="60a4a-125">Vedere Aggiungere utenti singolarmente o in blocco a Microsoft 365 [o Office 365 - Guida per gli amministratori.](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec)</span><span class="sxs-lookup"><span data-stu-id="60a4a-125">See [Add users individually or in bulk to Microsoft 365 or Office 365 - Admin Help](https://support.office.com/article/Add-users-individually-or-in-bulk-to-Office-365-Admin-Help-1970f7d6-03b5-442f-b385-5880b9c256ec).</span></span> 

<span data-ttu-id="60a4a-126">Se la distribuzione di Skype for Business Online coesiste con Skype for Business 2015 o Lync 2010 o 2013 locale, l'unica opzione supportata è creare l'utente in Active Directory locale e sincronizzare l'utente con il cloud (opzione 1).</span><span class="sxs-lookup"><span data-stu-id="60a4a-126">If your Skype for Business Online deployment coexists with Skype for Business 2015 or Lync 2010 or 2013 on-premises, the only supported option is to create the user in the on-premises Active Directory and sync the user to the cloud (Option 1).</span></span> 

<span data-ttu-id="60a4a-127">Per informazioni sui requisiti di licenza, vedere [licenze e altri requisiti](direct-routing-plan.md#licensing-and-other-requirements) in Pianificare il routing [diretto.](direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="60a4a-127">For information about license requirements, see [licensing and other requirements](direct-routing-plan.md#licensing-and-other-requirements) in [Plan Direct Routing](direct-routing-plan.md).</span></span>

## <a name="ensure-that-the-user-is-homed-online-and-phone-number-is-not-being-synced-from-on-premises-applicable-for-skype-for-business-server-enterprise-voice-enabled-users-being-migrated-to-teams-direct-routing"></a><span data-ttu-id="60a4a-128">Verificare che l'utente sia ospitata online e che il numero di telefono non venga sincronizzato da locale (applicabile per gli utenti abilitati per Skype for Business Server VoIP aziendale di cui viene eseguita la migrazione a Teams Direct Routing)</span><span class="sxs-lookup"><span data-stu-id="60a4a-128">Ensure that the user is homed online and phone number is not being synced from on-premises (applicable for Skype for Business Server Enterprise Voice enabled users being migrated to Teams Direct Routing)</span></span>

<span data-ttu-id="60a4a-129">Il routing diretto richiede che l'utente sia ospitato online.</span><span class="sxs-lookup"><span data-stu-id="60a4a-129">Direct Routing requires the user to be homed online.</span></span> <span data-ttu-id="60a4a-130">È possibile verificare esaminando il parametro RegistrarPool, che deve avere un valore nel infra.lync.com dominio.</span><span class="sxs-lookup"><span data-stu-id="60a4a-130">You can check by looking at the RegistrarPool parameter, which needs to have a value in the infra.lync.com domain.</span></span> <span data-ttu-id="60a4a-131">Anche il parametro OnPremLineUriManuallySet deve essere impostato su True.</span><span class="sxs-lookup"><span data-stu-id="60a4a-131">OnPremLineUriManuallySet parameter should also to be set to True.</span></span> <span data-ttu-id="60a4a-132">A questo scopo, è possibile configurare il numero di telefono e abilitare la segreteria telefonica e la segreteria telefonica aziendale Skype for Business PowerShell online.</span><span class="sxs-lookup"><span data-stu-id="60a4a-132">This is achieved by configuring the phone number and enable enterprise voice and voicemail using Skype for Business Online PowerShell.</span></span>

1. <span data-ttu-id="60a4a-133">Connessione una Skype for Business di PowerShell online.</span><span class="sxs-lookup"><span data-stu-id="60a4a-133">Connect a Skype for Business Online PowerShell session.</span></span>

2. <span data-ttu-id="60a4a-134">Eseguire il comando:</span><span class="sxs-lookup"><span data-stu-id="60a4a-134">Issue the command:</span></span> 

    ```PowerShell
    Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri
    ``` 
    <span data-ttu-id="60a4a-135">Se OnPremLineUriManuallySet è impostato su False e LineUri viene popolato con un numero di telefono <E.164>, pulire i parametri usando Skype for Business Management Shell locale, prima di configurare il numero di telefono con Skype for Business Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="60a4a-135">In case OnPremLineUriManuallySet is set to False and LineUri is populated with a <E.164 phone number>, please clean the parameters using on-premises Skype for Business Management Shell, before configuring the phone number using Skype for Business Online PowerShell.</span></span> 

1. <span data-ttu-id="60a4a-136">Da Skype for Business Management Shell eseguire il comando:</span><span class="sxs-lookup"><span data-stu-id="60a4a-136">From Skype for Business Management Shell issue the command:</span></span> 

   ```PowerShell
   Set-CsUser -Identity "<User name>" -LineUri $null -EnterpriseVoiceEnabled $False -HostedVoiceMail $False
    ``` 
   <span data-ttu-id="60a4a-137">Dopo la sincronizzazione delle modifiche con Office 365 l'output previsto di `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` sarebbe:</span><span class="sxs-lookup"><span data-stu-id="60a4a-137">After the changes have synced to Office 365 the expected output of `Get-CsOnlineUser -Identity "<User name>" | fl RegistrarPool,OnPremLineUriManuallySet,OnPremLineUri,LineUri` would be:</span></span>

   ```console
   RegistrarPool                        : pool.infra.lync.com
   OnPremLineURIManuallySet             : True
   OnPremLineURI                        : 
   LineURI                              : 
   ```

## <a name="configure-the-phone-number-and-enable-enterprise-voice-and-voicemail"></a><span data-ttu-id="60a4a-138">Configurare il numero di telefono e abilitare la segreteria telefonica e la segreteria telefonica aziendale</span><span class="sxs-lookup"><span data-stu-id="60a4a-138">Configure the phone number and enable enterprise voice and voicemail</span></span> 

<span data-ttu-id="60a4a-139">Dopo aver creato l'utente e aver assegnato una licenza, il passaggio successivo consiste nel configurare il numero di telefono e la segreteria telefonica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="60a4a-139">After you have created the user and assigned a license, the next step is to configure the user's phone number and voicemail.</span></span> 

<span data-ttu-id="60a4a-140">Per aggiungere il numero di telefono e abilitare la segreteria telefonica:</span><span class="sxs-lookup"><span data-stu-id="60a4a-140">To add the phone number and enable for voicemail:</span></span>
 
1. <span data-ttu-id="60a4a-141">Connessione una Skype for Business di PowerShell online.</span><span class="sxs-lookup"><span data-stu-id="60a4a-141">Connect a Skype for Business Online PowerShell session.</span></span> 

2. <span data-ttu-id="60a4a-142">Eseguire il comando:</span><span class="sxs-lookup"><span data-stu-id="60a4a-142">Issue the command:</span></span> 
 
    ```PowerShell
    Set-CsUser -Identity "<User name>" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true -OnPremLineURI tel:<phone number>
    ```
    
    <span data-ttu-id="60a4a-143">Ad esempio, per aggiungere un numero di telefono per l'utente "Spencer Low", immettere quanto segue:</span><span class="sxs-lookup"><span data-stu-id="60a4a-143">For example, to add a phone number for user "Spencer Low," enter the following:</span></span> 

    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI tel:+14255388797 -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```
    <span data-ttu-id="60a4a-144">Se gli utenti "Spencer Low" e "Stacy Quinn" condividono lo stesso numero di base con estensioni univoche, immettere quanto segue</span><span class="sxs-lookup"><span data-stu-id="60a4a-144">If the users "Spencer Low" and "Stacy Quinn" share the same base number with unique extensions, enter the following</span></span>
    
    ```PowerShell
    Set-CsUser -Identity "spencer.low@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1001" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    Set-CsUser -Identity "stacy.quinn@contoso.com" -OnPremLineURI "tel:+14255388701;ext=1002" -EnterpriseVoiceEnabled $true -HostedVoiceMail $true
    ```

    <span data-ttu-id="60a4a-145">È consigliabile, ma non obbligatorio, che il numero di telefono usato sia configurato come numero di telefono E.164 completo con codice paese.</span><span class="sxs-lookup"><span data-stu-id="60a4a-145">It's recommended, but not required, that the phone number used is configured as a full E.164 phone number with country code.</span></span> <span data-ttu-id="60a4a-146">È supportato per configurare i numeri di telefono con estensioni che verranno usate per cercare gli utenti quando la ricerca rispetto al numero di base restituisce più di un risultato.</span><span class="sxs-lookup"><span data-stu-id="60a4a-146">It is supported to configure phone numbers with extensions which will be used to lookup users when the lookup against the base number returns more than one result.</span></span> <span data-ttu-id="60a4a-147">In questo modo le aziende possono configurare i numeri di telefono con lo stesso numero di base ed estensioni univoche.</span><span class="sxs-lookup"><span data-stu-id="60a4a-147">This allows companies to configure phone numbers with the same base number and unique extensions.</span></span> <span data-ttu-id="60a4a-148">Per eseguire correttamente la ricerca, l'invito deve includere il numero completo con l'interno nel modo seguente:</span><span class="sxs-lookup"><span data-stu-id="60a4a-148">For lookup to be successful, the invite must include the full number with extension as follows:</span></span>
    ```PowerShell
    To: <sip:+14255388701;ext=1001@sbc1.adatum.biz
    ```
    
    > [!NOTE]
    > <span data-ttu-id="60a4a-149">Se il numero di telefono dell'utente è gestito in locale, usare in locale Skype for Business Management Shell o il Pannello di controllo per configurare il numero di telefono dell'utente.</span><span class="sxs-lookup"><span data-stu-id="60a4a-149">If the user’s phone number is managed on premises, use on-premises Skype for Business Management Shell or Control Panel to configure the user's phone number.</span></span> 


## <a name="configuring-sending-calls-directly-to-voicemail"></a><span data-ttu-id="60a4a-150">Configurazione dell'invio di chiamate direttamente alla segreteria telefonica</span><span class="sxs-lookup"><span data-stu-id="60a4a-150">Configuring sending calls directly to voicemail</span></span>

<span data-ttu-id="60a4a-151">Instradamento diretto consente di terminare la chiamata a un utente e inviarla direttamente alla segreteria telefonica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="60a4a-151">Direct Routing allows you to end the call to a user and send it directly to the user's voicemail.</span></span> <span data-ttu-id="60a4a-152">Se si vuole inviare la chiamata direttamente alla segreteria telefonica, allegare opaque=app:voicemail all'intestazione Request URI.</span><span class="sxs-lookup"><span data-stu-id="60a4a-152">If you want to send the call directly to voicemail, attach opaque=app:voicemail to the Request URI header.</span></span> <span data-ttu-id="60a4a-153">Ad esempio, "sip:user@yourdomain.com;opaque=app:voicemail".</span><span class="sxs-lookup"><span data-stu-id="60a4a-153">For example, "sip:user@yourdomain.com;opaque=app:voicemail".</span></span> <span data-ttu-id="60a4a-154">In questo caso, l Teams'utente non riceverà la notifica di chiamata, la chiamata verrà connessa direttamente alla segreteria telefonica dell'utente.</span><span class="sxs-lookup"><span data-stu-id="60a4a-154">In this case, the Teams user will not receive the calling notification, the call will be connected to the voicemail of the user directly.</span></span>

## <a name="assign-teams-only-mode-to-users-to-ensure-calls-land-in-microsoft-teams"></a><span data-ttu-id="60a4a-155">Assegnare Teams solo agli utenti per garantire che le chiamate siano Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="60a4a-155">Assign Teams Only mode to users to ensure calls land in Microsoft Teams</span></span>

<span data-ttu-id="60a4a-156">Instradamento diretto richiede che gli utenti siano in Teams solo per garantire che le chiamate in arrivo atterrano nel client Teams messaggi.</span><span class="sxs-lookup"><span data-stu-id="60a4a-156">Direct Routing requires that users be in Teams Only mode to ensure incoming calls land in the Teams client.</span></span> <span data-ttu-id="60a4a-157">Per mettere gli utenti in Teams solo utenti, assegnare loro l'istanza "UpgradeToTeams" di TeamsUpgradePolicy.</span><span class="sxs-lookup"><span data-stu-id="60a4a-157">To put users in Teams Only mode, assign them the "UpgradeToTeams" instance of TeamsUpgradePolicy.</span></span> <span data-ttu-id="60a4a-158">Per altre informazioni, vedere [Strategie di aggiornamento per gli amministratori IT.](upgrade-to-teams-on-prem-implement.md)</span><span class="sxs-lookup"><span data-stu-id="60a4a-158">For more information, see [Upgrade strategies for IT administrators](upgrade-to-teams-on-prem-implement.md).</span></span> <span data-ttu-id="60a4a-159">Se l'organizzazione usa Skype for Business Server o Skype for Business Online, vedere l'articolo seguente per informazioni sull'interoperabilità tra Skype e Teams: Migrazione e interoperabilità con [Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span><span class="sxs-lookup"><span data-stu-id="60a4a-159">If your organization uses Skype for Business Server or Skype for Business Online, see the following article for information about interoperability between Skype and Teams: [Migration and interoperability with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="60a4a-160">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="60a4a-160">See also</span></span>

[<span data-ttu-id="60a4a-161">Pianificare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="60a4a-161">Plan Direct Routing</span></span>](direct-routing-plan.md)

[<span data-ttu-id="60a4a-162">Configurare Instradamento diretto</span><span class="sxs-lookup"><span data-stu-id="60a4a-162">Configure Direct Routing</span></span>](direct-routing-configure.md)
