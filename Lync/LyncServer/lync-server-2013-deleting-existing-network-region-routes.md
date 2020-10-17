---
title: 'Lync Server 2013: eliminazione delle route delle aree di rete esistenti'
description: 'Lync Server 2013: eliminazione delle route delle aree di rete esistenti.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2501dc3f4ed88a56e9f591e3af11a673046280a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557902"
---
# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a>Eliminazione delle route delle aree di rete esistenti in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-01_

Ogni area di una configurazione di controllo di ammissione di chiamata deve in qualche modo poter accedere a tutte le altre aree. Mentre i collegamenti area impostano limitazioni della larghezza di banda nelle connessioni tra aree e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione per passare da un'area all'altra. È possibile utilizzare il pannello di controllo di Lync Server per configurare le route delle aree di rete. Dal pannello di controllo di Lync Server, è possibile creare, modificare o eliminare una route area di rete. Utilizzare questo argomento per informazioni su come eliminare le route area di rete. Per informazioni dettagliate sulla creazione o la modifica delle route delle aree di rete, vedere [creazione o modifica di route delle aree di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).

<div>

## <a name="to-delete-a-network-region-route"></a>Per eliminare una route area di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Route area**.

4.  Nella pagina **Route area** fare clic sulla route area che si desidera eliminare.
    
    <div>
    

    > [!NOTE]  
    > È possibile eliminare più di una route area per volta. A tale scopo, selezionare più route area tenendo premuto CTRL oppure, per selezionare tutte le route area, scegliere <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>Modifica</STRONG>.

    
    </div>

5.  Scegliere **Elimina** dal menu **Modifica**.

6.  Fare clic su **OK**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creazione o modifica delle route delle aree di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md)  


[Configurare una route di un'area di rete](https://technet.microsoft.com/library/gg133706\(v=ocs.15\))  


[New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)  
[Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)  
[Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)  
[Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

