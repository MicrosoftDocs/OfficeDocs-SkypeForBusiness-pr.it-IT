---
title: "Lync Server 2013: pianificazione per l'individuazione automatica"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Autodiscover
ms:assetid: 51f1ff94-1d64-4e6d-a878-b86fa07edc2d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945628(v=OCS.15)
ms:contentKeyID: 51541474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0a1d0ce7a775bc73c5f3afa10d1f9c148395b0eb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40978315"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-autodiscover-in-lync-server-2013"></a>Pianificazione per l'individuazione automatica in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-16_

L'individuazione automatica è stata introdotta per Lync Server nell'aggiornamento cumulativo per Lync Server 2010: novembre 2011. Lo scopo principale di questa implementazione iniziale di individuazione automatica consiste nel creare un mezzo per Lync mobile per individuare il servizio di mobilità (MCX). Il servizio di individuazione automatica in Lync Server 2013 è ora un servizio usato da tutti i client per individuare i servizi server e utente. Il servizio di individuazione automatica di Microsoft Lync Server 2013 viene eseguito su direttori e server front-end.

<div>


> [!TIP]  
> Per una maggiore comprensione tecnica dell'individuazione automatica e delle comunicazioni ai client, vedere informazioni sull' <A href="lync-server-2013-understanding-autodiscover.md">individuazione automatica in Lync Server 2013</A>.<BR>La mobilità è ancora uno scenario distinto e i servizi di mobilità richiedono comunque una pianificazione speciale. Per ulteriori informazioni, vedere <A href="lync-server-2013-planning-for-mobility.md">pianificazione della mobilità in Lync Server 2013</A>.



</div>

Quando l'individuazione automatica è stata introdotta in Lync Server 2010, sono stati compromessi da eseguire per implementare un servizio che richiedeva potenziali modifiche al certificato alle distribuzioni del server esistenti. L'individuazione automatica può essere usata tramite la porta TCP 443 per HTTPS o tramite la porta TCP 80 per HTTP. Se è stata presa la decisione di usare HTTPS, i certificati su proxy inverso, direttori e server front-end devono essere ristampati per contenere i record necessari `lyncdiscover.<domain>` e `lyncdiscoverinternal.<domain>` DNS. Se si decide di usare HTTP, la ristampa dei certificati può essere evitata usando i record CNAME DNS (o alias) per usare i nomi esistenti nei certificati. L'uso di HTTP significava che le comunicazioni iniziali non erano crittografate.

Poiché Lync Server 2013 usa l'individuazione automatica per tutti i client, lo scenario principale è l'uso esclusivo di HTTPS e la creazione di certificati con lyncdiscover. \<dominio\> come parte della configurazione di proxy inverso, direttori e server front-end. Se si implementa l'individuazione automatica in una distribuzione aggiornata da Lync Server 2010, è consigliabile usare HTTP per evitare di riemettere certificati. Le linee guida per entrambi gli scenari sono disponibili nelle sezioni seguenti.

<div>


> [!IMPORTANT]  
> L'elenco di nomi alternativi oggetto nei certificati usati dalla regola di pubblicazione dei servizi Web esterni deve contenere un <EM>lyncdiscover.&lt; SipDomain&gt; </EM> voce per ogni dominio SIP all'interno dell'organizzazione. Per informazioni dettagliate sulle voci di nome alternative oggetto necessarie per direttori, server front-end e reverse proxy, vedere <A href="lync-server-2013-certificate-summary-autodiscover.md">Riepilogo dei certificati-individuazione automatica in Lync Server 2013</A>.



</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Riepilogo del certificato-individuazione automatica in Lync Server 2013](lync-server-2013-certificate-summary-autodiscover.md)

  - [Riepilogo della porta-individuazione automatica in Lync Server 2013](lync-server-2013-port-summary-autodiscover.md)

  - [Riepilogo DNS-individuazione automatica in Lync Server 2013](lync-server-2013-dns-summary-autodiscover.md)

  - [Hybrid e Split-Domain-individuazione automatica in Lync Server 2013](lync-server-2013-hybrid-and-split-domain-autodiscover.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

