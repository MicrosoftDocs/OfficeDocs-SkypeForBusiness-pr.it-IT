---
title: 'Lync Server 2013: Caratteristiche e funzionalità per dispositivi mobili'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e47a37acd45ed577b9ad730de39c79d4113c8f0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40980749"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a>Caratteristiche e funzionalità per dispositivi mobili in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2013-02-19_

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

La funzionalità mobilità introdotta negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 supporta la funzionalità Lync 2010 mobile e Lync 2013 per i client mobili. Quando si distribuisce il servizio di mobilità di Lync Server 2013, gli utenti possono usare i dispositivi mobili Apple iOS, Android e Windows Phone o Nokia Symbian per eseguire attività come l'invio e la ricezione di messaggi istantanei, la visualizzazione dei contatti e la visualizzazione della presenza. I dispositivi mobili supportano inoltre alcune funzionalità VoIP aziendale, ad esempio fare clic per partecipare a una conferenza, chiamare tramite lavoro, raggiungere un numero singolo, la segreteria telefonica e le chiamate perse. Le nuove funzionalità introdotte negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 includono funzionalità VoIP (Voice over IP) e video (H. 264) per i partecipanti alla riunione.

La funzionalità mobilità introdotta negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 supporta la funzionalità client per dispositivi mobili Lync 2013. Gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 installare Unified Communications Web API o UCWA. UCWA è il componente usato per i client mobili Lync 2013. In Lync Server 2013 viene usato MCX per i client mobili di Lync 2010. Aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 Introduzione a UCWA come nuovo punto di ingresso per i servizi di mobilità. Lync Server 2013 implementa contemporaneamente il servizio di mobilità (MCX), introdotto negli aggiornamenti cumulativi per Lync Server 2010: novembre 2011 e fornisce il supporto per Lync 2010 mobile. Quando si distribuiscono gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013, gli utenti possono usare i dispositivi mobili supportati da Apple iOS, Android e Windows Phone per eseguire attività quali:

<div>


> [!IMPORTANT]  
> Funzionalità supportate dal servizio di mobilità degli aggiornamenti cumulativi per Lync Server 2010: novembre 2011 sono notati con (MCX). Tutte le caratteristiche elencate sono supportate da UCWA, introdotte negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.



</div>

  - Inviare e ricevere messaggi istantanei (MCX)

  - Visualizzazione presenza (MCX)

  - Visualizzare i contatti (MCX)

  - Fare clic per partecipare a una conferenza (MCX)

  - Chiamata tramite lavoro (MCX)

  - Portata numero singolo (MCX)

  - Segreteria telefonica (MCX)

  - Notifica delle chiamate perse (MCX)

  - Voice over IP (VoIP)

  - Video partecipanti (H. 264)

<div>


> [!NOTE]  
> Lync 2010 Mobile ha fornito un client per dispositivi Nokia Symbian. Lync 2013 mobile non avrà un client per dispositivi Nokia basati su Symbian.



</div>

Gli utenti di Apple iPad avranno accesso a funzionalità avanzate. Dopo aver partecipato a una riunione usando la chiamata audio, un utente di iPad sarà in grado di visualizzare le presentazioni di Microsoft PowerPoint in una riunione, condividere applicazioni e desktop, visualizzare l'elenco dei partecipanti alla riunione e ricevere le notifiche di altri tipi di contenuto. che vengono condivisi all'interno della riunione.

<div>


> [!TIP]  
> Con un numero a portata di mano, un utente riceve le chiamate su un telefono cellulare che sono state chiamate al numero di lavoro. Con la chiamata tramite il lavoro, l'utente inserisce una chiamata in uscita dal client mobile di Lync usando un numero di telefono dell'ufficio anziché il numero di cellulare. Con chiamata in uscita, il client invia una richiesta a MCX o UCWA (in base alla versione per dispositivi mobili Lync) per effettuare la chiamata. Il server avvia la chiamata e quindi richiama l'utente sul telefono cellulare. Quando l'utente risponde, il server completa la chiamata componendo l'altra parte. Usando la chiamata tramite il lavoro, gli utenti possono mantenere l'identità del lavoro durante una chiamata, il che significa che il destinatario della chiamata non vede il numero di cellulare del chiamante e il chiamante evita l'incorrere in spese di chiamata in uscita.



</div>

<div>


> [!NOTE]  
> Non tutte le caratteristiche funzionano esattamente come in tutti i dispositivi mobili. Per informazioni dettagliate sulle caratteristiche supportate nei dispositivi mobili, vedere le tabelle di <A href="http://go.microsoft.com/fwlink/p/?linkid=234777">http://go.microsoft.com/fwlink/p/?LinkId=234777</A>confronto tra client mobili. Per informazioni dettagliate sui dispositivi e i sistemi operativi supportati, vedere gli argomenti relativi ai requisiti in <A href="lync-server-2013-planning-for-mobile-clients.md">pianificazione per i client mobili in Lync Server 2013</A>.



</div>

Quando si usa la funzionalità di individuazione automatica di Lync Server 2013, le applicazioni per dispositivi mobili possono individuare automaticamente i servizi Web di Lync Server 2013 senza richiedere agli utenti di immettere manualmente gli URL nelle impostazioni del dispositivo. È anche supportata l'immissione manuale di URL nelle impostazioni dei dispositivi mobili, principalmente per scopi di risoluzione.

<div>


> [!IMPORTANT]  
> MCX e UCWA sono servizi gratuiti ed entrambi sono distribuiti per supportare i client mobili Lync 2010 per dispositivi mobili e Lync 2013. Lync 2013 mobile non sarà in grado di accedere alle distribuzioni di Lync Server 2010. Lync 2010 mobile e Lync 2013 mobile saranno in grado di usare una distribuzione di Lync Server 2013 con gli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013 applicato.



</div>

La funzionalità mobilità supporta anche le *notifiche push* per i dispositivi mobili che non supportano le applicazioni in uso in background. Una notifica push è una notifica inviata a un dispositivo mobile su un evento che si verifica mentre un'applicazione per dispositivi mobili è inattiva. Ad esempio, un invito alla messaggistica istantanea senza risposta può causare una notifica push.

MCX, UCWA, il servizio di individuazione automatica e il supporto per le notifiche push sono disponibili in Lync Server 2013. Le caratteristiche del client aggiornate, le funzionalità e l'uso di UCWA come punto di ingresso per la mobilità vengono introdotte negli aggiornamenti cumulativi per Lync Server 2013: febbraio 2013.

</div>

<span> </span>

</div>

</div>

</div>

