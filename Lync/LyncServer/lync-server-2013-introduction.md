---
title: 'Lync Server 2013: Introduzione'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: df182c8d58d6f1e60b164fbb28299945f6a8cba3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982187"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a>Introduzione a Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-07_

Lync Server 2013 e il relativo software client, ad esempio Lync 2013, consentono agli utenti di connettersi in modo nuovo e di rimanere connessi, indipendentemente dalla loro posizione fisica. Lync e Lync Server riuniscono i diversi modi in cui gli utenti comunicano in una singola interfaccia client, vengono distribuiti come piattaforma unificata e gestiti tramite un'unica infrastruttura di gestione.

Questa tabella e le sezioni seguenti illustrano i set di caratteristiche principali o i *carichi di lavoro*, forniti da Lync Server per gli utenti.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Carico</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Messaggistica istantanea e presenza</p></td>
<td><p>Messaggistica istantanea (IM) e presenza aiutano gli utenti a trovare e comunicare tra loro in modo efficiente ed efficace.</p>
<p>IM offre una piattaforma di messaggistica istantanea con cronologia delle conversazioni e supporta la connettività di messaggistica immediata pubblica con gli utenti di reti di messaggistica istantanea pubbliche come MSN/Windows Live, Yahoo!, AOL e Google Talk.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User ("PIC USL") non è più disponibile per l'acquisto di contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di chiusura del servizio. Data di fine vita del 2014 giugno per AOL e Yahoo! è stato annunciato. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
> <LI>
> <P>Il PIC USL è una licenza per abbonamento mensile per ogni utente necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo! Messenger. La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto di Yahoo!, l'accordo sottostante per il quale sta per finire.</P>
> <LI>
> <P>Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e voce.</P></LI></UL>


