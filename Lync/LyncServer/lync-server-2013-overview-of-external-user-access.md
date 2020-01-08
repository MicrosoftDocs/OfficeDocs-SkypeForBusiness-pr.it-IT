---
title: "Lync Server 2013: Panoramica dell'accesso degli utenti esterni"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of external user access
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398775(v=OCS.15)
ms:contentKeyID: 48184934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a527df5a3bc7b296d17860c7a02876dbc31fbc4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40979904"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-external-user-access-in-lync-server-2013"></a>Panoramica dell'accesso degli utenti esterni in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-11-07_

In questa documentazione usiamo il termine *utente esterno* per definire un'ampia categoria di utenti che comunicano con gli utenti di lync Server 2013 e Lync 2013 esterni al firewall. Gli utenti esterni autorizzati a comunicare Lync Server 2013 con utenti interni, ovvero gli utenti che accedono a Lync Server dall'interno del firewall, possono includere i seguenti elementi:

  - **Utenti remoti**   utenti dell'organizzazione che accedono a Lync Server dall'esterno del firewall.

  - **Utenti federati utenti**   che dispongono di un account con un cliente o un'organizzazione partner attendibile, ad esempio Lync Server 2010, Lync Server 2013 o Office Communications Server 2007 R2. Gli utenti federati possono anche essere membri di organizzazioni partner definite che usano il protocollo XMPP (Extensible Messaging and Presence Protocol) tramite il proxy XMPP sul server perimetrale e il gateway XMPP nel server o nel pool Front-end. Una relazione di trust definita, denominata Federazione, non è correlata o dipendente da una relazione di trust tra servizi di dominio Active Directory.
    
    <div>
    

    > [!NOTE]  
    > Data di fine vita del 2014 giugno per AOL e Yahoo! è stato annunciato. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.

    
    </div>

  - **Utenti della connettività di messaggistica istantanea pubblica**   contatti che gli utenti stabiliscono tramite servizi di connettività di messaggistica istantanea pubblica (Windows Live, Yahoo\! e AOL).

  - **Utenti di dispositivi mobili**   utenti che fanno parte dell'organizzazione che usano uno smartphone o un tablet con un client di Lync mobile che esegue l'accesso alla distribuzione interna e che possono comunicare con le altre classi di utenti. L'utente di dispositivi mobili usa i servizi di mobilità pubblicati tramite il proxy inverso per accedere alla distribuzione interna. Per informazioni dettagliate sulle caratteristiche e le funzionalità disponibili per Lync mobile, vedere le tabelle di [http://go.microsoft.com/fwlink/p/?LinkID=234777](http://go.microsoft.com/fwlink/p/?linkid=234777)confronto tra client per dispositivi mobili.

  - **Utenti anonimi**   utenti che non dispongono di un account utente nei servizi di dominio Active Directory dell'organizzazione o in un dominio federato supportato, ma che hanno ricevuto inviti a partecipare in remoto in una conferenza locale.

La distribuzione di Edge consente l'accesso esterno per i tipi di comunicazione seguenti:

  - **Messaggistica istantanea e presenza**   gli utenti esterni autorizzati possono partecipare a conversazioni e conferenze di messaggistica istantanea e possono ottenere informazioni sullo stato presenza di un altro utente. Gli utenti dei provider di servizi di messaggistica istantanea pubblica possono partecipare alle conversazioni di messaggistica istantanea con singoli utenti di Lync Server nell'organizzazione e accedere alle informazioni sulla presenza, ma non possono partecipare a conferenze multiparte di messaggistica istantanea tramite Lync Server. Si tratta di comunicazioni strettamente peer-to-peer. Il trasferimento di file non è supportato per gli utenti di provider di servizi di messaggistica istantanea pubblici e l'audio/video nelle comunicazioni peer-to-peer è supportato per gli utenti di Windows Messenger 2011, ma non per altri utenti di provider di servizi di messaggistica istantanea pubblici.
    
    Sono supportati sia i protocolli SIP che XMPP. Per ottenere servizi per XMPP, vedere [pianificazione per SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md).

  - ****   Gli utenti esterni autorizzati da Web Conferencing possono partecipare a conferenze ospitate nella distribuzione di Lync Server. Gli utenti remoti, gli utenti federati e gli utenti anonimi possono essere abilitati per la partecipazione alle conferenze Web, ma gli utenti di messaggistica istantanea pubblica non possono partecipare alle conferenze. A seconda delle opzioni selezionate, gli utenti abilitati per le conferenze Web possono partecipare alla condivisione di desktop e applicazioni e possono fungere da organizzatori o relatori della riunione.

  - **Gli utenti esterni autorizzati a/V Conferencing**   possono partecipare a conferenze audio e video che gli host di distribuzione di Lync Server. L'audio/video nelle comunicazioni peer-to-peer è supportato per gli utenti di Windows Messenger 2011, ma non per altri utenti di provider di servizi di messaggistica istantanea pubblica.

