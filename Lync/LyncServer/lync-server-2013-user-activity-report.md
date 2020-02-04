---
title: 'Lync Server 2013: report attività utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: User Activity Report
ms:assetid: 3aa6fef2-ea02-4f0f-93e8-fa2e0a953d79
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558638(v=OCS.15)
ms:contentKeyID: 48183862
ms.date: 02/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 583c647ac3cdab290f1833539abbbd033ea89410
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744626"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-activity-report-in-lync-server-2013"></a>Report attività utente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2015-02-27_

Il report attività utente fornisce un elenco dettagliato delle sessioni peer-to-peer e di conferenza svolte dagli utenti in un determinato periodo di tempo. Diversamente da molti dei report di monitoraggio, il report attività utente lega ogni chiamata a singoli utenti. Ad esempio, le sessioni peer-to-peer specificano gli URI SIP della persona che ha avviato la chiamata (l'utente da) e la persona che veniva chiamata (l'utente). Se si espandono le informazioni per una conferenza, viene visualizzato un elenco di tutti i partecipanti alla conferenza e il ruolo che hanno tenuto per la conferenza.

Il report attività utente viene talvolta indicato come report "Help desk". Questo perché il report viene spesso usato dal personale dell'helpdesk per recuperare le informazioni sulla sessione per un utente specifico. Puoi filtrare le chiamate effettuate o effettuate da un singolo utente semplicemente digitando l'URI SIP dell'utente nella casella prefisso URI utente.

In questo caso, il report attività utente restituirà informazioni per tutti gli utenti il cui URI SIP inizia con la stringa specificata. Ad esempio, se si digita **Ken** nella casella URI, il report attività utente individuerà **Ken**. Myer@litwareinc.com. Verranno tuttavia individuati anche gli utenti seguenti:

  - **davide**azi@litwareinc.com

  - **davide**Burg@litwareinc.com

  - **Ken**. Sanchez@litwareinc.com

  - **Davide**Nedy@litwareinc.com

Per fare in modo che vengano restituite le informazioni solo per Ken, digitare l'URI completo (Ken.Myer@litwareinc.com) nella casella di ricerca o almeno il tipo di URI di Ken per distinguerlo in modo univoco dagli altri utenti dell'organizzazione. Ad esempio:

Ken.my

<div>

## <a name="to-access-the-user-activity-report"></a>Per accedere al report attività utente

Il report attività utente si accede dalla Home page dei report di monitoraggio. È anche possibile accedere al report attività utente facendo clic sulla metrica URI utente nel [report inventario IP telefono in Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md). Dall'interno del report attività utente fare clic sull'URI conferenza (per una conferenza) per il report Dettagli conferenza. Analogamente, se si fa clic sulla metrica di dettaglio per una chiamata peer-to-peer si passa al [report Dettagli sessione peer-to-peer in Lync Server 2013](lync-server-2013-peer-to-peer-session-detail-report.md).

</div>

<div>

## <a name="making-the-best-use-of-the-user-activity-report"></a>Sfruttare al meglio il report attività utente

Anche se nel report attività utente sono presenti numerose informazioni utili, è possibile che le informazioni a volte siano difficili da individuare. Ad esempio, tutte le attività utente che si svolgono nell'organizzazione durante un periodo specificato sono incluse nel report attività utente; Questo significa che, sepolto, nel report sono disponibili informazioni su quali utenti hanno effettivamente usato Microsoft Lync Server 2013 in qualche modo.

<div>


> [!WARNING]  
> Tecnicamente, è possibile che alcune attività dell'utente non vengano registrate: mentre Lync Server si sforza di conservare le informazioni su tutte le telefonate, è possibile che sia stata eseguita una chiamata senza che le informazioni relative alla chiamata vengano scritte nel database. Lync Server è progettato per fornire un aspetto estremamente accurato ma non necessariamente perfetto per l'uso di Lync Server 2013. Il fatto che non sia garantito che il 100% di tutte le chiamate venga registrato spiega perché il monitoraggio di Lync Server non deve essere usato come sistema di fatturazione.<BR>In secondo luogo, un report di report di monitoraggio può solo visualizzare, al massimo, i record di 1.000. A seconda della quantità di attività utente in uso e in base al periodo di tempo in cui si sta lavorando, significa che la query potrebbe non restituire tutti i dati effettivamente archiviati nel database.



</div>

  - Quali utenti hanno effettivamente usato il sistema durante questo periodo di tempo?

  - Quali utenti sono stati i più attivi durante questo periodo di tempo?

  - Gli utenti che effettuano la maggior parte delle chiamate telefoniche sono anche gli utenti che partecipano alle sessioni di messaggistica istantanea più?

Se è necessario rispondere a domande di questo tipo, è possibile esportare i dati recuperati dai report di monitoraggio in un foglio di calcolo di Excel. Puoi quindi usare il foglio di calcolo e/o un file con valori delimitati da virgole per analizzare i dati in modo che il report attività utente. Si supponga ad esempio di aver esportato i dati del report in Excel e quindi in un file con valori delimitati da virgole. A questo punto è possibile importare i dati da. File CSV in Windows PowerShell usando un comando simile al seguente:

    $x = Import-Csv -Path "C:\Data\User_Activity_Report.csv"

