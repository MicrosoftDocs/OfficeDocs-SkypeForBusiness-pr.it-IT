---
title: "Lync Server 2013: creare o modificare un'area di rete"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a network region
ms:assetid: bf7a3dc4-71a2-4559-a547-d90305d4f904
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412933(v=OCS.15)
ms:contentKeyID: 48185281
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 417fece34f8e5177760e470083cd929cbddaab60
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197429"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a>Creare o modificare un'area di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-19_

Le *aree di rete* sono gli hub di rete o gli backbone utilizzati nella configurazione del controllo di ammissione di chiamata, E9-1-1 e bypass multimediale. Utilizzare le procedure seguenti per creare o modificare le aree di rete. Ad esempio, se sono già state create aree di rete per una caratteristica vocale, non è necessario creare nuove aree di rete. altre funzionalità di VoIP aziendale avanzate utilizzeranno le stesse aree di rete. Potrebbe tuttavia essere necessario modificare una definizione di area di rete esistente per applicare impostazioni specifiche della caratteristica. Ad esempio, se sono state create aree di rete per il servizio E9-1-1 (che non richiede un sito centrale associato) e quindi si distribuisce il controllo di ammissione di chiamata, è necessario modificare le definizioni delle aree di rete per specificare un sito centrale. Per ulteriori informazioni, vedere [Configure Network Regions for CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).

<div>


> [!NOTE]  
> Tutti i requisiti specifici per particolari funzionalità per le definizioni delle aree di rete sono documentati negli argomenti relativi alla distribuzione per la funzionalità.



</div>

Per informazioni dettagliate sull'utilizzo delle aree di rete, vedere la documentazione di Lync Server Management Shell relativa ai cmdlet seguenti:

  - [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a>Creare un'area di rete

Creare un'area di rete utilizzabile dal controllo di ammissione di chiamata, E9-1-1 o il bypass multimediale.

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a>Per creare un'area di rete utilizzando Lync Server Management Shell

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire il cmdlet New-CsNetworkRegion per creare le aree di rete:
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Ad esempio:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    Con questo esempio viene creata un'area di rete denominata “NorthAmerica” associata a un sito centrale con ID di sito CHICAGO.

3.  Per completare la creazione delle aree di rete per la topologia, ripetere il passaggio 2 con le impostazioni per ogni area di rete.

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a>Per creare un'area di rete utilizzando il pannello di controllo di Lync Server

1.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.

3.  Fare clic su **Area**.

4.  Fare clic su **Nuovo**.

5.  Nella pagina **Nuova area** fare clic su **Nome** e quindi digitare un nome per l'area di rete.

6.  Fare clic su **Sito centrale** e quindi fare clic su un sito centrale nell'elenco.

7.  Facoltativamente, fare clic su **Descrizione** e quindi digitare ulteriori informazioni per descrivere il sito di rete.

8.  Fare clic su **Commit**.

9.  Per completare la creazione delle aree di rete per la topologia, ripetere i passaggi da 4 a 8 con le impostazioni per le altre aree.

</div>

</div>

<div>

## <a name="modify-a-network-region"></a>Modificare un'area di rete

È possibile modificare le impostazioni per un'area di rete esistente per adattarle a modifiche delle informazioni di base sull'area o a modifiche rese necessarie da una nuova funzionalità.

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a>Per modificare un'area di rete utilizzando Lync Server Management Shell

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Lync Server Management Shell**.

2.  Eseguire il cmdlet Set-CsNetworkRegion per modificare un'area di rete esistente:
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Ad esempio:
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    Con questo esempio si modifica un'area di rete esistente denominata “NorthAmerica” (creata con le procedure descritte in precedenza in questo argomento) modificandone la descrizione. Se per l'area “NorthAmerica” esiste già una descrizione, questo comando la sostituisce con il valore specificato. Se non è mai stata impostata una descrizione, con questo comando viene aggiunta.

3.  Per modificare altre aree di rete, ripetere il passaggio 2 con le impostazioni per le altre aree.

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a>Per modificare un'area di rete utilizzando il pannello di controllo di Lync Server

1.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete**.

3.  Fare clic sul pulsante di spostamento **Area**.

4.  Nella tabella fare clic sull'area di rete che si desidera modificare.

5.  Fare clic su **Modifica** e quindi su **Mostra dettagli**.

6.  Nella pagina **Modifica area** modificare i valori per le impostazioni dell'area di rete in base alle esigenze.

7.  Fare clic su **Commit**.

8.  Per completare la modifica delle aree di rete, ripetere i passaggi da 4 a 7 con le impostazioni per le altre aree.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

