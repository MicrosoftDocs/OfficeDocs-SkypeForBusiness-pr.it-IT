---
title: "Lync Server 2013: visualizzazione delle informazioni sulla route dell'area di rete"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4438a3af4a9bfbdaf88d4412b769cdaaba9d3d43
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40984787"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-route-information-in-lync-server-2013"></a>Visualizzazione delle informazioni sulla route dell'area di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

Ogni area geografica in una configurazione di controllo di ammissione chiamata (CAC) deve avere un modo per accedere a tutte le altre aree geografiche. Mentre i collegamenti con le aree geografiche impostano limitazioni della larghezza di banda sulle connessioni tra regioni e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione da un'area a un'altra. Usare le procedure seguenti per visualizzare le route dell'area di rete esistenti nel pannello di controllo di Lync Server 2013 o in Lync Server 2013 Management Shell. Per informazioni dettagliate sulla creazione o la modifica di route di area di rete, vedere [creazione o modifica di route dell'area di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a>Per visualizzare le informazioni sulla route dell'area di rete nel pannello di controllo di Lync Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **area geografica**.

4.  Nella pagina **route dell'area geografica** fare clic sulla route dell'area geografica che si desidera visualizzare.
    
    <div>
    

    > [!NOTE]  
    > È possibile visualizzare una sola route geografica alla volta.

    
    </div>

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni sulla route dell'area di rete tramite i cmdlet di Windows PowerShell

Le informazioni sulla route dell'area di rete possono essere visualizzate usando Windows PowerShell e il cmdlet Get-CsNetworkInterRegionRoute. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-view-network-region-route-information"></a>Per visualizzare le informazioni sulla route dell'area di rete

  - Per visualizzare informazioni su tutte le route dell'area di rete, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsNetworkInterRegionRoute
    
    Questo restituirà informazioni simili alla seguente:
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creazione o modifica di route dell'area di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[Eliminazione di route di area di rete esistenti in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

