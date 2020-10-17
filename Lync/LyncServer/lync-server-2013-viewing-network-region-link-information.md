---
title: "Lync Server 2013: visualizzazione delle informazioni sul collegamento di un'area di rete"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d69040594a04d71f07d004826e4207c0b23612f6
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535693"
---
# <a name="viewing-network-region-link-information-in-lync-server-2013"></a>Visualizzazione delle informazioni sul collegamento area di rete in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

È possibile visualizzare i collegamenti tra due aree di rete nell'ambito del servizio Controllo di ammissione di chiamata. Le aree di una rete sono collegate mediante una connettività WAN fisica. È possibile utilizzare il pannello di controllo di Lync Server per visualizzare un collegamento esistente tra due aree di rete. Per informazioni dettagliate sulla creazione o la modifica di un collegamento area di rete, vedere [Configuring Network Region Links in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a>Per visualizzare un collegamento area di rete nel pannello di controllo di Lync Server

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Collegamento area**.

4.  Nella pagina **Collegamento area** fare clic sul collegamento area che si desidera visualizzare.
    
    <div>
    

    > [!NOTE]  
    > È possibile visualizzare informazioni su un collegamento aree alla volta.

    
    </div>

5.  Scegliere **Elimina** dal menu **Mostra dettagli**.

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni sul collegamento area di rete tramite i cmdlet di Windows PowerShell

È possibile visualizzare i collegamenti area di rete utilizzando Windows PowerShell e il cmdlet **Get-CsNetworkRegionLink** . È possibile eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-network-region-link-information"></a>Per visualizzare informazioni su un collegamento area di rete

  - Per visualizzare informazioni su tutti i collegamenti dell'area di rete, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsNetworkRegionLink
    
    Il comando restituisce informazioni simili a quelle riportate di seguito:
    
        Identity            : NorthwestToCalifornia
        BWPolicyProfileID   :
        NetworkRegionLinkID : NorthwestToCalifornia
        NetworkRegionID1    : Pacific Northwest
        NetworkRegionID2    : California

</div>

Per informazioni dettagliate, vedere [Get-CsNetworkRegionLink](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Configurazione di collegamenti di sito di rete in Lync Server 2013](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

