---
title: "Lync Server 2013: eliminare le route esistenti nell'area di rete"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deleting existing network region routes
ms:assetid: 6256ff80-5f1e-48b4-928b-24aeb3c1a0e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688074(v=OCS.15)
ms:contentKeyID: 49733669
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e188ef3214088fe9c38c144fad1908d13fef162
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976511"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deleting-existing-network-region-routes-in-lync-server-2013"></a>Eliminazione di route di area di rete esistenti in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-11-01_

Ogni area geografica in una configurazione di controllo di ammissione chiamata (CAC) deve avere un modo per accedere a tutte le altre aree geografiche. Mentre i collegamenti con le aree geografiche impostano limitazioni della larghezza di banda sulle connessioni tra regioni e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione da un'area a un'altra. È possibile usare il pannello di controllo di Lync Server per configurare le route dell'area di rete. Dal pannello di controllo di Lync Server è possibile creare, modificare o eliminare una route dell'area di rete. Usare questo argomento per eliminare le route esistenti nell'area di rete. Per informazioni dettagliate sulla creazione o la modifica di route di area di rete, vedere [creazione o modifica di route dell'area di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md).

<div>

## <a name="to-delete-a-network-region-route"></a>Per eliminare una route dell'area di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **area geografica**.

4.  Nella pagina **route dell'area geografica** fare clic sulla route di area che si desidera eliminare.
    
    <div>
    

    > [!NOTE]  
    > Puoi eliminare più di una route della regione alla volta. Per eseguire questa operazione, premere CTRL e selezionare più percorsi per le aree geografiche mentre si tiene premuto il tasto CTRL. In alternativa, per selezionare tutte le route dell'area geografica, fare clic su <STRONG>Seleziona tutto</STRONG> dal menu <STRONG>modifica</STRONG> .

    
    </div>

5.  Scegliere **Elimina**dal menu **modifica** .

6.  Fare clic su **OK**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creazione o modifica di route dell'area di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-region-routes.md)  


[Configurare una route di un'area di rete](https://technet.microsoft.com/en-us/library/gg133706\(v=ocs.15\))  


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

