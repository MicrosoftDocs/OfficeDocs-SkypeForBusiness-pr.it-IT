---
title: 'Lync Server 2013: opzioni di distribuzione del gateway PSTN'
description: 'Lync Server 2013: opzioni di distribuzione del gateway PSTN.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 871bc4d573e927f83cdb07d4fb2b5d5b954e6383
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565592"
---
# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a>Opzioni di distribuzione di gateway PSTN in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-21_

<div>

## <a name="pstn-gateways"></a>Gateway PSTN

I gateway PSTN (Public Switched Telephone Network) sono componenti hardware di terze parti che convertono i segnali e i dati multimediali tra l'infrastruttura VoIP aziendale e la rete PSTN direttamente o mediante connessione a trunk SIP. In entrambe le topologie il gateway termina la rete PSTN. Il gateway è isolato nella propria subnet ed è connesso alla rete aziendale tramite il Mediation Server.

Un'organizzazione con più siti in genere distribuisce uno o più gateway in ogni sito. I siti di succursale possono connettersi alla rete PSTN tramite un gateway o tramite un Survivable Branch Appliance, che combina gateway e server in una singola casella. Se i siti di succursale utilizzano un gateway, è necessario che il servizio di registrazione e Mediation Server siano necessari nel sito, a meno che il collegamento WAN non sia resiliente. Uno o più Mediation Server, che sono collocati nei Front End Server, possono instradare le chiamate per uno o più gateway in ogni sito. È consigliabile che il servizio di registrazione, il Mediation Server e il gateway richiesti nel sito siano distribuiti come Survivable Branch Appliance.

Determinare il numero, le dimensioni e la posizione dei gateway PSTN è forse la decisione più importante e costosa che è necessario apportare quando si pianifica l'infrastruttura VoIP aziendale.

Di seguito sono riportate le principali domande da prendere in considerazione. Tenere presente che le risposte a queste domande sono tutte interdipendenti

  - Quanti gateway PSTN sono necessari? La risposta dipende dal numero di utenti, dal numero previsto di chiamate simultanee (carico del traffico) e dal numero di siti (ogni sito ne ha bisogno).

  - Quali dimensioni devono essere i gateway? La risposta dipende dal numero di utenti nel sito e dal carico di traffico.

  - Dove devono essere ubicati i gateway? La risposta dipende in parte dalla topologia e in parte dalla distribuzione geografica dell'organizzazione.

È inoltre consigliabile prendere in considerazione le opzioni di topologia del gateway (per informazioni dettagliate, vedere Topologie del gateway più avanti in questo argomento).

<div>

## <a name="mn-trunk-support"></a>Supporto dei trunk M:N

I Mediation Server possono instradare le chiamate tramite più gateway, Session Border Controller (SBCs) forniti da provider di servizi di telefonia Internet o una combinazione di due. Inoltre, più Mediation Server nel pool è in grado di interagire con più gateway. La route logica definita tra un Mediation Server e un gateway è denominata *trunk*. Quando un utente interno inserisce una chiamata PSTN, la logica di routing in uscita nel pool Front End sceglie il trunk da instradare oltre tutte le combinazioni possibili che potrebbero essere disponibili per il routing di quella chiamata specifica. Con il bilanciamento del carico DNS, se una chiamata non riesce a raggiungere un gateway a causa di un problema con un determinato Mediation Server nel pool, la chiamata verrà ritentata in un Mediation server alternativo nel pool.

Per informazioni dettagliate sulla pianificazione di più gateway, vedere [M:N trunk in Lync Server 2013](lync-server-2013-m-n-trunk.md).

Per informazioni dettagliate sull'altro miglioramento del routing in uscita, vedere [Voice routes in Lync Server 2013](lync-server-2013-voice-routes.md).

</div>

<div>

## <a name="gateway-topologies"></a>Topologie di gateway

Se si considerano le questioni fondamentali della distribuzione di gateway, eseguire la procedura seguente:

1.  Contare i siti in cui si desidera fornire la connettività PSTN tramite VoIP aziendale.

