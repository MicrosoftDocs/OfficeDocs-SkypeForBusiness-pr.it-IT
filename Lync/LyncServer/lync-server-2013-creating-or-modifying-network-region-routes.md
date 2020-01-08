---
title: 'Lync Server 2013: creazione o modifica di route di area di rete'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Creating or modifying network region routes
ms:assetid: 76993daa-76c2-4cec-8363-de8aebef0145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg521016(v=OCS.15)
ms:contentKeyID: 48184540
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f31daafe6cafbf74f9f12812f8259c24cfa7349
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979888"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="creating-or-modifying-network-region-routes-in-lync-server-2013"></a>Creazione o modifica di route dell'area di rete in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-08_

Ogni area geografica in una configurazione di controllo di ammissione chiamata (CAC) deve avere un modo per accedere a tutte le altre aree geografiche. Mentre i collegamenti con le aree geografiche impostano limitazioni della larghezza di banda sulle connessioni tra regioni e rappresentano anche i collegamenti fisici, una route determina il percorso collegato che verrà attraversato dalla connessione da un'area a un'altra. È possibile usare il pannello di controllo di Lync Server per configurare le route dell'area di rete. Dal pannello di controllo di Lync Server è possibile creare, modificare o eliminare una route dell'area di rete. Usare questo argomento per creare o modificare una route dell'area di rete. Per informazioni dettagliate sull'eliminazione di route di un'area di rete esistenti, vedere [eliminazione di route di area di rete esistenti in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md).

<div>

## <a name="to-create-a-network-region-route"></a>Per creare una route dell'area di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **area geografica**.

4.  Nella pagina **Route Region** fare clic su **nuovo**.

5.  Nella **Route New Region**Digitare un valore nel campo **nome** .
    
    <div>
    

    > [!NOTE]  
    > Questo valore deve essere univoco all'interno della distribuzione di Microsoft Lync Server 2013.

    
    </div>

6.  Nell'elenco a discesa ** \#area di rete 1** Selezionare una delle due aree geografiche da connettere tramite questa route.

7.  Nell'elenco a discesa **Network Region \#2** Selezionare l'altra area per questa route. L'area geografica deve essere diversa da quella selezionata per l' \#area geografica di rete 1.

8.  Usare la casella di riepilogo **collegamenti area di rete** per aggiungere collegamenti all'area geografica. Fare clic sul pulsante **Aggiungi** per visualizzare la pagina del **collegamento all'area geografica** . Fare clic su un collegamento all'area da aggiungere alla route e quindi fare clic su **OK**.
    
    <div>
    

    > [!NOTE]  
    > Continuare a fare clic sul pulsante <STRONG>Aggiungi</STRONG> per aggiungere altri collegamenti oppure selezionare un collegamento e fare clic su <STRONG>Rimuovi</STRONG> per rimuovere un collegamento.

    
    </div>

9.  Fare clic su **Commit**.

</div>

<div>

## <a name="to-modify-a-network-region-route"></a>Per modificare una route dell'area di rete

1.  Da un account utente che è un membro del gruppo RTCUniversalServerAdmins (o ha diritti utente equivalenti) o viene assegnato al ruolo CsAdministrator, accedere a qualsiasi computer della distribuzione interna.

2.  Aprire una finestra del browser e quindi immettere l'URL di amministratore per aprire il pannello di controllo di Lync Server. Per informazioni dettagliate sui diversi metodi che è possibile usare per avviare il pannello di controllo di Lync Server, vedere [aprire gli strumenti di amministrazione di Lync server 2013](lync-server-2013-open-lync-server-administrative-tools.md).

3.  Sulla barra di spostamento sinistra fare clic su **configurazione di rete** e quindi su **area geografica**.

4.  Nella pagina **Route Region** fare clic sulla route dell'area geografica che si desidera modificare.

5.  Nel menu **modifica** fare clic su **Mostra dettagli**.

6.  In **modifica route area**è possibile modificare le aree affiancate da questa route e i collegamenti dell'area geografica associati alla route.

7.  Fare clic su **Commit**.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Eliminazione di route di area di rete esistenti in Lync Server 2013](lync-server-2013-deleting-existing-network-region-routes.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

