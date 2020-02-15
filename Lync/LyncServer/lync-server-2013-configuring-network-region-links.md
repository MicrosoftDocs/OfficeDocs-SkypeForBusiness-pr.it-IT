---
title: 'Lync Server 2013: configurazione di collegamenti tra aree di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring network region links
ms:assetid: 952bc93e-e6aa-4539-85c7-2b15f14eb382
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182551(v=OCS.15)
ms:contentKeyID: 48184829
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccafd4302897a8768164f9f085f382e2ad806c2d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030520"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-network-region-links-in-lync-server-2013"></a>Configurazione di collegamenti tra aree di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

È possibile configurare i collegamenti tra due aree di rete nell'ambito del servizio Controllo di ammissione di chiamata. Le aree di una rete sono collegate mediante una connettività WAN fisica. È possibile utilizzare il pannello di controllo di Lync Server per definire un collegamento tra due aree di rete e impostare le limitazioni della larghezza di banda per le connessioni audio e video tra queste aree geografiche. Per informazioni dettagliate sull'eliminazione di un collegamento a un'area di rete esistente, vedere [eliminazione di collegamenti di aree di rete in Lync Server 2013](lync-server-2013-deleting-network-region-links.md).

<div>

## <a name="to-create-a-network-region-link"></a>Per creare un collegamento area di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Collegamento area**.

4.  Nella pagina **collegamento area** fare clic su **nuovo**.

5.  In **nuovo collegamento area**Digitare un valore nel campo **nome** .
    
    <div>
    

    > [!NOTE]  
    > Questo valore deve essere univoco all'interno della distribuzione di Lync Server 2013.

    
    </div>

6.  Nell'elenco a discesa ** \#area di rete 1** Selezionare una delle due aree geografiche da collegare.

7.  Nell'elenco a discesa ** \#area di rete 2** Selezionare l'altra area da collegare. Questa area deve essere diversa dall'area selezionata per l'area \#di rete 1.

8.  Optional Se si desidera inserire limitazioni della larghezza di banda per le chiamate audio o video tra queste aree, selezionare un profilo dei criteri di larghezza di banda nell'elenco a discesa **criteri larghezza** di banda.

9.  Fare clic su **Commit**.

</div>

<div>

## <a name="to-modify-a-network-region-link"></a>Per modificare un collegamento area di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Collegamento area**.

4.  Nella pagina **collegamento area** fare clic sul collegamento area che si desidera modificare.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

6.  In **Modifica collegamento area**è possibile modificare le aree collegate o il profilo dei criteri di larghezza di banda per questo collegamento.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Eliminazione di collegamenti delle aree di rete in Lync Server 2013](lync-server-2013-deleting-network-region-links.md)  


[New-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegionLink)  
[Set-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegionLink)  
[Remove-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegionLink)  
[Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>
