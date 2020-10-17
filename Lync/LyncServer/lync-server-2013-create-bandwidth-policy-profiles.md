---
title: 'Lync Server 2013: creare profili di criteri di larghezza di banda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create bandwidth policy profiles
ms:assetid: a71881ef-b04a-465e-9abb-0577bfd182f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412785(v=OCS.15)
ms:contentKeyID: 48185086
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 173f63fce60215ca0bc68791b0bc051136d931a4
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48501703"
---
# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="8719b-102">Creare profili di criteri di larghezza di banda in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="8719b-102">Create bandwidth policy profiles in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8719b-103">_**Ultimo argomento modificato:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="8719b-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="8719b-p101">I *criteri di larghezza di banda* definiscono restrizioni per l'utilizzo della larghezza di banda per le modalità audio e video in tempo reale. I criteri di larghezza di banda vengono applicati a *profili di criteri di larghezza di banda*, che possono essere a loro volta applicati a più siti di rete per il controllo di ammissione di chiamata.</span><span class="sxs-lookup"><span data-stu-id="8719b-p101">*Bandwidth policies* define limitations on bandwidth usage for real-time audio and video modalities. Bandwidth policies are applied to *bandwidth policy profiles*, which can be applied to multiple network sites for call admission control.</span></span>

<span data-ttu-id="8719b-106">Per le linee guida relative ai limiti della larghezza di banda che è necessario impostare nella distribuzione di CAC, vedere [definizione dei requisiti per il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="8719b-106">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Defining your requirements for call admission control in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="8719b-107">Per informazioni dettagliate sull'utilizzo di criteri di larghezza di banda e profili di criteri, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="8719b-107">For details about working with bandwidth policies and policy profiles, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="8719b-108">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="8719b-108">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="8719b-109">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="8719b-109">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="8719b-110">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="8719b-110">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="8719b-111">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="8719b-111">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

<span data-ttu-id="8719b-112">I criteri di esempio creati nella procedura seguente impostano limiti per il traffico audio e il traffico video complessivi e per le sessioni audio e le sessioni video individuali.</span><span class="sxs-lookup"><span data-stu-id="8719b-112">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions.</span></span> <span data-ttu-id="8719b-113">Ad esempio, il profilo dei criteri di larghezza di banda del collegamento di 5 MB \_ imposta i seguenti limiti:</span><span class="sxs-lookup"><span data-stu-id="8719b-113">For example, the 5Mb\_Link bandwidth policy profile sets the following limits:</span></span>

  - <span data-ttu-id="8719b-114">Limite audio: 2.000 kbps</span><span class="sxs-lookup"><span data-stu-id="8719b-114">Audio Limit: 2,000 kbps</span></span>

  - <span data-ttu-id="8719b-115">Limite sessione audio: 200 kbps</span><span class="sxs-lookup"><span data-stu-id="8719b-115">Audio Session Limit: 200 kbps</span></span>

  - <span data-ttu-id="8719b-116">Limite video: 1.400 kbps</span><span class="sxs-lookup"><span data-stu-id="8719b-116">Video Limit: 1,400 kbps</span></span>

  - <span data-ttu-id="8719b-117">Limite sessione video: 700 kbps</span><span class="sxs-lookup"><span data-stu-id="8719b-117">Video Session Limit: 700 kbps</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="8719b-p103">Il valore minimo per il limite di una sessione audio è 40 kbps. Il valore minimo per il limite di una sessione video è 100 kbps.</span><span class="sxs-lookup"><span data-stu-id="8719b-p103">The minimum Audio Session Limit value is 40 kbps. The minimum Video Session Limit value is 100 kbps.</span></span>



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a><span data-ttu-id="8719b-120">Per creare profili di criteri di larghezza di banda mediante Management Shell</span><span class="sxs-lookup"><span data-stu-id="8719b-120">To create bandwidth policy profiles by using Management Shell</span></span>

1.  <span data-ttu-id="8719b-121">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="8719b-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="8719b-p104">Per ogni profilo di criteri di larghezza di banda che si desidera creare eseguire il cmdlet New-CsNetworkBandwidthPolicyProfile. Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="8719b-p104">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet. For example, run:</span></span>
    
       ```powershell
        New-CsNetworkBandwidthPolicyProfile -Identity 5Mb_Link -Description "BW profile for 5Mb links" -AudioBWLimit 2000 -AudioBWSessionLimit 200 -VideoBWLimit 1400  -VideoBWSessionLimit 700
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

</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a><span data-ttu-id="8719b-124">Per creare profili di criteri di larghezza di banda mediante il Pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="8719b-124">To create bandwidth policy profiles by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="8719b-125">Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="8719b-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="8719b-126">Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="8719b-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="8719b-127">Sulla barra di spostamento sinistra fare clic su **Configurazione rete**.</span><span class="sxs-lookup"><span data-stu-id="8719b-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="8719b-128">Fare clic sul pulsante di spostamento **Profilo criteri**.</span><span class="sxs-lookup"><span data-stu-id="8719b-128">Click the **Policy Profile** navigation button.</span></span>

4.  <span data-ttu-id="8719b-129">Fare clic su **Nuovo**.</span><span class="sxs-lookup"><span data-stu-id="8719b-129">Click **New**.</span></span>

5.  <span data-ttu-id="8719b-130">Nella pagina **Nuovo profilo criteri** fare clic su **Nome** e quindi digitare un nome per il profilo di criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="8719b-130">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>

6.  <span data-ttu-id="8719b-131">Fare clic su **Limite audio** e quindi digitare il numero massimo di kbps consentiti per tutte le sessioni audio nel loro insieme.</span><span class="sxs-lookup"><span data-stu-id="8719b-131">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>

7.  <span data-ttu-id="8719b-132">Fare clic su **Limite sessione audio** e quindi digitare il numero massimo di kbps consentiti per ogni singola sessione audio.</span><span class="sxs-lookup"><span data-stu-id="8719b-132">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>

8.  <span data-ttu-id="8719b-133">Fare clic su **Limite video** e quindi digitare il numero massimo di kbps consentiti per tutte le sessioni video nel loro insieme.</span><span class="sxs-lookup"><span data-stu-id="8719b-133">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>

9.  <span data-ttu-id="8719b-134">Fare clic su **Limite sessione video** e quindi digitare il numero massimo di kbps consentiti per ogni singola sessione video.</span><span class="sxs-lookup"><span data-stu-id="8719b-134">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>

10. <span data-ttu-id="8719b-135">Se si desidera, fare clic su **Descrizione** e quindi digitare ulteriori informazioni per descrivere il profilo di criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="8719b-135">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>

11. <span data-ttu-id="8719b-136">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="8719b-136">Click **Commit**.</span></span>

12. <span data-ttu-id="8719b-137">Per completare la creazione dei profili di criteri di larghezza di banda, ripetere i passaggi da 4 a 11 con le impostazioni per gli altri profili.</span><span class="sxs-lookup"><span data-stu-id="8719b-137">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

