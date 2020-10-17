---
title: Distribuzione del carico per le conferenze di Lync Server 2013
description: Distribuzione del carico per le conferenze di Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Conferencing load distribution
ms:assetid: 5901a076-1b6f-4720-8837-95fc7f3c37f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204922(v=OCS.15)
ms:contentKeyID: 48184233
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 28897b26d7351bf0ea577e2678d916aec6d15647
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48557012"
---
# <a name="conferencing-load-distribution-in-lync-server-2013"></a>Distribuzione del carico per le conferenze in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

A differenza di altre soluzioni per conferenze dedicate, Lync Server Architecture è un modello di hardware condiviso. Questo significa che lo stesso hardware viene condiviso da molti componenti software, ognuno dei quali supporta tipi diversi di comunicazione in tempo reale. Ciascun tipo di comunicazione in tempo reale impone un carico specifico ai server. Ad esempio, il front end server può eseguire i componenti di routing SIP (Session Initiation Protocol), le applicazioni Web (come la ricerca rubrica), il servizio Web Conferencing, il servizio A/V Conferencing, le applicazioni VoIP aziendale, ad esempio l'applicazione Operatore Conferenza e Response Group, e Mediation Server. Un set di database sul front end Server fornisce anche l'archiviazione e l'elaborazione per i dati relativi a utenti, contatti, presenza, conferenze e routing vocale. Con la condivisione dell'hardware i componenti, i servizi e i processi sono in competizione per le risorse di CPU e memoria, e quindi i carichi di lavoro non correlati alle conferenze influiscono in modo diretto sulla scalabilità dei server.

Rispetto ad altre soluzioni per le conferenze basate su porta hardware, Lync Server Conferencing Architecture è un modello senza prenotazione. Quando un utente pianifica una riunione, Lync Server crea un record nel database delle conferenze, in cui vengono archiviati i dati per le conferenze, ma non riserva le risorse hardware per la riunione pianificata in anticipo. Al contrario, Lync Server dispone di una logica di bilanciamento del carico incorporata per allocare dinamicamente le risorse di conferenza nei front end server in modo da distribuire i carichi equamente in tutti i Front End Server nel pool. Questo sistema esegue il provisioning e usa le risorse hardware in modo efficiente, ma rende difficile supportare le riunioni di dimensioni molto grandi (soprattutto se non è stata eseguita una pianificazione accurata). Ad esempio, quando un pool di Lync Server 2013 è in esecuzione vicino alla capacità massima, ogni Front End Server può ospitare circa 125 riunioni di medie dimensioni. L'aggiunta di un'altra riunione di piccole dimensioni non è un problema, ma l'aggiunta di una riunione per gli utenti di 1000 potrebbe essere un problema perché i front end server probabilmente non sarebbero in grado di supportare una riunione di grandi dimensioni contemporaneamente alle altre riunioni di 125.

</div>

<span> </span>

</div>

</div>

</div>

