---
title: 'Lync Server 2013: attività settimanali'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Weekly tasks
ms:assetid: d564839b-b49d-4c5d-b67e-dc5abb0f6980
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn722432(v=OCS.15)
ms:contentKeyID: 63969650
ms.date: 08/20/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87d3f87b37b8c0fe29c4dee76467a9e07931551a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42041215"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="weekly-tasks-in-lync-server-2013"></a>Attività settimanali in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2015-08-17_

Le attività settimanali sono generalmente correlate alla raccolta e all'analisi di registri e report.

<div>

## <a name="archive-event-logs"></a>Registri eventi di archiviazione

Se sono configurati in modo che gli eventi registrati vengano sovrascritti in base alle esigenze, i registri eventi devono essere archiviati ed eliminati a intervalli regolari. Questa azione è particolarmente importante quando si tratta dei registri di protezione, poiché questi potrebbero essere necessari quando si tenta di individuare eventuali tentativi di violazione della protezione.

L'organizzazione dovrà definire i criteri e le procedure per l'archiviazione dei log.

</div>

<div>

## <a name="create-reports"></a>Creazione di rapporti

Creare rapporti di stato per facilitare la pianificazione della capacità, le revisioni di SLA e l'analisi delle prestazioni. Utilizzare i dati giornalieri del registro eventi e del monitor di sistema per creare report su disco, memoria e utilizzo della CPU. Utilizzare System Center Operations Manager per generare i rapporti di disponibilità e di uptime.

L'organizzazione dovrà definire i criteri e le procedure per i report sullo stato.

</div>

<div>

## <a name="incident-reports"></a>Rapporti operazioni non consentite

Eseguire un controllo settimanale dei rapporti sugli incidenti dell'organizzazione correlati a Lync Server. Questo controllo deve includere gli elementi seguenti:

  - Gli incidenti principali generati, risolti e in sospeso.

  - Soluzioni per gli incidenti non risolti.

  - Aggiornamento di report per includere nuovi ticket di problemi.

  - Aggiornamento di un archivio di documenti per la risoluzione dei problemi relativi a guide e post mortem su interruzioni.

Dal momento che il sistema di verifica degli incidenti dell'organizzazione è una scelta indipendente da Lync Server, istruzioni specifiche o puntatori non sono disponibili. Consultare la documentazione per il sistema scelto dall'organizzazione.

</div>

<div>

## <a name="check-iis-logs-and-performance"></a>Controllare i registri e le prestazioni di IIS

