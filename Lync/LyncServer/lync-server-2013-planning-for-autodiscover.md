---
title: "Lync Server 2013: pianificazione dell'individuazione automatica"
description: "Lync Server 2013: pianificazione dell'individuazione automatica."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e28a6a3a317f063151eadde7c5de51b02a46b482
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544632"
---
# <a name="planning-for-autodiscover-in-lync-server-2013"></a>Pianificazione dell'individuazione automatica in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-16_

L'individuazione automatica è stata introdotta per Lync Server nell'aggiornamento cumulativo per Lync Server 2010: novembre 2011. Lo scopo principale di questa implementazione iniziale dell'individuazione automatica è stato quello di fornire un mezzo per Lync mobile per individuare il servizio per dispositivi mobili (MCX). Il servizio di individuazione automatica in Lync Server 2013 è ora un servizio utilizzato da tutti i client per individuare i servizi server e utente. Il servizio di individuazione automatica di Microsoft Lync Server 2013 viene eseguito su Director e front end server.

<div>


> [!TIP]  
> Per informazioni più tecniche sull'individuazione automatica e su ciò che viene comunicato ai client, vedere <A href="lync-server-2013-understanding-autodiscover.md">Understanding Autodiscover in Lync Server 2013</A>.<BR>La mobilità è ancora uno scenario distinto e i servizi per dispositivi mobili richiedono comunque una pianificazione speciale. Per ulteriori informazioni, vedere <A href="lync-server-2013-planning-for-mobility.md">Planning for Mobility in Lync Server 2013</A>.



</div>

Quando la funzione di individuazione automatica è stata introdotta in Lync Server 2010, sono stati necessari compromessi per implementare un servizio che richiedeva potenziali modifiche del certificato alle distribuzioni esistenti del server. L'individuazione automatica può essere utilizzata su porta TCP 443 per HTTPS o su porta TCP 80 per HTTP. Se è stata presa la decisione di utilizzare HTTPS, i certificati su proxy inversi, direttori e front end server devono essere riemessi per soddisfare i `lyncdiscover.<domain>` `lyncdiscoverinternal.<domain>` record DNS e necessari. Se si decide di utilizzare il protocollo HTTP, la ristampa dei certificati potrebbe essere evitata utilizzando record CNAME DNS (o alias) per l'utilizzo dei nomi esistenti nei certificati. L'utilizzo di HTTP significa che le comunicazioni iniziali non sono state crittografate.

Poiché Lync Server 2013 utilizza l'individuazione automatica per tutti i client, lo scenario principale consiste nell'utilizzare solo HTTPS e creare certificati con lyncdiscover.\<domain\> come parte della configurazione dei proxy inversi, direttori e front end server. Se si sta implementando l'individuazione automatica in una distribuzione aggiornata da Lync Server 2010, è consigliabile utilizzare HTTP per evitare di riemettere certificati. Le linee guida per entrambi gli scenari sono disponibili nelle sezioni seguenti.

<div>


> [!IMPORTANT]  
> L'elenco dei nomi alternativi del soggetto nei certificati utilizzati dalla regola di pubblicazione dei servizi Web esterni deve contenere un <EM>lyncdiscover. &lt; voce &gt; SipDomain</EM> per ogni dominio SIP all'interno dell'organizzazione. Per informazioni dettagliate sulle voci dei nomi alternativi del soggetto necessarie per i direttori, i Front End Server e i proxy inversi, vedere <A href="lync-server-2013-certificate-summary-autodiscover.md">Certificate Summary-Autodiscover in Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Riepilogo del certificato-individuazione automatica in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)

  - [Riepilogo delle porte-individuazione automatica in Lync Server 2013](lync-server-2013-port-summary-autodiscover.md)

  - [Riepilogo DNS-individuazione automatica in Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md)

  - [Ambiente ibrido e Split-Domain-individuazione automatica in Lync Server 2013](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

