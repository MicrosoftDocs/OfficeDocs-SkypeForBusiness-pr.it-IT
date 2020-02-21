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
ms.openlocfilehash: 389d545c18edb4a3c14fc2f0abdf5fb185fcd0ae
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="user-models-in-lync-server-2013"></a>Modelli utente in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-07_

I modelli utente descritti di seguito forniscono la base per le misure di pianificazione della capacità e i suggerimenti descritti nella [pianificazione della capacità di Lync Server 2013 utilizzando i modelli utente](lync-server-2013-capacity-planning-using-the-user-models.md).

<div>

## <a name="lync-server-2013-user-models"></a>Modelli utente di Lync Server 2013

Nella tabella seguente viene descritto il modello utente per la registrazione, i contatti, la messaggistica istantanea (IM) e la presenza per Lync Server 2013.

### <a name="environment-and-registration-user-model"></a>Modello utente per ambiente e registrazione

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
<td><p>Dimensione e distribuzione</p></td>
<td><p>Viene creato un modello di distribuzione estesa con tre siti centrali e un pool Front End per sito.</p></td>
</tr>
<tr class="even">
<td><p>Percentuale di utenti di Active Directory</p></td>
<td><p>Si presuppone che il 70% di tutti gli utenti di Active Directory nell'organizzazione sia abilitato per Lync Server. 80% di tali utenti abilitati sono connessi a Lync Server ogni giorno (80% Concurrency). Gli utenti simultanei rappresentano la base per i valori indicati nel resto di questa sezione.</p></td>
</tr>
<tr class="odd">
<td><p>Cambiamenti in Active Directory</p></td>
<td><p>Si presuppone che il 0,5% del totale degli utenti siano stati creati e abilitati per Lync in Active Directory ogni settimana e che il 0,5% del totale degli utenti sia disabilitato da Active Directory e da Lync ogni settimana. Per il 5% degli utenti viene modificato almeno un attributo di Active Directory ogni settimana.</p></td>
</tr>
<tr class="even">
<td><p>Gruppi di distribuzione di Active Directory</p></td>
<td><p>Si parte dal presupposto che il numero di gruppi di distribuzione di Active Directory nell'organizzazione sia pari a tre volte il numero di tutti gli utenti in Active Directory. Le dimensioni dei gruppi di distribuzione sono le seguenti:</p>
<ul>
<li><p>64% con 2-30 utenti</p></li>
<li><p>13% con 31-50 utenti</p></li>
<li><p>10% con 51-100 utenti</p></li>
<li><p>13% con 101-500 utenti</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Utenti di VoIP (Voice over IP)</p></td>
<td><p>60% degli utenti di Lync Server sono abilitati per le comunicazioni unificate (ovvero i numeri di telefono sono di proprietà di Lync Server).</p></td>
</tr>
<tr class="even">
<td><p>Distribuzione dei client registrati</p></td>
<td><p>il 65% dei client esegue il software Lync 2013, tra cui Lync e Lync Phone Edition.</p>
<p>30% dei client che eseguono il software client da una versione precedente di Lync.</p>
<p>5% di client che utilizzano Lync Web App.</p>
<p>Se la mobilità è abilitata, si presuppone che il 40% degli utenti utilizzi la mobilità contemporaneamente alle altre opzioni client registrate precedentemente citate. In questo caso, il rapporto più punti di presenza del client (MPOP) è 1:1.9. Se l'utilizzo dei dispositivi mobili è disabilitato, il rapporto MPOP invece è pari a 1:1,5.</p></td>
</tr>
<tr class="odd">
<td><p>Distribuzione degli utenti remoti</p></td>
<td><p>Il 70% degli utenti si connette internamente.</p>
<p>Il 30% degli utenti si connette tramite un server perimetrale e un server Director.</p></td>
</tr>
<tr class="even">
<td><p>Distribuzione dei contatti</p></td>
<td><p>Il numero massimo di contatti di cui può disporre un utente è 1.000. Meno dell'1% degli utenti dispone di 1.000 contatti. Meno del 25% degli utenti dispone di 100 o più contatti.</p>
<p>Media di 80 contatti per gli utenti con connettività a cloud pubblici. Di questi utenti:</p>
<ul>
<li><p>Il 50% dei contatti è all'interno dell'organizzazione. Il 10% di questi utenti è rappresentato da utenti remoti che si connettono dall'esterno del firewall.</p></li>
<li><p>Il 40% dei contatti è rappresentato da utenti di cloud pubblici, ad esempio AOL, Yahoo!, MSN o Google Talk.</p></li>
<li><p>Il 10% dei contatti proviene da partner federati.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Al 1 ° settembre 2012, la licenza di sottoscrizione di Microsoft Lync Public IM Connectivity ("PIC USL") non è più disponibile per l'acquisto dei contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di arresto del servizio. Una data di fine vita del 2014 giugno per AOL e Yahoo! sono stati annunciati. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
> <LI>
> <P>Il PIC USL è una licenza per ogni utente per ogni mese che è necessaria per Lync Server o Office Communications Server per la Federazione con Yahoo! Messaggero. La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale si sta liquidando.</P>
> <LI>
> <P>Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</P></LI></UL>


