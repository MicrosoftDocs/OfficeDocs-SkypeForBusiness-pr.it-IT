---
title: 'Lync Server 2013: definire e configurare una topologia in Generatore di topologie'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define and configure a topology in Topology Builder
ms:assetid: 99231ff5-1c21-432b-ad65-8675fcd484f9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398788(v=OCS.15)
ms:contentKeyID: 48184953
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0aa4a2c12771adf41972fc0c69222935d6935570
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504603"
---
# <a name="define-and-configure-a-topology-in-topology-builder-for-lync-server-2013"></a>Definire e configurare una topologia in Generatore di topologie per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-21_

L'esecuzione di generatore di topologie per definire una nuova topologia o per modificare una topologia esistente non richiede l'appartenenza a un amministratore locale o a un gruppo di dominio privilegiato. In Generatore di topologie vengono illustrati i passaggi necessari per definire la topologia per un pool Enterprise Edition front end o una versione standard, in base ai requisiti di configurazione.

Per poter installare Lync Server 2013 sui server, è necessario utilizzare Generatore di topologie per completare e pubblicare la topologia. La procedura seguente include i passaggi per definizione di una nuova topologia.

<div>

## <a name="to-define-a-topology"></a>Per definire una topologia

1.  Avviare Generatore di topologie: fare clic sul pulsante **Start**, scegliere **Tutti i programmi**, **Microsoft Lync Server 2013** e quindi **Generatore di topologie**.

2.  In Generatore di topologie selezionare **nuova topologia**. Verrà richiesto di inserire un percorso e un nome file per il salvataggio della topologia. Assegnare alla topologia un nome significativo e accettare l'estensione predefinita tbxml. Fare clic su **OK**.

3.  Passare al percorso in cui si desidera salvare il file XML della nuova topologia, immettere un nome per il file e quindi fare clic su **Salva**.

4.  Nella pagina **Definire il dominio primario** immettere il nome del dominio SIP primario per l'organizzazione e quindi fare clic su **Avanti**.

5.  Nella pagina **Specificare i domini aggiuntivi supportati** immettere i nomi degli eventuali domini aggiuntivi e quindi fare clic su **Avanti**.

6.  Nella pagina **Definire il primo sito** immettere il nome e la descrizione del primo sito e quindi fare clic su **Avanti**.

7.  Nella pagina **Specificare i dettagli del sito** immettere le informazioni relative alla posizione del sito e quindi fare clic su **Avanti**.

8.  Nella pagina **nuova topologia è stata definita correttamente** , verificare che la casella di controllo **Apri la procedura guidata nuovo front-end al termine della procedura guidata** sia selezionata e quindi fare clic su **fine**.

Dopo aver definito e salvato la topologia, utilizzare la nuova procedura guidata front-end per definire un pool Front end o un server Standard Edition per il sito. Per informazioni dettagliate, vedere [define and Configure a front end pool or Standard Edition server in Lync server 2013](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

