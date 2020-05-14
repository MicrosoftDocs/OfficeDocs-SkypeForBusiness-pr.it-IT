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
description: "Riepilogo: informazioni su come configurare l'interoperabilità tra la distribuzione locale e Skype for business online."
ms.openlocfilehash: 0df507fcc47157a9290018a199e1362cb203048b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221450"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="1d6cb-103">Configurare Skype for Business ibrido</span><span class="sxs-lookup"><span data-stu-id="1d6cb-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="1d6cb-104">Per configurare Skype for Business ibrido, è necessario:</span><span class="sxs-lookup"><span data-stu-id="1d6cb-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="1d6cb-105">[Configurare il servizio perimetrale locale per la Federazione con Microsoft 365 o Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365).</span><span class="sxs-lookup"><span data-stu-id="1d6cb-105">[Configure your on-premises Edge service to federate with Microsoft 365 or Office 365](#configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="1d6cb-106">[Configurare l'ambiente locale in modo che consideri attendibile Microsoft 365 o Office 365 e che sia abilitato lo spazio degli indirizzi SIP condiviso](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365).</span><span class="sxs-lookup"><span data-stu-id="1d6cb-106">[Configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365).</span></span>
- <span data-ttu-id="1d6cb-107">[Abilitare lo spazio degli indirizzi SIP condiviso nell'organizzazione Microsoft 365 o Office 365](#enable-shared-sip-address-space-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="1d6cb-107">[Enable shared SIP address space in your Microsoft 365 or Office 365 organization](#enable-shared-sip-address-space-in-your-organization).</span></span>

<span data-ttu-id="1d6cb-108">Si noti che, se si dispone di Exchange locale, è possibile configurare OAuth tra gli ambienti Exchange locale e Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="1d6cb-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="1d6cb-109">Per ulteriori informazioni, vedere [gestire l'autenticazione da server a server in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) e [pianificare l'integrazione di Skype for business ed Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span><span class="sxs-lookup"><span data-stu-id="1d6cb-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-microsoft-365-or-office-365"></a><span data-ttu-id="1d6cb-110">Configurare il servizio perimetrale locale per la Federazione con Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="1d6cb-110">Configure your on-premises Edge service to federate with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="1d6cb-111">La federazione consente agli utenti della distribuzione locale di comunicare con gli utenti di Microsoft 365 o Office 365 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="1d6cb-111">Federation allows users in your on-premises deployment to communicate with Microsoft 365 or Office 365 users in your organization.</span></span> <span data-ttu-id="1d6cb-112">Per configurare la Federazione, eseguire il seguente cmdlet in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="1d6cb-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers $True -AllowFederatedUsers $True -EnablePartnerDiscovery $True -UseDnsSrvRouting
```

<span data-ttu-id="1d6cb-113">Se il valore di '-EnablePartnerDiscovery ' è impostato su $True, Skype for Business Server utilizzerà i record DNS per cercare di individuare i domini dei partner non elencati nell'elenco AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="1d6cb-113">If '-EnablePartnerDiscovery' value is set to $True, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="1d6cb-114">Se il valore è impostato su $False, in Skype for Business Server la federazione verrà associata solo ai domini trovati nell'elenco AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="1d6cb-114">If the value is set to $False , Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="1d6cb-115">Questo parametro è obbligatorio se si utilizza il routing del servizio DNS.</span><span class="sxs-lookup"><span data-stu-id="1d6cb-115">This parameter is required if you use DNS service routing.</span></span>

> [!NOTE]
> <span data-ttu-id="1d6cb-116">Per ulteriori informazioni sull'abilitazione della Federazione tra gli utenti della distribuzione di Skype for business locale e gli utenti di un'organizzazione di Skype for business online, vedere [Configuring Federation support for a Skype for business online Customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).</span><span class="sxs-lookup"><span data-stu-id="1d6cb-116">For more details about enabling federation between users of your on-premises Skype for Business deployment and users of a Skype for Business Online organization, see [Configuring federation support for a Skype for Business Online customer in Skype for Business Server](https://docs.microsoft.com/skypeforbusiness/manage/federation-and-external-access/federation-support/configuring-federation-support).</span></span>


## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-microsoft-365-or-office-365"></a><span data-ttu-id="1d6cb-117">Configurare l'ambiente locale per abilitare lo spazio degli indirizzi SIP condiviso con Microsoft 365 o Office 365</span><span class="sxs-lookup"><span data-stu-id="1d6cb-117">Configure your on-premises environment to enable shared SIP address space with Microsoft 365 or Office 365</span></span>

<span data-ttu-id="1d6cb-118">È inoltre necessario configurare l'ambiente locale in modo che consideri attendibile Microsoft 365 o Office 365 e che sia abilitato lo spazio degli indirizzi SIP condiviso.</span><span class="sxs-lookup"><span data-stu-id="1d6cb-118">You must also configure your on-premises environment to trust Microsoft 365 or Office 365 and enable shared SIP address space.</span></span> <span data-ttu-id="1d6cb-119">Questo significa che Microsoft 365 o Office 365 può potenzialmente ospitare account utente per lo stesso insieme di domini SIP dell'ambiente locale e i messaggi possono essere instradati tra gli utenti ospitati in locale e online.</span><span class="sxs-lookup"><span data-stu-id="1d6cb-119">This means Microsoft 365 or Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="1d6cb-120">A tale scopo, configurare un provider di hosting con ProxyFqdn = sipfed. online. Lync. com come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="1d6cb-120">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="1d6cb-121">In primo luogo, controllare se si dispone già di un provider di hosting con ProxyFqdn = sipfed. online. Lync. com.</span><span class="sxs-lookup"><span data-stu-id="1d6cb-121">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="1d6cb-122">Se esiste, rimuoverlo utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="1d6cb-122">If one exists, then remove it by using the following command:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="1d6cb-123">Creare quindi un nuovo provider di hosting, utilizzare il cmdlet New-CsHostingProvider come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="1d6cb-123">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-organization"></a><span data-ttu-id="1d6cb-124">Abilitare lo spazio degli indirizzi SIP condiviso nell'organizzazione</span><span class="sxs-lookup"><span data-stu-id="1d6cb-124">Enable shared SIP address space in your organization</span></span>
  
<span data-ttu-id="1d6cb-125">Oltre alla modifica apportata nella distribuzione locale, è necessario apportare le modifiche corrispondenti nell'organizzazione Microsoft 365 o Office 365 per abilitare lo spazio degli indirizzi SIP condiviso con la distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="1d6cb-125">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Microsoft 365 or Office 365 organization to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="1d6cb-126">Per abilitare lo spazio degli indirizzi SIP condiviso nell'organizzazione, stabilire una sessione remota di PowerShell con Skype for business online e quindi eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="1d6cb-126">To enable shared SIP address space in your organization, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="1d6cb-127">L'attributo SharedSipAddressSpace deve rimanere "true" fino a quando lo spostamento in linea è finale e nessuno degli utenti rimane in locale.</span><span class="sxs-lookup"><span data-stu-id="1d6cb-127">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="1d6cb-128">Per creare una sessione di PowerShell remota con team o Skype for business online, è necessario prima di tutto installare il modulo del connettore di Skype for business online per Windows PowerShell, che è possibile ottenere [qui](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="1d6cb-128">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="1d6cb-129">Dopo aver installato il modulo, è possibile stabilire una sessione remota con i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="1d6cb-129">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="1d6cb-130">Per ulteriori informazioni su come stabilire una sessione remota di PowerShell con Skype for business online e su come usare il modulo connettore di Skype for business online, vedere [configurare il computer per Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="1d6cb-130">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="1d6cb-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1d6cb-131">See also</span></span>

[<span data-ttu-id="1d6cb-132">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="1d6cb-132">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)
