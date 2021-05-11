---
title: Configurare Skype for Business ibrido
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: "Riepilogo: informazioni su come configurare l'interoperabilità tra la distribuzione locale e Teams."
ms.openlocfilehash: 2c6fda43b939a616071009be2b8d28e636036101
ms.sourcegitcommit: 17ad87556fb8e0de3c498e53f98f951ae3fa526b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/10/2021
ms.locfileid: "52305970"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="060c3-103">Configurare Skype for Business ibrido</span><span class="sxs-lookup"><span data-stu-id="060c3-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="060c3-104">Per configurare Skype for Business ibrido, è necessario:</span><span class="sxs-lookup"><span data-stu-id="060c3-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="060c3-105">[Configurare il servizio Edge locale per la federazione con Teams](#configure-your-on-premises-edge-service-to-federate-with-teams).</span><span class="sxs-lookup"><span data-stu-id="060c3-105">[Configure your on-premises Edge service to federate with Teams](#configure-your-on-premises-edge-service-to-federate-with-teams).</span></span>
- <span data-ttu-id="060c3-106">[Configurare l'ambiente locale in modo che ritieni attendibile Teams e abilitare lo spazio di indirizzi SIP condiviso.](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams)</span><span class="sxs-lookup"><span data-stu-id="060c3-106">[Configure your on-premises environment to trust Teams and enable shared SIP address space](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams).</span></span>
- <span data-ttu-id="060c3-107">[Abilitare lo spazio di indirizzi SIP condiviso nell'Teams organizzazione](#enable-shared-sip-address-space-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="060c3-107">[Enable shared SIP address space in your Teams organization](#enable-shared-sip-address-space-in-your-organization).</span></span>

<span data-ttu-id="060c3-108">Se si dispone Exchange locale, è possibile configurare OAuth tra gli ambienti Exchange locali e Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="060c3-108">If you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="060c3-109">Per ulteriori informazioni, vedere [Manage server-to-server authentication in Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) e Plan to integrate Skype for Business and [Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span><span class="sxs-lookup"><span data-stu-id="060c3-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](../../SfbServer/manage/authentication/server-to-server-and-partner-applications.md) and [Plan to integrate Skype for Business and Exchange](../../SfbServer/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-teams"></a><span data-ttu-id="060c3-110">Configurare il servizio Edge locale per la federazione con Teams</span><span class="sxs-lookup"><span data-stu-id="060c3-110">Configure your on-premises Edge service to federate with Teams</span></span>

<span data-ttu-id="060c3-111">La federazione consente agli utenti della distribuzione locale di comunicare con Teams e Skype for Business utenti online nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="060c3-111">Federation allows users in your on-premises deployment to communicate with Teams and Skype for Business Online  users in your organization.</span></span> <span data-ttu-id="060c3-112">Per configurare la federazione, eseguire il cmdlet seguente in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="060c3-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="060c3-113">Se il valore '-EnablePartnerDiscovery' è impostato su $True, Skype for Business Server utilizzerà i record DNS per cercare di individuare i domini partner non elencati nell'elenco AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="060c3-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="060c3-114">Se il valore è impostato su $False , Skype for Business Server solo i domini trovati nell'elenco AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="060c3-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="060c3-115">Questo parametro è obbligatorio se si utilizza il routing del servizio DNS.</span><span class="sxs-lookup"><span data-stu-id="060c3-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="060c3-116">Per ulteriori informazioni sull'abilitazione della federazione tra gli utenti della distribuzione di Skype for Business locale e gli utenti di un'organizzazione di Microsoft 365, vedere [Configuring federation support for a Microsoft 365 customer in Skype for Business Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).</span><span class="sxs-lookup"><span data-stu-id="060c3-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Microsoft 365 organization, see [Configuring federation support for a Microsoft 365 customer in Skype for Business Server](../../SfbServer/manage/federation-and-external-access/federation-support/configuring-federation-support.md).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-teams"></a><span data-ttu-id="060c3-117">Configurare l'ambiente locale per abilitare lo spazio di indirizzi SIP condiviso con Teams</span><span class="sxs-lookup"><span data-stu-id="060c3-117">Configure your on-premises environment to enable shared SIP address space with Teams</span></span>

<span data-ttu-id="060c3-118">È inoltre necessario configurare l'ambiente locale in modo che ritieni attendibile Teams e abilitare lo spazio di indirizzi SIP condiviso.</span><span class="sxs-lookup"><span data-stu-id="060c3-118">You must also configure your on-premises environment to trust Teams and enable shared SIP address space.</span></span> <span data-ttu-id="060c3-119">Questa configurazione significa Teams possono ospitare account utente per lo stesso set di domini SIP dell'ambiente locale e i messaggi possono essere instradati tra gli utenti ospitati in locale e online.</span><span class="sxs-lookup"><span data-stu-id="060c3-119">This configuration means Teams can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span> <span data-ttu-id="060c3-120">Configurare un provider di hosting con ProxyFqdn=sipfed.online.lync.com come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="060c3-120">You configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="060c3-121">Verificare innanzitutto se si dispone già di un provider di hosting con ProxyFqdn=sipfed.online.lync.com.</span><span class="sxs-lookup"><span data-stu-id="060c3-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="060c3-122">Se ne esiste uno, rimuoverlo utilizzando il comando seguente in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="060c3-122">If one exists, then remove it by using the following command in the Skype for Business Server Management Shell:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="060c3-123">Creare quindi un nuovo provider di hosting utilizzando il cmdlet New-CsHostingProvider seguente:</span><span class="sxs-lookup"><span data-stu-id="060c3-123">Then create a new hosting provider by using the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a><span data-ttu-id="060c3-124">Abilitare lo spazio di indirizzi SIP condiviso nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="060c3-124">Enable shared SIP address space in your organization</span></span>
  
<span data-ttu-id="060c3-125">Oltre alla modifica apportata nella distribuzione locale, è necessario apportare la modifica corrispondente nell'organizzazione di Teams per l'attivazione dello spazio di indirizzi SIP condiviso con la distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="060c3-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Teams organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="060c3-126">Per abilitare lo spazio di indirizzi SIP condiviso nell'organizzazione, stabilire una sessione remota di PowerShell con Teams ed eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="060c3-126">To enable shared SIP address space in your organization, establish a remote PowerShell session with Teams, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="060c3-127">L'attributo SharedSipAddressSpace deve rimanere "True" finché il passaggio online non è definitivo e nessun utente rimane in locale.</span><span class="sxs-lookup"><span data-stu-id="060c3-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="060c3-128">Per stabilire una sessione remota di PowerShell con Teams (o Skype for Business Online), è innanzitutto necessario installare il modulo [Teams PowerShell.](/microsoftteams/teams-powershell-install)</span><span class="sxs-lookup"><span data-stu-id="060c3-128">To establish a remote PowerShell session with Teams (or Skype for Business Online), you first need to install the [Teams PowerShell module](/microsoftteams/teams-powershell-install).</span></span> <span data-ttu-id="060c3-129">Il Teams PowerShell sostituisce il modulo Skype per Busines Online Connector, che è stato ritirato.</span><span class="sxs-lookup"><span data-stu-id="060c3-129">The Teams PowerShell module replaces the Skype for Busines Online Connector module, which has been retired.</span></span>
  
<span data-ttu-id="060c3-130">Dopo aver installato il modulo, è possibile stabilire una sessione remota con i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="060c3-130">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
   ```powershell
   # When using Teams PowerShell Module

   Import-Module MicrosoftTeams
   $credential = Get-Credential
   Connect-MicrosoftTeams -Credential $credential
   ```

<span data-ttu-id="060c3-131">Per ulteriori informazioni su come stabilire una sessione remota di PowerShell con Teams e su come usare il modulo powershell di Teams, vedere [Set up your computer for Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span><span class="sxs-lookup"><span data-stu-id="060c3-131">For more information about how to establish a remote PowerShell session with Teams, and how to use the Teams PowerShell module, see [Set up your computer for Windows PowerShell](../../SfbOnline/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="060c3-132">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="060c3-132">See also</span></span>

[<span data-ttu-id="060c3-133">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="060c3-133">New-CsHostingProvider</span></span>](/powershell/module/skype/new-cshostingprovider?view=skype-ps)
