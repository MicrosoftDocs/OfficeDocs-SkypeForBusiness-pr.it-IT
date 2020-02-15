---
title: 'Lync Server 2013: rapporto inventario telefoni IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP Phone Inventory Report
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615027(v=OCS.15)
ms:contentKeyID: 48185044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c99945626105282324202d1fd754cd5d966bc81
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035098"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-phone-inventory-report-in-lync-server-2013"></a>Rapporto inventario telefoni IP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-11-12_

Il rapporto inventario telefoni IP riporta informazioni sui telefoni IP attualmente in uso nell'organizzazione. Il report inventario IP fornisce un elenco dettagliato dei telefoni IP che sono stati effettivamente utilizzati durante il periodo di riferimento specificato. Tra le altre cose, questo rapporto consente agli amministratori di sapere se sono presenti telefoni obsoleti o obsoleti ancora in uso che devono essere sostituiti; è inoltre possibile avvisare gli amministratori del fatto che sono presenti telefoni costosi nell'organizzazione raramente utilizzati. Questo tipo di informazioni può essere prezioso quando arriva il momento di acquistare nuovi telefoni o di ridistribuire i telefoni esistenti. Ad esempio, un utente che raramente utilizza il proprio telefono costoso potrebbe essere invitato a scambiare telefoni con un utente che usa il proprio telefono con molta più frequenza.

Si noti che questo rapporto ha alcune limitazioni quando si tratta di essere utilizzato come un rapporto di inventario vero. Per prima cosa, il rapporto telefoni IP elenca semplicemente tutti i telefoni che hanno effettuato l'accesso a Lync Server durante il periodo di tempo specificato, ordinati in base alla data dell'ultimo accesso. Se un telefono non ha eseguito l'accesso durante il periodo di tempo specificato, non verrà elencato nel rapporto inventario. Che include i telefoni che hanno effettuato l'accesso prima del periodo di tempo in cui sono stati avviati e che sono ancora connessi durante l'intervallo di tempo specificato. Ad esempio, si supponga di voler esaminare tutti gli inventari telefonici per il 2012 luglio. Si supponga, anche, che alcuni telefoni connessi a Lync Server il 30 giugno 2012 e siano ancora connessi al primo luglio. Tali telefoni non verranno visualizzati nel rapporto inventario del 1 ° luglio.

È inoltre importante tenere presente che il rapporto inventario potrebbe includere i telefoni che l'organizzazione non utilizza più. Si supponga, ad esempio, che un numero di telefoni Fabrikam sia connesso al sistema il 1 ° luglio 2012; 5 giorni dopo l'organizzazione si è sbarazzata di tutti i telefoni Fabrikam e li ha sostituiti con un modello contoso più recente. I telefoni Fabrikam continueranno a essere visualizzati sul rapporto "inventario" semplicemente perché si sono connessi al sistema nel corso del mese di luglio.

Inoltre, il rapporto inventario telefoni IP non riporta i totali di riepilogo per i diversi tipi di telefoni. Ad esempio, si supponga di disporre di 105 telefoni CX600 Polycom. Il report non dirà di avere 105 di questi telefoni; al contrario, si vedranno semplicemente 105 voci separate per la Cx600 Polycom. L'unico modo per sapere che ci sono 105 voci per l'Polycom Cx600 sarebbe quello di contare ognuna di queste voci manualmente.

<div>


> [!WARNING]  
> In alternativa, esportare i dati e utilizzare Microsoft Excel o Windows PowerShell per eseguire il conteggio per l'utente.



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a>Accesso al rapporto inventario telefoni IP

È possibile accedere al rapporto inventario telefoni IP dalla Home page dei rapporti di monitoraggio. Se si fa clic sulla metrica URI dell'utente, è possibile accedere al rapporto attività utente per tale utente. Se si fa clic sulla metrica Ultima attività per una chiamata peer-to-peer, verrà eseguito il rapporto Dettagli sessione peer-to-peer. Se si fa clic sulla stessa metrica di una conferenza, verrà utilizzato il rapporto Dettagli conferenza.

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a>Utilizzo ottimale del rapporto inventario telefoni IP

