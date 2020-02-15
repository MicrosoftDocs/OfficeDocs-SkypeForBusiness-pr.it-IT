---
title: 'Lync Server 2013: creare record DNS per i server proxy inversi'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create DNS records for reverse proxy servers
ms:assetid: b3513339-e49b-4665-80f1-b5a1c81a0e2e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg429719(v=OCS.15)
ms:contentKeyID: 48185181
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60cd3033ae06f3fd9f0fc4a7a1e881f08f2ee90f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035792"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-dns-records-for-reverse-proxy-servers-in-lync-server-2013"></a>Creare record DNS per i server proxy inversi in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-03-29_

Creare record DNS esterni che puntano all'interfaccia esterna pubblica di Microsoft Internet Security and Acceleration (ISA) Server 2006 SP1, Forefront Threat Management Gateway 2010 Server o Internet Information Server Application Request Routing, come descritto in [configure DNS for Edge support in Lync Server 2013](lync-server-2013-configure-dns-for-edge-support.md). Sono necessari record DNS per gli FQDN dei servizi Web esterni per ogni pool, il Director (o il pool di server Director) e ogni URL semplice.

Per la risoluzione dei client nel proxy inverso, è almeno necessario creare i record DNS seguenti:

  - Record host (A) che definiscono i servizi Web esterni pubblicati per gli amministratori e i pool di server Director (ad esempio, **webdirext.contoso.com**)

  - Record host (A) che definiscono i servizi Web esterni pubblicati per i servizi Web esterni ospitati in tutti i pool Front end e i ruoli del server Standard Edition (ad esempio, **webext.contoso.com**)

  - Record host (A) per gli URL semplici (ad esempio, **dialin.contoso.com** e **meet.contoso.com**)

  - Record host (A) per il record esterno di individuazione di Lync e fornisce anche il puntatore all'individuazione automatica per tutte le applicazioni Web, tra cui Lync Web App, utilità di pianificazione e mobilità (ad esempio, **lyncdiscover.contoso.com**)

  - Record host (A) per l'URL del server Office Web Apps (ad esempio **officewebapp01.contoso.com**)

Per informazioni dettagliate, vedere [DNS Summary-reverse proxy in Lync Server 2013](lync-server-2013-dns-summary-reverse-proxy.md).

</div>

<span> </span>

</div>

</div>

</div>

