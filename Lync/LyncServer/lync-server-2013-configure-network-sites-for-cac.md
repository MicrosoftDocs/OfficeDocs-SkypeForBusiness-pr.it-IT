---
title: 'Lync Server 2013: configurare i siti di rete per il servizio di controllo di ammissione'
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
ms.openlocfilehash: e24932b23b1a9168ed64279f98db125f06ad0e2e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48520523"
---
# <a name="configure-network-sites-for-cac-in-lync-server-2013"></a>Configurazione dei siti di rete per il servizio di controllo di ammissione in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-05_

<div class=" ">


> [!IMPORTANT]  
> Se sono stati già creati siti di rete per il servizio per chiamate di emergenza (E9-1-1) o per il bypass multimediale, è possibile modificare i siti di rete esistenti per applicare un profilo di criteri di larghezza di banda utilizzando il cmdlet <STRONG>Set-CsNetworkSite</STRONG>. Per un esempio di come modificare un sito di rete, vedere <A href="lync-server-2013-create-or-modify-a-network-site.md">creare o modificare un sito di rete in Lync Server 2013</A>.



</div>

I *siti di rete* sono gli uffici o le postazioni in ogni area di rete delle distribuzioni del servizio Controllo di ammissione di chiamata (CAC), del servizio per chiamate di emergenza E9-1-1 e del bypass multimediale. Utilizzare le procedure seguenti per creare siti di rete da allineare ai siti di rete nella topologia di rete di esempio per il servizio Controllo di ammissione di chiamata. In queste procedure viene illustrato come creare e configurare siti di rete vincolati dalla larghezza di banda WAN che quindi richiedono criteri di larghezza di banda per limitare il flusso di traffico audio o video in tempo reale.

Nella distribuzione di esempio del servizio Controllo di ammissione di chiamata, il Nord America ha sei siti. Tre di questi siti sono vincolati dalla larghezza di banda WAN: Reno, Portland e Albuquerque. Gli altri tre siti, *non* vincolati dalla larghezza di banda WAN, sono: New York, Chicago e Detroit. Per un esempio di come creare o modificare gli altri siti di rete, vedere [creare o modificare un sito di rete in Lync Server 2013](lync-server-2013-create-or-modify-a-network-site.md).

Per visualizzare la topologia di rete di esempio, vedere [esempio: raccogliere i requisiti per il controllo di ammissione di chiamata in Lync Server 2013](lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md) nella documentazione relativa alla pianificazione.

<div class=" ">


> [!NOTE]  
> Nella procedura seguente, Lync Server Management Shell viene utilizzato per creare un sito di rete. Per informazioni dettagliate sull'utilizzo del pannello di controllo di Lync Server per creare un sito di rete, vedere <A href="lync-server-2013-create-or-modify-a-network-site.md">creare o modificare un sito di rete in Lync Server 2013</A>.



</div>

<div>

## <a name="to-create-network-sites-for-call-admission-control"></a>Per creare siti di rete per il servizio Controllo di ammissione di chiamata

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire il cmdlet **New-CsNetworkSite** per creare i siti di rete e applicare un profilo di criteri di larghezza di banda appropriato a ogni sito. Ad esempio, eseguire:
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Reno -Description "NA:Branch office for sales force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 10MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Portland -Description "NA:Branch office for marketing force" -NetworkRegionID NorthAmerica -BWPolicyProfileID 5MB_Link
       ```
    
       ```powershell
        New-CsNetworkSite -NetworkSiteID Albuquerque -Description "NA:Branch office for SouthWest sales" -NetworkRegionID EMEA -BWPolicyProfileID 10MB_Link
       ```

3.  Per completare la creazione dei siti di rete per l'intera topologia di esempio, ripetere il passaggio 2 per i siti di rete vincolati dalla larghezza di banda nelle aree EMEA e APAC.

</div>

</div>

<span> </span>

</div>

</div>

</div>