Per controllare le comunicazioni, è possibile configurare uno o più criteri che definiscono il modo in cui gli utenti all'interno e all'esterno dell'organizzazione comunicano tra loro. È anche possibile configurare le impostazioni e applicare criteri per singoli utenti interni o per tipi specifici di utenti esterni per controllare le comunicazioni con utenti esterni.

Ruoli di Lync Server 2013 usati per consentire l'accesso esterno:

**Edge Server**   l'Edge Server è un server o un pool di server che eseguono i servizi che consentono l'accesso esterno a messaggistica istantanea e presenza, servizi di conferenza, audio/video e altri elementi multimediali (ad esempio file di trasferimento). Facoltativamente, è possibile configurare l'Edge Server per la Federazione con altre distribuzioni di Lync Server o Office Communications Server 2007 R2 e altre distribuzioni XMPP. La caratteristica di connettività di messaggistica istantanea pubblica facoltativa viene abilitata e configurata tramite il server perimetrale.

**Director**   il Director è un server o un pool di server facoltativo che esegue il ruolo di amministratore di Lync Server 2013 che pre-autentica le richieste utente e instrada le richieste al server front-end o al pool Front-end degli utenti, ma non a tutti gli account utente.

**Proxy**   inverso un proxy inverso è un termine generico per i server specializzati che pubblicano le risorse disponibili nella rete interna e recuperano le informazioni per i clienti dalla risorsa pubblicata. Lync Server 2013 usa il proxy inverso per pubblicare una serie di funzionalità, ad esempio riunioni di conferenza, percorsi di conferenza, rubrica, espansione della lista di distribuzione, download del contenuto della riunione, aggiornamenti dei dispositivi, servizi di mobilità e altro ancora. Può essere usato qualsiasi proxy inverso che soddisfi i requisiti per la pubblicazione delle posizioni di risorse necessarie. Microsoft Forefront Threat Management Gateway (TMG) 2010 viene usato come esempio per illustrare le regole di pubblicazione necessarie, ma Forefront TMG 2010 non è obbligatorio.

<div>


> [!IMPORTANT]  
> Lync Server 2013 supporta sia IPv4 che IPv6. Windows Server&nbsp;2008&nbsp;r2, Windows Server 2012 e Windows Server 2012 R2 usano uno stack duale che può usare contemporaneamente IPv4 e IPv6. Questa operazione è importante a causa della natura transitoria di una distribuzione che si sposta da IPv4 a IPv6. IPv4 può essere supportato in alcune aree, dove in altre aree della distribuzione è possibile usare IPv6. Questo aspetto è particolarmente importante per quanto riguarda Internet e le distribuzioni interne. I client esterni devono comunicare tramite il proxy inverso per l'uso di servizi come la mobilità, le riunioni, il download della Rubrica e altri. Attualmente, Forefront Threat Management Gateway 2010 e Internet Security e Acceleration Server 2006 non supportano l'indirizzamento IPv6, indipendentemente dalla versione del sistema operativo in cui sono stati distribuiti. È necessario pianificare di conseguenza l'uso di IPv6 e IPv4 in relazione ai client esterni.



</div>

</div>

<span> </span>

</div>

</div>

</div>

