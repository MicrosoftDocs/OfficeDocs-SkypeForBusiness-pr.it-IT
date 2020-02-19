---
title: 'Lync Server 2013: visualizzazione dei report di Best Practices Analyzer'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing reports from Best Practices Analyzer
ms:assetid: 7217a47b-36b1-4923-81ea-df754cff29bb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg607690(v=OCS.15)
ms:contentKeyID: 48184465
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 842a04fbf47373060632ee4b367975c5c5df1cc6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138097"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="viewing-reports-from-best-practices-analyzer-in-lync-server-2013"></a>Visualizzazione dei report di Best Practices Analyzer in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

Quando si utilizza lo strumento Best Practices Analyzer per l'analisi del proprio ambiente, è necessario specificare un nome per l'analisi. Al termine di questa, Best Practices Analyzer archivia i risultati all'interno di rapporti e li salva con il nome dell'analisi. Al termine dell'analisi, è possibile visualizzare i rapporti generati sull'analisi stessa, facendo clic su **Visualizza un rapporto di questa analisi Best Practices** direttamente dalla pagina **Analisi completata**. I rapporti delle analisi possono essere visualizzati in qualunque momento dal computer locale sul quale è stata eseguita l'analisi, o importarli da un altro computer. È inoltre possibile esportare i risultati delle analisi per visualizzare i rapporti da un altro computer sul quale è installato lo strumento Best Practices Analyzer.

I risultati dell'analisi sono presentati all'interno dei seguenti tipi di rapporto:

  - Rapporti a elenco

  - Rapporti a albero

  - Altri rapporti

I rapporti includono errori, avvertenze e altre informazioni. Per informazioni dettagliate su ognuno di questi tipi di report e problemi, vedere [Understanding Reports created by Best Practices Analyzer in Lync Server 2013](lync-server-2013-understanding-reports-created-by-best-practices-analyzer.md).

Per visualizzare i risultati delle analisi generate in precedenza attraverso lo strumento Best Practices Analyzer, seguire questa procedura.

<div>

## <a name="to-view-reports-from-a-previous-scan"></a>Per visualizzare i rapporti di un'analisi precedente

1.  Accedere a un computer sul quale è installato lo strumento Best Practices Analyzer, utilizzando un account membro dell'account dell'utente locale.
    
    > [!NOTE]  
    > È possibile visualizzare i risultati di un'analisi utilizzando un account membro del gruppo degli amministratori locali, ma è possibile eseguire un'analisi solo se si dispone dei diritti e delle autorizzazioni appropriate. Per informazioni dettagliate, vedere <A href="lync-server-2013-group-memberships-and-user-rights-requirements-for-best-practices-analyzer.md">appartenenza a gruppi e requisiti per i diritti utente per Best Practices Analyzer in Lync Server 2013</A>.

2.  Fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Lync Server 2013**e quindi fare clic su **Best Practices Analyzer**.

3.  Nella schermata di **Benvenuto**, fare clic su **Selezionare i risultati dell'analisi da visualizzare**.

4.  Nella pagina **Selezionare un'analisi Best Practices da visualizzare**, eseguire una delle seguenti operazioni:
    
      - Per visualizzare rapporti dall'elenco dei risultati archiviati localmente, fare clic sul nome dell'analisi e quindi su **Visualizza un rapporto di questa analisi**.
        
        > [!NOTE]  
        > Best Practices Analyzer crea l'elenco dei &lt;file locali dalla cartella systemDrive&gt;\\Documents and Settings\\&lt;user&gt;\Dati Data\Microsoft\RtcBPA.
    
      - Per visualizzare rapporti dei risultati di un'analisi, memorizzati in un altro percorso, fare clic su **Importa analisi**, localizzare il file contenente i risultati dell'analisi, quindi fare clic su **Apri**.
        
        > [!NOTE]  
        > Se la versione di Best Practices Analyzer del computer non corrisponde a quella utilizzata per la raccolta dei dati nel file importato, lo strumento nel computer potrebbe analizzare nuovamente il file dopo l'importazione.

5.  Nella pagina **Visualizza rapporto Best Practices** effettuare una delle seguenti operazioni:
    
      - Per visualizzare i rapporti in un elenco organizzato per componente server, fare clic su **Elenca rapporti**, quindi fare clic sulla scheda **Tutti i problemi** o **Elementi informativi**.
    
      - Per visualizzare i rapporti in un elenco gerarchico organizzato per tipo di risultato, fare clic su **Rapporti albero**, quindi fare clic sulla scheda **Visualizzazione Dettagli** o **Visualizzazione riepilogo**.
    
      - Per visualizzare altri rapporti, fare clic su **Altri rapporti**.
    
    > [!NOTE]  
    > Per informazioni dettagliate sui report Analizzatore procedure consigliate e sui problemi che identificano, vedere <A href="lync-server-2013-viewing-and-working-with-reports-created-by-best-practices-analyzer.md">viewing and working with Reports created by Best Practices Analyzer in Lync server 2013</A> e <A href="lync-server-2013-analyzing-and-resolving-issues-identified-by-best-practices-analyzer.md">analisi e risoluzione dei problemi identificati da Best Practices Analyzer in Lync Server 2013</A>.

</div>

</div>

</div>

</div>

</div>

