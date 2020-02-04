---
title: 'Lync Server 2013: requisiti DNS (Domain Name System)'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Domain Name System (DNS) requirements
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398386(v=OCS.15)
ms:contentKeyID: 48184194
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2eddf86c881875ebbe08fddd6ffa85403dda6b60
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739796"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a>Requisiti DNS (Domain Name System) per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-06-18_

Per distribuire Lync Server, è necessario creare record DNS (Domain Name System) che consentano l'individuazione di client e server e, facoltativamente, il supporto per l'accesso automatico al client se l'organizzazione vuole supportarlo.

Lync Server usa il DNS nei modi seguenti:

  - Per individuare i server o i pool interni per le comunicazioni da server a server.

  - Per consentire ai client di individuare il pool Front-end o il server Standard Edition usato per varie transazioni SIP.

  - Per consentire ai dispositivi Unified Communications (UC) che non hanno eseguito l'accesso di individuare il pool Front-end o il server Standard Edition che esegue il servizio Web Update Device, ottenere gli aggiornamenti e inviare i log.

  - Per consentire ai server e ai client esterni di connettersi ai server Edge o al proxy inverso HTTP per la messaggistica istantanea o i servizi di conferenza.

  - Per consentire ai dispositivi UC esterni di connettersi al servizio Web Update per dispositivi tramite Edge Server o il proxy inverso HTTP e ottenere gli aggiornamenti.

  - Per consentire ai client mobili di individuare automaticamente le risorse dei servizi Web senza richiedere agli utenti di immettere manualmente gli URL nelle impostazioni del dispositivo.

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Determinare i requisiti di DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Requisiti DNS per i pool Front-end in Lync Server 2013](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [Requisiti DNS per i server Standard Edition in Lync Server 2013](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [Requisiti DNS per gli URL semplici in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Requisiti DNS per l'accesso automatico client in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [Requisiti DNS per la mobilità con Lync Server 2013](lync-server-2013-dns-requirements-for-mobility.md)

  - [Bilanciamento del carico DNS in Lync Server 2013](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

