---
title: 'Lync Server 2013: attività settimanali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d3128780c456c3f38f306d31f258ce903eb50a5
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40974344"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a>Attività settimanali in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-08-17_

Le attività settimanali sono in genere correlate alla raccolta e all'analisi di registri e report.

<div>

## <a name="archive-event-logs"></a>Archiviare i registri eventi

Se i registri eventi non sono configurati per sovrascrivere gli eventi come richiesto, devono essere archiviati e eliminati regolarmente. Questa azione è particolarmente importante per i registri di sicurezza, che potrebbero essere necessari per esaminare le violazioni della sicurezza tentate.

L'organizzazione dovrà definire i criteri e le procedure per l'archiviazione dei log.

</div>

<div>

## <a name="create-reports"></a>Creare report

Creare report sullo stato per facilitare la pianificazione della capacità, le recensioni di SLA e le analisi delle prestazioni. Usare i dati giornalieri da log eventi e monitor di sistema per creare report su disco, memoria e utilizzo della CPU. Usare System Center Operations Manager per generare i report di uptime e disponibilità.

L'organizzazione dovrà definire i criteri e le procedure per i report di stato.

</div>

<div>

## <a name="incident-reports"></a>Report sugli incidenti

Eseguire un controllo settimanale dei report sugli incidenti dell'organizzazione correlati a Lync Server. Questo controllo deve includere i seguenti elementi:

  - Gli eventi principali generati, risolti e in sospeso.

  - Soluzioni per gli eventi non risolti.

  - Aggiornare i report per includere nuovi ticket di problemi.

  - Aggiornamento di un archivio documenti per le guide alla risoluzione dei problemi e post mortem sulle interruzioni.

Dato che il sistema di monitoraggio degli incidenti dell'organizzazione è una scelta indipendente da Lync Server, le istruzioni specifiche o i puntatori non sono disponibili. Consultare la documentazione per il sistema scelto dall'organizzazione.

</div>

<div>

## <a name="check-iis-logs-and-performance"></a>Controllare i registri e le prestazioni di IIS

