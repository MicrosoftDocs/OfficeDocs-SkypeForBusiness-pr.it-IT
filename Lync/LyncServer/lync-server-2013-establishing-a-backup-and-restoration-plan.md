---
title: 'Lync Server 2013: creazione di un piano di backup e ripristino'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Establishing a backup and restoration plan
ms:assetid: 9f562ef1-3804-41e2-b3e4-d45b2e8c63c9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh202183(v=OCS.15)
ms:contentKeyID: 51541499
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bbe142d697fc3d95772fb2d4ca758b8550054a8e
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42042523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="establishing-a-backup-and-restoration-plan-for-lync-server-2013"></a>Creazione di un piano di backup e ripristino per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-17_

La creazione di un piano di backup e ripristino prevede i passaggi seguenti:

  - Sviluppo del piano.

  - Implementazione del piano.

  - Gestione del piano.

<div>

## <a name="developing-a-backup-and-restoration-plan"></a>Sviluppo di un piano di backup e ripristino

Dopo aver sviluppato la strategia di backup e ripristino per Lync Server, utilizzarla per documentare un piano di backup e ripristino dettagliato. Il piano deve comunicare chiaramente le priorità e i requisiti per il backup di dati e impostazioni. È possibile utilizzare le informazioni contenute nella [creazione di una strategia di backup e ripristino per Lync server 2013](lync-server-2013-establishing-a-backup-and-restoration-strategy.md) e fogli di lavoro in fogli di lavoro di [backup e ripristino per Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md) per facilitare la documentazione della propria strategia. Il piano deve inoltre contenere criteri in base ai quali stabilire quando e come ripristinare il servizio.

Quando si sviluppa il piano, è necessario prendere in considerazione e tenere conto di quanto segue:

  - La modalità di recupero dei server nel nuovo hardware.

  - La modalità di recupero dei servizi per i quali è necessario l'intervento di più aree aziendali o reparti.

  - La modalità di acquisizione rapida di server di riserva.

  - Il tempo necessario per il ripristino secondo la strategia in questione Considerare i requisiti dell'organizzazione per l'obiettivo del tempo di ripristino (RTO).

Modificare le procedure di backup e ripristino in questo argomento, aggiungendo ed eliminando le procedure appropriate, in modo da riflettere i server e i componenti della distribuzione. È inoltre possibile aggiungere informazioni appropriate, ad esempio la pianificazione di backup, alle procedure appropriate per assicurarsi che le informazioni non vengano trascurate.

<div>


> [!NOTE]  
> È consigliabile creare script per il maggior numero possibile di passaggi, per garantire la qualità e la riproducibilità delle procedure.



</div>

Nel piano specificare chi è responsabile della revisione del piano, che è responsabile del testing e della convalida di qualsiasi nuova procedura o strumento e che deve approvare le modifiche apportate al piano e alle relative procedure.

Per assicurarsi che il piano di backup e ripristino soddisfi pienamente tutti gli obiettivi e le priorità stabiliti, ottenere l'approvazione dei responsabili decisionali e delle decisioni tecniche aziendali appropriate nell'organizzazione prima di implementare il piano.

</div>

<div>

## <a name="implementing-the-backup-and-restoration-plan"></a>Implementazione del piano di backup e ripristino

L'implementazione di un piano di backup e ripristino richiede i passaggi seguenti:

  - Test e convalida del piano.

  - Comunicazione del piano.

  - Convalida delle operazioni di backup e ripristino.

<div>

## <a name="testing-and-validating-the-plan"></a>Test e convalida del piano

Le procedure descritte in questo articolo sono state testate e convalidate in un ambiente lab. Per assicurarsi che queste o altre procedure funzionino nell'ambiente in uso, è consigliabile testare e convalidare ogni procedura che si intende implementare. Completare i test e la convalida prima di inviare il piano per l'approvazione finale.

</div>

<div>

## <a name="communicating-the-plan"></a>Comunicazione del piano

