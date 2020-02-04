---
title: 'Lync Server 2013: modelli utente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server 2013 user models
ms:assetid: c551371c-d740-4372-bada-f0d713ec0d33
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398811(v=OCS.15)
ms:contentKeyID: 49733811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8f45b3ea11911ea7a3dce36b0b6a9d64ac1e690
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41744586"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="user-models-in-lync-server-2013"></a>Modelli utente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-07_

I modelli di utenti descritti in questa sezione costituiscono la base per le misure e le raccomandazioni per la pianificazione della capacità descritte nella [pianificazione della capacità per Lync Server 2013 con i modelli utente](lync-server-2013-capacity-planning-using-the-user-models.md).

<div>

## <a name="lync-server-2013-user-models"></a>Modelli di utenti di Lync Server 2013

La tabella seguente descrive il modello di utente per la registrazione, i contatti, la messaggistica istantanea e la presenza per Lync Server 2013.

### <a name="environment-and-registration-user-model"></a>Modello utente ambiente e registrazione

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoria</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dimensioni e distribuzione della distribuzione</p></td>
<td><p>Modelliamo una distribuzione di grandi dimensioni con tre siti centrali, con un pool di front-end per ogni sito.</p></td>
</tr>
<tr class="even">
<td><p>Percentuale di utenti di Active Directory</p></td>
<td><p>Supponiamo che il 70% di tutti gli utenti di Active Directory dell'organizzazione siano abilitati per Lync Server. 80% degli utenti abilitati hanno eseguito l'accesso a Lync Server ogni giorno (80% di concorrenza). Gli utenti simultanei sono la base per i numeri nel resto di questa sezione.</p></td>
</tr>
<tr class="odd">
<td><p>Modifiche di Active Directory</p></td>
<td><p>Supponiamo che il 0,5% degli utenti totali venga creato e abilitato per Lync in Active Directory ogni settimana e che il 0,5% degli utenti totali sia disabilitato da Active Directory e da Lync ogni settimana. il 5% degli utenti ha almeno un attributo Active Directory modificato ogni settimana.</p></td>
</tr>
<tr class="even">
<td><p>Gruppi di distribuzione di Active Directory</p></td>
<td><p>Supponiamo che il numero di gruppi di distribuzione di Active Directory nell'organizzazione sia pari a tre volte il numero di tutti gli utenti in Active Directory. I gruppi di distribuzione hanno le dimensioni seguenti:</p>
<ul>
<li><p>64% hanno utenti di 2-30</p></li>
<li><p>il 13% ha 31-50 utenti</p></li>
<li><p>10% hanno 51-100 utenti</p></li>
<li><p>il 13% ha 101-500 utenti</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Utenti VoIP (Voice over IP)</p></td>
<td><p>60% degli utenti di Lync Server sono abilitati per le comunicazioni unificate (UC), ovvero i relativi numeri di telefono sono di proprietà di Lync Server.</p></td>
</tr>
<tr class="even">
<td><p>Distribuzione client registrata</p></td>
<td><p>il 65% dei client esegue il software Lync 2013, inclusi Lync e Lync Phone Edition.</p>
<p>30% dei client che gestiscono il software client da una versione precedente di Lync.</p>
<p>5% di client che usano Lync Web App.</p>
<p>Se è abilitata la mobilità, presupponiamo che il 40% degli utenti usi la mobilità in concomitanza con le altre opzioni del client registrato precedentemente citate. In questo caso, il rapporto di multiple Point of Presence (MPOP) del client è 1:1.9. Se la mobilità è disabilitata, il rapporto MPOP è 1:1.5.</p></td>
</tr>
<tr class="odd">
<td><p>Distribuzione remota degli utenti</p></td>
<td><p>70% degli utenti che si connettono internamente.</p>
<p>30% degli utenti che si connettono tramite un server perimetrale e un amministratore.</p></td>
</tr>
<tr class="even">
<td><p>Distribuzione di contatti</p></td>
<td><p>Il numero massimo di contatti di un utente è 1.000. Meno dell'1% degli utenti ha contatti di 1.000. Meno del 25% degli utenti ha 100 o più contatti.</p>
<p>Media dei contatti di 80 per gli utenti con connettività cloud pubblica. Di questi utenti:</p>
<ul>
<li><p>50% dei contatti si trovano all'interno dell'organizzazione. il 10% degli utenti sono utenti remoti, che si connettono dall'esterno del firewall.</p></li>
<li><p>40% dei contatti sono utenti di cloud pubblici (ad esempio utenti di AOL, Yahoo!, MSN o Google Talk).</p></li>
<li><p>il 10% dei contatti è da partner federati.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di chiusura del servizio. Data di fine vita del 2014 giugno per AOL e Yahoo! è stato annunciato. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
> <LI>
> <P>Il PIC USL è una licenza per abbonamento mensile per ogni utente necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo! Messenger. La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto di Yahoo!, l'accordo sottostante per il quale sta per finire.</P>
> <LI>
> <P>Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e voce.</P></LI></UL>


