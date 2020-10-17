---
title: "Lync Server 2013: Panoramica dell'accesso degli utenti esterni"
description: "Lync Server 2013: Panoramica dell'accesso degli utenti esterni."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of external user access
ms:assetid: 97aded6c-5fa3-4225-95a6-9ad094d61654
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398775(v=OCS.15)
ms:contentKeyID: 48184934
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d2900dde457da34c4438892878ae7ddb4f74723a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48562892"
---
# <a name="overview-of-external-user-access-in-lync-server-2013"></a>Panoramica dell'accesso degli utenti esterni in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-11-07_

In questa documentazione, viene utilizzato il termine *utente esterno* per definire una categoria di utenti di grandi dimensioni che comunicano con gli utenti di lync Server 2013 e Lync 2013 dall'esterno del firewall. Gli utenti esterni autorizzati a comunicare con gli utenti interni di Lync Server 2013 (ovvero gli utenti che eseguono l'accesso a Lync Server dall'interno del firewall) possono includere gli elementi seguenti:

  - **Utenti**     remoti Utenti dell'organizzazione che effettuano l'accesso a Lync Server dall'esterno del firewall.

  - **Utenti federati**     Gli utenti che dispongono di un account con un cliente o un'organizzazione partner attendibili, ad esempio Lync Server 2010, Lync Server 2013 o Office Communications Server 2007 R2. Gli utenti federati possono inoltre essere membri di organizzazioni partner definite che utilizzano il protocollo XMPP (Extensible Messaging and Presence Protocol) tramite il proxy XMPP sul server perimetrale e il gateway XMPP nel server front-end o nel pool. Una relazione di trust definita, denominata Federazione, non è correlata o dipendente da una relazione di trust tra servizi di dominio Active Directory.
    
    <div>
    

    > [!NOTE]  
    > Una data di fine vita del 2014 giugno per AOL e Yahoo! sono stati annunciati. Per informazioni dettagliate, vedere <A href="lync-server-2013-support-for-public-instant-messenger-connectivity.md">supporto per la connettività di messaggistica istantanea pubblica in Lync Server 2013</A>.

    
    </div>

  - Utenti di connettività per la **messaggistica istantanea pubblica**     Contatti che gli utenti stabiliscono tramite servizi di connettività di messaggistica istantanea pubblica (Windows Live, Yahoo\! e AOL).

  - **Utenti mobili**     Gli utenti che sono membri dell'organizzazione che utilizzano uno Smart Phone o un tablet che eseguono un accesso client di Lync mobile alla distribuzione interna e sono in grado di comunicare con le altre classi di utenti. L'utente mobile utilizza i servizi per dispositivi mobili che vengono pubblicati tramite il proxy inverso per accedere alla distribuzione interna. Per informazioni dettagliate sulle caratteristiche e le funzionalità disponibili per Lync mobile, vedere le tabelle di confronto dei client per dispositivi mobili all'indirizzo [https://go.microsoft.com/fwlink/p/?LinkID=234777](https://go.microsoft.com/fwlink/p/?linkid=234777) .

  - **Utenti**     anonimi Gli utenti che non dispongono di un account utente nei servizi di dominio Active Directory dell'organizzazione o in un dominio federato supportato, ma che hanno ricevuto inviti a partecipare in remoto in una conferenza locale.

La distribuzione del server perimetrale fornisce l'accesso esterno per i tipi di comunicazione seguenti:

  - **Messaggistica istantanea e presenza**     Gli utenti esterni autorizzati possono partecipare alle conversazioni e alle conferenze di messaggistica istantanea e possono ottenere informazioni sullo stato di presenza di un altro utente. Gli utenti dei provider di servizi di messaggistica istantanea possono partecipare alle conversazioni di messaggistica istantanea con singoli utenti di Lync Server nell'organizzazione e accedere alle informazioni sulla presenza, ma non possono partecipare a conferenze di messaggistica istantanea con più partecipanti utilizzando Lync Server. Il supporto è limitato alle comunicazioni peer-to-peer. Il trasferimento di file non è supportato per gli utenti di provider di servizi di messaggistica istantanea pubblica e audio/video nelle comunicazioni peer-to-peer è supportato per gli utenti di Windows Messenger 2011, ma non per gli altri utenti di provider di servizi di messaggistica istantanea pubblica.
    
    Sono supportati sia i protocolli SIP che XMPP. Per fornire servizi per XMPP, vedere [pianificazione per SIP, Federazione XMPP e messaggistica istantanea pubblica in Lync Server 2013](lync-server-2013-planning-for-sip-xmpp-federation-and-public-instant-messaging.md).

  - **Web Conferencing**     Gli utenti esterni autorizzati possono partecipare a conferenze ospitate nella distribuzione di Lync Server. Gli utenti remoti, federati e anonimi possono essere autorizzati alla partecipazione alle conferenze Web, ma gli utenti di messaggistica istantanea pubblica non possono partecipare alle conferenze. In base alle opzioni selezionate, gli utenti abilitati per il Web Conferencing possono partecipare alla condivisione di desktop e applicazioni e possono fungere da organizzatori o relatori delle riunioni.

  - **A/V Conferencing**     Gli utenti esterni autorizzati possono partecipare alle conferenze audio e video che la distribuzione di Lync Server ospita. Audio/video nelle comunicazioni peer-to-peer è supportato per gli utenti di Windows Messenger 2011, ma non per gli altri utenti di provider di servizi di messaggistica istantanea pubblica.

