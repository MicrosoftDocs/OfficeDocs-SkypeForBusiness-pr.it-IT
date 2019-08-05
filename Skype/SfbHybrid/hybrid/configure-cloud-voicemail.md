---
title: Configurare il servizio cloud Voicemail per gli utenti locali
ms.reviewer: ''
ms.author: dstrome
author: dstrome
manager: serdars
ms.date: 2/11/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: Istruzioni per l'implementazione della segreteria telefonica basata su cloud per gli utenti residenti in Skype for Business Server.
ms.openlocfilehash: 99fc250ff4c01a0b51e784c165edb99cbb867b3c
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36185468"
---
# <a name="configure-cloud-voicemail-service-for-on-premises-users"></a><span data-ttu-id="ba558-103">Configurare il servizio cloud Voicemail per gli utenti locali</span><span class="sxs-lookup"><span data-stu-id="ba558-103">Configure Cloud Voicemail service for on-premises users</span></span>

## <a name="overview"></a><span data-ttu-id="ba558-104">Panoramica</span><span class="sxs-lookup"><span data-stu-id="ba558-104">Overview</span></span> 
<span data-ttu-id="ba558-105">Questo articolo descrive come configurare il servizio Microsoft Cloud Voicemail per gli utenti locali di Skype for business.</span><span class="sxs-lookup"><span data-stu-id="ba558-105">This article describes how to configure Microsoft Cloud Voicemail service for your Skype for Business on-premises users.</span></span>  

<span data-ttu-id="ba558-106">Questo articolo presuppone che si disponga già di Skype for Business Server distribuito in una topologia supportata e che siano stati soddisfatti i prerequisiti per la configurazione della connettività ibrida.</span><span class="sxs-lookup"><span data-stu-id="ba558-106">This article assumes that you already have Skype for Business Server deployed in a supported topology, and that you have met the prerequisites for setting up hybrid connectivity.</span></span>

<span data-ttu-id="ba558-107">Per altre informazioni sui vantaggi, le considerazioni sulla pianificazione e i requisiti per l'implementazione della segreteria telefonica cloud, vedere [pianificare il servizio di segreteria telefonica cloud](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="ba558-107">For more information about the benefits, planning considerations, and requirements for implementing Cloud Voicemail, see [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>




<span data-ttu-id="ba558-108">La configurazione della segreteria telefonica Cloud include le attività seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba558-108">Configuring Cloud Voicemail involves the following tasks:</span></span>

