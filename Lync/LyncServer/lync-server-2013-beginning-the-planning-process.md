---
title: 'Lync Server 2013: inizio del processo di pianificazione'
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
ms.openlocfilehash: d436da8efa7194c2a0a341f4bed7794e532446ec
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513040"
---
# <a name="beginning-the-planning-process-for-lync-server-2013"></a>Inizio del processo di pianificazione per Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-24_

Durante la pianificazione di una distribuzione di Unified Communications locale può sembrare intimidatorio, Lync Server fornisce due strumenti utili per:

  - **Lo strumento di pianificazione** è una procedura guidata che presenta una serie di domande relative all'organizzazione, alle funzionalità di Lync Server che si desidera abilitare e alle esigenze di pianificazione della capacità. Viene quindi creata una topologia di distribuzione consigliata in base alle risposte fornite e viene generato un diagramma di Microsoft Visio della distribuzione.

  - **Generatore di topologie** è un componente di installazione di Lync Server. Per creare, modificare e pubblicare la topologia pianificata, è possibile utilizzare Generatore di topologie. Convalida inoltre la topologia prima di iniziare le installazioni del server. Quando si installa Lync Server nei singoli server, i server leggono la topologia pubblicata come parte del processo di installazione e il server viene distribuito come indicato nella topologia.

<div>

## <a name="lync-server-planning-tool"></a>Strumento di pianificazione di Lync Server

Lo strumento di pianificazione accetta le risposte alle domande nello strumento e genera una topologia basata sulle linee guida e le procedure consigliate di Lync Server. Fornisce inoltre diverse visualizzazioni di una distribuzione in base alle risposte fornite. Mostra una visualizzazione globale dei siti, ossia con siti centrali e siti di succursale, e visualizzazioni dettagliate dei server e di altri componenti in ogni sito.

L'esecuzione dello strumento di pianificazione non consente di eseguire una distribuzione specifica o di avviare eventuali processi. In effetti, l'esecuzione dello strumento di pianificazione anche prima di avere un piano aziendale in mente può essere un modo molto istruttivo per comprendere i tipi di domande che è necessario considerare nel processo di pianificazione.

È possibile eseguire lo strumento di pianificazione più volte, rispondere a domande in modo diverso e confrontare i risultati. Se si dispone di un progetto di cui si è soddisfatti per la maggior parte ma che è necessario apportare modifiche, è possibile tornare allo strumento di pianificazione, caricare la struttura e apportare le modifiche. Il completamento dello strumento di pianificazione richiede circa 15 minuti.

Una volta soddisfatti, è possibile utilizzare lo strumento di pianificazione per creare un diagramma della distribuzione pianificata. È possibile utilizzare questo diagramma durante la creazione della distribuzione in Generatore di topologie.

<div>


> [!NOTE]  
> Lo strumento di pianificazione incluso con questa versione di Lync Server 2013 è una versione definitiva. Si noti che i numeri relativi alla pianificazione della capacità nello strumento di pianificazione sono preliminari e non sono supportati per la versione finale.



</div>

</div>

<div>

## <a name="lync-server-topology-builder"></a>Generatore di topologie di Lync Server

Dopo aver deciso il piano di distribuzione, è possibile utilizzare Generatore di topologie per iniziare la distribuzione. Al termine, è possibile utilizzare il generatore di topologie per convalidare la topologia e quindi, se la si passa, si può pubblicare la topologia. Quando si pubblica la topologia, Lync Server inserisce la topologia nell'archivio di gestione centrale, che viene creata in questo momento, se non esiste già. Quando si installa Lync Server in ogni server della distribuzione, il server legge la topologia dall'archivio di gestione centrale e si installa per adattarsi al proprio ruolo nella distribuzione.

In alternativa, se si ha familiarità con Lync Server e si ha bisogno di linee guida meno prescrittivo, è possibile ignorare lo strumento di pianificazione e utilizzare le procedure guidate in Generatore di topologie per la progettazione iniziale della distribuzione e anche per la procedura di convalida e pubblicazione.

L'utilizzo di generatore di topologie per la pianificazione e la pubblicazione di una topologia è un passaggio obbligatorio. Non è possibile ignorare il generatore di topologie e installare Lync Server singolarmente sui server della distribuzione. Ogni server deve leggere la topologia da una topologia pubblicata convalidata nell'archivio di gestione centrale.

</div>

<div>

## <a name="high-level-planning-process"></a>Processo generale di pianificazione

Per pianificare la distribuzione di Lync Server, è consigliabile eseguire la procedura generale seguente per l'utilizzo sia della documentazione sia dello strumento di pianificazione.

1.  Se si ha familiarità con le versioni precedenti di Lync Server, leggere le [nuove funzionalità in Lync server 2013](lync-server-2013-new-features.md) per acquisire familiarità con le nuove funzionalità e i requisiti di lync Server 2013.

2.  Leggere gli altri argomenti in questa sezione della documentazione: [nozioni di base sulla topologia che è necessario conoscere prima di pianificare Lync server 2013](lync-server-2013-topology-basics-you-must-know-before-planning.md), le [topologie di riferimento in Lync Server 2013](lync-server-2013-reference-topologies.md), [le decisioni di pianificazione iniziali per Lync Server 2013](lync-server-2013-initial-planning-decisions.md)e [i client per Lync Server 2013](lync-server-2013-clients.md). Prendere nota delle decisioni di pianificazione rappresentate nelle [topologie di riferimento in Lync Server 2013](lync-server-2013-reference-topologies.md).

3.  Dopo aver acquisito familiarità con le funzionalità di Lync Server e i tipi di domande che devono essere risolte, eseguire lo strumento di pianificazione e visualizzare la topologia risultante e i relativi dettagli. Assicurarsi che la topologia sia adatta ai requisiti specifici dell'organizzazione.

4.  Se sono presenti particolari carichi di lavoro o funzionalità che sono interessati o che è necessario conoscere, leggere le sezioni appropriate di [pianificazione per Lync Server 2013](lync-server-2013-planning.md).

5.  Eseguire di nuovo lo strumento di pianificazione. È possibile iniziare con la distribuzione creata nel passaggio 3 e modificare i risultati oppure ricominciare daccapo.
    
    Se necessario, eseguire lo strumento di pianificazione una terza volta e ripetere fino a quando non si è soddisfatti dell'output.

6.  Dopo aver completato il piano di topologia, utilizzare lo strumento di pianificazione per creare e stampare un diagramma di Visio della topologia. È possibile utilizzare questa stampa durante l'utilizzo di generatore di topologie per immettere la topologia.

7.  Prima di iniziare la distribuzione, leggere [determinare i requisiti di sistema per Lync server 2013](lync-server-2013-determining-your-system-requirements.md) e [determinare i requisiti dell'infrastruttura per Lync Server 2013](lync-server-2013-determining-your-infrastructure-requirements.md) per acquisire familiarità con i prerequisiti e l'infrastruttura necessaria per Lync Server. È inoltre necessario leggere tutte le sezioni di [pianificazione per Lync Server 2013](lync-server-2013-planning.md) che si applicano ai carichi di lavoro e alle caratteristiche che si intende distribuire.

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

