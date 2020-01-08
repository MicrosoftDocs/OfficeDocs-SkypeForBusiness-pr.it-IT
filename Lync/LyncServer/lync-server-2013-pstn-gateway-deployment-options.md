---
title: 'Lync Server 2013: Opzioni di distribuzione di gateway PSTN'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: PSTN gateway deployment options
ms:assetid: d1ab4f74-18aa-40c7-a8cf-ec806cf6e28a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398899(v=OCS.15)
ms:contentKeyID: 48185445
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 137c9996429e953db22bea0c0dbd382f5a7af9a2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980976"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="pstn-gateway-deployment-options-in-lync-server-2013"></a>Opzioni di distribuzione di gateway PSTN in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-21_

<div>

## <a name="pstn-gateways"></a>Gateway PSTN

I gateway PSTN (Public Switched Telephone Network) sono componenti hardware di terze parti che traducono segnalazioni e elementi multimediali tra l'infrastruttura VoIP aziendale e la rete PSTN, direttamente o tramite connessione ai trunk SIP. In entrambe le topologie il gateway termina la rete PSTN. Il gateway è isolato nella relativa subnet ed è connesso alla rete aziendale tramite il server Mediation.

Un'organizzazione con più siti in genere distribuisce uno o più gateway in ogni sito. I siti di succursale possono connettersi alla rete PSTN tramite un gateway o tramite un Survivable Branch Appliance, che combina gateway e server in una singola casella. Se i siti di succursale usano un gateway, è necessario che il registrar e Mediation Server sia obbligatorio nel sito, a meno che il collegamento WAN non sia resiliente. Uno o più server di mediazione, che sono collocati nei server front-end, possono instradare le chiamate per uno o più gateway in ogni sito. È consigliabile che il registrar, il Mediation Server e il gateway richiesto nel sito vengano distribuiti come Survivable Branch Appliance.

La determinazione del numero, delle dimensioni e della posizione dei gateway PSTN è forse la decisione più importante e costosa che è necessario apportare quando si pianifica l'infrastruttura VoIP aziendale.

Ecco le principali domande da prendere in considerazione. Tieni presente che le risposte a queste domande sono tutte interdipendenti

  - Quanti gateway PSTN sono necessari? La risposta dipende dal numero di utenti, dal numero previsto di chiamate simultanee (carico di traffico) e dal numero di siti (ogni sito ne ha bisogno).

  - Quali sono le dimensioni dei gateway? La risposta dipende dal numero di utenti nel sito e dal carico di traffico.

  - Dove devono essere ubicati i gateway? La risposta dipende in parte dalla topologia e in parte dalla distribuzione geografica dell'organizzazione.

Dovresti anche prendere in considerazione le opzioni della topologia del gateway (per informazioni dettagliate, Vedi topologie del gateway più avanti in questo argomento).

<div>

## <a name="mn-trunk-support"></a>Supporto di M:N trunk

I Mediation Server possono instradare le chiamate attraverso più gateway, Session Border Controller (SBCs) forniti da provider di servizi di telefonia Internet o una combinazione dei due. Inoltre, più server di mediazione nel pool possono interagire con più gateway. La route logica definita tra un Mediation Server e un gateway viene chiamata *trunk*. Quando un utente interno inserisce una chiamata PSTN, la logica di routing in uscita nel pool Front-End sceglie quale trunk per instradare oltre tutte le possibili combinazioni che potrebbero essere disponibili per il routing di quella particolare chiamata. Con il bilanciamento del carico DNS, se una chiamata non riesce a raggiungere un gateway a causa di un problema con un determinato Mediation Server nel pool, la chiamata verrà riprovata in un server di mediazione alternativo nel pool.

Per informazioni dettagliate sulla pianificazione di più gateway, vedere [Trunk M:N in Lync Server 2013](lync-server-2013-m-n-trunk.md).

Per informazioni dettagliate sugli altri miglioramenti del routing in uscita, vedere [route vocali in Lync Server 2013](lync-server-2013-voice-routes.md).

</div>

<div>

## <a name="gateway-topologies"></a>Topologie del gateway

Quando si considerano le domande fondamentali della distribuzione di gateway, eseguire le operazioni seguenti:

1.  Contare i siti in cui si vuole specificare la connettività PSTN tramite VoIP aziendale.

