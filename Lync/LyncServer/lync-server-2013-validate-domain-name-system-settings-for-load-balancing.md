---
title: 'Lync Server 2013: convalida delle impostazioni di sistema dei nomi di dominio per il bilanciamento del carico'
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
ms.openlocfilehash: 0178d179a9684cf07450cdee839af1c8c1ebc22d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41727526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="validate-domain-name-system-settings-for-load-balancing-in-lync-server-2013"></a>Convalidare le impostazioni di sistema dei nomi di dominio per il bilanciamento del carico in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-05-02_

Per supportare il nome di dominio completo usato dal bilanciamento del carico DNS, è necessario eseguire il provisioning del DNS per risolvere il nome di dominio completo del pool, ad esempio pool01.contoso.com, agli indirizzi IP di tutti i server del pool (ad es. 192.168.1.1, 192.168.1.2 e così via). Dovresti includere solo gli indirizzi IP dei server attualmente distribuiti.

Inoltre, se si usa il bilanciamento del carico DNS per i pool di bordi, sono necessarie le seguenti voci DNS:

  - Per il servizio Access Edge di Lync Server è necessario disporre di una voce per ogni server nel pool. Ogni voce deve risolvere il nome di dominio completo di Lync Server Access Edge service, ad esempio sip.contoso.com, all'indirizzo IP del servizio Access Edge di Lync Server in uno degli Edge Server del pool.

  - Per il servizio Web Conferencing Edge di Lync Server, è necessario avere una voce per ogni server nel pool. Ogni voce deve risolvere il nome di dominio completo di Lync Server Web Conferencing Edge Services, ad esempio webconf.contoso.com, all'indirizzo IP di Lync Server Web Conferencing Edge Services in uno degli Edge Server del pool.

  - Per il servizio Edge audio/video di Lync Server è necessario disporre di una voce per ogni server nel pool. Ogni voce deve risolvere il nome di dominio completo del servizio Edge audio/video di Lync Server, ad esempio av.contoso.com, all'indirizzo IP del servizio Edge audio/video di Lync Server in uno degli Edge Server del pool.

  - Se si vuole usare il bilanciamento del carico DNS nell'interfaccia interna del pool di Edge, è necessario aggiungere un record DNS, che risolve il nome di dominio completo interno del pool di Edge nell'indirizzo IP di ogni server nel pool.

Per verificare che il DNS stia restituendo i valori corretti per il bilanciamento del carico DNS, usare lo strumento Nslookup. Per restituire tutti i valori di un record DNS con Nslookup, eseguire il comando:

`nslookup <FQDN >`

Eseguire questo comando per ogni nome di dominio completo usato nella configurazione di bilanciamento del carico DNS per verificare che ogni set di record per il bilanciamento del carico DNS restituisca tutte le voci corrette.

</div>

<span> </span>

</div>

</div>

</div>