Per controllare le comunicazioni, è possibile configurare uno o più criteri che definiscono il modo in cui gli utenti all'interno e all'esterno dell'organizzazione comunicano tra loro. È inoltre possibile configurare impostazioni e applicare criteri per singoli utenti interni o per tipi specifici di utenti esterni allo scopo di controllare le comunicazioni con gli utenti esterni.

Ruoli di Lync Server 2013 utilizzati per fornire accesso esterno:

**Server**     perimetrale Il server perimetrale è un server o un pool di server che eseguono i servizi che consentono l'accesso esterno alle funzionalità di messaggistica istantanea e presenza, conferenze, audio/video e altri elementi multimediali, ad esempio i servizi di trasferimento file. Facoltativamente, è possibile configurare il server perimetrale per la Federazione con altre distribuzioni di Lync Server o Office Communications Server 2007 R2 e altre distribuzioni XMPP. La funzionalità di connettività di messaggistica istantanea pubblica facoltativa è abilitata e configurata tramite il server perimetrale.

**Direttrice**     Il Director è un server o un pool di server facoltativo che esegue il ruolo di amministratore di Lync Server 2013 che consente di preautenticare le richieste degli utenti e di indirizzare le richieste al front end server o al pool Front-end degli utenti, ma non a casa degli account utente.

**Proxy**     inverso Un proxy inverso è un termine generale per i server specializzati che pubblicano le risorse disponibili nella rete interna e recuperano informazioni per i client dalla risorsa pubblicata. Lync Server 2013 utilizza il proxy inverso per pubblicare una serie di funzionalità, ad esempio riunioni di conferenza, percorsi di partecipazione alle conferenze, rubrica, espansione della lista di distribuzione, download del contenuto delle riunioni, aggiornamenti dei dispositivi, servizi di mobilità e altro ancora. È possibile utilizzare qualsiasi proxy inverso in grado di soddisfare i requisiti per la pubblicazione dei percorsi delle risorse necessari. Microsoft Forefront Threat Management Gateway (TMG) 2010 viene utilizzato come esempio allo scopo di illustrare le regole di pubblicazione necessarie, ma Forefront TMG 2010 non è necessario.

<div>


> [!IMPORTANT]  
> Lync Server 2013 supporta sia IPv4 che IPv6. Windows Server &nbsp; 2008 &nbsp; R2, windows Server 2012 e windows Server 2012 R2 utilizzano uno stack doppio in grado di utilizzare contemporaneamente IPv4 e IPv6. Questo è importante a causa della natura transitoria di una distribuzione che si sposta da IPv4 a IPv6. IPv4 può essere supportato in alcune aree, dove in altre aree della distribuzione è possibile utilizzare IPv6. Questo è particolarmente importante per la distribuzione di Internet e delle distribuzioni interne. I client esterni devono comunicare tramite il proxy inverso per l'utilizzo di servizi quali mobilità, riunioni, download della Rubrica e altro. Attualmente, Forefront Threat Management Gateway 2010 e Internet Security and Acceleration Server 2006 non supportano l'indirizzamento IPv6, indipendentemente dalla versione del sistema operativo in cui sono state distribuite. È necessario pianificare di conseguenza l'utilizzo di IPv6 e IPv4 in relazione ai client esterni.



</div>

</div>

<span> </span>

</div>

</div>

</div>

