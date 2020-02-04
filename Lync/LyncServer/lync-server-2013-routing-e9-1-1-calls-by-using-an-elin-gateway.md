---
title: 'Lync Server 2013: Routing delle chiamate di emergenza tramite un gateway ELIN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using an ELIN gateway
ms:assetid: 5a3997e3-898d-49cb-922a-4184c3373350
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204919(v=OCS.15)
ms:contentKeyID: 48184221
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 97c921a0b31438103ba74dcc64925e5b2069a8e8
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41732848"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a>Routing delle chiamate di emergenza tramite un gateway ELIN in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-05_

Alcuni partner del programma Unified Communications Open Interoperability offrono i gateway con funzionalità di sicurezza per le chiamate di emergenza qualificati (ELIN), che possono fungere da alternativa a una connessione trunk SIP a un provider di servizi E9-1-1 qualificato. I gateway ELIN supportano la connettività (CAMA) ISDN o centralizzata per l'accounting automatico dei messaggi con servizi E9-1-1 basati su PSTN (Public Switched Telephone Network). Per informazioni dettagliate sui partner che includono gateway ELIN e collegamenti alla propria documentazione, vedere [http://go.microsoft.com/fwlink/p/?LinkId=248425](http://go.microsoft.com/fwlink/p/?linkid=248425).

Analogamente alle connessioni trunk SIP ai provider di servizi E9-1-1, i gateway ELIN supportano anche i mezzi per il routing di una chiamata di emergenza al punto di risposta di sicurezza pubblica più appropriato del chiamante (PSAP), ma questi gateway usano un ELIN come identificatore della posizione. Si definiscono gli ELIN per ogni posizione di risposta all'emergenza nell'organizzazione (per informazioni dettagliate, vedere [gestione delle posizioni per i gateway ELIN in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).

Quando si usa un gateway ELIN per le chiamate di emergenza, si usa la stessa infrastruttura E9-1-1 di Lync Server che si usa per una connessione trunk SIP. Il database del servizio informazioni sulla posizione fornisce la posizione al client Lync Server e il criterio della posizione Abilita la caratteristica e definisce il routing. Con un gateway ELIN, tuttavia, è necessario aggiungere il contrassegno ELINs al database del servizio informazioni sulla posizione e fare in modo che il gestore PSTN li carichi nel database ALI (Automatic Location Identification).

Quando un client Lync ottiene la propria posizione dal servizio informazioni sulla posizione, la posizione include il valore ELIN. Durante una chiamata di emergenza, il ELIN è incluso nella posizione inviata al gateway ELIN. Il gateway ELIN identifica la chiamata come chiamata di emergenza e scambia il numero della parte chiamante con ELIN. Il gateway ELIN instrada quindi la chiamata alla rete PSTN con il numero di chiamata ELIN. Il provider E9-1-1 PSTN cerca il numero ELIN nel database ALI, un database complementare per il database stradario (Master Street Address Guide). La rete PSTN invia quindi la chiamata al PSAP più appropriato in base alla ricerca di ALI e PSAP invia i primi soccorritori alla posizione del chiamante in base alla ricerca di ALI. Il numero chiamante viene memorizzato nella cache del gateway ELIN per un periodo di tempo predefinito per i callback. Durante un callback, il PSAP raggiunge il gateway ELIN, che scambia il numero ELIN per il num DID (Direct Interior Dialing) del chiamante.

I gateway ELIN supportano le chiamate di emergenza solo dall'interno della rete dell'organizzazione. Non supportano le chiamate di emergenza effettuate dall'esterno della rete.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'uso di una connessione trunk SIP per le chiamate di emergenza, vedere <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">routing di chiamate E9-1-1 tramite trunk SIP in Lync Server 2013</A>.



</div>

Il diagramma seguente mostra il modo in cui una chiamata di emergenza viene instradata da Lync Server a PSAP quando si usa un gateway ELIN.

**Routing delle chiamate E9-1-1 con un gateway ELIN**

![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")

1.  Un invito SIP contenente la posizione, il numero di callback del chiamante e l'URL di notifica (facoltativo) e il numero di callback della conferenza vengono instradati a Lync Server.

2.  Lync Server corrisponde al numero di emergenza e quindi instrada la chiamata (in base al valore di **utilizzo PSTN** definito nel criterio di posizione applicabile) a un Mediation Server e da lì a un gateway ELIN.

3.  Il gateway ELIN instrada la chiamata su un trunk ISDN o CAMA verso la rete PSTN.

4.  La PSTN identifica la chiamata come chiamata di emergenza e la instrada a un router selettivo E9-1-1 nella rete. Il router selettivo E9-1-1 Cerca il numero del chiamante nel database ALI per ottenere la posizione geografica. Il router selettivo E9-1-1 Invia la chiamata al PSAP più appropriato in base alle informazioni sulla posizione recuperate dal database ALI.

5.  Se sono stati configurati i criteri di posizione per le notifiche, uno o più agenti di sicurezza dell'organizzazione riceveranno un messaggio istantaneo speciale di notifica di emergenza Lync. Questo messaggio compare sempre nella schermata degli addetti alla sicurezza e contiene il nome, il numero di telefono, l'ora e la posizione del chiamante, che consente al personale di sicurezza di rispondere rapidamente al chiamante di emergenza usando un messaggio istantaneo o una voce.

6.  Se la chiamata viene interrotta prematuramente, PSAP usa il ELIN per contattare direttamente il chiamante. Il gateway ELIN scambia il ELIN per il chiamante.

</div>

<span> </span>

</div>

</div>

</div>

