---
title: 'Lync Server 2013: Routing delle chiamate di emergenza tramite un trunk SIP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Routing E9-1-1 calls by using a SIP trunk
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204701(v=OCS.15)
ms:contentKeyID: 48183492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c537b66883ab786bc28e3cc808874c0fcb79b92d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40977409"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a>Routing delle chiamate di emergenza tramite un trunk SIP in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-29_

L'uso di un trunk SIP per connettersi a un provider di servizi E9-1-1 qualificato è un modo in cui è possibile distribuire E9-1-1. Per informazioni dettagliate sull'uso di un gateway ELIN per la connessione a un provider di servizi E9-1-1 Basato su PSTN (Public Switched Telephone Network), vedere [routing delle chiamate di E9-1-1 tramite un gateway ELIN in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).

Il diagramma seguente mostra il modo in cui una chiamata di emergenza viene instradata da Lync Server al punto di PSAP (Public Safety Answering Point) quando si usa un trunk SIP e un provider di servizi E9-1-1 qualificato.

**Routing di chiamate E9-1-1 tramite trunk SIP**

![Routing delle chiamate di emergenza da Lync Server a PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "routing delle chiamate di emergenza da Lync Server a PSAP")

Quando una chiamata di emergenza viene inserita da un client Lync Server compatibile:

1.  Un invito SIP che contiene la posizione, il numero di callback del chiamante e l'URL di notifica (facoltativo) e il numero di callback di conferenza vengono instradati a Lync Server.

2.  Lync Server corrisponde al numero di emergenza e instrada la chiamata (in base al valore di **utilizzo PSTN** definito nel criterio di posizione applicabile) a un Mediation Server e da lì, tramite un trunk SIP al provider di servizi E9-1-1.

3.  Il provider di servizi E9-1-1 instrada la chiamata di emergenza alla PSAP corretta in base alla posizione fornita con la chiamata. Quando il client include un percorso di risposta di emergenza convalidato con la chiamata di emergenza, il provider instrada automaticamente la chiamata al PSAP appropriato. Se la posizione è stata immessa manualmente dall'utente, il centro risposte per le chiamate di emergenza (ECRC) verifica verbalmente la precisione della posizione con il chiamante prima di instradare la chiamata di emergenza al PSAP.

4.  Se sono stati configurati i criteri di posizione per le notifiche, uno o più agenti di sicurezza dell'organizzazione riceveranno un messaggio istantaneo speciale di notifica di emergenza Lync. Questo messaggio compare sempre nella schermata degli addetti alla sicurezza e contiene il nome, il numero di telefono, l'ora e la posizione del chiamante, che consente al personale di sicurezza di rispondere rapidamente al chiamante di emergenza usando un messaggio istantaneo o una voce.

5.  Se sono stati configurati i criteri di posizione per le conferenze ed è supportato dal provider di servizi E9-1-1, è possibile partecipare a una conferenza di sicurezza interna alla chiamata con audio unidirezionale o audio bidirezionale.

6.  Se la chiamata viene interrotta prematuramente, PSAP usa il numero di callback per contattare direttamente il chiamante.

</div>

<span> </span>

</div>

</div>

</div>

