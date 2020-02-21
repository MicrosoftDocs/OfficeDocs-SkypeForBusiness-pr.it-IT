---
title: Lync Server 2013; Creare route tra aree di rete
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: admin
manager: serdars
f1.keywords:
- NOCSH
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 72917dc3ef179e0c27de6d47e599746a97e0540e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210242"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a>Creare route tra aree di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-20_

Una *route tra aree di rete* definisce la route tra una coppia di aree di rete. Ogni coppia di aree di rete nella distribuzione del servizio Controllo di ammissione di chiamata richiede una route di questo tipo. In tal modo ogni area di rete della distribuzione può accedere a tutte le altre aree.

Se i collegamenti di area impostano limitazioni della larghezza di banda per le connessioni tra le aree, una route tra aree determina il percorso collegato attraversato dalla connessione per passare da un'area all'altra.

Per informazioni dettagliate sull'utilizzo delle route tra aree di rete, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:

  - [New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

Nella topologia di esempio, le route tra aree di rete devono essere definite per ognuna delle tre coppie di aree, ovvero Nord America/EMEA, EMEA/APAC e Nord America/APAC.

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a>Per creare route tra aree di rete tramite Lync Server Management Shell

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire il cmdlet **New-CsNetworkInterRegionRoute** per definire le route richieste. Ad esempio, eseguire:
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_EMEA_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 EMEA -NetworkRegionLinkIDs "NA-EMEA-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity NorthAmerica_APAC_Route -NetworkRegionID1 NorthAmerica -NetworkRegionID2 APAC -NetworkRegionLinkIDs "NA-EMEA-LINK, EMEA-APAC-LINK"
       ```
    
       ```PowerShell
        New-CsNetworkInterRegionRoute -Identity EMEA_APAC_Route -NetworkRegionID1 EMEA -NetworkRegionID2 APAC -NetworkRegionLinkIDs "EMEA-APAC-LINK"
       ```
    
    <div class=" ">
    

    > [!NOTE]  
    > La route tra aree di rete Nord America/APAC richiede due collegamenti tra aree di rete perché non esiste un collegamento diretto tra le due aree.

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a>Per creare route tra aree di rete utilizzando il pannello di controllo di Lync Server

1.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.

3.  Fare clic sul pulsante di spostamento **Route area**.

4.  Fare clic su **Nuovo**.

5.  Nella pagina **Nuova route aree di rete** fare clic su **Nome** e quindi digitare un nome per la route tra aree di rete.

6.  Fare clic su **area \#** di rete 1 e quindi fare clic su un'area di rete nell'elenco che si desidera instradare all'area \#di rete 2.

7.  Fare clic su **area \#di rete 2**e quindi fare clic su un'area di rete nell'elenco che si desidera instradare all'area \#di rete 1.

8.  Fare clic su **Aggiungi** accanto al campo **Collegamenti aree di rete** e quindi aggiungere un collegamento all'area di rete che verrà usato come route tra aree di rete.
    
    <div class=" ">
    

    > [!NOTE]  
    > Se si crea una route per due aree di rete tra le quali non esiste un collegamento diretto, è necessario aggiungere tutti i collegamenti necessari per completare la route. Ad esempio, la route tra le aree di rete Nord America/APAC richiede due collegamenti tra aree di rete perché non esiste un collegamento diretto tra le due aree.

    
    </div>

9.  Fare clic su **Commit**.

10. Per completare la creazione delle route tra aree di rete per la topologia, ripetere i passaggi da 4 a 9 con le impostazioni per le altre route.

</div>

</div>

<span> </span>

</div>

</div>

</div>

