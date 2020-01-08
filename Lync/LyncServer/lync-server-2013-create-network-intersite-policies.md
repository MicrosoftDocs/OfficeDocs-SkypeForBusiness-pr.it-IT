---
title: 'Lync Server 2013: creare criteri di rete tra siti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b6309b27ddedb37c2c38e7d40e74e427f61b904a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981919"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a>Creare criteri di intersito di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

Un *criterio intersito di rete* definisce le limitazioni della larghezza di banda tra i siti con collegamenti WAN diretti tra di essi.

Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:

  - [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> È necessario un criterio intersito di rete <EM>solo</EM> se esiste un collegamento incrociato diretto tra due siti di rete.



</div>

Nella topologia di esempio dell'area Nord America esiste un collegamento diretto tra i siti Reno e Albuquerque. Questi due siti richiedono un criterio intersito che applica un profilo dei criteri di larghezza di banda appropriato. L'esempio seguente applica il profilo\_del collegamento 20MB.

<div>

## <a name="to-create-a-network-intersite-policy"></a>Per creare un criterio intersito di rete

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet New-CsNetworkInterSitePolicy per creare criteri di intersito di rete e applicare un profilo dei criteri di larghezza di banda appropriato per due siti che hanno un collegamento incrociato diretto. Ad esempio, eseguire:
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  Ripetere il passaggio 2 in base alle esigenze per creare criteri di intersito di rete per tutte le coppie di siti di rete con un collegamento incrociato diretto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

