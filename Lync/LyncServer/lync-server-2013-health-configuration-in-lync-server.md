---
title: "Lync Server 2013: configurazione dell'integrità in Lync Server"
description: "Lync Server 2013: configurazione dell'integrità in Lync Server."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Health configuration in Lync Server 2013
ms:assetid: c00a8c8e-c2d2-4557-8c42-211c7cc96550
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205234(v=OCS.15)
ms:contentKeyID: 48185305
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 999a6d5401cb34382a4120f9255c91c846f72422
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552852"
---
# <a name="health-configuration-in-lync-server-2013"></a>Configurazione dell'integrità in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

Tra i diversi siti Web, gli articoli della Microsoft Knowledge base e gli strumenti di Lync Server Resource Kit, gli amministratori che riscontrano problemi durante l'esecuzione di Lync Server non sono mai lontani da un modo per risolvere questi problemi.

Non è ovviamente possibile garantire che non vengano mai riscontrati problemi con Lync Server 2013 perché Lync Server può essere influenzato da molte operazioni, ad esempio arresti anomali della rete e hardware, che il prodotto stesso non è in grado di controllare. Implementando il monitoraggio dello stato, gli amministratori possono identificare potenziali problemi prima che diventino problemi a tutti gli effetti. Ad esempio, gli amministratori possono utilizzare il monitoraggio di Lync Server per identificare tendenze e tendenze. Un aumento costante del numero di conferenze audio/video ad esempio può suggerire la necessità di aggiungere capacità prima che si verifichi un sovraccarico del sistema.

Analogamente, gli amministratori possono utilizzare System Center Operations Manager per eseguire operazioni quali gli avvisi in tempo reale quando si verificano gli eventi specificati e l'esecuzione di transazioni sintetiche che verificano il sistema in modo proattivo. Le transazioni sintetiche vengono utilizzate in Lync Server per verificare che gli utenti siano in grado di completare correttamente attività comuni, ad esempio l'accesso al sistema, lo scambio di messaggi istantanei o l'esecuzione di chiamate a un telefono che si trova nella rete PSTN (Public Switched Telephone Network). Ad esempio, l'esecuzione periodica di questi test può avvisare l'utente di eventuali problemi con gli utenti che accedono a Lync Server e fornire la possibilità di risolvere il problema prima che il team di supporto sia inondato da chiamate provenienti da utenti che non sono in grado di effettuare una connessione. Tramite System Center Operations Manager per eseguire queste transazioni sintetiche, gli amministratori possono monitorare periodicamente la distribuzione di Lync Server continuamente per 24 ore al giorno, senza dover rispondere a qualsiasi avviso che potrebbe essere emesso.

<div>


> [!NOTE]  
> Per Lync Server 2013, il Management Pack per System Center Operations Manager è anche in grado di rilevare problemi "esterni" che possono influire negativamente su Lync Server. Ad esempio, gli amministratori possono ricevere una notifica se Internet Information Services (IIS) non è in linea, le risorse di sistema in un computer Lync Server scendono al di sotto di un determinato importo oppure un computer con Lync Server subisce un errore hardware.



</div>

La configurazione dell'integrità in Lync Server 2013 è basata su System Center Operations Manager e sull'utilizzo dei Management Pack di Lync Server. Tali Management Pack includono diverse nuove funzionalità e miglioramenti, tra cui:

  - **Disponibilità degli scenari da qualsiasi posizione.** Il Management Pack di Lync Server 2010 introduce il concetto di monitoraggio della disponibilità degli scenari degli utenti finali con transazioni sintetiche. In Lync Server 2013, questi agenti dispongono di transazioni più sintetiche e possono essere eseguiti da diverse posizioni all'interno dell'organizzazione, dalle posizioni geografiche remote esterne all'organizzazione, dagli strumenti di succursale e dalle distribuzioni di Lync Server 2010 per aggiungere una copertura alle distribuzioni di Edge legacy.

  - **Log delle transazioni sintetiche.** Quando una transazione sintetica ha esito negativo, gli amministratori hanno accesso a log HTML utili per determinare cosa sia accaduto. Tra le informazioni fornite vi sono l'azione non riuscita, la latenza di ogni azione, la riga di comando utilizzata per eseguire il test e l'errore verificatosi.

  - **Maggiore copertura per segnalare l'affidabilità delle chiamate.** Lync Server 2010 Management Pack ha introdotto l'avviso di affidabilità delle chiamate per rilevare gravi problemi di connettività che influiscono sulle chiamate audio degli utenti finali. I Management Pack di Lync Server 2013 aggiungono una copertura per la messaggistica istantanea peer-to-peer e altre funzionalità di base per le conferenze per massimizzare la copertura durante la riduzione del rumore.

  - **Monitoraggio delle dipendenze.** Gli scenari di Lync Server possono avere esito negativo a causa di una serie di fattori esterni, ad esempio IIS non in linea, limitate risorse di memoria e CPU e problemi relativi al disco. I nuovi Management Pack verificano diverse dipendenze critiche in modo che gli amministratori siano consapevoli del relativo impatto.

  - **Miglioramento dei report.** È disponibile una serie di report che consentono agli amministratori di stimare la disponibilità degli scenari, pianificare la capacità e controllare i componenti su cui si verifica la maggior parte dei problemi.

