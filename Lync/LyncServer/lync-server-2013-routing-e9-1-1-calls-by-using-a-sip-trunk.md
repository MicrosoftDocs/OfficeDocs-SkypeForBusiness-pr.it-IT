---
title: 'Lync Server 2013: routing delle chiamate al servizio E9-1-1 tramite un trunk SIP'
description: 'Lync Server 2013: routing delle chiamate al servizio E9-1-1 tramite un trunk SIP.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Routing E9-1-1 calls by using a SIP trunk
ms:assetid: 157753c3-fe74-4e2c-81da-ee06911d4cc2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204701(v=OCS.15)
ms:contentKeyID: 48183492
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9e45b2b3d33556a5ff97235345c7b538023a7449
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48571822"
---
# <a name="routing-e9-1-1-calls-by-using-a-sip-trunk-in-lync-server-2013"></a>Routing delle chiamate al servizio E9-1-1 tramite un trunk SIP in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-29_

L'utilizzo di un trunk SIP per la connessione a un provider di servizi E9-1-1 qualificato rappresenta un metodo per la distribuzione del servizio E9-1-1. Per informazioni dettagliate sull'utilizzo di un gateway ELIN per la connessione a un provider di servizi E9-1-1 Basato su rete PSTN (Public Switched Telephone Network), vedere [routing di chiamate E9-1-1 tramite un gateway ELIN in Lync Server 2013](lync-server-2013-routing-e9-1-1-calls-by-using-an-elin-gateway.md).

Nel diagramma seguente viene illustrato in che modo viene instradata una chiamata di emergenza da Lync Server al punto di risposta di sicurezza pubblica (PSAP) quando si utilizza un trunk SIP e un provider di servizi E9-1-1 qualificato.

**Routing delle chiamate al servizio E9-1-1 tramite un trunk SIP**

![Routing delle chiamate di emergenza da Lync Server a PSAP](images/JJ204701.0637a9d4-2ca7-438a-8ed0-19090a4b992d(OCS.15).jpg "Routing delle chiamate di emergenza da Lync Server a PSAP")

Quando viene effettuata una chiamata di emergenza da un client Lync Server compatibile:

1.  Un invito SIP che contiene la posizione, il numero di callback del chiamante e l'URL di notifica (facoltativo) e il numero di callback di conferenza vengono instradati a Lync Server.

2.  Lync Server corrisponde al numero di emergenza e instrada la chiamata (in base al valore di **utilizzo PSTN** definito nei criteri di percorso applicabili) a un Mediation Server e, da qui, tramite un trunk SIP al provider di servizi E9-1-1.

3.  Il provider di servizi E9-1-1 instrada la chiamata di emergenza al centro di raccolta delle chiamate di emergenza (PSAP, Public Safety Answering Point) appropriato in base alle informazioni sulla posizione fornite nella chiamata. Quando il client include nella chiamata di emergenza una posizione ERL (Emergency Response Location) convalidata, la chiamata viene instradata automaticamente dal provider al centro di raccolta delle chiamate di emergenza appropriato. Se la posizione è stata immessa manualmente dall'utente, il centro ECRC (Emergency Call Response Center) verifica innanzitutto verbalmente l'accuratezza della posizione con il chiamante prima di instradare la chiamata al centro di raccolta delle chiamate di emergenza.

4.  Se i criteri percorso sono stati configurati per le notifiche, uno o più agenti di sicurezza dell'organizzazione ricevono un messaggio istantaneo speciale di notifica di emergenza di Lync. Questo messaggio viene sempre visualizzato nelle schermate degli addetti alla sicurezza e contiene il nome, il numero di telefono, l'ora e il percorso del chiamante, consentendo al personale di sicurezza di rispondere rapidamente al chiamante di emergenza utilizzando un messaggio istantaneo o una voce.

5.  Se sono stati configurati criteri di percorso per il servizio di conferenza e il provider di servizi E9-1-1 lo supporta, un desk di sicurezza interno viene invitato a partecipare in conferenza alla chiamata con audio unidirezionale o bidirezionale.

6.  Se la chiamata viene interrotta prematuramente, il centro di raccolta delle chiamate di emergenza utilizza il numero di richiamata per contattare direttamente il chiamante.

</div>

<span> </span>

</div>

</div>

</div>