</div></li>
</ul>
<p>Media di 50 contatti per gli utenti senza connettività a cloud pubblici. Di questi utenti:</p>
<ul>
<li><p>L'80% dei contatti è all'interno dell'organizzazione. Il 10% di questi utenti è rappresentato da utenti remoti che si connettono dall'esterno del firewall.</p></li>
<li><p>Il 20% dei contatti proviene da partner federati.</p>
<p>Ogni utente dispone di un gruppo di distribuzione nell'elenco contatti. Per i test delle prestazioni, si presuppone che i gruppi di distribuzione siano sempre espansi.</p></li>
</ul>
<p>Il 25% dei contatti di un utente utilizza XMPP.</p></td>
</tr>
<tr class="odd">
<td><p>Durata delle sessioni</p></td>
<td><p>La sessione di accesso utente dura in media 12 ore. Tutti gli utenti eseguono l'accesso entro 120 minuti dall'avvio della sessione.</p></td>
</tr>
</tbody>
</table>


### <a name="im-and-presence-user-model"></a>Modello utente per messaggistica istantanea e presenza

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
<td><p>Ogni utente esegue in media sei sessioni di messaggistica istantanea peer-to-peer al giorno.</p>
<p>10 messaggi istantanei per sessione.</p>
<p>Ogni messaggio è associato a due messaggi di informazioni SIP e 2 messaggi SIP 200 OK (per gli indicatori di stato, ad&lt;esempio&gt; "nome digitando")</p></td>
</tr>
<tr class="even">
<td><p>Polling della presenza</p></td>
<td><p>In generale, si presuppongono 60 polling di presenza per utente all'ora. Per ogni utente si presuppone una media di:</p>
<ul>
<li><p>Un polling al giorno della presenza degli utenti nella scheda dell'organizzazione dell'utente, ma non nell'elenco Contatti. Il numero medio di utenti non contatti nella scheda dell'organizzazione dell'utente è di 15 utenti. Due operazioni di visualizzazione di schede contatto al giorno.</p></li>
<li><p>Un polling di presenza ogni volta che l'utente fa clic su un altro per avviare una conversazione, con frequenza stimata di una volta all'ora.</p></li>
<li><p>Sei ricerche utente all'ora. Ogni volta che viene eseguita una ricerca, viene inviato un polling batch per ogni utente nell'elenco dei risultati della ricerca. Si presuppone che la dimensione media dei risultati della ricerca sia di 20 utenti. Se i risultati della ricerca restano visualizzati sullo schermo, il polling batch viene aggiornato ogni cinque minuti. Si presuppongono due aggiornamenti di questo tipo all'ora.</p></li>
<li><p>Quando l'utente apre un messaggio di posta elettronica in Outlook o lo visualizza in anteprima, un polling della presenza per gli utenti nei campi A e Cc del messaggio di posta elettronica, con valori stimati di cinque messaggi di posta elettronica all'ora e quattro utenti per ogni messaggio.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Sottoscrizioni della presenza</p></td>
<td><p>Quando un utente ne aggiunge un altro come contatto, il primo utente <em>sottoscrive</em> cinque categorie di informazioni sul secondo utente. Gli aggiornamenti di queste categorie di informazioni vengono inviati automaticamente al primo utente.</p>
<p>Per ogni client, viene inviata una singola richiesta di sottoscrizione batch per ottenere lo stato di presenza di una media di 40 contatti, con ulteriori 40 finestre di dialogo per ottenere la presenza dei contatti federati.</p>
<p>Le informazioni sulla presenza per i membri di un gruppo di distribuzione espanso vengono trovate mediante sottoscrizioni della presenza persistenti e non mediante il polling. Il modello prevede un'espansione per utente ogni due ore.</p>
<p>Le <em>sottoscrizioni brevi</em> si verificano quando un utente esegue l'accesso, viene eseguita una sottoscrizione batch per tutti i contatti dell'utente e quindi l'utente si disconnette. Si presuppongono sei sottoscrizioni brevi per utente all'ora, ognuna della durata di 10 minuti.</p></td>
</tr>
<tr class="even">
<td><p>Pubblicazione della presenza</p></td>
<td><p>Lo stato di presenza viene pubblicato con una media di quattro pubblicazioni per utente all'ora, con un massimo di sei pubblicazioni per utente all'ora.</p></td>
</tr>
<tr class="odd">
<td><p>Dimensione del documento delle informazioni sulla presenza</p></td>
<td><p>Si presuppone che la dimensione media di un documento completo di informazioni sulla presenza corrisponda a 4 K, fino a un massimo di 25 K.</p></td>
</tr>
</tbody>
</table>