Se si è interessati solo alle informazioni sull'utilizzo per un determinato tipo di telefono (ad esempio, "con quale frequenza Gli utenti utilizzano un telefono CX600 di Polycom?"), è possibile ottenere tali informazioni direttamente dal rapporto inventario telefoni IP tramite filtro per quel tipo di telefono specifico. Tuttavia, se si desiderano informazioni di riepilogo per tutti i telefoni (numero di utenti che utilizzano un CX600 di Polycom, quanti utilizzano un IP8540 LG-Nortel e così via), è necessario esportare i dati e utilizzare un'altra applicazione, ad esempio Windows PowerShell, per eseguire questo tipo di analisi. Si supponga, ad esempio, di esportare i dati in un file con valori delimitati da virgole\_(\_C\_:\\data\\IP Phone inventario report. csv). In tal caso, è possibile utilizzare questi due comandi per fornire dati di riepilogo per tutti i telefoni:

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

Il comando restituisce dati analoghi a questi:

    Count    Name
    -----    ----
      267    POLYCOM, CX700
      267    POLYCOM, CX600
      166    POLYCOM, C
       68    Microsoft, CPE
       64    LG-Nortel, IP8540
       59    Aastra, 6725ip
       37    LG-Nortel, IP
       22    POLYCOM, CX3000
       11    Microsoft, CPE_A
        9    POLYCOM, CX500
        7    Aastra, 6721ip