Eseguire una revisione settimanale dei registri e delle prestazioni di Internet Information Services (IIS). Per ulteriori informazioni su come monitorare i registri e le prestazioni di IIS, vedere [Panoramica della registrazione di eventi di Windows Server 2003 Internet Information Services (IIS)](http://go.microsoft.com/fwlink/?linkid=36077). La revisione deve includere gli elementi seguenti:

  - Contatori della cache del servizio Web per monitorare la cache del servizio WWW.

  - Contatori ASP (Active Server Pages) per monitorare le applicazioni eseguite come ASP.

</div>

<div>

## <a name="generate-database-reports"></a>Generare report di database

**Per generare report nel database SQL**

1.  Aprire Lync Server 2013.

2.  Nell'albero della console espandere il nodo foresta, espandere **pool Enterprise**e quindi fare clic sul pool per il quale si desidera generare un report di database.

3.  Nel riquadro dei dettagli, fare clic sulla scheda **database** .

4.  Nella scheda **database** eseguire le operazioni seguenti:
    
    1.  Per visualizzare il nome del database, espandere **Impostazioni generali**e visualizzare il nome del database.
    
    2.  Per recuperare le statistiche di riepilogo degli utenti correnti per il pool, espandere **rapporti di riepilogo degli utenti**, fare clic su **Vai**e visualizzare i risultati.
    
    3.  Per recuperare i dati per utente correnti per un singolo utente del pool, espandere **report per utente**, digitare l'URI SIP dell'utente, fare clic su **Vai**e visualizzare i risultati.

Per recuperare le statistiche di riepilogo delle conferenze correnti per il pool, espandere **rapporti di riepilogo conferenze**, fare clic su **Vai**e visualizzare i risultati.

</div>

<div>

## <a name="check-for-security-and-lync-server-updates"></a>Verificare la disponibilità di aggiornamenti per la sicurezza e Lync Server

Identificare nuovi Service Pack, hotfix o aggiornamenti. Se necessario, testarli in un laboratorio di testing e utilizzare le procedure di controllo delle modifiche per organizzare la distribuzione nei server di produzione. Inoltre, gli aggiornamenti dei componenti di Lync Server sono ora disponibili come parte di Windows Update. Tutti gli aggiornamenti del componente di Lync Server devono essere aggiornati contemporaneamente su tutti i server che eseguono Lync Server per il quale sono applicabili gli aggiornamenti.

</div>

<div>

## <a name="run-the-lync-server-2013-best-practice-analyzer"></a>Eseguire l'analizzatore delle procedure consigliate di Lync Server 2013

Lync Server 2013 Best Practices Analyzer Tool è uno strumento di diagnostica che raccoglie le informazioni di configurazione e determina se la configurazione è impostata in base alle procedure consigliate di Microsoft. La documentazione per questo strumento è in [Lync Server 2013 Best Practices Analyzer](lync-server-2013-lync-server-best-practices-analyzer.md).

Lo strumento Confronta i dati di configurazione della distribuzione in base a un set di regole predefinite per Lync Server e segnala potenziali problemi. Per tutti i problemi segnalati, lo strumento fornisce la configurazione corrente nell'ambiente Lync Server e la configurazione consigliata.

Con l'accesso di rete corretto, lo strumento può esaminare i servizi di dominio Active Directory e i server in cui è in esecuzione Lync Server 2013 per eseguire le operazioni seguenti:

  - Eseguire le verifiche di integrità in modo proattivo, verificando che la configurazione sia impostata in base alle procedure consigliate.

  - Generare un elenco di problemi, ad esempio le impostazioni di configurazione non ottimali o le opzioni non supportate o consigliate

  - Giudicare l'integrità generale di un sistema

  - Risoluzione dei problemi specifici

  - Richiedere di scaricare gli aggiornamenti se disponibili

  - Fornire documentazione online e locale sui problemi segnalati e includere suggerimenti per la risoluzione dei problemi

  - Generare informazioni di configurazione che possono essere acquisite per la revisione successiva

Verificare che RTCBPA. msi sia installato in tutti i server Lync Server 2013 e generare un rapporto di verifica dell'integrità settimanale. Prendere nota dei risultati e correggere, se necessario.

</div>

<div>

## <a name="review-sla-performance-figures"></a>Esaminare i dati sulle prestazioni del contratto di servizio

Controllare i dati chiave relativi alle prestazioni per la settimana precedente. Esaminare le prestazioni in base ai requisiti del contratto di servizio. Identificare le tendenze e gli elementi che non hanno soddisfatto gli obiettivi.

</div>

<div>

## <a name="review-system-center-operations-manager-management-pack-and-quality-of-experience-reports"></a>Esaminare il Management Pack di System Center Operations Manager e i report sulla qualità dei rapporti di utilizzo

Ottenere e rivedere i report di Lync Server 2013 Management Pack e Quality of Experience.

</div>

<div>

## <a name="generating-and-viewing-database-reports-for-enterprise-pools"></a>Generazione e visualizzazione di report di database per pool Enterprise

**Per generare i report del pool**

1.  Aprire Lync Server 2013.

2.  Nell'albero della console espandere il nodo foresta, espandere **pool Enterprise**e quindi fare clic sul pool per il quale si desidera generare un report di database.

3.  Nel riquadro dei dettagli, fare clic sulla scheda **database** .

4.  Nella scheda **database** eseguire le operazioni seguenti:
    
    1.  Per visualizzare il nome del database, espandere **Impostazioni generali**e visualizzare il nome del database.
    
    2.  Per recuperare le statistiche di riepilogo degli utenti correnti per il pool, espandere **rapporti di riepilogo degli utenti**, fare clic su **Vai**e visualizzare i risultati.
    
    3.  Per recuperare i dati per utente correnti per un singolo utente del pool, espandere **report per utente**, digitare l'URI SIP dell'utente, fare clic su **Vai**e visualizzare i risultati.

Per recuperare le statistiche di riepilogo delle conferenze correnti per il pool, espandere **rapporti di riepilogo conferenze**, fare clic su **Vai**e visualizzare i risultati.

Per ogni pool Enterprise, gli amministratori possono utilizzare la scheda **database** per visualizzare il nome del database e recuperare e visualizzare i report dal database.

### <a name="database-reports-and-descriptions"></a>Report e descrizioni dei database

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
<td><p>Rapporti di riepilogo degli utenti</p></td>
<td><p>Dbanalyze/v/report: diag [/SqlServer: valore]</p>
<p>In questa sezione vengono visualizzate informazioni di aggregazione sugli utenti in un pool, ad esempio il numero di utenti abilitati, il numero medio di contatti per utente e il numero di utenti per caratteristiche specifiche.</p>
<p>Quando si utilizzano questi rapporti, è possibile che siano utili le seguenti informazioni:</p>
<ul>
<li><p>Un utente abilitato è un utente abilitato per Lync Server 2013 mediante lo snap-in utenti e computer di Active Directory.</p></li>
<li><p>Un utente attivo è un utente che ha eseguito l'accesso o la registrazione.</p></li>
<li><p>I rapporti di riepilogo offrono anche una serie di informazioni statistiche sui contatti. Queste statistiche sono valide solo per la popolazione di utenti che hanno effettuato l'accesso almeno una volta e che dispongono di almeno un contatto. Di conseguenza, in genere, non viene visualizzato un numero minimo di contatti pari a 0. A causa di questo comportamento, se un utente non ha contatti (ma è attivo, in quanto l'utente è registrato), è possibile che &lt;venga&gt; visualizzato: vuoto per alcuni campi di statistiche.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Report per utente</p></td>
<td><p>Dbanalyze/v/report: disco [/SqlServer: valore]</p>
<p>A differenza dei rapporti di riepilogo, che vengono calcolati su un gruppo di utenti, si tratta di report relativi a un utente specifico.</p></td>
</tr>
<tr class="odd">
<td><p>Rapporti di riepilogo conferenze</p></td>
<td><p>Dbanalyze/v/report: conf [/SqlServer: valore]</p>
<p>In questa sezione vengono visualizzate informazioni di aggregazione sulle statistiche di riepilogo delle conferenze per il pool, ad esempio il numero di conferenze attive e il numero totale di partecipanti.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="running-bandwidth-utilization-analyzer"></a>Esecuzione dell'analizzatore dell'utilizzo della larghezza di banda

