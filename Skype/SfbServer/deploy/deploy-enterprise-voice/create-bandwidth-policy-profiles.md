---
title: Creare profili dei criteri di larghezza di banda in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Creare o modificare i criteri di larghezza di banda usati dal controllo di ammissione alle chiamate vocali aziendali in Skype for Business Server.
ms.openlocfilehash: c7fecafe5f036405088a3c6c62b70774b779e266
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36191342"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="7c6c5-103">Creare profili dei criteri di larghezza di banda in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7c6c5-103">Create bandwidth policy profiles in Skype for Business Server</span></span> 
 
<span data-ttu-id="7c6c5-104">Creare o modificare i criteri di larghezza di banda usati dal controllo di ammissione alle chiamate vocali aziendali in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7c6c5-104">Create or modify bandwidth policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="7c6c5-105">I criteri di larghezza di banda definiscono le limitazioni dell'utilizzo della larghezza di banda per le modalità audio e video in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="7c6c5-105">Bandwidth policies define limitations on bandwidth usage for real-time audio and video modalities.</span></span> <span data-ttu-id="7c6c5-106">I criteri di larghezza di banda vengono applicati ai profili dei criteri di larghezza di banda, che possono essere applicati a più siti di rete per il controllo ammissione chiamata.</span><span class="sxs-lookup"><span data-stu-id="7c6c5-106">Bandwidth policies are applied tobandwidth policy profiles, which can be applied to multiple network sites for call admission control.</span></span>
  
<span data-ttu-id="7c6c5-107">Per linee guida sui limiti della larghezza di banda da impostare nella distribuzione di CAC, vedere [pianificare il controllo dell'ammissione alle chiamate in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span><span class="sxs-lookup"><span data-stu-id="7c6c5-107">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
<span data-ttu-id="7c6c5-108">I criteri di esempio creati nella procedura seguente impostano i limiti per il traffico audio globale, le singole sessioni audio, il traffico video complessivo e le singole sessioni video.</span><span class="sxs-lookup"><span data-stu-id="7c6c5-108">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions.</span></span> <span data-ttu-id="7c6c5-109">Ad esempio, il profilo dei criteri di larghezza di banda 5Mb_Link imposta i limiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7c6c5-109">For example, the 5Mb_Link bandwidth policy profile sets the following limits:</span></span> 
  
- <span data-ttu-id="7c6c5-110">Limite audio: 2.000 Kbps</span><span class="sxs-lookup"><span data-stu-id="7c6c5-110">Audio Limit: 2,000 kbps</span></span>
    
- <span data-ttu-id="7c6c5-111">Limite della sessione audio: 200 Kbps</span><span class="sxs-lookup"><span data-stu-id="7c6c5-111">Audio Session Limit: 200 kbps</span></span>
    
- <span data-ttu-id="7c6c5-112">Limite video: 1.400 kbps</span><span class="sxs-lookup"><span data-stu-id="7c6c5-112">Video Limit: 1,400 kbps</span></span>
    
- <span data-ttu-id="7c6c5-113">Limite sessione video: 700 Kbps</span><span class="sxs-lookup"><span data-stu-id="7c6c5-113">Video Session Limit: 700 kbps</span></span>
    
> [!NOTE]
> <span data-ttu-id="7c6c5-114">Il valore limite minimo della sessione audio è 40 Kbps.</span><span class="sxs-lookup"><span data-stu-id="7c6c5-114">The minimum Audio Session Limit value is 40 kbps.</span></span> <span data-ttu-id="7c6c5-115">Il valore limite minimo della sessione video è di 100 kbps.</span><span class="sxs-lookup"><span data-stu-id="7c6c5-115">The minimum Video Session Limit value is 100 kbps.</span></span> 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="7c6c5-116">Per creare profili dei criteri di larghezza di banda tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="7c6c5-116">To create bandwidth policy profiles by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="7c6c5-117">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Skype for business 2015**e quindi fare clic su **Skype for Business Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="7c6c5-117">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="7c6c5-118">Per ogni profilo dei criteri di larghezza di banda che si vuole creare, eseguire il cmdlet New-CsNetworkBandwidthPolicyProfile.</span><span class="sxs-lookup"><span data-stu-id="7c6c5-118">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="7c6c5-119">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="7c6c5-119">For example, run:</span></span>
    
   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="7c6c5-120">Per creare profili dei criteri di larghezza di banda tramite il pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="7c6c5-120">To create bandwidth policy profiles by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="7c6c5-121">Aprire il pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="7c6c5-121">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="7c6c5-122">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="7c6c5-122">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="7c6c5-123">Fare clic sul pulsante di spostamento del **profilo dei criteri** .</span><span class="sxs-lookup"><span data-stu-id="7c6c5-123">Click the **Policy Profile** navigation button.</span></span>
    
4. <span data-ttu-id="7c6c5-124">Fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="7c6c5-124">Click **New**.</span></span>
    
5. <span data-ttu-id="7c6c5-125">Nella pagina **nuovo profilo dei criteri** fare clic su **nome** e quindi digitare un nome per il profilo dei criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="7c6c5-125">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>
    
6. <span data-ttu-id="7c6c5-126">Fare clic su **limite audio**e quindi digitare il numero massimo di kbps da consentire per tutte le sessioni audio combinate.</span><span class="sxs-lookup"><span data-stu-id="7c6c5-126">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>
    
7. <span data-ttu-id="7c6c5-127">Fare clic su **limite sessione audio**e quindi digitare il numero massimo di kbps da consentire per ogni singola sessione audio.</span><span class="sxs-lookup"><span data-stu-id="7c6c5-127">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>
    
8. <span data-ttu-id="7c6c5-128">Fare clic su **limite video**e quindi digitare il numero massimo di kbps da consentire per tutte le sessioni video combinate.</span><span class="sxs-lookup"><span data-stu-id="7c6c5-128">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>
    
9. <span data-ttu-id="7c6c5-129">Fare clic su **limite sessione video**e quindi digitare il numero massimo di kbps da consentire per ogni singola sessione video.</span><span class="sxs-lookup"><span data-stu-id="7c6c5-129">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>
    
10. <span data-ttu-id="7c6c5-130">Facoltativamente, fare clic su **Descrizione**e quindi digitare altre informazioni per descrivere il profilo dei criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="7c6c5-130">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>
    
11. <span data-ttu-id="7c6c5-131">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="7c6c5-131">Click **Commit**.</span></span>
    
12. <span data-ttu-id="7c6c5-132">Per completare la creazione di profili dei criteri di larghezza di banda per la topologia, ripetere i passaggi da 4 a 11 con impostazioni per altri profili dei criteri di larghezza</span><span class="sxs-lookup"><span data-stu-id="7c6c5-132">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="7c6c5-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7c6c5-133">See also</span></span>

[<span data-ttu-id="7c6c5-134">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="7c6c5-134">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="7c6c5-135">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="7c6c5-135">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="7c6c5-136">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="7c6c5-136">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="7c6c5-137">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="7c6c5-137">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)
