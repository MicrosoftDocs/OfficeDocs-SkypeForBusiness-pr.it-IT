---
title: Configurare la distribuzione locale per Skype Meeting Broadcast
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
description: 'Riepilogo: informazioni sui passaggi da eseguire per configurare Skype Meeting Broadcast per la distribuzione ibrida di Skype for Business Server locale.'
ms.openlocfilehash: b70272ee90146bdac87264acf0c7673b8def05c2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103692"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="42d85-103">Configurare la distribuzione locale per Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="42d85-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="42d85-104">**Riepilogo:** Informazioni sui passaggi da eseguire per configurare Skype Meeting Broadcast per la distribuzione ibrida di Skype for Business Server locale.</span><span class="sxs-lookup"><span data-stu-id="42d85-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="42d85-105">Skype Meeting Broadcast è un servizio online che fa parte di Office 365.</span><span class="sxs-lookup"><span data-stu-id="42d85-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="42d85-106">Se si esegue Skype for Business Server in locale e si desidera utilizzare Skype Meeting Broadcast nel proprio ambiente, è necessario seguire i passaggi di configurazione descritti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="42d85-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="42d85-107">Prima di iniziare, l'ambiente deve essere configurato per la distribuzione ibrida con Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="42d85-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="42d85-108">Per ulteriori informazioni, vedere Pianificare la connettività ibrida tra [Skype for Business Server](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) e Skype for Business online e Distribuire la connettività ibrida tra Skype for Business Server e Skype for Business [online.](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json)</span><span class="sxs-lookup"><span data-stu-id="42d85-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../SfbHybrid/hybrid/plan-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../../SfbHybrid/hybrid/configure-hybrid-connectivity.md?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="42d85-109">Configurare l'ambiente ibrido per Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="42d85-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="42d85-110">Dovrai eseguire le operazioni seguenti per preparare l'ambiente per Skype Meeting Broadcast:</span><span class="sxs-lookup"><span data-stu-id="42d85-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="42d85-111">Configurare la federazione con le risorse di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="42d85-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="42d85-112">Configurare i domini federati SIP</span><span class="sxs-lookup"><span data-stu-id="42d85-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="42d85-113">Configurare la federazione con le risorse di Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="42d85-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="42d85-114">Per abilitare la federazione con le risorse di Skype for Business Online, è necessario configurare l'accesso esterno per un provider federato SIP.</span><span class="sxs-lookup"><span data-stu-id="42d85-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="42d85-115">Per eseguire questa operazione utilizzando il Pannello di controllo di Skype for Business Server, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="42d85-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="42d85-116">Avviare il Pannello di controllo di Skype for Business Server e selezionare **Accesso esterno** a sinistra.</span><span class="sxs-lookup"><span data-stu-id="42d85-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="42d85-117">Selezionare **Provider federati SIP e** fare clic su **Nuovo.**</span><span class="sxs-lookup"><span data-stu-id="42d85-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="42d85-118">Configurare il nuovo provider con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="42d85-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="42d85-119">**Abilita comunicazioni con questo provider:**</span><span class="sxs-lookup"><span data-stu-id="42d85-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="42d85-120">Opzione selezionata</span><span class="sxs-lookup"><span data-stu-id="42d85-120">Selected</span></span>  <br/> |
|<span data-ttu-id="42d85-121">**Nome provider:**</span><span class="sxs-lookup"><span data-stu-id="42d85-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="42d85-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="42d85-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="42d85-123">**Servizio Access Edge (FQDN):**</span><span class="sxs-lookup"><span data-stu-id="42d85-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="42d85-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="42d85-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="42d85-125">**Livello di verifica predefinito**</span><span class="sxs-lookup"><span data-stu-id="42d85-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="42d85-126">Consenti agli utenti di comunicare con tutti gli utenti che usano questo provider.</span><span class="sxs-lookup"><span data-stu-id="42d85-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="42d85-127">È inoltre possibile abilitare la federazione con le risorse di Skype for Business Online eseguendo il cmdlet seguente in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="42d85-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="42d85-128">Configurare i domini federati SIP</span><span class="sxs-lookup"><span data-stu-id="42d85-128">Configure SIP federated domains</span></span>

<span data-ttu-id="42d85-129">Successivamente, è necessario aggiungere domini federati SIP all'elenco dei domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="42d85-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="42d85-130">Ripetere questi passaggi per ognuno dei domini elencati, creando 4 nuovi domini federati SIP.</span><span class="sxs-lookup"><span data-stu-id="42d85-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="42d85-131">Questi domini includono i data center regionali usati in Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="42d85-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="42d85-132">Avviare il Pannello di controllo di Skype for Business Server e selezionare **Accesso esterno** a sinistra.</span><span class="sxs-lookup"><span data-stu-id="42d85-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="42d85-133">Selezionare **Domini federati SIP e** fare clic su **Nuovo.**</span><span class="sxs-lookup"><span data-stu-id="42d85-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="42d85-134">Per **nome di dominio (o FQDN):** immettere il dominio, ripetendo questa procedura per ognuno dei domini seguenti:</span><span class="sxs-lookup"><span data-stu-id="42d85-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="42d85-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="42d85-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="42d85-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="42d85-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="42d85-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="42d85-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="42d85-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="42d85-138">resources.lync.com</span></span>
    
<span data-ttu-id="42d85-139">È inoltre possibile configurare l'accesso esterno per i domini federati SIP eseguendo i cmdlet seguenti in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="42d85-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="42d85-140">Dopo aver completato questi passaggi di configurazione, puoi iniziare a usare Skype Meeting Broadcast nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="42d85-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="42d85-141">Per altre informazioni su Skype Meeting Broadcast, vedi [Che cos'è Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) e Guida all'amministratore [di Skype Meeting Broadcast.](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md)</span><span class="sxs-lookup"><span data-stu-id="42d85-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](../../SfbOnline/set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md).</span></span>
