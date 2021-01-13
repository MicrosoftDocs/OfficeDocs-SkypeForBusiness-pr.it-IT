---
title: Configurare la distribuzione locale per Skype meeting broadcast
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Riepilogo: informazioni sui passaggi che è necessario eseguire per configurare Skype meeting broadcast per la distribuzione ibrida di Skype for Business Server locale.'
ms.openlocfilehash: c016d60b416c7b6d935b15718f3f1a10f439b9ab
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820706"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="52854-103">Configurare la distribuzione locale per Skype meeting broadcast</span><span class="sxs-lookup"><span data-stu-id="52854-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="52854-104">**Riepilogo:** Informazioni sui passaggi che è necessario eseguire per configurare Skype meeting broadcast per la distribuzione ibrida di Skype for Business Server locale.</span><span class="sxs-lookup"><span data-stu-id="52854-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="52854-105">Skype meeting broadcast è un servizio online che fa parte di Office 365.</span><span class="sxs-lookup"><span data-stu-id="52854-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="52854-106">Se si esegue Skype for Business Server in locale e si desidera utilizzare Skype meeting broadcast nell'ambiente in uso, è necessario seguire la procedura di configurazione descritta in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="52854-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="52854-107">Prima di iniziare, è necessario configurare l'ambiente per l'ibrido con Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="52854-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="52854-108">Per ulteriori informazioni, vedere [pianificare la connettività ibrida tra Skype for Business Server e Skype for business online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) e [distribuire la connettività ibrida tra Skype for Business Server e Skype for business online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="52854-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="52854-109">Configurare l'ambiente ibrido per Skype meeting broadcast</span><span class="sxs-lookup"><span data-stu-id="52854-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="52854-110">Per preparare l'ambiente per Skype meeting broadcast, è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="52854-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="52854-111">Configurare la Federazione con le risorse di Skype for business online</span><span class="sxs-lookup"><span data-stu-id="52854-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="52854-112">Configurare i domini federati SIP</span><span class="sxs-lookup"><span data-stu-id="52854-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="52854-113">Configurare la Federazione con le risorse di Skype for business online</span><span class="sxs-lookup"><span data-stu-id="52854-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="52854-114">Per abilitare la Federazione con le risorse di Skype for business online, è necessario configurare l'accesso esterno per un provider federato SIP.</span><span class="sxs-lookup"><span data-stu-id="52854-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="52854-115">Per eseguire questa operazione utilizzando il pannello di controllo di Skype for Business Server, eseguire la procedura seguente:</span><span class="sxs-lookup"><span data-stu-id="52854-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="52854-116">Avviare il pannello di controllo di Skype for Business Server e selezionare **accesso esterno** a sinistra.</span><span class="sxs-lookup"><span data-stu-id="52854-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="52854-117">Selezionare **provider federati SIP** e fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="52854-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="52854-118">Configurare il nuovo provider con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="52854-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="52854-119">**Abilitare le comunicazioni con questo provider:**</span><span class="sxs-lookup"><span data-stu-id="52854-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="52854-120">Opzione selezionata</span><span class="sxs-lookup"><span data-stu-id="52854-120">Selected</span></span>  <br/> |
|<span data-ttu-id="52854-121">**Nome provider:**</span><span class="sxs-lookup"><span data-stu-id="52854-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="52854-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="52854-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="52854-123">**Servizio Access Edge (FQDN):**</span><span class="sxs-lookup"><span data-stu-id="52854-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="52854-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="52854-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="52854-125">**Livello di verifica predefinito**</span><span class="sxs-lookup"><span data-stu-id="52854-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="52854-126">Consenti agli utenti di comunicare con tutti quelli che utilizzano questo provider.</span><span class="sxs-lookup"><span data-stu-id="52854-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="52854-127">È inoltre possibile abilitare la Federazione con le risorse di Skype for business online eseguendo il cmdlet seguente in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="52854-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="52854-128">Configurare i domini federati SIP</span><span class="sxs-lookup"><span data-stu-id="52854-128">Configure SIP federated domains</span></span>

<span data-ttu-id="52854-129">Successivamente, è necessario aggiungere i domini federati SIP all'elenco dei domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="52854-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="52854-130">Ripetere questi passaggi per ognuno dei domini elencati, creando 4 nuovi domini federati SIP.</span><span class="sxs-lookup"><span data-stu-id="52854-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="52854-131">Questi domini includono sono per i data center regionali usati in Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="52854-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="52854-132">Avviare il pannello di controllo di Skype for Business Server e selezionare **accesso esterno** a sinistra.</span><span class="sxs-lookup"><span data-stu-id="52854-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="52854-133">Selezionare **domini federati SIP** e fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="52854-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="52854-134">Per il **nome di dominio (o FQDN):** immettere il dominio, ripetendo questa procedura per ognuno dei domini seguenti:</span><span class="sxs-lookup"><span data-stu-id="52854-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="52854-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="52854-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="52854-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="52854-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="52854-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="52854-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="52854-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="52854-138">resources.lync.com</span></span>
    
<span data-ttu-id="52854-139">È inoltre possibile configurare l'accesso esterno per i domini federati SIP eseguendo i cmdlet seguenti in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="52854-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="52854-140">Dopo aver completato questi passaggi di configurazione, è possibile iniziare a usare Skype meeting broadcast nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="52854-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="52854-141">Per ulteriori informazioni su Skype meeting broadcast, vedere [che cos'è un Skype meeting broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) e [Skype meeting broadcast admin guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span><span class="sxs-lookup"><span data-stu-id="52854-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

