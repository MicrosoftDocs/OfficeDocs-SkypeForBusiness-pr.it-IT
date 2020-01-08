---
title: 'Lync Server 2013: utilizzo di report di monitoraggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Using Monitoring Reports
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558662(v=OCS.15)
ms:contentKeyID: 48184480
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6b7c1e70a47e3f3043215e1d16e1f01bfec4b677
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978952"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-monitoring-reports-in-lync-server-2013"></a>Uso di report di monitoraggio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-21_

Lync Server 2013 include un set di report standard pubblicati da Microsoft SQL Server Reporting Service. Questi report, accessibili tramite un Web browser, consentono l'utilizzo, le informazioni di diagnostica delle chiamate e le informazioni sulla qualità dei contenuti multimediali, tutte basate sui record di registrazione dei dettagli delle chiamate (CDR) e la qualità dell'esperienza (QoE) archiviati nei database CDR e QoE.

Per usare questi report, è necessario installare i report di monitoraggio in un computer in cui è in corso un'istanza di SQL Server.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [L'uso del dashboard di monitoraggio in Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   offre agli amministratori una rapida panoramica dell'integrità del sistema e dell'uso del sistema.

  - [I report sull'utilizzo del sistema in Lync Server 2013](lync-server-2013-system-usage-reports.md)   offrono informazioni sull'uso del sistema in base ai dati CDR raccolti da Lync Server.

  - [I report di diagnostica delle chiamate (per utente) in Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   offrono informazioni per utente sulle sessioni peer-to-peer e conferenze non riuscite.

  - [I report di diagnostica delle chiamate in Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   offrono informazioni di riepilogo e dati di diagnostica per sessioni peer-to-peer e conferenze non riuscite.

  - [Report di diagnostica di qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   fornisce informazioni sulla qualità delle chiamate, nonché informazioni di diagnostica e risoluzione dei problemi per le chiamate non riuscite.

</div>

<div>

## <a name="locating-records"></a>Individuazione di record

I report di monitoraggio mostrano solo un numero limitato di record sullo schermo in qualsiasi momento. Il numero effettivo di record visualizzati in uno schermo varia a seconda del report. Per visualizzare i record che non sono attualmente visualizzati sullo schermo, è possibile usare il controllo avanti e indietro standard (disponibile nella barra degli strumenti di ogni report) che consente di eseguire la pagina dei dati. È anche possibile passare rapidamente alla prima pagina o all'ultima pagina del set di dati.

Oltre a usare i controlli avanti e indietro, è anche possibile passare a una pagina qualsiasi del DataSet digitando semplicemente il numero di pagina nella casella **pagina corrente** e quindi premere INVIO.

Oltre a fornire la possibilità di paginare i dati, ogni report include anche la limitata capacità di trovare record. Per trovare i record in base a un valore specifico, digitare tale valore nella casella **trova** e quindi fare clic su **trova**. Il report inizia la ricerca nei dati e si arresta nella prima istanza del valore immesso nella casella **trova** . Per trovare il record successivo che soddisfa i criteri di ricerca, fare clic su **Avanti**.

Come indicato, i report di monitoraggio contengono solo le funzioni di ricerca più basilari. Ad esempio, non è possibile specificare il campo in cui deve essere trovato il valore. Il meccanismo di ricerca cerca automaticamente i valori corrispondenti in tutti i campi di ogni record. Non è possibile usare i caratteri jolly nelle ricerche e tutte le ricerche cercano valori parziali. Ciò significa che se si cerca 111 la ricerca restituisce il valore 111 insieme ai valori 11100, 811, 3112, 611A5B e tutti gli altri campi che includono il valore 111 in un punto qualsiasi all'interno di tale campo.

Ogni report è configurato per visualizzare un set predefinito di record. Per impostazione predefinita, ad esempio, il report di registrazione dell'utente Mostra le attività di registrazione degli utenti per la settimana passata. In alcuni casi, potrebbe verificarsi un report che restituisce nessun record. In questo caso, significa che non sono state registrate registrazioni utente nell'ultima settimana. Se viene visualizzato il messaggio "nessun risultato corrisponde ai filtri dei report", provare a modificare i valori di filtro (ad esempio, cambiare il periodo di tempo dell'ultimo mese anziché la settimana precedente) e rieseguire la query. Per informazioni dettagliate, vedere la sezione "filtro dei dati" più avanti in questo argomento.

</div>

<div>

## <a name="filtering-data"></a>Filtrare i dati

Ci saranno probabilmente momenti in cui si vuole esaminare solo un sottoinsieme di record. Ad esempio, solo le sessioni peer-to-peer invece di sessioni peer-to-peer e conferenze. Allo stesso modo, ci saranno momenti in cui è necessario ridurre il numero di record restituiti. Per impostazione predefinita, un report può visualizzare solo i primi record di 1.000 in un set di dati. Per risolvere questi problemi, la maggior parte dei report include una serie di opzioni di filtro. Ad esempio, se si vogliono visualizzare solo i record per l'intervallo di tempo compreso tra il 1 ° gennaio 2011 e il 15 gennaio 2011, è possibile immettere il 1 ° gennaio 2011 nella casella **da** e il 15 gennaio 2011 nella casella **a** . Se si fa clic su **Visualizza report**, i dati restituiti saranno limitati alle attività che hanno avuto luogo tra il 1 ° gennaio 2011 e il 15 gennaio 2011.

I filtri disponibili variano a seconda del report che si sta visualizzando. Per informazioni dettagliate su un report specifico, vedere l'argomento della Guida relativo al report.

</div>

<div>

## <a name="exporting-data"></a>Esportazione di dati

I report di monitoraggio includono almeno due modi diversi per esportare i dati inclusi in un report. È possibile usare l'opzione **Esporta** nella barra degli strumenti visualizzata nella parte superiore di ogni report. Per usare questa opzione, selezionare il formato di esportazione desiderato nell'elenco a discesa **selezionare un formato** . I formati seguenti sono disponibili:

  - File XML con i dati del report

  - CSV (delimitato da virgola)

  - File Acrobat (PDF)

  - MHTML (archivio Web)

  - Excel

  - File TIFF

  - Word

Dopo aver selezionato un formato, fare clic su **Esporta**. Quando viene visualizzata la finestra di dialogo **Download file** , fare clic su **Salva**. Nella finestra di dialogo **Salva con** nome selezionare una cartella di destinazione e quindi fare clic su **Salva**.

Se è installato Microsoft OneNote, è anche possibile copiare i dati del report in OneNote. A questo scopo, fai clic con il **pulsante destro del mouse sulla barra** degli strumenti. Nella finestra di dialogo **Seleziona posizione in OneNote** selezionare la sezione in OneNote in cui si vogliono copiare i dati e quindi fare clic su **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

