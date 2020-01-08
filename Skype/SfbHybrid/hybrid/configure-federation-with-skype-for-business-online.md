---
title: Configurare l'ambiente ibrido di Skype for business
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
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
ms.openlocfilehash: c451224e7f421b4505560533b2880a14cc04e1a9
ms.sourcegitcommit: afc7edd03f4baa1d75f9642d4dbce767fec69b00
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "40963034"
---
# <a name="configure-skype-for-business-hybrid"></a><span data-ttu-id="5b827-103">Configurare l'ambiente ibrido di Skype for business</span><span class="sxs-lookup"><span data-stu-id="5b827-103">Configure Skype for Business hybrid</span></span>

<span data-ttu-id="5b827-104">Per configurare Skype for business ibrido, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b827-104">To configure Skype for Business hybrid, you need to:</span></span>

- <span data-ttu-id="5b827-105">[Configurare il servizio dell'ambiente locale per la Federazione con Office 365](#configure-your-on-premises-edge-service-to-federate-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="5b827-105">[Configure your on-premises environment service to federate with Office 365](#configure-your-on-premises-edge-service-to-federate-with-office-365).</span></span>
- <span data-ttu-id="5b827-106">[Configurare l'ambiente locale in modo che consideri attendibile office 365 e che venga abilitato lo spazio degli indirizzi SIP condiviso con office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).</span><span class="sxs-lookup"><span data-stu-id="5b827-106">[Configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365](#configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365).</span></span>
- <span data-ttu-id="5b827-107">[Abilitare lo spazio degli indirizzi SIP condiviso nel tenant di Office 365](#enable-shared-sip-address-space-in-your-office-365-tenant).</span><span class="sxs-lookup"><span data-stu-id="5b827-107">[Enable shared SIP address space in your Office 365 tenant](#enable-shared-sip-address-space-in-your-office-365-tenant).</span></span>

<span data-ttu-id="5b827-108">Si noti che, se si dispone di Exchange locale, è possibile configurare OAuth tra gli ambienti Exchange locale e Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="5b827-108">Note that if you have Exchange on-premises, you may want to configure OAuth between your Exchange on-premises and Skype for Business Online environments.</span></span> <span data-ttu-id="5b827-109">Per ulteriori informazioni, vedere [gestire l'autenticazione da server a server in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) e [pianificare l'integrazione di Skype for business ed Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span><span class="sxs-lookup"><span data-stu-id="5b827-109">For more information, see  [Manage server-to-server authentication in Skype for Business Server](https://docs.microsoft.com/SkypeForBusiness/manage/authentication/server-to-server-and-partner-applications) and [Plan to integrate Skype for Business and Exchange](https://docs.microsoft.com/SkypeForBusiness/plan-your-deployment/integrate-with-exchange/integrate-with-exchange#feature_support).</span></span> 
  
## <a name="configure-your-on-premises-edge-service-to-federate-with-office-365"></a><span data-ttu-id="5b827-110">Configurare il servizio perimetrale locale per la Federazione con Office 365</span><span class="sxs-lookup"><span data-stu-id="5b827-110">Configure your on-premises Edge service to federate with Office 365</span></span>

<span data-ttu-id="5b827-111">La federazione consente agli utenti della distribuzione locale di comunicare con gli utenti di Office 365 nell'organizzazione.</span><span class="sxs-lookup"><span data-stu-id="5b827-111">Federation allows users in your on-premises deployment to communicate with Office 365 users in your organization.</span></span> <span data-ttu-id="5b827-112">Per configurare la Federazione, eseguire il seguente cmdlet in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="5b827-112">To configure federation, run the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```PowerShell
Set-CSAccessEdgeConfiguration -AllowOutsideUsers 1 -AllowFederatedUsers 1 -EnablePartnerDiscovery 1 -UseDnsSrvRouting
```

<span data-ttu-id="5b827-113">Se il valore di '-EnablePartnerDiscovery ' è impostato su 1, Skype for Business Server utilizzerà i record DNS per cercare di individuare i domini dei partner non elencati nell'elenco AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="5b827-113">If '-EnablePartnerDiscovery' value set to 1, Skype for Business Server will use DNS records to try and discover partner domains not listed in the AllowedDomains list.</span></span> <span data-ttu-id="5b827-114">Se il valore è impostato su 0, in Skype for Business Server la federazione verrà associata solo ai domini trovati nell'elenco AllowedDomains.</span><span class="sxs-lookup"><span data-stu-id="5b827-114">If the value set to 0, Skype for Business Server will only federate with domains found on the AllowedDomains list.</span></span> <span data-ttu-id="5b827-115">Questo parametro è obbligatorio se si utilizza il routing del servizio DNS.</span><span class="sxs-lookup"><span data-stu-id="5b827-115">This parameter is required if you use DNS service routing.</span></span>



## <a name="configure-your-on-premises-environment-to-enable-shared-sip-address-space-with-office-365"></a><span data-ttu-id="5b827-116">Configurare l'ambiente locale per abilitare lo spazio degli indirizzi SIP condiviso con Office 365</span><span class="sxs-lookup"><span data-stu-id="5b827-116">Configure your on-premises environment to enable shared SIP address space with Office 365</span></span>

<span data-ttu-id="5b827-117">È inoltre necessario configurare l'ambiente locale affinché consideri attendibile Office 365 e abilitare lo spazio degli indirizzi SIP condiviso con Office 365.</span><span class="sxs-lookup"><span data-stu-id="5b827-117">You must also configure your on-premises environment to trust Office 365 and enable shared SIP address space with Office 365.</span></span> <span data-ttu-id="5b827-118">Questo significa che Office 365 può ospitare account utente per lo stesso gruppo di domini SIP dell'ambiente locale e i messaggi possono essere instradati tra gli utenti ospitati in locale e online.</span><span class="sxs-lookup"><span data-stu-id="5b827-118">This means Office 365 can potentially host user accounts for the same set of SIP domains as your on-premises environment, and messages can be routed between users hosted on premises and online.</span></span>  <span data-ttu-id="5b827-119">A tale scopo, configurare un provider di hosting con ProxyFqdn = sipfed. online. Lync. com come descritto di seguito.</span><span class="sxs-lookup"><span data-stu-id="5b827-119">You do this by configuring a hosting provider with ProxyFqdn=sipfed.online.lync.com as described below.</span></span>

<span data-ttu-id="5b827-120">In primo luogo, controllare se si dispone già di un provider di hosting con ProxyFqdn = sipfed. online. Lync. com.</span><span class="sxs-lookup"><span data-stu-id="5b827-120">First, check if you already have a hosting provider with ProxyFqdn=sipfed.online.lync.com.</span></span> <span data-ttu-id="5b827-121">Se esiste, rimuoverlo utilizzando il comando seguente:</span><span class="sxs-lookup"><span data-stu-id="5b827-121">If one exists, then remove it by using the following command:</span></span>

```PowerShell
Get-CsHostingProvider | ?{ $_.ProxyFqdn -eq "sipfed.online.lync.com" } | Remove-CsHostingProvider
```

<span data-ttu-id="5b827-122">Creare quindi un nuovo provider di hosting, utilizzare il cmdlet New-CsHostingProvider come indicato di seguito:</span><span class="sxs-lookup"><span data-stu-id="5b827-122">Then create a new hosting provider, use the New-CsHostingProvider cmdlet as follows:</span></span> 

```PowerShell
New-CsHostingProvider -Identity Office365 -ProxyFqdn "sipfed.online.lync.com" -Enabled $true -EnabledSharedAddressSpace $true -HostsOCSUsers $true -VerificationLevel UseSourceVerification -IsLocal $false -AutodiscoverUrl https://webdir.online.lync.com/Autodiscover/AutodiscoverService.svc/root 
```

 ## <a name="enable-shared-sip-address-space-in-your-office-365-tenant"></a><span data-ttu-id="5b827-123">Abilitare lo spazio degli indirizzi SIP condiviso nel tenant di Office 365</span><span class="sxs-lookup"><span data-stu-id="5b827-123">Enable shared SIP address space in your Office 365 tenant</span></span>
  
<span data-ttu-id="5b827-124">Oltre alla modifica apportata nella distribuzione locale, è necessario apportare la modifica corrispondente nel tenant di Office 365 per abilitare lo spazio di indirizzi SIP condiviso con la distribuzione locale.</span><span class="sxs-lookup"><span data-stu-id="5b827-124">In addition to the change you made in your on-premises deployment, you'll need to make the corresponding change in your Office 365 tenant to enabled shared SIP address space with your on-premises deployment.</span></span>  

<span data-ttu-id="5b827-125">Per abilitare lo spazio degli indirizzi SIP condiviso nel tenant di Office 365, stabilire una sessione remota di PowerShell con Skype for business online e quindi eseguire il cmdlet seguente:</span><span class="sxs-lookup"><span data-stu-id="5b827-125">To enable shared SIP address space in your Office 365 tenant, establish a remote PowerShell session with Skype for Business Online, and then run the following cmdlet:</span></span>
  
```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $true
```

> [!NOTE]
> <span data-ttu-id="5b827-126">L'attributo SharedSipAddressSpace deve rimanere "true" fino a quando lo spostamento in linea è finale e nessuno degli utenti rimane in locale.</span><span class="sxs-lookup"><span data-stu-id="5b827-126">The SharedSipAddressSpace attribute needs to remain "True" until moving to online is final, and no users remain on-premises.</span></span> 
  
<span data-ttu-id="5b827-127">Per creare una sessione di PowerShell remota con team o Skype for business online, è necessario prima di tutto installare il modulo del connettore di Skype for business online per Windows PowerShell, che è possibile ottenere [qui](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span><span class="sxs-lookup"><span data-stu-id="5b827-127">To establish a remote PowerShell session with Teams or Skype for Business Online, you first need to install the Skype for Business Online connector module for Windows PowerShell, which you can get [here](https://go.microsoft.com/fwlink/p/?LinkId=391911).</span></span>
  
<span data-ttu-id="5b827-128">Dopo aver installato il modulo, è possibile stabilire una sessione remota con i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="5b827-128">After you install the module, you can establish a remote session with the following cmdlets:</span></span>
  
```PowerShell
$cred = Get-Credential
Import-PSSession (New-CsOnlineSession -Credential $cred) -AllowClobber
```

<span data-ttu-id="5b827-129">Per ulteriori informazioni su come stabilire una sessione remota di PowerShell con Skype for business online e su come usare il modulo connettore di Skype for business online, vedere [configurare il computer per Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="5b827-129">For more information about how to establish a remote PowerShell session with Skype for Business Online, and how to use the Skype for Business Online Connector module, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span>
  


## <a name="see-also"></a><span data-ttu-id="5b827-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="5b827-130">See also</span></span>

[<span data-ttu-id="5b827-131">New-CsHostingProvider</span><span class="sxs-lookup"><span data-stu-id="5b827-131">New-CsHostingProvider</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshostingprovider?view=skype-ps)

