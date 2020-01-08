---
title: 'Lync Server 2013: visualizzazione delle informazioni sul sito di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing network site information
ms:assetid: 24a97d98-b168-4016-81bf-c2c478092b87
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687996(v=OCS.15)
ms:contentKeyID: 49733586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 788440d02a3f41198a870f8419cece4dc8e66900
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40975222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-network-site-information-in-lync-server-2013"></a>Visualizzazione delle informazioni sul sito di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-23_

I siti di rete sono gli uffici o i percorsi configurati in ogni area geografica di un controllo di ammissione alle chiamate (CAC) o una distribuzione avanzata di 9-1-1. È possibile visualizzare le informazioni sul sito di rete nel pannello di controllo di Lync Server 2013 o Lync Server Management Shell. Per informazioni dettagliate sulla creazione o la modifica di siti di rete, vedere [creazione o modifica di siti di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md).

<div>

## <a name="to-view-network-site-information-in-lync-server-control-panel"></a>Per visualizzare le informazioni sul sito di rete nel pannello di controllo di Lync Server

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **sito**.

4.  Nella pagina del **sito** fare clic sul sito che si desidera visualizzare.
    
    <div>
    

    > [!NOTE]  
    > È possibile visualizzare le informazioni solo per un sito alla volta.

    
    </div>

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.

</div>

<div>

## <a name="viewing-network-site-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni sul sito di rete tramite i cmdlet di Windows PowerShell

È possibile visualizzare le informazioni sul sito di rete usando Windows PowerShell e il cmdlet Get-CsNetworkSite. Questo cmdlet può essere eseguito da Lync Server 2013 Management Shell o da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'uso di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo sul Blog di Lync Server di Windows PowerShell "Guida introduttiva: gestione di Microsoft [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)Lync Server 2010 con Remote PowerShell" at.

<div>

## <a name="to-view-network-site-information"></a>Per visualizzare le informazioni sul sito di rete

  - Per visualizzare informazioni su tutti i siti di rete, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsNetworkSite
    
    Questo restituirà informazioni simili alla seguente:
    
        Identity          : Redmond
        NetworkSiteID     : Redmond
        Description       :
        NetworkRegionID   : Pacific Northwest
        BypassID          : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        BWPolicyProfileID :
        LocationPolicy    :

</div>

Per altre informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkSite](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkSite) .

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creazione o modifica di siti di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-sites.md)  
[Eliminazione di un sito di rete esistente in Lync Server 2013](lync-server-2013-deleting-an-existing-network-site.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

