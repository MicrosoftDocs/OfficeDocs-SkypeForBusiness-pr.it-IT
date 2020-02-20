---
title: 'Lync Server 2013: caratteristiche e funzionalità per dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a001a6fb76a0612f7f650a31de5cf788a7f69327
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149585"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a>Funzionalità e funzionalità per dispositivi mobili in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2013-02-19_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

La funzionalità di mobilità introdotta negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 supporta la funzionalità Lync 2010 mobile e Lync 2013 Mobile Clients. Quando si distribuisce il servizio di mobilità di Lync Server 2013, gli utenti possono utilizzare i dispositivi mobili Apple iOS, Android e Windows Phone o Nokia Symbian per eseguire attività quali l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza. I dispositivi mobili inoltre supportano alcune funzionalità di VoIP aziendale, tra cui la possibilità di partecipare a una conferenza mediante clic del mouse, la chiamata tramite ufficio, il numero unico, la segreteria telefonica e le chiamate senza risposta. Nuove funzionalità introdotte negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 includono funzionalità Voice over IP (VoIP) e video (H. 264) per la riunione dei partecipanti.

La funzionalità di mobilità introdotta negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 supporta la funzionalità client per dispositivi mobili Lync 2013. Gli aggiornamenti cumulativi per Lync Server 2013: February 2013 install Unified Communications Web API, o UCWA. UCWA è il componente utilizzato per i client mobili di Lync 2013. In Lync Server 2013, MCX viene utilizzato per i client mobili di Lync 2010. Aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 introdurre UCWA come nuovo punto di ingresso per i servizi per dispositivi mobili. Lync Server 2013 implementa contemporaneamente il servizio per dispositivi mobili (MCX), introdotto negli aggiornamenti cumulativi per Lync Server 2010: novembre 2011 e fornisce il supporto per Lync 2010 mobile. Quando si distribuiscono gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013, gli utenti possono utilizzare i dispositivi mobili Apple iOS, Android e Windows Phone supportati per eseguire le attività seguenti:

<div>


> [!IMPORTANT]  
> Le funzionalità supportate dal servizio per dispositivi mobili dagli aggiornamenti cumulativi per Lync Server 2010: novembre 2011 sono note con (MCX). Tutte le funzionalità elencate sono supportate da UCWA, introdotte negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.



</div>

  - Inviare e ricevere messaggi istantanei (MCX)

  - Visualizzazione presenza (MCX)

  - Visualizza contatti (MCX)

  - Fare clic per partecipare a una conferenza (MCX)

  - Chiamata tramite lavoro (MCX)

  - Portata numeri singola (MCX)

  - Segreteria telefonica (MCX)

  - Notifica di chiamata senza risposta (MCX)

  - VoIP (Voice over IP)

  - Video partecipante (H. 264)

<div>


> [!NOTE]  
> Lync 2010 Mobile ha fornito un client per i dispositivi Nokia Symbian. Lync 2013 mobile non avrà un client per dispositivi basati su Nokia Symbian.



</div>

Gli utenti di Apple iPad avranno accesso a funzionalità avanzate. Dopo aver partecipato a una riunione tramite la chiamata audio, un utente iPad sarà in grado di visualizzare le presentazioni di Microsoft PowerPoint caricate all'interno di una riunione, condividere applicazioni e desktop, visualizzare l'elenco dei partecipanti alla riunione e ricevere notifiche di altri tipi di contenuto. che vengono condivisi all'interno della riunione.

<div>


> [!TIP]  
> Con il numero unico, un utente riceve sul telefono cellulare le chiamate effettuate al suo numero dell'ufficio. Con la chiamata tramite il lavoro, l'utente inserisce una chiamata in uscita dal client per dispositivi mobili Lync utilizzando un numero di telefono di lavoro invece del numero di cellulare. Con accesso esterno, il client invia una richiesta a MCX o UCWA (in base alla versione Lync mobile) per effettuare la chiamata. Il server perciò avvia la chiamata e quindi richiama l'utente sul cellulare. Quando l'utente risponde, il server completa la chiamata componendo il numero dell'altra parte. Mediante la chiamata tramite ufficio, gli utenti possono mantenere la loro identità di lavoro durante una chiamata, pertanto il destinatario non vedrà il numero di cellulare del chiamante e a quest'ultimo non verranno addebitati i costi della chiamata in uscita.



</div>

<div>


> [!NOTE]  
> Non tutte le funzionalità hanno esattamente lo stesso comportamento su tutti i dispositivi mobili. Per informazioni dettagliate sulle funzionalità supportate nei dispositivi mobili, vedere le tabelle di confronto dei <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A>client mobili in. Per informazioni dettagliate sui dispositivi e i sistemi operativi supportati, vedere gli argomenti relativi ai requisiti in <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for Mobile Clients in Lync Server 2013</A>.



</div>

Quando si utilizza la funzionalità di individuazione automatica di Lync Server 2013, le applicazioni per dispositivi mobili possono individuare automaticamente i servizi Web di Lync Server 2013 senza richiedere agli utenti di immettere manualmente gli URL nelle impostazioni dei dispositivi. Tale immissione manuale degli URL è comunque supportata, principalmente per la risoluzione dei problemi.

<div>


> [!IMPORTANT]  
> MCX e UCWA sono servizi gratuiti ed entrambi sono distribuiti per supportare i client mobili Lync 2010 mobile e Lync 2013. Lync 2013 mobile non sarà in grado di accedere alle distribuzioni di Lync Server 2010. Lync 2010 mobile e Lync 2013 mobile saranno in grado di utilizzare una distribuzione di Lync Server 2013 con gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 applicato.



</div>

La funzionalità per dispositivi mobili inoltre supporta le *notifiche push* per i dispositivi mobili che non supportano le applicazioni eseguite in background. Una notifica push è una notifica inviata a un dispositivo mobile relativamente a un evento che si verifica mentre un'applicazione per dispositivi mobili non è attiva. Ad esempio, un invito a messaggistica istantanea mancante può comportare una notifica push.

MCX, UCWA, il servizio di individuazione automatica e il supporto per le notifiche push sono disponibili in Lync Server 2013. Le funzionalità e le funzionalità del client aggiornate e l'utilizzo di UCWA come punto di ingresso per dispositivi mobili sono stati introdotti negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.

</div>

<span> </span>

</div>

</div>

</div>

