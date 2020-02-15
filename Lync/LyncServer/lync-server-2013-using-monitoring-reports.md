---
title: 'Lync Server 2013: utilizzo di report di monitoraggio'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Using Monitoring Reports
ms:assetid: 733577d0-c70f-4c70-ab7b-59b89fb495a8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558662(v=OCS.15)
ms:contentKeyID: 48184480
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c37cd0f96ea0dd8e3fa63a851c3c93caf5988c7d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42044278"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="using-monitoring-reports-in-lync-server-2013"></a>Utilizzo di report di monitoraggio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-21_

Lync Server 2013 include un insieme di report standard pubblicati da Microsoft SQL Server Reporting Services. Questi rapporti, cui è possibile accedere utilizzando un browser, contengono informazioni sull'utilizzo, di diagnostica della chiamate e sulla qualità multimediale, tutte basate su record di registrazione dettagli chiamata e QoE (Quality of Experience) archiviati nei database CDR e QoE.

Per utilizzare questi rapporti, è necessario installare i report di monitoraggio in un computer che esegue un'istanza di SQL Server.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [L'utilizzo del dashboard di monitoraggio in Lync Server 2013](lync-server-2013-using-the-monitoring-dashboard.md)   fornisce agli amministratori una breve panoramica dell'integrità del sistema e dell'utilizzo del sistema.

  - [I report sull'utilizzo del sistema in Lync Server 2013](lync-server-2013-system-usage-reports.md)   offrono informazioni sull'utilizzo del sistema in base ai dati di registrazione dettagli chiamata raccolti da Lync Server.

  - [Rapporti di diagnostica chiamate (per utente) in Lync Server 2013](lync-server-2013-call-diagnostic-reports-per-user.md)   fornisce informazioni per utente sulle sessioni peer-to-peer e di conferenza non riuscite.

  - [Rapporti di diagnostica delle chiamate in Lync Server 2013](lync-server-2013-call-diagnostic-reports.md)   fornisce informazioni di riepilogo e dati di diagnostica per le sessioni peer-to-peer e di conferenza non riuscite.

  - [Rapporti di diagnostica qualità multimediale in Lync Server 2013](lync-server-2013-media-quality-diagnostic-reports.md)   fornisce informazioni sulla qualità delle chiamate e informazioni di diagnostica e risoluzione dei problemi per le telefonate non riuscite.

</div>

<div>

## <a name="locating-records"></a>Individuazione dei record

I rapporti di monitoraggio mostrano solo un numero limitato di record sullo schermo per volta. Il numero effettivo di record visualizzati sullo schermo varia a seconda del rapporto. Per visualizzare i record non mostrati sullo schermo, è possibile utilizzare il controllo Avanti o Indietro standard, disponibile sulla barra degli strumenti di ogni rapporto, che consente di scorrere i dati. È inoltre possibile passare rapidamente alla prima pagina o all'ultima pagina del set di dati.

Oltre a utilizzare i controlli Avanti e Indietro, è possibile passare a qualsiasi pagina nel set di dati semplicemente digitando il numero di pagina nella casella **Pagina corrente** e quindi premendo INVIO.

Oltre a consentire di scorrere i dati, ogni rapporto include anche caratteristiche limitate per trovare i record. Per trovare record in base a un valore specificato, digitare il valore nella casella **Trova** e quindi fare clic su **Trova**. Viene avviata la ricerca nei dati del rapporto e viene arrestata alla prima istanza del valore immesso nella casella **Trova**. Per trovare il record successivo che soddisfa i criteri di ricerca, fare clic su **Avanti**.

Come accennato, i rapporti di monitoraggio offrono solo funzioni di ricerca di base. Non è ad esempio possibile specificare il campo in cui deve essere presente il valore. Il meccanismo di ricerca esegue automaticamente la ricerca di valori corrispondenti in ogni campo di ogni record. Non è possibile utilizzare caratteri jolly nelle ricerche e in tutte le ricerche vengono cercati i valori parziali. Di conseguenza, se si cerca 111, non verrà trovato solo il valore 111, ma anche i valori 11100, 811, 3112, 611A5B e tutti gli altri campi che includono il valore 111 in qualsiasi posizione.

Ogni rapporto è configurato per visualizzare un insieme predefinito di record. Ad esempio, per impostazione predefinita, in Rapporto registrazione utenti vengono visualizzate le attività di registrazione degli utenti per l'ultima settimana. In alcuni casi, ciò può produrre un rapporto che non restituisce alcun record. In questo caso, significa che nell'ultima settimana non è stata effettuata alcuna registrazione di utenti. Se viene visualizzato il messaggio "Nessun risultato corrisponde ai filtri del rapporto", provare a modificare i valori del filtro, ad esempio modificando il periodo di tempo dall'ultima settimana all'ultimo mese, e quindi eseguire di nuovo la query. Per informazioni dettagliate, vedere la sezione "Applicazione di filtri ai dati" più avanti in questo argomento.

</div>

<div>

## <a name="filtering-data"></a>Applicazione di filtri ai dati

In alcuni casi può essere utile cercare solo un sottoinsieme di record, ad esempio solo le sessioni peer-to-peer anziché le sessioni peer-to-peer e di conferenza. Analogamente, in altri casi sarà necessario ridurre il numero di record restituiti. Per impostazione predefinita, un rapporto può visualizzare solo i primi 1.000 record in un set di dati. Per risolvere questi problemi, la maggior parte dei rapporti include un certo numero di opzioni di filtro. Se, ad esempio, si desidera visualizzare solo i record per il periodo di tempo compreso tra l'1 gennaio 2011 e il 15 gennaio 2011, è possibile immettere 1 gennaio 2011 nella casella **Da** e 15 gennaio 2011 nella casella **A**. Se quindi si fa clic su **Visualizza rapporto**, i dati restituiti saranno limitati alle attività avvenute dall'1 gennaio 2011 al 15 gennaio 2011.

I filtri disponibili dipendono dal rapporto visualizzato. Per informazioni dettagliate su un rapporto specifico, vedere l'argomento della Guida relativo al rapporto desiderato.

</div>

<div>

## <a name="exporting-data"></a>Esportazione di dati

I rapporti di monitoraggio consentono di esportare i dati inclusi in un rapporto in almeno due modi diversi. È possibile utilizzare l'opzione **Esporta** sulla barra degli strumenti visualizzata nella parte superiore di ogni rapporto. Per utilizzare questa opzione, selezionare innanzitutto il formato di esportazione desiderato nell'elenco a discesa **Selezionare un formato**. Sono disponibili i formati seguenti:

  - File XML con dati del rapporto

  - CSV (delimitato da virgole)

  - File Acrobat (PDF)

  - MHTML (archivio Web)

  - Excel

  - File TIFF

  - Word

Dopo aver selezionato un formato, fare clic su **Esporta**. Quando viene visualizzata la finestra di dialogo **Download file**, fare clic su **Salva**. Nella finestra di dialogo **Salva con nome** selezionare una cartella di destinazione, immettere un nome di file e quindi fare clic su **Salva**.

Se nel computer è installato Microsoft OneNote, è anche possibile copiare i dati del rapporto in OneNote. A tale scopo, fare clic con il pulsante destro del mouse sul pulsante **Visualizza rapporto** sulla barra degli strumenti. Nella finestra di dialogo **Seleziona percorso in OneNote** selezionare la sezione di OneNote in cui si desidera copiare i dati e quindi fare clic su **OK**.

</div>

</div>

<span> </span>

</div>

</div>

</div>

