---
title: 'Lync Server 2013: routing delle chiamate al servizio E9-1-1 tramite un gateway ELIN'
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
ms.openlocfilehash: 93e2e3bf94175f2f0ec3f4f7528cc969fe19529c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144532"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-an-elin-gateway-in-lync-server-2013"></a>Routing delle chiamate al servizio E9-1-1 tramite un gateway ELIN in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-05_

Alcuni partner del programma Unified Communications Open Interoperability offrono gateway ELIN (Emergency Location Identification Number) qualificati, che rappresentano un'alternativa a una connessione trunk SIP a un provider di servizi E9-1-1 qualificato. I gateway ELIN supportano la connettività ISDN o CAMA (Centralized Automatic Message Accounting) ai servizi E9-1-1 basati su PSTN (Public Switched Telephone Network). Per informazioni dettagliate sui partner che forniscono gateway ELIN e collegamenti alla relativa documentazione, vedere [https://go.microsoft.com/fwlink/p/?LinkId=248425](https://go.microsoft.com/fwlink/p/?linkid=248425).

Analogamente alle connessioni trunk SIP ai provider di servizi E9-1-1, i gateway ELIN offrono anche i mezzi per instradare una chiamata di emergenza al punto di risposta di sicurezza pubblica più appropriato del chiamante (PSAP), ma questi gateway utilizzano un ELIN come identificatore di percorso. È possibile definire i numeri ELIN per ogni posizione di risposta di emergenza nell'organizzazione (per informazioni dettagliate, vedere [Managing locations for Elin Gateways in Lync Server 2013](lync-server-2013-managing-locations-for-elin-gateways.md)).

Quando si utilizza un gateway ELIN per le chiamate di emergenza, è possibile utilizzare la stessa infrastruttura E9-1-1 di Lync Server che si desidera utilizzare per una connessione trunk SIP. Il database del servizio informazioni percorso fornisce il percorso al client di Lync Server e il criterio percorso consente di abilitare la caratteristica e di definire il routing. Con un gateway ELIN, tuttavia, è necessario aggiungere i numeri ELIN al database del servizio informazioni percorso e fare in modo che il gestore PSTN li carichi nel database ALI (Automatic Location Identification).

Quando un client Lync ottiene la propria posizione dal servizio informazioni percorso, il percorso include il valore ELIN. Durante la chiamata di emergenza, il numero ELIN viene incluso nella posizione inviata al gateway ELIN. Il gateway ELIN identifica la chiamata come chiamata di emergenza e scambia il numero del chiamante con il numero ELIN. La chiamata viene quindi instradata dal gateway ELIN a PSTN con il numero ELIN indicato come numero chiamante. Il provider di servizi E9-1-1 PSTN cerca il numero ELIN nel database ALI, che è un database complementare a quello dello stradario generale. La chiamata viene quindi inviata tramite PSTN al centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point) più appropriato, in base alla ricerca nel database ALI e il centro di raccolta delle chiamate di emergenza invia i soccorsi alla posizione del chiamante in base alla ricerca nel database ALI. Il numero chiamante viene memorizzato nella cache nel gateway ELIN per un periodo di tempo predefinito per le richiamate. Durante la richiamata, il centro di raccolta delle chiamate di emergenza raggiunge il gateway ELIN, che scambia il numero ELIN con il numero DID (Direct Inward Dialing) del chiamante.

I gateway ELIN supportano chiamate di emergenza solo dall'interno della rete dell'organizzazione. Non sono supportate chiamate di emergenza effettuate dall'esterno della rete.

<div>


> [!NOTE]  
> Per informazioni dettagliate sull'utilizzo di una connessione trunk SIP per le chiamate di emergenza, vedere routing delle chiamate al servizio <A href="lync-server-2013-routing-e9-1-1-calls-by-using-a-sip-trunk.md">E9-1-1 tramite un trunk SIP in Lync Server 2013</A>.



</div>

Nel diagramma seguente viene illustrato in che modo viene instradata una chiamata di emergenza da Lync Server a PSAP quando si utilizza un gateway ELIN.

**Routing delle chiamate E9-1-1 con un gateway ELIN**

![ea68f88a-0fc4-43d4-9660-79a7e8936df1](images/JJ204919.ea68f88a-0fc4-43d4-9660-79a7e8936df1(OCS.15).jpg "ea68f88a-0fc4-43d4-9660-79a7e8936df1")

1.  Un SIP INVITE contenente la posizione, il numero di callback del chiamante e l'URL di notifica (facoltativo) e il numero di richiamata della conferenza sono instradati a Lync Server.

2.  Lync Server corrisponde al numero di emergenza e quindi instrada la chiamata (in base al valore di **utilizzo PSTN** definito nei criteri di percorso applicabili) a un Mediation Server e da qui a un gateway ELIN.

3.  Il gateway ELIN instrada la chiamata su un trunk ISDN o CAMA alla rete PSTN.

4.  La rete PSTN identifica quindi la chiamata come chiamata di emergenza e la instrada a un router selettivo E9-1-1 nella rete. Tale router selettivo E9-1-1 cerca il numero del chiamante nel database ALI per ottenere la posizione geografica. Il router selettivo E9-1-1 invia la chiamata al punto PSAP più appropriato in base alle informazioni sulla posizione recuperate dal database ALI.

5.  Se i criteri percorso sono stati configurati per le notifiche, uno o più agenti di sicurezza dell'organizzazione ricevono un messaggio istantaneo speciale di notifica di emergenza di Lync. Questo messaggio viene sempre visualizzato nelle schermate degli addetti alla sicurezza e contiene il nome, il numero di telefono, l'ora e il percorso del chiamante, consentendo al personale di sicurezza di rispondere rapidamente al chiamante di emergenza utilizzando un messaggio istantaneo o una voce.

6.  Se la chiamata viene interrotta prematuramente, il centro di raccolta delle chiamate di emergenza utilizza il numero ELIN per contattare direttamente il chiamante. Il gateway ELIN scambia i numero ELIN con il numero DID del chiamante.

</div>

<span> </span>

</div>

</div>

</div>