I Management Pack includono anche una serie di funzionalità che consentono di rilevare e diagnosticare una visibilità in tempo reale nell'integrità della distribuzione di Lync Server. Queste funzionalità sono elencate nella tabella riportata di seguito.

### <a name="management-pack-features"></a>Funzionalità dei Management Pack

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Funzionalità</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Transazioni sintetiche</p></td>
<td><p>Cmdlet di Windows PowerShell che possono essere eseguiti da diverse posizioni per garantire che gli scenari degli utenti finali, ad esempio l'accesso, la presenza, la messaggistica istantanea e le conferenze, siano prontamente disponibili per gli utenti finali.</p></td>
</tr>
<tr class="even">
<td><p>Avvisi di affidabilità delle chiamate</p></td>
<td><p>Query di database per le registrazioni dettagli chiamata. Questi record vengono scritti dai Front End Server per riflettere se gli utenti finali sono stati in grado di connettersi a una chiamata o perché una chiamata è stata terminata. Queste query generano avvisi che segnalano quando un numero elevato di utenti finali ha problemi di connettività per chiamate peer-to-peer o funzionalità di conferenza di base.</p></td>
</tr>
<tr class="odd">
<td><p>Avvisi sulla qualità multimediale</p></td>
<td><p>Query di database che esaminano i report sulla qualità percepita dagli utenti (QoE) pubblicati dai client alla fine di ogni chiamata. Queste query generano avvisi che segnalano gli scenari in cui è probabile che gli utenti percepiscano una scarsa qualità multimediale durante le chiamate e le conferenze. I dati si basano su metriche chiave, come la latenza e la perdita di pacchetti, che notoriamente contribuiscono in modo diretto alla qualità delle chiamate.</p></td>
</tr>
<tr class="even">
<td><p>Stato dei componenti</p></td>
<td><p>I singoli componenti server generano avvisi mediante log eventi e contatori delle prestazioni. Questi avvisi indicano le condizioni di errore che possono influire in modo significativo su uno o più scenari degli utenti finali. Questi avvisi inoltre indicano diverse altre condizioni di errore, tra cui i servizi non in esecuzione, alte percentuali di problemi, un'elevata latenza dei messaggi o i problemi di connettività.</p></td>
</tr>
<tr class="odd">
<td><p>Stato delle dipendenze</p></td>
<td><p>I problemi possono essere causati da una vasta gamma di motivi esterni. I Management Pack ora eseguono il monitoraggio e raccolgono dati per alcune delle dipendenze esterne più importanti che possono indicare seri problemi, inclusi la disponibilità di IIS, l'utilizzo di CPU e memoria dei server e dei processi e le metriche del disco.</p></td>
</tr>
</tbody>
</table>


Gli avvisi generati dal sistema sono stati classificati in tre categorie generali:

  - **Avvisi di alta priorità.** Questi avvisi indicano le condizioni che causeranno interruzioni dei servizi per gruppi estesi di utenti. Ad esempio, un errore del componente su un singolo computer non è un avviso di priorità alta perché Lync Server 2013 dispone di funzionalità di disponibilità elevata incorporate. Gli avvisi di alta priorità rappresentano invece problemi sufficientemente gravi da richiedere l'attenzione degli amministratori anche in piena notte. I problemi rilevati dalle transazioni sintetiche e i servizi offline, ad esempio per conferenze audio/video, sono considerati avvisi di alta priorità.

  - **Avvisi di media priorità.** Questi avvisi indicano le condizioni che incidono su un sottoinsieme di utenti o segnalano un degrado della qualità delle chiamate. Sono inclusi problemi quali guasti dei componenti, latenza per stabilire una chiamata o un peggioramento della qualità audio durante una chiamata. Gli avvisi di questa categoria sono con stato e indicano lo stato corrente del problema. Si supponga ad esempio che i tempi per stabilire una chiamata superino la soglia di avviso. Se l'establishment di chiamata torna alla normalità, questi avvisi verranno risolti automaticamente in System Center Operations Manager. È prevedibile che un amministratore esamini tali avvisi nello stesso giorno lavorativo.

  - **Altri avvisi.** Sono avvisi di componenti che possono incidere su un utente o un sottoinsieme specifico di utenti. Ad esempio, il servizio Rubrica non riesce ad analizzare la voce di Active Directory di un determinato utente. È prevedibile che gli amministratori si occupino di tali avvisi quando hanno tempo a disposizione.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Configurazione di Lync Server 2013 per l'utilizzo con System Center Operations Manager](lync-server-2013-configuring-lync-server-to-work-with-system-center-operations-manager.md)

  - [Utilizzo della registrazione avanzata per le transazioni sintetiche in Lync Server 2013](lync-server-2013-using-rich-logging-for-synthetic-transactions.md)

  - [Utilizzo di Microsoft SQL Server 2008 R2 come database di System Center Operations Manager per Lync Server 2013](lync-server-2013-using-microsoft-sql-server-2008-r2-as-your-system-center-operations-manager-database.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

