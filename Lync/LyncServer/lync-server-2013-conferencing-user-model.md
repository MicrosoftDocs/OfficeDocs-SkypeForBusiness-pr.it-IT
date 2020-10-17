---
title: Modello utente per le conferenze di Lync Server 2013
description: Modello utente per le conferenze di Lync Server 2013.
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: The conferencing user model
ms:assetid: ba4bbba9-f2e3-4cab-8eba-b51f12133cab
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205199(v=OCS.15)
ms:contentKeyID: 48185229
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 699f41303b82f4d8fd2864cbf1b29a1c601b826e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2020
ms.locfileid: "48555982"
---
# <a name="the-conferencing-user-model-in-lync-server-2013"></a>Il modello utente per le conferenze in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-10-22_

Una parte critica del modello utente di Lync Server Conferencing è la dimensione della riunione. Dopo avere raccolto i dati dai diversi punti dati, come illustrato nella sezione precedente, è stato possibile determinare quanto segue:

  - Nella maggior parte dei casi le riunioni sono riunioni di piccole dimensioni per la collaborazione con una media di 4-6 partecipanti.

  - All'incirca l'80% delle riunioni ha meno di 20 partecipanti.

  - Il 99,98% delle riunioni ha meno di 100.

Oltre alle dimensioni delle riunioni, nel modello utente per le conferenze vengono inoltre considerati diversi fattori, tra cui i seguenti:

  - **Riunioni**     simultanee Quanti utenti dovrebbero partecipare contemporaneamente a riunioni?

  - **Combinazione multimediale**     Quali tipi di contenuto multimediale sono disponibili e dovrebbero essere utilizzati dagli utenti nelle riunioni?

  - **Tipi**     di utenti Gli utenti sono utenti interni, utenti remoti, utenti federati o utenti anonimi?

  - Tempo per la **rampa di riunioni**     Quanto tempo è necessario per tutti gli utenti di una riunione per partecipare a una riunione?

Per informazioni dettagliate sul modello utente, vedere [User Models in Lync Server 2013](lync-server-2013-user-models.md).

Per determinare il numero di riunioni e utenti da utilizzare per il testing, sono state eseguite le operazioni seguenti:

  - Il numero totale degli utenti di un'organizzazione (ad esempio, 80.000 utenti) è stato moltiplicato per la percentuale di riunioni simultanee (ad esempio, il 5% di tutti gli utenti) per determinare il numero totale di utenti che si prevede partecipino a riunioni nello stesso momento (in questo caso, 4.000 utenti).

  - Suddiviso il numero totale di utenti in base al numero di Lync Server 2013, Front End Server nella distribuzione (ad esempio, 8 Server) per determinare il numero stimato di partecipanti alla riunione per Front End Server (in questo esempio, 500 utenti per Front End Server).

  - Il numero di utenti per Front End Server è stato diviso per la dimensione media delle riunioni (ad esempio, 4 utenti) per determinare il numero medio stimato di riunioni per Front End Server (in questo esempio, 125 riunioni per Front End Server).

  - Per ottenere il carico per ogni supporto su ogni Front End Server, è stato valutato il media mix. Ad esempio, presupponendo che il 75% delle riunioni richieda più di un semplice supporto audio e che il 50% di tali riunioni richieda la condivisione delle applicazioni, una media di 47 riunioni e 188 utenti si connettono contemporaneamente a ogni Front End Server per la condivisione delle applicazioni.

  - I test sono stati eseguiti su riunioni di diverse dimensioni (in base al modello utente di un massimo di 250 utenti in un pool condiviso) per assicurare la scalabilità dei server.

</div>

<span> </span>

</div>

</div>

</div>

