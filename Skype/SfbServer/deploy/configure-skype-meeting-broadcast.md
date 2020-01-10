---
title: Configurare la distribuzione locale per Skype meeting broadcast
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Riepilogo: informazioni sui passaggi che è necessario eseguire per configurare Skype meeting broadcast per la distribuzione ibrida di Skype for Business Server locale.'
ms.openlocfilehash: ac08707a60e0c71719ab2cb85141e89329a947f9
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/09/2020
ms.locfileid: "41002806"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="f6cbb-103">Configurare la distribuzione locale per Skype meeting broadcast</span><span class="sxs-lookup"><span data-stu-id="f6cbb-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="f6cbb-104">**Riepilogo:** Informazioni sui passaggi che è necessario eseguire per configurare Skype meeting broadcast per la distribuzione ibrida di Skype for Business Server locale.</span><span class="sxs-lookup"><span data-stu-id="f6cbb-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="f6cbb-105">Skype meeting broadcast è un servizio online che fa parte di Office 365.</span><span class="sxs-lookup"><span data-stu-id="f6cbb-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="f6cbb-106">Se si usa Skype for Business Server locale e si vuole usare Skype meeting broadcast nell'ambiente, è necessario seguire la procedura di configurazione in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="f6cbb-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="f6cbb-107">Prima di iniziare, l'ambiente deve essere configurato per l'ibrido con Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="f6cbb-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="f6cbb-108">Per altre informazioni, Vedi [pianificare la connettività ibrida tra Skype for Business Server e Skype for business online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) e [distribuire la connettività ibrida tra Skype for Business Server e Skype for business online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="f6cbb-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="f6cbb-109">Configurare l'ambiente ibrido per Skype meeting broadcast</span><span class="sxs-lookup"><span data-stu-id="f6cbb-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="f6cbb-110">Per preparare l'ambiente per Skype meeting broadcast è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6cbb-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="f6cbb-111">Configurare la Federazione con le risorse di Skype for business online</span><span class="sxs-lookup"><span data-stu-id="f6cbb-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="f6cbb-112">Configurare i domini federati SIP</span><span class="sxs-lookup"><span data-stu-id="f6cbb-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="f6cbb-113">Configurare la Federazione con le risorse di Skype for business online</span><span class="sxs-lookup"><span data-stu-id="f6cbb-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="f6cbb-114">Per abilitare la Federazione con le risorse di Skype for business online, è necessario configurare l'accesso esterno per un provider federato SIP.</span><span class="sxs-lookup"><span data-stu-id="f6cbb-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="f6cbb-115">Per eseguire questa operazione, usare il pannello di controllo di Skype for Business Server seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="f6cbb-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="f6cbb-116">Avviare il pannello di controllo di Skype for Business Server e selezionare **accesso esterno** a sinistra.</span><span class="sxs-lookup"><span data-stu-id="f6cbb-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="f6cbb-117">Selezionare **provider federati SIP** e fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f6cbb-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="f6cbb-118">Configurare il nuovo provider con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6cbb-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="f6cbb-119">**Abilitare le comunicazioni con questo provider:**</span><span class="sxs-lookup"><span data-stu-id="f6cbb-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="f6cbb-120">Selezionato</span><span class="sxs-lookup"><span data-stu-id="f6cbb-120">Selected</span></span>  <br/> |
|<span data-ttu-id="f6cbb-121">**Nome provider:**</span><span class="sxs-lookup"><span data-stu-id="f6cbb-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="f6cbb-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="f6cbb-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="f6cbb-123">**Access Edge Services (FQDN):**</span><span class="sxs-lookup"><span data-stu-id="f6cbb-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="f6cbb-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="f6cbb-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="f6cbb-125">**Livello di verifica predefinito:**</span><span class="sxs-lookup"><span data-stu-id="f6cbb-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="f6cbb-126">Consentire agli utenti di comunicare con tutti tramite questo provider.</span><span class="sxs-lookup"><span data-stu-id="f6cbb-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="f6cbb-127">Puoi anche abilitare la Federazione con le risorse di Skype for business online eseguendo il cmdlet seguente in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="f6cbb-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="f6cbb-128">Configurare i domini federati SIP</span><span class="sxs-lookup"><span data-stu-id="f6cbb-128">Configure SIP federated domains</span></span>

<span data-ttu-id="f6cbb-129">È quindi necessario aggiungere domini federati SIP all'elenco di domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="f6cbb-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="f6cbb-130">Ripetere questi passaggi per ogni dominio elencato, creando 4 nuovi domini federati SIP.</span><span class="sxs-lookup"><span data-stu-id="f6cbb-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="f6cbb-131">Questi domini includono sono per i centri dati regionali usati in Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="f6cbb-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="f6cbb-132">Avviare il pannello di controllo di Skype for Business Server e selezionare **accesso esterno** a sinistra.</span><span class="sxs-lookup"><span data-stu-id="f6cbb-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="f6cbb-133">Selezionare **domini federati SIP** e fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="f6cbb-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="f6cbb-134">Per il **nome di dominio (o FQDN):** immettere il dominio, ripetendo questa procedura per ognuno dei domini seguenti:</span><span class="sxs-lookup"><span data-stu-id="f6cbb-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="f6cbb-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="f6cbb-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="f6cbb-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="f6cbb-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="f6cbb-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="f6cbb-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="f6cbb-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="f6cbb-138">resources.lync.com</span></span>
    
<span data-ttu-id="f6cbb-139">È anche possibile configurare l'accesso esterno per i domini federati SIP eseguendo i cmdlet seguenti in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="f6cbb-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```powershell
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="f6cbb-140">Dopo aver completato questi passaggi di configurazione, è possibile iniziare a usare Skype meeting broadcast nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="f6cbb-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="f6cbb-141">Per altre informazioni su Skype meeting broadcast, vedere [cos'è un Skype meeting broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) e [Guida per gli amministratori di Skype meeting broadcast](https://go.microsoft.com/fwlink/?LinkId=617075).</span><span class="sxs-lookup"><span data-stu-id="f6cbb-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

