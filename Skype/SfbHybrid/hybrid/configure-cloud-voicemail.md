---
title: Configurare il servizio di segreteria cloud per gli utenti locali
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Istruzioni per l'implementazione della segreteria telefonica basata su cloud per gli utenti ospitati in Skype for Business Server.
ms.openlocfilehash: 4542207beb3ccd090c1215a8832f53b3ab08ed97
ms.sourcegitcommit: 152eb7daacd0a36f42aa441633c12c7037a0969a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/27/2020
ms.locfileid: "42288714"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="daca8-103">Configurare il servizio di segreteria cloud per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="daca8-103">Configure Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="daca8-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="daca8-104">Overview</span></span> 
<span data-ttu-id="daca8-105">In questo articolo viene descritto come configurare il servizio segreteria telefonica Microsoft Cloud per gli utenti locali di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="daca8-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="daca8-106">In questo articolo si presuppone che sia già stato distribuito Skype for Business Server in una topologia supportata e che siano stati soddisfatti i prerequisiti per la configurazione della connettività ibrida.</span><span class="sxs-lookup"><span data-stu-id="daca8-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="daca8-107">Per ulteriori informazioni sui vantaggi, le considerazioni sulla pianificazione e i requisiti per l'implementazione del servizio di segreteria cloud, vedere [Plan cloud Voicemail Service](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="daca8-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="daca8-108">La configurazione del messaggio vocale cloud prevede le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="daca8-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="daca8-109">Assicurarsi di aver soddisfatto i prerequisiti come descritto in [Plan cloud Voicemail Service](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="daca8-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="daca8-110">Assicurarsi di aver configurato la connettività ibrida, come descritto in [Plan Hybrid Connectivity](plan-hybrid-connectivity.md) e [Configure Hybrid Connectivity](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="daca8-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="daca8-111">Configurare il servizio di [segreteria cloud come provider di hosting nel server perimetrale](#configure-cloud-voicemail-as-the-hosting-provider) , come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="daca8-111">[Configure Cloud Voicemail as the hosting provider on the Edge Server](#configure-cloud-voicemail-as-the-hosting-provider) as described in this article.</span></span>