Nella tabella riportata di seguito viene descritto il modello utente per l'utilizzo della Rubrica.

### <a name="address-book-usage-user-model"></a>Modello utente per l'utilizzo della Rubrica

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Modalità di ricerca nella Rubrica</th>
<th>Usage</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Solo query Web nella Rubrica (tutte le query eseguite dal servizio Address Book Web Query)</p></td>
<td><p>Quattro query di prefisso per utente al giorno.</p>
<p>60 query di ricerca esatta per utente al giorno. Il 40% di queste è eseguito in batch, con una media di 20 contatti per query. L'altro 60% delle query è per un singolo contatto.</p>
<p>25 query di foto per utente al giorno. 24 per una singola foto, l'altra è una query in batch con una media di 20 contatti.</p>
<p>Una query di ricerca in tutta l'organizzazione per utente al giorno.</p></td>
</tr>
<tr class="even">
<td><p>Modalità mista con utilizzo sia di query nel file della Rubrica che di query Web. Questa è la modalità predefinita.</p></td>
<td><p>Solo due tipi di query vanno in rete, ovvero le query di ricerca di foto e quelle di ricerca in tutta l'organizzazione.</p>
<p>25 query di foto per utente al giorno. 24 per una singola foto, l'altra è una query in batch con una media di 20 contatti.</p>
<p>Una query di ricerca in tutta l'organizzazione per utente al giorno.</p></td>
</tr>
</tbody>
</table>


Nella tabella seguente viene descritto il modello per i servizi di conferenza.

### <a name="conferencing-model"></a>Modello per i servizi di conferenza

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
<td><p>&quot;Riunioni pianificate e riunioni&quot; risalenti a oggi</p></td>
<td><p>60% pianificate, 40% non pianificate.</p>
<p>Delle riunioni pianificate, si presuppone che l'80% corrisponda a conferenze assegnate, ovvero occorrenze di conferenze ricorrenti, il 10% corrisponda a riunioni aperte occasionali, l'8% corrisponda a riunioni anonime occasionali e il 2% corrisponda a riunioni chiuse occasionali.</p></td>
</tr>
<tr class="even">
<td><p>Distribuzione dei client per i servizi di conferenza</p></td>
<td><p>Per le riunioni pianificate:</p>
<ul>
<li><p>65% di utenti di conferenze utilizzano Lync 2013.</p></li>
<li><p>5% di utenti di conferenze utilizzano Microsoft Lync Web App.</p></li>
<li><p>il 30% degli utenti di servizi di conferenza utilizza client precedenti, tra cui Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 e Microsoft Office Communicator Web Access (versione 2007).</p></li>
</ul>
<p>Per le riunioni non pianificate:</p>
<ul>
<li><p>70% di utenti di conferenze utilizzano Lync 2013.</p></li>
<li><p>il 30% degli utenti di servizi di conferenza utilizza client precedenti, tra cui Microsoft Lync 2010, Office Communicator 2007 R2, Office Communicator 2007 e Microsoft Office Communicator Web Access (versione 2007).</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Concorrenza riunione</p></td>
<td><p>Il 5% degli utenti sarà in conferenza durante le ore lavorative. Per un pool di 80.000 utenti, pertanto, fino a 4.000 utenti potrebbe essere in conferenza contemporaneamente.</p></td>
</tr>
<tr class="even">
<td><p>Distribuzione dell'audio delle riunioni</p></td>
<td><p>40% misto di audio VoIP e conferenza telefonica con accesso esterno, con un rapporto di 3:1 di utenti VoIP rispetto agli utenti connessi tramite chiamata in ingresso.</p>
<p>35% solo audio VoIP.</p>
<p>15% solo audio di conferenza telefonica con accesso esterno.</p>
<p>10% senza audio (conferenze solo con messaggi istantanei, con una media di cinque messaggi inviati per utente).</p></td>
</tr>
<tr class="odd">
<td><p>Combinazioni multimediali per le conferenze</p></td>
<td><p>Il 75% delle conferenze è rappresentato da conferenze Web, che includono funzionalità audio e altre modalità di collaborazione.</p>
<p>Per queste conferenze, gli altri metodi di collaborazione sono i seguenti:</p>
<div>

