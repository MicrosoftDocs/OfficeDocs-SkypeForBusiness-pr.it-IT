---
title: 'Lync Server 2013: configurazione di collegamenti di sito di rete'
description: 'Lync Server 2013: configurazione di collegamenti di sito di rete.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network site links
ms:assetid: 7e9147ae-e727-46c8-8c1a-6c13201f09be
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521023(v=OCS.15)
ms:contentKeyID: 48184622
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 68b4ecce15b8f3ba5a5717c73a8f97f8a0633b58
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48572932"
---
# <a name="configuring-network-site-links-in-lync-server-2013"></a><span data-ttu-id="b51dc-103">Configurazione di collegamenti di sito di rete in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b51dc-103">Configuring network site links in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b51dc-104">_**Ultimo argomento modificato:** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="b51dc-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="b51dc-105">In una configurazione di controllo di ammissione di chiamata è possibile creare criteri intersito di rete che definiscono le limitazioni della larghezza di banda tra i siti collegati direttamente.</span><span class="sxs-lookup"><span data-stu-id="b51dc-105">Within a call admission control (CAC) configuration, you can create network inter-site policies that define bandwidth limitations between sites that are directly linked.</span></span> <span data-ttu-id="b51dc-106">Se due siti di rete condividono un collegamento diretto, è possibile definire dei limiti della larghezza di banda per le connessioni audio e video tra tali siti.</span><span class="sxs-lookup"><span data-stu-id="b51dc-106">When network sites share a direct link, bandwidth limitations for audio and video connections can be defined between those two sites.</span></span> <span data-ttu-id="b51dc-107">Non è possibile utilizzare il pannello di controllo di Lync Server per configurare i criteri sito di rete, è possibile eseguire questa operazione solo utilizzando i cmdlet di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b51dc-107">You cannot use the Lync Server Control Panel to configure network site policies, this can be done only by using cmdlets from the Lync Server Management Shell.</span></span> <span data-ttu-id="b51dc-108">È possibile creare, modificare e rimuovere un collegamento di sito di rete (noto anche come criterio tra siti di rete) da Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b51dc-108">You can create, modify, and remove a network site link (also known as a network inter-site policy) from the Lync Server Management Shell.</span></span>

<div>

## <a name="to-create-a-network-site-link"></a><span data-ttu-id="b51dc-109">Per creare un collegamento di sito di rete</span><span class="sxs-lookup"><span data-stu-id="b51dc-109">To create a network site link</span></span>

1.  <span data-ttu-id="b51dc-110">Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b51dc-110">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="b51dc-111">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b51dc-111">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b51dc-112">Al prompt dei comandi digitare il comando seguente, utilizzando valori validi per la configurazione in uso:</span><span class="sxs-lookup"><span data-stu-id="b51dc-112">From the command prompt, type the following command, substituting values that are valid for your configuration:</span></span>
    
        New-CsNetworkInterSitePolicy -Identity Reno_Portland -NetworkSiteID1 Reno -NetworkSiteID2 Portland -BWPolicyProfileID LowBWLimits
    
    <span data-ttu-id="b51dc-113">In questo esempio viene creato un nuovo collegamento di sito di rete denominato Reno \_ Portland che imposta le limitazioni della larghezza di banda tra i siti di rete Reno e Portland.</span><span class="sxs-lookup"><span data-stu-id="b51dc-113">This example creates a new network site link named Reno\_Portland that sets bandwidth limitations between the Reno and Portland network sites.</span></span> <span data-ttu-id="b51dc-114">Il profilo dei criteri di larghezza di banda e siti di rete deve essere già presente prima dell'esecuzione di questo comando.</span><span class="sxs-lookup"><span data-stu-id="b51dc-114">The network sites and the bandwidth policy profile must already exist before running this command.</span></span>

