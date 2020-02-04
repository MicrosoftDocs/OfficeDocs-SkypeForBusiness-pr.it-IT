---
title: 'Lync Server 2013: Definizione dei requisiti per Front End Server, messaggistica istantanea e presenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your requirements for Front End Servers, instant messaging, and presence
ms:assetid: c21198bc-520c-4d17-8b84-7ff1475b9b0a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412956(v=OCS.15)
ms:contentKeyID: 48185319
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: af371d116948d348b49c552dfe53290c1dae1900
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743416"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Definizione dei requisiti per Front End Server, messaggistica istantanea e presenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-10-07_

L'attività principale di pianificazione per la messaggistica istantanea e la presenza è garantire che i server front-end siano sufficienti per gli utenti.

<div>

## <a name="enabling-communication-with-external-users"></a>Abilitazione delle comunicazioni con utenti esterni

È possibile aumentare notevolmente i vantaggi offerti dall'investimento in Lync Server, consentendo agli utenti di comunicare con utenti esterni. Gli utenti esterni possono includere:

  - **Utenti remoti**   gli utenti dell'organizzazione, quando lavorano all'esterno dei firewall e usano i loro laptop o altri dispositivi Lync Server.

  - **Gli utenti federati**   degli utenti di aziende con cui si lavora che eseguono anche Lync Server. Per consentire agli utenti di contattare facilmente questi utenti, è possibile creare relazioni federate con queste società.

  - **Utenti pubblici**   utenti di servizi di messaggistica istantanea pubblica, ad esempio i servizi di messaggistica istantanea forniti da Windows Live Network of\!Internet Services, Yahoo e AOL, e gli utenti di provider e server che usano il protocollo XMPP (Extensible Messaging and Presence Protocol), ad esempio Google Talk.
    
    <div>
    

    > [!NOTE]  
    > Tieni presente che potrebbe essere necessaria una licenza separata per la connettività di messaggistica istantanea pubblica con Windows Live, AOL e Yahoo!

    
    </div>
    
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

Per abilitare uno o tutti questi scenari, è necessario distribuire un server perimetrale per facilitare le comunicazioni sicure tra la distribuzione di Lync Server e gli utenti esterni. Gli utenti e gli utenti remoti dell'organizzazione presso le organizzazioni federate potranno vedere la presenza e comunicare tramite messaggistica istantanea. Per informazioni dettagliate sull'abilitazione delle comunicazioni con utenti esterni, vedere [pianificazione per l'accesso degli utenti esterni in Lync Server 2013](lync-server-2013-planning-for-external-user-access.md) nella documentazione relativa alla pianificazione.

</div>

<div>

## <a name="archiving-im-content"></a>Archiviazione del contenuto di messaggistica istantanea

Lync Server offre funzionalità che possono essere usate se l'organizzazione deve seguire le regole di conformità. È possibile usare l'archiviazione per archiviare il contenuto dei messaggi di messaggistica istantanea per tutti gli utenti dell'organizzazione o solo per determinati utenti specificati. Per informazioni dettagliate, vedere [pianificazione dell'archiviazione in Lync Server 2013](lync-server-2013-planning-for-archiving.md) nella documentazione relativa alla pianificazione.

Se è stato distribuito anche Microsoft Exchange Server 2013, è possibile integrare l'archiviazione dei dati di Exchange con l'archiviazione dei dati di Lync Server e usare un singolo strumento per eseguire ricerche in entrambi i tipi di dati archiviati. Per altre informazioni, vedere [configurazione di Microsoft Lync server 2013 per usare l'archiviazione di Microsoft Exchange server 2013](configuring-lync-server-2013-to-use-microsoft-exchange-server-2013-archiving.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

