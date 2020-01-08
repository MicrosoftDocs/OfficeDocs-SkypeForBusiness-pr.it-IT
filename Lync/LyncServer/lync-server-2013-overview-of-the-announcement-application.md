---
title: "Lync Server 2013: Panoramica dell'applicazione di annunci"
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0e9cedddf6dfdf714bb3d0eef0e0cd01063b89f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40982118"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a>Panoramica dell'applicazione di annuncio in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-13_

Quando si distribuisce l'applicazione di annuncio, è necessario configurare una tabella dei numeri non assegnati che determina l'azione da eseguire quando un utente compone un numero non assegnato. La tabella numero non assegnati contiene gli intervalli di numeri di telefono validi per l'organizzazione e specifica l'applicazione di un annuncio che gestisce ogni intervallo. Quando un chiamante compone un numero di telefono valido per l'organizzazione ma non viene assegnato a nessuno, Lync Server cerca il numero nella tabella di routing dei numeri non assegnati, identifica l'intervallo in cui il numero rientra e instrada la chiamata all'annuncio. applicazione specificata per tale intervallo. L'applicazione di annuncio risponde alla chiamata e riproduce un messaggio audio (se è stato configurato per farlo) e quindi disconnette la chiamata o la trasferisce a una destinazione predeterminata, ad esempio a un operatore. Puoi usare i cmdlet di Lync Server Management Shell per configurare più messaggi audio o per trasferire destinazioni.

La configurazione della tabella dei numeri non assegnati dipende dall'utilizzo previsto di questa. Se si hanno numeri specifici che non sono più in uso e si vogliono riprodurre i messaggi personalizzati per ogni numero, è possibile immettere i numeri specifici nella tabella dei numeri non assegnati. Se ad esempio è stato modificato il numero per il servizio di assistenza clienti, è possibile immettere il vecchio numero di servizio clienti e associarlo a un annuncio che fornisce il nuovo numero. Se si vuole riprodurre un messaggio generale a chiunque chiami un numero non assegnato, ad esempio per i dipendenti che hanno lasciato l'organizzazione, è possibile immettere gli intervalli per tutte le estensioni valide dell'organizzazione. La tabella numeri non assegnati viene richiamata ogni volta che il chiamante compone un numero che non è attualmente assegnato.

In Lync Server 2013 l'applicazione annuncio viene installata automaticamente con l'applicazione Response Group. Le applicazioni per l'annuncio e il gruppo di risposta sono componenti standard di una distribuzione di VoIP aziendale: quando si distribuisce VoIP aziendale, entrambe le applicazioni vengono distribuite automaticamente.

</div>

<span> </span>

</div>

</div>

</div>

