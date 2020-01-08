---
title: 'Lync Server 2013: configurare le aree di rete per CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure network regions for CAC
ms:assetid: ea3ff988-dd5a-4bc4-bec5-39a0fb09793a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399051(v=OCS.15)
ms:contentKeyID: 48185906
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 773bae62596143c0e974ae02f2bd643172a99ac3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981189"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-regions-for-cac-in-lync-server-2013"></a>Configurare le aree di rete per CAC in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

<div>


> [!IMPORTANT]  
> Se sono già state create aree di rete per il E9-1-1 o il bypass multimediale, è possibile modificare le aree di rete esistenti aggiungendo le impostazioni specifiche del controllo di ammissione di chiamata tramite il cmdlet <STRONG>Set-CsNetworkRegion</STRONG> . Per un esempio di come modificare un'area geografica di rete, vedere <A href="lync-server-2013-create-or-modify-a-network-region.md">creare o modificare un'area di rete in Lync Server 2013</A>.



</div>

Le *aree di rete* sono gli hub di rete o le backbone usate per la configurazione di CAC, E9-1-1 e bypass multimediale. Usare la procedura seguente per creare aree di rete che si allineano alle aree di rete nella topologia di rete di esempio per CAC. Per visualizzare la topologia di rete di esempio, vedere [esempio: raccogliere i requisiti per il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) nella documentazione relativa alla pianificazione.

La topologia di rete di esempio per CAC include tre aree geografiche: Nord America, EMEA e APAC. Ogni area geografica ha un sito centrale specificato. Per l'area Nord America, il sito centrale designato è denominato CHICAGO. La procedura seguente mostra un esempio di come usare il cmdlet **New-CsNetworkRegion** per creare l'area Nord America.

<div>


> [!NOTE]  
> Nella procedura seguente viene usato Lync Server Management Shell per creare un'area di rete. Per informazioni dettagliate sull'uso del pannello di controllo di Lync Server per creare un'area di rete, vedere <A href="lync-server-2013-create-or-modify-a-network-region.md">creare o modificare un'area di rete in Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-a-network-region-for-call-admission-control"></a>Per creare un'area di rete per il controllo dell'ammissione alle chiamate

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Per ogni area geografica che è necessario creare, eseguire il cmdlet **New-CsNetworkRegion** . Ad esempio, per creare l'area Nord America, eseguire:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"

3.  Ripetere il passaggio 2 per creare le aree di rete, EMEA e APAC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