1.  <span data-ttu-id="ba558-109">Verificare di avere soddisfatto i prerequisiti come descritto in [servizio cloud Voicemail](plan-cloud-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="ba558-109">Ensure that you have met the prerequisites as described in [Plan Cloud Voicemail service](plan-cloud-voicemail.md).</span></span>

2.  <span data-ttu-id="ba558-110">Verificare di aver configurato la connettività ibrida come descritto in [pianificare](plan-hybrid-connectivity.md) la connettività ibrida e [configurare la connettività ibrida](configure-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="ba558-110">Ensure that you have set up hybrid connectivity as described in [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 

3.  <span data-ttu-id="ba558-111">[Configurare la segreteria telefonica cloud come provider di hosting nell'Edge Server](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="ba558-111">[Configure Cloud Voicemail as the hosting provider on the Edge Server](#configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server) as described in this article.</span></span>

4.  <span data-ttu-id="ba558-112">[Configurare un criterio per la segreteria telefonica ospitata](#configure-a-hosted-voicemail-policy) come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="ba558-112">[Configure a hosted voicemail policy](#configure-a-hosted-voicemail-policy) as described in this article.</span></span>

5.  <span data-ttu-id="ba558-113">[Assegnare un criterio per la segreteria telefonica ospitata](#assign-a-hosted-voicemail-policy) come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="ba558-113">[Assign a hosted voicemail policy](#assign-a-hosted-voicemail-policy) as described in this article.</span></span>

6.  <span data-ttu-id="ba558-114">[Abilitare un utente per la segreteria telefonica cloud](#enable-a-user-for-cloud-voicemail) come descritto in questo articolo.</span><span class="sxs-lookup"><span data-stu-id="ba558-114">[Enable a user for Cloud Voicemail](#enable-a-user-for-cloud-voicemail) as described in this article.</span></span>


## <a name="configure-cloud-voicemail-as-the-hosting-provider-on-the-edge-server"></a><span data-ttu-id="ba558-115">Configurare la segreteria telefonica cloud come provider di hosting nell'Edge Server</span><span class="sxs-lookup"><span data-stu-id="ba558-115">Configure Cloud Voicemail as the hosting provider on the Edge Server</span></span> 

<span data-ttu-id="ba558-116">È possibile configurare la segreteria telefonica cloud come provider di hosting in un server front-end usando il cmdlet New-CsHostingProvider con i parametri seguenti:</span><span class="sxs-lookup"><span data-stu-id="ba558-116">You configure Cloud Voicemail as the hosting provider on a Front End Server by using the New-CsHostingProvider cmdlet with the following parameters:</span></span>

- <span data-ttu-id="ba558-117">**Identity** specifica un identificatore di valore stringa univoco per il provider di hosting da creare. ad esempio, cloud Voicemail.</span><span class="sxs-lookup"><span data-stu-id="ba558-117">**Identity** specifies a unique string value identifier for the hosting provider that you are creating; for example, Cloud Voicemail.</span></span> 

- <span data-ttu-id="ba558-118">\*\*Enabled \*\* indica se la connessione di rete tra il dominio dell'organizzazione e il provider di hosting è abilitata.</span><span class="sxs-lookup"><span data-stu-id="ba558-118">**Enabled** indicates whether the network connection between your domain and the hosting provider is enabled.</span></span> <span data-ttu-id="ba558-119">Questo parametro deve essere impostato su true.</span><span class="sxs-lookup"><span data-stu-id="ba558-119">This parameter must be set to True.</span></span>

- <span data-ttu-id="ba558-120">**EnabledSharedAddressSpace** indica se il provider di hosting verrà usato in uno scenario di spazio di indirizzi SIP condiviso.</span><span class="sxs-lookup"><span data-stu-id="ba558-120">**EnabledSharedAddressSpace** indicates whether the hosting provider will be used in a shared SIP address space scenario.</span></span> <span data-ttu-id="ba558-121">Questo parametro deve essere impostato su true.</span><span class="sxs-lookup"><span data-stu-id="ba558-121">This parameter must be set to True.</span></span>

- <span data-ttu-id="ba558-122">**HostsOCSUsers** indica se il provider di hosting viene usato per ospitare gli account di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ba558-122">**HostsOCSUsers** indicates whether the hosting provider is used to host Skype for Business Server accounts.</span></span> <span data-ttu-id="ba558-123">Questo parametro deve essere impostato su false.</span><span class="sxs-lookup"><span data-stu-id="ba558-123">This parameter must be set to False.</span></span>

- <span data-ttu-id="ba558-124">**ProxyFqdn** specifica il nome di dominio completo (FQDN) per il server proxy usato dal provider di hosting. ad esempio, proxyserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="ba558-124">**ProxyFQDN** specifies the fully qualified domain name (FQDN) for the proxy server used by the hosting provider; for example, proxyserver.contoso.com.</span></span> <span data-ttu-id="ba558-125">Contattare il provider di hosting per queste informazioni.</span><span class="sxs-lookup"><span data-stu-id="ba558-125">Contact your hosting provider for this information.</span></span> <span data-ttu-id="ba558-126">Questo valore non può essere modificato.</span><span class="sxs-lookup"><span data-stu-id="ba558-126">This value cannot be modified.</span></span> <span data-ttu-id="ba558-127">Se il provider di hosting modifica il proprio server proxy, sarà necessario eliminarlo e ricrearlo.</span><span class="sxs-lookup"><span data-stu-id="ba558-127">If the hosting provider changes its proxy server, you will need to delete and then re-create the entry for that provider.</span></span>

- <span data-ttu-id="ba558-128">La **lingua locale** indica se il server proxy usato dal provider di hosting è contenuto nella topologia di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ba558-128">**IsLocal** indicates whether the proxy server used by the hosting provider is contained within your Skype for Business Server topology.</span></span> <span data-ttu-id="ba558-129">Questo parametro deve essere impostato su false.</span><span class="sxs-lookup"><span data-stu-id="ba558-129">This parameter must be set to False.</span></span>

<span data-ttu-id="ba558-130">Ad esempio, in Skype for Business Management Shell, il cmdlet seguente configura il cloud Voicemail come provider di hosting:</span><span class="sxs-lookup"><span data-stu-id="ba558-130">For example, in the Skype for Business Management shell, the following cmdlet configures Cloud Voicemail as the hosting provider:</span></span>


```
New-CsHostingProvider -Identity "Exchange Online" -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $False -ProxyFqdn "exap.um.outlook.com" -IsLocal $False -VerificationLevel UseSourceVerification
```

## <a name="configure-a-hosted-voicemail-policy"></a><span data-ttu-id="ba558-131">Configurare un criterio per la segreteria telefonica ospitata</span><span class="sxs-lookup"><span data-stu-id="ba558-131">Configure a hosted voicemail policy</span></span>

<span data-ttu-id="ba558-132">Per assicurarsi che la segreteria telefonica per l'organizzazione venga instradata al servizio cloud voicemail, è necessario configurare un criterio per la segreteria telefonica ospitata per l'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="ba558-132">To ensure that voicemail for your organization is routed to the Cloud Voicemail service, you must configure a hosted voicemail policy for your organization.</span></span> <span data-ttu-id="ba558-133">In molti casi è necessario un solo criterio per la segreteria telefonica ospitata ed è possibile modificare il criterio globale in base a tutte le esigenze.</span><span class="sxs-lookup"><span data-stu-id="ba558-133">In many cases, only one hosted voicemail policy is required, and you can modify the global policy to meet all your needs.</span></span> <span data-ttu-id="ba558-134">Se l'organizzazione richiede più criteri per la segreteria telefonica ospitata, è possibile aggiungere criteri usando il cmdlet New-CsHostedVoicemailPolicy.</span><span class="sxs-lookup"><span data-stu-id="ba558-134">If your organization requires multiple hosted voicemail policies, you can add policies by using the new-cshostedvoicemailpolicy cmdlet.</span></span>

<span data-ttu-id="ba558-135">Per modificare il criterio globale, eseguire il comando seguente in Skype for Business Server Management Shell dopo l'aggiornamento dell'organizzazione e ID tenant:</span><span class="sxs-lookup"><span data-stu-id="ba558-135">To modify the global policy, run the following command in the Skype for Business Server management shell after updating your Organization and TenantID:</span></span>

```
Set-CsHostedVoicemailPolicy -Identity Global -Description "Global Cloud Voicemail Policy" -Destination exap.um.outlook.com -Organization YourDefaultDomain.onmicrosoft.com -TenantID “11111111-1111-1111-1111-111111111111”
```

- <span data-ttu-id="ba558-136">**Destinazione** specifica il nome di dominio completo (FQDN) del servizio di segreteria telefonica ospitata.</span><span class="sxs-lookup"><span data-stu-id="ba558-136">**Destination** specifies the fully qualified domain name (FQDN) of the hosted Cloud Voicemail service.</span></span> <span data-ttu-id="ba558-137">Questo valore deve essere impostato su **exap.um.Outlook.com**.</span><span class="sxs-lookup"><span data-stu-id="ba558-137">This value should be set to **exap.um.outlook.com**.</span></span>

- <span data-ttu-id="ba558-138">**Organizzazione** è il dominio predefinito assegnato al tenant.</span><span class="sxs-lookup"><span data-stu-id="ba558-138">**Organization** is the default domain assigned to your tenant.</span></span> <span data-ttu-id="ba558-139">Per recuperare queste informazioni, è possibile che l'amministratore del tenant acceda a office.com, fare clic sull'app dell'interfaccia di amministrazione, passare a **configurazione** a sinistra e fare clic su **domini**.</span><span class="sxs-lookup"><span data-stu-id="ba558-139">You can retrieve this information by having the tenant admin log in to office.com, click on the Admin Center app, navigate to **Setup** on the left, and click **Domains**.</span></span> <span data-ttu-id="ba558-140">Ad esempio: mytenant.onmicrosoft.com.</span><span class="sxs-lookup"><span data-stu-id="ba558-140">For example: mytenant.onmicrosoft.com.</span></span>

    <span data-ttu-id="ba558-141">Il nome dell'organizzazione è anche il nome di dominio predefinito in Office 365.</span><span class="sxs-lookup"><span data-stu-id="ba558-141">The Organization name is also the Default Domain name in Office 365.</span></span>

- <span data-ttu-id="ba558-142">**ID tenant** viene usato per identificare il tenant in Office 365.</span><span class="sxs-lookup"><span data-stu-id="ba558-142">**TenantID** is used to identify your tenant in Office 365.</span></span> <span data-ttu-id="ba558-143">Per altre informazioni, vedere [trovare l'ID tenant di Office 365](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span><span class="sxs-lookup"><span data-stu-id="ba558-143">For more information, see [Find your Office 365 tenant ID](https://support.office.com/en-us/article/find-your-office-365-tenant-id-6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>

<span data-ttu-id="ba558-144">Per assicurarsi che sia stato creato correttamente un criterio di segreteria telefonica ospitata, eseguire il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="ba558-144">To ensure that a hosted voicemail policy was created successfully, run the following command:</span></span>

```
Get-CsHostedVoicemailPolicy
```

## <a name="assign-a-hosted-voicemail-policy"></a><span data-ttu-id="ba558-145">Assegnare un criterio per la segreteria telefonica ospitata</span><span class="sxs-lookup"><span data-stu-id="ba558-145">Assign a hosted voicemail policy</span></span>

<span data-ttu-id="ba558-146">Per impostazione predefinita, il criterio della segreteria telefonica ospitata globale viene assegnato a tutti gli utenti.</span><span class="sxs-lookup"><span data-stu-id="ba558-146">By default, the Global hosted voicemail policy is assigned to all users.</span></span> <span data-ttu-id="ba558-147">Se usi un criterio diverso, prima di abilitare gli utenti per la segreteria telefonica ospitata, devi prima concedere agli utenti i criteri desiderati per la segreteria telefonica ospitata usando il cmdlet [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) .</span><span class="sxs-lookup"><span data-stu-id="ba558-147">If you use a different policy, before enabling users for hosted voicemail, you must first grant users the desired hosted voicemail policy by using the [Grant-CSHostedVoicemailPolicy](https://docs.microsoft.com/powershell/module/skype/grant-cshostedvoicemailpolicy?view=skype-ps) cmdlet.</span></span>

<span data-ttu-id="ba558-148">Ad esempio, con il comando seguente viene assegnato un criterio di segreteria telefonica ospitata non globale a un utente:</span><span class="sxs-lookup"><span data-stu-id="ba558-148">For example, the following command assigns a non-Global hosted voicemail policy to a user:</span></span>


```
Get-CsUser -Identity "User1" | Grant-CsHostedVoicemailPolicy -Identity "Tag:CloudVoiceMailUsers" 
```

## <a name="enable-a-user-for-cloud-voicemail"></a><span data-ttu-id="ba558-149">Abilitare un utente per la segreteria telefonica cloud</span><span class="sxs-lookup"><span data-stu-id="ba558-149">Enable a user for Cloud Voicemail</span></span>

<span data-ttu-id="ba558-150">Per consentire alle chiamate vocali dell'utente di essere instradate alla segreteria telefonica cloud, puoi usare il cmdlet [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) con il parametro HostedVoiceMail.</span><span class="sxs-lookup"><span data-stu-id="ba558-150">To enable a user’s voicemail calls to be routed to Cloud Voicemail, you use the [Set-CsUser](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) cmdlet with the HostedVoiceMail parameter.</span></span> 

<span data-ttu-id="ba558-151">Ad esempio, il comando seguente abilita un account utente per la segreteria telefonica cloud:</span><span class="sxs-lookup"><span data-stu-id="ba558-151">For example, the following command enables a user account for Cloud Voicemail:</span></span> 

```Set-CsUser -Identity "User1" -HostedVoiceMail $True```

<span data-ttu-id="ba558-152">Il cmdlet verifica che un criterio per la segreteria telefonica cloud, a livello globale, del sito o dell'utente, si applichi a questo utente.</span><span class="sxs-lookup"><span data-stu-id="ba558-152">The cmdlet verifies that a Cloud Voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="ba558-153">Se non viene applicato alcun criterio, il cmdlet non riesce.</span><span class="sxs-lookup"><span data-stu-id="ba558-153">If no policy applies, the cmdlet fails.</span></span>  

<span data-ttu-id="ba558-154">Nell'esempio seguente viene disabilitato un account utente per la segreteria telefonica cloud:</span><span class="sxs-lookup"><span data-stu-id="ba558-154">The next example disables a user account for Cloud Voicemail:</span></span>

```Set-CsUser -Identity "User1" -HostedVoiceMail $False```

<span data-ttu-id="ba558-155">Il cmdlet verifica che nessun criterio per la segreteria telefonica ospitata, a livello globale, del sito o dell'utente, si applichi a questo utente.</span><span class="sxs-lookup"><span data-stu-id="ba558-155">The cmdlet verifies that no hosted voicemail policy--at the global, site, or user level--applies to this user.</span></span> <span data-ttu-id="ba558-156">Se un criterio si applica, il cmdlet non riesce.</span><span class="sxs-lookup"><span data-stu-id="ba558-156">If a policy does apply, the cmdlet fails.</span></span>

> [!NOTE]
>  <span data-ttu-id="ba558-157">Gli utenti devono essere abilitati a Enterprise-Voice per usare il servizio Microsoft Cloud Voicemail.</span><span class="sxs-lookup"><span data-stu-id="ba558-157">Users must be enterprise-voice enabled to use the Microsoft Cloud Voicemail Service.</span></span>
