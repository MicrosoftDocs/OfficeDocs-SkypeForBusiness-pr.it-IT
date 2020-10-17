---
title: 'Lync Server 2013: interoperabilità client in Lync 2013'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client interoperability in Lync 2013
ms:assetid: 0f126571-91a2-45d5-855c-1e4ddb45fc04
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204672(v=OCS.15)
ms:contentKeyID: 48183417
ms.date: 03/04/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2e00071edd4a3d65e9db763914577983306491fc
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48502673"
---
# <a name="client-interoperability-in-lync-2013"></a>Interoperabilità client in Lync 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2016-03-04_

In questo argomento viene illustrata la possibilità per i client Microsoft Lync Server 2013 di coesistere e interagire con client provenienti da versioni precedenti di Lync Server e Office Communications Server.

<div>

## <a name="server-and-client-compatibility"></a>Compatibilità di server e client

Nella tabella seguente sono mostrate le combinazioni supportate di versioni client e server. Viene indicato se è supportato l'accesso quando il client tenta di connettersi al server indicato. Lync Server 2013 supporta la versione client precedente. Inoltre, a differenza delle versioni precedenti, Lync Server 2010 supporta i nuovi client Lync 2013. In questo modo, le organizzazioni che eseguono l'aggiornamento da Lync Server 2010 possono implementare nuovi client indipendenti dagli aggiornamenti di Lync Server.


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
<td><p>Supportato</p></td>
<td><p>Supported5</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="even">
<td><p>Lync 2013 Basic</p></td>
<td><p>Supportato</p></td>
<td><p>Supportato</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2013</p></td>
<td><p>Supportato</p></td>
<td><p>Non supportato</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>Supportato</p></td>
<td><p>Supportato</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendant</p></td>
<td><p>Supportato</p></td>
<td><p>Supportato</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="even">
<td><p>Chat di gruppo Lync 2010</p></td>
<td><p>Supported1</p></td>
<td><p>Supported2</p></td>
<td><p>Non applicabile</p></td>
</tr>
<tr class="odd">
<td><p>Lync Web App 2010</p></td>
<td><p>Non supportato</p></td>
<td><p>Supportato</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendee</p></td>
<td><p>Non Supported3</p></td>
<td><p>Supportato</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable4</p></td>
<td><p>Supportato</p></td>
<td><p>Supportato</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
<td><p>Non supportato</p></td>
<td><p>Supportato</p></td>
<td><p>Supportato</p></td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007</p></td>
<td><p>Non supportato</p></td>
<td><p>Supportato</p></td>
<td><p>Supportato</p></td>
</tr>
<tr class="even">
<td><p>Office Live Meeting 2007</p></td>
<td><p>Non supportato</p></td>
<td><p>Supportato</p></td>
<td><p>Supportato</p></td>
</tr>
<tr class="odd">
<td><p>App Lync Windows Store</p></td>
<td><p>Supportato</p></td>
<td><p>Supportato</p></td>
<td><p>Non supportato</p></td>
</tr>
</tbody>
</table>


per informazioni dettagliate su 1per, vedere [Migration from Lync server 2010, Group Chat o Office Communications Server 2007 R2 Group Chat to Lync server 2013, Persistent Chat Server](migration-from-lync-server-2010-group-chat-or-office-communications-server-2007-r2-group-chat-to-lync-server-2013-persistent-chat-server.md).

2In Microsoft Lync Server 2010, la funzionalità Group Chat era disponibile con Group Chat Server, un'applicazione attendibile di terze parti per Lync Server 2010. I client Lync 2013 non sono compatibili con Lync Server 2010, Group Chat.

3Lync Web App 2013 ora offre un'esperienza di riunione completa, tra cui audio e video del computer, ed è considerata la sostituzione di Lync 2010 Attendee. Lync 2010 Attendee si connetterà a Lync Server 2013 solo quando si utilizza un browser non supportato (Internet Explorer 6 o Internet Explorer 7) e Windows XP.

