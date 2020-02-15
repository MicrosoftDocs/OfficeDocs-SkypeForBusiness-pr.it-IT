---
title: Introduzione a Lync Server 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Introduction to Lync Server
ms:assetid: 99dd6b65-e591-421f-852b-ee9fe9588998
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398795(v=OCS.15)
ms:contentKeyID: 48184885
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8b0b6868486f9486758d2a346dd62339d98ed1e7
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42046159"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="introduction-to-lync-server-2013"></a>Introduzione a Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-10-07_

Lync Server 2013 e il relativo software client, ad esempio Lync 2013, consentono agli utenti di connettersi in modo nuovo e di rimanere connessi, indipendentemente dalla posizione fisica. Lync e Lync Server riuniscono i diversi modi in cui gli utenti comunicano in una singola interfaccia client, vengono distribuiti come piattaforma unificata e vengono amministrati tramite un'unica infrastruttura di gestione.

In questa tabella e nelle sezioni seguenti vengono illustrati i principali set di caratteristiche, o *carichi di lavoro*, che Lync Server fornisce per gli utenti.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Carico di lavoro</th>
<th>Descrizione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Messaggistica istantanea e presenza</p></td>
<td><p>Messaggistica istantanea (IM) e presenza consentono agli utenti di trovarsi e comunicare tra loro in modo efficace ed efficiente.</p>
<p>La messaggistica istantanea fornisce una piattaforma IM con cronologia delle conversazioni e supporta la connettività di messaggistica istantanea pubblica con gli utenti di reti come MSN/Windows Live, Yahoo!, AOL e Google Talk.</p>
<div>

> [!IMPORTANT]  
> <UL>
> <LI>
> <P>Al 1 ° settembre 2012, la licenza di sottoscrizione di Microsoft Lync Public IM Connectivity ("PIC USL") non è più disponibile per l'acquisto dei contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di arresto del servizio. Una data di fine vita del 2014 giugno per AOL e Yahoo! sono stati annunciati. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
> <LI>
> <P>Il PIC USL è una licenza per ogni utente per ogni mese che è necessaria per Lync Server o Office Communications Server per la Federazione con Yahoo! Messaggero. La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale si sta liquidando.</P>
> <LI>
> <P>Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone con messaggistica istantanea e vocale.</P></LI></UL>


