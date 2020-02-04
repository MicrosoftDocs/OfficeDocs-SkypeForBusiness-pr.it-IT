---
title: 'Lync Server 2013: Inizio del processo di pianificazione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Beginning the planning process
ms:assetid: df3722b3-f859-49e1-b3ff-ee6863483731
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398986(v=OCS.15)
ms:contentKeyID: 48185618
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a9da1c5535f190a6f57aa76b78a04845d4a073e2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741726"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="beginning-the-planning-process-for-lync-server-2013"></a>Inizio del processo di pianificazione per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-24_

Durante la pianificazione di una distribuzione di Unified Communications locale può sembrare intimidatorio, Lync Server offre due strumenti utili per aiutarti:

  - **Lo strumento di pianificazione** è una procedura guidata che presenta una serie di domande sull'organizzazione, le caratteristiche di Lync Server che si desidera abilitare e le esigenze di pianificazione della capacità. Crea quindi una topologia di distribuzione consigliata in base alle risposte e produce un diagramma di Microsoft Visio della distribuzione.

  - **Generatore di topologia** è un componente di installazione di Lync Server. Si usa generatore di topologie per creare, modificare e pubblicare la topologia pianificata. Convalida anche la topologia prima di iniziare le installazioni del server. Quando si installa Lync Server nei singoli server, i server leggono la topologia pubblicata come parte del processo di installazione e il programma di installazione distribuisce il server come indicato nella topologia.

<div>

## <a name="lync-server-planning-tool"></a>Strumento di pianificazione di Lync Server

Lo strumento di pianificazione prende le risposte alle domande nello strumento e genera una topologia basata sulle linee guida e le procedure consigliate di Lync Server. Offre anche diverse visualizzazioni di una distribuzione in base alle risposte. Mostra sia una visualizzazione globale di tutti i siti, sia i siti centrali che i siti di succursale, nonché visualizzazioni dettagliate che mostrano i server e altri componenti di ogni sito.

L'uso dello strumento di pianificazione non consente di eseguire il commit di una specifica distribuzione o di avviare processi. In realtà, l'esecuzione dello strumento di pianificazione anche prima di avere un piano fisso in mente può essere un modo molto istruttivo per comprendere i tipi di domande che è necessario considerare nel processo di pianificazione.

Puoi eseguire lo strumento di pianificazione più volte, rispondendo alle domande in modo diverso e confrontando i risultati. Se si ha un progetto di cui si è soddisfatti per la maggior parte, ma è necessario apportare modifiche, è possibile tornare allo strumento di pianificazione, caricare la struttura e apportare le modifiche. È necessario circa 15 minuti per completare lo strumento di pianificazione una sola volta.

Dopo aver soddisfatto, è possibile usare lo strumento pianificazione per creare un diagramma della distribuzione pianificata. Puoi usare questo diagramma durante la creazione della distribuzione in Generatore di topologie.

<div>


> [!NOTE]  
> Lo strumento di pianificazione incluso in questo rilascio di Lync Server 2013 è una versione prerelease. Tieni presente che i numeri di pianificazione della capacità nello strumento di pianificazione sono preliminari e non sono supportati per la versione finale.



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a>Generatore di topologia di Lync Server

Dopo aver deciso il piano di distribuzione, è possibile usare generatore di topologia per iniziare la distribuzione. Al termine, puoi usare generatore di topologia per convalidare la topologia e quindi, se passa, puoi pubblicare la topologia. Quando si pubblica la topologia, Lync Server inserisce la topologia in Central Management store, che viene creata in questo momento, se non esiste già. Quando si installa Lync Server in ogni server della distribuzione, il server legge la topologia da Central Management store e si installa per adattarsi al proprio ruolo nella distribuzione.

In alternativa, se si ha familiarità con Lync Server e si ha bisogno di indicazioni meno prescrittivi, è possibile ignorare lo strumento di pianificazione e usare le procedure guidate in Generatore di topologia per la progettazione iniziale della distribuzione e anche per la procedura di convalida e pubblicazione.

L'uso di generatore di topologia per pianificare e pubblicare una topologia è un passaggio obbligatorio. Non è possibile ignorare il generatore di topologie e installare Lync Server singolarmente nei server della distribuzione. Ogni server deve leggere la topologia da una topologia convalidata e pubblicata nell'Central Management store.

</div>

<div>

## <a name="high-level-planning-process"></a>Processo di pianificazione ad alto livello

Per pianificare la distribuzione di Lync Server è consigliabile seguire la procedura generale seguente per l'uso della documentazione e dello strumento di pianificazione.

1.  Se si ha familiarità con le versioni precedenti di Lync Server, leggere le [nuove caratteristiche di Lync server 2013](lync-server-2013-new-features.md) per familiarizzare con le nuove caratteristiche e i requisiti di lync Server 2013.

2.  Leggere gli altri argomenti in questa sezione della documentazione: [nozioni di base sulla topologia che è necessario conoscere prima di pianificare Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), [fare riferimento a topologie in Lync Server 2013](lync-server-2013-reference-topologies.md), [decisioni di pianificazione iniziali per Lync Server 2013](lync-server-2013-initial-planning-decisions.md)e [client per Lync Server 2013](lync-server-2013-clients.md). Prendere nota delle decisioni di pianificazione rappresentate nelle [topologie di riferimento in Lync Server 2013](lync-server-2013-reference-topologies.md).

3.  Ora che si ha familiarità con le caratteristiche di Lync Server e i tipi di domande a cui rispondere, eseguire lo strumento di pianificazione e visualizzare la topologia risultante e i relativi dettagli. Verificare che la topologia corrisponda ai requisiti univoci per l'organizzazione.

4.  Se sono presenti particolari carichi di lavoro o funzionalità di cui si è interessati o che è necessario conoscere, leggere le sezioni appropriate della [pianificazione per Lync Server 2013](lync-server-2013-planning.md).

5.  Eseguire di nuovo lo strumento di pianificazione. È possibile iniziare con la distribuzione creata al passaggio 3 e modificare i risultati oppure ricominciare dall'inizio.
    
    Se necessario, eseguire la terza volta lo strumento di pianificazione e ripetere finché non si soddisfa l'output.

6.  Dopo aver finalizzato il piano della topologia, usare lo strumento pianificazione per creare e stampare un diagramma di Visio della topologia. È possibile usare questa stampa mentre si lavora con generatore di topologie per immettere la topologia.

7.  Prima di iniziare la distribuzione, leggere [determinare i requisiti di sistema per Lync server 2013](lync-server-2013-determining-your-system-requirements.md) e [determinare i requisiti di infrastruttura per Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) per familiarizzare con i prerequisiti e l'infrastruttura necessaria per Lync Server. Assicurarsi inoltre di aver letto tutte le sezioni della [pianificazione per Lync Server 2013](lync-server-2013-planning.md) che si applicano ai carichi di lavoro e alle caratteristiche che si prevede di distribuire.

</div>

<div>

## <a name="migrating-from-previous-versions"></a>Migrazione da versioni precedenti

Se si esegue la migrazione a Lync Server da una versione precedente, vedere la documentazione relativa alla [migrazione](migration.md) per istruzioni specifiche per la migrazione e la distribuzione.

</div>

</div>

<span> </span>

</div>

</div>

</div>

