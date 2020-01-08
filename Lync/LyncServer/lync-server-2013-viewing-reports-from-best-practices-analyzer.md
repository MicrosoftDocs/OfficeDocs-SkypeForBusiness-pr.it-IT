---
title: 'Lync Server 2013: visualizzare i report di Best Practices Analyzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing reports from Best Practices Analyzer
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607690(v=OCS.15)
ms:contentKeyID: 48184465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fb2c229d683ecd0dcf4fee94b456514527226152
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978012"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a>Visualizzazione dei report di Best Practices Analyzer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

Quando si usa Best Practices Analyzer per analizzare l'ambiente, è necessario specificare un nome per l'analisi. Dopo che Best Practices Analyzer completa una scansione, archivia i risultati della scansione nei report e li salva sotto il nome della scansione. Al termine della scansione, è possibile visualizzare i report generati per tale analisi facendo clic su **Visualizza un report di questa analisi delle procedure consigliate** direttamente dalla pagina di **analisi completata** . È anche possibile visualizzare i report da tale analisi o scansioni precedenti in un secondo momento. È possibile visualizzare i report nel computer locale in cui è stata eseguita l'analisi, importare i risultati dell'analisi da un altro computer oppure esportare i risultati della scansione per visualizzare i report in un altro computer in cui è installato Best Practices Analyzer.

I risultati della scansione vengono presentati nei tipi di report seguenti:

  - Report elenco

  - Report albero

  - Altri report

Questi report includono errori, avvisi e altre informazioni. Per informazioni dettagliate su ognuno di questi tipi di report e problemi, vedere [informazioni sui report creati da Best Practices Analyzer in Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).

Usare la procedura seguente per visualizzare i risultati di analisi generati in precedenza dall'analizzatore delle procedure consigliate.

<div>

## <a name="to-view-reports-from-a-previous-scan"></a>Per visualizzare i report da una scansione precedente

1.  Accedere a un computer in cui è installato Best Practices Analyzer usando un account che fa parte dell'account utente locale.
    
    > [!NOTE]  
    > È possibile visualizzare i risultati di un'analisi usando un account che è un membro del gruppo Administrators locale, ma non è possibile eseguire un'analisi a meno che non si disponga di autorizzazioni e diritti utente appropriati. Per informazioni dettagliate, vedere <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">appartenenze ai gruppi e requisiti per i diritti utente per Best Practices Analyzer in Lync Server 2013</A>.

2.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Best Practices Analyzer**.

3.  Nella schermata **iniziale** fare clic su **Seleziona i risultati della scansione da visualizzare**.

4.  Nella pagina **selezionare una procedura consigliata per la visualizzazione** , eseguire una delle operazioni seguenti:
    
      - Per visualizzare i report dall'elenco dei risultati di analisi archiviati localmente, fare clic sul nome della scansione e quindi fare clic su **Visualizza un report di questa analisi**.
        
        > [!NOTE]  
        > L'Analizzatore procedure consigliate crea l'elenco dei file locali dalla &lt;cartella&gt;\\systemDrive Documents\\&lt;and&gt;Settings user \Dati Data\Microsoft\RtcBPA.
    
      - Per visualizzare i report per i risultati di un'analisi archiviata in un'altra posizione, fare clic su **Importa analisi**, individuare il file contenente i risultati della scansione e quindi fare clic su **Apri**.
        
        > [!NOTE]  
        > Se la versione di Best Practices Analyzer in questo computer non corrisponde alla versione usata per raccogliere i dati nel file importato, lo strumento nel computer potrebbe analizzare di nuovo il file dopo l'importazione.

5.  Nella pagina **Visualizza report procedure consigliate** eseguire una delle operazioni seguenti:
    
      - Per visualizzare i report in un elenco organizzato dal componente server, fare clic su **rapporti elenco**e quindi fare clic sulla scheda **tutti i problemi** o sulla scheda **elementi informativi** .
    
      - Per visualizzare i report come elenco gerarchico organizzato in base a tipi di risultati, fare clic su **report albero**e quindi fare clic sulla scheda **visualizzazione dettagliata** o sulla scheda **visualizzazione Riepilogo** .
    
      - Per visualizzare altri report, fare clic su **altri report**.
    
    > [!NOTE]  
    > Per informazioni dettagliate sui report di analizzatore delle procedure consigliate e sui problemi che identificano, vedere <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">visualizzazione e utilizzo dei report creati da Best Practices Analyzer in Lync server 2013</A> e <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analisi e risoluzione dei problemi identificati dall'analizzatore delle procedure consigliate in Lync Server 2013</A>.

</div>

</div>

</div>

</div>

</div>

