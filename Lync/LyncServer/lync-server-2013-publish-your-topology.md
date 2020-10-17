---
title: 'Lync Server 2013: pubblicare la topologia'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7aed74df38f1d09d4aff46531bb6f61bdb6f03c8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512263"
---
# <a name="publish-your-topology-in-lync-server-2013"></a>Pubblicare la topologia in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-08_

Ogni volta che si utilizza il generatore di topologie per creare la topologia, è necessario pubblicare la topologia in un database nell'archivio di gestione centrale in modo che i dati possano essere utilizzati per la distribuzione di Lync Server 2013. Eseguire la procedura seguente per pubblicare la topologia.

<div>

## <a name="to-publish-the-topology"></a>Per pubblicare la topologia

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

2.  In Generatore di topologie, nell'albero della console, fare clic con il pulsante destro del mouse su **Lync 2013**e quindi scegliere **Pubblica topologia**.

3.  Nella pagina iniziale della**** procedura guidata fare clic su **Avanti**.

4.  Nella pagina **Archivio di gestione centrale rilevato da Generatore di topologie** fare clic su **Avanti**.

5.  Nella pagina **Crea database** fare clic su **Avanti**.

6.  Quando lo stato indica che la creazione del database è stata completata, eseguire le operazioni seguenti:
    
      - Per visualizzare il registro, fare clic su **Visualizza registro**.
    
      - Per chiudere la procedura guidata, fare clic su **Fine**.
        
        <div>
        

        > [!IMPORTANT]  
        > Se si tratta di una nuova installazione di un server perimetrale o di un pool di Edge, è necessario esportare la configurazione del server perimetrale da un server front end server esistente, un pool Front end o uno Standard Edition. Per esportare la configurazione, vedere <A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">esportare la topologia di Lync Server 2013 e copiarla su supporto esterno per l'installazione perimetrale</A>. Il file di configurazione verrà importato dal supporto esterno o dalla condivisione di rete durante la fase di installazione e distribuzione dei server perimetrali tramite la distribuzione guidata di Lync Server.<BR>Una volta che i server perimetrali sono operativi e il database dell'archivio di gestione della configurazione locale viene replicato con la distribuzione interna, i successivi aggiornamenti alla configurazione di Lync Server 2013 verranno pubblicati e replicati nei server perimetrali.

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