</div>
<p>La presenza determina e visualizza la disponibilità personale di un utente e la sua volontà di comunicare, mediante l'utilizzo di stati comuni quali <strong>Disponibile</strong> o <strong>Occupato</strong> nonché con stati più dettagliati quali <strong>Torno subito</strong> e <strong>Non disturbare</strong>. Queste informazioni sulla presenza avanzata consentono agli altri utenti di utilizzare immediatamente scelte di comunicazione efficienti.</p></td>
</tr>
<tr class="even">
<td><p>Conferenza</p></td>
<td><p>Lync Server include il supporto per le conferenze di messaggistica istantanea, audioconferenza, Web Conferencing, video Conferencing e condivisione applicazioni, sia per le riunioni pianificate che per quelle estemporanee. Tutti questi tipi di riunione sono supportati mediante un unico client. Lync Server supporta anche le conferenze telefoniche con accesso esterno in modo che gli utenti del telefono PSTN (Public Switched Telephone Network) possano partecipare alla parte audio delle conferenze.</p>
<p>Le conferenze possono cambiare e crescere in tempo reale senza problemi. Ad esempio, una singola conferenza può iniziare come un semplice scambio di messaggi istantanei tra pochi utenti e trasformarsi in una conferenza audio con condivisione del desktop e con un pubblico più vasto istantaneamente, facilmente e senza interrompere il flusso di conversazione.</p></td>
</tr>
<tr class="odd">
<td><p>VoIP aziendale</p></td>
<td><p>VoIP <em>aziendale</em> è la voce che offre il protocollo Voice over Internet Protocol in Lync Server. Offre un'opzione vocale per migliorare o sostituire i sistemi PBX (Private Branch Exchange) tradizionali. Oltre alle funzionalità di telefonia complete di un sistema IP PBX, VoIP aziendale è integrato con presenza avanzata, messaggistica istantanea, collaborazione e riunioni. Sono supportate direttamente funzionalità quali la risposta alla chiamata, il blocco, il riassunto, il trasferimento, l'inoltro e la deviazione, mentre i tasti di composizione rapida personalizzati vengono sostituiti da elenchi di contatti e il citofono automatico viene sostituito con messaggistica istantanea.</p>
<p>VoIP aziendale supporta la disponibilità elevata mediante controllo di ammissione di chiamata (CAC), branch office survivability e opzioni estese per la resilienza dei dati.</p></td>
</tr>
<tr class="even">
<td><p>Supporto per gli utenti remoti</p></td>
<td><p>È possibile fornire funzionalità complete di Lync Server per gli utenti che si trovano al di fuori dei firewall dell'organizzazione distribuendo server denominati <em>server perimetrali</em> per fornire una connessione a questi utenti remoti. Questi utenti remoti possono connettersi a conferenze utilizzando un personal computer con Lync 2013 installato, il telefono o un'interfaccia Web.</p>
<p>La distribuzione dei server perimetrali consente inoltre di attuare la <em>federazione</em> con altre organizzazioni, ad esempio partner o fornitori. Una relazione federata consente agli utenti di inserire gli utenti federati nei propri elenchi di contatti, scambiare con essi informazioni sulla presenza e messaggi istantanei e invitarli a chiamate audio, chiamate video e conferenze.</p></td>
</tr>
<tr class="odd">
<td><p>Supporto di client mobili</p></td>
<td><p>Inoltre, con i servizi per dispositivi mobili di Lync Server, gli utenti possono accedere alle funzionalità di Lync quando utilizzano i sistemi Apple iOS, Android, Windows Phone o Nokia e eseguono tali attività come l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti, e la presenza di visualizzazione. Inoltre, i dispositivi mobili supportano alcune funzionalità di VoIP aziendale, quali l'accesso con un clic alle conferenze, la chiamata tramite ufficio, il numero unico, la segreteria telefonica e le chiamate senza risposta. Le notifiche push sono inoltre supportate per i dispositivi mobili che non supportano applicazioni in esecuzione in background.</p></td>
</tr>
<tr class="even">
<td><p>Integrazione con altri prodotti</p></td>
<td><p>Lync Server si integra con numerosi altri prodotti per offrire vantaggi aggiuntivi agli utenti e agli amministratori.</p>
<p>Gli strumenti per riunioni sono integrati in Outlook per consentire agli organizzatori di pianificare una riunione o avviare una conferenza improvvisata con un solo clic e renderla altrettanto semplice per i partecipanti.</p>
<p>Le informazioni sulla presenza sono integrate in Outlook e SharePoint.</p>
<p>La messaggistica unificata di Exchange offre numerose funzionalità di integrazione. Gli utenti possono vedere se dispongono di una nuova segreteria telefonica all'interno di Lync Server. Possono fare clic su un pulsante di riproduzione nel messaggio di Outlook per ascoltare l'audio del messaggio, oppure visualizzarne una trascrizione nel messaggio di notifica.</p>
<p>Inoltre, l'esecuzione di Lync Server 2013 con Exchange 2013 consente di abilitare diverse nuove funzionalità, ad esempio un archivio contatti unificato, che può essere eseguito dai client di entrambi i prodotti, nonché foto ad alta risoluzione per i contatti archiviati nel database di Exchange 2013.</p></td>
</tr>
<tr class="odd">
<td><p>Distribuzione semplice</p></td>
<td><p>Per semplificare la pianificazione e la distribuzione di server e client, Lync Server fornisce il generatore di topologie.</p>
<p>Generatore di topologie è un componente di installazione di Lync Server. Per creare, modificare e pubblicare la topologia pianificata, è possibile utilizzare Generatore di topologie. Convalida inoltre la topologia prima di iniziare le installazioni del server. Quando si installa Lync Server nei singoli server, il programma di installazione distribuisce il server come indicato nella topologia.</p></td>
</tr>
<tr class="even">
<td><p>Gestione semplice</p></td>
<td><p>Dopo la distribuzione di Lync Server, sono disponibili i seguenti strumenti di gestione efficienti e potenti:</p>
<ul>
<li><p>La gestione centrale della configurazione che consente di gestire le modifiche in modo centralizzato e di replicarle rapidamente nell'intera distribuzione.</p></li>
<li><p>Pannello di controllo di Lync Server, un'interfaccia utente grafica basata sul Web per gli amministratori. Con questa interfaccia utente basata sul Web, gli amministratori di Lync Server possono gestire i propri sistemi da qualsiasi punto della rete aziendale, senza dover installare il software di gestione specializzato nei propri computer.</p></li>
<li><p>Strumento di gestione della riga di comando di Lync Server Management Shell, basato sull'interfaccia della riga di comando di Windows PowerShell. Fornisce un set di comandi RTF per l'amministrazione di tutti gli aspetti del prodotto e consente agli amministratori di Lync Server di automatizzare le attività ripetitive utilizzando uno strumento familiare.</p></li>
</ul></td>
</tr>
</tbody>
</table>


Anche se le funzionalità di messaggistica istantanea e presenza vengono installate automaticamente in ogni distribuzione di Lync Server, è possibile scegliere se distribuire servizi di conferenza, VoIP aziendale e accesso utente remoto per adattare la distribuzione alle esigenze dell'organizzazione.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

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

