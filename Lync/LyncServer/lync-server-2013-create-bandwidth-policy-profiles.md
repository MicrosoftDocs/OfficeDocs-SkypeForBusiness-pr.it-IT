---
title: 'Lync Server 2013: creare profili dei criteri di larghezza di banda'
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
ms.openlocfilehash: 7d3eef3ea6dfb349f0f712c1127adb8310d90c27
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726336"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-bandwidth-policy-profiles-in-lync-server-2013"></a><span data-ttu-id="cb89c-102">Creare profili dei criteri di larghezza di banda in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="cb89c-102">Create bandwidth policy profiles in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cb89c-103">_**Argomento Ultima modifica:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="cb89c-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="cb89c-104">I *criteri di larghezza di banda* definiscono le limitazioni dell'utilizzo della larghezza di banda per le modalità audio e video in tempo reale.</span><span class="sxs-lookup"><span data-stu-id="cb89c-104">*Bandwidth policies* define limitations on bandwidth usage for real-time audio and video modalities.</span></span> <span data-ttu-id="cb89c-105">I criteri di larghezza di banda vengono applicati ai *profili dei criteri di larghezza di banda*, che possono essere applicati a più siti di rete per il controllo ammissione chiamata.</span><span class="sxs-lookup"><span data-stu-id="cb89c-105">Bandwidth policies are applied to *bandwidth policy profiles*, which can be applied to multiple network sites for call admission control.</span></span>

<span data-ttu-id="cb89c-106">Per le linee guida sui limiti della larghezza di banda da impostare nella distribuzione di CAC, vedere [definizione dei requisiti per il controllo dell'ammissione delle chiamate in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) nella documentazione relativa alla pianificazione.</span><span class="sxs-lookup"><span data-stu-id="cb89c-106">For guidelines about what bandwidth limits you should set in your CAC deployment, see [Defining your requirements for call admission control in Lync Server 2013](lync-server-2013-defining-your-requirements-for-call-admission-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="cb89c-107">Per informazioni dettagliate su come usare i criteri di larghezza di banda e i profili dei criteri, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:</span><span class="sxs-lookup"><span data-stu-id="cb89c-107">For details about working with bandwidth policies and policy profiles, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - [<span data-ttu-id="cb89c-108">New-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="cb89c-108">New-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="cb89c-109">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="cb89c-109">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="cb89c-110">Set-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="cb89c-110">Set-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkBandwidthPolicyProfile)

  - [<span data-ttu-id="cb89c-111">Remove-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="cb89c-111">Remove-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkBandwidthPolicyProfile)

<span data-ttu-id="cb89c-112">I criteri di esempio creati nella procedura seguente impostano i limiti per il traffico audio globale, le singole sessioni audio, il traffico video complessivo e le singole sessioni video.</span><span class="sxs-lookup"><span data-stu-id="cb89c-112">The example policies created in the following procedure set limits for overall audio traffic, individual audio sessions, overall video traffic, and individual video sessions.</span></span> <span data-ttu-id="cb89c-113">Ad esempio, il profilo\_dei criteri di larghezza di banda collegamento di MB imposta i limiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="cb89c-113">For example, the 5Mb\_Link bandwidth policy profile sets the following limits:</span></span>

  - <span data-ttu-id="cb89c-114">Limite audio: 2.000 Kbps</span><span class="sxs-lookup"><span data-stu-id="cb89c-114">Audio Limit: 2,000 kbps</span></span>

  - <span data-ttu-id="cb89c-115">Limite della sessione audio: 200 Kbps</span><span class="sxs-lookup"><span data-stu-id="cb89c-115">Audio Session Limit: 200 kbps</span></span>

  - <span data-ttu-id="cb89c-116">Limite video: 1.400 kbps</span><span class="sxs-lookup"><span data-stu-id="cb89c-116">Video Limit: 1,400 kbps</span></span>

  - <span data-ttu-id="cb89c-117">Limite sessione video: 700 Kbps</span><span class="sxs-lookup"><span data-stu-id="cb89c-117">Video Session Limit: 700 kbps</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="cb89c-118">Il valore limite minimo della sessione audio è 40 Kbps.</span><span class="sxs-lookup"><span data-stu-id="cb89c-118">The minimum Audio Session Limit value is 40 kbps.</span></span> <span data-ttu-id="cb89c-119">Il valore limite minimo della sessione video è di 100 kbps.</span><span class="sxs-lookup"><span data-stu-id="cb89c-119">The minimum Video Session Limit value is 100 kbps.</span></span>



</div>

<div>

## <a name="to-create-bandwidth-policy-profiles-by-using-management-shell"></a><span data-ttu-id="cb89c-120">Per creare profili dei criteri di larghezza di banda tramite Management Shell</span><span class="sxs-lookup"><span data-stu-id="cb89c-120">To create bandwidth policy profiles by using Management Shell</span></span>

1.  <span data-ttu-id="cb89c-121">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="cb89c-121">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="cb89c-122">Per ogni profilo dei criteri di larghezza di banda che si vuole creare, eseguire il cmdlet New-CsNetworkBandwidthPolicyProfile.</span><span class="sxs-lookup"><span data-stu-id="cb89c-122">For each bandwidth policy profile that you want to create, run the New-CsNetworkBandwidthPolicyProfile cmdlet.</span></span> <span data-ttu-id="cb89c-123">Ad esempio, eseguire:</span><span class="sxs-lookup"><span data-stu-id="cb89c-123">For example, run:</span></span>
    
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

## <a name="to-create-bandwidth-policy-profiles-by-using-lync-server-control-panel"></a><span data-ttu-id="cb89c-124">Per creare profili dei criteri di larghezza di banda tramite il pannello di controllo di Lync Server</span><span class="sxs-lookup"><span data-stu-id="cb89c-124">To create bandwidth policy profiles by using Lync Server Control Panel</span></span>

1.  <span data-ttu-id="cb89c-125">Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server.</span><span class="sxs-lookup"><span data-stu-id="cb89c-125">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="cb89c-126">Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).</span><span class="sxs-lookup"><span data-stu-id="cb89c-126">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

