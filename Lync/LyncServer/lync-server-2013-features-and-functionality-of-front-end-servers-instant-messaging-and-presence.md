---
title: 'Lync Server 2013: caratteristiche e funzionalità di front end server, messaggistica istantanea e presenza'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Features and functionality of Front End Servers, instant messaging, and presence
ms:assetid: 05b29536-dcd7-49b5-934a-2ebf20ddc45c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398109(v=OCS.15)
ms:contentKeyID: 48183294
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ab1b2285b80098ec6acf1faad64f21a78472c0b2
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179653"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Caratteristiche e funzionalità di front end server, messaggistica istantanea e presenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-17_

I Front End Server offrono la maggior parte delle funzionalità di Lync Server. Sono disponibili due edizioni: Lync Server Enterprise Edition, che è stato creato principalmente per organizzazioni di grandi dimensioni e Lync Server Standard Edition, che è stato creato principalmente per organizzazioni di piccole dimensioni che desiderano un Investment hardware più piccolo e non richiedono disponibilità elevata. Entrambe le edizioni supportano tutti i carichi di lavoro di Lync Server, tra cui messaggistica istantanea, presenza, conferenza e VoIP aziendale.

La messaggistica istantanea consente agli utenti di comunicare tra loro in tempo reale mediante i loro computer con messaggi di testo. Sono supportate le sessioni di messaggistica istantanea sia tra due che tra più parti. Un partecipante a una conversazione di messaggistica istantanea tra due parti può aggiungere un terzo partecipante in qualsiasi momento. In tal caso, la finestra relativa alla conversazione cambia in modo da supportare le funzionalità di conferenza.

<div>


> [!IMPORTANT]
> I client Lync e Communicator quando sono coinvolti in una comunicazione One to One, vengono spesso definiti peer-to-peer. Tecnicamente, i due client stanno comunicando in una conversazione One to One, con la Central Messaging Multipoint Control Unit (IMMCU) al centro. IMMCU è un componente di front end server. L'inserimento di IMMCU nel flusso di lavoro di comunicazione necessario consente di abilitare la registrazione dettagli chiamata e altre caratteristiche abilitate dal front end server. La comunicazione è da una porta di origine dinamica sul client alla porta del server front-end TLS/TCP/5061 (presupponendo l'utilizzo della sicurezza del layer di trasporto consigliato). In base alla progettazione, la comunicazione peer-to-peer (così come la messaggistica istantanea a più parti) è possibile solo quando Lync Server e IMMCU sono attivi e disponibili.



</div>

La *presenza* fornisce informazioni sullo stato di altri utenti presenti sulla rete. Lo stato di presenza di un utente fornisce informazioni che aiutano altri utenti a decidere se tentare di contattarlo e se utilizzare la messaggistica istantanea, il telefono o la posta elettronica. La presenza induce a scegliere la comunicazione istantanea ma, segnalando anche se un utente è in riunione o fuori ufficio, consente di capire quando la comunicazione istantanea non può essere utilizzata. Questo stato di presenza viene visualizzato come icona presenza in Lync e in altre applicazioni in grado di riconoscere la presenza, tra cui il client di messaggistica e collaborazione di Microsoft Outlook, Microsoft SharePoint Technologies, Microsoft Word e il foglio di calcolo di Microsoft Excel software. L'icona della presenza rappresenta la volontà di comunicare e la disponibilità corrente dell'utente.

</div>

<span> </span>

</div>

</div>

</div>

