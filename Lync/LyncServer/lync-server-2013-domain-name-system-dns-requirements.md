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
ms.openlocfilehash: 13fcb074ea5ce90bbe7097bf5c2f1f975de809c8
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42214663"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="domain-name-system-dns-requirements-for-lync-server-2013"></a>Requisiti DNS (Domain Name System) per Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-06-18_

Per distribuire Lync Server, è necessario creare record DNS (Domain Name System) che consentono l'individuazione di client e server e, facoltativamente, il supporto per l'accesso automatico dei client, se l'organizzazione vuole supportarla.

Lync Server utilizza DNS nei modi seguenti:

  - Per individuare i pool o i server interni per le comunicazioni tra server.

  - Per consentire ai client di individuare il pool Front end o il server Standard Edition utilizzato per varie transazioni SIP.

  - Per consentire ai dispositivi per comunicazioni unificate non connessi di individuare il pool Front end o il server Standard Edition che esegue il servizio Web aggiornamento dispositivi, ottenere gli aggiornamenti e inviare i registri.

  - Per consentire ai server e ai client esterni di connettersi ai server perimetrali o al proxy inverso HTTP per i servizi di messaggistica istantanea o di conferenza.

  - Consentire ai dispositivi UC esterni di connettersi al servizio Web aggiornamento dispositivi tramite i server perimetrali o il proxy inverso HTTP e ottenere gli aggiornamenti.

  - Per consentire ai client mobili di individuare automaticamente le risorse dei servizi Web senza richiedere agli utenti di immettere manualmente gli URL nelle impostazioni dei dispositivi.

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Determinare i requisiti DNS per Lync Server 2013](lync-server-2013-determine-dns-requirements.md)

  - [Requisiti DNS per i pool Front end in Lync Server 2013](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [Requisiti DNS per i server Standard Edition in Lync Server 2013](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [Requisiti DNS per gli URL semplici in Lync Server 2013](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [Requisiti DNS per l'accesso automatico dei client in Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [Requisiti DNS per i dispositivi mobili con Lync Server 2013](lync-server-2013-dns-requirements-for-mobility.md)

  - [Bilanciamento del carico DNS in Lync Server 2013](lync-server-2013-dns-load-balancing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