2.  <span data-ttu-id="cb89c-127">Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.</span><span class="sxs-lookup"><span data-stu-id="cb89c-127">In the left navigation bar, click **Network Configuration**.</span></span>

3.  <span data-ttu-id="cb89c-128">Fare clic sul pulsante di spostamento del **profilo dei criteri** .</span><span class="sxs-lookup"><span data-stu-id="cb89c-128">Click the **Policy Profile** navigation button.</span></span>

4.  <span data-ttu-id="cb89c-129">Fare clic su **nuovo**.</span><span class="sxs-lookup"><span data-stu-id="cb89c-129">Click **New**.</span></span>

5.  <span data-ttu-id="cb89c-130">Nella pagina **nuovo profilo dei criteri** fare clic su **nome** e quindi digitare un nome per il profilo dei criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="cb89c-130">On the **New Policy Profile** page, click **Name** and then type a name for the bandwidth policy profile.</span></span>

6.  <span data-ttu-id="cb89c-131">Fare clic su **limite audio**e quindi digitare il numero massimo di kbps da consentire per tutte le sessioni audio combinate.</span><span class="sxs-lookup"><span data-stu-id="cb89c-131">Click **Audio limit**, and then type in the maximum number of kbps to allow for all audio sessions combined.</span></span>

7.  <span data-ttu-id="cb89c-132">Fare clic su **limite sessione audio**e quindi digitare il numero massimo di kbps da consentire per ogni singola sessione audio.</span><span class="sxs-lookup"><span data-stu-id="cb89c-132">Click **Audio session limit**, and then type in the maximum number of kbps to allow for each individual audio session.</span></span>

8.  <span data-ttu-id="cb89c-133">Fare clic su **limite video**e quindi digitare il numero massimo di kbps da consentire per tutte le sessioni video combinate.</span><span class="sxs-lookup"><span data-stu-id="cb89c-133">Click **Video limit**, and then type in the maximum number of kbps to allow for all video sessions combined.</span></span>

9.  <span data-ttu-id="cb89c-134">Fare clic su **limite sessione video**e quindi digitare il numero massimo di kbps da consentire per ogni singola sessione video.</span><span class="sxs-lookup"><span data-stu-id="cb89c-134">Click **Video session limit**, and then type in the maximum number of kbps to allow for each individual video session.</span></span>

10. <span data-ttu-id="cb89c-135">Facoltativamente, fare clic su **Descrizione**e quindi digitare altre informazioni per descrivere il profilo dei criteri di larghezza di banda.</span><span class="sxs-lookup"><span data-stu-id="cb89c-135">Optionally, click **Description**, and then type additional information to describe this bandwidth policy profile.</span></span>

11. <span data-ttu-id="cb89c-136">Fare clic su **Commit**.</span><span class="sxs-lookup"><span data-stu-id="cb89c-136">Click **Commit**.</span></span>

12. <span data-ttu-id="cb89c-137">Per completare la creazione di profili dei criteri di larghezza di banda per la topologia, ripetere i passaggi da 4 a 11 con impostazioni per altri profili dei criteri di larghezza</span><span class="sxs-lookup"><span data-stu-id="cb89c-137">To finish creating bandwidth policy profiles for your topology, repeat steps 4 through 11 with settings for other bandwidth policy profiles.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

