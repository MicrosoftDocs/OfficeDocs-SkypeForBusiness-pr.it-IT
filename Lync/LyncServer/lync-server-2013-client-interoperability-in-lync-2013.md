---
title: 'Lync Server 2013: Interoperabilità dei client in Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f8ccc6239ffa0216e36839a7e58b510d8c8c3240
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40976598"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-interoperability-in-lync-2013"></a>Interoperabilità dei client in Lync 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2016-03-04_

Questo argomento illustra la capacità dei client di Microsoft Lync Server 2013 di coesistere e interagire con i client di versioni precedenti di Lync Server e Office Communications Server.

<div>

## <a name="server-and-client-compatibility"></a>Compatibilità di server e client

La tabella seguente mostra le combinazioni supportate delle versioni client e delle versioni del server. Questa tabella indica se l'accesso è supportato quando il client tenta di connettersi al server indicato. Lync Server 2013 supporta la versione precedente del client. Inoltre, a differenza delle versioni precedenti, Lync Server 2010 supporta i nuovi client Lync 2013. Ciò consente alle organizzazioni che eseguono l'aggiornamento da Lync Server 2010 di implementare nuovi client indipendentemente dagli aggiornamenti di Lync Server.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Supportati</p></td>
<td><p>Supported5</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Supportati</p></td>
<td><p>Supportati</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2013</p></td>
<td><p>Supportati</p></td>
<td><p>Non supportato</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Supportati</p></td>
<td><p>Supportati</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="odd">
<td><p>Assistente di Lync 2010</p></td>
<td><p>Supportati</p></td>
<td><p>Supportati</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="even">
<td><p>Chat di gruppo di Lync 2010</p></td>
<td><p>Supported1</p></td>
<td><p>Supported2</p></td>
<td><p>Non applicabile</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2010</p></td>
<td><p>Non supportato</p></td>
<td><p>Supportati</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="even">
<td><p>Partecipante Lync 2010</p></td>
<td><p>Non Supported3</p></td>
<td><p>Supportati</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable4</p></td>
<td><p>Supportati</p></td>
<td><p>Supportati</p></td>
</tr>
<tr class="even">
<td><p>Assistente di Microsoft Office Communications Server 2007 R2</p></td>
<td><p>Non supportato</p></td>
<td><p>Supportati</p></td>
<td><p>Supportati</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007</p></td>
<td><p>Non supportato</p></td>
<td><p>Supportati</p></td>
<td><p>Supportati</p></td>
</tr>
<tr class="even">
<td><p>Office Live Meeting 2007</p></td>
<td><p>Non supportato</p></td>
<td><p>Supportati</p></td>
<td><p>Supportati</p></td>
</tr>
<tr class="odd">
<td><p>App Lync di Windows Store</p></td>
<td><p>Supportati</p></td>
<td><p>Supportati</p></td>
<td><p>Non supportato</p></td>
</tr>
</tbody>
</table>


