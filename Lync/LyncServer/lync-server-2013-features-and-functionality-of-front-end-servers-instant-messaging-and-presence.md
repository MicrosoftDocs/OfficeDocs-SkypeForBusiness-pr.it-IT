---
title: 'Lync Server 2013: Caratteristiche e funzionalità di Front End Server, messaggistica istantanea e presenza'
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
ms.openlocfilehash: 4a76dfed553e85838739c7c348e5bc53fc9943a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="features-and-functionality-of-front-end-servers-instant-messaging-and-presence-in-lync-server-2013"></a>Caratteristiche e funzionalità di Front End Server, messaggistica istantanea e presenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-03-17_

I server front-end garantiscono la maggior parte delle funzionalità di Lync Server. Sono disponibili due edizioni: Lync Server Enterprise Edition, progettato principalmente per le organizzazioni di grandi dimensioni, e Lync Server Standard Edition, progettato principalmente per le organizzazioni più piccole che desiderano un Investment hardware più piccolo e non richiedono disponibilità elevata. Entrambe le edizioni supportano tutti i carichi di lavoro di Lync Server, tra cui messaggistica istantanea, presenza, conferenza e VoIP aziendale.

La messaggistica istantanea consente agli utenti di comunicare tra loro in tempo reale nei propri computer usando messaggi basati su testo. Sono supportate entrambe le sessioni di messaggistica istantanea a due parti e a più parti. Un partecipante a una conversazione di messaggistica istantanea a due parti può aggiungere un terzo partecipante alla conversazione in qualsiasi momento. In questo caso, la finestra di conversazione viene modificata per supportare le funzionalità di conferenza.

<div>


> [!IMPORTANT]
> I client di Lync e Communicator quando sono coinvolti in una comunicazione uno-a-uno, vengono spesso definiti peer-to-peer. Tecnicamente, i due client comunicano in una conversazione uno-a-uno, con l'unità di controllo multipunto di messaggistica istantanea (IMMCU) al centro. IMMCU è un componente del server front-end. L'immissione di IMMCU nel flusso di lavoro di comunicazione richiesto consente la registrazione dei dettagli delle chiamate e altre caratteristiche abilitate dal server front-end. La comunicazione è da una porta di origine dinamica nel client alla porta del server front-end TLS/TCP/5061 (presupponendo l'uso della sicurezza del livello di trasporto consigliato). In base alla progettazione, la comunicazione peer-to-peer (così come la messaggistica istantanea a più parti) è possibile solo quando Lync Server e IMMCU è attivo e disponibile.



</div>

La *presenza* fornisce informazioni agli utenti sullo stato di un altro utente nella rete. Lo stato presenza di un utente fornisce informazioni utili per consentire agli altri utenti di decidere se provare a contattare l'utente e se usare la messaggistica istantanea, il telefono o l'indirizzo di posta elettronica. La presenza incoraggia le comunicazioni istantanee quando possibile, ma fornisce anche informazioni sul fatto che un utente si trovi in una riunione o fuori sede, indicando che la comunicazione immediata non è possibile. Questo stato presenza viene visualizzato come icona presenza in Lync e in altre applicazioni che supportano la presenza, incluso il client di messaggistica e collaborazione di Microsoft Outlook, Microsoft SharePoint Technologies, Microsoft Word e il foglio di calcolo di Microsoft Excel software. L'icona presenza rappresenta la disponibilità corrente dell'utente e la disponibilità a comunicare.

</div>

<span> </span>

</div>

</div>

</div>