</div></li>
</ul>
<p>Media dei contatti di 50 per gli utenti senza connettività cloud pubblica. Di questi utenti:</p>
<ul>
<li><p>80% dei contatti si trovano all'interno dell'organizzazione. il 10% degli utenti sono utenti remoti, che si connettono dall'esterno del firewall.</p></li>
<li><p>il 20% dei contatti è da partner federati.</p>
<p>Ogni utente ha un gruppo di distribuzione nell'elenco contatti. Per i test delle prestazioni, presupponiamo che i gruppi di distribuzione siano sempre espansi.</p></li>
</ul>
<p>il 25% dei contatti di un utente usa XMPP.</p></td>
</tr>
<tr class="odd">
<td><p>Ora della sessione</p></td>
<td><p>La sessione di accesso utente media dura 12 ore. Tutti gli utenti accedono a 120 minuti dall'inizio della sessione.</p></td>
</tr>
</tbody>
</table>


### <a name="im-and-presence-user-model"></a>Modello utente di messaggistica istantanea e presenza

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoria</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Sessioni di messaggistica istantanea peer-to-peer</p></td>
<td><p>Ogni utente calcola la media di sei sessioni di messaggistica istantanea peer-to-peer per giorno.</p>
<p>10 messaggi istantanei per sessione.</p>
<p>Ogni messaggio è abbinato a due messaggi di informazioni SIP e 2 messaggi OK di SIP 200 (per gli indicatori di stato&lt;,&gt; ad esempio "nome sta digitando")</p></td>
</tr>
<tr class="even">
<td><p>Polling presenza</p></td>
<td><p>In generale, presupponiamo il polling della presenza in media di 60 sondaggi per utente per ora. Per ogni utente, assumere una media di:</p>
<ul>
<li><p>Un sondaggio per giorno della presenza di utenti nella scheda organizzazione dell'utente, ma non nell'elenco contatti. Il numero medio di non contatti nella scheda organizzazione dell'utente è di 15 utenti. Due operazioni di visualizzazione della scheda contatto per giorno.</p></li>
<li><p>Un sondaggio di presenza ogni volta che l'utente fa clic su un altro utente per avviare una conversazione, stimata in una volta all'ora.</p></li>
<li><p>Sei ricerche utente per ora. Ogni volta che viene eseguita una ricerca, viene inviato un sondaggio batch per tutti gli utenti nell'elenco dei risultati di ricerca. Supponiamo che la dimensione media dei risultati della ricerca sia 20. Se i risultati della ricerca rimangono sullo schermo, il sondaggio batch viene aggiornato ogni 5 minuti; Supponiamo che ci saranno due aggiornamenti per ora.</p></li>
<li><p>Quando l'utente apre o Visualizza in anteprima un messaggio di posta elettronica in Outlook, viene visualizzato un sondaggio sulla presenza degli utenti nei campi a: e CC: del messaggio di posta elettronica, stimati in cinque messaggi all'ora e quattro utenti per ogni messaggio di posta elettronica.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Abbonamenti alla presenza</p></td>
<td><p>Quando un utente aggiunge un altro come contatto, il primo utente sta <em>sottoscrivendo</em> cinque categorie di informazioni sul secondo utente. Gli aggiornamenti di queste categorie di informazioni vengono inviati automaticamente al primo utente.</p>
<p>Per ogni client, viene inviata una richiesta di abbonamento a un singolo batch per ottenere lo stato di presenza di una media di contatti di 40, con una finestra di dialogo di 40 aggiuntiva per ottenere la presenza di contatti federati.</p>
<p>La presenza per i membri di un gruppo di distribuzione espanso viene trovata tramite sottoscrizioni di presenza persistente, non polling, ed è modellata come 1 espansione per ogni utente per ogni 2 ore.</p>
<p>Gli <em>abbonamenti brevi</em> si verificano quando un utente effettua l'accesso, esiste un abbonamento batch per tutti i contatti dell'utente e quindi l'utente si disconnette presto. Assumiamo 6 abbonamenti brevi per ogni utente per ora, in cui ogni sottoscrizione dura 10 minuti.</p></td>
</tr>
<tr class="even">
<td><p>Pubblicazione di presenza</p></td>
<td><p>Lo stato presenza viene pubblicato in media 4 pubblicazioni per utente per ora, con un massimo di 6 per utente per ora.</p></td>
</tr>
<tr class="odd">
<td><p>Dimensioni del documento di presenza</p></td>
<td><p>Si presume che la dimensione media di un documento di presenza completa sia 4K, con un massimo di 25K.</p></td>
</tr>
</tbody>
</table>


