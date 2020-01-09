---
title: Lync Server 2013; Creare route interregion di rete
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: admin
manager: serdars
TOCTitle: Create network interregion routes
ms:assetid: 5555262a-a502-4b01-9593-836dd30064f5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398368(v=OCS.15)
ms:contentKeyID: 48184159
ms.date: 07/23/2014
mtps_version: v=OCS.15
ms.openlocfilehash: 9d234d959f434e9e2b96850add488ecd4eac952c
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991711"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-network-interregion-routes-in-lync-server-2013"></a>Creare route interregion di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-20_

Una *Route interregion di rete* definisce la route tra una coppia di aree della rete. Ogni coppia di aree della rete nella distribuzione del controllo di ammissione alle chiamate richiede una route interregion di rete. In questo modo ogni area di rete della distribuzione consente di accedere a tutte le altre aree geografiche.

Mentre i collegamenti con le aree geografiche impostano limitazioni della larghezza di banda sulle connessioni tra regioni, una route interregion determina il percorso collegato che la connessione attraverserà da un'area a un'altra.

Per informazioni dettagliate sull'uso delle route interregion di rete, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:

  - [New-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkInterRegionRoute)

  - [Get-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkInterRegionRoute)

  - [Set-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkInterRegionRoute)

  - [Remove-CsNetworkInterRegionRoute](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkInterRegionRoute)

Nella topologia di esempio è necessario definire le route interregion di rete per ognuna delle tre coppie di aree geografiche: Nord America/EMEA, EMEA/APAC e Nord America/APAC.

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-management-shell"></a>Per creare route interregion di rete tramite Lync Server Management Shell

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet **New-CsNetworkInterRegionRoute** per definire le route necessarie. Ad esempio, eseguire:
    
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
    > La route interregion di rete Nord America/APAC richiede due collegamenti all'area di rete perché non è presente un collegamento all'area di rete diretta.

    
    </div>

</div>

<div>

## <a name="to-create-network-interregion-routes-by-using-lync-server-control-panel"></a>Per creare route interregion di rete tramite il pannello di controllo di Lync Server

1.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.

3.  Fare clic sul pulsante di spostamento della **Route geografica** .

4.  Fare clic su **nuovo**.

5.  Nella pagina **nuova route dell'area geografica** fare clic su **nome** e quindi digitare un nome per la route interregion di rete.

6.  Fare clic su **area \#di rete 1**e quindi fare clic su un'area di rete nell'elenco che si vuole instradare all'area geografica \#di rete 2.

7.  Fare clic su **area geografica \#di rete 2**e quindi fare clic su un'area di rete nell'elenco che si \#vuole instradare all'area geografica di rete 1.

8.  Fare clic su **Aggiungi** accanto al campo **collegamenti area geografica** e quindi aggiungere un collegamento all'area di rete che verrà usato nella route interregion di rete.
    
    <div class=" ">
    

    > [!NOTE]  
    > Se si sta creando una route per due aree di rete che non dispongono di un collegamento all'area di rete diretta, è necessario aggiungere tutti i collegamenti necessari per completare la route. Ad esempio, la route interregion di rete Nord America/APAC richiede due collegamenti all'area geografica di rete perché non è presente un collegamento all'area di rete diretta.

    
    </div>

9.  Fare clic su **Commit**.

10. Per completare la creazione di route interregion di rete per la topologia, ripetere i passaggi da 4 a 9 con le impostazioni per altre route interregion di rete.

</div>

</div>

<span> </span>

</div>

</div>

</div>