<span data-ttu-id="b51dc-115">Per le descrizioni dettagliate dei parametri, vedere [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b51dc-115">For detailed parameter descriptions, see [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span> <span data-ttu-id="b51dc-116">Per ottenere un elenco dei profili dei criteri di larghezza di banda che è possibile applicare al collegamento di sito di rete, chiamare il cmdlet **Get-CsNetworkBandwidthPolicyProfile**.</span><span class="sxs-lookup"><span data-stu-id="b51dc-116">To retrieve a list of bandwidth policy profiles that can be applied to the network site link, call the **Get-CsNetworkBandwidthPolicyProfile** cmdlet.</span></span> <span data-ttu-id="b51dc-117">Per informazioni dettagliate, vedere [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b51dc-117">For details, see [Get-CsNetworkBandwidthPolicyProfile](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-modify-a-network-site-link"></a><span data-ttu-id="b51dc-118">Per modificare un collegamento di sito di rete</span><span class="sxs-lookup"><span data-stu-id="b51dc-118">To modify a network site link</span></span>

1.  <span data-ttu-id="b51dc-119">Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b51dc-119">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="b51dc-120">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b51dc-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b51dc-121">Utilizzare il cmdlet **CsNetworkInterSitePolicy Set** per modificare le proprietà di un collegamento di sito di rete specifico.</span><span class="sxs-lookup"><span data-stu-id="b51dc-121">Use the **Set-CsNetworkInterSitePolicy** cmdlet to modify the properties of a given network site link.</span></span> <span data-ttu-id="b51dc-122">È possibile modificare uno dei siti connessi o entrambi ed è possibile modificare il profilo dei criteri di larghezza di banda associato al collegamento.</span><span class="sxs-lookup"><span data-stu-id="b51dc-122">You can modify either (or both) or the connected sites, and you can modify the bandwidth policy profile associated with the link.</span></span> <span data-ttu-id="b51dc-123">Di seguito è riportato un esempio di modifica del profilo dei criteri di larghezza di banda di un collegamento di sito denominato Reno \_ Portland:</span><span class="sxs-lookup"><span data-stu-id="b51dc-123">Here is an example of modifying the bandwidth policy profile of a site link named Reno\_Portland:</span></span>
    
        Set-CsNetworkInterSitePolicy -Identity Reno_Portland -BWPolicyProfileID HighBWLimits

<span data-ttu-id="b51dc-124">Per le descrizioni dettagliate dei parametri, vedere [set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b51dc-124">For detailed parameter descriptions, see [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="to-delete-a-network-site-link"></a><span data-ttu-id="b51dc-125">Per eliminare un collegamento di sito di rete</span><span class="sxs-lookup"><span data-stu-id="b51dc-125">To delete a network site link</span></span>

1.  <span data-ttu-id="b51dc-126">Accedere al computer in cui è installato Lync Server Management Shell come membro del gruppo RTCUniversalServerAdmins o con i diritti utente necessari, come descritto in [delegate Setup Permissions in Lync server 2013](lync-server-2013-delegate-setup-permissions.md).</span><span class="sxs-lookup"><span data-stu-id="b51dc-126">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="b51dc-127">Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.</span><span class="sxs-lookup"><span data-stu-id="b51dc-127">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="b51dc-128">Utilizzare il cmdlet **Remove-CsNetworkInterSitePolicy** per rimuovere un collegamento di sito di rete.</span><span class="sxs-lookup"><span data-stu-id="b51dc-128">Use the **Remove-CsNetworkInterSitePolicy** cmdlet to remove a network site link.</span></span> <span data-ttu-id="b51dc-129">Nell'esempio seguente viene eliminato il \_ collegamento al sito di rete di Reno Portland:</span><span class="sxs-lookup"><span data-stu-id="b51dc-129">The following example deletes the Reno\_Portland network site link:</span></span>
    
        Remove-CsNetworkInterSitePolicy -Identity Reno_Portland

<span data-ttu-id="b51dc-130">Per le descrizioni dettagliate dei parametri, vedere [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) nella documentazione di Lync Server Management Shell.</span><span class="sxs-lookup"><span data-stu-id="b51dc-130">For detailed parameter descriptions, see [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b51dc-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="b51dc-131">See Also</span></span>


[<span data-ttu-id="b51dc-132">Cmdlet per il controllo di ammissione di chiamata in Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b51dc-132">Call admission control cmdlets in Lync Server 2013</span></span>](https://docs.microsoft.com/powershell/module/skype/)  


[<span data-ttu-id="b51dc-133">New-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b51dc-133">New-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)  
[<span data-ttu-id="b51dc-134">Set-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b51dc-134">Set-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)  
[<span data-ttu-id="b51dc-135">Remove-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b51dc-135">Remove-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)  
[<span data-ttu-id="b51dc-136">Get-CsNetworkInterSitePolicy</span><span class="sxs-lookup"><span data-stu-id="b51dc-136">Get-CsNetworkInterSitePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)  
[<span data-ttu-id="b51dc-137">Get-CsNetworkBandwidthPolicyProfile</span><span class="sxs-lookup"><span data-stu-id="b51dc-137">Get-CsNetworkBandwidthPolicyProfile</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkBandwidthPolicyProfile)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