</div>
<p>La presenza stabilisce e visualizza la disponibilità e la volontà personali di un utente per comunicare attraverso l'uso di stati comuni, come <strong>disponibile</strong> o <strong>occupato</strong>, oltre a stati più dettagliati, come ad esempio il <strong>ritorno a destra</strong> e <strong>non disturbare</strong>. Queste informazioni di presenza avanzata consentono ad altri utenti di effettuare immediatamente scelte di comunicazione efficaci.</p></td>
</tr>
<tr class="even">
<td><p>Servizi di conferenza</p></td>
<td><p>Lync Server include il supporto per la messaggistica istantanea, le conferenze audio, le conferenze Web, le videoconferenze e la condivisione di applicazioni, sia per le riunioni programmate che per quelle estemporanee. Tutti questi tipi di riunione sono supportati con un singolo client. Lync Server supporta inoltre i servizi di conferenza telefonica con accesso esterno in modo che gli utenti di telefoni PSTN (Public Switched Telephone Network) possano partecipare alla parte audio delle conferenze.</p>
<p>Le conferenze possono facilmente cambiare e crescere in tempo reale. Ad esempio, una singola conferenza può iniziare come solo messaggi istantanei tra pochi utenti e inoltrarsi a una conferenza audio con condivisione desktop e un pubblico più ampio istantaneamente, facilmente e senza interrompere il flusso di conversazione.</p></td>
</tr>
<tr class="odd">
<td><p>VoIP aziendale</p></td>
<td><p><em>Enterprise Voice</em> è l'offerta VoIP (Voice over Internet Protocol) in Lync Server. Offre un'opzione vocale per migliorare o sostituire sistemi PBX (Private Branch Exchange) tradizionali. Oltre alle funzionalità complete di telefonia di un IP PBX, Enterprise Voice è integrata con la presenza, la messaggistica istantanea, la collaborazione e le riunioni avanzate. Le caratteristiche come la risposta alle chiamate, il blocco, la ripresa, il trasferimento, l'inoltro e la deviazione sono supportate direttamente, mentre i tasti di scelta rapida personalizzati vengono sostituiti dagli elenchi di contatti e il citofono automatico viene sostituito da messaggistica istantanea.</p>
<p>Enterprise Voice supporta la disponibilità elevata tramite il controllo di ammissione alle chiamate (CAC), la sopravvivenza della filiale e le opzioni estese per la resilienza dei dati.</p></td>
</tr>
<tr class="even">
<td><p>Supporto per gli utenti remoti</p></td>
<td><p>Puoi specificare la funzionalità completa di Lync Server per gli utenti che si trovano al di fuori dei firewall dell'organizzazione distribuendo server denominati <em>Edge Server</em> per creare una connessione per questi utenti remoti. Questi utenti remoti possono connettersi alle conferenze usando un personal computer con Lync 2013 installato, il telefono o un'interfaccia Web.</p>
<p>La distribuzione di Edge Server consente inoltre di eseguire la <em>Federazione</em> con organizzazioni partner o fornitori. Una relazione federata consente agli utenti di inserire gli utenti federati negli elenchi dei contatti, le informazioni sulla presenza di Exchange e i messaggi istantanei con questi utenti e invitarli a chiamate audio, videochiamate e conferenze.</p></td>
</tr>
<tr class="odd">
<td><p>Supporto per i client per dispositivi mobili</p></td>
<td><p>Inoltre, con i servizi di mobilità di Lync Server, gli utenti possono accedere alle funzionalità di Lync quando usano i dispositivi mobili Apple iOS, Android, Windows Phone o Nokia ed eseguono attività come l'invio e la ricezione di messaggi istantanei, la visualizzazione di contatti, e la visualizzazione della presenza. I dispositivi mobili supportano inoltre alcune funzionalità VoIP aziendale, ad esempio fare clic per partecipare a una conferenza, chiamare tramite lavoro, raggiungere un numero singolo, la segreteria telefonica e le chiamate perse. Le notifiche push sono supportate anche per i dispositivi mobili che non supportano le applicazioni in uso in background.</p></td>
</tr>
<tr class="even">
<td><p>Integrazione con altri prodotti</p></td>
<td><p>Lync Server si integra con diversi altri prodotti per ottenere vantaggi aggiuntivi per gli utenti e gli amministratori.</p>
<p>Gli strumenti riunione sono integrati in Outlook per consentire agli organizzatori di pianificare una riunione o iniziare una conferenza estemporanea con un solo clic e renderlo altrettanto semplice per i partecipanti partecipare.</p>
<p>Le informazioni sulla presenza sono integrate in Outlook e SharePoint.</p>
<p>La messaggistica unificata di Exchange offre diverse funzionalità di integrazione. Gli utenti possono vedere se hanno una nuova segreteria telefonica in Lync Server. È possibile fare clic sul pulsante Riproduci nel messaggio di Outlook per ascoltare la segreteria telefonica o visualizzare una trascrizione della segreteria telefonica nel messaggio di notifica.</p>
<p>Inoltre, l'uso di Lync Server 2013 con Exchange 2013 consente di accedere a diverse nuove funzionalità, ad esempio un archivio contatti unificato, accessibile dai client di entrambi i prodotti, nonché foto ad alta risoluzione per i contatti archiviati nel database di Exchange 2013.</p></td>
</tr>
<tr class="odd">
<td><p>Distribuzione semplice</p></td>
<td><p>Per facilitare la pianificazione e la distribuzione di server e client, Lync Server fornisce il generatore di topologia.</p>
<p>Generatore di topologia è un componente di installazione di Lync Server. Si usa generatore di topologie per creare, modificare e pubblicare la topologia pianificata. Convalida anche la topologia prima di iniziare le installazioni del server. Quando si installa Lync Server nei singoli server, il programma di installazione distribuisce il server come indicato nella topologia.</p></td>
</tr>
<tr class="even">
<td><p>Gestione semplice</p></td>
<td><p>Dopo la distribuzione di Lync Server, offre gli strumenti di gestione potenti e semplificati seguenti:</p>
<ul>
<li><p>Gestione della configurazione centrale, che consente di gestire le modifiche in modo centralizzato e di replicarle rapidamente nell'intera distribuzione.</p></li>
<li><p>Pannello di controllo di Lync Server, un'interfaccia utente grafica basata sul Web per gli amministratori. Con questa interfaccia utente basata sul Web, gli amministratori di Lync Server possono gestire i loro sistemi ovunque si trovino nella rete aziendale, senza bisogno di un software di gestione specializzato installato nei propri computer.</p></li>
<li><p>Strumento di gestione della riga di comando di Lync Server Management Shell basato sull'interfaccia della riga di comando di Windows PowerShell. Fornisce un set di comandi RTF per l'amministrazione di tutti gli aspetti del prodotto e consente agli amministratori di Lync Server di automatizzare le attività ripetitive con uno strumento familiare.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Mentre le funzionalità di messaggistica istantanea e presenza vengono installate automaticamente in tutte le distribuzioni di Lync Server, è possibile scegliere se distribuire servizi di conferenza, VoIP aziendale e accesso remoto agli utenti per adattare la distribuzione alle esigenze dell'organizzazione.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Messaggistica istantanea e presenza in Lync Server 2013](lync-server-2013-im-and-presence.md)

  - [Servizi di conferenza in Lync Server 2013](lync-server-2013-conferencing.md)

  - [VoIP aziendale in Lync Server 2013](lync-server-2013-enterprise-voice.md)

  - [Scalabilità con Lync Server 2013](lync-server-2013-scalability.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