L'analizzatore dell'utilizzo della larghezza di banda è uno strumento che consente di creare report su diverse visualizzazioni del consumo di larghezza di banda da parte degli endpoint UC tra i collegamenti WAN nella rete aziendale. Questi report possono essere utilizzati per comprendere il modello di consumo di larghezza di banda corrente e per facilitare la pianificazione della capacità della larghezza di banda. Inoltre, viene eseguita una iterazione sulla capacità di larghezza di banda assegnata a vari collegamenti.

Questo strumento esegue le operazioni seguenti:

  - Genera relazioni specifiche per l'utilizzo dell'audio tramite la rete

  - Consente di eseguire una pianificazione e un'iterazione della capacità più efficace sulla capacità di larghezza di banda assegnata a vari collegamenti

L'analizzatore dell'utilizzo della larghezza di banda può generare trame grafiche dei rapporti di utilizzo e capacità della larghezza di banda Sono i seguenti:

  - Tutti i collegamenti WAN nella rete aziendale

  - Filtrato da collegamenti WAN selezionati che sono stati scelti

  - Filtrato tramite collegamenti WAN che hanno superato la capacità dei collegamenti

  - Filtrato mediante collegamenti WAN che sono stati sottoposti a utilizzo della larghezza di banda provisioning

  - Filtrare mediante collegamenti WAN che raggiungevano livelli critici (un utilizzo della larghezza di banda maggiore del 90% della capacità di larghezza di banda del collegamento WAN)

  - Filtro in base al tipo di collegamento WAN: collegamenti a siti di rete, collegamenti interregionali e collegamenti all'interno di un sito

  - Filtrato in base all'area di rete

La documentazione per questo strumento è disponibile in [Lync Server 2013 Resource Kit Tools Documentation](http://go.microsoft.com/fwlink/?linkid=623245).

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Elenco di controllo delle attività settimanali](lync-server-2013-operations-checklists.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

