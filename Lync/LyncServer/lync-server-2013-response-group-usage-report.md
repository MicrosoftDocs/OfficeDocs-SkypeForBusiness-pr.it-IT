---
title: "Lync Server 2013: report sull'utilizzo di Response Group"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Response Group Usage Report
ms:assetid: 3248b320-a552-400a-8485-6891af4eb0f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558632(v=OCS.15)
ms:contentKeyID: 48183811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9334fea5bded88b4f2453f46a0848819743766d9
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980004"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-usage-report-in-lync-server-2013"></a>Report sull'utilizzo di Response Group in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-22_

L'applicazione Response Group consente a Microsoft Lync Server 2013 di rispondere e instradare le telefonate in base al numero composto e, facoltativamente, alle risposte del chiamante a una serie di domande. In genere, le chiamate di Response Group non vengono instradate a una singola persona, ma vengono invece indirizzate a un team di persone denominato gruppo di agenti. Ad esempio, se qualcuno chiama il numero di telefono dell'help desk, Lync Server 2013 può automaticamente indirizzare la chiamata al primo agente del supporto tecnico disponibile. In alternativa, Lync Server può porre una serie di domande ("premere 1 se si verificano problemi hardware. Premere 2 Se si verificano problemi di software. Premere 3 Se si verificano problemi di rete. ") quindi instradare la chiamata all'agente del supporto tecnico più appropriato in base alla risposta a queste domande.

Il report sull'utilizzo dei gruppi di risposta fornisce un'occhiata dettagliata al numero di telefonate ricevute da tutti i flussi di lavoro di Response Group, quindi suddivide le chiamate in categorie più finite, ad esempio le chiamate offerte, le chiamate e le chiamate interrotte.

La chiave per l'uso del report sull'utilizzo del gruppo di risposte consiste nel comprendere la differenza tra i tipi di chiamata segnalati:

  - **Chiamate ricevute**. Numero totale di chiamate ricevute da tutte le istanze dell'applicazione Response Group.

  - **Chiamate di successo**. Numero totale di chiamate rilevate dall'applicazione Response Group.

  - **Chiamate offerte**. Numero totale di chiamate trasferite a un agente di Response Group.

  - **Chiamate con risposta**. Numero totale di chiamate effettivamente risolte da un agente di Response Group.

  - **Percentuale di chiamate abbandonate**. Percentuale di chiamate ricevute dall'applicazione Response Group, ma non è stata mai risolta da un agente. Questo valore viene calcolato sottraendo le chiamate risposte dalle chiamate ricevute e quindi dividendo il valore in base al numero di chiamate ricevute. Ad esempio, se sono state ricevute 10 chiamate e 7 sono state risolte, è necessario sottrarre 7 da 10, lasciando 3 chiamate senza risposta. Tale valore verrebbe quindi diviso per 10, assegnando una percentuale di chiamata abbandonata del 30%.

  - **Chiamate trasferite**. Numero totale di chiamate al gruppo di risposte trasferite a causa di un timeout della coda o di un overflow della coda.

Se si sta esaminando il report sull'utilizzo di Response Group e non si riesce a ricordare la definizione per uno di questi tipi di chiamata, è sufficiente posizionare il puntatore del mouse sull'etichetta appropriata per il tipo di chiamata. Verrà visualizzata una descrizione comando che offre una breve descrizione del tipo di chiamata.

Il report sull'utilizzo di Response Group consente di filtrare in base a un URI del flusso di lavoro (l'indirizzo SIP associato al flusso di lavoro). Tuttavia, gli URI del flusso di lavoro non vengono effettivamente visualizzati nel report stesso. Se si vuole sapere quali sono i flussi di lavoro che rispondono alla maggior parte delle chiamate o i flussi di lavoro in cui si verificano le chiamate più trasferite, fare clic sulla metrica appropriata per aprire il report di elenco delle chiamate di Response Group per il periodo di tempo indicato. Questi report elencano gli URI del flusso di lavoro.

<div>

## <a name="accessing-the-response-group-usage-report"></a>Accesso al report sull'utilizzo dei gruppi di risposte