> [!NOTE]  
> La somma di questi numeri è maggiore del 100% perché in una conferenza si possono utilizzare più metodi di collaborazione.


</div>
<ul>
<li><p>Nel 50% viene aggiunta la condivisione di applicazioni. Si presuppone che un utente invii dati fino a un massimo di 1,1 MB al secondo.</p></li>
<li><p>Nel 50% viene aggiunta la messaggistica istantanea (con una media di due messaggi per utente).</p></li>
<li><p>Nel 20% viene aggiunta la collaborazione dati, inclusi PowerPoint o una lavagna. In questo gruppo in media vengono presentati due file di PowerPoint per conferenza, con una dimensione media dei file di PowerPoint di 10 MB (senza video incorporato) o di 30 MB (con video incorporato). Sono presenti in media 20 annotazioni per lavagna.</p></li>
<li><p>Nel 20% viene aggiunto il video. Di questi utenti, il 70% partecipa a conferenze abilitate per il video multiview, in cui ogni utente riceve 2-3 flussi video.</p></li>
<li><p>Nel 15% vengono aggiunte note condivise.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Distribuzione dei partecipanti alle riunioni</p></td>
<td><p>50% utenti interni autenticati.</p>
<p>25% utenti autenticati con accesso remoto.</p>
<p>15% utenti anonimi.</p>
<p>10% utenti federati.</p></td>
</tr>
<tr class="odd">
<td><p>Distribuzione della partecipazione alle riunioni</p></td>
<td><p>Si presuppone la partecipazione degli utenti alla riunione entro i primi cinque minuti.</p></td>
</tr>
</tbody>
</table>


In pool Front End regolari, Lync Server 2013 ha una dimensione massima di riunioni supportate di 250 utenti. Ogni pool può ospitare una riunione da 250 utenti per volta. Mentre è in corso una riunione di dimensioni così elevate, il pool può ospitare anche altre conferenze più ridotte. È inoltre possibile supportare riunioni a cui partecipano fino a 1000 utenti configurando un pool dedicato per ospitare tali riunioni. Per informazioni dettagliate, vedere [supporto per le riunioni di grandi dimensioni in Lync Server 2013](lync-server-2013-support-for-large-meetings.md).

Sono state simulate le conferenze seguenti:

  - 85% di conferenze con quattro partecipanti.

  - 10% di conferenze con sei partecipanti.

  - 5% di conferenze con 11 partecipanti.

  - Una conferenza estesa con 250 utenti.

Nella tabella seguente sono disponibili informazioni dettagliate sul modello utente per le conferenze che coinvolgono utenti connessi tramite chiamate in ingresso.

### <a name="dial-in-conferencing-user-model"></a>Modello utente per conferenze telefoniche con accesso esterno

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
<td><p>Il 70% dei chiamanti partecipa in modalità anonima e deve specificare un nome registrato. Il 30% partecipa come utente autenticato.</p></td>
</tr>
<tr class="even">
<td><p>Durata delle chiamate e musica di attesa</p></td>
<td><p>Durata media della chiamata senza musica di attesa: 50 secondi.</p>
<p>Il 50% degli utenti che chiamano ascoltano la musica di attesa per una media di 5 minuti.</p></td>
</tr>
<tr class="odd">
<td><p>Multifrequenza (DTMF)</p></td>
<td><p>Per il 15% delle conferenze telefoniche con accesso esterno è presente un coordinatore della chiamata. Anche per il 10% delle conferenze miste che includono utenti connessi tramite chiamate in ingresso sono presenti coordinatori della chiamata.</p>
<p>Il 20% dei coordinatori utilizza due comandi DTMF per conferenza.</p></td>
</tr>
<tr class="even">
<td><p>Lingue degli annunci</p></td>
<td><p>Nelle simulazioni viene utilizzato l'inglese come lingua degli annunci.</p></td>
</tr>
</tbody>
</table>


Nella tabella seguente sono disponibili informazioni dettagliate sul modello utente per le sale di attesa delle conferenze.