le funzionalità di presenza e messaggistica istantanea di 4Il in Office Communicator 2007 R2 sono compatibili con Lync Server 2013, ma non le funzionalità di conferenza. Durante la migrazione da Office Communications Server 2007 R2, Office Communicator 2007 R2 è idoneo per l'interoperabilità della messaggistica istantanea e della presenza, ma gli utenti devono utilizzare Lync Web App 2013 per partecipare alle riunioni di Lync Server 2013.

5 per le limitazioni, vedere "supporto delle funzionalità di conferenza per i client di Lync 2013 nelle riunioni di Lync Server 2010" più avanti in questo argomento.

</div>

<div>

## <a name="interoperability-among-clients"></a>Interoperabilità tra client

Con la versione Lync Server 2013, diverse versioni client possono interagire senza problemi in entrambi gli scenari peer-to-peer e di conferenza. In questa sezione vengono illustrate le funzionalità disponibili quando gli utenti interagiscono con altri utenti che utilizzano versioni diverse dei client e server.

<div>

## <a name="peer-to-peer-feature-support"></a>Supporto della funzionalità peer-to-peer

Le funzionalità peer-to-peer sono supportate per gli utenti ospitati su diverse versioni del server e che utilizzano diverse versioni client. L'esperienza dell'utente finale e le caratteristiche disponibili sono in linea con le funzionalità del client dell'utente e con la versione del server a cui l'utente ha eseguito l'accesso. In altri termini:

  - Se un utente ha eseguito l'accesso a Lync Server 2013 con un client precedente, l'utente avrà la stessa esperienza a cui viene utilizzato. Nessuna delle nuove funzionalità introdotte in Lync Server 2013 sarà disponibile finché il client dell'utente non viene aggiornato. Gli esempi includono la visualizzazione raccolta video, video HD, la condivisione di PowerPoint aggiornata e l'opzione per disattivare l'audio e il video di tutti i partecipanti dopo la voce di riunione. Le nuove funzionalità sono descritte in [nuove funzionalità di conferenza in Lync server 2013](lync-server-2013-new-conferencing-features.md) e [novità per i client in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

  - Se un utente ha eseguito l'accesso a Lync Server 2010 con un client Lync 2013, tutte le nuove funzionalità non supportate da Lync Server 2010 non saranno disponibili fino a quando l'utente non verrà spostato in Lync Server 2013.

Nella tabella seguente vengono confrontate le funzionalità disponibili nelle sessioni peer-to-peer in cui il client ha eseguito l'accesso a Lync Server 2013 o Lync Server 2010.

<div>


> [!NOTE]  
> Lync Web App e Lync 2010 Attendee sono client solo per riunioni e non sono inclusi in questa tabella.



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
<th>Presenza</th>
<th>Voce</th>
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
<td><p>Lync 2010 Attendant</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td><p>Sì</p></td>
<td></td>
<td></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Mobile</p></td>
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
<td><p>Yes1</p></td>
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
> <P>Al 1 ° settembre 2012, la licenza di sottoscrizione a Microsoft Lync Public IM Connectivity (PIC USL) non è più disponibile per l'acquisto dei contratti nuovi o rinnovati. I clienti con licenze attive saranno in grado di continuare a eseguire la Federazione con Yahoo! Messenger fino alla data di arresto del servizio. Una data di fine vita del 2014 giugno per AOL e Yahoo! sono stati annunciati. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>..</P>
> <LI>
> <P>Il PIC USL è una licenza di sottoscrizione per utente, per mese, necessaria per la Federazione di Lync Server o Office Communications Server con Yahoo! Messaggero. La capacità di Microsoft di fornire questo servizio è stata subordinata al supporto da Yahoo!, ovvero il contratto sottostante per il quale non verrà rinnovato.</P>
> <LI>
> <P>Più che mai, Lync è uno strumento potente per la connessione tra le organizzazioni e gli utenti di tutto il mondo. La Federazione con Windows Live Messenger non richiede licenze aggiuntive per utenti e dispositivi oltre la licenza CAL standard di Lync. La Federazione Skype verrà aggiunta a questo elenco, consentendo agli utenti di Lync di raggiungere centinaia di milioni di persone attraverso la messaggistica istantanea e la voce.</P></LI></UL>



