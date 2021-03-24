---
title: Creare profili dei criteri di larghezza di banda in Skype for Business Server
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
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
description: Creare o modificare i criteri di larghezza di banda utilizzati VoIP aziendale controllo di ammissione di chiamata in Skype for Business Server.
ms.openlocfilehash: 9458c5576d2c89254c4ee6477ede33c010cb4a21
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/23/2021
ms.locfileid: "51093244"
---
# <a name="create-bandwidth-policy-profiles-in-skype-for-business-server"></a><span data-ttu-id="ccd9c-103">Creare profili dei criteri di larghezza di banda in Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ccd9c-103">Create bandwidth policy profiles in Skype for Business Server</span></span> 
 
<span data-ttu-id="ccd9c-104">Creare o modificare i criteri di larghezza di banda utilizzati VoIP aziendale controllo di ammissione di chiamata in Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ccd9c-104">Create or modify bandwidth policies, which are used by Enterprise Voice call admission control in Skype for Business Server.</span></span> 
  
<span data-ttu-id="ccd9c-105">I criteri di larghezza di banda definiscono restrizioni per l'utilizzo della larghezza di banda per le modalità audio e video in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="ccd9c-105">Bandwidth policies define limitations on bandwidth usage for real-time audio and video modalities.</span></span> <span data-ttu-id="ccd9c-106">I criteri di larghezza di banda vengono applicati ai profili dei criteri di larghezza di banda, che possono essere applicati a più siti di rete per il controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="ccd9c-106">Bandwidth policies are applied tobandwidth policy profiles, which can be applied to multiple network sites for call admission control.</span></span>
  
<span data-ttu-id="ccd9c-107">Per linee guida sui limiti di larghezza di banda da impostare nella distribuzione del servizio Controllo di ammissione di chiamata, vedere [Plan for call admission control in Skype for Business Server.](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md)</span><span class="sxs-lookup"><span data-stu-id="ccd9c-107">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Plan for call admission control in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/call-admission-control.md).</span></span>
  
<span data-ttu-id="ccd9c-p102">I criteri di esempio creati nella procedura seguente impostano limiti per il traffico audio e il traffico video complessivi e per le sessioni audio e le sessioni video individuali. Ad esempio, il profilo di criteri di larghezza di banda 5Mb_Link imposta i limiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="ccd9c-p102">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions. For example, the 5Mb_Link bandwidth policy profile sets the following limits:</span></span> 
  
- <span data-ttu-id="ccd9c-110">Limite audio: 2.000 kbps</span><span class="sxs-lookup"><span data-stu-id="ccd9c-110">Audio Limit: 2,000 kbps</span></span>
    
- <span data-ttu-id="ccd9c-111">Limite sessione audio: 200 kbps</span><span class="sxs-lookup"><span data-stu-id="ccd9c-111">Audio Session Limit: 200 kbps</span></span>
    
- <span data-ttu-id="ccd9c-112">Limite video: 1.400 kbps</span><span class="sxs-lookup"><span data-stu-id="ccd9c-112">Video Limit: 1,400 kbps</span></span>
    
- <span data-ttu-id="ccd9c-113">Limite sessione video: 700 kbps</span><span class="sxs-lookup"><span data-stu-id="ccd9c-113">Video Session Limit: 700 kbps</span></span>
    
> [!NOTE]
> <span data-ttu-id="ccd9c-p103">Il valore minimo per il limite di una sessione audio è 40 kbps. Il valore minimo per il limite di una sessione video è 100 kbps.</span><span class="sxs-lookup"><span data-stu-id="ccd9c-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span> 
  
### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-management-shell"></a><span data-ttu-id="ccd9c-116">Per creare profili dei criteri di larghezza di banda tramite Skype for Business Server Management Shell</span><span class="sxs-lookup"><span data-stu-id="ccd9c-116">To create bandwidth policy profiles by using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="ccd9c-117">Avviare Skype for Business Server Management Shell: fare clic sul pulsante **Start,** scegliere Tutti i **programmi,** **Skype for Business 2015** e quindi **Skype for Business Server Management Shell.**</span><span class="sxs-lookup"><span data-stu-id="ccd9c-117">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
2. <span data-ttu-id="ccd9c-118">Per ogni profilo di criteri di larghezza di banda che si desidera creare eseguire il cmdlet New-CsNetworkBandwidthPolicyProfile.</span><span class="sxs-lookup"><span data-stu-id="ccd9c-118">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="ccd9c-119">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="ccd9c-119">For example, run:</span></span>
    
   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400   -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 10Mb_Link -Description "BW profile for 10Mb links" -AudioBWLimit 4000 -AudioBWSessionLimit 200 -VideoBWLimit 2800 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 50Mb_Link -Description "BW profile for 50Mb links" -AudioBWLimit 20000 -AudioBWSessionLimit 200 -VideoBWLimit 14000 -VideoBWSessionLimit 700
   ```

   ```powershell
   New-CsNetworkBandwidthPolicyProfile -Identity 25Mb_Link -Description "BW profile for 25Mb links" -AudioBWLimit 10000 -AudioBWSessionLimit 200 -VideoBWLimit 7000 -VideoBWSessionLimit 700
   ```

### <a name="to-create-bandwidth-policy-profiles-by-using-skype-for-business-server-control-panel"></a><span data-ttu-id="ccd9c-120">Per creare profili di criteri di larghezza di banda tramite il Pannello di controllo di Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="ccd9c-120">To create bandwidth policy profiles by using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="ccd9c-121">Aprire il Pannello di controllo di Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="ccd9c-121">Open Skype for Business Server Control Panel.</span></span>
    
2. <span data-ttu-id="ccd9c-122">Sulla barra di spostamento sinistra fare clic su **Configurazione rete**.</span><span class="sxs-lookup"><span data-stu-id="ccd9c-122">In the left navigation bar, click **Network Configuration**.</span></span>
    
3. <span data-ttu-id="ccd9c-123">Fare clic sul pulsante di spostamento **Profilo criteri**.</span><span class="sxs-lookup"><span data-stu-id="ccd9c-123">Click the **Policy Profile** navigation button.</span></span>
    
4. <span data-ttu-id="ccd9c-124">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="ccd9c-124">Click **New**.</span></span>
    
5. <span data-ttu-id="ccd9c-125">Nella pagina **Nuovo profilo criteri** fare clic su **Nome** e quindi digitare un nome per il profilo di criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="ccd9c-125">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>
    
6. <span data-ttu-id="ccd9c-126">Fare clic su **Limite audio** e quindi digitare il numero massimo di kbps consentiti per tutte le sessioni audio nel loro insieme.</span><span class="sxs-lookup"><span data-stu-id="ccd9c-126">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>
    
7. <span data-ttu-id="ccd9c-127">Fare clic su **Limite sessione audio** e quindi digitare il numero massimo di kbps consentiti per ogni singola sessione audio.</span><span class="sxs-lookup"><span data-stu-id="ccd9c-127">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>
    
8. <span data-ttu-id="ccd9c-128">Fare clic su **Limite video** e quindi digitare il numero massimo di kbps consentiti per tutte le sessioni video nel loro insieme.</span><span class="sxs-lookup"><span data-stu-id="ccd9c-128">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>
    
9. <span data-ttu-id="ccd9c-129">Fare clic su **Limite sessione video** e quindi digitare il numero massimo di kbps consentiti per ogni singola sessione video.</span><span class="sxs-lookup"><span data-stu-id="ccd9c-129">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>
    
10. <span data-ttu-id="ccd9c-130">Se si desidera, fare clic su **Descrizione** e quindi digitare ulteriori informazioni per descrivere il profilo di criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="ccd9c-130">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>
    
11. <span data-ttu-id="ccd9c-131">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="ccd9c-131">Click **Commit**.</span></span>
    
12. <span data-ttu-id="ccd9c-132">Per completare la creazione dei profili di criteri di larghezza di banda, ripetere i passaggi da 4 a 11 con le impostazioni per gli altri profili.</span><span class="sxs-lookup"><span data-stu-id="ccd9c-132">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>
    
## <a name="see-also"></a><span data-ttu-id="ccd9c-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="ccd9c-133">See also</span></span>

[<span data-ttu-id="ccd9c-134">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="ccd9c-134">New-CsNetworkBandwidthPolicyProfile</span></span>](/powershell/module/skype/new-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="ccd9c-135">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="ccd9c-135">Get-CsNetworkBandwidthPolicyProfile</span></span>](/powershell/module/skype/get-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="ccd9c-136">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="ccd9c-136">Set-CsNetworkBandwidthPolicyProfile</span></span>](/powershell/module/skype/set-csnetworkbandwidthpolicyprofile?view=skype-ps)
  
[<span data-ttu-id="ccd9c-137">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="ccd9c-137">Remove-CsNetworkBandwidthPolicyProfile</span></span>](/powershell/module/skype/remove-csnetworkbandwidthpolicyprofile?view=skype-ps)