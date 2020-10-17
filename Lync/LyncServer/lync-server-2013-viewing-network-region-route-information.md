---
title: 'Lync Server 2013: visualizzazione delle informazioni sulle route delle aree di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region route information
ms:assetid: 34dd9fa3-e695-4680-b244-3019298b5009
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688021(v=OCS.15)
ms:contentKeyID: 49733611
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e671bb8f714e2444cc2f271f6ad7ecebc74f7ddb
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535683"
---
# <a name="viewing-network-region-route-information-in-lync-server-2013"></a>Visualizzazione delle informazioni sulle route delle aree di rete in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Ogni area di una configurazione di controllo di ammissione di chiamata deve in qualche modo poter accedere a tutte le altre aree. Mentre i collegamenti area impostano limitazioni della larghezza di banda nelle connessioni tra aree e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione per passare da un'area all'altra. Utilizzare le procedure seguenti per visualizzare le route delle aree di rete esistenti in Lync Server 2013 Control Panel o Lync Server 2013 Management Shell. Per informazioni dettagliate sulla creazione o la modifica delle route delle aree di rete, vedere [creazione o modifica di route delle aree di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).

<div>

## <a name="to-view-network-region-route-information-in-lync-server-control-panel"></a>Per visualizzare le informazioni sulle route delle aree di rete nel pannello di controllo di Lync Server

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Configurazione di rete**, quindi su **Route area**.

4.  Nella pagina **Route area** fare clic sulla route area che si vuole visualizzare.
    
    <div>
    

    > [!NOTE]  
    > È possibile visualizzare una sola route area per volta.

    
    </div>

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

</div>

<div>

## <a name="viewing-network-region-route-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni sulle route delle aree di rete tramite i cmdlet di Windows PowerShell

È possibile visualizzare le informazioni sulle route delle aree di rete utilizzando Windows PowerShell e il cmdlet Get-CsNetworkInterRegionRoute. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-network-region-route-information"></a>Per visualizzare le informazioni sulle route delle aree di rete

  - Per visualizzare informazioni su tutte le route delle aree di rete, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsNetworkInterRegionRoute
    
    Verranno restituite informazioni simili alle seguenti:
    
        Identity                  : TransAmericaRoute
        NetworkRegionLinks        : {NorthwestToNortheast}
        InterNetworkRegionRouteID : TransAmericaRoute
        NetworkRegionID1          : Pacific Northwest
        NetworkRegionID2          : Northeast

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creazione o modifica delle route delle aree di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md)  
[Eliminazione delle route delle aree di rete esistenti in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

