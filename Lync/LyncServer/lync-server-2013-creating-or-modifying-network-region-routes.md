---
title: 'Lync Server 2013: creazione o modifica di route delle aree di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5e10cfddaa0e99ee5e6dbab5d196803923bfef95
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a>Creazione o modifica delle route delle aree di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-08_

Ogni area di una configurazione di controllo di ammissione di chiamata deve in qualche modo poter accedere a tutte le altre aree. Mentre i collegamenti area impostano limitazioni della larghezza di banda nelle connessioni tra aree e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione per passare da un'area all'altra. È possibile utilizzare il pannello di controllo di Lync Server per configurare le route delle aree di rete. Dal pannello di controllo di Lync Server, è possibile creare, modificare o eliminare una route area di rete. Utilizzare questo argomento per creare o modificare una nuova route area di rete. Per informazioni dettagliate sull'eliminazione di una route area di rete esistente, vedere [eliminazione delle route delle aree di rete esistenti in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).

<div>

## <a name="to-create-a-network-region-route"></a>Per creare una route area di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Nella barra di spostamento sinistra fare clic su **Configurazione di rete**, quindi su **Route area**.

4.  Nella pagina **Route area** fare clic su **Nuovo**.

5.  In **Nuova route area** digitare un valore nel campo **Nome**.
    
    <div>
    

    > [!NOTE]  
    > Questo valore deve essere univoco all'interno della distribuzione di Microsoft Lync Server 2013.

    
    </div>

6.  Nell'elenco a discesa ** \#area di rete 1** Selezionare una delle due aree geografiche da connettere tramite questa route.

7.  Nell'elenco a discesa ** \#area di rete 2** Selezionare l'altra area per la route. Questa area deve essere diversa dall'area selezionata per l'area \#di rete 1.

8.  Utilizzare la casella di riepilogo **Collegamenti aree di rete** per aggiungere collegamenti area di rete alla route. Fare clic sul pulsante **Aggiungi** per visualizzare la pagina **Collegamento area**. Fare clic su un collegamento area da aggiungere alla route e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Continuare a fare clic sul pulsante <STRONG>Aggiungi</STRONG> per aggiungere altri collegamenti oppure selezionare un collegamento e fare clic su <STRONG>Rimuovi</STRONG> per rimuoverlo.

    
    </div>

9.  Fare clic su **Commit**.

</div>

<div>

## <a name="to-modify-a-network-region-route"></a>Per modificare una route area di rete

1.  Da un account utente membro del gruppo RTCUniversalServerAdmins (o con diritti utente equivalenti) oppure assegnato al ruolo CsAdministrator, accedere a qualsiasi computer nella distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministrazione per aprire il Pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile utilizzare per avviare il pannello di controllo di Lync Server, vedere [apertura degli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **Configurazione di rete** e quindi su **Route area**.

4.  Nella pagina **Route area** fare clic sulla route area che si desidera modificare.

5.  Scegliere **Mostra dettagli** dal menu **Modifica**.

6.  In **Modifica route area** è possibile modificare le aree unite dalla route e i collegamenti area associati alla route.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Eliminazione delle route delle aree di rete esistenti in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