Il report sull'utilizzo dei gruppi di risposte si accede dalla Home page dei report di monitoraggio. È possibile eseguire il drill-down nel [report elenco delle chiamate di Response Group in Lync Server 2013](lync-server-2013-response-group-call-list-report.md) facendo clic su una delle metriche seguenti:

  - Chiamate ricevute

  - Chiamate di successo

  - Chiamate offerte

  - Chiamate con risposta

  - Chiamate trasferite

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a>Uso ottimale del report sull'utilizzo dei gruppi di risposte

Uno degli usi più interessanti del report sull'utilizzo dei gruppi di risposte potrebbe non essere evidente: la possibilità di recuperare le informazioni sull'utilizzo per un singolo flusso di lavoro di Response Group.

<div>


> [!WARNING]  
> Un flusso di lavoro di Response Group è fondamentalmente un set di istruzioni che determina il funzionamento di Lync Server quando un utente compone un determinato numero di telefono. A questo scopo, ogni flusso di lavoro è associato in modo univoco a un numero di telefono. Quando qualcuno chiama tale numero, il flusso di lavoro determina il modo in cui verrà gestita la chiamata. Ad esempio, il flusso di lavoro può causare la instradamento della chiamata a una serie di domande IVR (Interactive Voice Response) che richiedono al chiamante di immettere altre informazioni ("premere 1 per il supporto hardware. Premere 2 per il supporto del software. "). In alternativa, il flusso di lavoro potrebbe causare la chiamata a essere inserita in una coda, con il chiamante messo in attesa finché non è disponibile un agente per rispondere alla chiamata. La disponibilità degli agenti per rispondere alle chiamate viene dettata anche dal flusso di lavoro: i flussi di lavoro vengono usati per configurare sia gli orari di ufficio (i giorni della settimana che gli orari in cui gli agenti sono disponibili per rispondere alle chiamate) e le festività (giorni in cui non sono disponibili agenti per rispondere chiamate). Ogni volta che si digita un numero di telefono che appartiene all'applicazione Response Group si sta essenzialmente chiamando un flusso di lavoro di Response Group.



</div>

Anche se gli URI del flusso di lavoro non vengono visualizzati nel report sull'utilizzo dei gruppi di risposte, è comunque possibile visualizzare le statistiche di utilizzo per un singolo flusso di lavoro, un aspetto spesso estremamente utile. Supponi, ad esempio, che tu abbia recentemente svelato una nuova campagna pubblicitaria e che sia curioso sapere se le persone stanno chiamando per chiedere informazioni sul prodotto. Se è stato associato un flusso di lavoro di Response Group con il numero di telefono indicato nella campagna pubblicitaria, è possibile verificare facilmente quante persone (se presenti) chiamano tale numero.

Potresti anche usare un approccio simile per valutare il numero di chiamate gestite dall'help desk interno o dal reparto assistenza clienti.

