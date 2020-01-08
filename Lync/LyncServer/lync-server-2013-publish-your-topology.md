---
title: 'Lync Server 2013: Pubblicare la topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bd542db6acedbec75e475045ae2ace6d63d5469
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40985582"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-your-topology-in-lync-server-2013"></a>Pubblicare la topologia in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-08_

Ogni volta che si usa generatore di topologie per compilare la topologia, è necessario pubblicare la topologia in un database in Central Management store in modo che i dati possano essere usati per distribuire Lync Server 2013. Usare la procedura seguente per pubblicare la topologia.

<div>

## <a name="to-publish-the-topology"></a>Per pubblicare la topologia

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Generatore di topologia di Lync Server**.

2.  Nell'albero della console, in Generatore di topologia, fare clic con il pulsante destro del mouse su **Lync 2013**e quindi scegliere **Pubblica topologia**.

3.  Nella pagina di **benvenuto** della procedura guidata fare clic su **Avanti**.

4.  Nella pagina **Generatore di topologia è stata trovata una pagina di CMS Store** , fare clic su **Avanti**.

5.  Nella pagina **crea altri database** fare clic su **Avanti**.

6.  Quando lo stato indica che la creazione del database è riuscita, eseguire le operazioni seguenti:
    
      - Per visualizzare il log, fare clic su **Visualizza log**.
    
      - Per chiudere la procedura guidata, fare clic su **fine**.
        
        <div>
        

        > [!IMPORTANT]  
        > Se si tratta di una nuova installazione di un server perimetrale o di un pool di Edge, è necessario esportare la configurazione del server perimetrale da un server front-end esistente, un pool Front-end o un server Standard Edition. Per esportare la configurazione, vedere <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">esportare la topologia di Lync Server 2013 e copiarla in elementi multimediali esterni per l'installazione di Edge</A>. Il file di configurazione verrà importato dal supporto esterno o dalla condivisione di rete durante la fase di configurazione e distribuzione degli Edge Server tramite la distribuzione guidata di Lync Server.<BR>Una volta che i server perimetrali sono operativi e il database dell'archivio di gestione della configurazione locale viene replicato con la distribuzione interna, gli aggiornamenti successivi alla configurazione di Lync Server 2013 verranno pubblicati e replicati in Edge Server.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