2.  Stimare il traffico in ogni sito (numero di utenti e numero medio di chiamate all'ora per utente).

3.  Distribuire uno o più gateway in ogni sito per gestire il traffico previsto.

La topologia del gateway distribuito risultante è illustrata nella figura seguente.

**Topologia del gateway distribuito**

![Diagramma della topologia di gateway distribuiti](images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "Diagramma della topologia di gateway distribuiti")

Con questa topologia, le chiamate tra i lavoratori di ogni sito e tra i siti vengono instradate all'interno della rete Intranet. Le chiamate alla rete PSTN vengono instradate tramite la Network IP dell'organizzazione ai gateway più vicini alla posizione dei numeri di destinazione. Ma cosa succede se l'organizzazione supporta decine o centinaia o addirittura migliaia di siti distribuiti in uno o più continenti, come fanno molte istituzioni finanziarie e altre imprese di grandi dimensioni? In questi casi, la distribuzione di un gateway separato in ogni sito non è pratico.

Per risolvere questo problema, molte società di grandi dimensioni preferiscono distribuire uno o più siti centrali di telefonia di grandi dimensioni, come illustrato nella figura seguente.

**Topologia del sito centrale di telefonia**

![Topologia del gateway Data Center](images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Topologia del gateway Data Center")

In questa topologia, numerosi gateway di grandi dimensioni sufficienti per ospitare il carico utente previsto vengono distribuiti in ogni sito centrale. Tutte le chiamate agli utenti nell'organizzazione vengono inoltrate dal provider di servizi telefonici della società a un sito centrale. La logica di routing nel sito centrale determina se la chiamata deve essere instradata attraverso la rete Intranet o la rete PSTN.

</div>

<div>

## <a name="gateway-location"></a>Posizione del gateway

Il percorso del gateway può anche determinare i tipi di gateway scelti e il modo in cui vengono configurati. Sono disponibili dozzine di protocolli PSTN, nessuno dei quali è uno standard mondiale. Se tutti i gateway sono situati in un singolo paese/area geografica, non si tratta di un problema, ma se si individuano i gateway in diversi paesi/aree geografiche, è necessario configurarli in base agli standard PSTN di quel paese/area geografica. Inoltre, i gateway certificati per l'operazione, ad esempio il Canada, potrebbero non essere certificati in India, Brasile o nell'Unione europea.

</div>

<div>

## <a name="gateway-size-and-number"></a>Dimensione e numero del gateway

I gateway PSTN che la maggior parte delle organizzazioni valuterà la distribuzione di un intervallo di dimensioni da 2 a fino a 960 porte. (Esistono anche gateway più grandi, ma questi sono utilizzati principalmente dai provider di servizi di telefonia). Quando si valuta il numero di porte richieste dall'organizzazione, utilizzare le linee guida seguenti:

  - Le organizzazioni con utilizzo di telefonia chiaro (una chiamata PSTN per utente all'ora) devono allocare una porta per ogni 15 utenti. Ad esempio, se si dispone di 20 utenti, sarà necessario un gateway con due porte.

  - Le organizzazioni con un utilizzo di telefonia moderato (due chiamate PSTN per utente all'ora) devono allocare una porta per ogni 10 utenti. Ad esempio, se si dispone di 100 utenti, sarà necessario un totale di 10 porte allocate tra uno o più gateway.

  - Le organizzazioni con un utilizzo pesante della telefonia (tre o più chiamate PSTN per utente all'ora) devono allocare una porta per ogni cinque utenti. Ad esempio, se si dispone di 47.000 utenti, sarà necessario un totale di 9.400 porte allocate tra almeno 10 gateway di grandi dimensioni.

  - È possibile acquisire ulteriori porte quando aumenta il numero di utenti o la quantità di traffico nell'organizzazione.

Per un determinato numero di utenti che è necessario supportare, è possibile scegliere di distribuire meno, gateway più grandi o più piccoli. Come regola generale, è consigliabile un minimo di due gateway per un'organizzazione per mantenere la disponibilità se un gateway ha esito negativo.

Ogni gateway PSTN distribuito deve disporre di almeno un Mediation Server corrispondente.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