Per rivedere le statistiche sull'utilizzo per un determinato flusso di lavoro, immettere l'URI del flusso di lavoro nella casella URI flusso di lavoro. Naturalmente, come indicato, gli URI del flusso di lavoro (l'indirizzo SIP associato a un flusso di lavoro) non vengono visualizzati nel report. Questo significa che devi trovare un altro modo per determinare l'URI di un flusso di lavoro. Un modo per eseguire questa operazione consiste nell'usare Windows PowerShell e Lync Server Management Shell. Ad esempio, questo comando restituisce gli URI per tutti i flussi di lavoro di Response Group:

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

Che restituirà dati simili a questi:

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

Questo comando restituisce le informazioni per un singolo flusso di lavoro, quello con la campagna nuovo annuncio nome:

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Ad esempio, il report sull'utilizzo di Response Group consente di visualizzare i dati per tutti i flussi di lavoro di Response Group o di visualizzare i dati per un singolo flusso di lavoro. È anche possibile scegliere la modalità di raggruppamento dei dati. In questo caso, gli usi vengono raggruppati per ora, giorno, settimana o mese.

Nella tabella seguente sono elencati i filtri che è possibile usare con il report sull'utilizzo di Response Group.

### <a name="response-group-usage-report-filters"></a>Filtri di report sull'utilizzo dei gruppi di risposta

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Da</strong></p></td>
<td><p>Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di inizio come indicato di seguito:</p>
<p>7/7/2012 1:00 PM</p>
<p>Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane si eseguono sempre da domenica a sabato.</p></td>
</tr>
<tr class="even">
<td><p><strong>A</strong></p></td>
<td><p>Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</p>
<p>7/7/2012 1:00 PM</p>
<p>Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane si eseguono sempre da domenica a sabato.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervallo</strong></p></td>
<td><p>Intervallo di tempo. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Ogni ora (può essere visualizzato un massimo di 25 ore)</p></li>
<li><p>Giornaliera (è possibile visualizzare un massimo di 31 giorni)</p></li>
<li><p>Settimanale (può essere visualizzato un massimo di 12 settimane)</p></li>
<li><p>Mensile (può essere visualizzato un massimo di 12 mesi)</p></li>
</ul>
<p>Se le date di inizio e di fine superano il numero massimo di valori consentiti per l'intervallo selezionato, viene visualizzato solo il numero massimo di valori (a partire dalla data di inizio). Se ad esempio si seleziona l'intervallo giornaliero con una data di inizio di 7/7/2012 e una data di fine 2/28/2012, i dati verranno visualizzati per i giorni 8/7/2012 12:00 da AM a 9/7/2012 12:00 AM, ovvero un totale di 31 giorni di dati.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI del flusso di lavoro</strong></p></td>
<td><p>Consente di limitare i dati restituiti al flusso di lavoro del gruppo di risposte specificato. Per usare questo filtro, immettere l'indirizzo SIP del flusso di lavoro. Ad esempio:</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel report sull'utilizzo di Response Group.

### <a name="response-group-usage-report-metrics"></a>Metriche del report sull'utilizzo di Response Group

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Si può ordinare su questo elemento?</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Oraria</strong></p>
<p><strong>Quotidiana</strong></p>
<p><strong>Settimanale</strong></p>
<p><strong>Mensile</strong></p></td>
<td><p>No</p></td>
<td><p>Indica l'intervallo di tempo selezionato. Se applicabile, è possibile fare clic su un intervallo di tempo specifico per visualizzare informazioni dettagliate per l'intervallo. Se ad esempio si usa l'intervallo giornaliero e si fa clic su 7/7/2012, viene visualizzata una ripartizione oraria dell'attività di registrazione utente per tale data.</p></td>
</tr>
<tr class="even">
<td><p><strong>Chiamate ricevute</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate ricevute da tutte le istanze dell'applicazione Response Group. Quando si fa clic su questo elemento, nel report viene visualizzato il report elenco delle chiamate di Response Group per il periodo di tempo selezionato.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Chiamate di successo</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate raccolte nell'applicazione Response Group. Quando si fa clic su questo elemento, nel report viene visualizzato il report elenco delle chiamate di Response Group per il periodo di tempo selezionato.</p></td>
</tr>
<tr class="even">
<td><p><strong>Chiamate offerte</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate trasferite a un agente di Response Group. Quando si fa clic su questo elemento, nel report viene visualizzato il report elenco delle chiamate di Response Group per il periodo di tempo selezionato.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Chiamate con risposta</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate effettivamente risolte da un agente di Response Group. Quando si fa clic su questo elemento, nel report viene visualizzato il report elenco delle chiamate di Response Group per il periodo di tempo selezionato.</p></td>
</tr>
<tr class="even">
<td><p><strong>Percentuale di chiamate abbandonate</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate ricevute dall'applicazione Response Group, ma non sono mai state risposte da un agente. Ciò viene calcolato sottraendo le chiamate risposte dalle chiamate ricevute e quindi dividendo il valore in base al numero di chiamate ricevute. Ad esempio, se hai 10 chiamate ricevute e sette hanno ricevuto una risposta, devi sottrarre sette da 10, lasciando tre chiamate senza risposta. Tale valore verrebbe quindi diviso per 10, assegnando una percentuale di chiamata abbandonata del 30%.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Minuti di chiamata media per agente</strong></p></td>
<td><p>No</p></td>
<td><p>Intervallo di tempo medio di un agente del gruppo di risposte speso per una chiamata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Chiamate trasferite</strong></p></td>
<td><p>No</p></td>
<td><p>Numero totale di chiamate al gruppo di risposte trasferite a causa di un timeout della coda o di un overflow della coda. Quando si fa clic su questo elemento, nel report viene visualizzato il report elenco delle chiamate di Response Group per il periodo di tempo selezionato.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

