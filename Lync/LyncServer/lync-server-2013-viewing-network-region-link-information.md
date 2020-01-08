---
title: "Lync Server 2013: visualizzazione delle informazioni sul collegamento all'area di rete"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network region link information
ms:assetid: 7b6b2ea2-83d8-4376-afb2-70e5d2cf6444
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688102(v=OCS.15)
ms:contentKeyID: 49733701
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ce5bec9bdc656a33a34727f29bfc56ad39b2476a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980644"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-region-link-information-in-lync-server-2013"></a>Visualizzazione delle informazioni sul collegamento all'area di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

È possibile visualizzare i collegamenti tra due aree di rete come parte del controllo di ammissione di chiamata (CAC). Le aree all'interno di una rete sono collegate tramite connettività WAN (Physical Wide Area Network). È possibile usare il pannello di controllo di Lync Server per visualizzare un collegamento esistente tra due aree di rete. Per informazioni dettagliate su come creare o modificare il collegamento all'area di rete, vedere [configurazione dei collegamenti all'area di rete in Lync Server 2013](lync-server-2013-configuring-network-region-links.md).

<div>

## <a name="to-view-a-network-region-link-in-lync-server-control-panel"></a>Per visualizzare un collegamento all'area di rete nel pannello di controllo di Lync Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su collegamento all' **area geografica**.

4.  Nella pagina **collegamento all'area geografica** fare clic sul collegamento all'area che si desidera visualizzare.
    
    <div>
    

    > [!NOTE]  
    > Puoi visualizzare solo le informazioni su un collegamento all'area geografica alla volta.

    
    </div>

5.  Nel menu **modifica** selezionare **Mostra dettagli**.

</div>

<div>

## <a name="viewing-network-region-link-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni sul collegamento all'area di rete tramite i cmdlet di Windows PowerShell

È possibile visualizzare i collegamenti all'area di rete usando Windows PowerShell e il cmdlet **Get-CsNetworkRegionLink** . Puoi eseguire questo cmdlet da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-view-network-region-link-information"></a>Per visualizzare le informazioni sul collegamento all'area di rete

  - Per visualizzare informazioni su tutti i collegamenti dell'area di rete, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsNetworkRegionLink
    
    Questo comando restituisce informazioni simili a quelle seguenti:
    
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


[Configurazione di collegamenti ai siti di rete in Lync Server 2013](lync-server-2013-configuring-network-site-links.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

