---
title: Distribuzione del carico di conferenza di Lync Server 2013
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
ms.openlocfilehash: baa8230470fc765bbda7c3b2bf49e6962b3db22f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741526"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="conferencing-load-distribution-in-lync-server-2013"></a>Distribuzione del carico di conferenza in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-10-22_

A differenza di altre soluzioni di conferenza dedicate, l'architettura Lync Server è un modello di hardware condiviso. Questo significa che lo stesso hardware è condiviso da molti componenti software, ognuno dei quali supporta diverse comunicazioni in tempo reale. Ogni tipo di comunicazioni in tempo reale colloca carichi specifici nei server. Ad esempio, il server front-end può eseguire i componenti di routing SIP (Session Initiation Protocol), le applicazioni Web (ad esempio la ricerca di Rubrica), il servizio Web Conferencing, il servizio di conferenza A/V, le applicazioni VoIP aziendali (ad esempio, l'applicazione per i servizi di conferenza e l'applicazione di Response Group) e Mediation Server. Un set di database nel server front-end offre anche l'archiviazione e l'elaborazione di dati per utenti, contatti, presenza, conferenze e routing vocale. Con questa condivisione hardware, i componenti, i servizi e i processi competono per le risorse della CPU e della memoria, quindi i carichi di lavoro non Conferencing hanno un impatto diretto sulla scalabilità del server.

Rispetto ad altre soluzioni di conferenza basate su porta hardware, Lync Server Conferencing Architecture è un modello senza prenotazione. Quando un utente pianifica una riunione, Lync Server crea un record nel database dei servizi di conferenza, che archivia i dati di conferenza, ma non riserva le risorse hardware per la riunione pianificata prima del tempo. Lync Server include invece la logica di bilanciamento del carico incorporata per allocare dinamicamente le risorse di conferenza nei server front-end in modo da distribuire equamente i carichi in tutti i server front-end del pool. In questo modo vengono effettivamente riportate e usate risorse hardware, ma è difficile supportare riunioni di grandi dimensioni (soprattutto senza una pianificazione appropriata). Ad esempio, quando un pool di Lync Server 2013 è in grado di essere eseguito in prossimità della capacità superiore, ogni server front-end può ospitare circa 125 riunioni di dimensione media. L'aggiunta di un'altra piccola riunione non è un problema, ma l'aggiunta di una riunione per gli utenti di 1000 sarebbe un problema, perché i server front-end probabilmente non sarebbero in grado di supportare una riunione di grandi dimensioni contemporaneamente alle altre riunioni di 125.

</div>

<span> </span>

</div>

</div>

</div>