</div>

1 in Office Communicator 2007 R2, è disponibile solo la condivisione del desktop (e non la condivisione dei programmi).

<div>


> [!NOTE]  
> La condivisione desktop tra Office Communicator 2007 R2 e Skype for business 2015 non può essere avviata dal client più recente quando viene applicata l'interfaccia utente del client Skype for business 2015.



</div>

</div>

<div>

## <a name="conferencing-feature-support-for-lync-2013-clients-in-lync-server-2010-meetings"></a>Supporto delle funzionalità di conferenza per i client di Lync 2013 nelle riunioni di Lync Server 2010

Quando gli utenti accedono alle riunioni di Lync Server 2010 con un client Lync 2013, possono accedere alle funzionalità client di Lync 2013 con le eccezioni seguenti:

  - Nelle opzioni di gestione dei **partecipanti** , che sono accessibili facendo riferimento all'icona persone nella finestra riunione, l'opzione **Nessuna riunione di messaggistica istantanea** non funziona.

  - La visualizzazione raccolta non funziona nelle conferenze video. L'utente visualizza solo l'altoparlante attivo invece di tutti gli altoparlanti. Nell'elenco delle opzioni **Seleziona un layout** , la **visualizzazione raccolta** non è disponibile

  - L'elenco dei partecipanti viene visualizzato per impostazione predefinita nelle conferenze video.

  - Quando si fa clic con il pulsante destro del mouse su un utente nell'elenco partecipanti, le opzioni di gestione del **blocco video e del** **pin per la raccolta** non sono disponibili.

</div>

<div>

## <a name="conferencing-feature-support-in-lync-server-2013-meetings"></a>Supporto delle funzionalità di conferenza nelle riunioni di Lync Server 2013

Lync Server 2013 fornisce nuove funzionalità di conferenza che diventano disponibili per gli utenti dopo lo spostamento degli account in Lync Server 2013 ed eseguono l'accesso con il client Lync 2013. Gli esempi includono la visualizzazione della raccolta video, il video HD, la condivisione di PowerPoint e l'opzione per disattivare l'audio e il video dei partecipanti dopo la voce di riunione. Le nuove funzionalità sono descritte in [nuove funzionalità di conferenza in Lync server 2013](lync-server-2013-new-conferencing-features.md) e [novità per i client in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md).

Nelle riunioni di Lync Server 2013, alcune funzionalità di conferenza sono supportate per gli utenti che si trovano in diverse versioni del server e che utilizzano client e versioni client diversi. Quando i client partecipano a una riunione di Lync Server 2013, gli utenti possono accedere alle caratteristiche e alle funzionalità illustrate in questa tabella.


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
<th>Voce</th>
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


1 in Office Communicator 2007 R2, è disponibile solo la condivisione del desktop (e non la condivisione dei programmi).

2 Lync Server 2013 utilizza un meccanismo aggiornato per il caricamento dei file di PowerPoint. Gli utenti di Lync Web App che partecipano a una riunione originariamente pianificata su Lync Server 2010 possono visualizzare e esplorare le presentazioni di PowerPoint, ma non possono caricare i file di PowerPoint.

3 Se la riunione è stata pianificata su Lync Server 2013 e le diapositive di PowerPoint sono state caricate da un client Lync 2013, gli utenti di Lync 2010 dispongono dell'accesso in sola visualizzazione alle diapositive. Viceversa, se le diapositive di PowerPoint sono state caricate da un utente Lync 2010, gli utenti di Lync Server 2013 saranno in grado di visualizzare e diapositive e, se il server Office Web Apps è configurato, accedere a nuove funzionalità come la visualizzazione a risoluzione più elevata, le animazioni, le transizioni di diapositive e i video incorporati. Per ulteriori informazioni, vedere [configurazione dell'integrazione con Office Web Apps Server e Lync server 2013](lync-server-2013-enabling-office-web-apps-server-and-lync-server-2013.md).

