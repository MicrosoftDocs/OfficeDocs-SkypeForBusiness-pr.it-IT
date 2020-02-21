---
title: 'Lync Server 2013: creare criteri di rete tra siti'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create network intersite policies
ms:assetid: b0714aae-55dc-4587-b718-34a03f596b22
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412844(v=OCS.15)
ms:contentKeyID: 48185148
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ae7024aa0a9f5c5734762ed0accb6e1dc723f2b9
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-intersite-policies-in-lync-server-2013"></a>Creare criteri intersito di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

Un *criterio intersito di rete* definisce limiti di larghezza di banda tra i siti collegati direttamente tramite WAN.

Per informazioni dettagliate, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:

  - [New-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterSitePolicy)

  - [Get-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterSitePolicy)

  - [Set-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterSitePolicy)

  - [Remove-CsNetworkInterSitePolicy](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterSitePolicy)

<div>


> [!IMPORTANT]  
> Un criterio intersito di rete è necessario <EM>solo</EM> se è presente un collegamento incrociato diretto tra due siti di rete.



</div>

Nell'area Nord America della topologia di esempio esiste un collegamento diretto tra i siti Reno e Albuquerque. Questi due siti richiedono un criterio intersito che applica un profilo dei criteri di larghezza di banda appropriato. Nell'esempio seguente viene applicato il\_profilo di collegamento di 20MB.

<div>

## <a name="to-create-a-network-intersite-policy"></a>Per creare un criterio intersito di rete

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire il cmdlet New-CsNetworkInterSitePolicy per creare i criteri intersito di rete e applicare un profilo dei criteri di larghezza di banda appropriato per due siti con collegamento incrociato diretto. Ad esempio, eseguire:
    
        New-CsNetworkInterSitePolicy -InterNetworkSitePolicyID Reno_Albuquerque -NetworkSiteID1 Reno -NetworkSiteID2 Albuquerque -BWPolicyProfileID 20Mb_Link

3.  Ripetere il passaggio 2 in base alle specifiche esigenze per creare i criteri intersito di rete per tutte le coppie di siti di rete con collegamento incrociato diretto.

</div>

</div>

<span> </span>

</div>

</div>

</div>