1Per dettagli, vedere [migrazione da Lync server 2010, Group Chat o Office Communications server 2007 R2 Group Chat in Lync server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

2In Microsoft Lync Server 2010, la funzionalità Group Chat era disponibile con Group Chat Server, un'applicazione attendibile di terze parti per Lync Server 2010. I client Lync 2013 non sono compatibili con Lync Server 2010, chat di gruppo.

3Lync Web App 2013 ora offre un'esperienza di riunione completa, inclusi l'audio e il video del computer, ed è considerata la sostituzione per il partecipante di Lync 2010. Lync 2010 partecipante si connette a Lync Server 2013 solo quando si usa un browser non supportato (Internet Explorer 6 o Internet Explorer 7) e Windows XP.

le funzionalità di presenza e messaggistica istantanea di 4Il in Office Communicator 2007 R2 sono compatibili con Lync Server 2013, ma le funzionalità di conferenza non lo sono. Durante la migrazione da Office Communications Server 2007 R2, Office Communicator 2007 R2 è adatto per l'interoperabilità in presenza e messaggistica istantanea, ma gli utenti devono usare Lync Web App 2013 per partecipare alle riunioni di Lync Server 2013.

5 per le limitazioni, vedere "supporto delle funzionalità di conferenza per i client Lync 2013 nelle riunioni di Lync Server 2010" più avanti in questo argomento.

</div>

<div>

## <a name="interoperability-among-clients"></a>Interoperabilità tra i clienti

Con la versione di Lync Server 2013, diverse versioni client possono interagire in modo uniforme in scenari peer-to-peer e conferenze. Questa sezione illustra la disponibilità delle caratteristiche quando gli utenti interagiscono con altri utenti che usano versioni diverse di client e server.

<div>

## <a name="peer-to-peer-feature-support"></a>Supporto delle funzionalità peer-to-peer

Le funzionalità peer-to-peer sono supportate per gli utenti residenti in versioni diverse del server e che usano versioni client diverse. L'esperienza utente finale e le funzionalità disponibili sono coerenti con le funzionalità del client dell'utente e la versione del server a cui l'utente ha eseguito l'accesso. In altre parole:

  - Se un utente ha eseguito l'accesso a Lync Server 2013 con un client precedente, l'utente avrà la stessa esperienza a cui viene usato. Nessuna delle nuove funzionalità introdotte in Lync Server 2013 sarà disponibile finché il client dell'utente non viene aggiornato. Gli esempi includono la visualizzazione raccolta video, il video HD, la condivisione aggiornata di PowerPoint e l'opzione per disattivare l'audio e il video di tutti i partecipanti alla voce della riunione. Le nuove caratteristiche sono descritte in [nuove caratteristiche di conferenza in Lync server 2013](lync-server-2013-new-conferencing-features.md) e [novità per i client in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

  - Se un utente ha eseguito l'accesso a Lync Server 2010 con un client Lync 2013, tutte le nuove funzionalità non supportate da Lync Server 2010 non saranno disponibili finché l'utente non viene spostato in Lync Server 2013.

Nella tabella seguente viene confrontata la disponibilità delle caratteristiche nelle sessioni peer-to-peer in cui il client ha eseguito l'accesso a Lync Server 2013 o Lync Server 2010.

<div>


> [!NOTE]  
> Lync Web App e Lync 2010 partecipanti sono client solo per riunioni e non sono inclusi in questa tabella.



</div>


<table style="width:100%;">
<colgroup>
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
<col style="width: 14%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Messaggistica istantanea</th>
<th>Icone di presenza</th>
<th>Segreteria telefonica</th>
<th>Video</th>
<th>Condivisione applicazioni</th>
<th>Trasferimento di file</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
</tr>
<tr class="even">
<td><p>Assistente di Lync 2010</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 per dispositivi mobili</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì1</p></td>
<td><p>Sì</p></td>
</tr>
<tr class="even">
<td><p>Messaggistica istantanea pubblica (AOL, Yahoo!)</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Messaggistica istantanea pubblica (MSN, Windows Live Messenger)</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


<div>


> [!IMPORTANT]  
> <UL>
> <LI>
> <P>A partire dal 1 ° settembre 2012, la licenza di abbonamento a Microsoft Lync Public IM Connectivity User (PIC USL) non è più disponibile per l'acquisto di contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di chiusura del servizio. Data di fine vita del 2014 giugno per AOL e Yahoo! è stato annunciato. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.</P>
> <LI>
> <P>Il PIC USL è una licenza per abbonamento per utente, per mese necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo! Messenger. La capacità di Microsoft di prestare questo servizio è stata subordinata al supporto da Yahoo!, l'accordo sottostante per il quale non verrà rinnovato.</P>
> <LI>
> <P>Più che mai, Lync è uno strumento efficace per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone tramite messaggistica istantanea e voce.</P></LI></UL>



</div>

1 in Office Communicator 2007 R2 è disponibile solo la condivisione desktop (e non la condivisione di programmi).

<div>


> [!NOTE]  
> La condivisione desktop tra Office Communicator 2007 R2 e Skype for business 2015 non può essere avviata dal client più recente quando viene applicata l'interfaccia utente del client Skype for business 2015.



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a>Supporto delle funzionalità di conferenza per i client Lync 2013 nelle riunioni di Lync Server 2010

Quando gli utenti partecipano alle riunioni di Lync Server 2010 con un client Lync 2013, hanno accesso alle funzionalità client di Lync 2013 con le eccezioni seguenti:

  - Nelle opzioni di gestione dei **partecipanti** , che sono accessibili puntando l'icona persone nella finestra della riunione, l'opzione **Nessuna messaggistica istantanea** non funziona.

  - La visualizzazione raccolta non funziona nelle conferenze video. L'utente vede solo l'altoparlante attivo invece di tutti gli altoparlanti. Nell'elenco delle opzioni **Scegli un layout** la **visualizzazione raccolta** non è disponibile

  - L'elenco dei partecipanti viene visualizzato per impostazione predefinita nelle videoconferenze.

  - Quando si fa clic con il pulsante destro del mouse su un utente nell'elenco dei partecipanti, le opzioni **di** gestione del **riflettore e del PIN delle** raccolte sono non disponibili.

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a>Supporto delle funzionalità di conferenza nelle riunioni di Lync Server 2013

Lync Server 2013 offre nuove caratteristiche di conferenza che diventano disponibili agli utenti dopo lo spostamento degli account in Lync Server 2013 e l'accesso con il client Lync 2013. Gli esempi includono la visualizzazione raccolta video, il video HD, la condivisione di PowerPoint e l'opzione per disattivare l'audio e il video di tutti i partecipanti alla voce di riunione. Le nuove caratteristiche sono descritte in [nuove caratteristiche di conferenza in Lync server 2013](lync-server-2013-new-conferencing-features.md) e [novità per i client in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

Nelle riunioni di Lync Server 2013 sono supportate alcune funzionalità di conferenza per gli utenti residenti in versioni diverse del server e che usano client e versioni client diversi. Quando i client partecipano a una riunione di Lync Server 2013, gli utenti hanno accesso alle funzionalità e alle funzionalità visualizzate in questa tabella.


<table style="width:100%;">
<colgroup>
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
<col style="width: 11%" />
</colgroup>
<thead>
<tr class="header">
<th>Client</th>
<th>Messaggistica istantanea peer-to-peer</th>
<th>Segreteria telefonica</th>
<th>Video</th>
<th>Condivisione applicazioni</th>
<th>PowerPoint</th>
<th>Trasferimento di file</th>
<th>Whiteboard</th>
<th>Polling</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì2</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Yes3</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2 4</p></td>
<td><p>Sì</p></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
<td></td>
</tr>
</tbody>
</table>


1 in Office Communicator 2007 R2 è disponibile solo la condivisione desktop (e non la condivisione di programmi).

2 Lync Server 2013 usa un meccanismo aggiornato per il caricamento di file di PowerPoint. Gli utenti di Lync Web App che partecipano a una riunione originariamente pianificata in Lync Server 2010 possono visualizzare ed esplorare le presentazioni di PowerPoint, ma non possono caricare i file di PowerPoint.

3 Se la riunione è stata pianificata in Lync Server 2013 e le diapositive di PowerPoint sono state caricate da un client Lync 2013, gli utenti di Lync 2010 hanno accesso solo alle diapositive. Viceversa, se le diapositive di PowerPoint sono state caricate da un utente di Lync 2010, gli utenti di Lync Server 2013 saranno in grado di visualizzare e diapositive e, se è configurato il server Office Web Apps, accedere a nuove funzionalità come la visualizzazione a risoluzione superiore, le animazioni, le transizioni delle diapositive e video incorporato. Per altre informazioni, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

le funzionalità di presenza e messaggistica istantanea di 4Il in Office Communicator 2007 R2 sono compatibili con Lync Server 2013, ma le funzionalità di conferenza non lo sono. Durante la migrazione da Office Communications Server 2007 R2, Office Communicator 2007 R2 è adatto per l'interoperabilità in presenza e messaggistica istantanea, ma gli utenti devono usare Lync Web App 2013 per partecipare alle riunioni di Lync Server 2013.

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a>Supporto per la pianificazione del componente aggiuntivo

Il supporto del server per i diversi componenti aggiuntivi per la pianificazione è coerente con la compatibilità del server e della versione client. In generale, i componenti aggiuntivi per la pianificazione seguenti sono supportati in Lync Server 2013. Le versioni precedenti dei componenti aggiuntivi, tuttavia, non includono nuove funzionalità del componente aggiuntivo Lync 2013, ad esempio l'opzione per disattivare l'audio e il video di tutti i partecipanti alla voce della riunione.

  - **Il componente aggiuntivo riunione online per Lync 2013**   offre le stesse caratteristiche del componente aggiuntivo riunione online per Lync 2010, con l'aggiunta di controlli di silenziamento dei partecipanti, che consentono agli organizzatori della riunione di pianificare le conferenze che hanno l'audio e il video del partecipante per impostazione predefinita. Gli amministratori possono anche personalizzare gli inviti alle riunioni dell'organizzazione aggiungendo un logo personalizzato, un URL di supporto, un URL di dichiarazione di non responsabilità legale o un testo del piè di pagina personalizzato.

  - **Il componente aggiuntivo riunione online per Lync 2010**   offre la pianificazione per le riunioni di Lync e rimuove la possibilità di pianificare le conferenze di Office Live Meeting.

  - **Il componente aggiuntivo per conferenze di Office Communicator 2007 R2**   offre la pianificazione sia per le conferenze di Office Live Meeting che per le conferenze di Office Communicator 2007 R2. 

<div>


> [!NOTE]  
> Le conferenze di Live Meeting non possono essere pianificate in Lync Server 2013.



</div>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Client di pianificazione</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Componente aggiuntivo riunione online per Lync 2013 (può essere usato con Office 2013, Outlook 2010 e Outlook 2007)</p></td>
<td><p>Supportati</p></td>
<td><p>Supportato (le nuove funzionalità del componente aggiuntivo non sono disponibili)</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="even">
<td><p>Utilità di pianificazione Web Lync 2013</p></td>
<td><p>Supportati</p></td>
<td><p>Non supportato</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="odd">
<td><p>Componente aggiuntivo riunione online per Lync 2010</p></td>
<td><p>Supportati</p></td>
<td><p>Supportati</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="even">
<td><p>Componente aggiuntivo per conferenze di Office Communicator 2007 R2</p></td>
<td><p>Non supportato</p></td>
<td><p>Supportati</p></td>
<td><p>Supportati</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a>Supporto per partecipare alle riunioni

Tutti i client supportati da Lync Server 2013 possono partecipare alle riunioni di Lync 2013. Poiché Lync Web App è un componente Web del server, nei casi in cui Lync Web App viene usato per partecipare a una riunione di Lync Server 2013, viene sempre usata la versione più recente di Lync Web App.

I client Lync 2013 possono partecipare a riunioni ospitate in Lync 2010 e Office Communications Server 2007 R2 con funzionalità in scala ridotta. Le caratteristiche di riunione sono limitate dalla versione del server in cui è ospitata la riunione.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Requisiti dell'app Lync di Windows Store per Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md)  
[Nuove funzionalità di conferenza in Lync Server 2013](lync-server-2013-new-conferencing-features.md)  
[Novità per i client in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