Il piano di backup e ripristino deve descrivere chiaramente chi implementa le procedure e le istruzioni dettagliate per l'esecuzione delle procedure. È necessario assicurarsi che tutti i responsabili di qualsiasi aspetto del backup e del ripristino comprendano il piano, il modo in cui deve essere implementato e il relativo ruolo. Sono inclusi tutti i requisiti di implementazione per gli elementi seguenti:

  - Backup del pool e del server.

  - Ripristino del servizio.

**Backup di pool e server**

Nel piano di backup e ripristino devono essere disponibili tutte le informazioni necessarie per l'esecuzione delle procedure di backup con regolarità costante. Le informazioni principali da comunicare ai membri del team dei responsabili sono le seguenti:

  - Team o Person (specificato come singolo o ruolo) responsabile del backup di ogni server.

  - Pianificazioni specifiche per il backup di ogni server.

  - Percorsi di backup per ogni tipo di dati (impostazioni, database e condivisioni di file).

  - Procedure di backup da utilizzare, compresi gli strumenti necessari per il completamento di ogni procedura.

  - Informazioni necessarie per completare i backup, come indicato nei [fogli di lavoro per il backup e il ripristino di Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

  - Metodi di convalida da utilizzare per garantire che i dati e le impostazioni siano adeguatamente sottoposti a backup e disponibili per il ripristino, che possono includere controlli periodici e ripristini dei test.

**Ripristino del servizio**

Il piano di backup e ripristino deve includere tutte le informazioni necessarie per il ripristino del servizio, nel caso in cui uno o più server verifichino una perdita che rende il servizio non disponibile. Le informazioni principali da comunicare ai membri del team dei responsabili sono le seguenti:

  - Team o persona (individuo o ruolo) responsabile di determinare quando è necessario il ripristino del servizio e le procedure da utilizzare per il ripristino, nonché il team o la persona responsabile dell'implementazione delle procedure per ogni scenario di ripristino.

  - Criteri per stabilire le procedure di ripristino più appropriate per una situazione specifica.

  - Stime temporali per il ripristino dell'obiettivo del tempo di ripristino e del servizio (RTO) in ogni scenario di ripristino.

  - Procedure di ripristino da seguire e strumenti necessari per l'esecuzione di ogni procedura.

  - Informazioni necessarie per il ripristino di dati e impostazioni. I fogli di lavoro vengono forniti nei fogli di lavoro [per il backup e il ripristino di Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

</div>

<div>

## <a name="validating-backup-and-restoration-operations"></a>Convalida delle operazioni di backup e ripristino

Dopo aver eseguito le operazioni di backup iniziali nell'ambiente di produzione a intervalli specifici, secondo quanto indicato nel piano di backup e ripristino, è necessario verificare che:

  - Il backup venga eseguito come richiesto.

  - I dati e le impostazioni di backup sono accessibili.

  - Le procedure di ripristino possono essere eseguite entro gli orari degli obiettivi del tempo di ripristino (RTO) specificati nel piano di backup e ripristino e i risultati soddisfano tutti i requisiti aziendali.

  - I fogli di lavoro di backup siano stati compilati, verificati e archiviati in un luogo sicuro. Questi fogli di lavoro sono disponibili nei fogli di lavoro di [backup e ripristino per Lync Server 2013](lync-server-2013-backup-and-restoration-worksheets.md).

  - Il funzionamento delle procedure di ripristino sia stato sottoposto a test e verificato come previsto, in base a quanto specificato nel piano di backup e ripristino.

</div>

</div>

<div>

## <a name="maintaining-the-backup-and-restoration-plan"></a>Gestione del piano di backup e ripristino

Una topologia di Lync Server è un ambiente dinamico che cambia con l'organizzazione. Rivalutare il piano di backup e ripristino come cambia l'organizzazione e rivederlo periodicamente per assicurarsi che continui a soddisfare le esigenze della propria azienda.

</div>

</div>

<span> </span>

</div>

</div>

</div>

