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
ms.openlocfilehash: c016d60b416c7b6d935b15718f3f1a10f439b9ab
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49820706"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="cdd3a-103">Configurare la distribuzione locale per Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="cdd3a-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="cdd3a-104">**Riepilogo:** Informazioni sui passaggi da eseguire per configurare Skype Meeting Broadcast per la distribuzione ibrida di Skype for Business Server locale.</span><span class="sxs-lookup"><span data-stu-id="cdd3a-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="cdd3a-105">Skype Meeting Broadcast è un servizio online che fa parte di Office 365.</span><span class="sxs-lookup"><span data-stu-id="cdd3a-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="cdd3a-106">Se si esegue Skype for Business Server in locale e si vuole usare Skype Meeting Broadcast nel proprio ambiente, è necessario seguire i passaggi di configurazione descritti in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="cdd3a-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="cdd3a-107">Prima di iniziare, l'ambiente deve essere configurato per l'ambiente ibrido con Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="cdd3a-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="cdd3a-108">Per ulteriori informazioni, vedere Pianificare la connettività ibrida tra Skype for Business Server e [Skype for Business online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) e Distribuire la connettività ibrida tra Skype for Business Server e Skype for Business [online.](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="cdd3a-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="cdd3a-109">Configurare l'ambiente ibrido per Skype Meeting Broadcast</span><span class="sxs-lookup"><span data-stu-id="cdd3a-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="cdd3a-110">Dovrai eseguire le operazioni seguenti per preparare l'ambiente per Skype Meeting Broadcast:</span><span class="sxs-lookup"><span data-stu-id="cdd3a-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="cdd3a-111">Configurare la federazione con le risorse di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="cdd3a-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="cdd3a-112">Configurare i domini federati SIP</span><span class="sxs-lookup"><span data-stu-id="cdd3a-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="cdd3a-113">Configurare la federazione con le risorse di Skype for Business online</span><span class="sxs-lookup"><span data-stu-id="cdd3a-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="cdd3a-114">Per abilitare la federazione con le risorse di Skype for Business online, è necessario configurare l'accesso esterno per un provider federato SIP.</span><span class="sxs-lookup"><span data-stu-id="cdd3a-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="cdd3a-115">Per eseguire questa operazione utilizzando il Pannello di controllo di Skype for Business Server, attenersi alla seguente procedura:</span><span class="sxs-lookup"><span data-stu-id="cdd3a-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="cdd3a-116">Avviare il Pannello di controllo di Skype for Business Server e selezionare **Accesso esterno** a sinistra.</span><span class="sxs-lookup"><span data-stu-id="cdd3a-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="cdd3a-117">Selezionare **Provider federati SIP e** fare clic su **Nuovo.**</span><span class="sxs-lookup"><span data-stu-id="cdd3a-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="cdd3a-118">Configurare il nuovo provider con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdd3a-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="cdd3a-119">**Abilita comunicazioni con questo provider:**</span><span class="sxs-lookup"><span data-stu-id="cdd3a-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="cdd3a-120">Opzione selezionata</span><span class="sxs-lookup"><span data-stu-id="cdd3a-120">Selected</span></span>  <br/> |
|<span data-ttu-id="cdd3a-121">**Nome provider:**</span><span class="sxs-lookup"><span data-stu-id="cdd3a-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="cdd3a-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="cdd3a-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="cdd3a-123">**Servizio Access Edge (FQDN):**</span><span class="sxs-lookup"><span data-stu-id="cdd3a-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="cdd3a-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="cdd3a-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="cdd3a-125">**Livello di verifica predefinito**</span><span class="sxs-lookup"><span data-stu-id="cdd3a-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="cdd3a-126">Consentire agli utenti di comunicare con tutti gli utenti che utilizzano questo provider.</span><span class="sxs-lookup"><span data-stu-id="cdd3a-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="cdd3a-127">È anche possibile abilitare la federazione con le risorse di Skype for Business online eseguendo il cmdlet seguente in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="cdd3a-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="cdd3a-128">Configurare i domini federati SIP</span><span class="sxs-lookup"><span data-stu-id="cdd3a-128">Configure SIP federated domains</span></span>

<span data-ttu-id="cdd3a-129">Successivamente, è necessario aggiungere i domini federati SIP all'elenco dei domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="cdd3a-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="cdd3a-130">Ripetere questi passaggi per ognuno dei domini elencati, creando 4 nuovi domini federati SIP.</span><span class="sxs-lookup"><span data-stu-id="cdd3a-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="cdd3a-131">Questi domini includono i data center regionali usati in Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="cdd3a-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="cdd3a-132">Avviare il Pannello di controllo di Skype for Business Server e selezionare **Accesso esterno** a sinistra.</span><span class="sxs-lookup"><span data-stu-id="cdd3a-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="cdd3a-133">Selezionare **Domini federati SIP e fare** clic su **Nuovo.**</span><span class="sxs-lookup"><span data-stu-id="cdd3a-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="cdd3a-134">Per il **nome di dominio (o FQDN):** immettere il dominio, ripetendo questa procedura per ognuno dei domini seguenti:</span><span class="sxs-lookup"><span data-stu-id="cdd3a-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="cdd3a-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="cdd3a-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="cdd3a-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="cdd3a-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="cdd3a-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="cdd3a-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="cdd3a-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="cdd3a-138">resources.lync.com</span></span>
    
<span data-ttu-id="cdd3a-139">È inoltre possibile configurare l'accesso esterno per i domini federati SIP eseguendo i cmdlet seguenti in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="cdd3a-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="cdd3a-140">Dopo aver completato questi passaggi di configurazione, puoi iniziare a usare Skype Meeting Broadcast nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="cdd3a-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="cdd3a-141">Per altre informazioni su Skype Meeting Broadcast, vedere [Che cos'è Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) e Guida all'amministratore [di Skype Meeting Broadcast.](https://go.microsoft.com/fwlink/?LinkId=617075)</span><span class="sxs-lookup"><span data-stu-id="cdd3a-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

