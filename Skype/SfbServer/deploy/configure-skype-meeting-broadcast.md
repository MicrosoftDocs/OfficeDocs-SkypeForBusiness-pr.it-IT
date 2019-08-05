---
title: Configurare la distribuzione locale per Skype meeting broadcast
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- Ent_O365_Hybrid_Top
- IT_Skype16
- IT_Skype4B_Hybrid
ms.assetid: 2979802e-fc6b-4555-bc43-7cd48f6a1d88
description: 'Riepilogo: informazioni sui passaggi che è necessario eseguire per configurare Skype meeting broadcast per la distribuzione ibrida di Skype for Business Server locale.'
ms.openlocfilehash: b744ae55fe9c866b2f65c816e471ed077312df13
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36192083"
---
# <a name="configure-your-on-premises-deployment-for-skype-meeting-broadcast"></a><span data-ttu-id="e1b92-103">Configurare la distribuzione locale per Skype meeting broadcast</span><span class="sxs-lookup"><span data-stu-id="e1b92-103">Configure your on-premises deployment for Skype Meeting Broadcast</span></span>
 
<span data-ttu-id="e1b92-104">**Riepilogo:** Informazioni sui passaggi che è necessario eseguire per configurare Skype meeting broadcast per la distribuzione ibrida di Skype for Business Server locale.</span><span class="sxs-lookup"><span data-stu-id="e1b92-104">**Summary:** Learn about the steps you need to perform to configure Skype Meeting Broadcast for your on-premises Skype for Business Server hybrid deployment.</span></span>
  