4.  <span data-ttu-id="daca8-112">[Configurare un criterio di segreteria telefonica ospitata](#configure-a-hosted-voicemail-policy) come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="daca8-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="daca8-113">[Assegnare un criterio di segreteria telefonica ospitata](#assign-a-hosted-voicemail-policy) come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="daca8-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="daca8-114">[Abilitare un utente per la segreteria telefonica cloud](#enable-a-user-for-cloud-voicemail) , come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="daca8-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider"></a><span data-ttu-id="daca8-115">Configurare il messaggio di posta vocale cloud come provider di hosting</span><span class="sxs-lookup"><span data-stu-id="daca8-115">Configure Cloud Voicemail as the hosting provider</span></span> 

<span data-ttu-id="daca8-116">È possibile configurare il messaggio vocale cloud come provider di hosting in un front end server utilizzando il cmdlet New-CsHostingProvider con i seguenti parametri:</span><span class="sxs-lookup"><span data-stu-id="daca8-116">You configure Cloud Voicemail as the hosting provider on a Front End Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="daca8-117">**Identity** specifica un identificatore di valore stringa univoco per il provider di hosting che si sta creando. ad esempio, il messaggio vocale cloud.</span><span class="sxs-lookup"><span data-stu-id="daca8-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="daca8-118">**Enabled** indica se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata.</span><span class="sxs-lookup"><span data-stu-id="daca8-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="daca8-119">Questo parametro deve essere impostato su true.</span><span class="sxs-lookup"><span data-stu-id="daca8-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="daca8-120">**EnabledSharedAddressSpace** consente di indicare se il provider di hosting verrà utilizzato in uno scenario con spazio di indirizzamento SIP condiviso.</span><span class="sxs-lookup"><span data-stu-id="daca8-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="daca8-121">Questo parametro deve essere impostato su true.</span><span class="sxs-lookup"><span data-stu-id="daca8-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="daca8-122">**HostsOCSUsers** indica se il provider di hosting viene utilizzato per ospitare gli account di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="daca8-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="daca8-123">Questo parametro deve essere impostato su false.</span><span class="sxs-lookup"><span data-stu-id="daca8-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="daca8-124">**ProxyFqdn** specifica il nome di dominio completo (FQDN) del server proxy utilizzato dal provider di hosting. ad esempio, proxyserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="daca8-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="daca8-125">Per avere tali informazioni, rivolgersi al provider di hosting.</span><span class="sxs-lookup"><span data-stu-id="daca8-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="daca8-126">Questo valore non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="daca8-126">This value cannot be modified.</span></span> <span data-ttu-id="daca8-127">Se il provider di hosting modifica il server proxy, sarà necessario eliminare e quindi ricreare la voce per il provider.</span><span class="sxs-lookup"><span data-stu-id="daca8-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="daca8-128">La **lingua locale** indica se il server proxy utilizzato dal provider di hosting è contenuto nella topologia di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="daca8-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="daca8-129">Questo parametro deve essere impostato su false.</span><span class="sxs-lookup"><span data-stu-id="daca8-129">This parameter must be set to False.</span></span>

<span data-ttu-id="daca8-130">Ad esempio, in Skype for Business Management Shell, il cmdlet seguente configura il messaggio di posta vocale cloud come provider di hosting:</span><span class="sxs-lookup"><span data-stu-id="daca8-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```PowerShell
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="daca8-131">Configurare un criterio di segreteria telefonica ospitata</span><span class="sxs-lookup"><span data-stu-id="daca8-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="daca8-132">Per assicurarsi che la segreteria telefonica dell'organizzazione sia instradata al servizio cloud voicemail, è necessario configurare un criterio di segreteria telefonica ospitata per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="daca8-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="daca8-133">In molti casi, è necessario un solo criterio di segreteria telefonica ospitata ed è possibile modificare i criteri globali per soddisfare tutte le esigenze.</span><span class="sxs-lookup"><span data-stu-id="daca8-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="daca8-134">Se nell'organizzazione sono necessari più criteri di segreteria telefonica ospitata, è possibile aggiungere criteri utilizzando il cmdlet New-CsHostedVoicemailPolicy.</span><span class="sxs-lookup"><span data-stu-id="daca8-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="daca8-135">Per modificare il criterio globale, eseguire il seguente comando in Skype for Business Server Management Shell dopo aver aggiornato l'organizzazione e TenantID:</span><span class="sxs-lookup"><span data-stu-id="daca8-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```PowerShell
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com
```

- <span data-ttu-id="daca8-136">**Destinazione** specifica il nome di dominio completo (FQDN) del servizio segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="daca8-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="daca8-137">Questo valore deve essere impostato su **exap.um.Outlook.com**.</span><span class="sxs-lookup"><span data-stu-id="daca8-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="daca8-138">**Organization** è il dominio predefinito assegnato al tenant.</span><span class="sxs-lookup"><span data-stu-id="daca8-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="daca8-139">È possibile recuperare queste informazioni facendo in modo che l'amministratore del tenant acceda a office.com, fare clic sull'app dell'interfaccia di amministrazione, passare a **installazione** a sinistra e fare clic su **domini**.</span><span class="sxs-lookup"><span data-stu-id="daca8-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="daca8-140">Ad esempio: mytenant.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="daca8-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="daca8-141">Il nome dell'organizzazione è anche il nome di dominio predefinito in Office 365.</span><span class="sxs-lookup"><span data-stu-id="daca8-141">The Organization name is also the Default Domain name in Office 365.</span></span>

<span data-ttu-id="daca8-142">Per assicurarsi che un criterio di segreteria telefonica ospitata sia stato creato correttamente, eseguire il seguente comando:</span><span class="sxs-lookup"><span data-stu-id="daca8-142">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```PowerShell
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="daca8-143">Assegnare un criterio di segreteria telefonica ospitata</span><span class="sxs-lookup"><span data-stu-id="daca8-143">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="daca8-144">Per impostazione predefinita, il criterio segreteria telefonica ospitata Global è assegnato a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="daca8-144">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="daca8-145">Se si utilizza un criterio diverso, prima di abilitare gli utenti per la segreteria telefonica ospitata, è necessario innanzitutto concedere agli utenti il criterio segreteria telefonica ospitata desiderata utilizzando il cmdlet [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="daca8-145">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="daca8-146">Ad esempio, il comando seguente consente di assegnare un criterio di segreteria telefonica ospitata non globale a un utente:</span><span class="sxs-lookup"><span data-stu-id="daca8-146">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```PowerShell
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="daca8-147">Abilitare un utente per la segreteria telefonica cloud</span><span class="sxs-lookup"><span data-stu-id="daca8-147">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="daca8-148">Per consentire alle chiamate vocali di un utente di essere instradate alla segreteria telefonica cloud, è possibile utilizzare il cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) con il parametro HostedVoiceMail.</span><span class="sxs-lookup"><span data-stu-id="daca8-148">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="daca8-149">Ad esempio, il comando seguente consente di abilitare un account utente per la segreteria telefonica cloud:</span><span class="sxs-lookup"><span data-stu-id="daca8-149">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $True
```

<span data-ttu-id="daca8-150">Il cmdlet verifica che un criterio di segreteria telefonica cloud, a livello globale, sito o utente, si applichi a questo utente.</span><span class="sxs-lookup"><span data-stu-id="daca8-150">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="daca8-151">Se nessun criterio è applicabile il cmdlet non riesce.</span><span class="sxs-lookup"><span data-stu-id="daca8-151">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="daca8-152">Nell'esempio seguente viene disabilitato un account utente per la segreteria telefonica cloud:</span><span class="sxs-lookup"><span data-stu-id="daca8-152">The next example disables a user account for Cloud Voicemail:</span></span>

```powershell
Set-CsUser -Identity "User1" -HostedVoiceMail $False
```

<span data-ttu-id="daca8-153">Il cmdlet verifica che nessun criterio di segreteria telefonica ospitata, a livello globale, sito o utente, si applichi a questo utente.</span><span class="sxs-lookup"><span data-stu-id="daca8-153">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="daca8-154">Se un criterio è applicabile il cmdlet non riesce.</span><span class="sxs-lookup"><span data-stu-id="daca8-154">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="daca8-155">Gli utenti devono essere abilitati alla funzionalità VoIP aziendale per l'utilizzo del servizio segreteria telefonica di Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="daca8-155">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>
