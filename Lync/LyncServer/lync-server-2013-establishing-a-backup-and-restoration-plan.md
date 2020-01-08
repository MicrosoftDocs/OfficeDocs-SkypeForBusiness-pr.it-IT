---
title: 'Lync Server 2013: creazione di un piano di backup e ripristino'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b3516e63a7cbada4a89fad3540406e38b299fef
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974551"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a>Creazione di un piano di backup e ripristino per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-17_

La creazione di un piano di backup e ripristino prevede i passaggi seguenti:

  - Sviluppo del piano.

  - Implementazione del piano.

  - Manutenzione del piano.

<div>

## <a name="developing-a-backup-and-restoration-plan"></a>Sviluppo di un piano di backup e ripristino

Dopo aver sviluppato la strategia di backup e ripristino per Lync Server, è possibile usarla per documentare un piano di backup e ripristino dettagliato. Il piano deve trasmettere chiaramente le priorità e i requisiti per il backup dei dati e delle impostazioni. È possibile usare le informazioni disponibili per [stabilire una strategia di backup e ripristino per Lync server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) e i fogli di lavoro in fogli di lavoro di [backup e ripristino per Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) per facilitare la documentazione della propria strategia. Il piano deve inoltre contenere criteri per decidere quando e come ripristinare il servizio.

Man mano che sviluppi il piano, devi prendere in considerazione e tenere conto di quanto segue:

  - Come ripristinare i server nel nuovo hardware.

  - Come si recupereranno i servizi che richiedono un'azione da parte di più aree o reparti aziendali.

  - Come è possibile acquisire rapidamente i server di riserva.

  - Il tempo necessario per il ripristino usando la strategia. Considera i requisiti dell'organizzazione per l'obiettivo del tempo di recupero (RTO).

Modificare le procedure di backup e ripristino in questo argomento, aggiungendo ed eliminando le procedure appropriate per riflettere i server e i componenti della distribuzione. È anche possibile aggiungere dettagli appropriati, ad esempio la pianificazione del backup, alle procedure appropriate per verificare che le informazioni non vengano trascurate.

<div>


> [!NOTE]  
> È buona norma creare script per il maggior numero possibile di passaggi, per garantire la qualità e la riproducibilità delle procedure.



</div>

Nel piano specificare chi è responsabile della revisione del piano, che è responsabile del test e della convalida di eventuali nuove procedure o strumenti e che deve approvare le eventuali modifiche apportate al piano e alle procedure correlate.

Per assicurarti che il piano di backup e ripristino soddisfi pienamente tutti gli obiettivi e le priorità stabiliti, Ottieni l'approvazione dei responsabili decisionali e delle decisioni tecniche aziendali appropriate prima di implementare il piano.

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a>Implementazione del piano di backup e ripristino

L'implementazione di un piano di backup e ripristino richiede i passaggi seguenti:

  - Testare e convalidare il piano.

  - Comunicare il piano.

  - Convalida delle operazioni di backup e ripristino.

<div>

## <a name="testing-and-validating-the-plan"></a>Test e convalida del piano

Le procedure descritte in questo articolo sono state testate e convalidate in un ambiente lab. Per assicurarsi che queste o altre procedure funzionino nell'ambiente, è consigliabile testare e convalidare ogni procedura da implementare. Completare i test e la convalida prima di inviare il piano per l'approvazione finale.

</div>

<div>

## <a name="communicating-the-plan"></a>Comunicare il piano

Il piano di backup e ripristino deve descrivere chiaramente chi implementa le procedure e le istruzioni dettagliate per l'esecuzione delle procedure. È necessario assicurarsi che tutti i responsabili di qualsiasi aspetto del backup e del ripristino comprendano il piano, il modo in cui devono essere implementati e il loro ruolo. Include tutti i requisiti di implementazione per i seguenti:

  - Backup di pool e server.

  - Ripristino del servizio.

**Backup di pool e server**

Il piano di backup e ripristino deve includere tutte le informazioni necessarie per completare le procedure di backup su base continuativa. Le informazioni principali da comunicare ai membri del team responsabili includono le seguenti:

  - Team o Person (specificato come singolo o ruolo) responsabile del backup di ogni server.

  - Pianificazioni specifiche per il backup di ogni server.

  - Percorsi di backup per ogni tipo di dati (impostazioni, database e condivisioni di file).

  - Procedure di backup da usare, inclusi gli strumenti necessari per completare ogni procedura.

  - Informazioni necessarie per completare i backup, come descritto in fogli di lavoro di [backup e ripristino per Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

  - Metodi di convalida da usare per verificare che i dati e le impostazioni siano opportunamente sostenuti e disponibili per il ripristino, che può includere controlli periodici e ripristini di test.

**Ripristino del servizio**

Il piano di backup e ripristino deve includere tutte le informazioni necessarie per il ripristino del servizio, nel caso in cui uno o più server verifichino una perdita che rende il servizio non disponibile. Le informazioni principali da comunicare ai membri del team responsabili includono le seguenti:

  - Team o Person (specificato come un singolo o un ruolo) responsabile per determinare quando è necessario il ripristino del servizio e le procedure da usare per ripristinare il servizio e anche il team o la persona responsabile dell'implementazione delle procedure per ogni scenario di ripristino.

  - Criteri per determinare quali procedure di ripristino sono più appropriate per una specifica situazione.

  - Stime temporali per il ripristino dell'obiettivo del tempo di servizio e di ripristino (RTO) in ogni scenario di ripristino.

  - Procedure di ripristino da usare, inclusi gli strumenti necessari per completare ogni procedura.

  - Informazioni necessarie per ripristinare dati e impostazioni. I fogli di lavoro sono disponibili in fogli di lavoro di [backup e ripristino per Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a>Convalida delle operazioni di backup e ripristino

Dopo aver completato gli sforzi iniziali di backup nell'ambiente di produzione e a intervalli specificati, come descritto nel piano di backup e ripristino, è necessario verificare quanto segue:

  - I backup si verificano come richiesto.

  - I dati e le impostazioni di cui è stato eseguito il backup sono accessibili.

  - Le procedure di ripristino possono essere eseguite entro gli orari di recupero degli obiettivi temporali (RTO) specificati nel piano di backup e ripristino e i risultati soddisfano tutti i requisiti aziendali.

  - I fogli di lavoro di backup sono stati completati e verificati e archiviati in una posizione sicura. Questi fogli di lavoro sono disponibili in fogli di lavoro di [backup e ripristino per Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

  - Le procedure di ripristino sono state testate e verificate per funzionare come previsto, come specificato nel piano di backup e ripristino.

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a>Manutenzione del piano di backup e ripristino

Una topologia di Lync Server è un ambiente dinamico che viene modificato con l'organizzazione. Rivalutare il piano di backup e ripristino Man mano che l'organizzazione cambia e rivederla periodicamente per verificare che continui a soddisfare le esigenze della propria azienda.

</div>

</div>

<span> </span>

</div>

</div>

</div>

