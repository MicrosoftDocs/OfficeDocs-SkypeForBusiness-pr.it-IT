---
title: 'Lync Server 2013: configurare le aree di rete per il servizio di controllo di ammissione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c029de2a7b6296dc81d365978c55d18c817e0894
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520543"
---
# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a>Configurare le aree di rete per il servizio di controllo di ammissione in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

<div>


> [!IMPORTANT]  
> Se sono state già create aree di rete per il servizio di emergenza (E9-1-1) o per il bypass multimediale, è possibile modificare le aree di rete esistenti aggiungendo impostazioni specifiche del servizio Controllo di ammissione di chiamata utilizzando il cmdlet <STRONG>Set-CsNetworkRegion</STRONG>. Per un esempio di come modificare un'area di rete, vedere <A href="lync-server-2013-create-or-modify-a-network-region.md">creare o modificare un'area di rete in Lync Server 2013</A>.



</div>

Le *aree di rete* sono hub o backbone di rete che si utilizzano nella configurazione del servizio Controllo di ammissione di chiamata, nel servizio di emergenza (E9-1-1) e nel bypass multimediale. Eseguire la procedura seguente per creare aree di rete allineate a quelle dell'esempio di topologia di rete per il servizio Controllo di ammissione di chiamata. Per visualizzare la topologia di rete di esempio, vedere [esempio: raccogliere i requisiti per il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) nella documentazione relativa alla pianificazione.

L'esempio di topologia di rete per il servizio Controllo di ammissione di chiamata include tre aree: Nord America, EMEA e APAC. Per ogni area è specificato un sito centrale. Per il Nord America, il sito centrale designato è denominato CHICAGO. Nella procedura seguente è illustrato un esempio di come utilizzare il cmdlet **New-CsNetworkRegion** per creare l'area del Nord America.

<div>


> [!NOTE]  
> Nella procedura seguente, Lync Server Management Shell viene utilizzato per creare un'area di rete. Per informazioni dettagliate sull'utilizzo del pannello di controllo di Lync Server per creare un'area di rete, vedere <A href="lync-server-2013-create-or-modify-a-network-region.md">creare o modificare un'area di rete in Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a>Per creare un'area di reste per il servizio Controllo di ammissione di chiamata

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire il cmdlet **New-CsNetworkRegion** per ogni area che è necessario creare. Ad esempio, per creare l'area del Nord America, eseguire:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  Ripetere il passaggio 2 per creare le aree di rete di EMEA e APAC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

