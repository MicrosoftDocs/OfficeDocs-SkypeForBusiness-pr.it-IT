---
title: 'Lync Server 2013: convalidare le impostazioni di sistema del nome di dominio per il bilanciamento del carico'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Validate Domain Name System settings for load balancing
ms:assetid: 92858e1c-91a5-4303-9bb4-b182e7f9c78b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720920(v=OCS.15)
ms:contentKeyID: 63969625
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3cc1766ad11a5a6b7933d95b2c3e1182ff8ffc6a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/14/2020
ms.locfileid: "42007435"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a>Convalidare le impostazioni di sistema del nome di dominio per il bilanciamento del carico in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-05-02_

Per supportare il nome di dominio completo utilizzato dal bilanciamento del carico DNS, è necessario effettuare il provisioning di DNS per risolvere il nome di dominio completo del pool (ad esempio pool01.contoso.com) negli indirizzi IP di tutti i server del pool (ad esempio 192.168.1.1, 192.168.1.2 e così via). Includere solo gli indirizzi IP dei server attualmente distribuiti.

Inoltre, se si utilizza il bilanciamento del carico DNS per i pool di server perimetrali, sono necessarie le seguenti voci DNS:

  - Per il servizio Lync Server Access Edge, è necessario disporre di una voce per ogni server nel pool. Ogni voce deve risolvere il nome di dominio completo del servizio Lync Server Access Edge (ad esempio, sip.contoso.com) all'indirizzo IP del servizio Lync Server Access Edge in uno dei server perimetrali del pool.

  - Per il servizio Web Conferencing Edge di Lync Server, è necessario disporre di una voce per ogni server nel pool. Ogni voce deve risolvere il nome di dominio completo del servizio Web Conferencing Edge di Lync Server (ad esempio, webconf.contoso.com) nell'indirizzo IP del servizio Web Conferencing Edge di Lync Server in uno dei server perimetrali del pool.

  - Per Lync Server audio/video Edge service, è necessario disporre di una voce per ogni server nel pool. Ogni voce deve risolvere il nome di dominio completo di Lync Server audio/video Edge del servizio (ad esempio, av.contoso.com) per l'indirizzo IP del servizio Lync Server audio/video Edge su uno dei server perimetrali nel pool.

  - Se si desidera utilizzare il bilanciamento del carico DNS nell'interfaccia interna del pool di server perimetrali, è necessario aggiungere un record DNS, che consente di risolvere il nome di dominio completo interno del pool perimetrale nell'indirizzo IP di ognuno di essi del pool.

Per verificare che DNS restituisca i valori corretti per il bilanciamento del carico DNS, è necessario utilizzare lo strumento Nslookup. Per restituire tutti i valori di un record DNS con Nslookup, è necessario eseguire il comando:

`nslookup <FQDN >`

Eseguire questo comando per ogni nome di dominio completo utilizzato nella configurazione del bilanciamento del carico DNS per verificare che ogni set di record per il bilanciamento del carico DNS abbia restituito tutte le voci corrette.

</div>

<span> </span>

</div>

</div>

</div>