Analogamente, questi due comandi indicano quali telefoni sono connessi al sistema ma non sono mai stati effettivamente utilizzati per effettuare una chiamata (il valore della metrica Ultima attività è vuoto, a indicare che non vi sono state attività nell'ultima operazione):

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

Che restituisce dati simili a questo per ogni telefono che non è stato utilizzato:

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

Un altro modo interessante per utilizzare il rapporto inventario telefoni IP è questo: se si ha l'indirizzo MAC di un telefono IP, è possibile trovare l'utente che ha utilizzato l'ultima volta quel telefono semplicemente inserendo quell'indirizzo nella casella di testo indirizzo MAC. Il rapporto inventario telefoni IP riporterà (tra le altre cose) l'indirizzo SIP dell'utente che ha effettuato l'ultimo accesso con il telefono. In alternativa, è possibile immettere un indirizzo SIP utente (nella casella prefisso URI utente) per individuare tutti i telefoni che sono stati utilizzati dall'utente.

</div>

<div>

## <a name="filters"></a>Filtri

I filtri consentono di ottenere un set di dati più specifico o di visualizzare in modo diverso i dati restituiti. Ad esempio, l'inventario del telefono IP consente di visualizzare solo i telefoni prodotti da una determinata società o persino una versione specifica di tali telefoni. È inoltre possibile scegliere la modalità di raggruppamento dei dati. In questo caso, le registrazioni sono raggruppate in base all'ora, al giorno, alla settimana o al mese.

Nella tabella seguente sono elencati i filtri che è possibile utilizzare con il rapporto inventario telefoni IP.

### <a name="ip-phone-inventory-report-filters"></a>Filtri del rapporto inventario telefoni IP

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
<td><p><strong>From</strong></p></td>
<td><p>Data/ora di inizio per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di inizio come segue:</p>
<p>07/07/2012 13.00</p>
<p>Se non si immette una data/ora di inizio, il rapporto inizia automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane vanno sempre dal lunedì alla domenica.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Data/ora di fine per l'intervallo di tempo. Per visualizzare i dati in base all'ora, immettere sia la data che l'ora di fine come segue:</p>
<p>07/07/2012 13.00</p>
<p>Se non si immette una data/ora di fine, il rapporto termina automaticamente alle 00.00 del giorno specificato. Per visualizzare i dati in base al giorno, immettere solo la data:</p>
<p>7/7/2012</p>
<p>Per visualizzare i dati in base alla settimana o al mese, immettere una data compresa nella settimana o nel mese che si desidera visualizzare (non è necessario specificare il primo giorno della settimana o del mese):</p>
<p>7/3/2012</p>
<p>Le settimane vanno sempre dal lunedì alla domenica.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Produttore</strong></p></td>
<td><p>Nome della società che ha prodotto il telefono IP. I valori per questo filtro vengono inseriti automaticamente per l'utente in base ai telefoni IP attualmente presenti nel database.</p></td>
</tr>
<tr class="even">
<td><p><strong>Versione hardware</strong></p></td>
<td><p>Numero di versione del telefono IP; Se si utilizza il produttore e i filtri versione hardware, è possibile identificare in modo univoco un determinato tipo di telefono. I valori per questo filtro vengono inseriti automaticamente per l'utente in base ai telefoni IP attualmente presenti nel database.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agente utente</strong></p></td>
<td><p>Identificatore del software utilizzato dal telefono IP. I valori per questo filtro vengono inseriti automaticamente per l'utente in base ai telefoni IP attualmente presenti nel database.</p></td>
</tr>
<tr class="even">
<td><p><strong>Indirizzo MAC</strong></p></td>
<td><p>Identificatore univoco per l'interfaccia di rete sul telefono IP. L'indirizzo MAC (Media Access Control) in genere viene assegnato al momento in cui il telefono è prodotto e viene collegato all'hardware del dispositivo.</p>
<p>Per cercare i record relativi a uno specifico indirizzo MAC, è sufficiente immettere quell'indirizzo. Ad esempio:</p>
<p>00-08-5D-16-16-48</p>
<p>È necessario immettere l'indirizzo completo. Un indirizzo parziale (ad esempio 00-08-5D) non restituisce dati.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ultima attività prima di ogni giorno</strong></p></td>
<td><p>Selezionare uno dei seguenti valori:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>10 </p></li>
<li><p>20</p></li>
<li><p>30</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Ora ultima disconnessione prima di giorni</strong></p></td>
<td><p>Selezionare uno dei seguenti valori:</p>
<ul>
<li><p>Tutti</p></li>
<li><p>10 </p></li>
<li><p>20</p></li>
<li><p>30</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Prefisso URI utente</strong></p></td>
<td><p>Indirizzo SIP dell'utente che ha utilizzato il telefono IP.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Metriche

Nella tabella seguente sono elencate le informazioni fornite nel rapporto inventario telefoni IP.

### <a name="ip-phone-inventory-report-metrics"></a>Metriche del rapporto inventario telefoni IP

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Elemento utilizzabile per eseguire l'ordinamento?</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Produttore</strong></p></td>
<td><p>Sì</p></td>
<td><p>Nome della società che ha prodotto il telefono IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Versione hardware</strong></p></td>
<td><p>Sì</p></td>
<td><p>Numero di versione del telefono IP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Indirizzo MAC</strong></p></td>
<td><p>Sì</p></td>
<td><p>Identificatore univoco per l'interfaccia di rete sul telefono IP. L'indirizzo MAC è in genere assegnato al momento in cui il telefono è prodotto e viene collegato all'hardware del dispositivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI dell'utente</strong></p></td>
<td><p>Sì</p></td>
<td><p>Indirizzo SIP dell'utente che ha utilizzato il telefono IP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agente utente</strong></p></td>
<td><p>Sì</p></td>
<td><p>Identificatore del software utilizzato dal telefono IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ora ultimo accesso</strong></p></td>
<td><p>Sì</p></td>
<td><p>Data e ora dell'ultimo accesso del telefono IP a Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ora ultima disconnessione</strong></p></td>
<td><p>Sì</p></td>
<td><p>Data e ora dell'ultima disconnessione del telefono IP da Lync Server.</p></td>
</tr>
<tr class="even">
<td><p><strong>Ultima attività</strong></p></td>
<td><p>Sì</p></td>
<td><p>Data e ora dell'ultimo utilizzo del telefono IP.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