La tabella seguente descrive il modello di utente per l'uso della Rubrica.

### <a name="address-book-usage-user-model"></a>Modello utente utilizzo Rubrica

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Modalità di ricerca della Rubrica</th>
<th>L'uso</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Solo query Web della Rubrica (tutte le query eseguite dal servizio query Web Rubrica)</p></td>
<td><p>Quattro query di prefisso per utente per giorno.</p>
<p>60 query di ricerca esatte per utente per giorno. 40% di questi vengono raggruppati in batch, con una media di 20 contatti per query. L'altro 60% delle query è per un singolo contatto.</p>
<p>25 query fotografiche per utente per giorno. 24 per una singola foto, l'altra è una query batch con una media di 20 contatti.</p>
<p>Una query di ricerca totale dell'organizzazione per ogni utente per giorno.</p></td>
</tr>
<tr class="even">
<td><p>Modalità mista, sia file della rubrica che query Web usate. Questa è la modalità predefinita.</p></td>
<td><p>Solo due tipi di query accedono alla rete, alla foto e alle query di ricerca dell'organizzazione totale.</p>
<p>25 query fotografiche per utente per giorno. 24 per una singola foto, l'altra è una query batch con una media di 20 contatti.</p>
<p>Una query di ricerca totale dell'organizzazione per ogni utente per giorno.</p></td>
</tr>
</tbody>
</table>


La tabella seguente descrive il modello di conferenza.

### <a name="conferencing-model"></a>Modello di conferenza

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoria</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Riunioni pianificate &quot;rispetto alle&quot; riunioni di riunione ora</p></td>
<td><p>60% programmato, 40% non programmato.</p>
<p>Delle riunioni pianificate, supponiamo che al 80% vengano assegnate conferenze, che sono occorrenze di conferenze periodiche; 10% sono riunioni aperte una tantum; 8% sono riunioni anonime una tantum e il 2% sono riunioni chiuse una sola volta.</p></td>
</tr>
<tr class="even">
<td><p>Distribuzione client di servizi di conferenza</p></td>
<td><p>Per le riunioni pianificate:</p>
<ul>
<li><p>65% degli utenti dei servizi di conferenza usano Lync 2013.</p></li>
<li><p>il 5% degli utenti dei servizi di conferenza USA Microsoft Lync Web App.</p></li>
<li><p>il 30% degli utenti dei servizi di conferenza USA client precedenti, inclusi Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 e Microsoft Office Communicator Web Access (versione 2007).</p></li>
</ul>
<p>Per le riunioni non pianificate:</p>
<ul>
<li><p>70% degli utenti dei servizi di conferenza usano Lync 2013.</p></li>
<li><p>il 30% degli utenti dei servizi di conferenza USA client precedenti, inclusi Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 e Microsoft Office Communicator Web Access (versione 2007).</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Concorrenza della riunione</p></td>
<td><p>il 5% degli utenti sarà in conferenze durante l'orario di lavoro. Quindi, in un pool di utenti di 80.000, almeno un numero di utenti di 4.000 potrebbe essere presente in una conferenza in qualsiasi momento.</p></td>
</tr>
<tr class="even">
<td><p>Distribuzione audio della riunione</p></td>
<td><p>40% di servizi di audioconferenza misti VoIP e con accesso esterno, con un rapporto di 3:1 degli utenti VoIP per gli utenti connessi con la chiamata.</p>
<p>solo audio VoIP per 35%.</p>
<p>solo audio per conferenze telefoniche con accesso esterno per il 15%.</p>
<p>10% Nessun audio (conferenze di messaggistica istantanea con una media di cinque messaggi inviati per ogni utente).</p></td>
</tr>
<tr class="odd">
<td><p>Combinazione multimediale per le conferenze</p></td>
<td><p>75% delle conferenze sono conferenze Web, che includono l'audio e altre modalità di collaborazione.</p>
<p>Per queste conferenze, gli altri metodi di collaborazione sono i seguenti:</p>
<div>