### <a name="conference-lobby-user-model"></a>Modello utente per le sale di attesa delle conferenze

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
<td><p>Il 5% degli utenti che si connettono tramite chiamate in ingresso passa dalla sala di attesa, come il 25% degli altri utenti</p></td>
</tr>
<tr class="even">
<td><p>Ammissione dalla sala di attesa</p></td>
<td><p>Nelle simulazioni tutti gli utenti sono stati ammessi dal relatore prima del timeout del client.</p></td>
</tr>
</tbody>
</table>


Nella tabella riportata di seguito viene descritto il modello utente per altre sessioni peer-to-peer.

### <a name="peer-to-peer-sessions-user-model"></a>Modello utente per altre sessioni peer-to-peer

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
<td><p>Ogni utente partecipa a cinque sessioni di condivisione applicazioni peer-to-peer al mese, per una media di 0,25 sessioni al giorno.</p></td>
</tr>
<tr class="even">
<td><p>Trasferimento di file</p></td>
<td><p>Ogni utente partecipa a 1 sessione di trasferimento file peer-to-peer al mese (nell'ambito di una sessione di messaggistica istantanea), per una media di 0,05 sessioni al giorno. Le dimensioni medie dei file trasferiti durante la sessione sono di 1 MB.</p></td>
</tr>
</tbody>
</table>


Nella tabella seguente viene descritto il modello utente per i criteri.

### <a name="policies-user-model"></a>Modello utente per i criteri

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
<td><p>Si presuppone che siano configurati un criterio globale, 10 criteri tag di conferenza, quattro criteri di archiviazione e 10 criteri tag di presenza.</p></td>
</tr>
<tr class="even">
<td><p>Criteri vocali</p></td>
<td><p>Si presuppone che esista un criterio globale e 2 criteri di tag per sito. il 100% dei siti dispone di un criterio sito e il 30% degli utenti ha un criterio per utente assegnato. Si presuppone un dial plan per sito e due route per sito.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="busy-hour"></a>Ora di punta

Per le sessioni peer-to-peer, il carico di picco viene calcolato tramite l'indicatore dei tentativi di chiamata durante l'ora di punta, noto anche come BHCA (Busy Hour Call Attempt). Questo indicatore del settore presuppone che il 50% di tutte le chiamate in un giorno venga effettuato nel 20% del tempo. Per il calcolo viene utilizzata la formula seguente:

`BHCA=(total calls * 0.5) / 1.6`

Per i test delle prestazioni l'ora di punta è stata simulata eseguendo sessioni VoIP e altre sessioni peer-to-peer con un carico di picco per almeno 1,6 ore al giorno.

Nel carico di picco per le conferenze si presuppone che il 75% di tutte le conferenze per un giorno di otto ore venga effettuato in 4 ore di punta. In tali ore di punta si concentra 1,5 volte il carico medio delle conferenze.

</div>

<div>

## <a name="enterprise-voice-to-pstn-calls"></a>VoIP aziendale per le chiamate PSTN

Le seguenti ipotesi si applicano alle chiamate vocali di VoIP aziendale:

  - 50% di utenti sono abilitati per VoIP aziendale e il 60% di questi utenti è abilitato per le chiamate PSTN.

  - Ognuno di questi utenti abilitati per le chiamate PSTN esegue quattro chiamate PSTN durante l'orario lavorativo. Ogni chiamata dura tre minuti.

  - Nel 65% di queste chiamate vocali PSTN viene utilizzato il bypass multimediale.

</div>

<div>

## <a name="mobility"></a>Mobilità

Si presuppone che il 40% degli utenti registrati sia abilitato per i dispositivi mobili. Per ogni utente abilitato per i dispositivi mobili, si presuppone che l'attività del client mobile si aggiunga a quella delle altre istanze MPOP dell'utente, ad eccezione delle interazioni con i servizi di conferenza, per cui il client per servizi mobili rappresenta solo un altro tipo di client che può essere utilizzato per partecipare alle conferenze.

</div>

<div>

## <a name="persistent-chat"></a>Persistent Chat

Si presuppone che il 25% degli utenti registrati parteciperà a sessioni di Persistent Chat, con le caratteristiche seguenti:

  - Una media di 1,5 chat room per utente

  - Ogni chat room comporta 12 richieste di polling all'ora, con una media di 10 utenti per ognuna

</div>

<div>

## <a name="response-group-and-call-park"></a>Response Group e parcheggio di chiamata

Si presuppone che lo 0,15% degli utenti registrati appartenga a Response Group e che lo 0,02% degli utenti registrati utilizzi la funzionalità di parcheggio di chiamata in un determinato momento.

</div>

</div>

<span> </span>

</div>

</div>

</div>

