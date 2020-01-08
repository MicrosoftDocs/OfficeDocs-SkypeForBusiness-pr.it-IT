---
title: 'Lync Server 2013: configurazione di collegamenti ai siti di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd0ddd5e28cd37cd31e28e5c6427b9b700b5a4c9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977431"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-site-links-in-lync-server-2013"></a><span data-ttu-id="72b38-102">Configurazione di collegamenti ai siti di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72b38-102">Configuring network site links in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="72b38-103">_**Argomento Ultima modifica:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="72b38-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="72b38-104">All'interno di una configurazione di controllo di ammissione chiamata (CAC), è possibile creare criteri intersito di rete che definiscono le limitazioni della larghezza di banda tra i siti direttamente collegati.</span><span class="sxs-lookup"><span data-stu-id="72b38-104">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="72b38-105">Quando i siti di rete condividono un collegamento diretto, è possibile definire limitazioni della larghezza di banda per le connessioni audio e video tra questi due siti.</span><span class="sxs-lookup"><span data-stu-id="72b38-105">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="72b38-106">Non è possibile usare il pannello di controllo di Lync Server per configurare i criteri del sito di rete, questo può essere eseguito solo usando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="72b38-106">You cannot use the Lync Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="72b38-107">È possibile creare, modificare e rimuovere un collegamento al sito di rete (noto anche come criterio intersito di rete) da Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="72b38-107">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Lync Server Management Shell.</span></span>

<div>

## <a name="to-create-a-network-site-link"></a><span data-ttu-id="72b38-108">Per creare un collegamento al sito di rete</span><span class="sxs-lookup"><span data-stu-id="72b38-108">To create a network site link</span></span>

1.  <span data-ttu-id="72b38-109">Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di [configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="72b38-109">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="72b38-110">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="72b38-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="72b38-111">Dal prompt dei comandi digitare il comando seguente, sostituendo i valori validi per la configurazione:</span><span class="sxs-lookup"><span data-stu-id="72b38-111">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="72b38-112">Questo esempio crea un nuovo collegamento di sito di rete\_denominato Reno Portland che imposta le limitazioni della larghezza di banda tra i siti di rete Reno e Portland.</span><span class="sxs-lookup"><span data-stu-id="72b38-112">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="72b38-113">I siti di rete e il profilo dei criteri di larghezza di banda devono già esistere prima di eseguire questo comando.</span><span class="sxs-lookup"><span data-stu-id="72b38-113">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="72b38-114">Per una descrizione dettagliata dei parametri, vedere [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="72b38-114">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="72b38-115">Per recuperare un elenco di profili dei criteri di larghezza di banda che possono essere applicati al collegamento al sito di rete, chiama il cmdlet **Get-CsNetworkBandwidthPolicyProfile** .</span><span class="sxs-lookup"><span data-stu-id="72b38-115">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="72b38-116">Per informazioni dettagliate, vedere [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="72b38-116">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-link"></a><span data-ttu-id="72b38-117">Per modificare un collegamento al sito di rete</span><span class="sxs-lookup"><span data-stu-id="72b38-117">To modify a network site link</span></span>

1.  <span data-ttu-id="72b38-118">Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di [configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="72b38-118">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="72b38-119">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="72b38-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="72b38-120">Utilizzare il cmdlet **set-CsNetworkInterSitePolicy** per modificare le proprietà di un collegamento al sito di rete specifico.</span><span class="sxs-lookup"><span data-stu-id="72b38-120">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="72b38-121">È possibile modificare uno o entrambi i siti connessi e modificare il profilo dei criteri di larghezza di banda associato al collegamento.</span><span class="sxs-lookup"><span data-stu-id="72b38-121">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="72b38-122">Ecco un esempio di modifica del profilo dei criteri di larghezza di banda di un collegamento\_di sito denominato Reno Portland:</span><span class="sxs-lookup"><span data-stu-id="72b38-122">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="72b38-123">Per una descrizione dettagliata dei parametri, vedere [set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="72b38-123">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site-link"></a><span data-ttu-id="72b38-124">Per eliminare un collegamento al sito di rete</span><span class="sxs-lookup"><span data-stu-id="72b38-124">To delete a network site link</span></span>

1.  <span data-ttu-id="72b38-125">Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in autorizzazioni di [configurazione delegate in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="72b38-125">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="72b38-126">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="72b38-126">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="72b38-127">Utilizzare il cmdlet **Remove-CsNetworkInterSitePolicy** per rimuovere un collegamento al sito di rete.</span><span class="sxs-lookup"><span data-stu-id="72b38-127">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="72b38-128">L'esempio seguente elimina il collegamento\_al sito network di Reno Portland:</span><span class="sxs-lookup"><span data-stu-id="72b38-128">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="72b38-129">Per una descrizione dettagliata dei parametri, vedere [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="72b38-129">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="72b38-130">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="72b38-130">See Also</span></span>


[<span data-ttu-id="72b38-131">Cmdlet di controllo dell'ammissione alle chiamate in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="72b38-131">Call admission control cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/)  


[<span data-ttu-id="72b38-132">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="72b38-132">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[<span data-ttu-id="72b38-133">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="72b38-133">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[<span data-ttu-id="72b38-134">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="72b38-134">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[<span data-ttu-id="72b38-135">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="72b38-135">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[<span data-ttu-id="72b38-136">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="72b38-136">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