<span data-ttu-id="e1b92-105">Skype meeting broadcast è un servizio online che fa parte di Office 365.</span><span class="sxs-lookup"><span data-stu-id="e1b92-105">Skype Meeting Broadcast is an online service that is part of Office 365.</span></span> <span data-ttu-id="e1b92-106">Se si usa Skype for Business Server locale e si vuole usare Skype meeting broadcast nell'ambiente, è necessario seguire la procedura di configurazione in questo argomento.</span><span class="sxs-lookup"><span data-stu-id="e1b92-106">If you are running Skype for Business Server on-premises and want to use Skype Meeting Broadcast in your environment, you'll need to follow the configuration steps in this topic.</span></span> <span data-ttu-id="e1b92-107">Prima di iniziare, l'ambiente deve essere configurato per l'ibrido con Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="e1b92-107">Before you begin, your environment needs to be configured for hybrid with Skype for Business Online.</span></span> <span data-ttu-id="e1b92-108">Per altre informazioni, Vedi [pianificare la connettività ibrida tra Skype for Business Server e Skype for business online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) e [distribuire la connettività ibrida tra Skype for Business Server e Skype for business online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span><span class="sxs-lookup"><span data-stu-id="e1b92-108">For more information, see [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md?toc=/SkypeForBusiness/sfbhybridtoc/toc.json) and [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](../skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity.md).</span></span>
  
## <a name="configure-your-hybrid-environment-for-skype-meeting-broadcast"></a><span data-ttu-id="e1b92-109">Configurare l'ambiente ibrido per Skype meeting broadcast</span><span class="sxs-lookup"><span data-stu-id="e1b92-109">Configure your hybrid environment for Skype Meeting Broadcast</span></span>

<span data-ttu-id="e1b92-110">Per preparare l'ambiente per Skype meeting broadcast è necessario eseguire le operazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1b92-110">You'll need to do the following to prepare your environment for Skype Meeting Broadcast:</span></span>
  
- <span data-ttu-id="e1b92-111">Configurare la Federazione con le risorse di Skype for business online</span><span class="sxs-lookup"><span data-stu-id="e1b92-111">Configure federation with Skype for Business Online resources</span></span>
    
- <span data-ttu-id="e1b92-112">Configurare i domini federati SIP</span><span class="sxs-lookup"><span data-stu-id="e1b92-112">Configure SIP federated domains</span></span>
    
### <a name="configure-federation-with-skype-for-business-online-resources"></a><span data-ttu-id="e1b92-113">Configurare la Federazione con le risorse di Skype for business online</span><span class="sxs-lookup"><span data-stu-id="e1b92-113">Configure federation with Skype for Business Online resources</span></span>

<span data-ttu-id="e1b92-114">Per abilitare la Federazione con le risorse di Skype for business online, è necessario configurare l'accesso esterno per un provider federato SIP.</span><span class="sxs-lookup"><span data-stu-id="e1b92-114">To enable federation with Skype for Business Online resources, you need to configure External Access for a SIP Federated Provider.</span></span> <span data-ttu-id="e1b92-115">Per eseguire questa operazione, usare il pannello di controllo di Skype for Business Server seguire questa procedura:</span><span class="sxs-lookup"><span data-stu-id="e1b92-115">To do this by using the Skype for Business Server Control Panel follow these steps:</span></span>
  
1. <span data-ttu-id="e1b92-116">Avviare il pannello di controllo di Skype for Business Server e selezionare **accesso esterno** a sinistra.</span><span class="sxs-lookup"><span data-stu-id="e1b92-116">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="e1b92-117">Selezionare **provider federati SIP** e fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e1b92-117">Select **SIP Federated Providers** and click **New**.</span></span>
    
3. <span data-ttu-id="e1b92-118">Configurare il nuovo provider con le impostazioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1b92-118">Configure the new provider with the following settings:</span></span>
    
|||
|:-----|:-----|
|<span data-ttu-id="e1b92-119">**Abilitare le comunicazioni con questo provider:**</span><span class="sxs-lookup"><span data-stu-id="e1b92-119">**Enable communications with this provider:**</span></span> <br/> |<span data-ttu-id="e1b92-120">Selezionato</span><span class="sxs-lookup"><span data-stu-id="e1b92-120">Selected</span></span>  <br/> |
|<span data-ttu-id="e1b92-121">**Nome provider:**</span><span class="sxs-lookup"><span data-stu-id="e1b92-121">**Provider name:**</span></span> <br/> |<span data-ttu-id="e1b92-122">LyncOnlineResources</span><span class="sxs-lookup"><span data-stu-id="e1b92-122">LyncOnlineResources</span></span>  <br/> |
|<span data-ttu-id="e1b92-123">**Access Edge Services (FQDN):**</span><span class="sxs-lookup"><span data-stu-id="e1b92-123">**Access Edge service (FQDN):**</span></span> <br/> |<span data-ttu-id="e1b92-124">sipfed.resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1b92-124">sipfed.resources.lync.com</span></span>  <br/> |
|<span data-ttu-id="e1b92-125">**Livello di verifica predefinito:**</span><span class="sxs-lookup"><span data-stu-id="e1b92-125">**Default verification level:**</span></span> <br/> |<span data-ttu-id="e1b92-126">Consentire agli utenti di comunicare con tutti tramite questo provider.</span><span class="sxs-lookup"><span data-stu-id="e1b92-126">Allow users to communicate with everyone using this provider.</span></span>  <br/> |
   
<span data-ttu-id="e1b92-127">Puoi anche abilitare la Federazione con le risorse di Skype for business online eseguendo il cmdlet seguente in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="e1b92-127">You can also enable federation with Skype for Business Online resources by running the following cmdlet in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsHostingProvider -Identity LyncOnlineResources -ProxyFqdn sipfed.resources.lync.com -VerificationLevel AlwaysVerifiable -Enabled $True -EnabledSharedAddressSpace $True -HostsOCSUsers $True -IsLocal $False
```

### <a name="configure-sip-federated-domains"></a><span data-ttu-id="e1b92-128">Configurare i domini federati SIP</span><span class="sxs-lookup"><span data-stu-id="e1b92-128">Configure SIP federated domains</span></span>

<span data-ttu-id="e1b92-129">È quindi necessario aggiungere domini federati SIP all'elenco di domini consentiti.</span><span class="sxs-lookup"><span data-stu-id="e1b92-129">Next, you need to add SIP Federated domains to the allowed domain list.</span></span> <span data-ttu-id="e1b92-130">Ripetere questi passaggi per ogni dominio elencato, creando 4 nuovi domini federati SIP.</span><span class="sxs-lookup"><span data-stu-id="e1b92-130">Repeat these steps for each of the domains listed, creating 4 new SIP federated domains.</span></span> <span data-ttu-id="e1b92-131">Questi domini includono sono per i centri dati regionali usati in Skype for business online.</span><span class="sxs-lookup"><span data-stu-id="e1b92-131">These domains include are for the regional data centers used in Skype for Business Online.</span></span>
  
1. <span data-ttu-id="e1b92-132">Avviare il pannello di controllo di Skype for Business Server e selezionare **accesso esterno** a sinistra.</span><span class="sxs-lookup"><span data-stu-id="e1b92-132">Start the Skype for Business Server Control Panel and select **External Access** on the left.</span></span>
    
2. <span data-ttu-id="e1b92-133">Selezionare **domini federati SIP** e fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="e1b92-133">Select **SIP Federated Domains** and click **New**.</span></span>
    
3. <span data-ttu-id="e1b92-134">Per il **nome di dominio (o FQDN):** immettere il dominio, ripetendo questa procedura per ognuno dei domini seguenti:</span><span class="sxs-lookup"><span data-stu-id="e1b92-134">For the **Domain name (or FQDN):**, enter the domain, repeating this procedure for each of the following domains:</span></span>
    
   - <span data-ttu-id="e1b92-135">noammeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1b92-135">noammeetings.lync.com</span></span>
    
   - <span data-ttu-id="e1b92-136">emeameetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1b92-136">emeameetings.lync.com</span></span>
    
   - <span data-ttu-id="e1b92-137">apacmeetings.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1b92-137">apacmeetings.lync.com</span></span>
    
   - <span data-ttu-id="e1b92-138">resources.lync.com</span><span class="sxs-lookup"><span data-stu-id="e1b92-138">resources.lync.com</span></span>
    
<span data-ttu-id="e1b92-139">È anche possibile configurare l'accesso esterno per i domini federati SIP eseguendo i cmdlet seguenti in Skype for Business Server Management Shell:</span><span class="sxs-lookup"><span data-stu-id="e1b92-139">You can also configure the external access for SIP federated domains by running the following cmdlets in the Skype for Business Server Management Shell:</span></span>
  
```
New-CsAllowedDomain -Identity "noammeetings.lync.com"
New-CsAllowedDomain -Identity "emeameetings.lync.com"
New-CsAllowedDomain -Identity "apacmeetings.lync.com"
New-CsAllowedDomain -Identity "resources.lync.com"
```

<span data-ttu-id="e1b92-140">Dopo aver completato questi passaggi di configurazione, è possibile iniziare a usare Skype meeting broadcast nella distribuzione.</span><span class="sxs-lookup"><span data-stu-id="e1b92-140">Once you've completed these configuration steps you can start using Skype Meeting Broadcast in your deployment.</span></span> <span data-ttu-id="e1b92-141">Per altre informazioni su Skype meeting broadcast, vedere [cos'è un Skype meeting broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) e [Guida per gli amministratori di Skype meeting broadcast](https://go.microsoft.com/fwlink/?LinkId=617075).</span><span class="sxs-lookup"><span data-stu-id="e1b92-141">For more information about Skype Meeting Broadcast, see [What is a Skype Meeting Broadcast?](https://go.microsoft.com/fwlink/?LinkId=617071) and [Skype Meeting Broadcast Admin Guide](https://go.microsoft.com/fwlink/?LinkId=617075).</span></span>
  

