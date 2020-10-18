---
title: "Lync Server 2013: Panoramica dell'applicazione annuncio"
description: "Lync Server 2013: Panoramica dell'applicazione annuncio."
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of the Announcement application
ms:assetid: 2abee804-2599-48bb-90b2-15df0bae5e20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204757(v=OCS.15)
ms:contentKeyID: 48183689
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 15e9834be5edc67777f258f8d041e134287a891a
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48577252"
---
# <a name="overview-of-the-announcement-application-in-lync-server-2013"></a>Panoramica dell'applicazione annuncio in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-13_

Quando si distribuisce l'applicazione annuncio, è necessario configurare una tabella dei numeri non assegnati che determina l'azione da eseguire quando un utente compone un numero non assegnato. La tabella numeri non assegnati contiene gli intervalli di numeri di telefono validi per l'organizzazione e specifica quale applicazione di annuncio gestisce ogni intervallo. Quando un chiamante compone un numero di telefono valido per l'organizzazione ma non è assegnato a nessuno, Lync Server cerca il numero nella tabella di routing dei numeri non assegnati, identifica l'intervallo in cui si trova il numero e instrada la chiamata all'applicazione annuncio specificata per tale intervallo. L'applicazione Annuncio risponde alla chiamata e riproduce un messaggio audio (se è stata configurata per farlo) e quindi disconnette la chiamata o la trasferisce in una destinazione predeterminata, ad esempio a un operatore. È possibile utilizzare i cmdlet di Lync Server Management Shell per configurare più messaggi audio o per trasferire le destinazioni.

Il modo in cui configurare la tabella dei numeri non assegnati dipende da come si desidera usarla. Se si dispone di numeri specifici non più in uso e si desidera riprodurre messaggi personalizzati per ogni numero, è possibile immettere tali numeri specifici nella tabella dei numeri non assegnati. Se, ad esempio, è stato modificato il numero del Service Desk clienti, è possibile immettere il vecchio numero del servizio clienti e associarlo a un annuncio che fornisce il nuovo numero. Se si desidera riprodurre un messaggio generale a chiunque chiami un numero non assegnato, ad esempio per dipendenti che non lavorano più nell'organizzazione, è possibile immettere intervalli per tutti gli interni validi dell'organizzazione. La tabella dei numeri non assegnati viene richiamata ogni volta che il chiamante compone un numero attualmente non assegnato.

In Lync Server 2013, l'applicazione annuncio viene automaticamente installata con l'applicazione Response Group. Le applicazioni annuncio e Response Group sono componenti standard di una distribuzione di VoIP aziendale: quando si distribuisce VoIP aziendale, entrambe le applicazioni vengono distribuite automaticamente.

</div>

<span> </span>

</div>

</div>

</div>

