---
title: 'Lync Server 2013: configurare i siti di rete per CAC'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure network sites for CAC
ms:assetid: afcea38f-5789-45ec-97af-c6e38364950c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412840(v=OCS.15)
ms:contentKeyID: 48185144
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0958c74d6f1ce587886b7a8456aee44381c00ff5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758364"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a>Configurare i siti di rete per CAC in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-05_

<div class=" ">


> [!IMPORTANT]  
> Se sono già stati creati siti di rete per il E9-1-1 o il bypass multimediale, è possibile modificare i siti di rete esistenti per applicare un profilo dei criteri di larghezza di banda usando il cmdlet <STRONG>Set-CsNetworkSite</STRONG> . Per un esempio di come modificare un sito di rete, vedere <A href="lync-server-2013-create-or-modify-a-network-site.md">creare o modificare un sito di rete in Lync Server 2013</A>.



</div>

I *siti di rete* sono gli uffici o le posizioni all'interno di ogni area di rete delle distribuzioni di controllo di ammissione di chiamata (CAC), E9-1-1 e bypass multimediale. Usare le procedure seguenti per creare siti di rete che si allineano ai siti di rete nella topologia di rete di esempio per CAC. Queste procedure illustrano come creare e configurare siti di rete vincolati dalla larghezza di banda WAN e quindi richiedono criteri di larghezza di banda che limitano il flusso di traffico audio o video in tempo reale.

Nell'esempio di distribuzione di CAC l'area Nord America include sei siti. Tre di questi siti sono vincolati da larghezza di banda WAN: Reno, Portland e Albuquerque. Gli altri tre siti, che *non* sono vincolati da larghezza di banda WAN: New York, Chicago e Detroit. Per un esempio di come creare o modificare gli altri siti di rete, vedere [creare o modificare un sito di rete in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).

Per visualizzare la topologia di rete di esempio, vedere [esempio: raccogliere i requisiti per il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) nella documentazione relativa alla pianificazione.

<div class=" ">


> [!NOTE]  
> Nella procedura seguente viene usato Lync Server Management Shell per creare un sito di rete. Per informazioni dettagliate sull'uso del pannello di controllo di Lync Server per creare un sito di rete, vedere <A href="lync-server-2013-create-or-modify-a-network-site.md">creare o modificare un sito di rete in Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a>Per creare siti di rete per il controllo dell'ammissione alle chiamate

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet **New-CsNetworkSite** per creare siti di rete e applicare un profilo dei criteri di larghezza di banda appropriato a ogni sito. Ad esempio, eseguire:
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  Per completare la creazione di siti di rete per l'intera topologia di esempio, ripetere il passaggio 2 per i siti di rete con vincoli di larghezza di banda nelle aree EMEA e APAC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