2.  Stimare il traffico in ogni sito (numero di utenti e numero medio di chiamate per ora per utente).

3.  Distribuire uno o più gateway in ogni sito per gestire il traffico previsto.

La topologia del gateway distribuito risultante è illustrata nella figura seguente.

**Topologia del gateway distribuito**

Diagramma(images/Gg398899.f0f65a0b-a462-491a-878b-4d4bf0a96f6d(OCS.15).jpg "topologia") del ![gateway distribuito]

Con questa topologia, le chiamate tra i dipendenti di ogni sito e tra i siti sono tutte instradate sulla Intranet. Le chiamate a PSTN vengono instradate tramite la rete IP aziendale verso i gateway più vicini alla posizione dei numeri di destinazione. Ma cosa succede se l'organizzazione supporta decine o centinaia o anche migliaia di siti distribuiti in uno o più continenti, come fanno molti istituti finanziari e altre imprese di grandi dimensioni? In questi casi, la distribuzione di un gateway separato in ogni sito non è pratica.

Per risolvere questo problema, molte aziende di grandi dimensioni preferiscono distribuire uno o più siti centrali di telefonia di grandi dimensioni, come illustrato nella figura seguente.

**Topologia del sito centrale di telefonia**

(images/Gg398899.927f4808-bf74-405a-be20-2cd9cd87af6d(OCS.15).jpg "Topologia gateway centro dati") ![topologia gateway centro dati]

In questa topologia, diversi gateway di grandi dimensioni sufficienti per supportare il caricamento previsto dell'utente vengono distribuiti in ogni sito centrale. Tutte le chiamate agli utenti dell'organizzazione vengono inoltrate dal provider di servizi telefonici della società a un sito centrale. La logica di routing nel sito centrale determina se la chiamata deve essere instradata tramite Intranet o PSTN.

</div>

<div>

## <a name="gateway-location"></a>Posizione del gateway

La posizione del gateway può anche determinare i tipi di gateway scelti e il modo in cui vengono configurati. Esistono decine di protocolli PSTN, nessuno dei quali è uno standard mondiale. Se tutti i gateway si trovano in un singolo paese/area geografica, questo non è un problema, ma se si individuano i gateway in più paesi/aree geografiche, ognuno deve essere configurato in base agli standard PSTN di tale paese/area geografica. Inoltre, i gateway certificati per l'operazione, ad esempio Canada, potrebbero non essere certificati in India, Brasile o Unione europea.

</div>

<div>

## <a name="gateway-size-and-number"></a>Dimensioni e numero del gateway

Gateway PSTN che la maggior parte delle organizzazioni valuterà la distribuzione di intervalli di dimensioni da 2 a fino a un massimo di 960 porte. (Ci sono anche gateway più grandi, ma questi sono usati principalmente dai provider di servizi telefonici). Per valutare il numero di porte richieste dall'organizzazione, usare le linee guida seguenti:

  - Le organizzazioni con utilizzo della telefonia leggera (una chiamata PSTN per utente per ora) devono allocare una sola porta per ogni 15 utenti. Se ad esempio sono presenti 20 utenti, sarà necessario un gateway con due porte.

  - Le organizzazioni con un utilizzo moderato della telefonia (due chiamate PSTN per utente per ora) devono allocare una sola porta per ogni 10 utenti. Ad esempio, se si hanno 100 utenti, è necessario un totale di 10 porte allocate tra uno o più gateway.

  - Le organizzazioni con uso di telefonia pesante (tre o più chiamate PSTN per utente per ora) devono allocare una porta per ogni cinque utenti. Ad esempio, se si hanno 47.000 utenti, sarà necessario un totale di 9.400 porte allocate tra almeno 10 gateway di grandi dimensioni.

  - Le porte aggiuntive possono essere acquisite Man mano che aumenta il numero di utenti o la quantità di traffico nell'organizzazione.

Per qualsiasi numero di utenti che è necessario supportare, è possibile scegliere di distribuire meno, gateway più grandi o quelli più piccoli. Di norma, è consigliabile un minimo di due gateway per un'organizzazione per mantenere la disponibilità se un gateway non riesce.

Ogni gateway PSTN distribuito deve avere almeno un Mediation Server corrispondente.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