> [!NOTE]  
> Questi numeri sommano più di 100% perché una conferenza può avere più metodi di collaborazione.


</div>
<ul>
<li><p>50% Aggiungi condivisione applicazioni. Supponiamo che un utente invii i dati a un massimo di 1,1 MB al secondo.</p></li>
<li><p>50% aggiungere la messaggistica istantanea (con una media di 2 messaggi per utente).</p></li>
<li><p>20% aggiungere la collaborazione ai dati, tra cui PowerPoint o lavagna in questi, una media di 2 file di PowerPoint presentati per conferenza, con una dimensione media di file di PowerPoint di 10 MB (senza video incorporato) o 30 MB (con video incorporato). Media di 20 annotazioni per lavagna.</p></li>
<li><p>aggiungere un video del 20%. Di questi utenti, 70% sono in conferenze abilitate per il video MultiView, in cui ogni utente riceve i flussi video di 2-3.</p></li>
<li><p>15% aggiungere note condivise.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Distribuzione di partecipanti alla riunione</p></td>
<td><p>50% utenti interni e autenticati.</p>
<p>25% di accesso remoto, utenti autenticati.</p>
<p>15% utenti anonimi.</p>
<p>10% utenti federati.</p></td>
</tr>
<tr class="odd">
<td><p>Distribuzione di join di riunione</p></td>
<td><p>Gli utenti vengono simulati per partecipare alla riunione entro i primi 5 minuti.</p></td>
</tr>
</tbody>
</table>


Nei pool di front end regolari Lync Server 2013 ha una dimensione di riunione massima supportata di 250 utenti. Ogni pool può ospitare 1 250-riunione utente alla volta. Mentre si verifica questa riunione di grandi dimensioni, il pool può ospitare anche altre conferenze più piccole. Inoltre, puoi supportare riunioni fino a 1000 utenti impostando un pool dedicato per ospitare queste riunioni. Per informazioni dettagliate, vedere [supporto per riunioni di grandi dimensioni in Lync Server 2013](lync-server-2013-support-for-large-meetings.md).

Le conferenze sono state simulate nel modo seguente:

  - il 85% delle conferenze ha quattro partecipanti.

  - il 10% delle conferenze ha sei partecipanti.

  - il 5% delle conferenze ha 11 partecipanti.

  - Una conferenza di grandi dimensioni per gli utenti di 250.

La tabella seguente fornisce informazioni dettagliate sul modello di utente per le conferenze che coinvolgono utenti con accesso esterno.

### <a name="dial-in-conferencing-user-model"></a>Modello utenti di servizi di conferenza telefonica con accesso esterno

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoria</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Autenticato/Anonimo</p></td>
<td><p>il 70% dei chiamanti si iscrive come anonimo e viene richiesto un nome registrato. 30% partecipa come utenti autenticati.</p></td>
</tr>
<tr class="even">
<td><p>Durata chiamata e musica in attesa</p></td>
<td><p>Durata media della chiamata senza musica in attesa: 50 secondi.</p>
<p>per una media di 5 minuti, 50% degli utenti di chiamate in attesa sente musica in sospeso.</p></td>
</tr>
<tr class="odd">
<td><p>DTMF (Dual-Tone Multifrequency)</p></td>
<td><p>il 15% delle conferenze telefoniche con accesso esterno ha solo i responsabili del telefono. il 10% delle conferenze miste che includono utenti con accesso esterno hanno anche i responsabili del telefono.</p>
<p>il 20% dei responsabili telefonici USA 2 comandi DTMF per conferenza.</p></td>
</tr>
<tr class="even">
<td><p>Lingue di annunci</p></td>
<td><p>Le simulazioni usano l'inglese come lingua di annuncio.</p></td>
</tr>
</tbody>
</table>


La tabella seguente fornisce informazioni dettagliate sul modello di utente per le lobby delle conferenze.

