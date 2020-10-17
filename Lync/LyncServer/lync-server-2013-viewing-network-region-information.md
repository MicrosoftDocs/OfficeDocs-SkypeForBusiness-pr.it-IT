---
title: 'Lync Server 2013: visualizzazione delle informazioni sulle aree di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing network region information
ms:assetid: 665740d0-a3ed-460f-8337-5ed945f90589
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688076(v=OCS.15)
ms:contentKeyID: 49733672
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7222afb226a211609423cb3c5ad1e40383de67e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48535723"
---
# <a name="viewing-network-region-information-in-lync-server-2013"></a>Visualizzazione delle informazioni sulle aree di rete in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-23_

Un'area di rete interconnette diverse parti di una rete dislocate su più aree geografiche. Ogni area di rete deve essere associata a un sito centrale. Il sito centrale è il sito del data center in cui è in esecuzione il servizio dei criteri di larghezza di banda del controllo di ammissione di chiamata. È possibile utilizzare il pannello di controllo di Lync Server per visualizzare le aree di rete. Per le aree di rete sono disponibili impostazioni che determinano se sono consentiti percorsi alternativi attraverso Internet per le connessioni audio e video. Le informazioni in questo argomento descrivono come visualizzare le aree di rete esistenti. Per informazioni dettagliate sulla creazione o la modifica delle aree di rete esistenti, vedere [creazione o modifica di aree di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md).

<div>

## <a name="to-view-information-about-a-network-region-with-lync-server-control-panel"></a>Per visualizzare informazioni su un'area di rete con il pannello di controllo di Lync Server

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Area**.

4.  Nella pagina **Area** fare clic sull'area che si desidera visualizzare.
    
    <div>
    

    > [!NOTE]  
    > È possibile visualizzare una sola area alla volta.

    
    </div>

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

</div>

<div>

## <a name="viewing-network-region-information-by-using-windows-powershell-cmdlets"></a>Visualizzazione delle informazioni sulle aree di rete tramite i cmdlet di Windows PowerShell

È possibile visualizzare le informazioni sulle aree di rete utilizzando Windows PowerShell e il cmdlet **Get-CsNetworkRegion** . È possibile eseguire questo cmdlet sia da Lync Server 2013 Management Shell sia da una sessione remota di Windows PowerShell. Per informazioni dettagliate sull'utilizzo di Windows PowerShell remoto per la connessione a Lync Server, vedere l'articolo del Blog su Lync Server di Windows PowerShell "Quick Start: Managing Microsoft Lync Server 2010 using Remote PowerShell" at [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) .

<div>

## <a name="to-view-network-region-information"></a>Per visualizzare le informazioni sulle aree di rete

  - Per visualizzare informazioni su tutte le aree di rete, digitare il comando seguente in Lync Server Management Shell e quindi premere INVIO:
    
        Get-CsNetworkRegion
    
    Verranno restituite informazioni simili alle seguenti:
    
        Identity         : Pacific Northwest
        Description      :
        BypassID         : 3b232b84-2c1d-4da2-8181-e9330bafebe9
        CentralSite      : Site:Redmond1
        BWAlternatePaths : {BWPolicyModality=Audio;AlternatePath=True, 
                           BWPolicyModality=Video;AlternatePath=True}
        NetworkRegionID  : Pacific Northwest

</div>

Per ulteriori informazioni, vedere l'argomento della Guida relativo al cmdlet [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Creazione o modifica di aree di rete in Lync Server 2013](lync-server-2013-creating-or-modifying-network-regions.md)  
[Eliminazione di aree di rete esistenti in Lync Server 2013](lync-server-2013-deleting-existing-network-regions.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