Dopo aver importato i dati, è possibile usare semplici comandi di Windows PowerShell per rispondere alle domande. Ad esempio, questo comando restituisce un elenco di utenti univoci che hanno servito come "da utente" in almeno una sessione:

    $x | Group-Object "From user" | Select Name | Sort-Object Name

In altre parole:

    Name
    ----
    David.Ahs@litwareinc.com
    Gilead.Amosnino@litwareinc.com
    Henrik.Jensen@litwareinc.com
    Ken.Myer@litwareinc.com
    Pilar.Ackerman@litwareinc.com

Questo comando elenca gli utenti univoci (in base al numero totale di sessioni a cui hanno partecipato:

    $x | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

Che restituisce dati simili a questi:

    Count    Name
    -----    ----
      523    Ken.Myer@litwareinc.com
       63    David.Ahs@litwareinc.com
       29    Pilar.Ackerman@litwareinc.com
       17    Gilead.Amosnino@litwareinc.com
       10    Henrik.Jensen@litwareinc.com

Questo comando limita le sessioni segnalate a quelle che includevano l'audio come modalità:

    $x | Where-Object {$_.Modalities -match "audio"} | Group-Object "From user" | Select Count, Name | Sort-Object Count -Descending

Se si tiene il mouse su un ID di diagnostica visualizzato nel report, verrà visualizzata una descrizione comando che descrive l'ID.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di restituire un set di dati più mirato o di visualizzare i dati restituiti in modi diversi. Ad esempio, il report attività utente consente di filtrare i dati restituiti in base a elementi come il tipo di attività (ovvero sessioni peer-to-peer o sessioni di conferenza) o l'indirizzo SIP dell'utente (che consente di visualizzare le attività di un utente). È anche possibile scegliere la modalità di raggruppamento dei dati. In questo caso, gli usi vengono raggruppati per ora, giorno, settimana o mese.

Nella tabella seguente sono elencati i filtri che è possibile usare con il report attività utente.

### <a name="user-activity-report-filters"></a>Filtri di report attività utente

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
<p>7/17/12012 1:00 PM</p>
<p>Se non si immette un'ora di inizio, il report inizia automaticamente da 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:</p>
<p>7/17/12012</p>
<p>Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</p>
<p>7/13/2012</p>
<p>Le settimane si eseguono sempre da domenica a sabato.</p></td>
</tr>
<tr class="even">
<td><p><strong>A</strong></p></td>
<td><p>Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base alle ore, immettere la data e l'ora di fine come indicato di seguito:</p>
<p>7/17/12012 1:00 PM</p>
<p>Se non si immette un'ora di fine, il report termina automaticamente a 12:00 AM nel giorno specificato. Per visualizzare i dati per giorno, immettere solo la data:</p>
<p>7/17/12012</p>
<p>Per visualizzare la settimana o il mese, immettere una data che rientri in qualsiasi punto della settimana o del mese che si vuole visualizzare (non è necessario immettere il primo giorno della settimana o del mese):</p>
<p>7/13/2012</p>
<p>Le settimane si eseguono sempre da domenica a sabato.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo di attività</strong></p></td>
<td><p>Tipo di attività. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Peer-to-peer</p></li>
<li><p>Conferenza</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Modalità</strong></p></td>
<td><p>La modalità disponibile varia in base al tipo di attività seleziona. Se il tipo di attività è peer-to-peer, è possibile selezionare la messaggistica istantanea. Trasferimento file; Condivisione di applicazioni; Segreteria telefonica o video come modalità.</p>
<p>Se il tipo di attività è conferenza, è possibile selezionare conferenza telefonica di messaggistica istantanea; Conferenza Web; Condivisione di applicazioni; Conferenza vocale/video; o conferenza telefonica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Categoria sessione</strong></p></td>
<td><p>Indica se l'attività in questione è riuscita o meno. Selezionare una delle opzioni seguenti:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>Successo</p></li>
<li><p>Errore previsto</p></li>
<li><p>Errore imprevisto</p></li>
</ul>
<p>Un &quot;errore&quot; previsto è un errore che dovrebbe verificarsi; ad esempio, se un utente ha impostato il proprio stato su non disturbare, si prevede che qualsiasi chiamata non venga eseguita correttamente. Un &quot;errore&quot; imprevisto è un errore che si verifica in quello che sembrerebbe essere un sistema altrimenti integro. Ad esempio, una chiamata non deve essere terminata se il chiamante viene posizionato in attesa. Se questo si verifica, verrebbe contrassegnato come errore imprevisto.</p></td>
</tr>
<tr class="even">
<td><p><strong>Prefisso URI utente</strong></p></td>
<td><p>Indirizzo SIP per l'utente. Per visualizzare solo i record per l'utente Ken si deve immettere l'indirizzo SIP di Ken. Ad esempio:</p>
<p>sip:kenmyer@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-peer-to-peer-sessions"></a>Metriche per le sessioni peer-to-peer

Nella tabella seguente sono elencate le informazioni fornite nel report attività utente per le sessioni peer-to-peer, ovvero le sessioni che coinvolgono solo due partecipanti.

### <a name="metrics-for-peer-to-peer-sessions"></a>Metriche per le sessioni peer-to-peer

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
<td><p><strong>Dettaglio</strong></p></td>
<td><p>No</p></td>
<td><p>Quando si fa clic su questo elemento, il report Mostra il report Dettagli sessione peer-to-peer per la sessione selezionata.</p></td>
</tr>
<tr class="even">
<td><p><strong>Dall'utente</strong></p></td>
<td><p>Sì</p></td>
<td><p>Indirizzo SIP dell'utente che ha avviato la sessione peer-to-peer.</p></td>
</tr>
<tr class="odd">
<td><p><strong>All'utente</strong></p></td>
<td><p>Sì</p></td>
<td><p>Indirizzo SIP dell'utente che ha partecipato alla sessione peer-to-peer.</p></td>
</tr>
<tr class="even">
<td><p><strong>Modalità</strong></p></td>
<td><p>Sì</p></td>
<td><p>Tipo di comunicazione usato nella sessione. Ad esempio, messaggistica istantanea, audio o trasferimento di file.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Invitare il tempo</strong></p></td>
<td><p>Sì</p></td>
<td><p>Data e ora in cui è stato inviato l'invito iniziale a partecipare alla sessione peer-to-peer.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tempo di risposta</strong></p></td>
<td><p>Sì</p></td>
<td><p>Data e ora in &quot;&quot; cui l'utente ha accettato l'invito alla sessione.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ora di fine</strong></p></td>
<td><p>Sì</p></td>
<td><p>Data e ora terminata la sessione peer-to-peer.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID diagnostica</strong></p></td>
<td><p>Sì</p></td>
<td><p>Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori. Le intestazioni di diagnostica sono facoltative (è possibile avere sessioni SIP che non includono queste intestazioni) e gli ID di diagnostica vengono riportati solo per le sessioni con problemi di qualche tipo.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conferencing-sessions"></a>Metriche per le sessioni di conferenza

Nella tabella seguente sono elencate le informazioni fornite nel report attività utente per le sessioni di conferenza, ovvero le sessioni che coinvolgono tre o più partecipanti.

### <a name="metrics-for-conferencing-sessions"></a>Metriche per le sessioni di conferenza

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
<td><p><strong>URI conferenza</strong></p></td>
<td><p>Sì</p></td>
<td><p>Identificatore di conferenza univoco. Quando si fa clic su questo elemento, il report Mostra il report Dettagli conferenza per la sessione selezionata. Quando si espande questo elemento, il report Mostra le informazioni sui partecipanti alla conferenza. Per informazioni dettagliate, vedere &quot;la sezione metriche per i&quot; partecipanti alla conferenza più avanti in questo argomento.</p></td>
</tr>
<tr class="even">
<td><p><strong>Organizzatore</strong></p></td>
<td><p>Sì</p></td>
<td><p>Indirizzo SIP dell'utente che ha organizzato la conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Pool</strong></p></td>
<td><p>Sì</p></td>
<td><p>Nome del server perimetrale (se presente) usato nella conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ora di inizio</strong></p></td>
<td><p>Sì</p></td>
<td><p>Data e ora di inizio della conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ora di fine</strong></p></td>
<td><p>Sì</p></td>
<td><p>Data e ora di fine della conferenza.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics-for-conference-participants"></a>Metriche per i partecipanti alla conferenza

La tabella seguente elenca le informazioni fornite nel report attività utente per ogni partecipante di una conferenza.

### <a name="metrics-for-conference-participants"></a>Metriche per i partecipanti alla conferenza

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
<td><p><strong>Ruolo</strong></p></td>
<td><p>No</p></td>
<td><p>Ruolo conferenza, ad esempio relatore, per l'utente.</p></td>
</tr>
<tr class="even">
<td><p><strong>Partecipante</strong></p></td>
<td><p>No</p></td>
<td><p>Indirizzo SIP dell'utente.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Connettività</strong></p></td>
<td><p>No</p></td>
<td><p>Tipo di connessione di rete. Ad esempio &quot;da Internal&quot; per la connessione interna &quot;o da&quot; PSTN per gli utenti con accesso esterno.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tempo di partecipazione</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora in cui l'utente ha partecipato alla conferenza.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ora di uscita</strong></p></td>
<td><p>No</p></td>
<td><p>Data e ora in cui l'utente ha lasciato la conferenza.</p></td>
</tr>
<tr class="even">
<td><p><strong>ID diagnostica</strong></p></td>
<td><p>No</p></td>
<td><p>Identificatore univoco (in forma di intestazione MS-Diagnostics) allegato a un messaggio SIP che spesso fornisce informazioni utili per la risoluzione di errori. Le intestazioni di diagnostica sono facoltative (è possibile avere sessioni SIP che non includono queste intestazioni) e gli ID di diagnostica vengono riportati solo per le sessioni con problemi di qualche tipo.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