Eseguire una revisione settimanale dei registri e delle prestazioni di Internet Information Services (IIS). Per altre informazioni su come monitorare i registri e le prestazioni di IIS, vedere [Panoramica della registrazione degli eventi di Windows Server 2003 (IIS)](http://go.microsoft.com/fwlink/?linkid=36077). La recensione deve includere le operazioni seguenti:

  - Contatori della cache dei servizi Web per monitorare la cache del servizio WWW.

  - Contatori ASP (Active Server Pages) per monitorare le applicazioni eseguite come ASP.

</div>

<div>

## <a name="generate-database-reports"></a>Generazione di report di database

**Per generare report nel database SQL**

1.  Aprire Lync Server 2013.

2.  Nell'albero della console espandere il nodo della foresta, espandere **pool di imprese**e quindi fare clic sul pool per il quale si desidera generare un report di database.

3.  Nel riquadro dei dettagli fare clic sulla scheda **database** .

4.  Nella scheda **database** eseguire le operazioni seguenti:
    
    1.  Per visualizzare il nome del database, espandere **Impostazioni generali**e visualizzare il nome del database.
    
    2.  Per recuperare le statistiche di riepilogo degli utenti correnti per il pool, espandere **report riepilogo utenti**, fare clic su **Vai**e visualizzare i risultati.
    
    3.  Per recuperare i dati per utente correnti per un singolo utente del pool, espandere **report per utente**, digitare l'URI SIP dell'utente, fare clic su **Vai**e visualizzare i risultati.

Per recuperare le statistiche di riepilogo delle conferenze correnti per il pool, espandere **report di riepilogo conferenze**, fare clic su **Vai**e visualizzare i risultati.

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a>Verificare la disponibilità di aggiornamenti per la sicurezza e Lync Server

Identificare eventuali nuovi Service Pack, hotfix o aggiornamenti. Se necessario, provali in un laboratorio di test e usa le procedure di controllo delle modifiche per organizzare la distribuzione per i server di produzione. Inoltre, gli aggiornamenti dei componenti di Lync Server sono ora disponibili come parte di Windows Update. Tutti gli aggiornamenti dei componenti di Lync Server devono essere aggiornati contemporaneamente su tutti i server che esegue Lync Server per cui sono applicabili gli aggiornamenti.

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a>Eseguire l'analizzatore delle procedure consigliate di Lync Server 2013

Lync Server 2013 Best Practices Analyzer Tool è uno strumento di diagnostica che raccoglie le informazioni di configurazione e determina se la configurazione è impostata in base alle procedure consigliate Microsoft. La documentazione per questo strumento è in [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).

Lo strumento Confronta i dati di configurazione della distribuzione in base a un set di regole predefinite per Lync Server e segnala potenziali problemi. Per ogni problema segnalato, lo strumento fornisce la configurazione corrente nell'ambiente Lync Server e la configurazione consigliata.

Con l'accesso alla rete corretto, lo strumento può esaminare i servizi di dominio Active Directory e i server che eseguono Lync Server 2013 per eseguire le operazioni seguenti:

  - Eseguire in modo proattivo i controlli di integrità, verificando che la configurazione sia impostata in base alle procedure consigliate

  - Generare un elenco di problemi, ad esempio le impostazioni di configurazione non ottimali o le opzioni non supportate o non consigliate

  - Valutare l'integrità generale di un sistema

  - Risolvere i problemi specifici della Guida

  - Richiedere di scaricare gli aggiornamenti se disponibili

  - Creare documentazione online e locale sui problemi segnalati e includere suggerimenti per la risoluzione dei problemi

  - Generare informazioni di configurazione che possono essere acquisite per la revisione successiva

Assicurarsi che RTCBPA. msi sia installato in tutti i server Lync Server 2013 e generare un report di controllo dell'integrità settimanale. Prendere nota dei risultati e correggere, se necessario.

</div>

<div>

## <a name="review-sla-performance-figures"></a>Rivedere i dati sulle prestazioni di SLA

Verificare i dati sulle prestazioni chiave per la settimana precedente. Esaminare le prestazioni in base ai requisiti dello SLA. Identificare le tendenze e gli elementi che non hanno soddisfatto le proprie destinazioni.

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a>Rivedere il Management Pack di System Center Operations Manager e la qualità dei report sull'esperienza

Ottenere e rivedere Lync Server 2013 Management Pack e la qualità dei report di esperienza.

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a>Generazione e visualizzazione di report di database per i pool aziendali

**Per generare i report del pool**

1.  Aprire Lync Server 2013.

2.  Nell'albero della console espandere il nodo della foresta, espandere **pool di imprese**e quindi fare clic sul pool per il quale si desidera generare un report di database.

3.  Nel riquadro dei dettagli fare clic sulla scheda **database** .

4.  Nella scheda **database** eseguire le operazioni seguenti:
    
    1.  Per visualizzare il nome del database, espandere **Impostazioni generali**e visualizzare il nome del database.
    
    2.  Per recuperare le statistiche di riepilogo degli utenti correnti per il pool, espandere **report riepilogo utenti**, fare clic su **Vai**e visualizzare i risultati.
    
    3.  Per recuperare i dati per utente correnti per un singolo utente del pool, espandere **report per utente**, digitare l'URI SIP dell'utente, fare clic su **Vai**e visualizzare i risultati.

Per recuperare le statistiche di riepilogo delle conferenze correnti per il pool, espandere **report di riepilogo conferenze**, fare clic su **Vai**e visualizzare i risultati.

Per ogni pool aziendale, gli amministratori possono usare la scheda **database** per visualizzare il nome del database e recuperare e visualizzare i report dal database.

### <a name="database-reports-and-descriptions"></a>Report e descrizioni di database

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Sezione</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Report di riepilogo degli utenti</p></td>
<td><p>Dbanalyze/v/report: diag [/SqlServer: valore]</p>
<p>In questa sezione vengono visualizzate informazioni di aggregazione sugli utenti in un pool, ad esempio il numero di utenti abilitati, il numero medio di contatti per utente e il numero di utenti per caratteristiche specifiche.</p>
<p>Quando si usano questi report, le informazioni seguenti possono essere utili:</p>
<ul>
<li><p>Un utente abilitato è un utente abilitato per Lync Server 2013 usando lo snap-in utenti e computer di Active Directory.</p></li>
<li><p>Un utente attivo è un utente che ha effettuato l'accesso o registrato.</p></li>
<li><p>I report di riepilogo offrono anche un set di informazioni statistiche sui contatti. Queste statistiche sono valide solo per la popolazione di utenti che hanno effettuato l'accesso almeno una volta e che hanno almeno un contatto. Di conseguenza, in genere non viene visualizzato un numero minimo di contatti pari a 0. A causa di questo comportamento, se un utente non ha contatti (ma è attivo, in quanto l'utente ha registrato), potrebbe essere visualizzato &lt;:&gt; vuoto per alcuni campi delle statistiche.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Report per utente</p></td>
<td><p>Dbanalyze/v/report: disco [/SqlServer: valore]</p>
<p>A differenza dei report di riepilogo, che vengono calcolati in base a un utente, si tratta di report relativi a un utente specifico.</p></td>
</tr>
<tr class="odd">
<td><p>Report di riepilogo conferenze</p></td>
<td><p>Dbanalyze/v/report: conf [/SqlServer: valore]</p>
<p>In questa sezione vengono visualizzate informazioni di aggregazione sulle statistiche di riepilogo conferenze per il pool, ad esempio il numero di conferenze attive e il numero totale di partecipanti.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a>Analizzatore dell'utilizzo della larghezza di banda

L'analizzatore dell'utilizzo della larghezza di banda è uno strumento che crea report su varie visualizzazioni del consumo di larghezza di banda dagli endpoint UC in collegamenti WAN nella rete aziendale. Questi report possono essere usati per comprendere il modello di consumo di larghezza di banda corrente e per facilitare la pianificazione della capacità di larghezza di banda. Viene inoltre iterata sulla capacità di larghezza di banda assegnata a diversi collegamenti.

Questo strumento esegue le operazioni seguenti:

  - Genera report specifici per l'utilizzo dell'audio tramite la rete

  - Facilita la pianificazione e l'iterazione della capacità più efficace sulla capacità di larghezza di banda assegnata a diversi collegamenti

L'analizzatore dell'utilizzo della larghezza di banda può generare trame grafiche della capacità e dei report sull'utilizzo Sono i seguenti:

  - Tutti i collegamenti WAN nella rete aziendale

  - Filtrati da collegamenti WAN selezionati scelti

  - Filtrati da collegamenti WAN che hanno superato la capacità di collegamento

  - Filtrati da collegamenti WAN che erano in uso della larghezza di banda provisioning

  - Filtrare in base a collegamenti WAN che raggiungevano livelli critici (un utilizzo della larghezza di banda maggiore di 90% della capacità di larghezza di banda del collegamento WAN)

  - Filtrato tramite il tipo di collegamento WAN: collegamenti a siti di rete, collegamenti interregionali e collegamenti all'interno di un sito

  - Filtrata per area di rete

La documentazione per questo strumento è disponibile nella [documentazione di strumenti del Resource Kit di Lync Server 2013](http://go.microsoft.com/fwlink/?linkid=623245).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Elenco di controllo attività settimanale](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