### <a name="conference-lobby-user-model"></a>Modello di utente di lobby conferenza

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoria</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Numero di utenti nella sala di attesa</p></td>
<td><p>il 5% degli utenti con accesso esterno passa attraverso la sala d'attesa e il 25% degli altri utenti passa attraverso la sala d'attesa</p></td>
</tr>
<tr class="even">
<td><p>Ammissione dalla sala di attesa</p></td>
<td><p>In simulazioni tutti gli utenti sono stati ammessi dal relatore prima del timeout del client.</p></td>
</tr>
</tbody>
</table>


La tabella seguente descrive il modello di utente per altre sessioni peer-to-peer.

### <a name="peer-to-peer-sessions-user-model"></a>Modello utente sessioni peer-to-peer

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoria</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Condivisione applicazioni</p></td>
<td><p>Ogni utente partecipa a 5 sessioni di condivisione delle applicazioni peer-to-peer al mese, per una media di 0,25 sessioni al giorno.</p></td>
</tr>
<tr class="even">
<td><p>Trasferimento di file</p></td>
<td><p>Ogni utente partecipa a una sessione di trasferimento di file peer-to-peer al mese (nell'ambito di una sessione di messaggistica istantanea), per una media di 0,05 sessioni al giorno. La dimensione media del file della sessione trasferita è di 1 MB.</p></td>
</tr>
</tbody>
</table>


La tabella seguente descrive il modello di utente per i criteri.

### <a name="policies-user-model"></a>Modello di criteri utente

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Categoria</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Criteri di conferenza, presenza e archiviazione</p></td>
<td><p>Supponiamo che esistano un criterio globale, 10 criteri di conferenza tag, 4 criteri di archiviazione e 10 criteri di presenza dei tag.</p></td>
</tr>
<tr class="even">
<td><p>Criteri vocali</p></td>
<td><p>Supponiamo che esistano un criterio globale e due criteri per i tag per sito. il 100% dei siti ha un criterio per il sito e il 30% degli utenti ha un criterio per utente assegnato. Assumiamo un dial plan per ogni sito e due rotte per sito.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a>Ora occupato

Per le sessioni peer-to-peer, il carico di picco viene calcolato usando i tentativi di chiamata di ora occupato (BHCA). Questo termine del settore vocale presuppone che il 50% di tutte le chiamate per il giorno verrà completato in 20% del tempo. Viene calcolata usando la formula seguente:

`BHCA=(total calls * 0.5) / 1.6`

Test delle prestazioni ora di occupato simulato eseguendo VoIP e altre sessioni peer-to-peer a un carico di ora occupato per almeno 1,6 ore al giorno.

Il carico di picco per i servizi di conferenza presuppone che il 75% di tutte le conferenze per un giorno di otto ore avvenga in quattro ore di punta. Le ore di punta hanno 1,5 volte il carico di conferenza media.

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a>VoIP aziendale per chiamate PSTN

Le ipotesi seguenti si applicano alle chiamate vocali aziendali:

  - 50% degli utenti sono abilitati per VoIP aziendale e il 60% di questi utenti è abilitato per le chiamate PSTN.

  - Ognuno di questi utenti abilitato per la chiamata PSTN effettua 4 chiamate PSTN durante l'ora di occupato. Ogni durata della chiamata è di 3 minuti.

  - 65% di queste chiamate vocali PSTN usano il bypass multimediale.

</div>

<div>

## <a name="mobility"></a>Mobilità

si presume che il 40% degli utenti registrati sia abilitato per la mobilità. Per ogni utente abilitato alla mobilità, supponiamo che l'attività del client per dispositivi mobili sia additiva rispetto alle altre istanze di MPOP per tale utente, ad eccezione delle interazioni di conferenza, per cui il client di mobilità è solo un altro tipo di client che può essere usato per partecipare alle conferenze.

</div>

<div>

## <a name="persistent-chat"></a>Chat persistente

Presupponiamo che il 25% degli utenti registrati sarà coinvolto in sessioni di chat persistenti, con le caratteristiche seguenti:

  - Media delle chat room di 1,5 per utente

  - Ogni chat room genera 12 richieste di polling per ora, destinate a una media di 10 utenti ogni

</div>

<div>

## <a name="response-group-and-call-park"></a>Gruppo di risposte e parcheggio delle chiamate

Supponiamo che il 0,15% degli utenti registrati appartenga ai gruppi di risposta. Supponiamo che il 0,02% degli utenti registrati abbia chiamate parcheggiate in un dato momento.

</div>

</div>

<span> </span>

</div>

</div>

</div>

