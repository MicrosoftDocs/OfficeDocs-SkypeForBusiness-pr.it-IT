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
ms.openlocfilehash: 75011a28567da8a6e386c42f272ee1510b8ceddc
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-network-region-in-lync-server-2013"></a>Creare o modificare un'area di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-19_

Le *aree di rete* sono gli hub di rete o le backbone usati nella configurazione del controllo di ammissione alle chiamate, E9-1-1 e bypass multimediale. Usare le procedure seguenti per creare o modificare aree di rete. Se ad esempio sono già state create aree di rete per una sola funzionalità vocale, non è necessario creare nuove aree di rete. altre funzionalità vocali avanzate di Enterprise useranno le stesse aree di rete. Può tuttavia essere necessario modificare una definizione di area di rete esistente per applicare impostazioni specifiche delle caratteristiche. Ad esempio, se sono state create aree di rete per E9-1-1 (che non richiedono un sito centrale associato) e quindi si distribuisce il controllo di ammissione delle chiamate, è necessario modificare le definizioni dell'area di rete per specificare un sito centrale. Per informazioni dettagliate, vedere [configurare le aree di rete per CAC in Lync Server 2013](lync-server-2013-configure-network-regions-for-cac.md).

<div>


> [!NOTE]  
> Tutti i requisiti specifici delle caratteristiche per le definizioni di area di rete sono documentati negli argomenti relativi alla distribuzione della funzionalità.



</div>

Per informazioni dettagliate sull'uso delle aree di rete, vedere la documentazione di Lync Server Management Shell per i cmdlet seguenti:

  - [New-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/New-CsNetworkRegion)

  - [Get-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Get-CsNetworkRegionLink)

  - [Set-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Set-CsNetworkRegion)

  - [Remove-CsNetworkRegion](https://docs.microsoft.com/powershell/module/skype/Remove-CsNetworkRegion)

<div>

## <a name="create-a-network-region"></a>Creare un'area di rete

Creare un'area di rete che può essere usata tramite il controllo di ammissione alle chiamate, E9-1-1 o bypass multimediale.

<div>

## <a name="to-create-a-network-region-using-lync-server-management-shell"></a>Per creare un'area di rete con Lync Server Management Shell

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet New-CsNetworkRegion per creare aree di rete:
    
        New-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Ad esempio:
    
        New-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "All North America Locations"
    
    In questo esempio è stata creata un'area di rete denominata "NorthAmerica" associata a un sito centrale con ID sito di CHICAGO.

3.  Per completare la creazione di aree di rete per la topologia, ripetere il passaggio 2 con le impostazioni per ogni area di rete.

</div>

<div>

## <a name="to-create-a-network-region-using-lync-server-control-panel"></a>Per creare un'area di rete tramite il pannello di controllo di Lync Server

1.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.

3.  Fare clic su **area geografica**.

4.  Fare clic su **nuovo**.

5.  Nella pagina **nuova area** fare clic su **nome** e quindi digitare un nome per l'area di rete.

6.  Fare clic su **sito centrale**e quindi su un sito centrale nell'elenco.

7.  Facoltativamente, fare clic su **Descrizione**e quindi digitare altre informazioni per descrivere questo sito di rete.

8.  Fare clic su **Commit**.

9.  Per completare la creazione di aree di rete per la topologia, ripetere i passaggi da 4 a 8 con le impostazioni per altre aree geografiche.

</div>

</div>

<div>

## <a name="modify-a-network-region"></a>Modificare un'area di rete

Modificare le impostazioni di un'area geografica esistente per adattare le modifiche alle informazioni relative alle aree di base o alle modifiche necessarie per una nuova funzionalità.

<div>

## <a name="to-modify-a-network-region-using-lync-server-management-shell"></a>Per modificare un'area di rete tramite Lync Server Management Shell

1.  Avviare Lync Server Management Shell: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Lync Server Management Shell**.

2.  Eseguire il cmdlet Set-CsNetworkRegion per modificare un'area di rete esistente:
    
        Set-CsNetworkRegion -Identity <String> -CentralSite <String>
    
    Ad esempio:
    
        Set-CsNetworkRegion -Identity NorthAmerica -CentralSite CHICAGO -Description "North American Region"
    
    In questo esempio è stata modificata un'area di rete esistente denominata "NorthAmerica" (creata usando le procedure descritte più indietro in questo argomento) modificando la descrizione. Se esiste una descrizione per l'area "NorthAmerica", questo comando lo sovrascrive con questo valore; Se non è stata impostata alcuna descrizione, questo comando lo imposta.

3.  Per modificare altre aree di rete, ripetere il passaggio 2 con le impostazioni per altre aree geografiche.

</div>

<div>

## <a name="to-modify-a-network-region-using-lync-server-control-panel"></a>Per modificare un'area di rete tramite il pannello di controllo di Lync Server

1.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

2.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete**.

3.  Fare clic sul pulsante di spostamento dell' **area geografica** .

4.  Nella tabella fare clic sull'area di rete che si vuole modificare.

5.  Fare clic su **modifica**e quindi su **Mostra dettagli.**

6.  Nella pagina **Edit Region** modificare i valori delle impostazioni dell'area di rete in base alle esigenze.

7.  Fare clic su **Commit**.

8.  Per completare la modifica delle aree di rete, ripetere i passaggi da 4 a 7 con le impostazioni per altre aree geografiche.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