le funzionalità di presenza e messaggistica istantanea di 4Il in Office Communicator 2007 R2 sono compatibili con Lync Server 2013, ma non le funzionalità di conferenza. Durante la migrazione da Office Communications Server 2007 R2, Office Communicator 2007 R2 è idoneo per l'interoperabilità della messaggistica istantanea e della presenza, ma gli utenti devono utilizzare Lync Web App 2013 per partecipare alle riunioni di Lync Server 2013.

</div>

</div>

<div>

## <a name="scheduling-add-in-support"></a>Supporto dei componenti aggiuntivi di pianificazione

Il supporto server per i vari componenti aggiuntivi di pianificazione è coerente con la compatibilità tra le versioni server e client. In generale, i componenti aggiuntivi di pianificazione seguenti sono supportati in Lync Server 2013. Tuttavia, le versioni precedenti dei componenti aggiuntivi non forniscono nuove funzionalità del componente aggiuntivo Lync 2013, ad esempio l'opzione per disattivare l'audio e il video dei partecipanti dopo la voce di riunione.

  - **Componente aggiuntivo per riunioni online per Lync 2013**     Sono disponibili le stesse caratteristiche del componente aggiuntivo per riunioni online per Lync 2010, con l'aggiunta di controlli di silenziamento dei partecipanti, che consentono agli organizzatori di riunioni di pianificare le conferenze in cui sono presenti audio e video per impostazione predefinita. Gli amministratori possono anche personalizzare gli inviti alle riunioni dell'organizzazione aggiungendo un logo personalizzato, un URL di supporto, un URL di dichiarazione di non responsabilità legale o un testo del piè di pagina personalizzato.

  - **Componente aggiuntivo per riunioni online per Lync 2010**     Fornisce la pianificazione per le riunioni di Lync e rimuove la possibilità di pianificare le conferenze di Office Live Meeting.

  - **Componente aggiuntivo per conferenze di**     Office Communicator 2007 R2 Fornisce la pianificazione per le conferenze di Office Live Meeting e Office Communicator 2007 R2. 

<div>


> [!NOTE]  
> Le conferenze di Live Meeting non possono essere pianificate su Lync Server 2013.



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
<td><p>Componente aggiuntivo per riunioni online per Lync 2013 (può essere utilizzato con Office 2013, Outlook 2010 e Outlook 2007)</p></td>
<td><p>Supportato</p></td>
<td><p>Supportato (nuove caratteristiche dei componenti aggiuntivi non disponibili)</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="even">
<td><p>Utilità di pianificazione Web di Lync 2013</p></td>
<td><p>Supportato</p></td>
<td><p>Non supportato</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="odd">
<td><p>Online Meeting Add-in per Lync 2010</p></td>
<td><p>Supportato</p></td>
<td><p>Supportato</p></td>
<td><p>Non supportato</p></td>
</tr>
<tr class="even">
<td><p>Componente aggiuntivo per conferenze per Office Communicator 2007 R2</p></td>
<td><p>Non supportato</p></td>
<td><p>Supportato</p></td>
<td><p>Supportato</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="support-for-joining-meetings"></a>Supporto della partecipazione a riunioni

Tutti i client supportati da Lync Server 2013 sono autorizzati a partecipare alle riunioni di Lync 2013. Poiché Lync Web App è un componente Web del server, nei casi in cui viene utilizzata Lync Web App per partecipare a una riunione di Lync Server 2013, viene sempre utilizzata la versione più recente di Lync Web App.

I client Lync 2013 possono partecipare alle riunioni ospitate in Lync 2010 e Office Communications Server 2007 R2 con funzionalità con scalabilità orizzontale. Le funzionalità per le riunioni sono limitate dalla versione del server in cui è ospitata la riunione.

</div>

<div>

## <a name="see-also"></a>Vedere anche


[Requisiti delle app di Windows Store di Lync per Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md)  
[Nuove funzionalità di conferenza in Lync Server 2013](lync-server-2013-new-conferencing-features.md)  
[Novità per i client in Lync Server 2013](lync-server-2013-what-s-new-for-clients.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

